# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::ToJson

- ea: `0x35ae0`
- end: `0x35bed`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::ToJson`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x2ec80`

## callees

- `0x359c0`
- `0x359e0`
- `0x35a00`
- `0x35a20`
- `0x35a40`
- `0x35a60`
- `0x35a80`
- `0x35aa0`
- `0x35ac0`
- `0x3a340`
- `0x3a390`
- `0x3a3e0`

## string_xrefs

- `0x35b3a`: `pluginTypeId`
- `0x35b77`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x35ae0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x35ae5  dup
0x35ae6  ldstr    asc_6E6E6// "{"
0x35aeb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35af0  pop
0x35af1  dup
0x35af2  ldstr    aName_0// "name"
0x35af7  ldarg.0
0x35af8  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Name()
0x35afd  ldc.i4.0
0x35afe  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b08  pop
0x35b09  dup
0x35b0a  ldstr    aGroupname// "groupName"
0x35b0f  ldarg.0
0x35b10  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_GroupName()
0x35b15  ldc.i4.1
0x35b16  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b20  pop
0x35b21  dup
0x35b22  ldstr    aTypename_0// "typeName"
0x35b27  ldarg.0
0x35b28  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_TypeName()
0x35b2d  ldc.i4.1
0x35b2e  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b33  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b38  pop
0x35b39  dup
0x35b3a  ldstr    aPlugintypeid// "pluginTypeId"
0x35b3f  ldarg.0
0x35b40  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x35b45  stloc.0
0x35b46  ldloca.s 0
0x35b48  ldstr    aB// "B"
0x35b4d  call     instance string [mscorlib]System.Guid::ToString(string)
0x35b52  ldc.i4.1
0x35b53  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b58  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b5d  pop
0x35b5e  dup
0x35b5f  ldstr    aAssemblyname// "assemblyName"
0x35b64  ldarg.0
0x35b65  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_AssemblyName()
0x35b6a  ldc.i4.1
0x35b6b  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b70  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b75  pop
0x35b76  dup
0x35b77  ldstr    aPublickeytoken_0// "publicKeyToken"
0x35b7c  ldarg.0
0x35b7d  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PublicKeyToken()
0x35b82  ldc.i4.1
0x35b83  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35b88  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35b8d  pop
0x35b8e  dup
0x35b8f  ldstr    aCulture_0// "culture"
0x35b94  ldarg.0
0x35b95  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Culture()
0x35b9a  ldc.i4.1
0x35b9b  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35ba0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35ba5  pop
0x35ba6  dup
0x35ba7  ldstr    aAssemblyversio// "assemblyVersion"
0x35bac  ldarg.0
0x35bad  call     instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_AssemblyVersion()
0x35bb2  ldc.i4.1
0x35bb3  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetPropertyJson(string propertyName, string propertyValue, bool prependComma)
0x35bb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35bbd  pop
0x35bbe  dup
0x35bbf  ldstr    aIsnet4// "isNet4"
0x35bc4  ldarg.0
0x35bc5  callvirt instance bool Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x35bca  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x35bcf  ldc.i4.1
0x35bd0  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x35bd5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35bda  pop
0x35bdb  dup
0x35bdc  ldstr    asc_6E70E// "}"
0x35be1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35be6  pop
0x35be7  callvirt instance string [mscorlib]System.Object::ToString()
0x35bec  ret
```
