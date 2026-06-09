# UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)

- ea: `0x18004bc98`
- end: `0x18004be74`
- name: `?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *, __int64, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003290`

## callees

- `0x180010ff4`
- `0x180013d9c`
- `0x18004bc98`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004bd57`
- `OLEAUT32!__imp_SysAllocString` at `0x18004bd57`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd90`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd90`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004bdf6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004bdf6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bd7f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bd7f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004bd2a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004bd2a`

## pseudocode

```c
__int64 __fastcall UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
        OLECHAR *psz,
        const unsigned __int16 *a2,
        __int64 a3,
        struct tagVARIANT *a4)
{
  const OLECHAR *v5; // rbx
  OLECHAR *v6; // rsi
  HRESULT v7; // edi
  signed int v8; // r8d
  OLECHAR *v9; // rdx
  OLECHAR *v10; // rcx
  signed int v11; // eax
  SAFEARRAY *Vector; // r14
  LONG v13; // r13d
  BSTR v14; // rax
  OLECHAR *v15; // r15
  LONG rgIndices; // [rsp+78h] [rbp+10h] BYREF

  v5 = psz;
  if ( (unsigned int)a2 < 4 || (v6 = &psz[(unsigned int)a2 - 1], *(_DWORD *)(v6 - 1)) )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids);
    }
    return (unsigned int)-2147024883;
  }
  else
  {
    v7 = 0;
    v8 = 0;
    v9 = psz;
    if ( psz >= v6 )
      goto LABEL_32;
    do
    {
      for ( ; v9; ++v9 )
      {
        if ( !*v9 )
          break;
        if ( v9 >= v6 )
          break;
      }
      v10 = v9;
      v11 = v8 + 1;
      ++v9;
      if ( v10 >= v6 )
        v11 = v8;
      v8 = v11;
    }
    while ( v9 < v6 );
    if ( v11 <= 0 )
    {
LABEL_32:
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids);
      }
    }
    else
    {
      Vector = SafeArrayCreateVector(8u, 0, v11);
      if ( Vector )
      {
        v13 = 0;
        while ( v7 >= 0 )
        {
          v14 = SysAllocString(v5);
          v15 = v14;
          if ( v14 )
          {
            rgIndices = v13++;
            v7 = SafeArrayPutElement(Vector, &rgIndices, v14);
            if ( v7 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids, v15);
              }
              while ( v5 < v6 && *v5 )
                ++v5;
              ++v5;
            }
            else
            {
              SysFreeString(v15);
            }
          }
          else
          {
            v7 = -2147024882;
          }
          if ( v5 >= v6 )
          {
            if ( v7 >= 0 )
            {
              *(_WORD *)a3 = 8200;
              *(_QWORD *)(a3 + 8) = Vector;
              return (unsigned int)v7;
            }
            break;
          }
        }
        SafeArrayDestroy(Vector);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004bc98  push    rbx
0x18004bc9a  push    rbp
0x18004bc9b  push    rsi
0x18004bc9c  push    rdi
0x18004bc9d  push    r12
0x18004bc9f  push    r13
0x18004bca1  push    r14
0x18004bca3  push    r15
0x18004bca5  sub     rsp, 28h
0x18004bca9  mov     r12, r8
0x18004bcac  mov     rbx, rcx
0x18004bcaf  cmp     edx, 4
0x18004bcb2  jb      loc_18004BE2E
0x18004bcb8  mov     esi, edx
0x18004bcba  xor     r15d, r15d
0x18004bcbd  dec     rsi
0x18004bcc0  lea     rsi, [rcx+rsi*2]
0x18004bcc4  cmp     r15w, [rsi]
0x18004bcc8  jnz     loc_18004BE2E
0x18004bcce  cmp     r15w, [rsi-2]
0x18004bcd3  jnz     loc_18004BE2E
0x18004bcd9  mov     edi, r15d
0x18004bcdc  mov     r8d, r15d
0x18004bcdf  mov     rdx, rcx
0x18004bce2  cmp     rcx, rsi
0x18004bce5  jnb     loc_18004BDFE
0x18004bceb  test    rdx, rdx
0x18004bcee  jz      short loc_18004BD01
0x18004bcf0  cmp     [rdx], r15w
0x18004bcf4  jz      short loc_18004BD01
0x18004bcf6  cmp     rdx, rsi
0x18004bcf9  jnb     short loc_18004BD01
0x18004bcfb  add     rdx, 2
0x18004bcff  jnz     short loc_18004BCF0
0x18004bd01  mov     rcx, rdx
0x18004bd04  lea     eax, [r8+1]
0x18004bd08  add     rdx, 2
0x18004bd0c  cmp     rcx, rsi
0x18004bd0f  cmovnb  eax, r8d
0x18004bd13  mov     r8d, eax; cElements
0x18004bd16  cmp     rdx, rsi
0x18004bd19  jb      short loc_18004BCEB
0x18004bd1b  test    eax, eax
0x18004bd1d  jle     loc_18004BDFE
0x18004bd23  mov     ecx, 8; vt
0x18004bd28  xor     edx, edx; lLbound
0x18004bd2a  call    cs:__imp_SafeArrayCreateVector
0x18004bd30  mov     r14, rax
0x18004bd33  test    rax, rax
0x18004bd36  jnz     short loc_18004BD42
0x18004bd38  mov     edi, 8007000Eh
0x18004bd3d  jmp     loc_18004BE61
0x18004bd42  mov     r13d, r15d
0x18004bd45  lea     rbp, WPP_GLOBAL_Control
0x18004bd4c  test    edi, edi
0x18004bd4e  js      loc_18004BDF3
0x18004bd54  mov     rcx, rbx; psz
0x18004bd57  call    cs:__imp_SysAllocString
0x18004bd5d  mov     r15, rax
0x18004bd60  test    rax, rax
0x18004bd63  jnz     short loc_18004BD6C
0x18004bd65  mov     edi, 8007000Eh
0x18004bd6a  jmp     short loc_18004BDD8
0x18004bd6c  mov     [rsp+68h+rgIndices], r13d
0x18004bd71  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x18004bd76  mov     r8, r15; pv
0x18004bd79  mov     rcx, r14; psa
0x18004bd7c  inc     r13d
0x18004bd7f  call    cs:__imp_SafeArrayPutElement
0x18004bd85  mov     edi, eax
0x18004bd87  xor     eax, eax
0x18004bd89  test    edi, edi
0x18004bd8b  jns     short loc_18004BD98
0x18004bd8d  mov     rcx, r15; bstrString
0x18004bd90  call    cs:__imp_SysFreeString
0x18004bd96  jmp     short loc_18004BDD8
0x18004bd98  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd9f  cmp     rcx, rbp
0x18004bda2  jz      short loc_18004BDCF
0x18004bda4  test    byte ptr [rcx+1Ch], 1
0x18004bda8  jz      short loc_18004BDCF
0x18004bdaa  mov     rcx, [rcx+10h]
0x18004bdae  lea     r8, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids
0x18004bdb5  mov     edx, 0Bh
0x18004bdba  mov     r9, r15
0x18004bdbd  call    WPP_SF_S
0x18004bdc2  xor     eax, eax
0x18004bdc4  jmp     short loc_18004BDCF
0x18004bdc6  cmp     [rbx], ax
0x18004bdc9  jz      short loc_18004BDD4
0x18004bdcb  add     rbx, 2
0x18004bdcf  cmp     rbx, rsi
0x18004bdd2  jb      short loc_18004BDC6
0x18004bdd4  add     rbx, 2
0x18004bdd8  cmp     rbx, rsi
0x18004bddb  jb      loc_18004BD4C
0x18004bde1  test    edi, edi
0x18004bde3  js      short loc_18004BDF3
0x18004bde5  mov     word ptr [r12], 2008h
0x18004bdec  mov     [r12+8], r14
0x18004bdf1  jmp     short loc_18004BE61
0x18004bdf3  mov     rcx, r14; psa
0x18004bdf6  call    cs:__imp_SafeArrayDestroy
0x18004bdfc  jmp     short loc_18004BE61
0x18004bdfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be05  lea     rbp, WPP_GLOBAL_Control
0x18004be0c  cmp     rcx, rbp
0x18004be0f  jz      short loc_18004BE61
0x18004be11  test    byte ptr [rcx+1Ch], 2
0x18004be15  jz      short loc_18004BE61
0x18004be17  mov     rcx, [rcx+10h]
0x18004be1b  lea     r8, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids
0x18004be22  mov     edx, 0Ch
0x18004be27  call    WPP_SF_
0x18004be2c  jmp     short loc_18004BE61
0x18004be2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be35  lea     rbp, WPP_GLOBAL_Control
0x18004be3c  cmp     rcx, rbp
0x18004be3f  jz      short loc_18004BE5C
0x18004be41  test    byte ptr [rcx+1Ch], 1
0x18004be45  jz      short loc_18004BE5C
0x18004be47  mov     rcx, [rcx+10h]
0x18004be4b  lea     r8, WPP_4d1331365da33410a9c6877b32abe2b9_Traceguids
0x18004be52  mov     edx, 0Ah
0x18004be57  call    WPP_SF_
0x18004be5c  mov     edi, 8007000Dh
0x18004be61  mov     eax, edi
0x18004be63  add     rsp, 28h
0x18004be67  pop     r15
0x18004be69  pop     r14
0x18004be6b  pop     r13
0x18004be6d  pop     r12
0x18004be6f  pop     rdi
0x18004be70  pop     rsi
0x18004be71  pop     rbp
0x18004be72  pop     rbx
0x18004be73  retn
```
