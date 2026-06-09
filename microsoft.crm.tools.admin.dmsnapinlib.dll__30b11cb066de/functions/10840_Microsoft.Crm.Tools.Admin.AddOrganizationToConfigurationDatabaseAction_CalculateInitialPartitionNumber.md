# Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CalculateInitialPartitionNumber

- ea: `0x10840`
- end: `0x1087d`
- name: `Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::CalculateInitialPartitionNumber`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x105a0`

## callees

- `0x10840`

## string_xrefs

- `0x10864`: `CalculateInitialPartitionIdForOrganizationCreate`

## pseudocode

```c

```

## disassembly

```asm
0x10840  ldc.i4.0
0x10841  stloc.0
0x10842  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x10847  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1084c  ldc.i4.2
0x1084d  bne.un.s loc_1087B
0x1084f  ldstr    aMicrosoftCrmCr// "Microsoft.Crm.CrmLive.WebStore"
0x10854  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x10859  ldstr    aMicrosoftCrmCr_0// "Microsoft.Crm.CrmLive.WebStore.WebStore"...
0x1085e  ldc.i4.1
0x1085f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x10864  ldstr    aCalculateiniti// "CalculateInitialPartitionIdForOrganizat"...
0x10869  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x1086e  ldnull
0x1086f  ldnull
0x10870  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x10875  unbox.any [mscorlib]System.Int32
0x1087a  stloc.0
0x1087b  ldloc.0
0x1087c  ret
```
