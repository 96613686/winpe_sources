# Microsoft.Crm.ObjectModel.SolutionTelemetryHelper::ClassifyException

- ea: `0x6dd50`
- end: `0x6efda`
- name: `Microsoft.Crm.ObjectModel.SolutionTelemetryHelper::ClassifyException`
- size: `4746`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x6dc10`

## callees

- `0x6dd50`
- `0x6efe0`

## string_xrefs

- `0x6e351`: `RoleService::VerifyCallerPrivileges failed.User:`
- `0x6e35e`: `Privilege not found in cache`
- `0x6e376`: `A security role with the same name but different Id already exists`
- `0x6e3e1`: `To create an entity, you must specify a value for the SchemaName property`
- `0x6e472`: `entity since mobile offline is already enabled`
- `0x6e4e4`: `Quick create is not supported for non-refreshed Entity`
- `0x6e5a5`: `is not a valid type for linked attribute`
- `0x6e5d1`: `Cannot create custom attribute '`
- `0x6e624`: `ComponentType cannot be null in a SolutionComponent when adding a new root component`
- `0x6e63a`: `Can only remove root components.  Component type`
- `0x6e65d`: `ComponentType cannot be null in a SolutionComponent when adding a new component`
- `0x6e673`: `ObjectId cannot be null in a SolutionComponent when adding a new component`
- `0x6e689`: `SolutionId cannot be null in a SolutionComponent when adding a new component`
- `0x6e69f`: `Can only add root components. Component with id`
- `0x6e6ac`: `and Component type`
- `0x6e6fb`: `Attributes defined for EntityKey must be valid for create and valid for update`
- `0x6e769`: `Layout XML must begin with a node of type 'Element'`
- `0x6e77f`: `Columnset XML must begin with a node of type 'Element'`
- `0x6e795`: `Fetch XML must begin with a node of type 'Element'`
- `0x6e8df`: `but it's not valid for update. Original value:`
- `0x6e918`: `in the Form XML`
- `0x6e93b`: `in the dashboard Form XML`
- `0x6e95e`: `in the dashboard Form XML`
- `0x6e981`: `in the dashboard Form XML`
- `0x6eb78`: `in the dashboard Form XML`
- `0x6e9a4`: `in the form XML`
- `0x6eb55`: `is not valid for create`
- `0x6ecc2`: `Cannot create a holding solution for missing base`
- `0x6ecee`: `Cannot update patched solution`
- `0x6ed34`: `already exists`
- `0x6edea`: `Plugin Assemblies import: Assembly file is missing from import zip file`
- `0x6ee00`: `was not found in the MetadataCache. MetadataCacheDetails`
- `0x6ee23`: `in MetadataCache`
- `0x6ee46`: `MetadataCacheDetails`
- `0x6ee7f`: `System.Xml.XmlException: Root element is missing`
- `0x6eea2`: `The report server has RDLSandboxing enabled and the report contains custom code. Remove the Code element from the report definition`
- `0x6eeb8`: `Trying to update an attribute in Live, which is not allowed`
- `0x6ef0b`: `already exists. Updating patch is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x6dd50  ldarg.0
0x6dd51  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException
0x6dd56  brfalse.s loc_6DD60
0x6dd58  ldc.i4.1
0x6dd59  ldc.i4.1
0x6dd5a  call     class Microsoft.Crm.ObjectModel.ErrorCategory Microsoft.Crm.ObjectModel.SolutionTelemetryHelper::BuildErrorDetails(valuetype ErrorCategories category, valuetype ErrorSubcategories subCategory)
0x6dd5f  ret
0x6dd60  ldarg.0
0x6dd61  callvirt instance string [mscorlib]System.Object::ToString()
0x6dd66  stloc.0
0x6dd67  ldarg.0
0x6dd68  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x6dd6d  brfalse  loc_6EE5B
0x6dd72  ldarg.0
0x6dd73  castclass [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x6dd78  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x6dd7d  stloc.1
0x6dd7e  ldloc.1
0x6dd7f  ldc.i4   0x8004841A
0x6dd84  bgt      loc_6DFC6
0x6dd89  ldloc.1
0x6dd8a  ldc.i4   0x80045038
0x6dd8f  bgt      loc_6DE8C
0x6dd94  ldloc.1
0x6dd95  ldc.i4   0x80044150
0x6dd9a  bgt.s    loc_6DE08
0x6dd9c  ldloc.1
0x6dd9d  ldc.i4   0x80040220
0x6dda2  bgt.s    loc_6DDCA
0x6dda4  ldloc.1
0x6dda5  ldc.i4   0x80040200
0x6ddaa  beq      loc_6E2A9
0x6ddaf  ldloc.1
0x6ddb0  ldc.i4   0x80040203
0x6ddb5  beq      loc_6E3BD
0x6ddba  ldloc.1
0x6ddbb  ldc.i4   0x80040220
0x6ddc0  beq      loc_6E350
0x6ddc5  br       loc_6EDA7
0x6ddca  ldloc.1
0x6ddcb  ldc.i4   0x80041403
0x6ddd0  bgt.s    loc_6DDED
0x6ddd2  ldloc.1
0x6ddd3  ldc.i4   0x80040256
0x6ddd8  beq      loc_6E240
0x6dddd  ldloc.1
0x6ddde  ldc.i4   0x80041403
0x6dde3  beq      loc_6E26C
0x6dde8  br       loc_6EDA7
0x6dded  ldloc.1
0x6ddee  ldc.i4   0x80041A06
0x6ddf3  beq      loc_6E2F0
0x6ddf8  ldloc.1
0x6ddf9  ldc.i4   0x80044150
0x6ddfe  beq      loc_6E394
0x6de03  br       loc_6EDA7
0x6de08  ldloc.1
0x6de09  ldc.i4   0x80044327
0x6de0e  bgt.s    loc_6DE4E
0x6de10  ldloc.1
0x6de11  ldc.i4   0x80044187
0x6de16  bgt.s    loc_6DE33
0x6de18  ldloc.1
0x6de19  ldc.i4   0x8004417D
0x6de1e  beq      loc_6E28F
0x6de23  ldloc.1
0x6de24  ldc.i4   0x80044187
0x6de29  beq      loc_6E2B2
0x6de2e  br       loc_6EDA7
0x6de33  ldloc.1
0x6de34  ldc.i4   0x8004418B
0x6de39  beq      loc_6E302
0x6de3e  ldloc.1
0x6de3f  ldc.i4   0x80044327
0x6de44  beq      loc_6E237
0x6de49  br       loc_6EDA7
0x6de4e  ldloc.1
0x6de4f  ldc.i4   0x8004500B
0x6de54  bgt.s    loc_6DE71
0x6de56  ldloc.1
0x6de57  ldc.i4   0x80044329
0x6de5c  beq      loc_6E237
0x6de61  ldloc.1
0x6de62  ldc.i4   0x8004500B
0x6de67  beq      loc_6E2B2
0x6de6c  br       loc_6EDA7
0x6de71  ldloc.1
0x6de72  ldc.i4   0x8004501D
0x6de77  beq      loc_6E302
0x6de7c  ldloc.1
0x6de7d  ldc.i4   0x80045038
0x6de82  beq      loc_6E33E
0x6de87  br       loc_6EDA7
0x6de8c  ldloc.1
0x6de8d  ldc.i4   0x8004801F
0x6de92  bgt      loc_6DF40
0x6de97  ldloc.1
0x6de98  ldc.i4   0x8004701E
0x6de9d  bgt.s    loc_6DEDD
0x6de9f  ldloc.1
0x6dea0  ldc.i4   0x80047003
0x6dea5  bgt.s    loc_6DEC2
0x6dea7  ldloc.1
0x6dea8  ldc.i4   0x80045040
0x6dead  beq      loc_6E2B2
0x6deb2  ldloc.1
0x6deb3  ldc.i4   0x80047003
0x6deb8  beq      loc_6E2C4
0x6debd  br       loc_6EDA7
0x6dec2  ldloc.1
0x6dec3  ldc.i4   0x80047007
0x6dec8  beq      loc_6E2C4
0x6decd  ldloc.1
0x6dece  ldc.i4   0x8004701E
0x6ded3  beq      loc_6E2CD
0x6ded8  br       loc_6EDA7
0x6dedd  ldloc.1
0x6dede  ldc.i4   0x80048005
0x6dee3  bgt.s    loc_6DF00
0x6dee5  ldloc.1
0x6dee6  ldc.i4   0x80048004
0x6deeb  beq      loc_6E2E7
0x6def0  ldloc.1
0x6def1  ldc.i4   0x80048005
0x6def6  beq      loc_6E26C
0x6defb  br       loc_6EDA7
0x6df00  ldloc.1
0x6df01  ldc.i4   0x80048010
0x6df06  beq      loc_6E2D6
0x6df0b  ldloc.1
0x6df0c  ldc.i4   0x80048017
0x6df11  sub
0x6df12  switch   loc_6E375, loc_6E32E, loc_6EDA7, loc_6E2BB, loc_6EDA7, loc_6EDA7, loc_6E275, loc_6EDA7, loc_6E25A
0x6df3b  br       loc_6EDA7
0x6df40  ldloc.1
0x6df41  ldc.i4   0x80048049
0x6df46  bgt.s    loc_6DF88
0x6df48  ldloc.1
0x6df49  ldc.i4   0x80048041
0x6df4e  bgt.s    loc_6DF6D
0x6df50  ldloc.1
0x6df51  ldc.i4   0x8004803A
0x6df56  beq      loc_6E263
0x6df5b  ldloc.1
0x6df5c  ldc.i4   0x80048040
0x6df61  sub
0x6df62  ldc.i4.1
0x6df63  ble.un   loc_6E286
0x6df68  br       loc_6EDA7
0x6df6d  ldloc.1
0x6df6e  ldc.i4   0x80048046
0x6df73  beq      loc_6E286
0x6df78  ldloc.1
0x6df79  ldc.i4   0x80048049
0x6df7e  beq      loc_6E286
0x6df83  br       loc_6EDA7
0x6df88  ldloc.1
0x6df89  ldc.i4   0x8004830D
0x6df8e  bgt.s    loc_6DFAB
0x6df90  ldloc.1
0x6df91  ldc.i4   0x80048071
0x6df96  beq      loc_6E2B2
0x6df9b  ldloc.1
0x6df9c  ldc.i4   0x8004830D
0x6dfa1  beq      loc_6E2B2
0x6dfa6  br       loc_6EDA7
0x6dfab  ldloc.1
0x6dfac  ldc.i4   0x80048403
0x6dfb1  beq      loc_6ED8E
0x6dfb6  ldloc.1
0x6dfb7  ldc.i4   0x8004841A
0x6dfbc  beq      loc_6E347
0x6dfc1  br       loc_6EDA7
0x6dfc6  ldloc.1
0x6dfc7  ldc.i4   0x8004F043
0x6dfcc  bgt      loc_6E0EA
0x6dfd1  ldloc.1
0x6dfd2  ldc.i4   0x8004E302
0x6dfd7  bgt.s    loc_6E045
0x6dfd9  ldloc.1
0x6dfda  ldc.i4   0x80048539
0x6dfdf  bgt.s    loc_6E007
0x6dfe1  ldloc.1
0x6dfe2  ldc.i4   0x80048425
0x6dfe7  beq      loc_6E2BB
0x6dfec  ldloc.1
0x6dfed  ldc.i4   0x80048470
0x6dff2  beq      loc_6E2C4
0x6dff7  ldloc.1
0x6dff8  ldc.i4   0x80048539
0x6dffd  beq      loc_6EBB6
0x6e002  br       loc_6EDA7
0x6e007  ldloc.1
0x6e008  ldc.i4   0x8004A104
0x6e00d  bgt.s    loc_6E02A
0x6e00f  ldloc.1
0x6e010  ldc.i4   0x80048540
0x6e015  beq      loc_6E27D
0x6e01a  ldloc.1
0x6e01b  ldc.i4   0x8004A104
0x6e020  beq      loc_6E251
0x6e025  br       loc_6EDA7
0x6e02a  ldloc.1
0x6e02b  ldc.i4   0x8004B043
0x6e030  beq      loc_6E2A0
0x6e035  ldloc.1
0x6e036  ldc.i4   0x8004E302
0x6e03b  beq      loc_6E336
0x6e040  br       loc_6EDA7
0x6e045  ldloc.1
0x6e046  ldc.i4   0x8004F016
0x6e04b  bgt.s    loc_6E0A8
0x6e04d  ldloc.1
0x6e04e  ldc.i4   0x8004E30F
0x6e053  bgt.s    loc_6E08D
0x6e055  ldloc.1
0x6e056  ldc.i4   0x8004E303
0x6e05b  beq      loc_6E2F0
0x6e060  ldloc.1
0x6e061  ldc.i4   0x8004E309
0x6e066  sub
0x6e067  switch   loc_6E336, loc_6EDA7, loc_6EDA7, loc_6E286, loc_6E26C, loc_6EDA7, loc_6E325
0x6e088  br       loc_6EDA7
0x6e08d  ldloc.1
0x6e08e  ldc.i4   0x8004F007
0x6e093  beq      loc_6E286
0x6e098  ldloc.1
0x6e099  ldc.i4   0x8004F016
0x6e09e  beq      loc_6E249
0x6e0a3  br       loc_6EDA7
0x6e0a8  ldloc.1
0x6e0a9  ldc.i4   0x8004F031
0x6e0ae  bgt.s    loc_6E0CD
0x6e0b0  ldloc.1
0x6e0b1  ldc.i4   0x8004F026
0x6e0b6  sub
0x6e0b7  ldc.i4.1
0x6e0b8  ble.un   loc_6E22E
0x6e0bd  ldloc.1
0x6e0be  ldc.i4   0x8004F031
0x6e0c3  beq      loc_6E2B2
0x6e0c8  br       loc_6EDA7
0x6e0cd  ldloc.1
0x6e0ce  ldc.i4   0x8004F036
0x6e0d3  sub
0x6e0d4  ldc.i4.1
0x6e0d5  ble.un   loc_6E275
0x6e0da  ldloc.1
0x6e0db  ldc.i4   0x8004F043
0x6e0e0  beq      loc_6E313
0x6e0e5  br       loc_6EDA7
0x6e0ea  ldloc.1
0x6e0eb  ldc.i4   0x80060417
0x6e0f0  bgt      loc_6E17B
0x6e0f5  ldloc.1
0x6e0f6  ldc.i4   0x80050109
0x6e0fb  bgt.s    loc_6E13D
0x6e0fd  ldloc.1
0x6e0fe  ldc.i4   0x8004F126
0x6e103  bgt.s    loc_6E122
0x6e105  ldloc.1
0x6e106  ldc.i4   0x8004F104
0x6e10b  sub
0x6e10c  ldc.i4.3
0x6e10d  ble.un   loc_6E2DF
0x6e112  ldloc.1
0x6e113  ldc.i4   0x8004F126
0x6e118  beq      loc_6E2B2
0x6e11d  br       loc_6EDA7
0x6e122  ldloc.1
0x6e123  ldc.i4   0x8004F658
0x6e128  beq      loc_6E26C
0x6e12d  ldloc.1
0x6e12e  ldc.i4   0x80050109
0x6e133  beq      loc_6E313
0x6e138  br       loc_6EDA7
0x6e13d  ldloc.1
0x6e13e  ldc.i4   0x80060384
0x6e143  bgt.s    loc_6E160
0x6e145  ldloc.1
0x6e146  ldc.i4   0x80060304
0x6e14b  beq      loc_6E26C
0x6e150  ldloc.1
0x6e151  ldc.i4   0x80060384
0x6e156  beq      loc_6E26C
0x6e15b  br       loc_6EDA7
0x6e160  ldloc.1
0x6e161  ldc.i4   0x80060413
0x6e166  beq      loc_6E2B2
0x6e16b  ldloc.1
0x6e16c  ldc.i4   0x80060417
0x6e171  beq      loc_6E31C
0x6e176  br       loc_6EDA7
0x6e17b  ldloc.1
0x6e17c  ldc.i4   0x80060543
0x6e181  bgt.s    loc_6E1C5
0x6e183  ldloc.1
0x6e184  ldc.i4   0x80060424
0x6e189  bgt.s    loc_6E1A6
0x6e18b  ldloc.1
  ... truncated ...
```
