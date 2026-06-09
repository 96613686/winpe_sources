# SubmitRequest

- ea: `0x180012330`
- end: `0x180013f32`
- name: `SubmitRequest`
- size: `7170`
- prototype: ``
- caller_count: `14`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012050`
- `0x180012240`
- `0x180017e20`
- `0x1800182f0`
- `0x180018c90`
- `0x180018da0`
- `0x1800190c0`
- `0x180019470`
- `0x1800195a0`
- `0x180019cb0`
- `0x18001b130`
- `0x18001b7d0`
- `0x18001f5b0`
- `0x18001fba0`

## callees

- `0x180012330`
- `0x180013f40`
- `0x180014230`
- `0x1800142b0`
- `0x180015010`
- `0x180015428`
- `0x180021ae4`
- `0x180021b14`
- `0x180022320`
- `0x18002484c`
- `0x180027386`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013144`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013144`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013397`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013162`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013da1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013da1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001238c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001238c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013249`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800131b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800131b8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013235`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013235`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800131f8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800131f8`
- `rtutils!TracePrintfExA` at `0x1800131a7`
- `rtutils!TracePrintfExA` at `0x1800131a7`

## string_xrefs

- `0x18001318f`: `PutRequestInQueue: OpenThreadToken Failed 0x%.8x`
- `0x180013225`: `PutRequestInQueue: DuplicateToken Failed 0x%.8x`
- `0x180013198`: `PutRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x`

## pseudocode

```c
__int64 SubmitRequest(__int64 a1, unsigned __int16 a2, ...)
{
  void *v3; // rdi
  char *v4; // rbx
  char *v5; // r12
  unsigned int v6; // r14d
  int v7; // r13d
  DWORD v8; // eax
  __int16 *v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  PVOID *v15; // rcx
  STRSAFE_LPSTR v16; // r14
  unsigned int v17; // eax
  unsigned int v19; // eax
  unsigned int v20; // r15d
  __int64 v21; // rdx
  PVOID *v22; // rcx
  const char *v23; // r13
  _OWORD *v24; // r14
  __int64 v25; // rcx
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  _DWORD *v29; // r13
  __int64 v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  int v33; // r14d
  _DWORD *v34; // r13
  __int64 v35; // rcx
  const char *v36; // r8
  char *v37; // r14
  size_t v38; // r13
  _DWORD *v39; // r14
  const char *v40; // r13
  __int64 v41; // rcx
  const char *v42; // r13
  int v43; // r14d
  __int64 v44; // rcx
  int v45; // eax
  const char *v46; // r13
  _DWORD *v47; // r14
  __int64 v48; // rcx
  char *v49; // rdx
  int v50; // eax
  __int64 v51; // rax
  __int128 v52; // xmm0
  int v53; // ecx
  const char *v54; // r13
  _DWORD *v55; // r14
  __int64 v56; // rcx
  char *v57; // rcx
  const void *v58; // rdx
  __int64 v59; // rax
  __int128 v60; // xmm0
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v63; // eax
  DWORD v64; // eax
  __int16 *v65; // rdx
  __int16 *v66; // kr10_8
  PVOID *v67; // rax
  STRSAFE_LPSTR v68; // rcx
  char *v69; // rax
  __int64 v70; // rdx
  __int128 v71; // xmm0
  PVOID *v72; // r10
  char *v73; // r14
  unsigned int v74; // eax
  STRSAFE_LPSTR v75; // r15
  __int64 v76; // rdx
  char *v77; // rdx
  size_t v78; // r8
  char *v79; // rcx
  PVOID *v80; // rcx
  char *v81; // r14
  PVOID *v82; // rax
  PVOID v83; // rcx
  PVOID *v84; // r10
  _DWORD *v85; // r15
  __int64 v86; // rdx
  _DWORD *v87; // rcx
  _DWORD *v88; // r14
  __int64 v89; // rdx
  __int64 v90; // r9
  unsigned int *v91; // r15
  unsigned int v92; // eax
  _QWORD *v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // r9
  int v96; // ecx
  char *v97; // rcx
  char *v98; // rcx
  PVOID *v99; // rcx
  bool v100; // zf
  unsigned int *v101; // r15
  char *v102; // r14
  unsigned int v103; // eax
  char *v104; // [rsp+30h] [rbp-29h]
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-21h] BYREF
  int v106; // [rsp+40h] [rbp-19h] BYREF
  STRSAFE_LPSTR *v107; // [rsp+48h] [rbp-11h]
  char *v108; // [rsp+50h] [rbp-9h]
  STRSAFE_LPCSTR pszSrc; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v110; // [rsp+60h] [rbp+7h]
  _DWORD *v111; // [rsp+68h] [rbp+Fh]
  _DWORD *v113; // [rsp+D0h] [rbp+77h] BYREF
  va_list va; // [rsp+D0h] [rbp+77h]
  const char *v115; // [rsp+D8h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+D8h] [rbp+7Fh]
  char *v117; // [rsp+E0h] [rbp+87h] BYREF
  va_list va2; // [rsp+E0h] [rbp+87h]
  _DWORD *v119; // [rsp+E8h] [rbp+8Fh] BYREF
  va_list va3; // [rsp+E8h] [rbp+8Fh]
  va_list va4; // [rsp+F0h] [rbp+97h] BYREF

  va_start(va4, a2);
  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v113 = va_arg(va1, _DWORD *);
  va_copy(va2, va1);
  v115 = va_arg(va2, const char *);
  va_copy(va3, va2);
  v117 = va_arg(va3, char *);
  va_copy(va4, va3);
  v119 = va_arg(va4, _DWORD *);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, a1, a2);
  }
  v106 = 7168;
  v111 = 0;
  DuplicateTokenHandle = 0;
  v3 = 0;
  v4 = (char *)LocalAlloc(0x40u, 0x1C00u);
  if ( v4 )
  {
    *((_DWORD *)v4 + 1) = a2;
    v5 = v4;
    *((_DWORD *)v4 + 2) = 8;
    v108 = 0;
    v104 = 0;
    v111 = 0;
    v110 = 0;
    va_copy((va_list)v107, va);
    switch ( a2 )
    {
      case 0xCu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v23 = v115;
        v24 = v113;
        v108 = (char *)v115;
        va_copy((va_list)v107, va3);
        v104 = v117;
        if ( !v117 )
          *(_DWORD *)v115 = 0;
        v25 = *(unsigned int *)v23;
        if ( !(_DWORD)v25 )
          goto LABEL_71;
        v26 = AllocateBuffer(v25, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 18;
LABEL_67:
          WPP_SF_d(v27[2], v28, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v26);
LABEL_68:
          v3 = DuplicateTokenHandle;
          goto LABEL_33;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_71:
        *((_DWORD *)v5 + 6) = *(_DWORD *)v23;
        *(_OWORD *)(v5 + 28) = *v24;
        goto LABEL_4;
      case 0x15u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v29 = v113;
        v108 = (char *)v113;
        va_copy((va_list)v107, va2);
        v104 = (char *)v115;
        if ( !v115 )
          *v113 = 0;
        v30 = (unsigned int)*v29;
        if ( !(_DWORD)v30 )
          goto LABEL_86;
        v26 = AllocateBuffer(v30, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 20;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_86:
        *((_DWORD *)v5 + 7) = *v29;
        goto LABEL_4;
      case 0x16u:
      case 0x30u:
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_201;
        }
        v32 = 21;
        goto LABEL_200;
      case 0x49u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v33 = (int)v113;
        pszSrc = v115;
        v104 = v117;
        va_copy((va_list)v107, va4);
        v34 = v119;
        v108 = (char *)v119;
        if ( !v117 )
          *v119 = 0;
        v35 = (unsigned int)*v34;
        if ( !(_DWORD)v35 )
          goto LABEL_105;
        v26 = AllocateBuffer(v35, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 23;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_105:
        v36 = pszSrc;
        *(_DWORD *)v5 = v33;
        StringCchCopyA(v5 + 28, 0x10u, v36);
        *((_DWORD *)v5 + 11) = *v34;
        goto LABEL_4;
      case 0x5Eu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v37 = v117;
        LODWORD(pszSrc) = (_DWORD)v113;
        v110 = (unsigned int)v115;
        va_copy((va_list)v107, va3);
        v38 = (unsigned int)v115;
        v104 = v117;
        v26 = AllocateBuffer((unsigned int)v115, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 25;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
        *((_DWORD *)v5 + 9) = (_DWORD)pszSrc;
        *((_DWORD *)v5 + 8) = v38;
        memcpy_0(v5 + 40, v37, v38);
        goto LABEL_4;
      case 0x5Fu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v39 = v113;
        v40 = v115;
        v111 = v113;
        v108 = (char *)v115;
        va_copy((va_list)v107, va3);
        v104 = v117;
        if ( !v117 )
          *(_DWORD *)v115 = 0;
        v41 = *(unsigned int *)v40;
        if ( !(_DWORD)v41 )
          goto LABEL_132;
        v26 = AllocateBuffer(v41, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 29;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_132:
        *((_DWORD *)v5 + 7) = *v39;
        *((_DWORD *)v5 + 8) = *(_DWORD *)v40;
        goto LABEL_4;
      case 0x67u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v42 = v115;
        v43 = (int)v113;
        v108 = (char *)v115;
        va_copy((va_list)v107, va3);
        v104 = v117;
        if ( !v117 )
          *(_DWORD *)v115 = 0;
        v44 = *(unsigned int *)v42;
        if ( !(_DWORD)v44 )
          goto LABEL_147;
        v26 = AllocateBuffer(v44, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 31;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_147:
        *(_DWORD *)v5 = v43;
        *((_DWORD *)v5 + 7) = *(_DWORD *)v42;
        goto LABEL_4;
      case 0x68u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v45 = (int)v113;
        *(_DWORD *)v4 = 0;
        *((_DWORD *)v4 + 7) = v45;
        goto LABEL_202;
      case 0x69u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v46 = v115;
        v47 = v113;
        va_copy((va_list)v107, va3);
        v108 = (char *)v115;
        v104 = v117;
        if ( !v117 )
          *(_DWORD *)v115 = 0;
        v48 = *(unsigned int *)v46;
        if ( !(_DWORD)v48 )
          goto LABEL_167;
        v26 = AllocateBuffer(v48, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 34;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_167:
        *(_DWORD *)v5 = 0;
        v49 = v5 + 52;
        v50 = *(_DWORD *)v46;
        if ( a1 )
        {
          v53 = *(_DWORD *)(a1 + 12);
          *((_DWORD *)v5 + 8) = v50;
          if ( v53 != 6 )
          {
            *(_OWORD *)v49 = *(_OWORD *)v47;
            *(_OWORD *)(v5 + 68) = *((_OWORD *)v47 + 1);
            *(_OWORD *)(v5 + 84) = *((_OWORD *)v47 + 2);
            *(_OWORD *)(v5 + 100) = *((_OWORD *)v47 + 3);
            *(_OWORD *)(v5 + 116) = *((_OWORD *)v47 + 4);
            *(_OWORD *)(v5 + 132) = *((_OWORD *)v47 + 5);
            *(_OWORD *)(v5 + 148) = *((_OWORD *)v47 + 6);
            *(_OWORD *)(v5 + 164) = *((_OWORD *)v47 + 7);
            *(_OWORD *)(v5 + 180) = *((_OWORD *)v47 + 8);
            *(_OWORD *)(v5 + 196) = *((_OWORD *)v47 + 9);
            *(_OWORD *)(v5 + 212) = *((_OWORD *)v47 + 10);
            *(_OWORD *)(v5 + 228) = *((_OWORD *)v47 + 11);
            *(_OWORD *)(v5 + 244) = *((_OWORD *)v47 + 12);
            *((_DWORD *)v5 + 65) = v47[52];
            goto LABEL_4;
          }
        }
        else
        {
          *((_DWORD *)v5 + 8) = v50;
        }
        v51 = 3;
        do
        {
          v49 += 128;
          v52 = *(_OWORD *)v47;
          v47 += 32;
          *((_OWORD *)v49 - 8) = v52;
          *((_OWORD *)v49 - 7) = *((_OWORD *)v47 - 7);
          *((_OWORD *)v49 - 6) = *((_OWORD *)v47 - 6);
          *((_OWORD *)v49 - 5) = *((_OWORD *)v47 - 5);
          *((_OWORD *)v49 - 4) = *((_OWORD *)v47 - 4);
          *((_OWORD *)v49 - 3) = *((_OWORD *)v47 - 3);
          *((_OWORD *)v49 - 2) = *((_OWORD *)v47 - 2);
          *((_OWORD *)v49 - 1) = *((_OWORD *)v47 - 1);
          --v51;
        }
        while ( v51 );
        *(_OWORD *)v49 = *(_OWORD *)v47;
        *((_OWORD *)v49 + 1) = *((_OWORD *)v47 + 1);
        *((_OWORD *)v49 + 2) = *((_OWORD *)v47 + 2);
        *((_OWORD *)v49 + 3) = *((_OWORD *)v47 + 3);
        *((_OWORD *)v49 + 4) = *((_OWORD *)v47 + 4);
        *((_QWORD *)v49 + 10) = *((_QWORD *)v47 + 10);
LABEL_4:
        v6 = v106;
        v7 = 0;
        pszSrc = 0;
        DuplicateTokenHandle = 0;
        if ( g_fRasmanService && g_fnRasmanServiceInitialized && g_fnRasmanServiceInitialized() )
        {
          if ( !g_fnServiceRequest )
          {
            v11 = 711;
            goto LABEL_7;
          }
          v11 = 0;
          if ( !NtCurrentTeb()->IsImpersonating )
          {
            ((void (__fastcall *)(char *, _QWORD))g_fnServiceRequest)(v5, v6);
            goto LABEL_7;
          }
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 2u, 1, (PHANDLE)&pszSrc) )
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "PutRequestInQueue: OpenThreadToken Failed 0x%.8x", LastError);
            goto LABEL_7;
          }
          if ( RevertToSelf() )
          {
            ((void (__fastcall *)(char *, _QWORD))g_fnServiceRequest)(v5, v6);
            if ( DuplicateToken((HANDLE)pszSrc, SecurityImpersonation, &DuplicateTokenHandle) )
            {
              if ( !ImpersonateLoggedOnUser(DuplicateTokenHandle) )
              {
                v64 = GetLastError();
                v11 = v64;
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(g_dwTraceId, 0xCu, "PutRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x", v64);
              }
            }
            else
            {
              v63 = GetLastError();
              v11 = v63;
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "PutRequestInQueue: DuplicateToken Failed 0x%.8x", v63);
            }
LABEL_7:
            if ( DuplicateTokenHandle )
              CloseHandle(DuplicateTokenHandle);
            if ( pszSrc )
              CloseHandle((HANDLE)pszSrc);
            if ( v11 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_33;
              }
              v13 = 39;
              v14 = v11;
              goto LABEL_32;
            }
            v66 = v9;
            v65 = &_ImageBase;
            switch ( a2 )
            {
              case 0xCu:
              case 0x15u:
                v72 = (PVOID *)WPP_GLOBAL_Control;
                v65 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v72 = (PVOID *)WPP_GLOBAL_Control;
                  v65 = (__int16 *)&WPP_GLOBAL_Control;
                }
                v73 = v108;
                v74 = *((_DWORD *)v5 + 7);
                v75 = *v107;
                if ( *(_DWORD *)v108 < v74 )
                {
                  v11 = 603;
                  if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 0x40) != 0 && *((_BYTE *)v72 + 25) >= 2u )
                  {
                    v76 = 42;
                    goto LABEL_239;
                  }
                }
                else
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( v11
                    && v72 != &WPP_GLOBAL_Control
                    && (*((_BYTE *)v72 + 28) & 0x40) != 0
                    && *((_BYTE *)v72 + 25) >= 2u )
                  {
                    v76 = 41;
LABEL_239:
                    WPP_SF_d(v72[2], v76, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                    *(_DWORD *)v73 = *((_DWORD *)v5 + 7);
                    *(_DWORD *)v75 = *((_DWORD *)v5 + 8);
                    goto LABEL_24;
                  }
                }
                *(_DWORD *)v108 = v74;
                *(_DWORD *)v75 = *((_DWORD *)v5 + 8);
                if ( v11 )
                  goto LABEL_24;
                v77 = v5 + 36;
                goto LABEL_247;
              case 0x16u:
                v67 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v67 = (PVOID *)WPP_GLOBAL_Control;
                }
                v16 = *v107;
                v11 = *((_DWORD *)v4 + 6);
                if ( v11
                  && v67 != &WPP_GLOBAL_Control
                  && (*((_BYTE *)v67 + 28) & 0x40) != 0
                  && *((_BYTE *)v67 + 25) >= 2u )
                {
                  WPP_SF_d(v67[2], 44, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                }
                v68 = v16;
                v69 = v4 + 32;
                v70 = 7;
                do
                {
                  v68 += 128;
                  v71 = *(_OWORD *)v69;
                  v69 += 128;
                  *((_OWORD *)v68 - 8) = v71;
                  *((_OWORD *)v68 - 7) = *((_OWORD *)v69 - 7);
                  *((_OWORD *)v68 - 6) = *((_OWORD *)v69 - 6);
                  *((_OWORD *)v68 - 5) = *((_OWORD *)v69 - 5);
                  *((_OWORD *)v68 - 4) = *((_OWORD *)v69 - 4);
                  *((_OWORD *)v68 - 3) = *((_OWORD *)v69 - 3);
                  *((_OWORD *)v68 - 2) = *((_OWORD *)v69 - 2);
                  *((_OWORD *)v68 - 1) = *((_OWORD *)v69 - 1);
                  --v70;
                }
                while ( v70 );
                *(_OWORD *)v68 = *(_OWORD *)v69;
                *((_QWORD *)v68 + 2) = *((_QWORD *)v69 + 2);
                *((_DWORD *)v16 + 83) = *((_DWORD *)v16 + 83) == GetCurrentProcessId();
                goto LABEL_25;
              case 0x30u:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                }
                *(_QWORD *)*v107 = *((_QWORD *)v4 + 4);
                v11 = *((_DWORD *)v4 + 6);
                if ( !v11 )
                  goto LABEL_24;
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_24;
                }
                v21 = 46;
                goto LABEL_411;
              case 0x49u:
                v80 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v80 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( v11 )
                {
                  if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 28) & 0x40) != 0 && *((_BYTE *)v80 + 25) >= 2u )
                    WPP_SF_d(v80[2], 48, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  v81 = v108;
                }
                else
                {
                  v81 = v108;
                  if ( *((_DWORD *)v5 + 11) <= *(_DWORD *)v108 )
                  {
                    memcpy_0(v104, v5 + 48, *((unsigned int *)v5 + 11));
                  }
                  else
                  {
                    v11 = 603;
                    if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 28) & 0x40) != 0 && *((_BYTE *)v80 + 25) >= 2u )
                      WPP_SF_d(v80[2], 49, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 603);
                  }
                }
                *(_DWORD *)v81 = *((_DWORD *)v5 + 11);
                goto LABEL_24;
              case 0x5Eu:
                v82 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v82 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11 )
                  goto LABEL_24;
                v65 = (__int16 *)*((unsigned int *)v5 + 8);
                if ( (unsigned int)v65 <= v110 )
                {
                  v16 = v104;
                  memcpy_0(v104, v5 + 40, *((unsigned int *)v5 + 8));
                  goto LABEL_25;
                }
                v11 = 603;
                if ( v82 != &WPP_GLOBAL_Control && (*((_BYTE *)v82 + 28) & 0x40) != 0 && *((_BYTE *)v82 + 25) >= 2u )
                {
                  v83 = v82[2];
                  v21 = 51;
                  goto LABEL_412;
                }
                goto LABEL_24;
              case 0x5Fu:
                v84 = (PVOID *)WPP_GLOBAL_Control;
                v65 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v84 = (PVOID *)WPP_GLOBAL_Control;
                  v65 = (__int16 *)&WPP_GLOBAL_Control;
                }
                v73 = v108;
                v85 = *v107;
                if ( *(_DWORD *)v108 < *((_DWORD *)v5 + 8) )
                {
                  v11 = 603;
                  if ( v84 != &WPP_GLOBAL_Control && (*((_BYTE *)v84 + 28) & 0x40) != 0 && *((_BYTE *)v84 + 25) >= 2u )
                  {
                    v86 = 55;
                    goto LABEL_303;
                  }
                }
                else
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( v11
                    && v84 != &WPP_GLOBAL_Control
                    && (*((_BYTE *)v84 + 28) & 0x40) != 0
                    && *((_BYTE *)v84 + 25) >= 2u )
                  {
                    v86 = 54;
LABEL_303:
                    WPP_SF_d(v84[2], v86, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  }
                }
                v87 = v111;
                *v85 = *((_DWORD *)v5 + 9);
                *(_DWORD *)v73 = *((_DWORD *)v5 + 8);
                *v87 = *((_DWORD *)v5 + 7);
                if ( v11 )
                  goto LABEL_24;
                v77 = v5 + 40;
