# Microsoft.Crm.PerThreadCacheManager::PostCommitTransactionCacheRemoveHandler

- ea: `0x229e0`
- end: `0x22b10`
- name: `Microsoft.Crm.PerThreadCacheManager::PostCommitTransactionCacheRemoveHandler`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1bb70`
- `0x1bb90`
- `0x22810`
- `0x229e0`
- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x229e8`: `PostCommitTransactionCacheRemoveHandler called in PerThreadCacheManager with PerThreadCacheIdentifier={0}`
- `0x22ae6`: `PostCommitTransactionCacheRemoveHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is empty`
- `0x22aff`: `PostCommitTransactionCacheRemoveHandler called but did not remove PerThreadCacheManager because eventArgs.Parameter is not set/null`

## pseudocode

```c

```

## disassembly

```asm
0x229e0  ldarg.0
0x229e1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x229e6  ldc.i4.s 0x1A
0x229e8  ldstr    aPostcommittran_2// "PostCommitTransactionCacheRemoveHandler"...
0x229ed  ldc.i4.1
0x229ee  newarr   [mscorlib]System.Object
0x229f3  dup
0x229f4  ldc.i4.0
0x229f5  ldarg.0
0x229f6  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x229fb  stelem.ref
0x229fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22a01  ldarg.2
0x22a02  isinst   [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs
0x22a07  stloc.0
0x22a08  ldloc.0
0x22a09  brfalse  loc_22AF7
0x22a0e  ldloc.0
0x22a0f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x22a14  brfalse  loc_22AF7
0x22a19  ldloc.0
0x22a1a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x22a1f  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>
0x22a24  stloc.1
0x22a25  ldloc.1
0x22a26  brfalse  loc_22ADE
0x22a2b  ldloc.1
0x22a2c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::get_Keys()
0x22a31  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::GetEnumerator()
0x22a36  stloc.2
0x22a37  br.s     loc_22AB6
0x22a39  ldloca.s 2
0x22a3b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::get_Current()
0x22a40  stloc.3
0x22a41  ldloc.1
0x22a42  ldloc.3
0x22a43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::get_Item(void)
0x22a48  callvirt instance var<u1> class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item1()
0x22a4d  castclass Microsoft.Crm.ICrmCacheRemove
0x22a52  stloc.s  4
0x22a54  ldloc.1
0x22a55  ldloc.3
0x22a56  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::get_Item(void)
0x22a5b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item2()
0x22a60  stloc.s  5
0x22a62  ldloc.s  5
0x22a64  ldloc.3
0x22a65  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x22a6a  brfalse.s loc_22A77
0x22a6c  ldloc.s  4
0x22a6e  ldc.i4.0
0x22a6f  ldnull
0x22a70  callvirt instance void Microsoft.Crm.ICrmCacheRemove::Flush(bool fireNotification, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22a75  br.s     loc_22AAF
0x22a77  ldloc.s  5
0x22a79  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x22a7e  stloc.s  6
0x22a80  br.s     loc_22A96
0x22a82  ldloca.s 6
0x22a84  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x22a89  stloc.s  7
0x22a8b  ldloc.s  4
0x22a8d  ldloc.s  7
0x22a8f  ldc.i4.0
0x22a90  ldnull
0x22a91  callvirt instance void Microsoft.Crm.ICrmCacheRemove::RemoveEntry(string key, bool fireNotification, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22a96  ldloca.s 6
0x22a98  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x22a9d  brtrue.s loc_22A82
0x22a9f  leave.s  loc_22AAF
0x22aa1  ldloca.s 6
0x22aa3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x22aa9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22aae  endfinally
0x22aaf  ldarg.0
0x22ab0  ldloc.3
0x22ab1  call     instance void Microsoft.Crm.PerThreadCacheManager::Flush(string cacheIdentifier)
0x22ab6  ldloca.s 2
0x22ab8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::MoveNext()
0x22abd  brtrue   loc_22A39
0x22ac2  leave.s  loc_22AD2
0x22ac4  ldloca.s 2
0x22ac6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>
0x22acc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22ad1  endfinally
0x22ad2  ldarg.0
0x22ad3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>> Microsoft.Crm.PerThreadCacheManager::_cacheEntriesMarkedForRemoval
0x22ad8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::Clear()
0x22add  ret
0x22ade  ldnull
0x22adf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22ae4  ldc.i4.s 0x14
0x22ae6  ldstr    aPostcommittran_3// "PostCommitTransactionCacheRemoveHandler"...
0x22aeb  ldc.i4.0
0x22aec  newarr   [mscorlib]System.Object
0x22af1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22af6  ret
0x22af7  ldnull
0x22af8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22afd  ldc.i4.s 0x14
0x22aff  ldstr    aPostcommittran_4// "PostCommitTransactionCacheRemoveHandler"...
0x22b04  ldc.i4.0
0x22b05  newarr   [mscorlib]System.Object
0x22b0a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22b0f  ret
```
