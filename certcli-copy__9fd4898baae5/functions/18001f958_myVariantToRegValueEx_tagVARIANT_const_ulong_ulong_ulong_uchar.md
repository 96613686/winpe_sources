# myVariantToRegValueEx(tagVARIANT const *,ulong,ulong *,ulong *,uchar * *)

- ea: `0x18001f958`
- end: `0x18001fe22`
- name: `?myVariantToRegValueEx@@YAJPEBUtagVARIANT@@KPEAK1PEAPEAE@Z`
- size: `1226`
- prototype: `__int64 __fastcall(const struct tagVARIANT *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180028a64`
- `0x18002bbd8`

## callees

- `0x180002306`
- `0x18000b9cc`
- `0x18000ba10`
- `0x18001f958`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fdbb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fdbb`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001fad7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001fb88`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001fad7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001fb88`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001fb1e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001fbcf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001fb1e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001fbcf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001fafc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001fbad`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001fafc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001fbad`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001fb3d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001fbee`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001fb3d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001fbee`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001fdf6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001fdf6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001fa40`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001fcff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001fa40`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001fcff`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001faab`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001faab`

## pseudocode

```c
__int64 __fastcall myVariantToRegValueEx(
        const struct tagVARIANT *a1,
        __int64 a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  int v5; // r13d
  unsigned int v7; // edi
  SAFEARRAY *v8; // rbx
  unsigned int vt; // r8d
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v10; // rbx
  unsigned int v11; // ecx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v12; // rdx
  unsigned int v13; // ecx
  SAFEARRAY *v14; // rcx
  HRESULT LBound; // eax
  int v16; // edx
  HRESULT UBound; // eax
  HRESULT v18; // eax
  const OLECHAR *p_uiVal; // r14
  SIZE_T v20; // rsi
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rsi
  int i; // ecx
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned __int8 *v28; // rax
  unsigned __int16 *v29; // r11
  unsigned __int64 v30; // r12
  __int64 v31; // r11
  __int64 v32; // rax
  __int64 v33; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  const OLECHAR *llVal; // rax
  bool v36; // zf
  __int64 v37; // r15
  unsigned __int8 *v38; // rax
  __int64 plUbound; // [rsp+20h] [rbp-40h] BYREF
  void *ppvData; // [rsp+28h] [rbp-38h] BYREF
  unsigned int *v42; // [rsp+30h] [rbp-30h]
  unsigned __int16 v43[12]; // [rsp+38h] [rbp-28h] BYREF

  v5 = 0;
  v42 = a4;
  plUbound = 0;
  *a5 = 0;
  v7 = 0;
  *a4 = 0;
  v8 = 0;
  vt = a1->vt;
  ppvData = 0;
  if ( vt > 0x2011 )
  {
    switch ( vt )
    {
      case 0x4002u:
        if ( !a1->llVal )
        {
          v13 = 145752474;
          goto LABEL_64;
        }
        goto LABEL_82;
      case 0x4003u:
        if ( !a1->llVal )
        {
          v13 = 146932122;
          goto LABEL_64;
        }
        goto LABEL_78;
      case 0x4008u:
        if ( !a1->llVal )
        {
          v13 = 141230490;
          goto LABEL_64;
        }
LABEL_67:
        p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->llVal;
        if ( (vt & 0x4000) != 0 )
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
        llVal = (const OLECHAR *)p_llVal->llVal;
        p_uiVal = &psz;
        v36 = p_llVal->llVal == 0;
        *a3 = 1;
        if ( !v36 )
          p_uiVal = llVal;
        v37 = -1;
        do
          ++v37;
        while ( p_uiVal[v37] );
        v20 = 2 * v37 + 2;
LABEL_74:
        if ( v20 >= 0x10000 )
        {
          v16 = -2147024362;
          v13 = 154141082;
          goto LABEL_65;
        }
        goto LABEL_85;
      case 0x6008u:
        if ( a1->llVal )
          goto LABEL_9;
        v13 = 148111770;
        goto LABEL_64;
    }
    if ( vt != 24593 )
      goto LABEL_24;
    v12 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->llVal;
    if ( !a1->llVal )
    {
      v13 = 142868890;
      goto LABEL_64;
    }
LABEL_14:
    if ( (vt & 0x4000) != 0 )
      v12 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v12->llVal;
    v8 = (SAFEARRAY *)v12->llVal;
    if ( !v12->llVal )
    {
      v11 = 143589786;
      goto LABEL_18;
    }
    v14 = (SAFEARRAY *)v12->llVal;
    *a3 = 3;
    if ( SafeArrayGetDim(v14) == 1 )
    {
      LBound = SafeArrayGetLBound(v8, 1u, (LONG *)&plUbound + 1);
      v7 = LBound;
      if ( LBound )
      {
        v16 = LBound;
        v13 = 144441754;
      }
      else
      {
        UBound = SafeArrayGetUBound(v8, 1u, (LONG *)&plUbound);
        v7 = UBound;
        if ( UBound )
        {
          v16 = UBound;
          v13 = 144834970;
        }
        else
        {
          v18 = SafeArrayAccessData(v8, &ppvData);
          v7 = v18;
          if ( !v18 )
          {
            p_uiVal = (const OLECHAR *)ppvData;
            v20 = (int)plUbound - HIDWORD(plUbound) + 1;
            goto LABEL_74;
          }
          v16 = v18;
          v13 = 145031578;
        }
      }
LABEL_66:
      CSPrintErrorLineFile(v13, v16);
      goto LABEL_90;
    }
    v13 = 143983002;
LABEL_64:
    v16 = -2147024809;
    goto LABEL_65;
  }
  switch ( vt )
  {
    case 0x2011u:
      v12 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->llVal;
      goto LABEL_14;
    case 2u:
LABEL_82:
      *a3 = 4;
      p_uiVal = &a1->uiVal;
      if ( (a1->vt & 0x4000) != 0 )
        p_uiVal = *(const OLECHAR **)p_uiVal;
      v20 = 2;
LABEL_85:
      if ( p_uiVal )
      {
        v38 = (unsigned __int8 *)LocalAlloc(0, v20);
        *a5 = v38;
        if ( !v38 )
        {
          v16 = -2147024882;
          v13 = 154665370;
          goto LABEL_65;
        }
        memcpy_0(v38, p_uiVal, v20);
      }
      goto LABEL_89;
    case 3u:
      goto LABEL_78;
    case 8u:
      goto LABEL_67;
    case 0x12u:
      goto LABEL_82;
    case 0x13u:
LABEL_78:
      v20 = 4;
      p_uiVal = &a1->uiVal;
      *a3 = 4;
      if ( (a1->vt & 0x4000) != 0 )
        p_uiVal = *(const OLECHAR **)p_uiVal;
      goto LABEL_85;
  }
  if ( vt != 8200 )
  {
LABEL_24:
    StringCchPrintfW(v43, 0xCu, L"%04x", vt, plUbound);
    v7 = -2147024809;
    CSPrintErrorLineFileData(v43, 0x929019Au, -2147024809);
    goto LABEL_90;
  }
LABEL_9:
  v10 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->llVal;
  if ( (vt & 0x4000) != 0 )
    v10 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v10->llVal;
  v8 = (SAFEARRAY *)v10->llVal;
  if ( !v8 )
  {
    v11 = 148898202;
LABEL_18:
    v7 = -2147024809;
    CSPrintErrorLineFile(v11, -2147024809);
    v8 = 0;
    goto LABEL_90;
  }
  *a3 = 7;
  if ( SafeArrayGetDim(v8) != 1 )
  {
    v13 = 149356954;
    goto LABEL_64;
  }
  v21 = SafeArrayGetLBound(v8, 1u, (LONG *)&plUbound + 1);
  v7 = v21;
  if ( v21 )
  {
    v16 = v21;
    v13 = 149815706;
    goto LABEL_66;
  }
  v22 = SafeArrayGetUBound(v8, 1u, (LONG *)&plUbound);
  v7 = v22;
  if ( v22 )
  {
    v16 = v22;
    v13 = 150208922;
    goto LABEL_66;
  }
  v23 = SafeArrayAccessData(v8, &ppvData);
  v7 = v23;
  if ( v23 )
  {
    v16 = v23;
    v13 = 150405530;
    goto LABEL_66;
  }
  v24 = 0;
  for ( i = 0; i <= (int)plUbound - HIDWORD(plUbound); ++i )
  {
    v26 = *((_QWORD *)ppvData + i);
    if ( !v26 )
    {
      v7 = -2147467261;
      v13 = 150995354;
      v16 = -2147467261;
      goto LABEL_66;
    }
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    v24 += v27 + 1;
  }
  v20 = 2 * v24 + 2;
  if ( v20 >= 0x10000 )
  {
    v16 = -2147024362;
    v13 = 151650714;
LABEL_65:
    v7 = v16;
    goto LABEL_66;
  }
  v28 = (unsigned __int8 *)LocalAlloc(0, v20);
  v29 = (unsigned __int16 *)v28;
  if ( !v28 )
  {
    v16 = -2147024882;
    v13 = 152109466;
    goto LABEL_65;
  }
  *a5 = v28;
  v30 = v20 >> 1;
  if ( (int)plUbound - HIDWORD(plUbound) >= 0 )
  {
    do
    {
      StringCchCopyW(v29, v30, *((const unsigned __int16 **)ppvData + v5));
      v32 = -1;
      do
        ++v32;
      while ( *(_WORD *)(v31 + 2 * v32) );
      v33 = v32 + 1;
      ++v5;
      v30 -= v33;
      v29 = (unsigned __int16 *)(v31 + 2 * v33);
    }
    while ( v5 <= (int)plUbound - HIDWORD(plUbound) );
  }
  *v29 = 0;
LABEL_89:
  *v42 = v20;
LABEL_90:
  if ( ppvData )
    SafeArrayUnaccessData(v8);
  return v7;
}

```

