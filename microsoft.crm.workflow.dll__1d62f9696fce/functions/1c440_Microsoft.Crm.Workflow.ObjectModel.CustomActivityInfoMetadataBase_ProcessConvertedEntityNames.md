# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::ProcessConvertedEntityNames

- ea: `0x1c440`
- end: `0x1c487`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::ProcessConvertedEntityNames`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1c1b0`

## callees

- `0x1c440`
- `0x1c490`
- `0x1c500`
- `0x1c560`

## string_xrefs

- `0x1c44e`: `SETWORDTEMPLATE_Target`

## pseudocode

```c

```

## disassembly

```asm
0x1c440  ldarg.1
0x1c441  ldstr    aSetprocessTarg// "SETPROCESS_Target"
0x1c446  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c44b  brtrue.s loc_1C469
0x1c44d  ldarg.1
0x1c44e  ldstr    aSetwordtemplat// "SETWORDTEMPLATE_Target"
0x1c453  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c458  brtrue.s loc_1C473
0x1c45a  ldarg.1
0x1c45b  ldstr    aSendnotificati_1// "SENDNOTIFICATION_RegardingObjectId"
0x1c460  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c465  brtrue.s loc_1C47D
0x1c467  br.s     loc_1C485
0x1c469  ldarg.0
0x1c46a  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetAllBpfEnabledEntities()
0x1c46f  starg.s  2
0x1c471  br.s     loc_1C485
0x1c473  ldarg.0
0x1c474  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetValidAdvanceFindEntities()
0x1c479  starg.s  2
0x1c47b  br.s     loc_1C485
0x1c47d  ldarg.0
0x1c47e  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetValidMOCAEntities()
0x1c483  starg.s  2
0x1c485  ldarg.2
0x1c486  ret
```
