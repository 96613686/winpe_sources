# Microsoft.Crm.BusinessEntities.SolutionManagementExtensionBaseFactory::.cctor

- ea: `0x84bf0`
- end: `0x84c56`
- name: `Microsoft.Crm.BusinessEntities.SolutionManagementExtensionBaseFactory::.cctor`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x84c19`: `Microsoft.Crm.ObjectModel.SolutionManagementExtension`
- `0x84c3c`: `Microsoft.Crm.ObjectModel.SolutionPreDeleteHandler`

## pseudocode

```c

```

## disassembly

```asm
0x84bf0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x84bf5  ldc.i4.s 0x14
0x84bf7  ldstr    a0// "{0}"
0x84bfc  ldc.i4.1
0x84bfd  newarr   [mscorlib]System.Object
0x84c02  dup
0x84c03  ldc.i4.0
0x84c04  ldstr    aCreatingInstan_2// "Creating instance of SolutionManagement"...
0x84c09  stelem.ref
0x84c0a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x84c0f  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x84c14  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x84c19  ldstr    aMicrosoftCrmOb_5// "Microsoft.Crm.ObjectModel.SolutionManag"...
0x84c1e  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x84c23  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x84c28  castclass Microsoft.Crm.BusinessEntities.ICrmExtension
0x84c2d  stsfld   class Microsoft.Crm.BusinessEntities.ICrmExtension Microsoft.Crm.BusinessEntities.SolutionManagementExtensionBaseFactory::_instance
0x84c32  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x84c37  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x84c3c  ldstr    aMicrosoftCrmOb_6// "Microsoft.Crm.ObjectModel.SolutionPreDe"...
0x84c41  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x84c46  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x84c4b  castclass Microsoft.Crm.BusinessEntities.ISolutionPreDeleteHandler
0x84c50  stsfld   class Microsoft.Crm.BusinessEntities.ISolutionPreDeleteHandler Microsoft.Crm.BusinessEntities.SolutionManagementExtensionBaseFactory::_preDeleteHandler
0x84c55  ret
```
