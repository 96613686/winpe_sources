# Microsoft.Crm.BusinessEntities.BusinessProcessObject::CreateOrganizationPOA

- ea: `0x57790`
- end: `0x57837`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::CreateOrganizationPOA`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x57760`
- `0x57860`

## callees

- `0x57790`

## string_xrefs

- `0x57790`: `PrincipalObjectAccess`
- `0x577f9`: `accessrightsmask`
- `0x5780e`: `inheritedaccessrightsmask`
- `0x57825`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x57790  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x57795  ldarg.3
0x57796  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5779b  stloc.0
0x5779c  ldloc.0
0x5779d  ldstr    aPrincipalid// "principalid"
0x577a2  ldarg.3
0x577a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x577a8  box      [mscorlib]System.Guid
0x577ad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x577b2  ldloc.0
0x577b3  ldstr    aPrincipaltypec// "principaltypecode"
0x577b8  ldc.i4   0x3FB
0x577bd  box      [mscorlib]System.Int32
0x577c2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x577c7  ldloc.0
0x577c8  ldstr    aObjectid// "objectid"
0x577cd  ldarg.1
0x577ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x577d3  box      [mscorlib]System.Guid
0x577d8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x577dd  ldloc.0
0x577de  ldstr    aObjecttypecode_81// "objecttypecode"
0x577e3  ldarg.1
0x577e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x577e9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x577ee  box      [mscorlib]System.Int32
0x577f3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x577f8  ldloc.0
0x577f9  ldstr    aAccessrightsma// "accessrightsmask"
0x577fe  ldc.i4.s 9
0x57800  box      [mscorlib]System.Int32
0x57805  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5780a  ldarg.2
0x5780b  brfalse.s loc_57824
0x5780d  ldloc.0
0x5780e  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x57813  ldc.i4   0x8000009
0x57818  box      [mscorlib]System.Int32
0x5781d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57822  br.s     loc_57835
0x57824  ldloc.0
0x57825  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x5782a  ldc.i4.0
0x5782b  box      [mscorlib]System.Int32
0x57830  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57835  ldloc.0
0x57836  ret
```
