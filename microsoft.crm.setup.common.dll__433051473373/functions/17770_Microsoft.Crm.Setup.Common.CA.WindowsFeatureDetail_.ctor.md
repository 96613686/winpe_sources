# Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::.ctor

- ea: `0x17770`
- end: `0x1779c`
- name: `Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x177a0`

## callees

- `0x177d0`
- `0x177f0`
- `0x17810`
- `0x17850`
- `0x17860`

## pseudocode

```c

```

## disassembly

```asm
0x17770  ldarg.0
0x17771  call     instance void [mscorlib]System.Object::.ctor()
0x17776  ldarg.0
0x17777  ldarg.1
0x17778  call     instance void Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::set_FeatureName(string value)
0x1777d  ldarg.0
0x1777e  ldarg.2
0x1777f  call     instance void Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::set_DisplayName(string value)
0x17784  ldarg.0
0x17785  ldarg.s  4
0x17787  call     instance void Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::set_RestartRequired(valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureRestartType value)
0x1778c  ldarg.0
0x1778d  ldarg.3
0x1778e  call     instance valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::ParseState(string state)
0x17793  stloc.0
0x17794  ldarg.0
0x17795  ldloc.0
0x17796  call     instance void Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::set_FeatureState(valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureState value)
0x1779b  ret
```
