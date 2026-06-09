# VerifyDefaultRevocation

- ea: `0x180028d9c`
- end: `0x18002948d`
- name: `VerifyDefaultRevocation`
- size: `1777`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, __int64, int, FILETIME *lpFileTime1, __int64, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f70`
- `0x18001347c`

## callees

- `0x180015ce8`
- `0x1800258c4`
- `0x180027ba8`
- `0x1800286e0`
- `0x180028d60`
- `0x180028d9c`
- `0x180029494`
- `0x180029500`
- `0x180029ce8`
- `0x180029db8`
- `0x180029f2c`
- `0x18002a7d8`
- `0x18002a850`
- `0x180061270`
- `0x1800bec20`
- `0x1800bf63c`
- `0x180115040`
- `0x1801150d0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002931f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002931f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028e31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002935e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029426`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028e31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002935e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029426`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002946b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002946b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002910b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002910b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800291e4`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800291e4`

## pseudocode

```c
__int64 __fastcall VerifyDefaultRevocation(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        FILETIME *lpFileTime1,
        __int64 a7,
        unsigned int *a8,
        __int64 a9)
{
  int v9; // r15d
  void *v10; // rdi
  unsigned int v12; // r13d
  struct _FUNC_SET *v13; // rbx
  unsigned int v14; // r14d
  const WCHAR *v15; // rdx
  int v16; // eax
  void *v17; // r14
  struct _FUNC_SET *v18; // rbx
  unsigned int v19; // r12d
  unsigned int v20; // ecx
  __int64 i; // rax
  unsigned int *v22; // r15
  unsigned __int64 v23; // rbx
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  struct _FUNC_SET *v28; // rbx
  int *v29; // r14
  unsigned int v30; // edi
  unsigned int v31; // ecx
  unsigned int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // r14d
  int v36; // ecx
  bool v37; // cf
  __int64 j; // rax
  __int64 v39; // rax
  struct _FUNC_SET *v40; // r13
  unsigned int v41; // r14d
  __int64 k; // rbx
  unsigned int m; // edi
  struct _DLL_ELEMENT *Dll; // rax
  HMODULE *v45; // rdi
  unsigned int *v46; // rax
  int v48; // eax
  unsigned int v49; // ebx
  __int64 v50; // rcx
  DWORD LastError; // r13d
  __int64 Tls; // r12
  unsigned __int16 *OIDFuncDll; // rbx
  int v54; // ecx
  int v55; // eax
  void *v56; // r14
  __int64 v57; // [rsp+0h] [rbp-40h] BYREF
  unsigned int v58; // [rsp+40h] [rbp+0h] BYREF
  int v59; // [rsp+44h] [rbp+4h]
  unsigned int v60; // [rsp+48h] [rbp+8h] BYREF
  unsigned int v61; // [rsp+4Ch] [rbp+Ch]
  unsigned int v62; // [rsp+50h] [rbp+10h]
  unsigned int v63; // [rsp+54h] [rbp+14h]
  unsigned int v64; // [rsp+58h] [rbp+18h]
  void *ProcAddress; // [rsp+60h] [rbp+20h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+68h] [rbp+28h] BYREF
  const WCHAR *v67; // [rsp+70h] [rbp+30h]
  __int64 v68; // [rsp+78h] [rbp+38h]
  __int64 v69; // [rsp+80h] [rbp+40h]

  v9 = -2146885615;
  v60 = 0;
  v59 = -2146885615;
  v10 = 0;
  v61 = 0;
  v62 = 0;
  v68 = a4;
  v63 = a3;
  v64 = a2;
  v58 = a1;
  v12 = (unsigned __int16)a1;
  while ( 1 )
  {
    v13 = qword_180158390;
    if ( !*((_DWORD *)qword_180158390 + 12) )
      LoadRegFunc(qword_180158390);
    if ( v12 )
      v14 = v12;
    else
      v14 = HIWORD(a1);
    if ( !v10 || *(_DWORD *)v10 != 2 )
    {
      v10 = (void *)*((_QWORD *)v13 + 4);
      goto LABEL_8;
    }
    do
    {
      v10 = (void *)*((_QWORD *)v10 + 1);
LABEL_8:
      if ( !v10 )
      {
        SetLastError(2u);
        v16 = 0;
        v10 = 0;
        v17 = 0;
        goto LABEL_10;
      }
    }
    while ( v14 != *((_DWORD *)v10 + 1) || CompareStringA(0x409u, 1u, "DEFAULT", -1, *((PCNZCH *)v10 + 2), -1) != 2 );
    v17 = (void *)*((_QWORD *)v10 + 4);
    v16 = 1;
LABEL_10:
    ProcAddress = v17;
    hFuncAddr = v10;
    if ( !v16 )
      break;
    v32 = *a8;
    memset_0(a8, 0, *a8);
    *a8 = v32;
    if ( (a5 & 4) != 0 )
    {
      v48 = I_CryptRemainingMilliseconds(lpFileTime1);
      v33 = a7;
      *(_DWORD *)(a7 + 48) = v48;
      if ( !v48 )
        *(_DWORD *)(a7 + 48) = 1;
    }
    else
    {
      v33 = a7;
    }
    v35 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, int, __int64, unsigned int *))v17)(
            a1,
            v64,
            v63,
            v68,
            a5,
            v33,
            a8);
    if ( a9 )
      CertDiagSetRevocationProvider(v34, v10);
    if ( v35 || (v36 = a8[2], v36 == -2146885616) || a8[1] )
    {
      CryptFreeOIDFunctionAddress(v10, 0);
      return v35;
    }
    if ( v36 )
    {
      if ( (unsigned int)(v9 + 2146885615) <= 1 )
      {
        v37 = *a8 < 0x18;
        v9 = a8[2];
        v60 = a8[3];
        v59 = v36;
        if ( !v37 )
        {
          v61 = a8[4];
          v62 = a8[5];
        }
      }
    }
  }
  v18 = qword_180158390;
  v19 = 2;
  if ( !*((_DWORD *)qword_180158390 + 12) )
    LoadRegFunc(qword_180158390);
  if ( v12 )
    v20 = v12;
  else
    v20 = HIWORD(v58);
  for ( i = *((_QWORD *)v18 + 9); i; i = *(_QWORD *)(i + 8) )
  {
    if ( v20 == *(_DWORD *)i )
    {
      v19 = *(_DWORD *)(i + 24);
      break;
    }
  }
  v22 = 0;
  v23 = 2LL * v19;
  if ( !v23
    || v23 > g_ulMaxStackAllocSize
    || v23 + g_ulAdditionalProbeSize + 8 < v23
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_116;
  }
  v24 = v23 + 23;
  if ( v23 + 23 <= v23 + 8 )
    v24 = 0xFFFFFFFFFFFFFF0LL;
  v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
  v26 = alloca(v25);
  v27 = alloca(v25);
  v22 = &v58;
  if ( &v57 == (__int64 *)-64LL || (v58 = 1801679955, (v22 = &v60) == 0) )
  {
LABEL_116:
    if ( v23 + 8 >= v23 )
    {
      v46 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      v22 = v46;
      if ( v46 )
      {
        *v46 = 1885431112;
        v22 = v46 + 2;
      }
    }
  }
  if ( v22 )
  {
    v28 = qword_180158390;
    v29 = &dword_180139F6C;
    v30 = 2;
    if ( !*((_DWORD *)qword_180158390 + 12) )
      LoadRegFunc(qword_180158390);
    if ( v12 )
      v31 = v12;
    else
      v31 = HIWORD(v58);
    for ( j = *((_QWORD *)v28 + 9); j; j = *(_QWORD *)(j + 8) )
    {
      if ( v31 == *(_DWORD *)j )
      {
        v30 = *(_DWORD *)(j + 24);
        v29 = *(int **)(j + 16);
        break;
      }
    }
    if ( v30 <= v19 )
    {
      v67 = (const WCHAR *)v22;
      memcpy_0(v22, v29, 2LL * v30);
      v15 = (const WCHAR *)v22;
      while ( 2 )
      {
        if ( !v15 )
          goto LABEL_80;
        v39 = -1;
        do
          ++v39;
        while ( v15[v39] );
        v69 = v39;
        if ( !(_DWORD)v39 )
          goto LABEL_80;
        v40 = qword_180158390;
        if ( !*((_DWORD *)qword_180158390 + 12) )
        {
          LoadRegFunc(qword_180158390);
          v15 = v67;
        }
        if ( (_WORD)v58 )
          v41 = (unsigned __int16)v58;
        else
          v41 = HIWORD(v58);
        for ( k = *((_QWORD *)v40 + 9); k; k = *(_QWORD *)(k + 8) )
        {
          if ( v41 == *(_DWORD *)k )
          {
            for ( m = 0; m < *(_DWORD *)(k + 28); ++m )
            {
              if ( CompareStringW(0x409u, 1u, v15, -1, *(PCNZWCH *)(*(_QWORD *)(k + 32) + 8LL * m), -1) == 2 )
              {
                if ( !(unsigned int)GetDllProcAddr(
                                      *(struct _DLL_PROC_ELEMENT **)(*(_QWORD *)(k + 40) + 8LL * m),
                                      &ProcAddress,
                                      &hFuncAddr) )
                  goto LABEL_67;
                v56 = ProcAddress;
                v45 = (HMODULE *)hFuncAddr;
                goto LABEL_91;
              }
              v15 = v67;
            }
          }
        }
        Dll = FindDll(v15);
        v45 = (HMODULE *)Dll;
        if ( Dll && (unsigned int)LoadDll(Dll) )
        {
          ProcAddress = GetProcAddress(v45[3], *((LPCSTR *)v40 + 1));
          v56 = ProcAddress;
          if ( ProcAddress )
          {
            hFuncAddr = v45;
LABEL_91:
            v49 = *a8;
            memset_0(a8, 0, *a8);
            *a8 = v49;
            if ( (a5 & 4) != 0 )
            {
              v55 = I_CryptRemainingMilliseconds(lpFileTime1);
              v50 = a7;
              *(_DWORD *)(a7 + 48) = v55;
              if ( !v55 )
                *(_DWORD *)(a7 + 48) = 1;
            }
            else
            {
              v50 = a7;
            }
            v35 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, int, __int64, unsigned int *))v56)(
                    v58,
                    v64,
                    v63,
                    v68,
                    a5,
                    v50,
                    a8);
            if ( a9 )
            {
              LastError = GetLastError();
              Tls = I_CryptGetTls(g_hTlsCertDiag);
              if ( Tls )
              {
                OIDFuncDll = I_CryptGetOIDFuncDll(v45);
                CertDiagSetTlsStr(Tls, 0, OIDFuncDll);
                PkiDefaultCryptFree(OIDFuncDll);
              }
              SetLastError(LastError);
            }
            CryptFreeOIDFunctionAddress(v45, 0);
            if ( v35 )
              goto LABEL_83;
            v54 = a8[2];
            if ( v54 == -2146885616 || a8[1] )
              goto LABEL_83;
            if ( v54 && (unsigned int)(v59 + 2146885615) <= 1 )
            {
              v37 = *a8 < 0x18;
              v60 = a8[3];
              v59 = v54;
              if ( !v37 )
              {
                v61 = a8[4];
                v62 = a8[5];
              }
            }
            goto LABEL_67;
          }
          ReleaseDll((struct _DLL_ELEMENT *)v45);
        }
        ProcAddress = 0;
        hFuncAddr = 0;
LABEL_67:
        v15 = &v67[(unsigned int)(v69 + 1)];
        v67 = v15;
        continue;
      }
    }
    SetLastError(0xEAu);
  }
LABEL_80:
  v37 = *a8 < 0x18;
  a8[2] = v59;
  a8[3] = v60;
  a8[1] = 0;
  if ( !v37 )
  {
    a8[4] = v61;
    a8[5] = v62;
  }
  v35 = 0;
  if ( v22 )
  {
LABEL_83:
    if ( *(v22 - 2) == 1885431112 )
      ((void (__fastcall *)(unsigned int *, const WCHAR *, _QWORD))g_pfnFree)(v22 - 2, v15, 0);
  }
  return v35;
}

```

