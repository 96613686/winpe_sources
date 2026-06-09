# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x18002470c`
- end: `0x18002475d`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `81`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this, const struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024308`
- `0x180024a04`

## callees

- `0x18002470c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180024733`
- `OLEAUT32!__imp_VariantCopy` at `0x180024733`

## pseudocode

```c
void __fastcall ATL::CComVariant::InternalCopy(VARIANTARG *this, const struct tagVARIANT *a2)
{
  char v2; // di
  HRESULT v4; // eax

  v2 = 0;
  if ( this->vt == 4095 )
  {
    this->vt = 8;
    v2 = 1;
  }
  v4 = VariantCopy(this, a2);
  if ( v2 )
    this->vt = 4095;
  if ( v4 < 0 )
  {
    this->vt = 10;
    this->lVal = v4;
  }
}

```

## disassembly

```asm
0x18002470c  mov     [rsp+arg_0], rbx
0x180024711  mov     [rsp+arg_8], rsi
0x180024716  push    rdi
0x180024717  sub     rsp, 20h
0x18002471b  xor     dil, dil
0x18002471e  mov     esi, 0FFFh
0x180024723  mov     rbx, rcx
0x180024726  cmp     [rcx], si
0x180024729  jnz     short loc_180024733
0x18002472b  mov     word ptr [rcx], 8
0x180024730  mov     dil, 1
0x180024733  call    cs:__imp_VariantCopy
0x180024739  test    dil, dil
0x18002473c  jz      short loc_180024741
0x18002473e  mov     [rbx], si
0x180024741  test    eax, eax
0x180024743  jns     short loc_18002474D
0x180024745  mov     word ptr [rbx], 0Ah
0x18002474a  mov     [rbx+8], eax
0x18002474d  mov     rbx, [rsp+28h+arg_0]
0x180024752  mov     rsi, [rsp+28h+arg_8]
0x180024757  add     rsp, 20h
0x18002475b  pop     rdi
0x18002475c  retn
```
