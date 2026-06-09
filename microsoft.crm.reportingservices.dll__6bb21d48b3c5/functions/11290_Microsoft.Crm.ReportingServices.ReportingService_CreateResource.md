# Microsoft.Crm.ReportingServices.ReportingService::CreateResource

- ea: `0x11290`
- end: `0x112c3`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateResource`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11291`: `CreateResource`

## pseudocode

```c

```

## disassembly

```asm
0x11290  ldarg.0
0x11291  ldstr    aCreateresource// "CreateResource"
0x11296  ldc.i4.6
0x11297  newarr   [mscorlib]System.Object
0x1129c  dup
0x1129d  ldc.i4.0
0x1129e  ldarg.1
0x1129f  stelem.ref
0x112a0  dup
0x112a1  ldc.i4.1
0x112a2  ldarg.2
0x112a3  stelem.ref
0x112a4  dup
0x112a5  ldc.i4.2
0x112a6  ldarg.3
0x112a7  box      [mscorlib]System.Boolean
0x112ac  stelem.ref
0x112ad  dup
0x112ae  ldc.i4.3
0x112af  ldarg.s  4
0x112b1  stelem.ref
0x112b2  dup
0x112b3  ldc.i4.4
0x112b4  ldarg.s  5
0x112b6  stelem.ref
0x112b7  dup
0x112b8  ldc.i4.5
0x112b9  ldarg.s  6
0x112bb  stelem.ref
0x112bc  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x112c1  pop
0x112c2  ret
```
