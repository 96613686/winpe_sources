# Microsoft.Crm.BusinessEntities.BusinessProcessObject::IsOperationExecutedViaUpdatePipeline

- ea: `0x5cd00`
- end: `0x5cd82`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::IsOperationExecutedViaUpdatePipeline`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5cc40`

## callees

- `0x5cd00`
- `0x66f10`
- `0x67c10`

## string_xrefs

- `0x5cd12`: `Update`
- `0x5cd30`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x5cd00  ldc.i4.0
0x5cd01  stloc.0
0x5cd02  ldarg.1
0x5cd03  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x5cd08  stloc.1
0x5cd09  ldloc.1
0x5cd0a  brfalse.s loc_5CD1D
0x5cd0c  ldloc.1
0x5cd0d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cd12  ldstr    aUpdate// "Update"
0x5cd17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd1c  stloc.0
0x5cd1d  ldloc.0
0x5cd1e  brtrue.s loc_5CD80
0x5cd20  ldarg.1
0x5cd21  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_RootPluginContext()
0x5cd26  stloc.1
0x5cd27  ldloc.1
0x5cd28  brfalse.s loc_5CD80
0x5cd2a  ldloc.1
0x5cd2b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cd30  ldstr    aUpdate// "Update"
0x5cd35  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd3a  stloc.0
0x5cd3b  ldarg.2
0x5cd3c  ldc.i4.1
0x5cd3d  bne.un.s loc_5CD69
0x5cd3f  ldloc.0
0x5cd40  ldloc.1
0x5cd41  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cd46  ldstr    aSetstate// "SetState"
0x5cd4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd50  brtrue.s loc_5CD64
0x5cd52  ldloc.1
0x5cd53  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cd58  ldstr    aSetstatedynami// "SetStateDynamicEntity"
0x5cd5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd62  br.s     loc_5CD65
0x5cd64  ldc.i4.1
0x5cd65  or
0x5cd66  stloc.0
0x5cd67  br.s     loc_5CD80
0x5cd69  ldarg.2
0x5cd6a  ldc.i4.2
0x5cd6b  bne.un.s loc_5CD80
0x5cd6d  ldloc.0
0x5cd6e  ldloc.1
0x5cd6f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cd74  ldstr    aAssign// "Assign"
0x5cd79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5cd7e  or
0x5cd7f  stloc.0
0x5cd80  ldloc.0
0x5cd81  ret
```
