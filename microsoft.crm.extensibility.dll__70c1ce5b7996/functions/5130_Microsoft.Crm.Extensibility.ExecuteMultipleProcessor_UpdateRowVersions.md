# Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::UpdateRowVersions

- ea: `0x5130`
- end: `0x51e9`
- name: `Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::UpdateRowVersions`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4f00`

## callees

- `0x5130`

## string_xrefs

- `0x5149`: `Update`
- `0x5136`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x5130  ldarg.0
0x5131  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x5136  ldstr    aCreate// "Create"
0x513b  ldc.i4.3
0x513c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5141  brtrue.s loc_5159
0x5143  ldarg.0
0x5144  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x5149  ldstr    aUpdate// "Update"
0x514e  ldc.i4.3
0x514f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5154  brfalse  loc_51E8
0x5159  ldarg.0
0x515a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x515f  ldstr    aReturnrowversi// "ReturnRowVersion"
0x5164  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5169  brfalse.s loc_51E8
0x516b  ldarg.0
0x516c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5171  ldstr    aReturnrowversi// "ReturnRowVersion"
0x5176  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x517b  unbox.any [mscorlib]System.Boolean
0x5180  brfalse.s loc_51E8
0x5182  ldarg.3
0x5183  brfalse.s loc_51BB
0x5185  ldarg.0
0x5186  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x518b  ldstr    aTarget// "Target"
0x5190  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5195  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x519a  stloc.0
0x519b  ldloc.0
0x519c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RowVersion()
0x51a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51a6  brtrue.s loc_51E8
0x51a8  ldarg.2
0x51a9  ldloc.0
0x51aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x51af  ldloc.0
0x51b0  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RowVersion()
0x51b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::set_Item(var<u1>, !!T0)
0x51ba  ret
0x51bb  ldarg.1
0x51bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::get_Response()
0x51c1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x51c6  ldstr    aEntityreferenc_0// "EntityReference"
0x51cb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x51d0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x51d5  stloc.1
0x51d6  ldarg.2
0x51d7  ldloc.1
0x51d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x51dd  ldloc.1
0x51de  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_RowVersion()
0x51e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::set_Item(var<u1>, !!T0)
0x51e8  ret
```
