# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsCommunicationActivity

- ea: `0x1fd90`
- end: `0x1fdfa`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsCommunicationActivity`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1fe00`
- `0x1ff90`
- `0x2bfb0`

## callees

- `0x1fd90`
- `0x20020`

## string_xrefs

- `0x1fd96`: `_IsCommunicationActivity`

## pseudocode

```c

```

## disassembly

```asm
0x1fd90  ldarg.0
0x1fd91  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1fd96  ldstr    aIscommunicatio// "_IsCommunicationActivity"
0x1fd9b  call     string [mscorlib]System.String::Concat(string, string)
0x1fda0  stloc.0
0x1fda1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1fda6  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1fdab  ldloc.0
0x1fdac  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x1fdb1  brfalse.s loc_1FDC9
0x1fdb3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1fdb8  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1fdbd  ldloc.0
0x1fdbe  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1fdc3  unbox.any [mscorlib]System.Boolean
0x1fdc8  ret
0x1fdc9  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1fdce  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1fdd3  ldloc.0
0x1fdd4  ldarg.0
0x1fdd5  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOrganizationContext()
0x1fdda  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fddf  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity
0x1fde4  ldnull
0x1fde5  cgt.un
0x1fde7  box      [mscorlib]System.Boolean
0x1fdec  dup
0x1fded  stloc.1
0x1fdee  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1fdf3  ldloc.1
0x1fdf4  unbox.any [mscorlib]System.Boolean
0x1fdf9  ret
```
