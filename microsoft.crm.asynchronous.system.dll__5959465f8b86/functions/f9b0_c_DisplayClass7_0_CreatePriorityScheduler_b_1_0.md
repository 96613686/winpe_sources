# <>c__DisplayClass7_0::<CreatePriorityScheduler>b__1_0

- ea: `0xf9b0`
- end: `0xf9bd`
- name: `<>c__DisplayClass7_0::<CreatePriorityScheduler>b__1_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xaa50`

## pseudocode

```c

```

## disassembly

```asm
0xf9b0  ldarg.0
0xf9b1  ldfld    string <>c__DisplayClass7_0::jobSqlServer
0xf9b6  ldarg.1
0xf9b7  call     void Microsoft.Crm.Asynchronous.TransactionLogTruncationJob::Execute(string sqlServer, class Microsoft.Crm.Asynchronous.TransactionLogData data)
0xf9bc  ret
```
