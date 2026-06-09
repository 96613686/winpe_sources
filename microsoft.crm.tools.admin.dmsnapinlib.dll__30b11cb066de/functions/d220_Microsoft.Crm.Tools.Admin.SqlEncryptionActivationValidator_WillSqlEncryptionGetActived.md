# Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::WillSqlEncryptionGetActived

- ea: `0xd220`
- end: `0xd278`
- name: `Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::WillSqlEncryptionGetActived`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd1e0`

## callees

- `0x84f0`
- `0x89f0`
- `0x8a70`
- `0x92d0`
- `0xbd70`
- `0xd220`

## string_xrefs

- `0xd22d`: `InstallInfo.CreateDatabase`
- `0xd249`: `InstallInfo.UpgradeDatabase`

## pseudocode

```c

```

## disassembly

```asm
0xd220  ldarg.1
0xd221  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xd226  stloc.0
0xd227  ldloc.0
0xd228  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xd22d  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xd232  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xd237  brfalse.s loc_D243
0xd239  ldloc.0
0xd23a  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xd23f  brfalse.s loc_D243
0xd241  ldc.i4.1
0xd242  ret
0xd243  ldloc.0
0xd244  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xd249  ldstr    aInstallinfoUpg// "InstallInfo.UpgradeDatabase"
0xd24e  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xd253  brfalse.s loc_D25F
0xd255  ldloc.0
0xd256  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_UpgradeDatabase()
0xd25b  brfalse.s loc_D25F
0xd25d  ldc.i4.1
0xd25e  ret
0xd25f  ldloc.0
0xd260  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsImportAndUpgrade()
0xd265  brfalse.s loc_D269
0xd267  ldc.i4.1
0xd268  ret
0xd269  ldarg.0
0xd26a  ldfld    class Microsoft.Crm.Tools.Admin.ISqlEncryptionGetActivationCheck Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::_sqlEncryptionGetActivationCheck
0xd26f  ldarg.1
0xd270  callvirt instance bool Microsoft.Crm.Tools.Admin.ISqlEncryptionGetActivationCheck::WillSqlEncryptionGetActivationCheck(class [mscorlib]System.Collections.IDictionary parameters)
0xd275  pop
0xd276  ldc.i4.0
0xd277  ret
```
