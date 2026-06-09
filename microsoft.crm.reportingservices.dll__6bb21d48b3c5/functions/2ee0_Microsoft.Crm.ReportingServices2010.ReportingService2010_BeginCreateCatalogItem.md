# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateCatalogItem

- ea: `0x2ee0`
- end: `0x2f16`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateCatalogItem`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2ee1`: `CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldarg.0
0x2ee1  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x2ee6  ldc.i4.6
0x2ee7  newarr   [mscorlib]System.Object
0x2eec  dup
0x2eed  ldc.i4.0
0x2eee  ldarg.1
0x2eef  stelem.ref
0x2ef0  dup
0x2ef1  ldc.i4.1
0x2ef2  ldarg.2
0x2ef3  stelem.ref
0x2ef4  dup
0x2ef5  ldc.i4.2
0x2ef6  ldarg.3
0x2ef7  stelem.ref
0x2ef8  dup
0x2ef9  ldc.i4.3
0x2efa  ldarg.s  4
0x2efc  box      [mscorlib]System.Boolean
0x2f01  stelem.ref
0x2f02  dup
0x2f03  ldc.i4.4
0x2f04  ldarg.s  5
0x2f06  stelem.ref
0x2f07  dup
0x2f08  ldc.i4.5
0x2f09  ldarg.s  6
0x2f0b  stelem.ref
0x2f0c  ldarg.s  7
0x2f0e  ldarg.s  8
0x2f10  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x2f15  ret
```
