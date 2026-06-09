# WMDSPPropClear

- ea: `0x180010b30`
- end: `0x180010b74`
- name: `WMDSPPropClear`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bff8`
- `0x180010640`

## callees

- `0x180010b30`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010b61`
- `OLEAUT32!__imp_SysFreeString` at `0x180010b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b4e`

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
0x180010b30  push    rbx
0x180010b32  sub     rsp, 20h
0x180010b36  mov     rbx, rdx
0x180010b39  cmp     cx, 8
0x180010b3d  jz      short loc_180010B5E
0x180010b3f  cmp     cx, 41h ; 'A'
0x180010b43  jnz     short loc_180010B6E
0x180010b45  mov     rcx, [rdx+8]; pv
0x180010b49  test    rcx, rcx
0x180010b4c  jz      short loc_180010B54
0x180010b4e  call    cs:__imp_CoTaskMemFree
0x180010b54  mov     qword ptr [rbx+8], 0
0x180010b5c  jmp     short loc_180010B6E
0x180010b5e  mov     rcx, [rdx]; bstrString
0x180010b61  call    cs:__imp_SysFreeString
0x180010b67  mov     qword ptr [rbx], 0
0x180010b6e  add     rsp, 20h
0x180010b72  pop     rbx
0x180010b73  retn
```