LABEL_247:
                v78 = *(unsigned int *)v73;
                v16 = v104;
                v79 = v104;
LABEL_249:
                memcpy_0(v79, v77, v78);
                goto LABEL_25;
              case 0x67u:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                v65 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                  v65 = (__int16 *)&WPP_GLOBAL_Control;
                }
                v19 = *((_DWORD *)v5 + 7);
                v20 = v19 + 36;
                if ( v19 + 36 < v19 )
                {
                  v11 = 87;
                  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 && *((_BYTE *)v15 + 25) >= 2u )
                  {
                    v21 = 57;
                    goto LABEL_411;
                  }
                  goto LABEL_24;
                }
                v88 = v108;
                if ( *(_DWORD *)v108 >= v20 )
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( !v11
                    || v15 == &WPP_GLOBAL_Control
                    || (*((_BYTE *)v15 + 28) & 0x40) == 0
                    || *((_BYTE *)v15 + 25) < 2u )
                  {
                    v90 = *(unsigned int *)v108;
                    *(_DWORD *)v108 = v20;
                    if ( !v11 )
                    {
                      v16 = v104;
                      if ( v104 )
                      {
                        v91 = (unsigned int *)(v5 + 32);
                        v92 = ValidateRasTapiInfo(v5 + 32, *((unsigned int *)v5 + 7), v10, v90);
                        v11 = v92;
                        if ( v92 )
                        {
                          v93 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v94 = 60;
                            v95 = v92;
LABEL_329:
                            WPP_SF_d(v93[2], v94, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v95);
                          }
                        }
                        else
                        {
                          v96 = *v91;
                          *(_DWORD *)v104 = *v91;
                          *((_DWORD *)v104 + 4) = *((_DWORD *)v5 + 10);
                          *((_DWORD *)v104 + 8) = *((_DWORD *)v5 + 12);
                          *((_DWORD *)v104 + 12) = *((_DWORD *)v5 + 14);
                          if ( v96 )
                          {
                            *((_QWORD *)v104 + 1) = v104 + 64;
                            memcpy_0(v104 + 64, (char *)v91 + *((unsigned int *)v5 + 9), *v91);
                          }
                          else
                          {
                            *((_QWORD *)v104 + 1) = 0;
                          }
                          if ( *((_DWORD *)v104 + 4) )
                          {
                            v97 = &v104[((*(_DWORD *)v104 + 7) & 0xFFFFFFF8) + 64];
                            *((_QWORD *)v104 + 3) = v97;
                            memcpy_0(v97, (char *)v91 + *((unsigned int *)v5 + 11), *((unsigned int *)v5 + 10));
                          }
                          else
                          {
                            *((_QWORD *)v104 + 3) = 0;
                          }
                          if ( *((_DWORD *)v104 + 8) )
                          {
                            v98 = &v104[((*(_DWORD *)v104 + 7) & 0xFFFFFFF8)
                                      + 64
                                      + ((*((_DWORD *)v104 + 4) + 7) & 0xFFFFFFF8)];
                            *((_QWORD *)v104 + 5) = v98;
                            memcpy_0(v98, (char *)v91 + *((unsigned int *)v5 + 13), *((unsigned int *)v5 + 12));
                          }
                          else
                          {
                            *((_QWORD *)v104 + 5) = 0;
                          }
                          if ( *((_DWORD *)v104 + 12) )
                          {
                            v79 = &v104[((*((_DWORD *)v104 + 4) + 7) & 0xFFFFFFF8)
                                      + 64
                                      + ((*((_DWORD *)v104 + 8) + 7) & 0xFFFFFFF8)
                                      + ((*(_DWORD *)v104 + 7) & 0xFFFFFFF8)];
                            *((_QWORD *)v104 + 7) = v79;
                            v78 = *((unsigned int *)v5 + 14);
                            v77 = (char *)v91 + *((unsigned int *)v5 + 15);
                            goto LABEL_249;
                          }
                          *((_QWORD *)v104 + 7) = 0;
                        }
                      }
                      goto LABEL_25;
                    }
