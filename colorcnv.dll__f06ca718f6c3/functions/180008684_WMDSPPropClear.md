# WMDSPPropClear

- ea: `0x180008684`
- end: `0x1800086c8`
- name: `WMDSPPropClear`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008564`
- `0x1800291b0`

## callees

- `0x180008684`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800086b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800086b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086a2`

## pseudocode

```c
void __fastcall WMDSPPropClear(__int16 a1, __int64 a2)
{
  void *v3; // rcx

  if ( a1 == 8 )
  {
    SysFreeString(*(BSTR *)a2);
    *(_QWORD *)a2 = 0;
  }
  else if ( a1 == 65 )
  {
    v3 = *(void **)(a2 + 8);
    if ( v3 )
      CoTaskMemFree(v3);
    *(_QWORD *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180008684  push    rbx
0x180008686  sub     rsp, 20h
0x18000868a  mov     rbx, rdx
0x18000868d  cmp     cx, 8
0x180008691  jz      short loc_1800086B2
0x180008693  cmp     cx, 41h ; 'A'
0x180008697  jnz     short loc_1800086C2
0x180008699  mov     rcx, [rdx+8]; pv
0x18000869d  test    rcx, rcx
0x1800086a0  jz      short loc_1800086A8
0x1800086a2  call    cs:__imp_CoTaskMemFree
0x1800086a8  mov     qword ptr [rbx+8], 0
0x1800086b0  jmp     short loc_1800086C2
0x1800086b2  mov     rcx, [rdx]; bstrString
0x1800086b5  call    cs:__imp_SysFreeString
0x1800086bb  mov     qword ptr [rbx], 0
0x1800086c2  add     rsp, 20h
0x1800086c6  pop     rbx
0x1800086c7  retn
```
