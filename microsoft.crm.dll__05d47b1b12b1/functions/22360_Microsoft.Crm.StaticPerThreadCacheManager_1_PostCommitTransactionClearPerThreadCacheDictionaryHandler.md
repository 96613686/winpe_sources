# Microsoft.Crm.StaticPerThreadCacheManager`1::PostCommitTransactionClearPerThreadCacheDictionaryHandler

- ea: `0x22360`
- end: `0x223ce`
- name: `Microsoft.Crm.StaticPerThreadCacheManager`1::PostCommitTransactionClearPerThreadCacheDictionaryHandler`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x22360`

## string_xrefs

- `0x22367`: `PostCommitTransactionClearPerThreadCacheDictionaryHandler called in StaticPerThreadCacheManager`
- `0x223a4`: `PostCommitTransactionClearPerThreadCacheDictionaryHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is false`
- `0x223bd`: `PostCommitTransactionClearPerThreadCacheDictionaryHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is not set/null`

## pseudocode

```c

```

## disassembly

```asm
0x22360  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22365  ldc.i4.s 0x14
0x22367  ldstr    aPostcommittran// "PostCommitTransactionClearPerThreadCach"...
0x2236c  ldc.i4.0
0x2236d  newarr   [mscorlib]System.Object
0x22372  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22377  ldarg.1
0x22378  isinst   [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs
0x2237d  stloc.0
0x2237e  ldloc.0
0x2237f  brfalse.s loc_223B5
0x22381  ldloc.0
0x22382  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x22387  brfalse.s loc_223B5
0x22389  ldloc.0
0x2238a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x2238f  unbox.any [mscorlib]System.Boolean
0x22394  brfalse.s loc_2239C
0x22396  call     void class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::RemovePerThreadCacheManagerForCurrentThread()
0x2239b  ret
0x2239c  ldnull
0x2239d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x223a2  ldc.i4.s 0x14
0x223a4  ldstr    aPostcommittran_0// "PostCommitTransactionClearPerThreadCach"...
0x223a9  ldc.i4.0
0x223aa  newarr   [mscorlib]System.Object
0x223af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x223b4  ret
0x223b5  ldnull
0x223b6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x223bb  ldc.i4.s 0x14
0x223bd  ldstr    aPostcommittran_1// "PostCommitTransactionClearPerThreadCach"...
0x223c2  ldc.i4.0
0x223c3  newarr   [mscorlib]System.Object
0x223c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x223cd  ret
```
