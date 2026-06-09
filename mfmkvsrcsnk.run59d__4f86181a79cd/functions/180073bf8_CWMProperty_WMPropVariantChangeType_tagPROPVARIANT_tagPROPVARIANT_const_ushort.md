# CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)

- ea: `0x180073bf8`
- end: `0x180073ca3`
- name: `?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z`
- size: `171`
- prototype: `int(CWMProperty *__hidden this, struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180073704`

## callees

- `0x18006f224`
- `0x180073bf8`
- `0x1800746f8`
- `0x1800748fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180073c4e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180073c4e`
- `PROPSYS!PropVariantChangeType` at `0x180073c14`
- `PROPSYS!PropVariantChangeType` at `0x180073c14`

## pseudocode

```c
__int64 __fastcall CWMProperty::WMPropVariantChangeType(
        CWMProperty *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3,
        VARTYPE a4)
{
  HRESULT v7; // ebx
  PROPVARIANT pvarSrc; // [rsp+20h] [rbp-48h] BYREF

  v7 = PropVariantChangeType(a2, a3, 0, a4);
  if ( v7 < 0 )
  {
    CMFPropVariant::CMFPropVariant(&pvarSrc, a3);
    v7 = CMFPropVariantConvert::Convert(&pvarSrc, a4);
    if ( v7 >= 0 )
      v7 = PropVariantCopy(a2, &pvarSrc);
    CMFPropVariant::Clear(&pvarSrc);
    if ( v7 < 0 && a3->vt == 21 && a4 == 64 )
    {
      *(_OWORD *)&a2->vt = 0;
      a2->bstrblobVal.pData = 0;
      v7 = 0;
      a2->vt = 64;
      a2->lVal = a3->lVal;
      a2->hVal.HighPart = a3->hVal.HighPart;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180073bf8  push    rbx
0x180073bfa  push    rbp
0x180073bfb  push    rsi
0x180073bfc  push    rdi
0x180073bfd  sub     rsp, 48h
0x180073c01  mov     rsi, r8
0x180073c04  mov     rdi, rdx
0x180073c07  mov     rdx, rsi; propvarSrc
0x180073c0a  mov     rcx, rdi; ppropvarDest
0x180073c0d  xor     r8d, r8d; flags
0x180073c10  movzx   ebp, r9w
0x180073c14  call    cs:__imp_PropVariantChangeType
0x180073c1b  nop     dword ptr [rax+rax+00h]
0x180073c20  mov     ebx, eax
0x180073c22  test    eax, eax
0x180073c24  jns     short loc_180073C97
0x180073c26  mov     rdx, rsi; pvarSrc
0x180073c29  lea     rcx, [rsp+68h+pvarSrc]; pvarDest
0x180073c2e  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x180073c33  movzx   edx, bp; unsigned __int16
0x180073c36  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180073c3b  call    ?Convert@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@G@Z; CMFPropVariantConvert::Convert(CMFPropVariant *,ushort)
0x180073c40  mov     ebx, eax
0x180073c42  test    eax, eax
0x180073c44  js      short loc_180073C5C
0x180073c46  lea     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x180073c4b  mov     rcx, rdi; pvarDest
0x180073c4e  call    cs:__imp_PropVariantCopy
0x180073c55  nop     dword ptr [rax+rax+00h]
0x180073c5a  mov     ebx, eax
0x180073c5c  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180073c61  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180073c66  test    ebx, ebx
0x180073c68  jns     short loc_180073C97
0x180073c6a  cmp     word ptr [rsi], 15h
0x180073c6e  jnz     short loc_180073C97
0x180073c70  mov     ecx, 40h ; '@'
0x180073c75  cmp     bp, cx
0x180073c78  jnz     short loc_180073C97
0x180073c7a  xor     eax, eax
0x180073c7c  xorps   xmm0, xmm0
0x180073c7f  movups  xmmword ptr [rdi], xmm0
0x180073c82  mov     [rdi+10h], rax
0x180073c86  xor     ebx, ebx
0x180073c88  mov     [rdi], cx
0x180073c8b  mov     eax, [rsi+8]
0x180073c8e  mov     [rdi+8], eax
0x180073c91  mov     eax, [rsi+0Ch]
0x180073c94  mov     [rdi+0Ch], eax
0x180073c97  mov     eax, ebx
0x180073c99  add     rsp, 48h
0x180073c9d  pop     rdi
0x180073c9e  pop     rsi
0x180073c9f  pop     rbp
0x180073ca0  pop     rbx
0x180073ca1  retn
```
