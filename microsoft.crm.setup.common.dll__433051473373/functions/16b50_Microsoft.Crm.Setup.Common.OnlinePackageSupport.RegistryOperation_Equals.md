# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Equals

- ea: `0x16b50`
- end: `0x16ba2`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Equals`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x164c0`
- `0x164e0`
- `0x16510`
- `0x16540`
- `0x16b50`

## pseudocode

```c

```

## disassembly

```asm
0x16b50  ldarg.1
0x16b51  castclass Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation
0x16b56  stloc.0
0x16b57  ldarg.0
0x16b58  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16b5d  ldloc.0
0x16b5e  callvirt instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16b63  bne.un.s loc_16BA0
0x16b65  ldarg.0
0x16b66  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16b6b  ldloc.0
0x16b6c  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16b71  ldc.i4.5
0x16b72  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x16b77  brfalse.s loc_16BA0
0x16b79  ldarg.0
0x16b7a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16b7f  ldloc.0
0x16b80  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16b85  ldc.i4.5
0x16b86  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x16b8b  brfalse.s loc_16BA0
0x16b8d  ldarg.0
0x16b8e  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x16b93  ldloc.0
0x16b94  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x16b99  ldc.i4.5
0x16b9a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x16b9f  ret
0x16ba0  ldc.i4.0
0x16ba1  ret
```
