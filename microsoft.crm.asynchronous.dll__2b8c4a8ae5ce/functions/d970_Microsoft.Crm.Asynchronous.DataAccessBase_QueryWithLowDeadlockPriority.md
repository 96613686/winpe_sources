# Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithLowDeadlockPriority

- ea: `0xd970`
- end: `0xd98a`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithLowDeadlockPriority`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xd975`: `\nSET DEADLOCK_PRIORITY LOW\nSET XACT_ABORT ON\nBEGIN TRANSACTION \n{0}\nCOMMIT TRANSACTION`

## pseudocode

```c

```

## disassembly

```asm
0xd970  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd975  ldstr    aSetDeadlockPri_0// "\r\nSET DEADLOCK_PRIORITY LOW\r\nSET XA"...
0xd97a  ldc.i4.1
0xd97b  newarr   [mscorlib]System.Object
0xd980  dup
0xd981  ldc.i4.0
0xd982  ldarg.1
0xd983  stelem.ref
0xd984  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd989  ret
```
