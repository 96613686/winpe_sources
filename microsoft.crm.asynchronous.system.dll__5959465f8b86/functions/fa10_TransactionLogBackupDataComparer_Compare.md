# TransactionLogBackupDataComparer::Compare

- ea: `0xfa10`
- end: `0xfa59`
- name: `TransactionLogBackupDataComparer::Compare`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xacf0`
- `0xfa10`

## pseudocode

```c

```

## disassembly

```asm
0xfa10  ldarg.1
0xfa11  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime()
0xfa16  stloc.0
0xfa17  ldloca.s 0
0xfa19  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xfa1e  brtrue.s loc_FA22
0xfa20  ldc.i4.m1
0xfa21  ret
0xfa22  ldarg.2
0xfa23  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime()
0xfa28  stloc.0
0xfa29  ldloca.s 0
0xfa2b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xfa30  brtrue.s loc_FA34
0xfa32  ldc.i4.1
0xfa33  ret
0xfa34  ldarg.1
0xfa35  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime()
0xfa3a  stloc.0
0xfa3b  ldloca.s 0
0xfa3d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xfa42  stloc.1
0xfa43  ldloca.s 1
0xfa45  ldarg.2
0xfa46  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.TransactionLogBackupData::get_LastBackupDateTime()
0xfa4b  stloc.0
0xfa4c  ldloca.s 0
0xfa4e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xfa53  call     instance int32 [mscorlib]System.DateTime::CompareTo(valuetype [mscorlib]System.DateTime)
0xfa58  ret
```
