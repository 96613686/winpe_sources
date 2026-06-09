# CIISWebService::ConvertArrayToMultiSZ(tagVARIANT,ushort * *)

- ea: `0x1800089e8`
- end: `0x180008c33`
- name: `?ConvertArrayToMultiSZ@CIISWebService@@IEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `587`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008c40`

## callees

- `0x180001054`
- `0x1800089e8`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180008bbc`
- `msvcrt!wcscpy_s` at `0x180008bbc`
- `OLEAUT32!__imp_VariantInit` at `0x180008ae9`
- `OLEAUT32!__imp_VariantInit` at `0x180008ae9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008b1b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008b1b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180008a98`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180008a98`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180008a7e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180008a7e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008afa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008afa`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180008ab7`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180008ab7`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180008c13`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180008c13`

## pseudocode

```c
__int64 __fastcall CIISWebService::ConvertArrayToMultiSZ(
        CIISWebService *this,
        struct tagVARIANT *a2,
        unsigned __int16 **a3)
{
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  SAFEARRAY *llVal; // rsi
  HRESULT LBound; // ebx
  VARIANTARG *v8; // rdi
  int v9; // r14d
  __int64 v10; // rax
  unsigned __int64 v11; // r15
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  wchar_t *i; // r14
  unsigned __int16 *v15; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+40h] BYREF
  int v18; // [rsp+84h] [rbp+44h]
  LONG plUbound; // [rsp+88h] [rbp+48h] BYREF
  LONG plLbound; // [rsp+98h] [rbp+58h] BYREF

  v18 = HIDWORD(this);
  plLbound = 0;
  plUbound = 0;
  rgIndices = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (a2->vt & 0x2000) == 0 )
    return 2147500037LL;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a2->llVal;
  if ( (a2->vt & 0x4000) != 0 )
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
  llVal = (SAFEARRAY *)p_llVal->llVal;
  if ( !llVal )
    goto LABEL_28;
  if ( llVal->cDims == 1 )
  {
    if ( llVal->rgsabound[0].cElements )
    {
      LBound = SafeArrayGetLBound(llVal, 1u, &plLbound);
      if ( LBound < 0 )
        return (unsigned int)LBound;
      LBound = SafeArrayGetUBound(llVal, 1u, &plUbound);
      if ( LBound < 0 )
        return (unsigned int)LBound;
      v8 = (VARIANTARG *)AllocADsMem(24 * (plUbound - plLbound + 1));
      if ( !v8 )
        return (unsigned int)-2147024882;
      v9 = 0;
      for ( rgIndices = plLbound; rgIndices <= (unsigned int)plUbound; v8[rgIndices++] = pvarg )
      {
        VariantInit(&pvarg);
        LBound = SafeArrayGetElement(llVal, &rgIndices, &pvarg);
        if ( LBound < 0 )
          goto LABEL_31;
        LBound = VariantChangeType(&pvarg, &pvarg, 0, 8u);
        if ( LBound < 0 )
          goto LABEL_31;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
        v9 += v10 + 1;
      }
      v11 = (unsigned int)(v9 + 1);
      v12 = (unsigned __int16 *)operator new[](saturated_mul(v11, 2u));
      if ( !v12 )
      {
        LBound = -2147024882;
        goto LABEL_31;
      }
      v13 = (unsigned int)plLbound;
      for ( i = v12; ; ++i )
      {
        rgIndices = v13;
        if ( (unsigned int)v13 > plUbound )
          break;
        wcscpy_s(i, v11 - (i - v12), v8[v13].bstrVal);
        while ( *i )
          ++i;
        v13 = (unsigned int)(rgIndices + 1);
      }
      *i = 0;
LABEL_30:
      *a3 = v12;
      if ( !v8 )
        return (unsigned int)LBound;
LABEL_31:
      FreeADsMem(v8);
      return (unsigned int)LBound;
    }
LABEL_28:
    v15 = (unsigned __int16 *)operator new[](4u);
    v12 = v15;
    if ( !v15 )
      return (unsigned int)-2147024882;
    LBound = 0;
    *(_DWORD *)v15 = 0x10000;
    v8 = 0;
    goto LABEL_30;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800089e8  mov     [rsp-38h+arg_10], rbx
0x1800089ed  mov     qword ptr [rsp-38h+rgIndices], rcx
0x1800089f2  push    rbp
0x1800089f3  push    rsi
0x1800089f4  push    rdi
0x1800089f5  push    r12
0x1800089f7  push    r13
0x1800089f9  push    r14
0x1800089fb  push    r15
0x1800089fd  mov     rbp, rsp
0x180008a00  sub     rsp, 40h
0x180008a04  xor     r13d, r13d
0x180008a07  xor     eax, eax
0x180008a09  mov     qword ptr [rbp+pvarg+10h], rax
0x180008a0d  xorps   xmm0, xmm0
0x180008a10  mov     eax, 2000h
0x180008a15  mov     [rbp+plLbound], r13d
0x180008a19  mov     r12, r8
0x180008a1c  mov     [rbp+plUbound], r13d
0x180008a20  mov     [rbp+rgIndices], r13d
0x180008a24  movups  xmmword ptr [rbp+pvarg], xmm0
0x180008a28  test    [rdx], ax
0x180008a2b  jnz     short loc_180008A37
0x180008a2d  mov     eax, 80004005h
0x180008a32  jmp     loc_180008C1B
0x180008a37  mov     eax, 4000h
0x180008a3c  lea     rsi, [rdx+8]
0x180008a40  test    [rdx], ax
0x180008a43  jz      short loc_180008A48
0x180008a45  mov     rsi, [rsi]
0x180008a48  mov     rsi, [rsi]
0x180008a4b  mov     r15d, 1
0x180008a51  test    rsi, rsi
0x180008a54  jz      loc_180008BE5
0x180008a5a  cmp     [rsi], r15w
0x180008a5e  jz      short loc_180008A6A
0x180008a60  mov     ebx, 80004005h
0x180008a65  jmp     loc_180008C19
0x180008a6a  cmp     [rsi+18h], r13d
0x180008a6e  jz      loc_180008BE5
0x180008a74  lea     r8, [rbp+plLbound]; plLbound
0x180008a78  mov     edx, r15d; nDim
0x180008a7b  mov     rcx, rsi; psa
0x180008a7e  call    cs:__imp_SafeArrayGetLBound
0x180008a84  mov     ebx, eax
0x180008a86  test    eax, eax
0x180008a88  js      loc_180008C19
0x180008a8e  lea     r8, [rbp+plUbound]; plUbound
0x180008a92  mov     edx, r15d; nDim
0x180008a95  mov     rcx, rsi; psa
0x180008a98  call    cs:__imp_SafeArrayGetUBound
0x180008a9e  mov     ebx, eax
0x180008aa0  test    eax, eax
0x180008aa2  js      loc_180008C19
0x180008aa8  mov     eax, [rbp+plUbound]
0x180008aab  sub     eax, [rbp+plLbound]
0x180008aae  add     eax, r15d
0x180008ab1  lea     ecx, [rax+rax*2]
0x180008ab4  shl     ecx, 3; cb
0x180008ab7  call    cs:__imp_AllocADsMem
0x180008abd  mov     rdi, rax
0x180008ac0  test    rax, rax
0x180008ac3  jnz     short loc_180008ACF
0x180008ac5  mov     ebx, 8007000Eh
0x180008aca  jmp     loc_180008C19
0x180008acf  mov     eax, [rbp+plLbound]
0x180008ad2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008ad6  mov     r14d, r13d
0x180008ad9  mov     [rbp+rgIndices], eax
0x180008adc  cmp     eax, [rbp+plUbound]
0x180008adf  ja      loc_180008B72
0x180008ae5  lea     rcx, [rbp+pvarg]; pvarg
0x180008ae9  call    cs:__imp_VariantInit
0x180008aef  lea     r8, [rbp+pvarg]; pv
0x180008af3  mov     rcx, rsi; psa
0x180008af6  lea     rdx, [rbp+rgIndices]; rgIndices
0x180008afa  call    cs:__imp_SafeArrayGetElement
0x180008b00  mov     ebx, eax
0x180008b02  test    eax, eax
0x180008b04  js      loc_180008C10
0x180008b0a  mov     r9d, 8; vt
0x180008b10  lea     rdx, [rbp+pvarg]; pvarSrc
0x180008b14  xor     r8d, r8d; wFlags
0x180008b17  lea     rcx, [rbp+pvarg]; pvargDest
0x180008b1b  call    cs:__imp_VariantChangeType
0x180008b21  mov     ebx, eax
0x180008b23  test    eax, eax
0x180008b25  js      loc_180008C10
0x180008b2b  mov     rcx, qword ptr [rbp+pvarg+8]
0x180008b2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b33  inc     rax
0x180008b36  cmp     [rcx+rax*2], r13w
0x180008b3b  jnz     short loc_180008B33
0x180008b3d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180008b41  inc     eax
0x180008b43  add     r14d, eax
0x180008b46  mov     eax, [rbp+rgIndices]
0x180008b49  lea     rcx, [rax+rax*2]
0x180008b4d  movups  xmmword ptr [rdi+rcx*8], xmm0
0x180008b51  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180008b56  movsd   qword ptr [rdi+rcx*8+10h], xmm1
0x180008b5c  mov     eax, [rbp+rgIndices]
0x180008b5f  add     eax, r15d
0x180008b62  mov     [rbp+rgIndices], eax
0x180008b65  cmp     eax, [rbp+plUbound]
0x180008b68  jbe     loc_180008AE5
0x180008b6e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008b72  lea     r15d, [r14+1]
0x180008b76  mov     eax, 2
0x180008b7b  mul     r15
0x180008b7e  cmovb   rax, rcx
0x180008b82  mov     rcx, rax; unsigned __int64
0x180008b85  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008b8a  mov     rsi, rax
0x180008b8d  test    rax, rax
0x180008b90  jnz     short loc_180008B99
0x180008b92  mov     ebx, 8007000Eh
0x180008b97  jmp     short loc_180008C10
0x180008b99  mov     eax, [rbp+plLbound]
0x180008b9c  mov     r14, rsi
0x180008b9f  jmp     short loc_180008BD7
0x180008ba1  lea     r8, [rax+rax*2]
0x180008ba5  mov     rdx, r15
0x180008ba8  mov     r8, [rdi+r8*8+8]; Source
0x180008bad  mov     rax, r14
0x180008bb0  sub     rax, rsi
0x180008bb3  mov     rcx, r14; Destination
0x180008bb6  sar     rax, 1
0x180008bb9  sub     rdx, rax; SizeInWords
0x180008bbc  call    cs:__imp_wcscpy_s
0x180008bc2  jmp     short loc_180008BC8
0x180008bc4  add     r14, 2
0x180008bc8  cmp     [r14], r13w
0x180008bcc  jnz     short loc_180008BC4
0x180008bce  mov     eax, [rbp+rgIndices]
0x180008bd1  add     r14, 2
0x180008bd5  inc     eax
0x180008bd7  mov     [rbp+rgIndices], eax
0x180008bda  cmp     eax, [rbp+plUbound]
0x180008bdd  jbe     short loc_180008BA1
0x180008bdf  mov     [r14], r13w
0x180008be3  jmp     short loc_180008C07
0x180008be5  mov     ecx, 4; unsigned __int64
0x180008bea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008bef  mov     rsi, rax
0x180008bf2  test    rax, rax
0x180008bf5  jz      loc_180008AC5
0x180008bfb  mov     ebx, r13d
0x180008bfe  mov     dword ptr [rax], 10000h
0x180008c04  mov     rdi, r13
0x180008c07  mov     [r12], rsi
0x180008c0b  test    rdi, rdi
0x180008c0e  jz      short loc_180008C19
0x180008c10  mov     rcx, rdi; pMem
0x180008c13  call    cs:__imp_FreeADsMem
0x180008c19  mov     eax, ebx
0x180008c1b  mov     rbx, [rsp+40h+arg_10]
0x180008c23  add     rsp, 40h
0x180008c27  pop     r15
0x180008c29  pop     r14
0x180008c2b  pop     r13
0x180008c2d  pop     r12
0x180008c2f  pop     rdi
0x180008c30  pop     rsi
0x180008c31  pop     rbp
0x180008c32  retn
```