LABEL_24:
                    v16 = v104;
LABEL_25:
                    if ( !v7 )
                      goto LABEL_33;
                    if ( v11 )
                      goto LABEL_33;
                    v17 = SanityFilterAfterRPC(v5, v65, a2, v16);
                    v11 = v17;
                    if ( !v17 )
                      goto LABEL_33;
                    v12 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_33;
                    }
                    v13 = 76;
                    v14 = v17;
LABEL_32:
                    WPP_SF_d(v12[2], v13, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v14);
LABEL_33:
                    if ( v3 )
                      LocalFree(v3);
                    LocalFree(v4);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        77,
                        &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids,
                        v11);
                    }
                    return v11;
                  }
                  v89 = 59;
                }
                else
                {
                  v11 = 603;
                  if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 || *((_BYTE *)v15 + 25) < 2u )
                    goto LABEL_317;
                  v89 = 58;
                }
                WPP_SF_d(v15[2], v89, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
LABEL_317:
                *v88 = v20;
                goto LABEL_24;
              case 0x68u:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11 )
                {
                  StringCchCopyA(*v107, 0x81u, v5 + 32);
                  goto LABEL_24;
                }
                if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 || *((_BYTE *)v15 + 25) < 2u )
                  goto LABEL_24;
                v21 = 62;
                goto LABEL_411;
              case 0x69u:
                v99 = (PVOID *)WPP_GLOBAL_Control;
                v65 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v99 = (PVOID *)WPP_GLOBAL_Control;
                  v65 = (__int16 *)&WPP_GLOBAL_Control;
                }
                if ( !a1 || (v100 = *(_DWORD *)(a1 + 12) == 6, v101 = (unsigned int *)(v5 + 264), v100) )
                  v101 = (unsigned int *)(v5 + 524);
                v11 = *((_DWORD *)v5 + 6);
                if ( v11 )
                {
                  if ( v99 != &WPP_GLOBAL_Control && (*((_BYTE *)v99 + 28) & 0x40) != 0 && *((_BYTE *)v99 + 25) >= 2u )
                    WPP_SF_d(v99[2], 64, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  *(_DWORD *)v108 = *((_DWORD *)v5 + 8);
                  goto LABEL_24;
                }
                v102 = v108;
                v103 = *((_DWORD *)v5 + 8);
                if ( *(_DWORD *)v108 < v103 )
                {
                  v11 = 603;
                  if ( v99 != &WPP_GLOBAL_Control && (*((_BYTE *)v99 + 28) & 0x40) != 0 && *((_BYTE *)v99 + 25) >= 2u )
                  {
                    WPP_SF_d(v99[2], 65, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 603);
                    *(_DWORD *)v102 = *((_DWORD *)v5 + 8);
                    goto LABEL_24;
                  }
                }
                *(_DWORD *)v108 = v103;
                if ( v11 )
                  goto LABEL_24;
                v16 = v104;
                if ( v104 )
                {
                  if ( *v101 <= *(_DWORD *)v104 )
                  {
                    memcpy_0(v104 + 4, v101 + 1, *v101);
                    *(_DWORD *)v104 = *v101;
                    goto LABEL_25;
                  }
                  v11 = 603;
                  v93 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v94 = 66;
                    v95 = 603;
                    goto LABEL_329;
                  }
                }
                goto LABEL_25;
              case 0x6Au:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11
                  || v15 == &WPP_GLOBAL_Control
                  || (*((_BYTE *)v15 + 28) & 0x40) == 0
                  || *((_BYTE *)v15 + 25) < 2u )
                {
                  goto LABEL_24;
                }
                v21 = 69;
                goto LABEL_411;
              case 0x6Fu:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11 )
                {
                  *(_QWORD *)*v107 = *(_QWORD *)(v5 + 28);
                  goto LABEL_24;
                }
                if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 || *((_BYTE *)v15 + 25) < 2u )
                  goto LABEL_24;
                v21 = 71;
                goto LABEL_411;
              case 0x7Du:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( v11 )
                {
                  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 && *((_BYTE *)v15 + 25) >= 2u )
                  {
                    v21 = 73;
LABEL_411:
                    v83 = v15[2];
LABEL_412:
                    WPP_SF_d(v83, v21, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  }
                }
                else
                {
                  StringCchCopyW((STRSAFE_LPWSTR)*v107, 0x81u, (STRSAFE_LPCWSTR)v5 + 14);
                }
                goto LABEL_24;
              default:
                v65 = v66;
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11
                  || v15 == &WPP_GLOBAL_Control
                  || (*((_BYTE *)v15 + 28) & 0x40) == 0
                  || *((_BYTE *)v15 + 25) < 2u )
                {
                  goto LABEL_24;
                }
                v21 = 75;
                goto LABEL_411;
            }
          }
          v8 = GetLastError();
        }
        else
        {
          v8 = RemoteSubmitRequest(a1, v5, v6);
          v7 = 1;
        }
        v11 = v8;
        goto LABEL_7;
      case 0x6Au:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v54 = v115;
        v55 = v113;
        va_copy((va_list)v107, va3);
        v56 = *(unsigned int *)v115;
        LODWORD(pszSrc) = (_DWORD)v117;
        v26 = AllocateBuffer(v56, &DuplicateTokenHandle, &v106);
        v11 = v26;
        if ( v26 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v28 = 36;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
        v57 = v5 + 52;
        *((_DWORD *)v5 + 7) = (_DWORD)pszSrc;
        v58 = v54 + 4;
        *(_DWORD *)v5 = 0;
        if ( !a1 || *(_DWORD *)(a1 + 12) == 6 )
        {
          v59 = 3;
          do
          {
            v57 += 128;
            v60 = *(_OWORD *)v55;
            v55 += 32;
            *((_OWORD *)v57 - 8) = v60;
            *((_OWORD *)v57 - 7) = *((_OWORD *)v55 - 7);
            *((_OWORD *)v57 - 6) = *((_OWORD *)v55 - 6);
            *((_OWORD *)v57 - 5) = *((_OWORD *)v55 - 5);
            *((_OWORD *)v57 - 4) = *((_OWORD *)v55 - 4);
            *((_OWORD *)v57 - 3) = *((_OWORD *)v55 - 3);
            *((_OWORD *)v57 - 2) = *((_OWORD *)v55 - 2);
            *((_OWORD *)v57 - 1) = *((_OWORD *)v55 - 1);
            --v59;
          }
          while ( v59 );
          *(_OWORD *)v57 = *(_OWORD *)v55;
          *((_OWORD *)v57 + 1) = *((_OWORD *)v55 + 1);
          *((_OWORD *)v57 + 2) = *((_OWORD *)v55 + 2);
          *((_OWORD *)v57 + 3) = *((_OWORD *)v55 + 3);
          *((_OWORD *)v57 + 4) = *((_OWORD *)v55 + 4);
          *((_QWORD *)v57 + 10) = *((_QWORD *)v55 + 10);
          memcpy_0(v5 + 528, v58, *(unsigned int *)v54);
          *((_DWORD *)v5 + 131) = *(_DWORD *)v54;
        }
        else
        {
          *(_OWORD *)v57 = *(_OWORD *)v55;
          *(_OWORD *)(v5 + 68) = *((_OWORD *)v55 + 1);
          *(_OWORD *)(v5 + 84) = *((_OWORD *)v55 + 2);
          *(_OWORD *)(v5 + 100) = *((_OWORD *)v55 + 3);
          *(_OWORD *)(v5 + 116) = *((_OWORD *)v55 + 4);
          *(_OWORD *)(v5 + 132) = *((_OWORD *)v55 + 5);
          *(_OWORD *)(v5 + 148) = *((_OWORD *)v55 + 6);
          *(_OWORD *)(v5 + 164) = *((_OWORD *)v55 + 7);
          *(_OWORD *)(v5 + 180) = *((_OWORD *)v55 + 8);
          *(_OWORD *)(v5 + 196) = *((_OWORD *)v55 + 9);
          *(_OWORD *)(v5 + 212) = *((_OWORD *)v55 + 10);
          *(_OWORD *)(v5 + 228) = *((_OWORD *)v55 + 11);
          *(_OWORD *)(v5 + 244) = *((_OWORD *)v55 + 12);
          *((_DWORD *)v5 + 65) = v55[52];
          memcpy_0(v5 + 268, v58, *(unsigned int *)v54);
          *((_DWORD *)v5 + 66) = *(_DWORD *)v54;
        }
        goto LABEL_4;
      case 0x6Fu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        *(_DWORD *)v4 = 0;
        goto LABEL_4;
      case 0x7Du:
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_201;
        }
        v32 = 38;
