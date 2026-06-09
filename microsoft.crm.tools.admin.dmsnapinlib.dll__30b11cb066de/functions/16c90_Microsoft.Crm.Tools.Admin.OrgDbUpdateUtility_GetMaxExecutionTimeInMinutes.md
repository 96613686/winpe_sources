# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetMaxExecutionTimeInMinutes

- ea: `0x16c90`
- end: `0x16cb5`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetMaxExecutionTimeInMinutes`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17000`

## callees

- `0x16c90`
- `0x16e40`

## string_xrefs

- `0x16c97`: `MaxUpdateRunTimeInMin`

## pseudocode

```c

```

## disassembly

```asm
0x16c90  ldc.i4   0xB4
0x16c95  stloc.0
0x16c96  ldarg.0
0x16c97  ldstr    aMaxupdaterunti// "MaxUpdateRunTimeInMin"
0x16c9c  call     instance string Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetSingleValueConfigSetting(string configSettingKey)
0x16ca1  stloc.1
0x16ca2  ldloc.1
0x16ca3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x16ca8  brtrue.s loc_16CB3
0x16caa  ldloc.1
0x16cab  ldloca.s 0
0x16cad  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x16cb2  pop
0x16cb3  ldloc.0
0x16cb4  ret
```
