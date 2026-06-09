# <>c__DisplayClass7_0::<CreatePriorityScheduler>b__1

- ea: `0xf8f0`
- end: `0xf8fd`
- name: `<>c__DisplayClass7_0::<CreatePriorityScheduler>b__1`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xa9a0`

## pseudocode

```c

```

## disassembly

```asm
0xf8f0  ldarg.0
0xf8f1  ldfld    string <>c__DisplayClass7_0::jobSqlServer
0xf8f6  ldarg.1
0xf8f7  call     void Microsoft.Crm.Asynchronous.TransactionLogShrinkJob::Execute(string sqlServer, class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction data)
0xf8fc  ret
```
