# Microsoft.Crm.Application.Platform.ServiceCommands.AssignCommand::Execute

- ea: `0x8e150`
- end: `0x8e1b9`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.AssignCommand::Execute`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x59c40`

## callees

- `0x11760`
- `0x30260`
- `0x8e150`
- `0x90e70`

## string_xrefs

- `0x8e183`: `SecurityPrincipal.Team`
- `0x8e1a5`: `SecurityPrincipal.User`

## pseudocode

```c

```

## disassembly

```asm
0x8e150  ldarg.0
0x8e151  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x8e156  pop
0x8e157  leave.s  loc_8E1B8
0x8e159  stloc.0
0x8e15a  ldloc.0
0x8e15b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x8e160  ldc.i4   0x80040231
0x8e165  bne.un.s loc_8E1B6
0x8e167  ldarg.0
0x8e168  ldfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipalType Microsoft.Crm.Application.Platform.ServiceCommands.AssignCommand::assigneeType
0x8e16d  stloc.1
0x8e16e  ldloc.1
0x8e16f  ldc.i4.1
0x8e170  bne.un.s loc_8E194
0x8e172  ldloc.0
0x8e173  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x8e178  ldc.i4.0
0x8e179  box      [mscorlib]System.Int32
0x8e17e  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8e183  ldstr    aSecurityprinci// "SecurityPrincipal.Team"
0x8e188  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8e18d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x8e192  br.s     loc_8E1B4
0x8e194  ldloc.0
0x8e195  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x8e19a  ldc.i4.0
0x8e19b  box      [mscorlib]System.Int32
0x8e1a0  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8e1a5  ldstr    aSecurityprinci_0// "SecurityPrincipal.User"
0x8e1aa  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8e1af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x8e1b4  rethrow
0x8e1b6  rethrow
0x8e1b8  ret
```
