# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)

- ea: `0x180013e30`
- end: `0x180013e71`
- name: `?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z`
- size: `65`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000763c`
- `0x180007a4c`
- `0x180013c0c`
- `0x180014018`
- `0x18001b89a`

## callees

- `0x180013e30`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180013e57`
- `OLEAUT32!__imp_VariantClear` at `0x180013e57`

## pseudocode

```c
HRESULT __fastcall std::vector<ATL::CComVariant>::_Destroy(__int64 a1, VARIANTARG *a2, VARIANTARG *a3)
{
  VARIANTARG *v4; // rbx
  HRESULT result; // eax

  if ( a2 != a3 )
  {
    v4 = a2;
    do
    {
      if ( v4->vt == 4095 )
        v4->vt = 8;
      result = VariantClear(v4++);
    }
    while ( v4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x180013e30  cmp     rdx, r8
0x180013e33  jz      short locret_180013E70
0x180013e35  mov     [rsp+arg_0], rbx
0x180013e3a  push    rdi
0x180013e3b  sub     rsp, 20h
0x180013e3f  mov     rdi, r8
0x180013e42  mov     rbx, rdx
0x180013e45  mov     eax, 0FFFh
0x180013e4a  cmp     [rbx], ax
0x180013e4d  jnz     short loc_180013E54
0x180013e4f  mov     word ptr [rbx], 8
0x180013e54  mov     rcx, rbx; pvarg
0x180013e57  call    cs:__imp_VariantClear
0x180013e5d  add     rbx, 18h
0x180013e61  cmp     rbx, rdi
0x180013e64  jnz     short loc_180013E45
0x180013e66  mov     rbx, [rsp+28h+arg_0]
0x180013e6b  add     rsp, 20h
0x180013e6f  pop     rdi
0x180013e70  retn
```
