# Microsoft.Crm.BusinessEntities.CrmBaseSecurityExtensionFactory::.cctor

- ea: `0x84b30`
- end: `0x84b73`
- name: `Microsoft.Crm.BusinessEntities.CrmBaseSecurityExtensionFactory::.cctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x84b44`: `Creating instance of CrmSecurityExtensionFactory`
- `0x84b59`: `Microsoft.Crm.ObjectModel.CrmSecurityExtensionFactory`

## pseudocode

```c

```

## disassembly

```asm
0x84b30  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x84b35  ldc.i4.s 0x14
0x84b37  ldstr    a0// "{0}"
0x84b3c  ldc.i4.1
0x84b3d  newarr   [mscorlib]System.Object
0x84b42  dup
0x84b43  ldc.i4.0
0x84b44  ldstr    aCreatingInstan_1// "Creating instance of CrmSecurityExtensi"...
0x84b49  stelem.ref
0x84b4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x84b4f  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x84b54  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x84b59  ldstr    aMicrosoftCrmOb_4// "Microsoft.Crm.ObjectModel.CrmSecurityEx"...
0x84b5e  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x84b63  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x84b68  castclass Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory
0x84b6d  stsfld   class Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory Microsoft.Crm.BusinessEntities.CrmBaseSecurityExtensionFactory::_instance
0x84b72  ret
```
