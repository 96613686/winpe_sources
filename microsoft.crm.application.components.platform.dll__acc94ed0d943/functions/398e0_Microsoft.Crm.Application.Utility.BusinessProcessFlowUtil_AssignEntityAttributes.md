# Microsoft.Crm.Application.Utility.BusinessProcessFlowUtil::AssignEntityAttributes

- ea: `0x398e0`
- end: `0x39a0f`
- name: `Microsoft.Crm.Application.Utility.BusinessProcessFlowUtil::AssignEntityAttributes`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x39840`

## callees

- `0x30e00`
- `0x30e80`
- `0x398e0`
- `0x5b850`
- `0x5b860`
- `0x5bae0`
- `0x5bb40`
- `0x5bb70`
- `0x5be40`
- `0x5e3f0`
- `0x5e570`
- `0x5e580`

## string_xrefs

- `0x399d2`: `processid`
- `0x399aa`: `traversedpath`
- `0x399bc`: `traversedpath`
- `0x399c2`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x398e0  ldarg.0
0x398e1  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x398e6  brfalse.s loc_3995B
0x398e8  ldarg.0
0x398e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x398ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x398f3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x398f8  brfalse.s loc_39928
0x398fa  ldarg.1
0x398fb  ldc.i4.0
0x398fc  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool value)
0x39901  ldarg.1
0x39902  ldarg.0
0x39903  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x39908  callvirt instance void Microsoft.Crm.Application.Platform.EntityProxy::set_BusinessProcessFlowInstanceId(valuetype [mscorlib]System.Guid value)
0x3990d  ldarg.1
0x3990e  ldarg.0
0x3990f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x39914  stloc.2
0x39915  ldloca.s 2
0x39917  ldstr    aB_0// "B"
0x3991c  call     instance string [mscorlib]System.Guid::ToString(string)
0x39921  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Id(string value)
0x39926  br.s     loc_39981
0x39928  ldarg.1
0x39929  ldarg.0
0x3992a  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x3992f  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool value)
0x39934  ldarg.1
0x39935  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3993a  callvirt instance void Microsoft.Crm.Application.Platform.EntityProxy::set_BusinessProcessFlowInstanceId(valuetype [mscorlib]System.Guid value)
0x3993f  ldarg.1
0x39940  ldarg.1
0x39941  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x39946  stloc.2
0x39947  ldloca.s 2
0x39949  constrained. [mscorlib]System.Guid
0x3994f  callvirt instance string [mscorlib]System.Object::ToString()
0x39954  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Id(string value)
0x39959  br.s     loc_39981
0x3995b  ldarg.1
0x3995c  ldarg.0
0x3995d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x39962  callvirt instance void Microsoft.Crm.Application.Platform.EntityProxy::set_BusinessProcessFlowInstanceId(valuetype [mscorlib]System.Guid value)
0x39967  ldarg.1
0x39968  ldarg.0
0x39969  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.EntityProxy::get_BusinessProcessFlowInstanceId()
0x3996e  stloc.2
0x3996f  ldloca.s 2
0x39971  constrained. [mscorlib]System.Guid
0x39977  callvirt instance string [mscorlib]System.Object::ToString()
0x3997c  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Id(string value)
0x39981  ldarg.0
0x39982  ldstr    aStageid// "stageid"
0x39987  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x3998c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x39991  brtrue.s loc_399A9
0x39993  ldarg.1
0x39994  ldstr    aActivestageid// "activestageid"
0x39999  ldarg.0
0x3999a  ldstr    aStageid// "stageid"
0x3999f  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x399a4  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x399a9  ldarg.0
0x399aa  ldstr    aTraversedpath// "traversedpath"
0x399af  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x399b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x399b9  brtrue.s loc_399D1
0x399bb  ldarg.1
0x399bc  ldstr    aTraversedpath// "traversedpath"
0x399c1  ldarg.0
0x399c2  ldstr    aTraversedpath// "traversedpath"
0x399c7  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x399cc  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x399d1  ldarg.1
0x399d2  ldstr    aProcessid// "processid"
0x399d7  ldarg.2
0x399d8  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x399dd  newobj   instance void Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x399e2  stloc.0
0x399e3  ldsfld   class [Microsoft.Crm.Platform.BusinessProcess]Microsoft.Crm.Platform.BusinessProcess.BusinessProcessFlowEntityService Microsoft.Crm.Application.Utility.BusinessProcessFlowUtil::businessProcessFlowEntityService
0x399e8  ldarg.1
0x399e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x399ee  ldarg.0
0x399ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x399f4  callvirt instance string [Microsoft.Crm.Platform.BusinessProcess]Microsoft.Crm.Platform.BusinessProcess.BusinessProcessFlowEntityService::GetParticipatingEntityColumnName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x399f9  stloc.1
0x399fa  ldloc.0
0x399fb  ldarg.0
0x399fc  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x39a01  callvirt instance void Microsoft.Crm.Application.Types.LookupValue::set_ID(string value)
0x39a06  ldarg.1
0x39a07  ldloc.1
0x39a08  ldloc.0
0x39a09  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x39a0e  ret
```
