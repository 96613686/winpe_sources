# EntityLoader::LoadCacheData

- ea: `0xa7ee0`
- end: `0xa7ffb`
- name: `EntityLoader::LoadCacheData`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1be70`
- `0x317f0`
- `0x32110`
- `0x32130`
- `0x32150`
- `0x32170`
- `0x32190`
- `0x321b0`
- `0x321d0`
- `0x321f0`
- `0x32210`
- `0x32230`
- `0x32250`
- `0x5be20`
- `0xa7ee0`

## string_xrefs

- `0xa7f05`: `formxml`
- `0xa7f88`: `formxml`
- `0xa7f1b`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0xa7ee0  ldarg.1
0xa7ee1  ldarg.2
0xa7ee2  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve(class Microsoft.Crm.Application.Forms.FormDescriptorCacheKey key, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xa7ee7  stloc.0
0xa7ee8  newobj   instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::.ctor()
0xa7eed  dup
0xa7eee  ldloc.0
0xa7eef  ldstr    aFormid// "formid"
0xa7ef4  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7ef9  unbox.any [mscorlib]System.Guid
0xa7efe  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_FormId(valuetype [mscorlib]System.Guid value)
0xa7f03  dup
0xa7f04  ldloc.0
0xa7f05  ldstr    aFormxml// "formxml"
0xa7f0a  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f0f  castclass [mscorlib]System.String
0xa7f14  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_FormXml(string value)
0xa7f19  dup
0xa7f1a  ldloc.0
0xa7f1b  ldstr    aComponentstate// "componentstate"
0xa7f20  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f25  unbox.any [mscorlib]System.Int32
0xa7f2a  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_CompState(int32 value)
0xa7f2f  dup
0xa7f30  ldloc.0
0xa7f31  ldstr    aSolutionid_0// "solutionid"
0xa7f36  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f3b  unbox.any [mscorlib]System.Guid
0xa7f40  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_SolutionId(valuetype [mscorlib]System.Guid value)
0xa7f45  dup
0xa7f46  ldloc.0
0xa7f47  ldstr    aObjecttypecode// "objecttypecode"
0xa7f4c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f51  brtrue.s loc_A7F56
0xa7f53  ldc.i4.0
0xa7f54  br.s     loc_A7F66
0xa7f56  ldloc.0
0xa7f57  ldstr    aObjecttypecode// "objecttypecode"
0xa7f5c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f61  unbox.any [mscorlib]System.Int32
0xa7f66  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_Otc(int32 value)
0xa7f6b  dup
0xa7f6c  ldloc.0
0xa7f6d  ldstr    aType// "type"
0xa7f72  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f77  unbox.any [mscorlib]System.Int32
0xa7f7c  call     valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::ConvertSdkFormTypeToAppFormType(int32 formType)
0xa7f81  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_FormType(valuetype Microsoft.Crm.Application.FormType value)
0xa7f86  dup
0xa7f87  ldloc.0
0xa7f88  ldstr    aFormxml// "formxml"
0xa7f8d  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7f92  castclass [mscorlib]System.String
0xa7f97  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xa7f9c  ldstr    aForm// "//form"
0xa7fa1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa7fa6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xa7fab  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa7fb0  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_VersionHash(int32 value)
0xa7fb5  dup
0xa7fb6  ldloc.0
0xa7fb7  ldstr    aVersionnumber// "versionnumber"
0xa7fbc  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7fc1  unbox.any [mscorlib]System.Int64
0xa7fc6  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_VersionNumber(int64 value)
0xa7fcb  dup
0xa7fcc  ldloc.0
0xa7fcd  ldstr    aFormpresentati// "formpresentation"
0xa7fd2  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7fd7  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode
0xa7fdc  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_FormPresentation(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode value)
0xa7fe1  dup
0xa7fe2  ldloc.0
0xa7fe3  ldstr    aFormactivation// "formactivationstate"
0xa7fe8  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0xa7fed  unbox.any [mscorlib]System.Int32
0xa7ff2  ldc.i4.1
0xa7ff3  ceq
0xa7ff5  callvirt instance void Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::set_IsActive(bool value)
0xa7ffa  ret
```
