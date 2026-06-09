# Microsoft.Crm.StaticPerThreadCacheManager`1::PostRollbackTransactionClearPerThreadCacheDictionaryHandler

- ea: `0x223e0`
- end: `0x2244f`
- name: `Microsoft.Crm.StaticPerThreadCacheManager`1::PostRollbackTransactionClearPerThreadCacheDictionaryHandler`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x223e0`

## string_xrefs

- `0x223e8`: `PostRollbackTransactionClearPerThreadCacheDictionaryHandler called in StaticPerThreadCacheManager`
- `0x22425`: `PostRollbackTransactionClearPerThreadCacheDictionaryHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is false`
- `0x2243e`: `PostRollbackTransactionClearPerThreadCacheDictionaryHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is not set/null`

## pseudocode

```c

```

## disassembly

```asm
0x223e0  ldnull
0x223e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x223e6  ldc.i4.s 0x14
0x223e8  ldstr    aPostrollbacktr// "PostRollbackTransactionClearPerThreadCa"...
0x223ed  ldc.i4.0
0x223ee  newarr   [mscorlib]System.Object
0x223f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x223f8  ldarg.1
0x223f9  isinst   [Microsoft.Crm.Core]Microsoft.Crm.RollbackTransactionEventArgs
0x223fe  stloc.0
0x223ff  ldloc.0
0x22400  brfalse.s loc_22436
0x22402  ldloc.0
0x22403  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.RollbackTransactionEventArgs::get_Parameter()
0x22408  brfalse.s loc_22436
0x2240a  ldloc.0
0x2240b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.RollbackTransactionEventArgs::get_Parameter()
0x22410  unbox.any [mscorlib]System.Boolean
0x22415  brfalse.s loc_2241D
0x22417  call     void class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::RemovePerThreadCacheManagerForCurrentThread()
0x2241c  ret
0x2241d  ldnull
0x2241e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22423  ldc.i4.s 0x14
0x22425  ldstr    aPostrollbacktr_0// "PostRollbackTransactionClearPerThreadCa"...
0x2242a  ldc.i4.0
0x2242b  newarr   [mscorlib]System.Object
0x22430  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22435  ret
0x22436  ldnull
0x22437  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2243c  ldc.i4.s 0x14
0x2243e  ldstr    aPostrollbacktr_1// "PostRollbackTransactionClearPerThreadCa"...
0x22443  ldc.i4.0
0x22444  newarr   [mscorlib]System.Object
0x22449  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2244e  ret
```