## disassembly

```asm
0x18001f958  mov     [rsp-38h+arg_8], rbx
0x18001f95d  push    rbp
0x18001f95e  push    rsi
0x18001f95f  push    rdi
0x18001f960  push    r12
0x18001f962  push    r13
0x18001f964  push    r14
0x18001f966  push    r15
0x18001f968  mov     rbp, rsp
0x18001f96b  sub     rsp, 60h
0x18001f96f  mov     rax, cs:__security_cookie
0x18001f976  xor     rax, rsp
0x18001f979  mov     [rbp+var_10], rax
0x18001f97d  mov     r12, [rbp+arg_20]
0x18001f981  xor     r13d, r13d
0x18001f984  mov     r10, r8
0x18001f987  mov     [rbp+var_30], r9
0x18001f98b  mov     eax, 2011h
0x18001f990  mov     [rbp+plLbound], r13d
0x18001f994  mov     rdx, rcx
0x18001f997  mov     [rbp+plUbound], r13d
0x18001f99b  mov     [r12], r13
0x18001f99f  mov     edi, r13d
0x18001f9a2  mov     [r9], r13d
0x18001f9a5  mov     ebx, r13d
0x18001f9a8  movzx   r8d, word ptr [rcx]
0x18001f9ac  mov     [rbp+ppvData], r13
0x18001f9b0  cmp     r8d, eax
0x18001f9b3  ja      loc_18001FA4E
0x18001f9b9  jz      short loc_18001FA19
0x18001f9bb  mov     ecx, r8d
0x18001f9be  sub     ecx, 2
0x18001f9c1  jz      loc_18001FD94
0x18001f9c7  sub     ecx, 1
0x18001f9ca  jz      loc_18001FD69
0x18001f9d0  sub     ecx, 5
0x18001f9d3  jz      loc_18001FD0A
0x18001f9d9  sub     ecx, 0Ah
0x18001f9dc  jz      loc_18001FD94
0x18001f9e2  sub     ecx, 1
0x18001f9e5  jz      loc_18001FD69
0x18001f9eb  cmp     ecx, 1FF5h
0x18001f9f1  jnz     loc_18001FA80
0x18001f9f7  bt      r8w, 0Eh
0x18001f9fd  lea     rbx, [rdx+8]
0x18001fa01  jnb     short loc_18001FA06
0x18001fa03  mov     rbx, [rbx]
0x18001fa06  mov     rbx, [rbx]
0x18001fa09  test    rbx, rbx
0x18001fa0c  jnz     loc_18001FB7E
0x18001fa12  mov     ecx, 8E0019Ah
0x18001fa17  jmp     short loc_18001FA39
0x18001fa19  add     rdx, 8
0x18001fa1d  bt      r8w, 0Eh
0x18001fa23  jnb     short loc_18001FA28
0x18001fa25  mov     rdx, [rdx]
0x18001fa28  mov     rbx, [rdx]
0x18001fa2b  test    rbx, rbx
0x18001fa2e  jnz     loc_18001FACD
0x18001fa34  mov     ecx, 88F019Ah
0x18001fa39  mov     edx, 80070057h
0x18001fa3e  mov     edi, edx
0x18001fa40  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001fa46  mov     rbx, r13
0x18001fa49  jmp     loc_18001FDED
0x18001fa4e  mov     ecx, r8d
0x18001fa51  sub     ecx, 4002h
0x18001fa57  jz      loc_18001FD84
0x18001fa5d  sub     ecx, 1
0x18001fa60  jz      loc_18001FD5C
0x18001fa66  sub     ecx, 5
0x18001fa69  jz      loc_18001FCED
0x18001fa6f  sub     ecx, 2000h
0x18001fa75  jz      loc_18001FB6A
0x18001fa7b  cmp     ecx, 9
0x18001fa7e  jz      short loc_18001FAB6
0x18001fa80  mov     r9d, r8d
0x18001fa83  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x18001fa87  lea     r8, Format; "%04x"
0x18001fa8e  mov     edx, 0Ch; unsigned __int64
0x18001fa93  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fa98  mov     edx, 80070057h
0x18001fa9d  lea     rcx, [rbp+var_28]
0x18001faa1  mov     edi, edx
0x18001faa3  mov     r8d, edx
0x18001faa6  mov     edx, 929019Ah
0x18001faab  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001fab1  jmp     loc_18001FDED
0x18001fab6  add     rdx, 8
0x18001faba  cmp     [rdx], r13
0x18001fabd  jnz     loc_18001FA1D
0x18001fac3  mov     ecx, 884019Ah
0x18001fac8  jmp     loc_18001FCF8
0x18001facd  mov     rcx, rbx; psa
0x18001fad0  mov     dword ptr [r10], 3
0x18001fad7  call    cs:__imp_SafeArrayGetDim
0x18001fadd  mov     r14d, 1
0x18001fae3  cmp     eax, r14d
0x18001fae6  jz      short loc_18001FAF2
0x18001fae8  mov     ecx, 895019Ah
0x18001faed  jmp     loc_18001FCF8
0x18001faf2  lea     r8, [rbp+plLbound]; plLbound
0x18001faf6  mov     edx, r14d; nDim
0x18001faf9  mov     rcx, rbx; psa
0x18001fafc  call    cs:__imp_SafeArrayGetLBound
0x18001fb02  mov     edi, eax
0x18001fb04  test    eax, eax
0x18001fb06  jz      short loc_18001FB14
0x18001fb08  mov     edx, eax
0x18001fb0a  mov     ecx, 89C019Ah
0x18001fb0f  jmp     loc_18001FCFF
0x18001fb14  lea     r8, [rbp+plUbound]; plUbound
0x18001fb18  mov     edx, r14d; nDim
0x18001fb1b  mov     rcx, rbx; psa
0x18001fb1e  call    cs:__imp_SafeArrayGetUBound
0x18001fb24  mov     edi, eax
0x18001fb26  test    eax, eax
0x18001fb28  jz      short loc_18001FB36
0x18001fb2a  mov     edx, eax
0x18001fb2c  mov     ecx, 8A2019Ah
0x18001fb31  jmp     loc_18001FCFF
0x18001fb36  lea     rdx, [rbp+ppvData]; ppvData
0x18001fb3a  mov     rcx, rbx; psa
0x18001fb3d  call    cs:__imp_SafeArrayAccessData
0x18001fb43  mov     edi, eax
0x18001fb45  test    eax, eax
0x18001fb47  jz      short loc_18001FB55
0x18001fb49  mov     edx, eax
0x18001fb4b  mov     ecx, 8A5019Ah
0x18001fb50  jmp     loc_18001FCFF
0x18001fb55  mov     eax, [rbp+plUbound]
0x18001fb58  sub     eax, [rbp+plLbound]
0x18001fb5b  add     eax, r14d
0x18001fb5e  mov     r14, [rbp+ppvData]
0x18001fb62  movsxd  rsi, eax
0x18001fb65  jmp     loc_18001FD47
0x18001fb6a  cmp     [rdx+8], r13
0x18001fb6e  jnz     loc_18001F9F7
0x18001fb74  mov     ecx, 8D4019Ah
0x18001fb79  jmp     loc_18001FCF8
0x18001fb7e  mov     rcx, rbx; psa
0x18001fb81  mov     dword ptr [r10], 7
0x18001fb88  call    cs:__imp_SafeArrayGetDim
0x18001fb8e  mov     r14d, 1
0x18001fb94  cmp     eax, r14d
0x18001fb97  jz      short loc_18001FBA3
0x18001fb99  mov     ecx, 8E7019Ah
0x18001fb9e  jmp     loc_18001FCF8
0x18001fba3  lea     r8, [rbp+plLbound]; plLbound
0x18001fba7  mov     edx, r14d; nDim
0x18001fbaa  mov     rcx, rbx; psa
0x18001fbad  call    cs:__imp_SafeArrayGetLBound
0x18001fbb3  mov     edi, eax
0x18001fbb5  test    eax, eax
0x18001fbb7  jz      short loc_18001FBC5
0x18001fbb9  mov     edx, eax
0x18001fbbb  mov     ecx, 8EE019Ah
0x18001fbc0  jmp     loc_18001FCFF
0x18001fbc5  lea     r8, [rbp+plUbound]; plUbound
0x18001fbc9  mov     edx, r14d; nDim
0x18001fbcc  mov     rcx, rbx; psa
0x18001fbcf  call    cs:__imp_SafeArrayGetUBound
0x18001fbd5  mov     edi, eax
0x18001fbd7  test    eax, eax
0x18001fbd9  jz      short loc_18001FBE7
0x18001fbdb  mov     edx, eax
0x18001fbdd  mov     ecx, 8F4019Ah
0x18001fbe2  jmp     loc_18001FCFF
0x18001fbe7  lea     rdx, [rbp+ppvData]; ppvData
0x18001fbeb  mov     rcx, rbx; psa
0x18001fbee  call    cs:__imp_SafeArrayAccessData
0x18001fbf4  mov     edi, eax
0x18001fbf6  test    eax, eax
0x18001fbf8  jz      short loc_18001FC06
0x18001fbfa  mov     edx, eax
0x18001fbfc  mov     ecx, 8F7019Ah
0x18001fc01  jmp     loc_18001FCFF
0x18001fc06  mov     r8, [rbp+ppvData]
0x18001fc0a  mov     rsi, r13
0x18001fc0d  mov     ecx, r13d
0x18001fc10  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001fc14  mov     eax, [rbp+plUbound]
0x18001fc17  sub     eax, [rbp+plLbound]
0x18001fc1a  cmp     ecx, eax
0x18001fc1c  jg      short loc_18001FC53
0x18001fc1e  movsxd  rax, ecx
0x18001fc21  mov     rdx, [r8+rax*8]
0x18001fc25  test    rdx, rdx
0x18001fc28  jz      short loc_18001FC42
0x18001fc2a  mov     rax, r15
0x18001fc2d  inc     rax
0x18001fc30  cmp     [rdx+rax*2], r13w
0x18001fc35  jnz     short loc_18001FC2D
0x18001fc37  inc     rsi
0x18001fc3a  add     rsi, rax
0x18001fc3d  add     ecx, r14d
0x18001fc40  jmp     short loc_18001FC14
0x18001fc42  mov     edi, 80004003h
0x18001fc47  mov     ecx, 900019Ah
0x18001fc4c  mov     edx, edi
0x18001fc4e  jmp     loc_18001FCFF
0x18001fc53  lea     rsi, ds:2[rsi*2]
0x18001fc5b  cmp     rsi, 10000h
0x18001fc62  jb      short loc_18001FC73
0x18001fc64  mov     edx, 80070216h
0x18001fc69  mov     ecx, 90A019Ah
0x18001fc6e  jmp     loc_18001FCFD
0x18001fc73  mov     rdx, rsi; uBytes
0x18001fc76  xor     ecx, ecx; uFlags
0x18001fc78  call    cs:__imp_LocalAlloc
0x18001fc7e  mov     r11, rax
0x18001fc81  test    rax, rax
0x18001fc84  jnz     short loc_18001FC92
0x18001fc86  mov     edx, 8007000Eh
0x18001fc8b  mov     ecx, 911019Ah
0x18001fc90  jmp     short loc_18001FCFD
0x18001fc92  mov     [r12], rax
0x18001fc96  mov     r12, rsi
0x18001fc99  mov     eax, [rbp+plUbound]
0x18001fc9c  shr     r12, 1
0x18001fc9f  cmp     eax, [rbp+plLbound]
0x18001fca2  js      short loc_18001FCE1
0x18001fca4  mov     r8, [rbp+ppvData]
0x18001fca8  mov     rdx, r12; unsigned __int64
0x18001fcab  movsxd  rax, r13d
0x18001fcae  mov     rcx, r11; unsigned __int16 *
0x18001fcb1  mov     r8, [r8+rax*8]; unsigned __int16 *
0x18001fcb5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fcba  mov     rax, r15
0x18001fcbd  xor     ecx, ecx
0x18001fcbf  inc     rax
0x18001fcc2  cmp     [r11+rax*2], cx
0x18001fcc7  jnz     short loc_18001FCBF
0x18001fcc9  inc     rax
0x18001fccc  add     r13d, r14d
0x18001fccf  sub     r12, rax
0x18001fcd2  lea     r11, [r11+rax*2]
0x18001fcd6  mov     eax, [rbp+plUbound]
0x18001fcd9  sub     eax, [rbp+plLbound]
0x18001fcdc  cmp     r13d, eax
0x18001fcdf  jle     short loc_18001FCA4
0x18001fce1  xor     r13d, r13d
0x18001fce4  mov     [r11], r13w
0x18001fce8  jmp     loc_18001FDE7
0x18001fced  cmp     [rdx+8], r13
0x18001fcf1  jnz     short loc_18001FD0A
0x18001fcf3  mov     ecx, 86B019Ah
0x18001fcf8  mov     edx, 80070057h
0x18001fcfd  mov     edi, edx
0x18001fcff  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001fd05  jmp     loc_18001FDED
0x18001fd0a  add     rdx, 8
0x18001fd0e  bt      r8w, 0Eh
0x18001fd14  jnb     short loc_18001FD19
0x18001fd16  mov     rdx, [rdx]
0x18001fd19  mov     rax, [rdx]
0x18001fd1c  lea     r14, psz
0x18001fd23  test    rax, rax
0x18001fd26  mov     dword ptr [r10], 1
0x18001fd2d  cmovnz  r14, rax
0x18001fd31  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001fd35  inc     r15
0x18001fd38  cmp     [r14+r15*2], r13w
0x18001fd3d  jnz     short loc_18001FD35
0x18001fd3f  lea     rsi, ds:2[r15*2]
0x18001fd47  cmp     rsi, 10000h
0x18001fd4e  jb      short loc_18001FDB1
0x18001fd50  mov     edx, 80070216h
0x18001fd55  mov     ecx, 930019Ah
0x18001fd5a  jmp     short loc_18001FCFD
0x18001fd5c  cmp     [rdx+8], r13
0x18001fd60  jnz     short loc_18001FD69
0x18001fd62  mov     ecx, 8C2019Ah
0x18001fd67  jmp     short loc_18001FCF8
0x18001fd69  mov     esi, 4
0x18001fd6e  lea     r14, [rdx+8]
0x18001fd72  mov     eax, 4000h
0x18001fd77  mov     [r10], esi
0x18001fd7a  test    [rdx], ax
0x18001fd7d  jz      short loc_18001FDB1
0x18001fd7f  mov     r14, [r14]
0x18001fd82  jmp     short loc_18001FDB1
0x18001fd84  cmp     [rdx+8], r13
0x18001fd88  jnz     short loc_18001FD94
0x18001fd8a  mov     ecx, 8B0019Ah
0x18001fd8f  jmp     loc_18001FCF8
0x18001fd94  mov     eax, 4000h
0x18001fd99  mov     dword ptr [r10], 4
0x18001fda0  lea     r14, [rdx+8]
0x18001fda4  test    [rdx], ax
0x18001fda7  jz      short loc_18001FDAC
0x18001fda9  mov     r14, [r14]
0x18001fdac  mov     esi, 2
0x18001fdb1  test    r14, r14
0x18001fdb4  jz      short loc_18001FDE7
0x18001fdb6  mov     rdx, rsi; uBytes
0x18001fdb9  xor     ecx, ecx; uFlags
0x18001fdbb  call    cs:__imp_LocalAlloc
0x18001fdc1  mov     [r12], rax
0x18001fdc5  test    rax, rax
  ... truncated ...
```
