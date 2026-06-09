# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::GetHttpVerbMask

- ea: `0x2e490`
- end: `0x2e4f9`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::GetHttpVerbMask`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2df60`
- `0x2e160`

## callees

- `0x2e490`

## string_xrefs

- `0x2e4de`: `DELETE`

## pseudocode

```c

```

## disassembly

```asm
0x2e490  ldarg.0
0x2e491  callvirt instance string [mscorlib]System.Object::ToString()
0x2e496  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2e49b  stloc.0
0x2e49c  ldloc.0
0x2e49d  ldstr    aGet_0// "GET"
0x2e4a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4a7  brtrue.s loc_2E4EC
0x2e4a9  ldloc.0
0x2e4aa  ldstr    aPost_0// "POST"
0x2e4af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4b4  brtrue.s loc_2E4EE
0x2e4b6  ldloc.0
0x2e4b7  ldstr    aPut_0// "PUT"
0x2e4bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4c1  brtrue.s loc_2E4F0
0x2e4c3  ldloc.0
0x2e4c4  ldstr    aPatch_0// "PATCH"
0x2e4c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4ce  brtrue.s loc_2E4F2
0x2e4d0  ldloc.0
0x2e4d1  ldstr    aMerge// "MERGE"
0x2e4d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4db  brtrue.s loc_2E4F2
0x2e4dd  ldloc.0
0x2e4de  ldstr    aDelete_1// "DELETE"
0x2e4e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4e8  brtrue.s loc_2E4F4
0x2e4ea  br.s     loc_2E4F7
0x2e4ec  ldc.i4.1
0x2e4ed  ret
0x2e4ee  ldc.i4.2
0x2e4ef  ret
0x2e4f0  ldc.i4.4
0x2e4f1  ret
0x2e4f2  ldc.i4.8
0x2e4f3  ret
0x2e4f4  ldc.i4.s 0x10
0x2e4f6  ret
0x2e4f7  ldc.i4.0
0x2e4f8  ret
```
