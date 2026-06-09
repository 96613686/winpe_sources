# Microsoft.Crm.ObjectModel.TemplateService::ValidateGenerationTypeCodeForUpdate

- ea: `0x1b6300`
- end: `0x1b646f`
- name: `Microsoft.Crm.ObjectModel.TemplateService::ValidateGenerationTypeCodeForUpdate`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1b6640`

## callees

- `0x1b6300`
- `0x1b6470`

## string_xrefs

- `0x1b6350`: `Template`
- `0x1b6323`: `templatetypecode`
- `0x1b638b`: `templatetypecode`
- `0x1b6398`: `templatetypecode`
- `0x1b63aa`: `templatetypecode`
- `0x1b6341`: `templateid`
- `0x1b6455`: `templateid`

## pseudocode

```c

```

## disassembly

```asm
0x1b6300  ldarg.0
0x1b6301  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1b6306  ldarg.2
0x1b6307  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1b630c  stloc.0
0x1b630d  ldloc.0
0x1b630e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1b6313  ldstr    aGenerationtype// "generationtypecode"
0x1b6318  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1b631d  ldloc.0
0x1b631e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1b6323  ldstr    aTemplatetypeco// "templatetypecode"
0x1b6328  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1b632d  ldloc.0
0x1b632e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1b6333  ldstr    aLanguagecode// "languagecode"
0x1b6338  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1b633d  ldnull
0x1b633e  stloc.1
0x1b633f  ldarg.0
0x1b6340  ldarg.1
0x1b6341  ldstr    aTemplateid_1// "templateid"
0x1b6346  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b634b  unbox.any [mscorlib]System.Guid
0x1b6350  ldstr    aTemplate_0// "Template"
0x1b6355  ldarg.2
0x1b6356  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b635b  ldloc.0
0x1b635c  ldarg.2
0x1b635d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b6362  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template
0x1b6367  stloc.1
0x1b6368  ldloc.1
0x1b6369  brfalse  loc_1B646D
0x1b636e  ldarg.1
0x1b636f  ldstr    aLanguagecode// "languagecode"
0x1b6374  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b6379  brfalse.s loc_1B638A
0x1b637b  ldloc.1
0x1b637c  ldstr    aLanguagecode// "languagecode"
0x1b6381  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b6386  brfalse.s loc_1B638A
0x1b6388  ldc.i4.1
0x1b6389  ret
0x1b638a  ldarg.1
0x1b638b  ldstr    aTemplatetypeco// "templatetypecode"
0x1b6390  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b6395  brfalse.s loc_1B63A9
0x1b6397  ldloc.1
0x1b6398  ldstr    aTemplatetypeco// "templatetypecode"
0x1b639d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b63a2  unbox.any [mscorlib]System.Int32
0x1b63a7  br.s     loc_1B63B9
0x1b63a9  ldarg.1
0x1b63aa  ldstr    aTemplatetypeco// "templatetypecode"
0x1b63af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b63b4  unbox.any [mscorlib]System.Int32
0x1b63b9  stloc.3
0x1b63ba  ldarg.1
0x1b63bb  ldstr    aGenerationtype// "generationtypecode"
0x1b63c0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b63c5  brfalse.s loc_1B63E9
0x1b63c7  ldloc.1
0x1b63c8  ldstr    aGenerationtype// "generationtypecode"
0x1b63cd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b63d2  brfalse.s loc_1B63D7
0x1b63d4  ldc.i4.0
0x1b63d5  br.s     loc_1B63F9
0x1b63d7  ldloc.1
0x1b63d8  ldstr    aGenerationtype// "generationtypecode"
0x1b63dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b63e2  unbox.any [mscorlib]System.Int32
0x1b63e7  br.s     loc_1B63F9
0x1b63e9  ldarg.1
0x1b63ea  ldstr    aGenerationtype// "generationtypecode"
0x1b63ef  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b63f4  unbox.any [mscorlib]System.Int32
0x1b63f9  stloc.2
0x1b63fa  ldloc.2
0x1b63fb  ldc.i4.8
0x1b63fc  bgt.s    loc_1B640A
0x1b63fe  ldloc.2
0x1b63ff  ldc.i4.1
0x1b6400  blt.s    loc_1B640A
0x1b6402  ldloc.3
0x1b6403  ldc.i4   0x125C
0x1b6408  beq.s    loc_1B640C
0x1b640a  ldc.i4.1
0x1b640b  ret
0x1b640c  ldarg.1
0x1b640d  ldstr    aLanguagecode// "languagecode"
0x1b6412  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b6417  brfalse.s loc_1B642B
0x1b6419  ldloc.1
0x1b641a  ldstr    aLanguagecode// "languagecode"
0x1b641f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b6424  unbox.any [mscorlib]System.Int32
0x1b6429  br.s     loc_1B643B
0x1b642b  ldarg.1
0x1b642c  ldstr    aLanguagecode// "languagecode"
0x1b6431  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b6436  unbox.any [mscorlib]System.Int32
0x1b643b  stloc.s  4
0x1b643d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b6442  stloc.s  5
0x1b6444  ldarg.0
0x1b6445  ldarg.2
0x1b6446  ldloc.2
0x1b6447  ldloc.s  4
0x1b6449  ldloca.s 5
0x1b644b  call     instance bool Microsoft.Crm.ObjectModel.TemplateService::AsyncTemplateExists(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 generationTypeCode, int32 languageCode, [out] valuetype [mscorlib]System.Guid& foundTemplateId)
0x1b6450  brfalse.s loc_1B646D
0x1b6452  ldloca.s 5
0x1b6454  ldarg.1
0x1b6455  ldstr    aTemplateid_1// "templateid"
0x1b645a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b645f  unbox.any [mscorlib]System.Guid
0x1b6464  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x1b6469  brtrue.s loc_1B646D
0x1b646b  ldc.i4.0
0x1b646c  ret
0x1b646d  ldc.i4.1
0x1b646e  ret
```
