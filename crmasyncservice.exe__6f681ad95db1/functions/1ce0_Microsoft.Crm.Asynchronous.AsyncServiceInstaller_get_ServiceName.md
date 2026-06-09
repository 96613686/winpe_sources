# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName

- ea: `0x1ce0`
- end: `0x1d11`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`
- `0x1b90`
- `0x1bb0`

## callees

- `0x1ce0`
- `0x1d60`
- `0x1e20`

## pseudocode

```c

```

## disassembly

```asm
0x1ce0  ldarg.0
0x1ce1  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceShortName()
0x1ce6  stloc.0
0x1ce7  ldarg.0
0x1ce8  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1ced  brfalse.s loc_1D0F
0x1cef  ldarg.0
0x1cf0  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1cf5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cfa  ldc.i4.0
0x1cfb  ble.s    loc_1D0F
0x1cfd  ldloc.0
0x1cfe  ldstr    asc_CFAC// "$"
0x1d03  ldarg.0
0x1d04  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix()
0x1d09  call     string [mscorlib]System.String::Concat(string, string, string)
0x1d0e  stloc.0
0x1d0f  ldloc.0
0x1d10  ret
```
