# CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)

- ea: `0x180070b18`
- end: `0x180070bb6`
- name: `?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z`
- size: `158`
- prototype: `int(CWMProperty *__hidden this, struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007064c`

## callees

- `0x18006c404`
- `0x180070b18`
- `0x180071524`
- `0x180071710`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180070b68`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180070b68`
- `PROPSYS!PropVariantChangeType` at `0x180070b34`
- `PROPSYS!PropVariantChangeType` at `0x180070b34`

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
0x180070b18  push    rbx
0x180070b1a  push    rbp
0x180070b1b  push    rsi
0x180070b1c  push    rdi
0x180070b1d  sub     rsp, 48h
0x180070b21  mov     rsi, r8
0x180070b24  mov     rdi, rdx
0x180070b27  mov     rdx, rsi; propvarSrc
0x180070b2a  mov     rcx, rdi; ppropvarDest
0x180070b2d  xor     r8d, r8d; flags
0x180070b30  movzx   ebp, r9w
0x180070b34  call    cs:__imp_PropVariantChangeType
0x180070b3a  mov     ebx, eax
0x180070b3c  test    eax, eax
0x180070b3e  jns     short loc_180070BAB
0x180070b40  mov     rdx, rsi; pvarSrc
0x180070b43  lea     rcx, [rsp+68h+pvarSrc]; pvarDest
0x180070b48  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x180070b4d  movzx   edx, bp; unsigned __int16
0x180070b50  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180070b55  call    ?Convert@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@G@Z; CMFPropVariantConvert::Convert(CMFPropVariant *,ushort)
0x180070b5a  mov     ebx, eax
0x180070b5c  test    eax, eax
0x180070b5e  js      short loc_180070B70
0x180070b60  lea     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x180070b65  mov     rcx, rdi; pvarDest
0x180070b68  call    cs:__imp_PropVariantCopy
0x180070b6e  mov     ebx, eax
0x180070b70  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180070b75  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180070b7a  test    ebx, ebx
0x180070b7c  jns     short loc_180070BAB
0x180070b7e  cmp     word ptr [rsi], 15h
0x180070b82  jnz     short loc_180070BAB
0x180070b84  mov     ecx, 40h ; '@'
0x180070b89  cmp     bp, cx
0x180070b8c  jnz     short loc_180070BAB
0x180070b8e  xor     eax, eax
0x180070b90  xorps   xmm0, xmm0
0x180070b93  movups  xmmword ptr [rdi], xmm0
0x180070b96  mov     [rdi+10h], rax
0x180070b9a  xor     ebx, ebx
0x180070b9c  mov     [rdi], cx
0x180070b9f  mov     eax, [rsi+8]
0x180070ba2  mov     [rdi+8], eax
0x180070ba5  mov     eax, [rsi+0Ch]
0x180070ba8  mov     [rdi+0Ch], eax
0x180070bab  mov     eax, ebx
0x180070bad  add     rsp, 48h
0x180070bb1  pop     rdi
0x180070bb2  pop     rsi
0x180070bb3  pop     rbp
0x180070bb4  pop     rbx
0x180070bb5  retn
```
