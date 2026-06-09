# Microsoft.Crm.StaticPerThreadCacheManager`1::RemovePerThreadCacheManagerForCurrentThread

- ea: `0x22470`
- end: `0x224da`
- name: `Microsoft.Crm.StaticPerThreadCacheManager`1::RemovePerThreadCacheManagerForCurrentThread`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x22470`

## string_xrefs

- `0x22490`: `StaticPerThreadCacheManager: Could not remove PerThreadCacheManager For Current Thread in StaticPerThreadCacheManager`
- `0x224a3`: `StaticPerThreadCacheManager failed to remove entry for thread {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x22470  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>> class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::_perThreadCacheManagers
0x22475  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2247a  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x2247f  ldloca.s 0
0x22481  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>>::TryRemove(var<u1>, !!T0)
0x22486  brtrue.s loc_224A0
0x22488  ldnull
0x22489  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2248e  ldc.i4.s 0x14
0x22490  ldstr    aStaticperthrea_1// "StaticPerThreadCacheManager: Could not "...
0x22495  ldc.i4.0
0x22496  newarr   [mscorlib]System.Object
0x2249b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x224a0  leave.s  loc_224D9
0x224a2  stloc.1
0x224a3  ldstr    aStaticperthrea_2// "StaticPerThreadCacheManager failed to r"...
0x224a8  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x224ad  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x224b2  box      [mscorlib]System.Int32
0x224b7  ldloc.1
0x224b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x224bd  call     string [mscorlib]System.String::Format(string, object, object)
0x224c2  stloc.2
0x224c3  ldloc.1
0x224c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x224c9  ldc.i4.s 0x19
0x224cb  ldloc.2
0x224cc  ldc.i4.0
0x224cd  newarr   [mscorlib]System.Object
0x224d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x224d7  leave.s  loc_224D9
0x224d9  ret
```
