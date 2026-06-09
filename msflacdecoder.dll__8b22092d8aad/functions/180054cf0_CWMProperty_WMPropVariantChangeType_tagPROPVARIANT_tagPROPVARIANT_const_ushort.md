# CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)

- ea: `0x180054cf0`
- end: `0x180054d8e`
- name: `?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z`
- size: `158`
- prototype: `int(CWMProperty *__hidden this, struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180054820`

## callees

- `0x180034a04`
- `0x180035148`
- `0x180050a48`
- `0x180054cf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054d40`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054d40`
- `PROPSYS!PropVariantChangeType` at `0x180054d0c`
- `PROPSYS!PropVariantChangeType` at `0x180054d0c`

## pseudocode

```c
__int64 __fastcall CWMProperty::WMPropVariantChangeType(
        CWMProperty *this,
        struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        VARTYPE a4)
{
  HRESULT v7; // ebx
  PROPVARIANT pvarSrc; // [rsp+20h] [rbp-48h] BYREF

  v7 = PropVariantChangeType(a2, a3, 0, a4);
  if ( v7 < 0 )
  {
    CMFPropVariant::CMFPropVariant((CMFPropVariant *)&pvarSrc, a3);
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
0x180054cf0  push    rbx
0x180054cf2  push    rbp
0x180054cf3  push    rsi
0x180054cf4  push    rdi
0x180054cf5  sub     rsp, 48h
0x180054cf9  mov     rsi, r8
0x180054cfc  mov     rdi, rdx
0x180054cff  mov     rdx, rsi; propvarSrc
0x180054d02  mov     rcx, rdi; ppropvarDest
0x180054d05  xor     r8d, r8d; flags
0x180054d08  movzx   ebp, r9w
0x180054d0c  call    cs:__imp_PropVariantChangeType
0x180054d12  mov     ebx, eax
0x180054d14  test    eax, eax
0x180054d16  jns     short loc_180054D83
0x180054d18  mov     rdx, rsi; struct tagPROPVARIANT *
0x180054d1b  lea     rcx, [rsp+68h+pvarSrc]; this
0x180054d20  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x180054d25  movzx   edx, bp; unsigned __int16
0x180054d28  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180054d2d  call    ?Convert@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@G@Z; CMFPropVariantConvert::Convert(CMFPropVariant *,ushort)
0x180054d32  mov     ebx, eax
0x180054d34  test    eax, eax
0x180054d36  js      short loc_180054D48
0x180054d38  lea     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x180054d3d  mov     rcx, rdi; pvarDest
0x180054d40  call    cs:__imp_PropVariantCopy
0x180054d46  mov     ebx, eax
0x180054d48  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x180054d4d  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180054d52  test    ebx, ebx
0x180054d54  jns     short loc_180054D83
0x180054d56  cmp     word ptr [rsi], 15h
0x180054d5a  jnz     short loc_180054D83
0x180054d5c  mov     ecx, 40h ; '@'
0x180054d61  cmp     bp, cx
0x180054d64  jnz     short loc_180054D83
0x180054d66  xor     eax, eax
0x180054d68  xorps   xmm0, xmm0
0x180054d6b  movups  xmmword ptr [rdi], xmm0
0x180054d6e  mov     [rdi+10h], rax
0x180054d72  xor     ebx, ebx
0x180054d74  mov     [rdi], cx
0x180054d77  mov     eax, [rsi+8]
0x180054d7a  mov     [rdi+8], eax
0x180054d7d  mov     eax, [rsi+0Ch]
0x180054d80  mov     [rdi+0Ch], eax
0x180054d83  mov     eax, ebx
0x180054d85  add     rsp, 48h
0x180054d89  pop     rdi
0x180054d8a  pop     rsi
0x180054d8b  pop     rbp
0x180054d8c  pop     rbx
0x180054d8d  retn
```
