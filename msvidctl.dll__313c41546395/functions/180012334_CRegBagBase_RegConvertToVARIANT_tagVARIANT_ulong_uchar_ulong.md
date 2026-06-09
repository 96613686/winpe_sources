# CRegBagBase::RegConvertToVARIANT(tagVARIANT *,ulong,uchar *,ulong)

- ea: `0x180012334`
- end: `0x18001259f`
- name: `?RegConvertToVARIANT@CRegBagBase@@IEAAJPEAUtagVARIANT@@KPEAEK@Z`
- size: `619`
- prototype: `int(CRegBagBase *__hidden this, struct tagVARIANT *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f00`

## callees

- `0x180012334`
- `0x1800eee18`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012580`
- `OLEAUT32!__imp_SysAllocString` at `0x180012580`
- `OLEAUT32!__imp_SysFreeString` at `0x180012431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124be`
- `OLEAUT32!__imp_SysFreeString` at `0x18001256d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124be`
- `OLEAUT32!__imp_SysFreeString` at `0x18001256d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001239d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012486`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012518`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012546`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001239d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012486`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012518`
- `OLEAUT32!__imp_VariantChangeType` at `0x180012546`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800123cb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800123cb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800123ee`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800123ee`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001240b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001240b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180012440`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800124dc`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180012440`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800124dc`

## pseudocode

```c
__int64 __fastcall CRegBagBase::RegConvertToVARIANT(
        CRegBagBase *this,
        struct tagVARIANT *a2,
        int a3,
        const OLECHAR *a4,
        size_t Size)
{
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  unsigned int v10; // ebp
  SAFEARRAY *v11; // rsi
  SAFEARRAY *v12; // rax
  OLECHAR *v14; // rcx
  BSTR v15; // rax
  size_t v16; // r8
  BSTR v17; // rax
  OLECHAR *v18; // rcx
  size_t v19; // rsi
  OLECHAR *bstrVal; // rcx
  void *ppvData; // [rsp+20h] [rbp-38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp+8h] BYREF

  rgsabound = (SAFEARRAYBOUND)this;
  v7 = a3 - 1;
  if ( !v7 )
  {
    if ( !a2->vt || a2->vt == 1 )
    {
      a2->vt = 8;
      a2->llVal = 0;
    }
    else if ( a2->vt != 8 && VariantChangeType(a2, a2, 0, 8u) < 0 )
    {
      return 2147942487LL;
    }
    bstrVal = a2->bstrVal;
    if ( bstrVal )
      SysFreeString(bstrVal);
    if ( !(_DWORD)Size )
    {
      a2->llVal = 0;
      return 0;
    }
    v17 = SysAllocString(a4);
    goto LABEL_48;
  }
  v8 = v7 - 3;
  if ( !v8 )
  {
    if ( a2->vt == 19 || VariantChangeType(a2, a2, 0, 0x13u) >= 0 )
    {
      a2->lVal = *(_DWORD *)a4;
      return 0;
    }
    return 2147942487LL;
  }
  v9 = v8 - 3;
  if ( !v9 )
  {
    if ( a2->vt && a2->vt != 1 && (a2->vt == 8 || a2->vt == 4104) )
    {
      v18 = a2->bstrVal;
      if ( v18 )
        SysFreeString(v18);
    }
    v19 = (unsigned int)Size;
    a2->vt = 4095;
    if ( !(_DWORD)v19 )
      return 0;
    v15 = SysAllocStringByteLen(0, v19);
    a2->llVal = (LONGLONG)v15;
    if ( !v15 )
      return 2147942414LL;
    if ( !a4 )
      return 0;
    v16 = v19;
LABEL_20:
    memcpy_0(v15, a4, v16);
    return 0;
  }
  if ( v9 == 4 )
  {
    if ( a2->vt != 21 && VariantChangeType(a2, a2, 0, 0x15u) < 0 )
      return 2147942487LL;
    v17 = *(BSTR *)a4;
LABEL_48:
    a2->llVal = (LONGLONG)v17;
    return 0;
  }
  if ( a2->vt == 8 || a2->vt == 4095 )
  {
    v14 = a2->bstrVal;
    if ( v14 )
      SysFreeString(v14);
    v15 = SysAllocStringByteLen(0, Size);
    a2->llVal = (LONGLONG)v15;
    if ( !v15 )
      return 2147942414LL;
    if ( !a4 )
      return 0;
    v16 = (unsigned int)Size;
    goto LABEL_20;
  }
  if ( a2->vt != 8209 && VariantChangeType(a2, a2, 0, 0x2011u) < 0 )
    return 2147942487LL;
  v10 = Size;
  v11 = 0;
  if ( (_DWORD)Size )
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = Size;
    v12 = SafeArrayCreate(0x11u, 1u, &rgsabound);
    v11 = v12;
    if ( v12 )
    {
      ppvData = 0;
      if ( SafeArrayAccessData(v12, &ppvData) )
        return 2147500037LL;
      memcpy_0(ppvData, a4, v10);
      if ( SafeArrayUnaccessData(v11) )
        return 2147500037LL;
      goto LABEL_14;
    }
    return 2147942414LL;
  }
