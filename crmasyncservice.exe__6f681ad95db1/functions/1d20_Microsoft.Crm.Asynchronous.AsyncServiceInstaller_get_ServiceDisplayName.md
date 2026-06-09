# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayName

- ea: `0x1d20`
- end: `0x1d56`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayName`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`

## callees

- `0x1d20`
- `0x1d60`
- `0x1da0`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.0
0x1d21  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayNameRoot()
0x1d26  stloc.0
0x1d27  ldarg.0
0x1d28  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1d2d  brfalse.s loc_1D54
0x1d2f  ldarg.0
0x1d30  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1d35  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d3a  ldc.i4.0
0x1d3b  ble.s    loc_1D54
0x1d3d  ldloc.0
0x1d3e  ldstr    asc_CFB0// " ("
0x1d43  ldarg.0
0x1d44  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1d49  ldstr    asc_CFB6// ")"
0x1d4e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1d53  stloc.0
0x1d54  ldloc.0
0x1d55  ret
```