## disassembly

```asm
0x180028d9c  push    rbp
0x180028d9e  push    rbx
0x180028d9f  push    rsi
0x180028da0  push    rdi
0x180028da1  push    r12
0x180028da3  push    r13
0x180028da5  push    r14
0x180028da7  push    r15
0x180028da9  sub     rsp, 98h
0x180028db0  lea     rbp, [rsp+40h]
0x180028db5  mov     rax, cs:__security_cookie
0x180028dbc  xor     rax, rbp
0x180028dbf  mov     [rbp+90h+var_48], rax
0x180028dc3  mov     rsi, [rbp+90h+arg_38]
0x180028dca  xor     eax, eax
0x180028dcc  mov     r15d, 80092011h
0x180028dd2  mov     [rbp+90h+var_88], eax
0x180028dd5  mov     [rbp+90h+var_8C], r15d
0x180028dd9  mov     edi, eax
0x180028ddb  mov     [rbp+90h+var_84], eax
0x180028dde  mov     r12d, ecx
0x180028de1  mov     [rbp+90h+var_80], eax
0x180028de4  mov     [rbp+90h+var_58], r9
0x180028de8  mov     [rbp+90h+var_7C], r8d
0x180028dec  mov     [rbp+90h+var_78], edx
0x180028def  mov     [rbp+90h+var_90], ecx
0x180028df2  movzx   r13d, cx
0x180028df6  mov     rbx, cs:qword_180158390
0x180028dfd  cmp     [rbx+30h], eax
0x180028e00  jnz     short loc_180028E0C
0x180028e02  mov     rcx, rbx; pvArg
0x180028e05  call    ?LoadRegFunc@@YAXPEAU_FUNC_SET@@@Z; LoadRegFunc(_FUNC_SET *)
0x180028e0a  xor     eax, eax
0x180028e0c  test    r13d, r13d
0x180028e0f  jz      loc_180028F4F
0x180028e15  mov     r14d, r13d
0x180028e18  test    rdi, rdi
0x180028e1b  jnz     loc_180029204
0x180028e21  mov     rdi, [rbx+20h]
0x180028e25  test    rdi, rdi
0x180028e28  jnz     loc_1800291B5
0x180028e2e  lea     ecx, [rdi+2]; dwErrCode
0x180028e31  call    cs:__imp_SetLastError
0x180028e37  xor     r8d, r8d
0x180028e3a  mov     eax, r8d
0x180028e3d  mov     edi, r8d
0x180028e40  mov     r14d, r8d
0x180028e43  mov     [rbp+90h+var_70], r14
0x180028e47  mov     [rbp+90h+hFuncAddr], rdi
0x180028e4b  test    eax, eax
0x180028e4d  jnz     loc_180028F66
0x180028e53  mov     rbx, cs:qword_180158390
0x180028e5a  lea     r12d, [rax+2]
0x180028e5e  cmp     [rbx+30h], r8d
0x180028e62  jz      loc_180029404
0x180028e68  test    r13d, r13d
0x180028e6b  jz      loc_180028F5B
0x180028e71  mov     ecx, r13d
0x180028e74  mov     rax, [rbx+48h]
0x180028e78  test    rax, rax
0x180028e7b  jz      short loc_180028E89
0x180028e7d  cmp     ecx, [rax]
0x180028e7f  jnz     loc_1800292B6
0x180028e85  mov     r12d, [rax+18h]
0x180028e89  mov     eax, r12d
0x180028e8c  mov     r15, r8
0x180028e8f  lea     rbx, [rax+rax]
0x180028e93  test    rbx, rbx
0x180028e96  jz      loc_18002917E
0x180028e9c  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180028ea3  ja      loc_18002917E
0x180028ea9  mov     rcx, cs:g_ulAdditionalProbeSize
0x180028eb0  add     rcx, 8
0x180028eb4  add     rcx, rbx
0x180028eb7  cmp     rcx, rbx
0x180028eba  jb      loc_18002917E
0x180028ec0  call    VerifyStackAvailable
0x180028ec5  xor     r8d, r8d
0x180028ec8  test    eax, eax
0x180028eca  jz      loc_18002917E
0x180028ed0  lea     rax, [rbx+8]
0x180028ed4  lea     rcx, [rax+0Fh]
0x180028ed8  cmp     rcx, rax
0x180028edb  ja      short loc_180028EE7
0x180028edd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180028ee7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180028eeb  mov     rax, rcx
0x180028eee  call    _alloca_probe
0x180028ef3  sub     rsp, rcx
0x180028ef6  lea     r15, [rsp+0D0h+var_90]
0x180028efb  test    r15, r15
0x180028efe  jz      loc_18002917E
0x180028f04  mov     dword ptr [r15], 6B637453h
0x180028f0b  add     r15, 8
0x180028f0f  jz      loc_18002917E
0x180028f15  test    r15, r15
0x180028f18  jz      loc_18002921E
0x180028f1e  mov     rbx, cs:qword_180158390
0x180028f25  lea     r14, dword_180139F6C
0x180028f2c  mov     edi, 2
0x180028f31  cmp     [rbx+30h], r8d
0x180028f35  jz      loc_180029414
0x180028f3b  test    r13d, r13d
0x180028f3e  jnz     loc_180029030
0x180028f44  mov     ecx, [rbp+90h+var_90]
0x180028f47  shr     ecx, 10h
0x180028f4a  jmp     loc_180029033
0x180028f4f  mov     r14d, r12d
0x180028f52  shr     r14d, 10h
0x180028f56  jmp     loc_180028E18
0x180028f5b  mov     ecx, [rbp+90h+var_90]
0x180028f5e  shr     ecx, 10h
0x180028f61  jmp     loc_180028E74
0x180028f66  mov     ebx, [rsi]
0x180028f68  xor     edx, edx; Val
0x180028f6a  mov     r8d, ebx; Size
0x180028f6d  mov     rcx, rsi; void *
0x180028f70  call    memset_0
0x180028f75  mov     [rsi], ebx
0x180028f77  mov     ebx, [rbp+90h+arg_20]
0x180028f7d  test    bl, 4
0x180028f80  jnz     loc_18002927E
0x180028f86  mov     rcx, [rbp+90h+arg_30]
0x180028f8d  mov     r9, [rbp+90h+var_58]
0x180028f91  mov     rax, r14
0x180028f94  mov     r8d, [rbp+90h+var_7C]
0x180028f98  mov     edx, [rbp+90h+var_78]
0x180028f9b  mov     [rsp+0D0h+var_A0], rsi
0x180028fa0  mov     qword ptr [rsp+0D0h+cchCount2], rcx
0x180028fa5  mov     ecx, r12d
0x180028fa8  mov     dword ptr [rsp+0D0h+lpString2], ebx
0x180028fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fb1  mov     r14d, eax
0x180028fb4  xor     eax, eax
0x180028fb6  cmp     [rbp+90h+arg_40], rax
0x180028fbd  jz      short loc_180028FC9
0x180028fbf  mov     rdx, rdi
0x180028fc2  call    CertDiagSetRevocationProvider
0x180028fc7  xor     eax, eax
0x180028fc9  test    r14d, r14d
0x180028fcc  jnz     loc_180029212
0x180028fd2  mov     ecx, [rsi+8]
0x180028fd5  cmp     ecx, 80092010h
0x180028fdb  jz      loc_180029212
0x180028fe1  cmp     [rsi+4], eax
0x180028fe4  ja      loc_180029212
0x180028fea  test    ecx, ecx
0x180028fec  jz      loc_180028DF6
0x180028ff2  lea     eax, [r15+7FF6DFEFh]
0x180028ff9  cmp     eax, 1
0x180028ffc  mov     eax, r14d
0x180028fff  ja      loc_180028DF6
0x180029005  cmp     dword ptr [rsi], 18h
0x180029008  mov     r15d, ecx
0x18002900b  mov     eax, [rsi+0Ch]
0x18002900e  mov     [rbp+90h+var_88], eax
0x180029011  mov     eax, r14d
0x180029014  mov     [rbp+90h+var_8C], ecx
0x180029017  jb      loc_180028DF6
0x18002901d  mov     eax, [rsi+10h]
0x180029020  mov     [rbp+90h+var_84], eax
0x180029023  mov     eax, [rsi+14h]
0x180029026  mov     [rbp+90h+var_80], eax
0x180029029  xor     eax, eax
0x18002902b  jmp     loc_180028DF6
0x180029030  mov     ecx, r13d
0x180029033  mov     rax, [rbx+48h]
0x180029037  test    rax, rax
0x18002903a  jz      short loc_18002904B
0x18002903c  cmp     ecx, [rax]
0x18002903e  jnz     loc_1800292BF
0x180029044  mov     edi, [rax+18h]
0x180029047  mov     r14, [rax+10h]
0x18002904b  cmp     edi, r12d
0x18002904e  ja      loc_180029421
0x180029054  mov     r8d, edi
0x180029057  mov     rdx, r14; Src
0x18002905a  add     r8, r8; Size
0x18002905d  mov     [rbp+90h+var_60], r15
0x180029061  mov     rcx, r15; void *
0x180029064  call    memcpy_0
0x180029069  mov     rdx, r15
0x18002906c  xor     r8d, r8d
0x18002906f  test    rdx, rdx
0x180029072  jz      loc_18002921E
0x180029078  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002907c  inc     rax
0x18002907f  cmp     [rdx+rax*2], r8w
0x180029084  jnz     short loc_18002907C
0x180029086  mov     [rbp+90h+var_50], rax
0x18002908a  test    eax, eax
0x18002908c  jz      loc_18002921E
0x180029092  mov     r13, cs:qword_180158390
0x180029099  cmp     [r13+30h], r8d
0x18002909d  jnz     short loc_1800290AE
0x18002909f  mov     rcx, r13; pvArg
0x1800290a2  call    ?LoadRegFunc@@YAXPEAU_FUNC_SET@@@Z; LoadRegFunc(_FUNC_SET *)
0x1800290a7  mov     rdx, [rbp+90h+var_60]
0x1800290ab  xor     r8d, r8d
0x1800290ae  mov     r12d, [rbp+90h+var_90]
0x1800290b2  movzx   eax, r12w
0x1800290b6  test    eax, eax
0x1800290b8  jz      loc_180029151
0x1800290be  mov     r14d, eax
0x1800290c1  mov     rbx, [r13+48h]
0x1800290c5  test    rbx, rbx
0x1800290c8  jz      loc_18002915D
0x1800290ce  cmp     r14d, [rbx]
0x1800290d1  jnz     loc_180029437
0x1800290d7  mov     edi, r8d
0x1800290da  cmp     edi, [rbx+1Ch]
0x1800290dd  jnb     loc_180029434
0x1800290e3  mov     rax, [rbx+20h]
0x1800290e7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800290eb  mov     r8, rdx; lpString1
0x1800290ee  mov     r12d, edi
0x1800290f1  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800290f9  mov     ecx, 409h; Locale
0x1800290fe  lea     edx, [r9+2]; dwCmpFlags
0x180029102  mov     rax, [rax+r12*8]
0x180029106  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18002910b  call    cs:__imp_CompareStringW
0x180029111  cmp     eax, 2
0x180029114  jnz     loc_180029273
0x18002911a  mov     rcx, [rbx+28h]
0x18002911e  lea     r8, [rbp+90h+hFuncAddr]; void **
0x180029122  lea     rdx, [rbp+90h+var_70]; void **
0x180029126  mov     rcx, [rcx+r12*8]; struct _DLL_PROC_ELEMENT *
0x18002912a  call    ?GetDllProcAddr@@YAHPEAU_DLL_PROC_ELEMENT@@PEAPEAX1@Z; GetDllProcAddr(_DLL_PROC_ELEMENT *,void * *,void * *)
0x18002912f  xor     r8d, r8d
0x180029132  test    eax, eax
0x180029134  jnz     loc_180029440
0x18002913a  mov     rax, [rbp+90h+var_50]
0x18002913e  mov     rdx, [rbp+90h+var_60]
0x180029142  inc     eax
0x180029144  lea     rdx, [rdx+rax*2]
0x180029148  mov     [rbp+90h+var_60], rdx
0x18002914c  jmp     loc_18002906F
0x180029151  mov     r14d, r12d
0x180029154  shr     r14d, 10h
0x180029158  jmp     loc_1800290C1
0x18002915d  mov     rcx, rdx; lpSrc
0x180029160  call    ?FindDll@@YAPEAU_DLL_ELEMENT@@PEBG@Z; FindDll(ushort const *)
0x180029165  xor     r8d, r8d
0x180029168  mov     rdi, rax
0x18002916b  test    rax, rax
0x18002916e  jnz     loc_180029450
0x180029174  mov     [rbp+90h+var_70], r8
0x180029178  mov     [rbp+90h+hFuncAddr], r8
0x18002917c  jmp     short loc_18002913A
0x18002917e  lea     rcx, [rbx+8]
0x180029182  cmp     rcx, rbx
0x180029185  jb      loc_180028F15
0x18002918b  mov     rax, cs:g_pfnAllocate
0x180029192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029197  xor     r8d, r8d
0x18002919a  mov     r15, rax
0x18002919d  test    rax, rax
0x1800291a0  jz      loc_180028F15
0x1800291a6  mov     dword ptr [rax], 70616548h
0x1800291ac  add     r15, 8
0x1800291b0  jmp     loc_180028F15
0x1800291b5  cmp     r14d, [rdi+4]
0x1800291b9  jnz     loc_1800293FB
0x1800291bf  mov     rax, [rdi+10h]
0x1800291c3  lea     r8, pszOID; "DEFAULT"
0x1800291ca  or      r9d, 0FFFFFFFFh; cchCount1
0x1800291ce  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800291d6  mov     ecx, 409h; Locale
0x1800291db  mov     [rsp+0D0h+lpString2], rax; lpString2
0x1800291e0  lea     edx, [r9+2]; dwCmpFlags
0x1800291e4  call    cs:__imp_CompareStringA
0x1800291ea  cmp     eax, 2
0x1800291ed  jnz     loc_1800293F9
0x1800291f3  mov     r14, [rdi+20h]
0x1800291f7  mov     eax, 1
0x1800291fc  xor     r8d, r8d
0x1800291ff  jmp     loc_180028E43
0x180029204  cmp     dword ptr [rdi], 2
0x180029207  jnz     loc_180028E21
0x18002920d  jmp     loc_1800293FB
0x180029212  xor     edx, edx; dwFlags
0x180029214  mov     rcx, rdi; hFuncAddr
0x180029217  call    CryptFreeOIDFunctionAddress
0x18002921c  jmp     short loc_180029253
0x18002921e  cmp     dword ptr [rsi], 18h
0x180029221  mov     eax, [rbp+90h+var_8C]
0x180029224  mov     [rsi+8], eax
0x180029227  mov     eax, [rbp+90h+var_88]
0x18002922a  mov     [rsi+0Ch], eax
0x18002922d  mov     [rsi+4], r8d
0x180029231  jb      short loc_18002923F
0x180029233  mov     eax, [rbp+90h+var_84]
0x180029236  mov     [rsi+10h], eax
0x180029239  mov     eax, [rbp+90h+var_80]
0x18002923c  mov     [rsi+14h], eax
0x18002923f  mov     r14d, r8d
0x180029242  test    r15, r15
0x180029245  jz      short loc_180029253
0x180029247  lea     rcx, [r15-8]
  ... truncated ...
```
