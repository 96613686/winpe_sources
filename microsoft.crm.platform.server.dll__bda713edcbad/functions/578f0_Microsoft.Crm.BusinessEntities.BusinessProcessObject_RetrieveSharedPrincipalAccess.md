# Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveSharedPrincipalAccess

- ea: `0x578f0`
- end: `0x579a1`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveSharedPrincipalAccess`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x578f0`
- `0x61160`
- `0x61180`
- `0x6dbd0`

## string_xrefs

- `0x57911`: `PrincipalObjectAccess`
- `0x57982`: `accessrightsmask`
- `0x5798f`: `accessrightsmask`
- `0x578fc`: `securityPrincipal`

## pseudocode

```c

```

## disassembly

```asm
0x578f0  ldarg.1
0x578f1  ldstr    aMoniker// "moniker"
0x578f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x578fb  ldarg.2
0x578fc  ldstr    aSecurityprinci// "securityPrincipal"
0x57901  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57906  ldarg.3
0x57907  ldstr    aContext// "context"
0x5790c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57911  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x57916  ldarg.3
0x57917  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5791c  stloc.0
0x5791d  ldloc.0
0x5791e  ldstr    aPrincipalid// "principalid"
0x57923  ldarg.2
0x57924  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x57929  box      [mscorlib]System.Guid
0x5792e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57933  ldloc.0
0x57934  ldstr    aPrincipaltypec// "principaltypecode"
0x57939  ldarg.2
0x5793a  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x5793f  box      [mscorlib]System.Int32
0x57944  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57949  ldloc.0
0x5794a  ldstr    aObjectid// "objectid"
0x5794f  ldarg.1
0x57950  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x57955  box      [mscorlib]System.Guid
0x5795a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5795f  ldloc.0
0x57960  ldstr    aObjecttypecode_81// "objecttypecode"
0x57965  ldarg.1
0x57966  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x5796b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x57970  box      [mscorlib]System.Int32
0x57975  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5797a  ldloc.0
0x5797b  ldarg.3
0x5797c  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x57981  ldloc.0
0x57982  ldstr    aAccessrightsma// "accessrightsmask"
0x57987  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5798c  brtrue.s loc_5799F
0x5798e  ldloc.0
0x5798f  ldstr    aAccessrightsma// "accessrightsmask"
0x57994  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57999  unbox.any [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x5799e  ret
0x5799f  ldc.i4.0
0x579a0  ret
```
