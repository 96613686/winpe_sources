# SubmitRequest

- ea: `0x180011b40`
- end: `0x1800136f2`
- name: `SubmitRequest`
- size: `7090`
- prototype: `__int64(__int64, unsigned __int16, ...)`
- caller_count: `14`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011860`
- `0x180011a50`
- `0x180017460`
- `0x180017930`
- `0x1800182a0`
- `0x1800183b0`
- `0x1800186d0`
- `0x180018a80`
- `0x180018bb0`
- `0x1800192c0`
- `0x18001a720`
- `0x18001adb0`
- `0x18001eb20`
- `0x18001f110`

## callees

- `0x180011b40`
- `0x180013700`
- `0x1800139e0`
- `0x180013a60`
- `0x1800146a0`
- `0x180014a40`
- `0x180020fd8`
- `0x180021000`
- `0x1800217a0`
- `0x180023b60`
- `0x1800263b6`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012b63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001295a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001295a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013567`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013567`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001299f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001299f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a16`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012995`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012995`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012a08`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012a08`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800129c9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800129c9`
- `rtutils!TracePrintfExA` at `0x18001298a`
- `rtutils!TracePrintfExA` at `0x1800129f9`
- `rtutils!TracePrintfExA` at `0x180012a3c`
- `rtutils!TracePrintfExA` at `0x18001298a`
- `rtutils!TracePrintfExA` at `0x1800129f9`
- `rtutils!TracePrintfExA` at `0x180012a3c`

## string_xrefs

- `0x18001297e`: `PutRequestInQueue: OpenThreadToken Failed 0x%.8x`
- `0x1800129ed`: `PutRequestInQueue: DuplicateToken Failed 0x%.8x`
- `0x180012a30`: `PutRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x`

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
  unsigned int *v23; // r13
  _OWORD *v24; // r14
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned int *v28; // r13
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  int v31; // r14d
  unsigned int *v32; // r13
  const char *v33; // r8
  char *v34; // r14
  size_t v35; // r13
  _DWORD *v36; // r14
  unsigned int *v37; // r13
  unsigned int *v38; // r13
  int v39; // r14d
  int v40; // eax
  unsigned int *v41; // r13
  _DWORD *v42; // r14
  char *v43; // rdx
  unsigned int v44; // eax
  __int64 v45; // rax
  __int128 v46; // xmm0
  int v47; // ecx
  const char *v48; // r13
  _DWORD *v49; // r14
  unsigned int v50; // ecx
  char *v51; // rcx
  const void *v52; // rdx
  __int64 v53; // rax
  __int128 v54; // xmm0
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v57; // eax
  DWORD v58; // eax
  __int16 *v59; // rdx
  __int16 *v60; // kr10_8
  PVOID *v61; // rax
  STRSAFE_LPSTR v62; // rcx
  char *v63; // rax
  __int64 v64; // rdx
  __int128 v65; // xmm0
  PVOID *v66; // r10
  char *v67; // r14
  unsigned int v68; // eax
  STRSAFE_LPSTR v69; // r15
  __int64 v70; // rdx
  char *v71; // rdx
  size_t v72; // r8
  char *v73; // rcx
  PVOID *v74; // rcx
  char *v75; // r14
  PVOID *v76; // rax
  PVOID v77; // rcx
  PVOID *v78; // r10
  _DWORD *v79; // r15
  __int64 v80; // rdx
  _DWORD *v81; // rcx
  _DWORD *v82; // r14
  __int64 v83; // rdx
  __int64 v84; // r9
  unsigned int *v85; // r15
  unsigned int v86; // eax
  _QWORD *v87; // rcx
  __int64 v88; // rdx
  __int64 v89; // r9
  int v90; // ecx
  char *v91; // rcx
  char *v92; // rcx
  PVOID *v93; // rcx
  bool v94; // zf
  unsigned int *v95; // r15
  char *v96; // r14
  unsigned int v97; // eax
  char *v98; // [rsp+30h] [rbp-29h]
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v100; // [rsp+40h] [rbp-19h] BYREF
  STRSAFE_LPSTR *v101; // [rsp+48h] [rbp-11h]
  char *v102; // [rsp+50h] [rbp-9h]
  STRSAFE_LPCSTR pszSrc; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v104; // [rsp+60h] [rbp+7h]
  _DWORD *v105; // [rsp+68h] [rbp+Fh]
  _DWORD *v107; // [rsp+D0h] [rbp+77h] BYREF
  va_list va; // [rsp+D0h] [rbp+77h]
  const char *v109; // [rsp+D8h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+D8h] [rbp+7Fh]
  char *v111; // [rsp+E0h] [rbp+87h] BYREF
  va_list va2; // [rsp+E0h] [rbp+87h]
  unsigned int *v113; // [rsp+E8h] [rbp+8Fh] BYREF
  va_list va3; // [rsp+E8h] [rbp+8Fh]
  va_list va4; // [rsp+F0h] [rbp+97h] BYREF

  va_start(va4, a2);
  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v107 = va_arg(va1, _DWORD *);
  va_copy(va2, va1);
  v109 = va_arg(va2, const char *);
  va_copy(va3, va2);
  v111 = va_arg(va3, char *);
  va_copy(va4, va3);
  v113 = va_arg(va4, unsigned int *);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, a1, a2);
  }
  v100 = 7168;
  v105 = 0;
  DuplicateTokenHandle = 0;
  v3 = 0;
  v4 = (char *)LocalAlloc(0x40u, 0x1C00u);
  if ( v4 )
  {
    *((_DWORD *)v4 + 1) = a2;
    v5 = v4;
    *((_DWORD *)v4 + 2) = 8;
    v102 = 0;
    v98 = 0;
    v105 = 0;
    v104 = 0;
    va_copy((va_list)v101, va);
    switch ( a2 )
    {
      case 0xCu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v23 = (unsigned int *)v109;
        v24 = v107;
        v102 = (char *)v109;
        va_copy((va_list)v101, va3);
        v98 = v111;
        if ( !v111 )
          *(_DWORD *)v109 = 0;
        if ( !*v23 )
          goto LABEL_71;
        v25 = AllocateBuffer(*v23, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 18;
LABEL_67:
          WPP_SF_d(v26[2], v27, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v25);
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
        *((_DWORD *)v5 + 6) = *v23;
        *(_OWORD *)(v5 + 28) = *v24;
        goto LABEL_4;
      case 0x15u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v28 = v107;
        v102 = (char *)v107;
        va_copy((va_list)v101, va2);
        v98 = (char *)v109;
        if ( !v109 )
          *v107 = 0;
        if ( !*v28 )
          goto LABEL_86;
        v25 = AllocateBuffer(*v28, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 20;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_86:
        *((_DWORD *)v5 + 7) = *v28;
        goto LABEL_4;
      case 0x16u:
      case 0x30u:
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_201;
        }
        v30 = 21;
        goto LABEL_200;
      case 0x49u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v31 = (int)v107;
        pszSrc = v109;
        v98 = v111;
        va_copy((va_list)v101, va4);
        v32 = v113;
        v102 = (char *)v113;
        if ( !v111 )
          *v113 = 0;
        if ( !*v32 )
          goto LABEL_105;
        v25 = AllocateBuffer(*v32, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 23;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_105:
        v33 = pszSrc;
        *(_DWORD *)v5 = v31;
        StringCchCopyA(v5 + 28, 0x10u, v33);
        *((_DWORD *)v5 + 11) = *v32;
        goto LABEL_4;
      case 0x5Eu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v34 = v111;
        LODWORD(pszSrc) = (_DWORD)v107;
        v104 = (unsigned int)v109;
        va_copy((va_list)v101, va3);
        v35 = (unsigned int)v109;
        v98 = v111;
        v25 = AllocateBuffer((unsigned int)v109, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 25;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
        *((_DWORD *)v5 + 9) = (_DWORD)pszSrc;
        *((_DWORD *)v5 + 8) = v35;
        memcpy_0(v5 + 40, v34, v35);
        goto LABEL_4;
      case 0x5Fu:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v36 = v107;
        v37 = (unsigned int *)v109;
        v105 = v107;
        v102 = (char *)v109;
        va_copy((va_list)v101, va3);
        v98 = v111;
        if ( !v111 )
          *(_DWORD *)v109 = 0;
        if ( !*v37 )
          goto LABEL_132;
        v25 = AllocateBuffer(*v37, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 29;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_132:
        *((_DWORD *)v5 + 7) = *v36;
        *((_DWORD *)v5 + 8) = *v37;
        goto LABEL_4;
      case 0x67u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v38 = (unsigned int *)v109;
        v39 = (int)v107;
        v102 = (char *)v109;
        va_copy((va_list)v101, va3);
        v98 = v111;
        if ( !v111 )
          *(_DWORD *)v109 = 0;
        if ( !*v38 )
          goto LABEL_147;
        v25 = AllocateBuffer(*v38, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 31;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
LABEL_147:
        *(_DWORD *)v5 = v39;
        *((_DWORD *)v5 + 7) = *v38;
        goto LABEL_4;
      case 0x68u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v40 = (int)v107;
        *(_DWORD *)v4 = 0;
        *((_DWORD *)v4 + 7) = v40;
        goto LABEL_202;
      case 0x69u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
        }
        v41 = (unsigned int *)v109;
        v42 = v107;
        va_copy((va_list)v101, va3);
        v102 = (char *)v109;
        v98 = v111;
        if ( !v111 )
          *(_DWORD *)v109 = 0;
        if ( !*v41 )
          goto LABEL_167;
        v25 = AllocateBuffer(*v41, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 34;
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
        v43 = v5 + 52;
        v44 = *v41;
        if ( a1 )
        {
          v47 = *(_DWORD *)(a1 + 12);
          *((_DWORD *)v5 + 8) = v44;
          if ( v47 != 6 )
          {
            *(_OWORD *)v43 = *(_OWORD *)v42;
            *(_OWORD *)(v5 + 68) = *((_OWORD *)v42 + 1);
            *(_OWORD *)(v5 + 84) = *((_OWORD *)v42 + 2);
            *(_OWORD *)(v5 + 100) = *((_OWORD *)v42 + 3);
            *(_OWORD *)(v5 + 116) = *((_OWORD *)v42 + 4);
            *(_OWORD *)(v5 + 132) = *((_OWORD *)v42 + 5);
            *(_OWORD *)(v5 + 148) = *((_OWORD *)v42 + 6);
            *(_OWORD *)(v5 + 164) = *((_OWORD *)v42 + 7);
            *(_OWORD *)(v5 + 180) = *((_OWORD *)v42 + 8);
            *(_OWORD *)(v5 + 196) = *((_OWORD *)v42 + 9);
            *(_OWORD *)(v5 + 212) = *((_OWORD *)v42 + 10);
            *(_OWORD *)(v5 + 228) = *((_OWORD *)v42 + 11);
            *(_OWORD *)(v5 + 244) = *((_OWORD *)v42 + 12);
            *((_DWORD *)v5 + 65) = v42[52];
            goto LABEL_4;
          }
        }
        else
        {
          *((_DWORD *)v5 + 8) = v44;
        }
        v45 = 3;
        do
        {
          v43 += 128;
          v46 = *(_OWORD *)v42;
          v42 += 32;
          *((_OWORD *)v43 - 8) = v46;
          *((_OWORD *)v43 - 7) = *((_OWORD *)v42 - 7);
          *((_OWORD *)v43 - 6) = *((_OWORD *)v42 - 6);
          *((_OWORD *)v43 - 5) = *((_OWORD *)v42 - 5);
          *((_OWORD *)v43 - 4) = *((_OWORD *)v42 - 4);
          *((_OWORD *)v43 - 3) = *((_OWORD *)v42 - 3);
          *((_OWORD *)v43 - 2) = *((_OWORD *)v42 - 2);
          *((_OWORD *)v43 - 1) = *((_OWORD *)v42 - 1);
          --v45;
        }
        while ( v45 );
        *(_OWORD *)v43 = *(_OWORD *)v42;
        *((_OWORD *)v43 + 1) = *((_OWORD *)v42 + 1);
        *((_OWORD *)v43 + 2) = *((_OWORD *)v42 + 2);
        *((_OWORD *)v43 + 3) = *((_OWORD *)v42 + 3);
        *((_OWORD *)v43 + 4) = *((_OWORD *)v42 + 4);
        *((_QWORD *)v43 + 10) = *((_QWORD *)v42 + 10);
LABEL_4:
        v6 = v100;
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
                v58 = GetLastError();
                v11 = v58;
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(g_dwTraceId, 0xCu, "PutRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x", v58);
              }
            }
            else
            {
              v57 = GetLastError();
              v11 = v57;
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "PutRequestInQueue: DuplicateToken Failed 0x%.8x", v57);
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
            v60 = v9;
            v59 = &_ImageBase;
            switch ( a2 )
            {
              case 0xCu:
              case 0x15u:
                v66 = (PVOID *)WPP_GLOBAL_Control;
                v59 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v66 = (PVOID *)WPP_GLOBAL_Control;
                  v59 = (__int16 *)&WPP_GLOBAL_Control;
                }
                v67 = v102;
                v68 = *((_DWORD *)v5 + 7);
                v69 = *v101;
                if ( *(_DWORD *)v102 < v68 )
                {
                  v11 = 603;
                  if ( v66 != &WPP_GLOBAL_Control && (*((_BYTE *)v66 + 28) & 0x40) != 0 && *((_BYTE *)v66 + 25) >= 2u )
                  {
                    v70 = 42;
                    goto LABEL_239;
                  }
                }
                else
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( v11
                    && v66 != &WPP_GLOBAL_Control
                    && (*((_BYTE *)v66 + 28) & 0x40) != 0
                    && *((_BYTE *)v66 + 25) >= 2u )
                  {
                    v70 = 41;
LABEL_239:
                    WPP_SF_d(v66[2], v70, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                    *(_DWORD *)v67 = *((_DWORD *)v5 + 7);
                    *(_DWORD *)v69 = *((_DWORD *)v5 + 8);
                    goto LABEL_24;
                  }
                }
                *(_DWORD *)v102 = v68;
                *(_DWORD *)v69 = *((_DWORD *)v5 + 8);
                if ( v11 )
                  goto LABEL_24;
                v71 = v5 + 36;
                goto LABEL_247;
              case 0x16u:
                v61 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v61 = (PVOID *)WPP_GLOBAL_Control;
                }
                v16 = *v101;
                v11 = *((_DWORD *)v4 + 6);
                if ( v11
                  && v61 != &WPP_GLOBAL_Control
                  && (*((_BYTE *)v61 + 28) & 0x40) != 0
                  && *((_BYTE *)v61 + 25) >= 2u )
                {
                  WPP_SF_d(v61[2], 44, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                }
                v62 = v16;
                v63 = v4 + 32;
                v64 = 7;
                do
                {
                  v62 += 128;
                  v65 = *(_OWORD *)v63;
                  v63 += 128;
                  *((_OWORD *)v62 - 8) = v65;
                  *((_OWORD *)v62 - 7) = *((_OWORD *)v63 - 7);
                  *((_OWORD *)v62 - 6) = *((_OWORD *)v63 - 6);
                  *((_OWORD *)v62 - 5) = *((_OWORD *)v63 - 5);
                  *((_OWORD *)v62 - 4) = *((_OWORD *)v63 - 4);
                  *((_OWORD *)v62 - 3) = *((_OWORD *)v63 - 3);
                  *((_OWORD *)v62 - 2) = *((_OWORD *)v63 - 2);
                  *((_OWORD *)v62 - 1) = *((_OWORD *)v63 - 1);
                  --v64;
                }
                while ( v64 );
                *(_OWORD *)v62 = *(_OWORD *)v63;
                *((_QWORD *)v62 + 2) = *((_QWORD *)v63 + 2);
                *((_DWORD *)v16 + 83) = *((_DWORD *)v16 + 83) == GetCurrentProcessId();
                goto LABEL_25;
              case 0x30u:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                }
                *(_QWORD *)*v101 = *((_QWORD *)v4 + 4);
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
                v74 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v74 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( v11 )
                {
                  if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 0x40) != 0 && *((_BYTE *)v74 + 25) >= 2u )
                    WPP_SF_d(v74[2], 48, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  v75 = v102;
                }
                else
                {
                  v75 = v102;
                  if ( *((_DWORD *)v5 + 11) <= *(_DWORD *)v102 )
                  {
                    memcpy_0(v98, v5 + 48, *((unsigned int *)v5 + 11));
                  }
                  else
                  {
                    v11 = 603;
                    if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 0x40) != 0 && *((_BYTE *)v74 + 25) >= 2u )
                      WPP_SF_d(v74[2], 49, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 603);
                  }
                }
                *(_DWORD *)v75 = *((_DWORD *)v5 + 11);
                goto LABEL_24;
              case 0x5Eu:
                v76 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v76 = (PVOID *)WPP_GLOBAL_Control;
                }
                v11 = *((_DWORD *)v5 + 6);
                if ( !v11 )
                  goto LABEL_24;
                v59 = (__int16 *)*((unsigned int *)v5 + 8);
                if ( (unsigned int)v59 <= v104 )
                {
                  v16 = v98;
                  memcpy_0(v98, v5 + 40, *((unsigned int *)v5 + 8));
                  goto LABEL_25;
                }
                v11 = 603;
                if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 0x40) != 0 && *((_BYTE *)v76 + 25) >= 2u )
                {
                  v77 = v76[2];
                  v21 = 51;
                  goto LABEL_412;
                }
                goto LABEL_24;
              case 0x5Fu:
                v78 = (PVOID *)WPP_GLOBAL_Control;
                v59 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v78 = (PVOID *)WPP_GLOBAL_Control;
                  v59 = (__int16 *)&WPP_GLOBAL_Control;
                }
                v67 = v102;
                v79 = *v101;
                if ( *(_DWORD *)v102 < *((_DWORD *)v5 + 8) )
                {
                  v11 = 603;
                  if ( v78 != &WPP_GLOBAL_Control && (*((_BYTE *)v78 + 28) & 0x40) != 0 && *((_BYTE *)v78 + 25) >= 2u )
                  {
                    v80 = 55;
                    goto LABEL_303;
                  }
                }
                else
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( v11
                    && v78 != &WPP_GLOBAL_Control
                    && (*((_BYTE *)v78 + 28) & 0x40) != 0
                    && *((_BYTE *)v78 + 25) >= 2u )
                  {
                    v80 = 54;
LABEL_303:
                    WPP_SF_d(v78[2], v80, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  }
                }
                v81 = v105;
                *v79 = *((_DWORD *)v5 + 9);
                *(_DWORD *)v67 = *((_DWORD *)v5 + 8);
                *v81 = *((_DWORD *)v5 + 7);
                if ( v11 )
                  goto LABEL_24;
                v71 = v5 + 40;
LABEL_247:
                v72 = *(unsigned int *)v67;
                v16 = v98;
                v73 = v98;
LABEL_249:
                memcpy_0(v73, v71, v72);
                goto LABEL_25;
              case 0x67u:
                v15 = (PVOID *)WPP_GLOBAL_Control;
                v59 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v15 = (PVOID *)WPP_GLOBAL_Control;
                  v59 = (__int16 *)&WPP_GLOBAL_Control;
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
                v82 = v102;
                if ( *(_DWORD *)v102 >= v20 )
                {
                  v11 = *((_DWORD *)v5 + 6);
                  if ( !v11
                    || v15 == &WPP_GLOBAL_Control
                    || (*((_BYTE *)v15 + 28) & 0x40) == 0
                    || *((_BYTE *)v15 + 25) < 2u )
                  {
                    v84 = *(unsigned int *)v102;
                    *(_DWORD *)v102 = v20;
                    if ( !v11 )
                    {
                      v16 = v98;
                      if ( v98 )
                      {
                        v85 = (unsigned int *)(v5 + 32);
                        v86 = ValidateRasTapiInfo(v5 + 32, *((unsigned int *)v5 + 7), v10, v84);
                        v11 = v86;
                        if ( v86 )
                        {
                          v87 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v88 = 60;
                            v89 = v86;
LABEL_329:
                            WPP_SF_d(v87[2], v88, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v89);
                          }
                        }
                        else
                        {
                          v90 = *v85;
                          *(_DWORD *)v98 = *v85;
                          *((_DWORD *)v98 + 4) = *((_DWORD *)v5 + 10);
                          *((_DWORD *)v98 + 8) = *((_DWORD *)v5 + 12);
                          *((_DWORD *)v98 + 12) = *((_DWORD *)v5 + 14);
                          if ( v90 )
                          {
                            *((_QWORD *)v98 + 1) = v98 + 64;
                            memcpy_0(v98 + 64, (char *)v85 + *((unsigned int *)v5 + 9), *v85);
                          }
                          else
                          {
                            *((_QWORD *)v98 + 1) = 0;
                          }
                          if ( *((_DWORD *)v98 + 4) )
                          {
                            v91 = &v98[((*(_DWORD *)v98 + 7) & 0xFFFFFFF8) + 64];
                            *((_QWORD *)v98 + 3) = v91;
                            memcpy_0(v91, (char *)v85 + *((unsigned int *)v5 + 11), *((unsigned int *)v5 + 10));
                          }
                          else
                          {
                            *((_QWORD *)v98 + 3) = 0;
                          }
                          if ( *((_DWORD *)v98 + 8) )
                          {
                            v92 = &v98[((*(_DWORD *)v98 + 7) & 0xFFFFFFF8)
                                     + 64
                                     + ((*((_DWORD *)v98 + 4) + 7) & 0xFFFFFFF8)];
                            *((_QWORD *)v98 + 5) = v92;
                            memcpy_0(v92, (char *)v85 + *((unsigned int *)v5 + 13), *((unsigned int *)v5 + 12));
                          }
                          else
                          {
                            *((_QWORD *)v98 + 5) = 0;
                          }
                          if ( *((_DWORD *)v98 + 12) )
                          {
                            v73 = &v98[((*((_DWORD *)v98 + 4) + 7) & 0xFFFFFFF8)
                                     + 64
                                     + ((*((_DWORD *)v98 + 8) + 7) & 0xFFFFFFF8)
                                     + ((*(_DWORD *)v98 + 7) & 0xFFFFFFF8)];
                            *((_QWORD *)v98 + 7) = v73;
                            v72 = *((unsigned int *)v5 + 14);
                            v71 = (char *)v85 + *((unsigned int *)v5 + 15);
                            goto LABEL_249;
                          }
                          *((_QWORD *)v98 + 7) = 0;
                        }
                      }
                      goto LABEL_25;
                    }
LABEL_24:
                    v16 = v98;
LABEL_25:
                    if ( !v7 )
                      goto LABEL_33;
                    if ( v11 )
                      goto LABEL_33;
                    v17 = SanityFilterAfterRPC(v5, v59, a2, v16);
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
                  v83 = 59;
                }
                else
                {
                  v11 = 603;
                  if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 || *((_BYTE *)v15 + 25) < 2u )
                    goto LABEL_317;
                  v83 = 58;
                }
                WPP_SF_d(v15[2], v83, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
LABEL_317:
                *v82 = v20;
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
                  StringCchCopyA(*v101, 0x81u, v5 + 32);
                  goto LABEL_24;
                }
                if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 || *((_BYTE *)v15 + 25) < 2u )
                  goto LABEL_24;
                v21 = 62;
                goto LABEL_411;
              case 0x69u:
                v93 = (PVOID *)WPP_GLOBAL_Control;
                v59 = (__int16 *)&WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
                  v93 = (PVOID *)WPP_GLOBAL_Control;
                  v59 = (__int16 *)&WPP_GLOBAL_Control;
                }
                if ( !a1 || (v94 = *(_DWORD *)(a1 + 12) == 6, v95 = (unsigned int *)(v5 + 264), v94) )
                  v95 = (unsigned int *)(v5 + 524);
                v11 = *((_DWORD *)v5 + 6);
                if ( v11 )
                {
                  if ( v93 != &WPP_GLOBAL_Control && (*((_BYTE *)v93 + 28) & 0x40) != 0 && *((_BYTE *)v93 + 25) >= 2u )
                    WPP_SF_d(v93[2], 64, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  *(_DWORD *)v102 = *((_DWORD *)v5 + 8);
                  goto LABEL_24;
                }
                v96 = v102;
                v97 = *((_DWORD *)v5 + 8);
                if ( *(_DWORD *)v102 < v97 )
                {
                  v11 = 603;
                  if ( v93 != &WPP_GLOBAL_Control && (*((_BYTE *)v93 + 28) & 0x40) != 0 && *((_BYTE *)v93 + 25) >= 2u )
                  {
                    WPP_SF_d(v93[2], 65, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, 603);
                    *(_DWORD *)v96 = *((_DWORD *)v5 + 8);
                    goto LABEL_24;
                  }
                }
                *(_DWORD *)v102 = v97;
                if ( v11 )
                  goto LABEL_24;
                v16 = v98;
                if ( v98 )
                {
                  if ( *v95 <= *(_DWORD *)v98 )
                  {
                    memcpy_0(v98 + 4, v95 + 1, *v95);
                    *(_DWORD *)v98 = *v95;
                    goto LABEL_25;
                  }
                  v11 = 603;
                  v87 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v88 = 66;
                    v89 = 603;
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
                  *(_QWORD *)*v101 = *(_QWORD *)(v5 + 28);
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
                    v77 = v15[2];
LABEL_412:
                    WPP_SF_d(v77, v21, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, v11);
                  }
                }
                else
                {
                  StringCchCopyW((STRSAFE_LPWSTR)*v101, 0x81u, (STRSAFE_LPCWSTR)v5 + 14);
                }
                goto LABEL_24;
              default:
                v59 = v60;
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
        v48 = v109;
        v49 = v107;
        va_copy((va_list)v101, va3);
        v50 = *(_DWORD *)v109;
        LODWORD(pszSrc) = (_DWORD)v111;
        v25 = AllocateBuffer(v50, &DuplicateTokenHandle, &v100);
        v11 = v25;
        if ( v25 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v27 = 36;
          goto LABEL_67;
        }
        v3 = DuplicateTokenHandle;
        if ( DuplicateTokenHandle )
        {
          v5 = (char *)DuplicateTokenHandle;
          *((_DWORD *)DuplicateTokenHandle + 1) = a2;
        }
        v51 = v5 + 52;
        *((_DWORD *)v5 + 7) = (_DWORD)pszSrc;
        v52 = v48 + 4;
        *(_DWORD *)v5 = 0;
        if ( !a1 || *(_DWORD *)(a1 + 12) == 6 )
        {
          v53 = 3;
          do
          {
            v51 += 128;
            v54 = *(_OWORD *)v49;
            v49 += 32;
            *((_OWORD *)v51 - 8) = v54;
            *((_OWORD *)v51 - 7) = *((_OWORD *)v49 - 7);
            *((_OWORD *)v51 - 6) = *((_OWORD *)v49 - 6);
            *((_OWORD *)v51 - 5) = *((_OWORD *)v49 - 5);
            *((_OWORD *)v51 - 4) = *((_OWORD *)v49 - 4);
            *((_OWORD *)v51 - 3) = *((_OWORD *)v49 - 3);
            *((_OWORD *)v51 - 2) = *((_OWORD *)v49 - 2);
            *((_OWORD *)v51 - 1) = *((_OWORD *)v49 - 1);
            --v53;
          }
          while ( v53 );
          *(_OWORD *)v51 = *(_OWORD *)v49;
          *((_OWORD *)v51 + 1) = *((_OWORD *)v49 + 1);
          *((_OWORD *)v51 + 2) = *((_OWORD *)v49 + 2);
          *((_OWORD *)v51 + 3) = *((_OWORD *)v49 + 3);
          *((_OWORD *)v51 + 4) = *((_OWORD *)v49 + 4);
          *((_QWORD *)v51 + 10) = *((_QWORD *)v49 + 10);
          memcpy_0(v5 + 528, v52, *(unsigned int *)v48);
          *((_DWORD *)v5 + 131) = *(_DWORD *)v48;
        }
        else
        {
          *(_OWORD *)v51 = *(_OWORD *)v49;
          *(_OWORD *)(v5 + 68) = *((_OWORD *)v49 + 1);
          *(_OWORD *)(v5 + 84) = *((_OWORD *)v49 + 2);
          *(_OWORD *)(v5 + 100) = *((_OWORD *)v49 + 3);
          *(_OWORD *)(v5 + 116) = *((_OWORD *)v49 + 4);
          *(_OWORD *)(v5 + 132) = *((_OWORD *)v49 + 5);
          *(_OWORD *)(v5 + 148) = *((_OWORD *)v49 + 6);
          *(_OWORD *)(v5 + 164) = *((_OWORD *)v49 + 7);
          *(_OWORD *)(v5 + 180) = *((_OWORD *)v49 + 8);
          *(_OWORD *)(v5 + 196) = *((_OWORD *)v49 + 9);
          *(_OWORD *)(v5 + 212) = *((_OWORD *)v49 + 10);
          *(_OWORD *)(v5 + 228) = *((_OWORD *)v49 + 11);
          *(_OWORD *)(v5 + 244) = *((_OWORD *)v49 + 12);
          *((_DWORD *)v5 + 65) = v49[52];
          memcpy_0(v5 + 268, v52, *(unsigned int *)v48);
          *((_DWORD *)v5 + 66) = *(_DWORD *)v48;
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
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_201;
        }
        v30 = 38;
LABEL_200:
        WPP_SF_(v29[2], v30, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids);
LABEL_201:
        *(_DWORD *)v4 = (_DWORD)v107;
LABEL_202:
        va_copy((va_list)v101, va1);
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
0x180011b40  mov     [rsp-8+arg_8], dx
0x180011b45  mov     [rsp-8+arg_10], r8
0x180011b4a  mov     [rsp-8+arg_18], r9
0x180011b4f  push    rbp
0x180011b50  push    rbx
0x180011b51  push    rsi
0x180011b52  push    rdi
0x180011b53  push    r14
0x180011b55  push    r15
0x180011b57  lea     rbp, [rsp-2Fh]
0x180011b5c  sub     rsp, 88h
0x180011b63  mov     r15, rcx
0x180011b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b6d  lea     rsi, WPP_GLOBAL_Control
0x180011b74  cmp     rcx, rsi
0x180011b77  jnz     loc_180011DFE
0x180011b7d  xor     r14d, r14d
0x180011b80  mov     [rbp+57h+var_70], 1C00h
0x180011b87  mov     edx, 1C00h; uBytes
0x180011b8c  mov     [rbp+57h+var_48], r14
0x180011b90  mov     ecx, 40h ; '@'; uFlags
0x180011b95  mov     [rbp+57h+DuplicateTokenHandle], r14
0x180011b99  mov     edi, r14d
0x180011b9c  call    cs:__imp_LocalAlloc
0x180011ba2  mov     rbx, rax
0x180011ba5  test    rax, rax
0x180011ba8  jz      loc_180011E36
0x180011bae  movzx   eax, [rbp+57h+arg_8]
0x180011bb2  lea     rsi, [rbp+57h+arg_10]
0x180011bb6  mov     [rbx+4], eax
0x180011bb9  lea     rdx, __ImageBase
0x180011bc0  mov     [rsp+0B0h+var_30], r12
0x180011bc8  mov     r12, rbx
0x180011bcb  mov     dword ptr [rbx+8], 8
0x180011bd2  movzx   eax, [rbp+57h+arg_8]
0x180011bd6  add     eax, 0FFFFFFF4h; switch 114 cases
0x180011bd9  mov     [rsp+0B0h+var_38], r13
0x180011bde  mov     [rbp+57h+var_60], r14
0x180011be2  mov     [rbp+57h+var_80], r14
0x180011be6  mov     [rbp+57h+var_48], r14
0x180011bea  mov     [rbp+57h+var_50], r14d
0x180011bee  mov     [rbp+57h+var_68], rsi
0x180011bf2  cmp     eax, 71h
0x180011bf5  jbe     loc_180011EB5
0x180011bfb  mov     r14d, [rbp+57h+var_70]; jumptable 0000000180011EC9 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x180011bff  xor     r13d, r13d
0x180011c02  cmp     cs:g_fRasmanService, r13d
0x180011c09  mov     [rbp+57h+pszSrc], r13
0x180011c0d  mov     [rbp+57h+DuplicateTokenHandle], r13
0x180011c11  jnz     short loc_180011C83
0x180011c13  mov     r8d, r14d
0x180011c16  mov     rdx, r12
0x180011c19  mov     rcx, r15
0x180011c1c  call    RemoteSubmitRequest
0x180011c21  mov     r13d, 1
0x180011c27  mov     esi, eax
0x180011c29  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x180011c2d  test    rcx, rcx
0x180011c30  jnz     loc_180012A51
0x180011c36  mov     rcx, [rbp+57h+pszSrc]; hObject
0x180011c3a  test    rcx, rcx
0x180011c3d  jnz     loc_180012A5C
0x180011c43  test    esi, esi
0x180011c45  jz      loc_180011CD3
0x180011c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c52  lea     r15, WPP_GLOBAL_Control
0x180011c59  cmp     rcx, r15
0x180011c5c  jz      loc_180011D5A
0x180011c62  test    byte ptr [rcx+1Ch], 40h
0x180011c66  jz      loc_180011D5A
0x180011c6c  cmp     byte ptr [rcx+19h], 2
0x180011c70  jb      loc_180011D5A
0x180011c76  mov     edx, 27h ; '''
0x180011c7b  mov     r9d, esi
0x180011c7e  jmp     loc_180011D4A
0x180011c83  mov     rax, cs:g_fnRasmanServiceInitialized
0x180011c8a  test    rax, rax
0x180011c8d  jz      short loc_180011C13
0x180011c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c94  test    rax, rax
0x180011c97  jz      loc_180011C13
0x180011c9d  cmp     cs:g_fnServiceRequest, r13
0x180011ca4  jz      loc_180012A47
0x180011caa  mov     eax, gs:179Ch
0x180011cb2  xor     esi, esi
0x180011cb4  test    eax, eax
0x180011cb6  jnz     loc_180012942
0x180011cbc  mov     rax, cs:g_fnServiceRequest
0x180011cc3  mov     edx, r14d
0x180011cc6  mov     rcx, r12
0x180011cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cce  jmp     loc_180011C29
0x180011cd3  movzx   eax, [rbp+57h+arg_8]
0x180011cd7  add     eax, 0FFFFFFF4h; switch 114 cases
0x180011cda  cmp     eax, 71h
0x180011cdd  jbe     loc_180012A67
0x180011ce3  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180012A82 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x180011cea  lea     r15, WPP_GLOBAL_Control
0x180011cf1  cmp     rcx, r15
0x180011cf4  jnz     loc_1800134F5
0x180011cfa  mov     esi, [r12+18h]
0x180011cff  test    esi, esi
0x180011d01  jnz     loc_18001352A
0x180011d07  mov     r14, [rbp+57h+var_80]
0x180011d0b  test    r13d, r13d
0x180011d0e  jz      short loc_180011D5A
0x180011d10  test    esi, esi
0x180011d12  jnz     short loc_180011D5A
0x180011d14  movzx   r8d, [rbp+57h+arg_8]
0x180011d19  mov     r9, r14
0x180011d1c  mov     rcx, r12
0x180011d1f  call    SanityFilterAfterRPC
0x180011d24  mov     esi, eax
0x180011d26  test    eax, eax
0x180011d28  jz      short loc_180011D5A
0x180011d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d31  cmp     rcx, r15
0x180011d34  jz      short loc_180011D5A
0x180011d36  test    byte ptr [rcx+1Ch], 40h
0x180011d3a  jz      short loc_180011D5A
0x180011d3c  cmp     byte ptr [rcx+19h], 2
0x180011d40  jb      short loc_180011D5A
0x180011d42  mov     edx, 4Ch ; 'L'
0x180011d47  mov     r9d, eax
0x180011d4a  mov     rcx, [rcx+10h]
0x180011d4e  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011d55  call    WPP_SF_d
0x180011d5a  mov     r13, [rsp+0B0h+var_38]
0x180011d5f  mov     r12, [rsp+0B0h+var_30]
0x180011d67  test    rdi, rdi
0x180011d6a  jnz     loc_180013564
0x180011d70  mov     rcx, rbx; hMem
0x180011d73  call    cs:__imp_LocalFree
0x180011d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d80  cmp     rcx, r15
0x180011d83  jnz     loc_180013572
0x180011d89  mov     eax, esi
0x180011d8b  add     rsp, 88h
0x180011d92  pop     r15
0x180011d94  pop     r14
0x180011d96  pop     rdi
0x180011d97  pop     rsi
0x180011d98  pop     rbx
0x180011d99  pop     rbp
0x180011d9a  retn
0x180011d9b  cmp     rcx, rsi
0x180011d9e  jnz     loc_180011E81
0x180011da4  mov     eax, 8007000Eh
0x180011da9  add     rsp, 88h
0x180011db0  pop     r15
0x180011db2  pop     r14
0x180011db4  pop     rdi
0x180011db5  pop     rsi
0x180011db6  pop     rbx
0x180011db7  pop     rbp
0x180011db8  retn
0x180011db9  mov     eax, [r12+1Ch]
0x180011dbe  lea     r15d, [rax+24h]
0x180011dc2  cmp     r15d, eax
0x180011dc5  jnb     loc_18001300C
0x180011dcb  mov     esi, 57h ; 'W'
0x180011dd0  lea     r15, WPP_GLOBAL_Control
0x180011dd7  cmp     rcx, r15
0x180011dda  jz      loc_180011D07
0x180011de0  test    byte ptr [rcx+1Ch], 40h
0x180011de4  jz      loc_180011D07
0x180011dea  cmp     byte ptr [rcx+19h], 2
0x180011dee  jb      loc_180011D07
0x180011df4  mov     edx, 39h ; '9'
0x180011df9  jmp     loc_18001354C
0x180011dfe  test    byte ptr [rcx+1Ch], 40h
0x180011e02  jz      loc_180011B7D
0x180011e08  cmp     byte ptr [rcx+19h], 6
0x180011e0c  jb      loc_180011B7D
0x180011e12  mov     rcx, [rcx+10h]
0x180011e16  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011e1d  movzx   eax, dx
0x180011e20  mov     r9, r15
0x180011e23  mov     edx, 0Eh
0x180011e28  mov     [rsp+0B0h+var_90], eax
0x180011e2c  call    WPP_SF_qd
0x180011e31  jmp     loc_180011B7D
0x180011e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e3d  cmp     rcx, rsi
0x180011e40  jz      loc_180011DA4
0x180011e46  test    byte ptr [rcx+1Ch], 40h
0x180011e4a  jz      loc_180011D9B
0x180011e50  cmp     byte ptr [rcx+19h], 2
0x180011e54  jb      loc_180011D9B
0x180011e5a  mov     rcx, [rcx+10h]
0x180011e5e  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011e65  mov     edx, 0Fh
0x180011e6a  mov     r9d, 8007000Eh
0x180011e70  call    WPP_SF_d
0x180011e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e7c  jmp     loc_180011D9B
0x180011e81  test    byte ptr [rcx+1Ch], 40h
0x180011e85  jz      loc_180011DA4
0x180011e8b  cmp     byte ptr [rcx+19h], 6
0x180011e8f  jb      loc_180011DA4
0x180011e95  mov     rcx, [rcx+10h]
0x180011e99  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011ea0  mov     edx, 10h
0x180011ea5  mov     r9d, 8007000Eh
0x180011eab  call    WPP_SF_d
0x180011eb0  jmp     loc_180011DA4
0x180011eb5  cdqe
0x180011eb7  movzx   eax, ds:(byte_1800135D8 - 180000000h)[rdx+rax]
0x180011ebf  mov     ecx, ds:(jpt_180011EC9 - 180000000h)[rdx+rax*4]
0x180011ec6  add     rcx, rdx
0x180011ec9  jmp     rcx; switch jump
0x180011ecb  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180011EC9 case 12
0x180011ed2  lea     rax, WPP_GLOBAL_Control
0x180011ed9  cmp     rcx, rax
0x180011edc  jz      short loc_180011EFF
0x180011ede  test    byte ptr [rcx+1Ch], 40h
0x180011ee2  jz      short loc_180011EFF
0x180011ee4  cmp     byte ptr [rcx+19h], 5
0x180011ee8  jb      short loc_180011EFF
0x180011eea  mov     rcx, [rcx+10h]
0x180011eee  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011ef5  mov     edx, 11h
0x180011efa  call    WPP_SF_
0x180011eff  mov     r13, [rsi+8]
0x180011f03  mov     r11, [rsi+10h]
0x180011f07  mov     r14, [rsi]
0x180011f0a  add     rsi, 18h
0x180011f0e  mov     [rbp+57h+var_60], r13
0x180011f12  mov     [rbp+57h+var_68], rsi
0x180011f16  mov     [rbp+57h+var_80], r11
0x180011f1a  test    r11, r11
0x180011f1d  jnz     short loc_180011F23
0x180011f1f  mov     [r13+0], edi
0x180011f23  mov     ecx, [r13+0]
0x180011f27  test    ecx, ecx
0x180011f29  jz      short loc_180011F98
0x180011f2b  lea     r8, [rbp+57h+var_70]
0x180011f2f  lea     rdx, [rbp+57h+DuplicateTokenHandle]
0x180011f33  call    AllocateBuffer
0x180011f38  mov     esi, eax
0x180011f3a  test    eax, eax
0x180011f3c  jz      short loc_180011F85
0x180011f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f45  lea     r15, WPP_GLOBAL_Control
0x180011f4c  cmp     rcx, r15
0x180011f4f  jz      short loc_180011F7C
0x180011f51  test    byte ptr [rcx+1Ch], 40h
0x180011f55  jz      short loc_180011F7C
0x180011f57  cmp     byte ptr [rcx+19h], 2
0x180011f5b  jb      short loc_180011F7C
0x180011f5d  mov     edx, 12h
0x180011f62  jmp     short loc_180011F69
0x180011f64  mov     edx, 24h ; '$'
0x180011f69  mov     rcx, [rcx+10h]
0x180011f6d  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011f74  mov     r9d, eax
0x180011f77  call    WPP_SF_d
0x180011f7c  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x180011f80  jmp     loc_180011D5A
0x180011f85  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x180011f89  test    rdi, rdi
0x180011f8c  jz      short loc_180011F98
0x180011f8e  movzx   eax, [rbp+57h+arg_8]
0x180011f92  mov     r12, rdi
0x180011f95  mov     [rdi+4], eax
0x180011f98  mov     eax, [r13+0]
0x180011f9c  mov     [r12+18h], eax
0x180011fa1  movups  xmm0, xmmword ptr [r14]
0x180011fa5  movups  xmmword ptr [r12+1Ch], xmm0
0x180011fab  jmp     def_180011EC9; jumptable 0000000180011EC9 default case, cases 13-20,23-47,49-72,74-93,96-102,107-110,112-124
0x180011fb0  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180011EC9 case 21
0x180011fb7  lea     rax, WPP_GLOBAL_Control
0x180011fbe  cmp     rcx, rax
0x180011fc1  jz      short loc_180011FE4
0x180011fc3  test    byte ptr [rcx+1Ch], 40h
0x180011fc7  jz      short loc_180011FE4
0x180011fc9  cmp     byte ptr [rcx+19h], 5
0x180011fcd  jb      short loc_180011FE4
0x180011fcf  mov     rcx, [rcx+10h]
0x180011fd3  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180011fda  mov     edx, 13h
0x180011fdf  call    WPP_SF_
0x180011fe4  mov     r13, [rsi]
0x180011fe7  add     rsi, 10h
0x180011feb  mov     [rbp+57h+var_60], r13
0x180011fef  mov     [rbp+57h+var_68], rsi
0x180011ff3  mov     r11, [rsi-8]
0x180011ff7  mov     [rbp+57h+var_80], r11
0x180011ffb  test    r11, r11
0x180011ffe  jnz     short loc_180012004
0x180012000  mov     [r13+0], r14d
0x180012004  mov     ecx, [r13+0]
0x180012008  test    ecx, ecx
0x18001200a  jz      short loc_180012067
0x18001200c  lea     r8, [rbp+57h+var_70]
0x180012010  lea     rdx, [rbp+57h+DuplicateTokenHandle]
0x180012014  call    AllocateBuffer
0x180012019  mov     esi, eax
0x18001201b  test    eax, eax
0x18001201d  jz      short loc_180012054
  ... truncated ...
```