LABEL_200:
        WPP_SF_(v31[2], v32, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
LABEL_201:
        *(_DWORD *)v4 = (_DWORD)v113;
LABEL_202:
        va_copy((va_list)v107, va1);
        goto LABEL_4;
      default:
        goto LABEL_4;
    }
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 2147942414LL);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x40) != 0 && *((_BYTE *)v22 + 25) >= 6u )
      WPP_SF_d(v22[2], 16, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 2147942414LL);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012330  mov     [rsp-8+arg_8], dx
0x180012335  mov     [rsp-8+arg_10], r8
0x18001233a  mov     [rsp-8+arg_18], r9
0x18001233f  push    rbp
0x180012340  push    rbx
0x180012341  push    rsi
0x180012342  push    rdi
0x180012343  push    r14
0x180012345  push    r15
0x180012347  lea     rbp, [rsp-2Fh]
0x18001234c  sub     rsp, 88h
0x180012353  mov     r15, rcx
0x180012356  mov     rcx, cs:WPP_GLOBAL_Control
0x18001235d  lea     rsi, WPP_GLOBAL_Control
0x180012364  cmp     rcx, rsi
0x180012367  jnz     loc_1800125FC
0x18001236d  xor     r14d, r14d
0x180012370  mov     [rbp+57h+var_70], 1C00h
0x180012377  mov     edx, 1C00h; uBytes
0x18001237c  mov     [rbp+57h+var_48], r14
0x180012380  mov     ecx, 40h ; '@'; uFlags
0x180012385  mov     [rbp+57h+DuplicateTokenHandle], r14
0x180012389  mov     edi, r14d
0x18001238c  call    cs:__imp_LocalAlloc
0x180012393  nop     dword ptr [rax+rax+00h]
0x180012398  mov     rbx, rax
0x18001239b  test    rax, rax
0x18001239e  jz      loc_180012634
0x1800123a4  movzx   eax, [rbp+57h+arg_8]
0x1800123a8  lea     rsi, [rbp+57h+arg_10]
0x1800123ac  mov     [rbx+4], eax
0x1800123af  lea     rdx, __ImageBase
0x1800123b6  mov     [rsp+0B0h+var_30], r12
0x1800123be  mov     r12, rbx
0x1800123c1  mov     dword ptr [rbx+8], 8
0x1800123c8  movzx   eax, [rbp+57h+arg_8]
0x1800123cc  add     eax, 0FFFFFFF4h; switch 114 cases
0x1800123cf  mov     [rsp+0B0h+var_38], r13
0x1800123d4  mov     [rbp+57h+var_60], r14
0x1800123d8  mov     [rbp+57h+var_80], r14
0x1800123dc  mov     [rbp+57h+var_48], r14
0x1800123e0  mov     [rbp+57h+var_50], r14d
0x1800123e4  mov     [rbp+57h+var_68], rsi
0x1800123e8  cmp     eax, 71h
0x1800123eb  jbe     loc_1800126B3
0x1800123f1  mov     r14d, [rbp+57h+var_70]; jumptable 00000001800126C7 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x1800123f5  xor     r13d, r13d
0x1800123f8  cmp     cs:g_fRasmanService, r13d
0x1800123ff  mov     [rbp+57h+pszSrc], r13
0x180012403  mov     [rbp+57h+DuplicateTokenHandle], r13
0x180012407  jnz     short loc_180012479
0x180012409  mov     r8d, r14d
0x18001240c  mov     rdx, r12
0x18001240f  mov     rcx, r15
0x180012412  call    RemoteSubmitRequest
0x180012417  mov     r13d, 1
0x18001241d  mov     esi, eax
0x18001241f  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x180012423  test    rcx, rcx
0x180012426  jnz     loc_180013275
0x18001242c  mov     rcx, [rbp+57h+pszSrc]; hObject
0x180012430  test    rcx, rcx
0x180012433  jnz     loc_180013286
0x180012439  test    esi, esi
0x18001243b  jz      loc_1800124C9
0x180012441  mov     rcx, cs:WPP_GLOBAL_Control
0x180012448  lea     r15, WPP_GLOBAL_Control
0x18001244f  cmp     rcx, r15
0x180012452  jz      loc_180012550
0x180012458  test    byte ptr [rcx+1Ch], 40h
0x18001245c  jz      loc_180012550
0x180012462  cmp     byte ptr [rcx+19h], 2
0x180012466  jb      loc_180012550
0x18001246c  mov     edx, 27h ; '''
0x180012471  mov     r9d, esi
0x180012474  jmp     loc_180012540
0x180012479  mov     rax, cs:g_fnRasmanServiceInitialized
0x180012480  test    rax, rax
0x180012483  jz      short loc_180012409
0x180012485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001248a  test    rax, rax
0x18001248d  jz      loc_180012409
0x180012493  cmp     cs:g_fnServiceRequest, r13
0x18001249a  jz      loc_18001326B
0x1800124a0  mov     eax, gs:179Ch
0x1800124a8  xor     esi, esi
0x1800124aa  test    eax, eax
0x1800124ac  jnz     loc_180013144
0x1800124b2  mov     rax, cs:g_fnServiceRequest
0x1800124b9  mov     edx, r14d
0x1800124bc  mov     rcx, r12
0x1800124bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c4  jmp     loc_18001241F
0x1800124c9  movzx   eax, [rbp+57h+arg_8]
0x1800124cd  add     eax, 0FFFFFFF4h; switch 114 cases
0x1800124d0  cmp     eax, 71h
0x1800124d3  jbe     loc_180013297
0x1800124d9  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001800132B2 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x1800124e0  lea     r15, WPP_GLOBAL_Control
0x1800124e7  cmp     rcx, r15
0x1800124ea  jnz     loc_180013D2F
0x1800124f0  mov     esi, [r12+18h]
0x1800124f5  test    esi, esi
0x1800124f7  jnz     loc_180013D64
0x1800124fd  mov     r14, [rbp+57h+var_80]
0x180012501  test    r13d, r13d
0x180012504  jz      short loc_180012550
0x180012506  test    esi, esi
0x180012508  jnz     short loc_180012550
0x18001250a  movzx   r8d, [rbp+57h+arg_8]
0x18001250f  mov     r9, r14
0x180012512  mov     rcx, r12
0x180012515  call    SanityFilterAfterRPC
0x18001251a  mov     esi, eax
0x18001251c  test    eax, eax
0x18001251e  jz      short loc_180012550
0x180012520  mov     rcx, cs:WPP_GLOBAL_Control
0x180012527  cmp     rcx, r15
0x18001252a  jz      short loc_180012550
0x18001252c  test    byte ptr [rcx+1Ch], 40h
0x180012530  jz      short loc_180012550
0x180012532  cmp     byte ptr [rcx+19h], 2
0x180012536  jb      short loc_180012550
0x180012538  mov     edx, 4Ch ; 'L'
0x18001253d  mov     r9d, eax
0x180012540  mov     rcx, [rcx+10h]
0x180012544  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x18001254b  call    WPP_SF_d
0x180012550  mov     r13, [rsp+0B0h+var_38]
0x180012555  mov     r12, [rsp+0B0h+var_30]
0x18001255d  test    rdi, rdi
0x180012560  jnz     loc_180013D9E
0x180012566  mov     rcx, rbx; hMem
0x180012569  call    cs:__imp_LocalFree
0x180012570  nop     dword ptr [rax+rax+00h]
0x180012575  mov     rcx, cs:WPP_GLOBAL_Control
0x18001257c  cmp     rcx, r15
0x18001257f  jnz     loc_180013DB2
0x180012585  mov     eax, esi
0x180012587  add     rsp, 88h
0x18001258e  pop     r15
0x180012590  pop     r14
0x180012592  pop     rdi
0x180012593  pop     rsi
0x180012594  pop     rbx
0x180012595  pop     rbp
0x180012596  retn
0x180012598  cmp     rcx, rsi
0x18001259b  jnz     loc_18001267F
0x1800125a1  mov     eax, 8007000Eh
0x1800125a6  add     rsp, 88h
0x1800125ad  pop     r15
0x1800125af  pop     r14
0x1800125b1  pop     rdi
0x1800125b2  pop     rsi
0x1800125b3  pop     rbx
0x1800125b4  pop     rbp
0x1800125b5  retn
0x1800125b7  mov     eax, [r12+1Ch]
0x1800125bc  lea     r15d, [rax+24h]
0x1800125c0  cmp     r15d, eax
0x1800125c3  jnb     loc_180013846
0x1800125c9  mov     esi, 57h ; 'W'
0x1800125ce  lea     r15, WPP_GLOBAL_Control
0x1800125d5  cmp     rcx, r15
0x1800125d8  jz      loc_1800124FD
0x1800125de  test    byte ptr [rcx+1Ch], 40h
0x1800125e2  jz      loc_1800124FD
0x1800125e8  cmp     byte ptr [rcx+19h], 2
0x1800125ec  jb      loc_1800124FD
0x1800125f2  mov     edx, 39h ; '9'
0x1800125f7  jmp     loc_180013D86
0x1800125fc  test    byte ptr [rcx+1Ch], 40h
0x180012600  jz      loc_18001236D
0x180012606  cmp     byte ptr [rcx+19h], 6
0x18001260a  jb      loc_18001236D
0x180012610  mov     rcx, [rcx+10h]
0x180012614  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x18001261b  movzx   eax, dx
0x18001261e  mov     r9, r15
0x180012621  mov     edx, 0Eh
0x180012626  mov     [rsp+0B0h+var_90], eax
0x18001262a  call    WPP_SF_qd
0x18001262f  jmp     loc_18001236D
0x180012634  mov     rcx, cs:WPP_GLOBAL_Control
0x18001263b  cmp     rcx, rsi
0x18001263e  jz      loc_1800125A1
0x180012644  test    byte ptr [rcx+1Ch], 40h
0x180012648  jz      loc_180012598
0x18001264e  cmp     byte ptr [rcx+19h], 2
0x180012652  jb      loc_180012598
0x180012658  mov     rcx, [rcx+10h]
0x18001265c  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180012663  mov     edx, 0Fh
0x180012668  mov     r9d, 8007000Eh
0x18001266e  call    WPP_SF_d
0x180012673  mov     rcx, cs:WPP_GLOBAL_Control
0x18001267a  jmp     loc_180012598
0x18001267f  test    byte ptr [rcx+1Ch], 40h
0x180012683  jz      loc_1800125A1
0x180012689  cmp     byte ptr [rcx+19h], 6
0x18001268d  jb      loc_1800125A1
0x180012693  mov     rcx, [rcx+10h]
0x180012697  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x18001269e  mov     edx, 10h
0x1800126a3  mov     r9d, 8007000Eh
0x1800126a9  call    WPP_SF_d
0x1800126ae  jmp     loc_1800125A1
0x1800126b3  cdqe
0x1800126b5  movzx   eax, ds:(byte_180013E18 - 180000000h)[rdx+rax]
0x1800126bd  mov     ecx, ds:(jpt_1800126C7 - 180000000h)[rdx+rax*4]
0x1800126c4  add     rcx, rdx
0x1800126c7  jmp     rcx; switch jump
0x1800126cd  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001800126C7 case 12
0x1800126d4  lea     rax, WPP_GLOBAL_Control
0x1800126db  cmp     rcx, rax
0x1800126de  jz      short loc_180012701
0x1800126e0  test    byte ptr [rcx+1Ch], 40h
0x1800126e4  jz      short loc_180012701
0x1800126e6  cmp     byte ptr [rcx+19h], 5
0x1800126ea  jb      short loc_180012701
0x1800126ec  mov     rcx, [rcx+10h]
0x1800126f0  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x1800126f7  mov     edx, 11h
0x1800126fc  call    WPP_SF_
0x180012701  mov     r13, [rsi+8]
0x180012705  mov     r11, [rsi+10h]
0x180012709  mov     r14, [rsi]
0x18001270c  add     rsi, 18h
0x180012710  mov     [rbp+57h+var_60], r13
0x180012714  mov     [rbp+57h+var_68], rsi
0x180012718  mov     [rbp+57h+var_80], r11
0x18001271c  test    r11, r11
0x18001271f  jnz     short loc_180012725
0x180012721  mov     [r13+0], edi
0x180012725  mov     ecx, [r13+0]
0x180012729  test    ecx, ecx
0x18001272b  jz      short loc_18001279A
0x18001272d  lea     r8, [rbp+57h+var_70]
0x180012731  lea     rdx, [rbp+57h+DuplicateTokenHandle]
0x180012735  call    AllocateBuffer
0x18001273a  mov     esi, eax
0x18001273c  test    eax, eax
0x18001273e  jz      short loc_180012787
0x180012740  mov     rcx, cs:WPP_GLOBAL_Control
0x180012747  lea     r15, WPP_GLOBAL_Control
0x18001274e  cmp     rcx, r15
0x180012751  jz      short loc_18001277E
0x180012753  test    byte ptr [rcx+1Ch], 40h
0x180012757  jz      short loc_18001277E
0x180012759  cmp     byte ptr [rcx+19h], 2
0x18001275d  jb      short loc_18001277E
0x18001275f  mov     edx, 12h
0x180012764  jmp     short loc_18001276B
0x180012766  mov     edx, 24h ; '$'
0x18001276b  mov     rcx, [rcx+10h]
0x18001276f  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180012776  mov     r9d, eax
0x180012779  call    WPP_SF_d
0x18001277e  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x180012782  jmp     loc_180012550
0x180012787  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x18001278b  test    rdi, rdi
0x18001278e  jz      short loc_18001279A
0x180012790  movzx   eax, [rbp+57h+arg_8]
0x180012794  mov     r12, rdi
0x180012797  mov     [rdi+4], eax
0x18001279a  mov     eax, [r13+0]
0x18001279e  mov     [r12+18h], eax
0x1800127a3  movups  xmm0, xmmword ptr [r14]
0x1800127a7  movups  xmmword ptr [r12+1Ch], xmm0
0x1800127ad  jmp     def_1800126C7; jumptable 00000001800126C7 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x1800127b2  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001800126C7 case 21
0x1800127b9  lea     rax, WPP_GLOBAL_Control
0x1800127c0  cmp     rcx, rax
0x1800127c3  jz      short loc_1800127E6
0x1800127c5  test    byte ptr [rcx+1Ch], 40h
0x1800127c9  jz      short loc_1800127E6
0x1800127cb  cmp     byte ptr [rcx+19h], 5
0x1800127cf  jb      short loc_1800127E6
0x1800127d1  mov     rcx, [rcx+10h]
0x1800127d5  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x1800127dc  mov     edx, 13h
0x1800127e1  call    WPP_SF_
0x1800127e6  mov     r13, [rsi]
0x1800127e9  add     rsi, 10h
0x1800127ed  mov     [rbp+57h+var_60], r13
0x1800127f1  mov     [rbp+57h+var_68], rsi
0x1800127f5  mov     r11, [rsi-8]
0x1800127f9  mov     [rbp+57h+var_80], r11
0x1800127fd  test    r11, r11
0x180012800  jnz     short loc_180012806
0x180012802  mov     [r13+0], r14d
0x180012806  mov     ecx, [r13+0]
0x18001280a  test    ecx, ecx
0x18001280c  jz      short loc_180012869
0x18001280e  lea     r8, [rbp+57h+var_70]
0x180012812  lea     rdx, [rbp+57h+DuplicateTokenHandle]
0x180012816  call    AllocateBuffer
0x18001281b  mov     esi, eax
  ... truncated ...
```
