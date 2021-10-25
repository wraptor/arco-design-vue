```yaml
title:
  zh-CN: 排序和筛选
  en-US: Sort & Filter
```

## zh-CN

通过设置 `columns` 中的 `sortable` 和 `filterable` 属性，可以配置排序和筛选功能。

---

## en-US

You can configure the sorting and filtering functions by setting the `sortable` and `filterable` attributes in `columns`.

---

```vue
<template>
  <a-table :columns="columns" :data="data" />
</template>

<script>
export default {
  data() {
    return {
      columns: [
        {
          title: 'Name',
          dataIndex: 'name',
          sortable: {
            sortDirections: ['ascend', 'descend']
          }
        },
        {
          title: 'Salary',
          dataIndex: 'salary',
          sortable: {
            sortDirections: ['ascend']
          },
          filterable: {
            filters: [
              {
                text: '> 20000',
                value: '20000',
              },
              {
                text: '> 30000',
                value: '30000',
              }
            ],
            filter: (value, row) => row.salary > value,
            multiple: true
          }
        },
        {
          title: 'Address',
          dataIndex: 'address',
          filterable: {
            filters: [
              {
                text: 'London',
                value: 'London',
              },
              {
                text: 'Paris',
                value: 'Paris',
              },
            ],
            filter: (value, row) => row.address.includes(value),
          }
        },
        {
          title: 'Email',
          dataIndex: 'email',
        },
      ],
      data: [{
        key: '1',
        name: 'Jane Doe',
        salary: 23000,
        address: '32 Park Road, London',
        email: 'jane.doe@example.com'
      }, {
        key: '2',
        name: 'Alisa Ross',
        salary: 25000,
        address: '35 Park Road, London',
        email: 'alisa.ross@example.com'
      }, {
        key: '3',
        name: 'Kevin Sandra',
        salary: 22000,
        address: '31 Park Road, London',
        email: 'kevin.sandra@example.com'
      }, {
        key: '4',
        name: 'Ed Hellen',
        salary: 17000,
        address: '42 Park Road, London',
        email: 'ed.hellen@example.com'
      }, {
        key: '5',
        name: 'William Smith',
        salary: 27000,
        address: '62 Park Road, London',
        email: 'william.smith@example.com'
      }]
    }
  }
}
</script>
```