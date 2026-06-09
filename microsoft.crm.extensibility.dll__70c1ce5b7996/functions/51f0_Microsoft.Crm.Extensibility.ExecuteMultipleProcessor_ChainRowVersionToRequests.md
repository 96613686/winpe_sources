# Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::ChainRowVersionToRequests

- ea: `0x51f0`
- end: `0x52a4`
- name: `Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::ChainRowVersionToRequests`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x4f00`

## callees

- `0x51f0`

## string_xrefs

- `0x5202`: `Update`
- `0x5256`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x51f0  ldarg.2
0x51f1  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Count()
0x51f6  ldc.i4.0
0x51f7  ble      loc_52A3
0x51fc  ldarg.0
0x51fd  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x5202  ldstr    aUpdate// "Update"
0x5207  ldc.i4.3
0x5208  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x520d  brfalse.s loc_5250
0x520f  ldarg.0
0x5210  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5215  ldstr    aTarget// "Target"
0x521a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x521f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x5224  stloc.0
0x5225  ldloc.0
0x5226  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x522b  stloc.1
0x522c  ldarg.2
0x522d  ldloc.1
0x522e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0x5233  brfalse.s loc_52A3
0x5235  ldloc.0
0x5236  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RowVersion()
0x523b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5240  brfalse.s loc_52A3
0x5242  ldloc.0
0x5243  ldarg.2
0x5244  ldloc.1
0x5245  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0x524a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_RowVersion(string)
0x524f  ret
0x5250  ldarg.0
0x5251  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x5256  ldstr    aDelete// "Delete"
0x525b  ldc.i4.3
0x525c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5261  brfalse.s loc_52A3
0x5263  ldarg.0
0x5264  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5269  ldstr    aTarget// "Target"
0x526e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5273  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5278  stloc.2
0x5279  ldloc.2
0x527a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x527f  stloc.3
0x5280  ldarg.2
0x5281  ldloc.3
0x5282  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0x5287  brfalse.s loc_52A3
0x5289  ldloc.2
0x528a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_RowVersion()
0x528f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5294  brfalse.s loc_52A3
0x5296  ldloc.2
0x5297  ldarg.2
0x5298  ldloc.3
0x5299  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0x529e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_RowVersion(string)
0x52a3  ret
```
