# CUnnamedArguments::Create(long,ushort const * *,CUnnamedArguments * *)

- ea: `0x140013bf8`
- end: `0x140013d8b`
- name: `?Create@CUnnamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `403`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CUnnamedArguments **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140007580`

## callees

- `0x140009c70`
- `0x140013bf8`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013d17`
- `OLEAUT32!__imp_SysAllocString` at `0x140013d17`
- `OLEAUT32!__imp_VariantClear` at `0x140013d3e`
- `OLEAUT32!__imp_VariantClear` at `0x140013d3e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013cdc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013cdc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013d32`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013d32`

## pseudocode

```c
__int64 __fastcall CUnnamedArguments::Create(int a1, const unsigned __int16 **a2, SAFEARRAY ***a3)
{
  HRESULT v3; // ebx
  SAFEARRAY **v7; // rax
  SAFEARRAY **v8; // rdi
  signed int v9; // esi
  int i; // edx
  int v11; // eax
  SAFEARRAY *v12; // rax
  LONG v13; // edx
  int j; // r14d
  const OLECHAR *v15; // rcx
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-28h] BYREF
  VARIANTARG pv; // [rsp+28h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  rgsabound = 0;
  rgIndices = 0;
  memset(&pv, 0, sizeof(pv));
  v7 = (SAFEARRAY **)operator new(0x50u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = (SAFEARRAY *)&CUnknown::`vftable';
    v7[5] = (SAFEARRAY *)&CUnknown::InnerUnknown::`vftable';
    *((_DWORD *)v7 + 12) = 1;
    v7[3] = (SAFEARRAY *)(v7 + 5);
    v7[4] = (SAFEARRAY *)v7;
    _InterlockedAdd(&Global::g_cObjects, 1u);
    *((_BYTE *)v7 + 64) = 0;
    v7[7] = (SAFEARRAY *)&TaUser_DescCUnnamedArguments;
    *v7 = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IWSHUnnamedArguments'};
    v7[1] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IProvideClassInfo'};
    v7[2] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `CDispatch'};
    v9 = 0;
    v7[9] = 0;
    for ( i = 0; i < a1; v9 = v11 )
    {
      v11 = v9 + 1;
      if ( *a2[i] == 47 )
        v11 = v9;
      ++i;
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v9;
    v12 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v8[9] = v12;
    if ( v12 )
    {
      v13 = 0;
      rgIndices = 0;
      for ( j = 0; j < a1 && v13 < v9; ++j )
      {
        v15 = a2[j];
        if ( *v15 != 47 )
        {
          pv.vt = 8;
          pv.llVal = (LONGLONG)SysAllocString(v15);
          if ( !pv.llVal )
            goto LABEL_15;
          v3 = SafeArrayPutElement(v8[9], &rgIndices, &pv);
          VariantClear(&pv);
          if ( v3 < 0 )
            goto LABEL_16;
          v13 = ++rgIndices;
          v3 = 0;
        }
      }
      *a3 = v8;
    }
    else
    {
LABEL_15:
      v3 = -2147024882;
LABEL_16:
      ((void (__fastcall *)(SAFEARRAY **))(*v8)->pvData)(v8);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140013bf8  push    rbp
0x140013bfa  push    rbx
0x140013bfb  push    rsi
0x140013bfc  push    rdi
0x140013bfd  push    r12
0x140013bff  push    r13
0x140013c01  push    r14
0x140013c03  push    r15
0x140013c05  mov     rbp, rsp
0x140013c08  sub     rsp, 48h
0x140013c0c  xor     ebx, ebx
0x140013c0e  mov     r15d, ecx
0x140013c11  xorps   xmm0, xmm0
0x140013c14  mov     qword ptr [rbp+rgsabound.cElements], rbx
0x140013c18  xor     eax, eax
0x140013c1a  mov     [rbp+rgIndices], ebx
0x140013c1d  mov     r12, r8
0x140013c20  mov     [rbp+var_10], rax
0x140013c24  lea     ecx, [rbx+50h]; Size
0x140013c27  mov     r13, rdx
0x140013c2a  movups  [rbp+pv], xmm0
0x140013c2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013c33  mov     rdi, rax
0x140013c36  test    rax, rax
0x140013c39  jz      loc_140013D73
0x140013c3f  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x140013c46  mov     [rdi+10h], rax
0x140013c4a  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x140013c51  lea     rax, [rdi+28h]
0x140013c55  mov     [rax], rcx
0x140013c58  lea     r9d, [rbx+1]
0x140013c5c  mov     [rax+8], r9d
0x140013c60  mov     [rdi+18h], rax
0x140013c64  mov     [rdi+20h], rdi
0x140013c68  lock add cs:?g_cObjects@Global@@2JA, r9d; long Global::g_cObjects
0x140013c70  mov     [rdi+40h], bl
0x140013c73  lea     rax, ?TaUser_DescCUnnamedArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCUnnamedArguments
0x140013c7a  mov     [rdi+38h], rax
0x140013c7e  lea     rax, ??_7CUnnamedArguments@@6BIWSHUnnamedArguments@@@; const CUnnamedArguments::`vftable'{for `IWSHUnnamedArguments'}
0x140013c85  mov     [rdi], rax
0x140013c88  lea     rax, ??_7CUnnamedArguments@@6BIProvideClassInfo@@@; const CUnnamedArguments::`vftable'{for `IProvideClassInfo'}
0x140013c8f  mov     [rdi+8], rax
0x140013c93  lea     rax, ??_7CUnnamedArguments@@6BCDispatch@@@; const CUnnamedArguments::`vftable'{for `CDispatch'}
0x140013c9a  mov     [rdi+10h], rax
0x140013c9e  mov     esi, ebx
0x140013ca0  mov     [rdi+48h], rbx
0x140013ca4  mov     edx, ebx
0x140013ca6  lea     r8d, [rbx+2Fh]
0x140013caa  test    r15d, r15d
0x140013cad  jle     short loc_140013CCA
0x140013caf  mov     eax, edx
0x140013cb1  mov     rcx, [r13+rax*8+0]
0x140013cb6  lea     eax, [rsi+1]
0x140013cb9  cmp     r8w, [rcx]
0x140013cbd  cmovz   eax, esi
0x140013cc0  add     edx, r9d
0x140013cc3  mov     esi, eax
0x140013cc5  cmp     edx, r15d
0x140013cc8  jl      short loc_140013CAF
0x140013cca  mov     ecx, 0Ch; vt
0x140013ccf  mov     [rbp+rgsabound.lLbound], ebx
0x140013cd2  lea     r8, [rbp+rgsabound]; rgsabound
0x140013cd6  mov     [rbp+rgsabound.cElements], esi
0x140013cd9  mov     edx, r9d; cDims
0x140013cdc  call    cs:__imp_SafeArrayCreate
0x140013ce2  mov     [rdi+48h], rax
0x140013ce6  test    rax, rax
0x140013ce9  jz      short loc_140013D57
0x140013ceb  mov     edx, ebx
0x140013ced  mov     [rbp+rgIndices], ebx
0x140013cf0  mov     r14d, ebx
0x140013cf3  cmp     r14d, r15d
0x140013cf6  jge     short loc_140013D6D
0x140013cf8  cmp     edx, esi
0x140013cfa  jge     short loc_140013D6D
0x140013cfc  movsxd  rax, r14d
0x140013cff  mov     rcx, [r13+rax*8+0]; psz
0x140013d04  mov     eax, 2Fh ; '/'
0x140013d09  cmp     ax, [rcx]
0x140013d0c  jz      short loc_140013D52
0x140013d0e  mov     eax, 8
0x140013d13  mov     word ptr [rbp+pv], ax
0x140013d17  call    cs:__imp_SysAllocString
0x140013d1d  mov     qword ptr [rbp+pv+8], rax
0x140013d21  test    rax, rax
0x140013d24  jz      short loc_140013D57
0x140013d26  mov     rcx, [rdi+48h]; psa
0x140013d2a  lea     r8, [rbp+pv]; pv
0x140013d2e  lea     rdx, [rbp+rgIndices]; rgIndices
0x140013d32  call    cs:__imp_SafeArrayPutElement
0x140013d38  lea     rcx, [rbp+pv]; pvarg
0x140013d3c  mov     ebx, eax
0x140013d3e  call    cs:__imp_VariantClear
0x140013d44  test    ebx, ebx
0x140013d46  js      short loc_140013D5C
0x140013d48  mov     edx, [rbp+rgIndices]
0x140013d4b  inc     edx
0x140013d4d  mov     [rbp+rgIndices], edx
0x140013d50  xor     ebx, ebx
0x140013d52  inc     r14d
0x140013d55  jmp     short loc_140013CF3
0x140013d57  mov     ebx, 8007000Eh
0x140013d5c  mov     rax, [rdi]
0x140013d5f  mov     rcx, rdi
0x140013d62  mov     rax, [rax+10h]
0x140013d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d6b  jmp     short loc_140013D78
0x140013d6d  mov     [r12], rdi
0x140013d71  jmp     short loc_140013D78
0x140013d73  mov     ebx, 8007000Eh
0x140013d78  mov     eax, ebx
0x140013d7a  add     rsp, 48h
0x140013d7e  pop     r15
0x140013d80  pop     r14
0x140013d82  pop     r13
0x140013d84  pop     r12
0x140013d86  pop     rdi
0x140013d87  pop     rsi
0x140013d88  pop     rbx
0x140013d89  pop     rbp
0x140013d8a  retn
```
