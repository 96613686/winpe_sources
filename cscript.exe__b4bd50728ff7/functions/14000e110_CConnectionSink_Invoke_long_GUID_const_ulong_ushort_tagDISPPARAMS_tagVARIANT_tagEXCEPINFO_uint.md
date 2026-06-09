# CConnectionSink::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x14000e110`
- end: `0x14000e4b7`
- name: `?Invoke@CConnectionSink@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `935`
- prototype: `__int64 __fastcall(CConnectionSink *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x140009c70`
- `0x140009cb0`
- `0x14000e110`
- `0x14000f180`
- `0x140017010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x14000e231`
- `msvcrt!wcscat_s` at `0x14000e231`
- `msvcrt!wcscpy_s` at `0x14000e220`
- `msvcrt!wcscpy_s` at `0x14000e220`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000e1f6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000e1f6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e471`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e480`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e471`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e480`
- `OLEAUT32!__imp_VariantInit` at `0x14000e325`
- `OLEAUT32!__imp_VariantInit` at `0x14000e325`
- `OLEAUT32!__imp_VariantClear` at `0x14000e443`
- `OLEAUT32!__imp_VariantClear` at `0x14000e443`
- `OLEAUT32!__imp_VariantCopy` at `0x14000e358`
- `OLEAUT32!__imp_VariantCopy` at `0x14000e358`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000e3d3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000e3d3`

## pseudocode

```c
__int64 __fastcall CConnectionSink::Invoke(
        CConnectionSink *this,
        __int64 a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  bool v9; // zf
  __int64 v10; // rax
  struct IDispatch *v13; // rsi
  HRESULT v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // ebx
  int ScriptDispatch; // eax
  int v20; // eax
  struct tagDISPPARAMS *v21; // r14
  UINT cNamedArgs; // edx
  unsigned __int64 v23; // rcx
  _WORD *v24; // rax
  unsigned int v25; // eax
  unsigned int i; // ebx
  unsigned int j; // edi
  _DWORD *v28; // rax
  unsigned int k; // r8d
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned int m; // edi
  int v34; // [rsp+20h] [rbp-71h]
  unsigned int v35; // [rsp+50h] [rbp-41h] BYREF
  int v36; // [rsp+54h] [rbp-3Dh] BYREF
  wchar_t *Destination; // [rsp+58h] [rbp-39h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp-31h] BYREF
  struct IDispatch *v39; // [rsp+68h] [rbp-29h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v41; // [rsp+80h] [rbp-11h]

  v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  v9 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1;
  v36 = 0;
  v35 = 0;
  *(_OWORD *)Block = 0;
  v41 = 0;
  v13 = 0;
  Source = 0;
  Destination = 0;
  v39 = 0;
  if ( v9 )
    v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v10 )
    return (unsigned int)-2147024809;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **, __int64, int *))(**((_QWORD **)this + 3) + 56LL))(
          *((_QWORD *)this + 3),
          a2,
          &Source,
          1,
          &v36);
  if ( v14 >= 0 )
  {
    if ( !v36 )
    {
      v14 = -2147418113;
      goto LABEL_37;
    }
    v15 = *((_QWORD *)this + 2);
    if ( v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(v15 + 2 * v16) );
    }
    else
    {
      LODWORD(v16) = 0;
    }
    if ( Source )
    {
      v17 = -1;
      do
        ++v17;
      while ( Source[v17] );
    }
    else
    {
      LODWORD(v17) = 0;
    }
    v18 = v17 + v16;
    Destination = SysAllocStringLen(0, (int)v17 + (int)v16);
    if ( !Destination )
    {
LABEL_18:
      v14 = -2147024882;
      goto LABEL_37;
    }
    wcscpy_s(Destination, v18 + 1, *((const wchar_t **)this + 2));
    wcscat_s(Destination, v18 + 1, Source);
    ScriptDispatch = CHost::GetScriptDispatch(g_pHost, &v39);
    v13 = v39;
    v14 = ScriptDispatch;
    if ( ScriptDispatch < 0 )
      goto LABEL_37;
    v35 = 0;
    v20 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, wchar_t **, __int64, unsigned int, unsigned int *))v39->lpVtbl->GetIDsOfNames)(
            v39,
            &GUID_NULL,
            &Destination,
            1,
            a4,
            &v35);
    if ( v20 < 0 )
    {
      v14 = 0;
      if ( v20 != -2147352570 )
        v14 = v20;
      goto LABEL_37;
    }
    v21 = a6;
    cNamedArgs = a6->cNamedArgs;
    if ( !cNamedArgs || *a6->rgdispidNamedArgs != -613 )
    {
      v23 = a6->cArgs + 1;
      HIDWORD(v41) = cNamedArgs + 1;
      LODWORD(v41) = v23;
      v24 = operator new(saturated_mul(v23, 0x18u));
      Block[0] = v24;
      if ( !v24 )
        goto LABEL_18;
      *v24 = 9;
      *((_QWORD *)Block[0] + 1) = *((_QWORD *)this + 1);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
      v25 = v41;
      for ( i = 1; i < (unsigned int)v41; ++i )
      {
        VariantInit((VARIANTARG *)Block[0] + i);
        v25 = v41;
      }
      for ( j = 1; j < v25; ++j )
      {
        v14 = VariantCopy((VARIANTARG *)Block[0] + j, &a6->rgvarg[j - 1]);
        if ( v14 < 0 )
          goto LABEL_37;
        v25 = v41;
      }
      v28 = operator new(saturated_mul(HIDWORD(v41), 4u));
      Block[1] = v28;
      if ( !v28 )
        goto LABEL_18;
      *v28 = -613;
      v21 = (struct tagDISPPARAMS *)Block;
      for ( k = 1; k < HIDWORD(v41); *((_DWORD *)Block[1] + v31) = a6->rgdispidNamedArgs[v30] )
      {
        v30 = k - 1;
        v31 = k++;
      }
    }
    SetErrorInfo(0, 0);
    LOWORD(v34) = a5;
    v14 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, _QWORD, int, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))v13->lpVtbl->Invoke)(
            v13,
            v35,
            &GUID_NULL,
            a4,
            v34,
            v21,
            a7,
            a8,
            a9);
  }
LABEL_37:
  if ( Block[0] )
  {
    for ( m = 0; m < (unsigned int)v41; ++m )
      VariantClear((VARIANTARG *)Block[0] + m);
    operator delete(Block[0]);
  }
  if ( Block[1] )
    operator delete(Block[1]);
  if ( Source )
    SysFreeString(Source);
  if ( Destination )
    SysFreeString(Destination);
  if ( v13 )
    ((void (__fastcall *)(struct IDispatch *))v13->lpVtbl->Release)(v13);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000e110  push    rbp
0x14000e112  push    rbx
0x14000e113  push    rsi
0x14000e114  push    rdi
0x14000e115  push    r12
0x14000e117  push    r13
0x14000e119  push    r14
0x14000e11b  push    r15
0x14000e11d  lea     rbp, [rsp-7]
0x14000e122  sub     rsp, 98h
0x14000e129  mov     rax, [r8]
0x14000e12c  xor     r12d, r12d
0x14000e12f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14000e136  xorps   xmm0, xmm0
0x14000e139  mov     r15d, r9d
0x14000e13c  mov     [rbp+3Fh+var_7C], r12d
0x14000e140  mov     rdi, rcx
0x14000e143  mov     [rbp+3Fh+var_80], r12d
0x14000e147  movdqu  xmmword ptr [rbp+3Fh+Block], xmm0
0x14000e14c  mov     [rbp+3Fh+var_50], r12
0x14000e150  mov     esi, r12d
0x14000e153  mov     [rbp+3Fh+Source], r12
0x14000e157  mov     [rbp+3Fh+Destination], r12
0x14000e15b  mov     [rbp+3Fh+var_68], r12
0x14000e15f  jnz     short loc_14000E16C
0x14000e161  mov     rax, [r8+8]
0x14000e165  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14000e16c  test    rax, rax
0x14000e16f  jnz     loc_14000E49C
0x14000e175  mov     rcx, [rcx+18h]
0x14000e179  lea     r8, [rbp+3Fh+var_7C]
0x14000e17d  mov     [rsp+0D0h+var_B0], r8
0x14000e182  mov     r13d, 1
0x14000e188  mov     r9d, r13d
0x14000e18b  lea     r8, [rbp+3Fh+Source]
0x14000e18f  mov     rax, [rcx]
0x14000e192  mov     rax, [rax+38h]
0x14000e196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e19b  mov     ebx, eax
0x14000e19d  test    eax, eax
0x14000e19f  js      loc_14000E426
0x14000e1a5  cmp     [rbp+3Fh+var_7C], r12d
0x14000e1a9  jnz     short loc_14000E1B5
0x14000e1ab  mov     ebx, 8000FFFFh
0x14000e1b0  jmp     loc_14000E426
0x14000e1b5  mov     rax, [rdi+10h]
0x14000e1b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000e1bd  test    rax, rax
0x14000e1c0  jz      short loc_14000E1D1
0x14000e1c2  mov     rcx, r8
0x14000e1c5  inc     rcx
0x14000e1c8  cmp     [rax+rcx*2], r12w
0x14000e1cd  jnz     short loc_14000E1C5
0x14000e1cf  jmp     short loc_14000E1D4
0x14000e1d1  mov     rcx, r12
0x14000e1d4  mov     rdx, [rbp+3Fh+Source]
0x14000e1d8  test    rdx, rdx
0x14000e1db  jz      short loc_14000E1EC
0x14000e1dd  mov     rax, r8
0x14000e1e0  inc     rax
0x14000e1e3  cmp     [rdx+rax*2], r12w
0x14000e1e8  jnz     short loc_14000E1E0
0x14000e1ea  jmp     short loc_14000E1EF
0x14000e1ec  mov     rax, r12
0x14000e1ef  lea     ebx, [rax+rcx]
0x14000e1f2  xor     ecx, ecx; strIn
0x14000e1f4  mov     edx, ebx; ui
0x14000e1f6  call    cs:__imp_SysAllocStringLen
0x14000e1fc  mov     [rbp+3Fh+Destination], rax
0x14000e200  test    rax, rax
0x14000e203  jnz     short loc_14000E20F
0x14000e205  mov     ebx, 8007000Eh
0x14000e20a  jmp     loc_14000E426
0x14000e20f  mov     r8, [rdi+10h]; Source
0x14000e213  lea     eax, [rbx+1]
0x14000e216  mov     rcx, [rbp+3Fh+Destination]; Destination
0x14000e21a  movsxd  rbx, eax
0x14000e21d  mov     rdx, rbx; SizeInWords
0x14000e220  call    cs:__imp_wcscpy_s
0x14000e226  mov     r8, [rbp+3Fh+Source]; Source
0x14000e22a  mov     rdx, rbx; SizeInWords
0x14000e22d  mov     rcx, [rbp+3Fh+Destination]; Destination
0x14000e231  call    cs:__imp_wcscat_s
0x14000e237  mov     rcx, cs:?g_pHost@@3PEAVCHost@@EA; this
0x14000e23e  lea     rdx, [rbp+3Fh+var_68]; struct IDispatch **
0x14000e242  call    ?GetScriptDispatch@CHost@@QEAAJPEAPEAUIDispatch@@@Z; CHost::GetScriptDispatch(IDispatch * *)
0x14000e247  mov     rsi, [rbp+3Fh+var_68]
0x14000e24b  mov     ebx, eax
0x14000e24d  test    eax, eax
0x14000e24f  js      loc_14000E426
0x14000e255  mov     [rbp+3Fh+var_80], r12d
0x14000e259  lea     rcx, [rbp+3Fh+var_80]
0x14000e25d  mov     rax, [rsi]
0x14000e260  lea     r8, [rbp+3Fh+Destination]
0x14000e264  mov     [rsp+0D0h+var_A8], rcx
0x14000e269  lea     rdx, GUID_NULL
0x14000e270  mov     r9d, r13d
0x14000e273  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x14000e278  mov     rcx, rsi
0x14000e27b  mov     rax, [rax+28h]
0x14000e27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e284  test    eax, eax
0x14000e286  jns     short loc_14000E298
0x14000e288  cmp     eax, 80020006h
0x14000e28d  mov     ebx, r12d
0x14000e290  cmovnz  ebx, eax
0x14000e293  jmp     loc_14000E426
0x14000e298  mov     r14, [rbp+3Fh+arg_28]
0x14000e29c  mov     edx, [r14+14h]
0x14000e2a0  test    edx, edx
0x14000e2a2  jz      short loc_14000E2B4
0x14000e2a4  mov     rax, [r14+8]
0x14000e2a8  cmp     dword ptr [rax], 0FFFFFD9Bh
0x14000e2ae  jz      loc_14000E3CF
0x14000e2b4  mov     ecx, [r14+10h]
0x14000e2b8  lea     eax, [rdx+1]
0x14000e2bb  inc     ecx
0x14000e2bd  mov     dword ptr [rbp+3Fh+var_50+4], eax
0x14000e2c0  mov     dword ptr [rbp+3Fh+var_50], ecx
0x14000e2c3  mov     eax, 18h
0x14000e2c8  mul     rcx
0x14000e2cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e2d2  cmovb   rax, rcx
0x14000e2d6  mov     rcx, rax; Size
0x14000e2d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e2de  mov     [rbp+3Fh+Block], rax
0x14000e2e2  test    rax, rax
0x14000e2e5  jz      loc_14000E205
0x14000e2eb  mov     word ptr [rax], 9
0x14000e2f0  mov     rax, [rbp+3Fh+Block]
0x14000e2f4  mov     rcx, [rdi+8]
0x14000e2f8  mov     [rax+8], rcx
0x14000e2fc  mov     rcx, [rdi+8]
0x14000e300  mov     rax, [rcx]
0x14000e303  mov     rax, [rax+8]
0x14000e307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e30c  mov     eax, dword ptr [rbp+3Fh+var_50]
0x14000e30f  mov     ebx, r13d
0x14000e312  cmp     eax, r13d
0x14000e315  jbe     short loc_14000E335
0x14000e317  mov     eax, ebx
0x14000e319  lea     rcx, [rax+rax*2]
0x14000e31d  mov     rax, [rbp+3Fh+Block]
0x14000e321  lea     rcx, [rax+rcx*8]; pvarg
0x14000e325  call    cs:__imp_VariantInit
0x14000e32b  mov     eax, dword ptr [rbp+3Fh+var_50]
0x14000e32e  add     ebx, r13d
0x14000e331  cmp     ebx, eax
0x14000e333  jb      short loc_14000E317
0x14000e335  mov     edi, r13d
0x14000e338  cmp     edi, eax
0x14000e33a  jnb     short loc_14000E370
0x14000e33c  lea     eax, [rdi-1]
0x14000e33f  lea     rdx, [rax+rax*2]
0x14000e343  mov     rax, [r14]
0x14000e346  lea     rdx, [rax+rdx*8]; pvargSrc
0x14000e34a  mov     eax, edi
0x14000e34c  lea     rcx, [rax+rax*2]
0x14000e350  mov     rax, [rbp+3Fh+Block]
0x14000e354  lea     rcx, [rax+rcx*8]; pvargDest
0x14000e358  call    cs:__imp_VariantCopy
0x14000e35e  mov     ebx, eax
0x14000e360  test    eax, eax
0x14000e362  js      loc_14000E426
0x14000e368  mov     eax, dword ptr [rbp+3Fh+var_50]
0x14000e36b  add     edi, r13d
0x14000e36e  jmp     short loc_14000E338
0x14000e370  mov     ecx, dword ptr [rbp+3Fh+var_50+4]
0x14000e373  mov     eax, 4
0x14000e378  mul     rcx
0x14000e37b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e382  cmovb   rax, rcx
0x14000e386  mov     rcx, rax; Size
0x14000e389  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e38e  mov     [rbp+3Fh+Block+8], rax
0x14000e392  test    rax, rax
0x14000e395  jz      loc_14000E205
0x14000e39b  mov     dword ptr [rax], 0FFFFFD9Bh
0x14000e3a1  mov     r9, r14
0x14000e3a4  lea     r14, [rbp+3Fh+Block]
0x14000e3a8  mov     r8d, r13d
0x14000e3ab  cmp     dword ptr [rbp+3Fh+var_50+4], r13d
0x14000e3af  jbe     short loc_14000E3CF
0x14000e3b1  mov     rax, [r9+8]
0x14000e3b5  lea     ecx, [r8-1]
0x14000e3b9  mov     edx, r8d
0x14000e3bc  add     r8d, r13d
0x14000e3bf  mov     ecx, [rax+rcx*4]
0x14000e3c2  mov     rax, [rbp+3Fh+Block+8]
0x14000e3c6  mov     [rax+rdx*4], ecx
0x14000e3c9  cmp     r8d, dword ptr [rbp+3Fh+var_50+4]
0x14000e3cd  jb      short loc_14000E3B1
0x14000e3cf  xor     edx, edx; perrinfo
0x14000e3d1  xor     ecx, ecx; dwReserved
0x14000e3d3  call    cs:__imp_SetErrorInfo
0x14000e3d9  mov     rcx, [rbp+3Fh+arg_40]
0x14000e3e0  lea     r8, GUID_NULL
0x14000e3e7  mov     rax, [rsi]
0x14000e3ea  mov     r9d, r15d
0x14000e3ed  mov     edx, [rbp+3Fh+var_80]
0x14000e3f0  mov     [rsp+0D0h+var_90], rcx
0x14000e3f5  mov     rcx, [rbp+3Fh+arg_38]
0x14000e3fc  mov     rax, [rax+30h]
0x14000e400  mov     [rsp+0D0h+var_98], rcx
0x14000e405  mov     rcx, [rbp+3Fh+arg_30]
0x14000e409  mov     [rsp+0D0h+var_A0], rcx
0x14000e40e  movzx   ecx, [rbp+3Fh+arg_20]
0x14000e412  mov     [rsp+0D0h+var_A8], r14
0x14000e417  mov     word ptr [rsp+0D0h+var_B0], cx
0x14000e41c  mov     rcx, rsi
0x14000e41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e424  mov     ebx, eax
0x14000e426  cmp     [rbp+3Fh+Block], r12
0x14000e42a  jz      short loc_14000E45A
0x14000e42c  mov     edi, r12d
0x14000e42f  cmp     dword ptr [rbp+3Fh+var_50], r12d
0x14000e433  jbe     short loc_14000E451
0x14000e435  mov     eax, edi
0x14000e437  lea     rcx, [rax+rax*2]
0x14000e43b  mov     rax, [rbp+3Fh+Block]
0x14000e43f  lea     rcx, [rax+rcx*8]; pvarg
0x14000e443  call    cs:__imp_VariantClear
0x14000e449  add     edi, r13d
0x14000e44c  cmp     edi, dword ptr [rbp+3Fh+var_50]
0x14000e44f  jb      short loc_14000E435
0x14000e451  mov     rcx, [rbp+3Fh+Block]; Block
0x14000e455  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e45a  mov     rcx, [rbp+3Fh+Block+8]; Block
0x14000e45e  test    rcx, rcx
0x14000e461  jz      short loc_14000E468
0x14000e463  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e468  mov     rcx, [rbp+3Fh+Source]; bstrString
0x14000e46c  test    rcx, rcx
0x14000e46f  jz      short loc_14000E477
0x14000e471  call    cs:__imp_SysFreeString
0x14000e477  mov     rcx, [rbp+3Fh+Destination]; bstrString
0x14000e47b  test    rcx, rcx
0x14000e47e  jz      short loc_14000E486
0x14000e480  call    cs:__imp_SysFreeString
0x14000e486  test    rsi, rsi
0x14000e489  jz      short loc_14000E4A1
0x14000e48b  mov     rax, [rsi]
0x14000e48e  mov     rcx, rsi
0x14000e491  mov     rax, [rax+10h]
0x14000e495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e49a  jmp     short loc_14000E4A1
0x14000e49c  mov     ebx, 80070057h
0x14000e4a1  mov     eax, ebx
0x14000e4a3  add     rsp, 98h
0x14000e4aa  pop     r15
0x14000e4ac  pop     r14
0x14000e4ae  pop     r13
0x14000e4b0  pop     r12
0x14000e4b2  pop     rdi
0x14000e4b3  pop     rsi
0x14000e4b4  pop     rbx
0x14000e4b5  pop     rbp
0x14000e4b6  retn
```
