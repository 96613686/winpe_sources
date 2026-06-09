# Microsoft.Crm.Common.InterfaceService::LoadFromConfig

- ea: `0x970`
- end: `0xa2a`
- name: `Microsoft.Crm.Common.InterfaceService::LoadFromConfig`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x870`

## callees

- `0x700`
- `0x730`
- `0x7a0`
- `0x7b0`
- `0x970`
- `0xa30`
- `0x1d40`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldc.i4.8
0x971  ldc.i4.s 0xB
0x973  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>>::.ctor(int32, int32)
0x978  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>> Microsoft.Crm.Common.InterfaceService::_services
0x97d  call     void Microsoft.Crm.Common.InterfaceMapper::LoadMapping()
0x982  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Common.InterfaceMapInfo> Microsoft.Crm.Common.InterfaceMapper::get_InterfaceMapValues()
0x987  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Common.InterfaceMapInfo>::GetEnumerator()
0x98c  stloc.0
0x98d  br       loc_A12
0x992  ldloc.0
0x993  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Common.InterfaceMapInfo>::get_Current()
0x998  stloc.1
0x999  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x99e  ldloc.1
0x99f  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass()
0x9a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x9a9  stloc.2
0x9aa  dup
0x9ab  ldloc.1
0x9ac  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_TargetClass()
0x9b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x9b6  stfld    class [mscorlib]System.Type <>c__DisplayClass6_0::destType
0x9bb  ldloc.2
0x9bc  ldnull
0x9bd  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9c2  brfalse.s loc_9DA
0x9c4  ldstr    aSourceClassNot// "Source class not found : "
0x9c9  ldloc.1
0x9ca  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass()
0x9cf  call     string [mscorlib]System.String::Concat(string, string)
0x9d4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9d9  throw
0x9da  dup
0x9db  ldfld    class [mscorlib]System.Type <>c__DisplayClass6_0::destType
0x9e0  ldnull
0x9e1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9e6  brfalse.s loc_9FE
0x9e8  ldstr    aTargetClassNot// "Target class not found : "
0x9ed  ldloc.1
0x9ee  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_TargetClass()
0x9f3  call     string [mscorlib]System.String::Concat(string, string)
0x9f8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9fd  throw
0x9fe  ldftn    instance object <>c__DisplayClass6_0::<LoadFromConfig>b__0()
0xa04  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0xa09  stloc.3
0xa0a  ldloc.2
0xa0b  ldloc.3
0xa0c  ldc.i4.1
0xa0d  call     void Microsoft.Crm.Common.InterfaceService::Set(class [mscorlib]System.Type interfaceType, class [mscorlib]System.Func`1<object> serviceConstructor, bool overrideExisting)
0xa12  ldloc.0
0xa13  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa18  brtrue   loc_992
0xa1d  leave.s  loc_A29
0xa1f  ldloc.0
0xa20  brfalse.s loc_A28
0xa22  ldloc.0
0xa23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa28  endfinally
0xa29  ret
```
