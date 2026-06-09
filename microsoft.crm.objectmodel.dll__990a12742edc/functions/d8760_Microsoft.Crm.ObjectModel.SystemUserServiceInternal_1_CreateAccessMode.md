# Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1::CreateAccessMode

- ea: `0xd8760`
- end: `0xd886a`
- name: `Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1::CreateAccessMode`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd8760`

## string_xrefs

- `0xd876c`: `accessmode`
- `0xd877d`: `accessmode`
- `0xd87cd`: `accessmode`
- `0xd882c`: `accessmode`
- `0xd8839`: `accessmode`
- `0xd8844`: `accessmode`
- `0xd87df`: `issyncwithdirectory`
- `0xd87ec`: `issyncwithdirectory`

## pseudocode

```c

```

## disassembly

```asm
0xd8760  ldarg.1
0xd8761  ldstr    aSystemuser// "systemuser"
0xd8766  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd876b  ldarg.1
0xd876c  ldstr    aAccessmode// "accessmode"
0xd8771  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd8776  brtrue   loc_D8817
0xd877b  ldc.i4.2
0xd877c  ldarg.1
0xd877d  ldstr    aAccessmode// "accessmode"
0xd8782  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd8787  unbox.any [mscorlib]System.Int32
0xd878c  bne.un.s loc_D87AC
0xd878e  ldc.i4.2
0xd878f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xd8794  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xd8799  bne.un.s loc_D87AC
0xd879b  ldc.i4   0x80041D40
0xd87a0  ldc.i4.0
0xd87a1  newarr   [mscorlib]System.Object
0xd87a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xd87ab  throw
0xd87ac  ldc.i4.2
0xd87ad  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xd87b2  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xd87b7  bne.un.s loc_D880E
0xd87b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xd87be  ldarg.2
0xd87bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd87c4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0xd87c9  brfalse.s loc_D880E
0xd87cb  ldc.i4.4
0xd87cc  ldarg.1
0xd87cd  ldstr    aAccessmode// "accessmode"
0xd87d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd87d7  unbox.any [mscorlib]System.Int32
0xd87dc  bne.un.s loc_D880E
0xd87de  ldarg.1
0xd87df  ldstr    aIssyncwithdire// "issyncwithdirectory"
0xd87e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd87e9  brtrue.s loc_D880E
0xd87eb  ldarg.1
0xd87ec  ldstr    aIssyncwithdire// "issyncwithdirectory"
0xd87f1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd87f6  unbox.any [mscorlib]System.Boolean
0xd87fb  brfalse.s loc_D880E
0xd87fd  ldarg.1
0xd87fe  ldstr    aIsdisabled// "isdisabled"
0xd8803  ldc.i4.0
0xd8804  box      [mscorlib]System.Boolean
0xd8809  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd880e  ldarg.0
0xd880f  ldarg.1
0xd8810  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::SetSetupUserFromAccessMode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xd8815  br.s     loc_D882B
0xd8817  ldarg.1
0xd8818  ldstr    aSetupuser// "setupuser"
0xd881d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd8822  brtrue.s loc_D882B
0xd8824  ldarg.0
0xd8825  ldarg.1
0xd8826  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::SetAccessModeFromSetupUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xd882b  ldarg.1
0xd882c  ldstr    aAccessmode// "accessmode"
0xd8831  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd8836  brfalse.s loc_D8862
0xd8838  ldarg.1
0xd8839  ldstr    aAccessmode// "accessmode"
0xd883e  ldarg.1
0xd883f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0xd8844  ldstr    aAccessmode// "accessmode"
0xd8849  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xd884e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0xd8853  unbox.any [mscorlib]System.Int32
0xd8858  box      [mscorlib]System.Int32
0xd885d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd8862  ldarg.0
0xd8863  ldarg.1
0xd8864  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::SetAndValidateCalType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xd8869  ret
```
