# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x180005728`
- end: `0x180005779`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `81`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this, const struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800056c4`
- `0x1800133dc`
- `0x180013584`
- `0x1800136d8`

## callees

- `0x180005728`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000574f`
- `OLEAUT32!__imp_VariantCopy` at `0x18000574f`

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
0x180005728  mov     [rsp+arg_0], rbx
0x18000572d  mov     [rsp+arg_8], rsi
0x180005732  push    rdi
0x180005733  sub     rsp, 20h
0x180005737  xor     dil, dil
0x18000573a  mov     esi, 0FFFh
0x18000573f  mov     rbx, rcx
0x180005742  cmp     [rcx], si
0x180005745  jnz     short loc_18000574F
0x180005747  mov     word ptr [rcx], 8
0x18000574c  mov     dil, 1
0x18000574f  call    cs:__imp_VariantCopy
0x180005755  test    dil, dil
0x180005758  jz      short loc_18000575D
0x18000575a  mov     [rbx], si
0x18000575d  test    eax, eax
0x18000575f  jns     short loc_180005769
0x180005761  mov     word ptr [rbx], 0Ah
0x180005766  mov     [rbx+8], eax
0x180005769  mov     rbx, [rsp+28h+arg_0]
0x18000576e  mov     rsi, [rsp+28h+arg_8]
0x180005773  add     rsp, 20h
0x180005777  pop     rdi
0x180005778  retn
```