LABEL_14:
  a2->llVal = (LONGLONG)v11;
  return 0;
}

```

## disassembly

```asm
0x180012334  mov     qword ptr [rsp+rgsabound.cElements], rcx
0x180012339  push    rbx
0x18001233a  push    rbp
0x18001233b  push    rsi
0x18001233c  push    rdi
0x18001233d  sub     rsp, 38h
0x180012341  mov     rdi, r9
0x180012344  mov     rbx, rdx
0x180012347  sub     r8d, 1
0x18001234b  jz      loc_180012529
0x180012351  sub     r8d, 3
0x180012355  jz      loc_180012506
0x18001235b  sub     r8d, 3
0x18001235f  jz      loc_18001249C
0x180012365  cmp     r8d, 4
0x180012369  jz      loc_180012474
0x18001236f  mov     eax, 8
0x180012374  cmp     [rdx], ax
0x180012377  jz      loc_180012428
0x18001237d  mov     eax, 0FFFh
0x180012382  cmp     [rdx], ax
0x180012385  jz      loc_180012428
0x18001238b  mov     r9d, 2011h; vt
0x180012391  cmp     [rdx], r9w
0x180012395  jz      short loc_1800123AB
0x180012397  xor     r8d, r8d; wFlags
0x18001239a  mov     rcx, rdx; pvargDest
0x18001239d  call    cs:__imp_VariantChangeType
0x1800123a3  test    eax, eax
0x1800123a5  js      loc_180012550
0x1800123ab  mov     ebp, dword ptr [rsp+58h+Size]
0x1800123b2  xor     esi, esi
0x1800123b4  test    ebp, ebp
0x1800123b6  jz      short loc_18001241F
0x1800123b8  lea     ecx, [rsi+11h]; vt
0x1800123bb  mov     [rsp+58h+rgsabound.lLbound], esi
0x1800123bf  lea     r8, [rsp+58h+rgsabound]; rgsabound
0x1800123c4  mov     [rsp+58h+rgsabound.cElements], ebp
0x1800123c8  lea     edx, [rsi+1]; cDims
0x1800123cb  call    cs:__imp_SafeArrayCreate
0x1800123d1  mov     rsi, rax
0x1800123d4  test    rax, rax
0x1800123d7  jz      loc_1800124EB
0x1800123dd  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800123e2  mov     [rsp+58h+ppvData], 0
0x1800123eb  mov     rcx, rax; psa
0x1800123ee  call    cs:__imp_SafeArrayAccessData
0x1800123f4  test    eax, eax
0x1800123f6  jnz     short loc_180012415
0x1800123f8  mov     rcx, [rsp+58h+ppvData]; void *
0x1800123fd  mov     r8d, ebp; Size
0x180012400  mov     rdx, rdi; Src
0x180012403  call    memcpy_0
0x180012408  mov     rcx, rsi; psa
0x18001240b  call    cs:__imp_SafeArrayUnaccessData
0x180012411  test    eax, eax
0x180012413  jz      short loc_18001241F
0x180012415  mov     eax, 80004005h
0x18001241a  jmp     loc_180012596
0x18001241f  mov     [rbx+8], rsi
0x180012423  jmp     loc_180012594
0x180012428  mov     rcx, [rdx+8]; bstrString
0x18001242c  test    rcx, rcx
0x18001242f  jz      short loc_180012437
0x180012431  call    cs:__imp_SysFreeString
0x180012437  mov     edx, dword ptr [rsp+58h+Size]; len
0x18001243e  xor     ecx, ecx; psz
0x180012440  call    cs:__imp_SysAllocStringByteLen
0x180012446  mov     [rbx+8], rax
0x18001244a  test    rax, rax
0x18001244d  jz      loc_1800124EB
0x180012453  test    rdi, rdi
0x180012456  jz      loc_180012594
0x18001245c  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x180012464  mov     rdx, rdi; Src
0x180012467  mov     rcx, rax; void *
0x18001246a  call    memcpy_0
0x18001246f  jmp     loc_180012594
0x180012474  mov     r9d, 15h; vt
0x18001247a  cmp     [rdx], r9w
0x18001247e  jz      short loc_180012494
0x180012480  xor     r8d, r8d; wFlags
0x180012483  mov     rcx, rbx; pvargDest
0x180012486  call    cs:__imp_VariantChangeType
0x18001248c  test    eax, eax
0x18001248e  js      loc_180012550
0x180012494  mov     rax, [rdi]
0x180012497  jmp     loc_180012586
0x18001249c  movzx   ecx, word ptr [rdx]
0x18001249f  test    ecx, ecx
0x1800124a1  jz      short loc_1800124C4
0x1800124a3  sub     ecx, 1
0x1800124a6  jz      short loc_1800124C4
0x1800124a8  sub     ecx, 7
0x1800124ab  jz      short loc_1800124B5
0x1800124ad  cmp     ecx, 1000h
0x1800124b3  jnz     short loc_1800124C4
0x1800124b5  mov     rcx, [rdx+8]; bstrString
0x1800124b9  test    rcx, rcx
0x1800124bc  jz      short loc_1800124C4
0x1800124be  call    cs:__imp_SysFreeString
0x1800124c4  mov     esi, dword ptr [rsp+58h+Size]
0x1800124cb  mov     word ptr [rbx], 0FFFh
0x1800124d0  test    esi, esi
0x1800124d2  jz      loc_180012594
0x1800124d8  mov     edx, esi; len
0x1800124da  xor     ecx, ecx; psz
0x1800124dc  call    cs:__imp_SysAllocStringByteLen
0x1800124e2  mov     [rbx+8], rax
0x1800124e6  test    rax, rax
0x1800124e9  jnz     short loc_1800124F5
0x1800124eb  mov     eax, 8007000Eh
0x1800124f0  jmp     loc_180012596
0x1800124f5  test    rdi, rdi
0x1800124f8  jz      loc_180012594
0x1800124fe  mov     r8, rsi
0x180012501  jmp     loc_180012464
0x180012506  mov     r9d, 13h; vt
0x18001250c  cmp     [rdx], r9w
0x180012510  jz      short loc_180012522
0x180012512  xor     r8d, r8d; wFlags
0x180012515  mov     rcx, rbx; pvargDest
0x180012518  call    cs:__imp_VariantChangeType
0x18001251e  test    eax, eax
0x180012520  js      short loc_180012550
0x180012522  mov     eax, [rdi]
0x180012524  mov     [rbx+8], eax
0x180012527  jmp     short loc_180012594
0x180012529  movzx   ecx, word ptr [rdx]
0x18001252c  test    ecx, ecx
0x18001252e  jz      short loc_180012557
0x180012530  sub     ecx, 1
0x180012533  jz      short loc_180012557
0x180012535  cmp     ecx, 7
0x180012538  jz      short loc_180012564
0x18001253a  mov     r9d, 8; vt
0x180012540  xor     r8d, r8d; wFlags
0x180012543  mov     rcx, rbx; pvargDest
0x180012546  call    cs:__imp_VariantChangeType
0x18001254c  test    eax, eax
0x18001254e  jns     short loc_180012564
0x180012550  mov     eax, 80070057h
0x180012555  jmp     short loc_180012596
0x180012557  mov     word ptr [rdx], 8
0x18001255c  mov     qword ptr [rdx+8], 0
0x180012564  mov     rcx, [rbx+8]; bstrString
0x180012568  test    rcx, rcx
0x18001256b  jz      short loc_180012573
0x18001256d  call    cs:__imp_SysFreeString
0x180012573  cmp     dword ptr [rsp+58h+Size], 0
0x18001257b  jz      short loc_18001258C
0x18001257d  mov     rcx, rdi; psz
0x180012580  call    cs:__imp_SysAllocString
0x180012586  mov     [rbx+8], rax
0x18001258a  jmp     short loc_180012594
0x18001258c  mov     qword ptr [rbx+8], 0
0x180012594  xor     eax, eax
0x180012596  add     rsp, 38h
0x18001259a  pop     rdi
0x18001259b  pop     rsi
0x18001259c  pop     rbp
0x18001259d  pop     rbx
0x18001259e  retn
```
