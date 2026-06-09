# Microsoft.Crm.Reporting.ReportPublisher::CreateReportEntity

- ea: `0x4260`
- end: `0x437b`
- name: `Microsoft.Crm.Reporting.ReportPublisher::CreateReportEntity`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4110`

## callees

- `0x4260`

## pseudocode

```c

```

## disassembly

```asm
0x4260  ldstr    aReport_0// "Report"
0x4265  ldarg.s  0xA
0x4267  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, valuetype [mscorlib]System.Guid)
0x426c  stloc.0
0x426d  ldloc.0
0x426e  ldstr    aReporttypecode// "reporttypecode"
0x4273  ldc.i4.1
0x4274  box      [mscorlib]System.Int32
0x4279  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x427e  ldloc.0
0x427f  ldstr    aDefaultfilter// "defaultfilter"
0x4284  ldnull
0x4285  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x428a  ldloc.0
0x428b  ldstr    aIspersonal// "ispersonal"
0x4290  ldc.i4.0
0x4291  box      [mscorlib]System.Boolean
0x4296  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x429b  ldloc.0
0x429c  ldstr    aName_0// "name"
0x42a1  ldarg.2
0x42a2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42a7  ldloc.0
0x42a8  ldstr    aBodytext// "bodytext"
0x42ad  ldarg.1
0x42ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42b3  ldloc.0
0x42b4  ldstr    aFilename// "filename"
0x42b9  ldarg.3
0x42ba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42bf  ldloc.0
0x42c0  ldstr    aDescription// "description"
0x42c5  ldarg.s  4
0x42c7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42cc  ldloc.0
0x42cd  ldstr    aLanguagecode// "languagecode"
0x42d2  ldarg.s  5
0x42d4  box      [mscorlib]System.Int32
0x42d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42de  ldloc.0
0x42df  ldstr    aReportnameonsr// "reportnameonsrs"
0x42e4  ldarg.s  0xB
0x42e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x42eb  ldarg.s  7
0x42ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42f2  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x42f7  brfalse.s loc_435E
0x42f9  ldloc.0
0x42fa  ldstr    aSignatureid// "signatureid"
0x42ff  ldarg.s  7
0x4301  box      [mscorlib]System.Guid
0x4306  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x430b  ldloc.0
0x430c  ldstr    aSignaturelcid// "signaturelcid"
0x4311  ldarg.s  5
0x4313  box      [mscorlib]System.Int32
0x4318  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x431d  ldloc.0
0x431e  ldstr    aSignaturemajor// "signaturemajorversion"
0x4323  ldarg.s  8
0x4325  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x432a  box      [mscorlib]System.Int32
0x432f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4334  ldloc.0
0x4335  ldstr    aSignatureminor// "signatureminorversion"
0x433a  ldarg.s  8
0x433c  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x4341  box      [mscorlib]System.Int32
0x4346  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x434b  ldloc.0
0x434c  ldstr    aSignaturedate// "signaturedate"
0x4351  ldarg.s  9
0x4353  ldc.i4.1
0x4354  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x4359  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x435e  ldarg.s  6
0x4360  brfalse.s loc_4379
0x4362  ldloc.0
0x4363  ldstr    aParentreportid// "parentreportid"
0x4368  ldarg.s  6
0x436a  unbox.any [mscorlib]System.Guid
0x436f  box      [mscorlib]System.Guid
0x4374  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4379  ldloc.0
0x437a  ret
```
