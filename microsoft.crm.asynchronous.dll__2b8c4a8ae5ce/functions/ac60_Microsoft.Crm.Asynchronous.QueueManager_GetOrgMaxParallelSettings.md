# Microsoft.Crm.Asynchronous.QueueManager::GetOrgMaxParallelSettings

- ea: `0xac60`
- end: `0xacba`
- name: `Microsoft.Crm.Asynchronous.QueueManager::GetOrgMaxParallelSettings`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa9d0`

## callees

- `0xac60`
- `0xb370`
- `0xd0a0`

## string_xrefs

- `0xac86`: `OrgMaxThreadCount`

## pseudocode

```c

```

## disassembly

```asm
0xac60  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::.ctor()
0xac65  stloc.0
0xac66  ldarg.0
0xac67  call     instance class Microsoft.Crm.Asynchronous.IQueueConfiguration Microsoft.Crm.Asynchronous.QueueManager::get_Configuration()
0xac6c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0xac71  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Keys()
0xac76  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xac7b  stloc.1
0xac7c  br.s     loc_ACA4
0xac7e  ldloc.1
0xac7f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0xac84  stloc.2
0xac85  ldloc.2
0xac86  ldstr    aOrgmaxthreadco// "OrgMaxThreadCount"
0xac8b  ldc.i4.s 0x14
0xac8d  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetOrganizationSettingOrDefault(valuetype [mscorlib]System.Guid orgId, string settingName, int32 defaultValue)
0xac92  stloc.3
0xac93  ldloc.0
0xac94  ldloc.2
0xac95  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::ContainsKey(var<u1>)
0xac9a  brtrue.s loc_ACA4
0xac9c  ldloc.0
0xac9d  ldloc.2
0xac9e  ldloc.3
0xac9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::Add(var<u1>, !!T0)
0xaca4  ldloc.1
0xaca5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xacaa  brtrue.s loc_AC7E
0xacac  leave.s  loc_ACB8
0xacae  ldloc.1
0xacaf  brfalse.s loc_ACB7
0xacb1  ldloc.1
0xacb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xacb7  endfinally
0xacb8  ldloc.0
0xacb9  ret
```
