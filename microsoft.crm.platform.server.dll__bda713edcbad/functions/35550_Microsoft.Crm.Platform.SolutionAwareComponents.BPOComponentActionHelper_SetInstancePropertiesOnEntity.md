# Microsoft.Crm.Platform.SolutionAwareComponents.BPOComponentActionHelper::SetInstancePropertiesOnEntity

- ea: `0x35550`
- end: `0x355b6`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.BPOComponentActionHelper::SetInstancePropertiesOnEntity`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x3f2f0`
- `0x3f3e0`
- `0x3f4e0`
- `0x3f890`

## callees

- `0x35550`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`

## string_xrefs

- `0x35578`: `componentstate`
- `0x35567`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x35550  ldarg.1
0x35551  ldstr    aSolutionid_0// "solutionid"
0x35556  ldarg.0
0x35557  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3555c  box      [mscorlib]System.Guid
0x35561  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x35566  ldarg.1
0x35567  ldstr    aOverwritetime_0// "overwritetime"
0x3556c  ldarg.0
0x3556d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x35572  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x35577  ldarg.1
0x35578  ldstr    aComponentstate// "componentstate"
0x3557d  ldarg.0
0x3557e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x35583  box      [mscorlib]System.Int32
0x35588  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x3558d  ldarg.0
0x3558e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x35593  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35598  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3559d  brfalse.s loc_355B5
0x3559f  ldarg.1
0x355a0  ldstr    aSupportingsolu// "supportingsolutionid"
0x355a5  ldarg.0
0x355a6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x355ab  box      [mscorlib]System.Guid
0x355b0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x355b5  ret
```
