# Microsoft.Crm.MonitoredStream::RegisterBytesRead

- ea: `0x17e20`
- end: `0x17e7e`
- name: `Microsoft.Crm.MonitoredStream::RegisterBytesRead`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17db0`
- `0x17dd0`
- `0x17e00`

## callees

- `0x17e20`
- `0x18460`

## string_xrefs

- `0x17e48`: `The stream being read from has more than {0} bytes`

## pseudocode

```c

```

## disassembly

```asm
0x17e20  ldarg.0
0x17e21  ldc.i4.0
0x17e22  stfld    int32 Microsoft.Crm.MonitoredStream::_totalBytesWrittenSinceLastRead
0x17e27  ldarg.0
0x17e28  ldarg.0
0x17e29  ldfld    int32 Microsoft.Crm.MonitoredStream::_totalBytesReadSinceLastWrite
0x17e2e  ldarg.1
0x17e2f  add
0x17e30  stfld    int32 Microsoft.Crm.MonitoredStream::_totalBytesReadSinceLastWrite
0x17e35  ldarg.0
0x17e36  ldfld    int32 Microsoft.Crm.MonitoredStream::_totalBytesReadSinceLastWrite
0x17e3b  ldarg.0
0x17e3c  ldfld    int32 Microsoft.Crm.MonitoredStream::_maxBytesToReadInOneResponse
0x17e41  ble.s    loc_17E71
0x17e43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17e48  ldstr    aTheStreamBeing// "The stream being read from has more tha"...
0x17e4d  ldc.i4.1
0x17e4e  newarr   [mscorlib]System.Object
0x17e53  dup
0x17e54  ldc.i4.0
0x17e55  ldarg.0
0x17e56  ldfld    int32 Microsoft.Crm.MonitoredStream::_maxBytesToReadInOneResponse
0x17e5b  box      [mscorlib]System.Int32
0x17e60  stelem.ref
0x17e61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17e66  ldc.i4   0x8004F901
0x17e6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17e70  throw
0x17e71  ldarg.0
0x17e72  ldfld    class Microsoft.Crm.ITrafficMonitor Microsoft.Crm.MonitoredStream::_trafficMonitor
0x17e77  ldarg.1
0x17e78  callvirt instance void Microsoft.Crm.ITrafficMonitor::RegisterBytesReceived(int32 countOfBytes)
0x17e7d  ret
```
