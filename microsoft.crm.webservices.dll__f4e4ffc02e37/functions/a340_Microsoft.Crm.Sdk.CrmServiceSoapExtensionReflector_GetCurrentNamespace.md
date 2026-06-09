# Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::GetCurrentNamespace

- ea: `0xa340`
- end: `0xa377`
- name: `Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::GetCurrentNamespace`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xa140`

## callees

- `0xa340`

## pseudocode

```c

```

## disassembly

```asm
0xa340  ldnull
0xa341  stloc.0
0xa342  ldarg.0
0xa343  ldc.i4.0
0xa344  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(bool)
0xa349  stloc.1
0xa34a  ldc.i4.0
0xa34b  stloc.2
0xa34c  br.s     loc_A36F
0xa34e  ldloc.1
0xa34f  ldloc.2
0xa350  ldelem.ref
0xa351  castclass [mscorlib]System.Attribute
0xa356  stloc.3
0xa357  ldloc.3
0xa358  isinst   [System.Web.Services]System.Web.Services.WebServiceAttribute
0xa35d  brfalse.s loc_A36B
0xa35f  ldloc.3
0xa360  castclass [System.Web.Services]System.Web.Services.WebServiceAttribute
0xa365  callvirt instance string [System.Web.Services]System.Web.Services.WebServiceAttribute::get_Namespace()
0xa36a  stloc.0
0xa36b  ldloc.2
0xa36c  ldc.i4.1
0xa36d  add
0xa36e  stloc.2
0xa36f  ldloc.2
0xa370  ldloc.1
0xa371  ldlen
0xa372  conv.i4
0xa373  blt.s    loc_A34E
0xa375  ldloc.0
0xa376  ret
```
