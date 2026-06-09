# CJob::CheckClientAccess(ulong,ulong *,bool *)

- ea: `0x18000d1f0`
- end: `0x18000db10`
- name: `?CheckClientAccess@CJob@@QEBAJKPEAKPEA_N@Z`
- size: `2336`
- prototype: `int(CJob *__hidden this, unsigned int, unsigned int *, bool *)`
- caller_count: `37`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009d48`
- `0x18000a24c`
- `0x18000a544`
- `0x18000ace0`
- `0x18000b1f0`
- `0x18000b640`
- `0x18000bf90`
- `0x18000c770`
- `0x180030480`
- `0x180059bd4`
- `0x18005fe4c`
- `0x1800606e4`
- `0x18006089c`
- `0x180068880`
- `0x180069204`
- `0x18006c12c`
- `0x180070038`
- `0x180077d24`
- `0x180078060`
- `0x180079058`
- `0x18007cb80`
- `0x18008030c`
- `0x180080678`
- `0x1800894b4`
- `0x1800c86d0`
- `0x1800c8a68`
- `0x1800c8f50`
- `0x1800c90f0`
- `0x1800c9360`
- `0x1800c9500`
- `0x1800c9740`
- `0x1800ca02c`
- `0x1800ca170`
- `0x1800ca520`
- `0x1800ca670`
- `0x1800ca8ec`
- `0x1800cbe68`

## callees

- `0x180006640`
- `0x18000d1f0`
- `0x18000dcb0`
- `0x18000e5c0`
- `0x18000e790`
- `0x180019a30`
- `0x1800856b8`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800ab7b0`
- `0x1800acacc`
- `0x1800b8b70`
- `0x1800c656c`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d8b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d8e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d8b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d8e0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d51f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d5a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d51f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6cd`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000d250`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000d250`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d84c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d84c`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000d74d`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000d74d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d2f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d4f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d2f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d4f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CJob::CheckClientAccess(CJob *this, DWORD a2, unsigned int *a3, bool *a4)
{
  AppPackageInfo *v6; // rdi
  unsigned int *v7; // rbx
  int v8; // eax
  AppPackageInfo *v9; // rax
  AppPackageInfo *v10; // rbx
  const char *v11; // r9
  __int64 v12; // r12
  char v13; // r12
  volatile signed __int32 *v14; // rcx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  void *v17; // rcx
  void *v19; // rcx
  void *v20; // rcx
  __int64 *PackageInfoFromToken; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  PSID *v24; // r15
  BOOL v25; // eax
  unsigned int v26; // esi
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // r8
  __int64 v29; // rdx
  AppPackageInfo *v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx
  unsigned int LastError; // eax
  unsigned int v34; // eax
  unsigned int TokenInformation; // [rsp+30h] [rbp-428h] BYREF
  DWORD ReturnLength[2]; // [rsp+38h] [rbp-420h] BYREF
  DWORD AccessMask[4]; // [rsp+40h] [rbp-418h] BYREF
  int v38; // [rsp+50h] [rbp-408h] BYREF
  void *v39; // [rsp+58h] [rbp-400h] BYREF
  char v40; // [rsp+60h] [rbp-3F8h]
  void *v41; // [rsp+68h] [rbp-3F0h]
  void *v42; // [rsp+70h] [rbp-3E8h]
  void *v43; // [rsp+78h] [rbp-3E0h]
  __int64 v44; // [rsp+80h] [rbp-3D8h]
  void *v45; // [rsp+88h] [rbp-3D0h]
  int v46; // [rsp+90h] [rbp-3C8h] BYREF
  AppPackageInfo *v47; // [rsp+98h] [rbp-3C0h] BYREF
  char v48[16]; // [rsp+A0h] [rbp-3B8h] BYREF
  void **pExceptionObject; // [rsp+B0h] [rbp-3A8h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-3A0h]
  int v51; // [rsp+C8h] [rbp-390h]
  int v52; // [rsp+CCh] [rbp-38Ch]
  int v53; // [rsp+D0h] [rbp-388h]
  void **v54; // [rsp+110h] [rbp-348h] BYREF
  __int128 v55; // [rsp+118h] [rbp-340h]
  int v56; // [rsp+128h] [rbp-330h]
  int v57; // [rsp+12Ch] [rbp-32Ch]
  int v58; // [rsp+130h] [rbp-328h]
  void **v59; // [rsp+170h] [rbp-2E8h] BYREF
  __int128 v60; // [rsp+178h] [rbp-2E0h]
  unsigned int v61; // [rsp+188h] [rbp-2D0h]
  int v62; // [rsp+18Ch] [rbp-2CCh]
  int v63; // [rsp+190h] [rbp-2C8h]
  void **v64; // [rsp+1D0h] [rbp-288h] BYREF
  __int128 v65; // [rsp+1D8h] [rbp-280h]
  int v66; // [rsp+1E8h] [rbp-270h]
  int v67; // [rsp+1ECh] [rbp-26Ch]
  int v68; // [rsp+1F0h] [rbp-268h]
  void **v69; // [rsp+230h] [rbp-228h] BYREF
  __int128 v70; // [rsp+238h] [rbp-220h]
  int v71; // [rsp+248h] [rbp-210h]
  int v72; // [rsp+24Ch] [rbp-20Ch]
  int v73; // [rsp+250h] [rbp-208h]
  void **v74; // [rsp+290h] [rbp-1C8h] BYREF
  __int128 v75; // [rsp+298h] [rbp-1C0h]
  unsigned int v76; // [rsp+2A8h] [rbp-1B0h]
  int v77; // [rsp+2ACh] [rbp-1ACh]
  int v78; // [rsp+2B0h] [rbp-1A8h]
  void **v79; // [rsp+2F0h] [rbp-168h] BYREF
  __int128 v80; // [rsp+2F8h] [rbp-160h]
  int v81; // [rsp+308h] [rbp-150h]
  int v82; // [rsp+30Ch] [rbp-14Ch]
  int v83; // [rsp+310h] [rbp-148h]
  void **v84; // [rsp+350h] [rbp-108h] BYREF
  __int128 v85; // [rsp+358h] [rbp-100h]
  int v86; // [rsp+368h] [rbp-F0h]
  int v87; // [rsp+36Ch] [rbp-ECh]
  int v88; // [rsp+370h] [rbp-E8h]
  void **v89; // [rsp+3B0h] [rbp-A8h] BYREF
  _DWORD v90[22]; // [rsp+3B8h] [rbp-A0h] BYREF

  AccessMask[0] = a2;
  v6 = 0;
  v38 = 0;
  v46 = 0;
  v7 = (unsigned int *)&v46;
  if ( a3 )
    v7 = a3;
  try
  {
    if ( a4 )
      *a4 = 0;
    MapGenericMask(AccessMask, &CJob::s_AccessMapping);
    if ( (~CJob::s_AccessMapping.GenericRead & AccessMask[0]) != 0 && (unsigned int)(*((_DWORD *)this + 165) - 7) <= 1 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
      v50 = 0;
      pExceptionObject = &ComError::`vftable';
      v51 = -2145386494;
      v52 = 0;
      v53 = 1;
      throw (ComError *)&pExceptionObject;
    }
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&v39);
    v8 = CJobSecurityDescriptor::CheckTokenAccess(
           *((CJobSecurityDescriptor **)this + 104),
           *(void **)v41,
           AccessMask[0],
           &CJob::s_AccessMapping,
           v7,
           &v38);
    if ( v8 < 0 )
    {
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = v8;
      v57 = 3904;
      v58 = 1;
      throw (ComError *)&v54;
    }
    if ( !v38 || AccessMask[0] != 0x2000000 && *v7 != AccessMask[0] )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = "TRUE";
        if ( !v38 )
          v11 = "FALSE";
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          (_DWORD)v11,
          *v7);
      }
      v85 = 0;
      v84 = &ComError::`vftable';
      v86 = -2147024891;
      v87 = 0;
      v88 = 1;
      throw (ComError *)&v84;
    }
    ReturnLength[0] = 0;
    TokenInformation = 0;
    if ( !GetTokenInformation(*(HANDLE *)v41, TokenElevation, &TokenInformation, 4u, ReturnLength) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = LastError;
      v62 = 437;
      v63 = 1;
      throw (ComError *)&v59;
    }
    if ( v44 )
      goto LABEL_11;
    PackageInfoFromToken = (__int64 *)GetPackageInfoFromToken(ReturnLength, *(_QWORD *)v41);
    v22 = *PackageInfoFromToken;
    *PackageInfoFromToken = 0;
    v23 = v44;
    v44 = v22;
    if ( v23 )
      ((void (*)(void))std::default_delete<AppPackageInfo>::operator())();
    if ( *(_QWORD *)ReturnLength )
      ((void (*)(void))std::default_delete<AppPackageInfo>::operator())();
    if ( v44 )
    {
LABEL_11:
      v9 = (AppPackageInfo *)operator new(0x48u);
      v47 = v9;
      if ( v9 )
      {
        v27 = (const unsigned __int16 *)v44;
        v28 = (const unsigned __int16 *)(v44 + 32);
        if ( *(_QWORD *)(v44 + 56) > 7u )
          v28 = *(const unsigned __int16 **)v28;
        if ( *(_QWORD *)(v44 + 24) > 7u )
          v27 = *(const unsigned __int16 **)v44;
        v10 = AppPackageInfo::AppPackageInfo(v9, v27, v28, *(_DWORD *)(v44 + 64), *(_BYTE *)(v44 + 68));
      }
      else
      {
        v10 = 0;
      }
      v47 = 0;
      *(_QWORD *)ReturnLength = v10;
      std::unique_ptr<AppPackageInfo>::~unique_ptr<AppPackageInfo>(&v47);
      v6 = v10;
    }
    else
    {
      v10 = 0;
      *(_QWORD *)ReturnLength = 0;
    }
    v24 = (PSID *)CNestedImpersonation::CopySid(&v39, v48);
    v25 = EqualSid(*v24, *((PSID *)this + 89));
    v26 = TokenInformation;
    if ( !v25 )
      goto LABEL_28;
    v12 = *((_QWORD *)this + 92);
    if ( v6 )
    {
      if ( !v12 || *((_DWORD *)v6 + 16) != *(_DWORD *)(v12 + 64) || *((_BYTE *)v6 + 68) != *(_BYTE *)(v12 + 68) )
        goto LABEL_28;
      v29 = *(_QWORD *)(v12 + 24) <= 7u ? *((_QWORD *)this + 92) : *(_QWORD *)v12;
      v30 = *((_QWORD *)v6 + 3) <= 7u ? v6 : *(AppPackageInfo **)v6;
      if ( (unsigned int)_o__wcsicmp(v30, v29) )
        goto LABEL_28;
      v31 = (_QWORD *)(v12 + 32);
      if ( *(_QWORD *)(v12 + 56) > 7u )
        v31 = (_QWORD *)*v31;
      v32 = (_QWORD *)((char *)v6 + 32);
      if ( *((_QWORD *)v6 + 7) > 7u )
        v32 = (_QWORD *)*v32;
      if ( (unsigned int)_o__wcsicmp(v32, v31) )
        goto LABEL_28;
    }
    else if ( v12 )
    {
LABEL_28:
      v13 = 0;
LABEL_29:
      v14 = (volatile signed __int32 *)v24[1];
      if ( _InterlockedExchangeAdd(v14, 0xFFFFFFFF) == 1 )
      {
        operator delete(v24[1], 4u);
        operator delete(*v24, 0);
        v24[1] = 0;
        *v24 = 0;
      }
      if ( v10 )
        std::default_delete<AppPackageInfo>::operator()(v14, v10);
      if ( v13 )
      {
        if ( a4 )
          *a4 = 1;
        if ( (signed int)v26 < *((_DWORD *)this + 188) )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
              v26,
              *((_DWORD *)this + 188));
          v65 = 0;
          v64 = &ComError::`vftable';
          v66 = -2147024891;
          v67 = 0;
          v68 = 1;
          throw (ComError *)&v64;
        }
      }
      else if ( !v26 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
        v70 = 0;
        v69 = &ComError::`vftable';
        v71 = -2147024891;
        v72 = 0;
        v73 = 1;
        throw (ComError *)&v69;
      }
      ReturnLength[0] = 0;
      TokenInformation = 0;
      if ( !GetTokenInformation(*(HANDLE *)v41, TokenElevationType, &TokenInformation, 4u, ReturnLength) )
      {
        if ( (int)GetLastError() > 0 )
          v34 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v34 = GetLastError();
        v75 = 0;
        v74 = &ComError::`vftable';
        v76 = v34;
        v77 = 454;
        v78 = 1;
        throw (ComError *)&v74;
      }
      v15 = TokenInformation;
      if ( TokenInformation != 3 && IsTokenRestricted(*(HANDLE *)v41) )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v15);
        v80 = 0;
        v79 = &ComError::`vftable';
        v81 = -2147024891;
        v82 = 0;
        v83 = 1;
        throw (ComError *)&v79;
      }
      v16 = 0;
      if ( v40 )
      {
        SetThreadToken(0, *(HANDLE *)v39);
        v40 = 0;
      }
      v17 = v45;
      if ( v45 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 + 2, 0xFFFFFFFF) == 1 )
          operator delete(v45, 0x10u);
        v45 = 0;
      }
      if ( v44 )
        std::default_delete<AppPackageInfo>::operator()(v17, v44);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43, 0xFFFFFFFF) == 1 )
      {
        operator delete(v43, 4u);
        operator delete(v42, 0);
        v43 = 0;
        v42 = 0;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
      {
        v19 = v41;
        if ( (unsigned __int64)(*(_QWORD *)v41 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v41);
          *(_QWORD *)v41 = 0;
          v19 = v41;
        }
        operator delete(v19, 0x10u);
        v41 = 0;
      }
      SetThreadToken(0, *(HANDLE *)v39);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v39 + 2, 0xFFFFFFFF) == 1 )
      {
        v20 = v39;
        if ( (unsigned __int64)(*(_QWORD *)v39 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v39);
          *(_QWORD *)v39 = 0;
          v20 = v39;
        }
        operator delete(v20, 0x10u);
      }
      return v16;
    }
    v13 = 1;
    goto LABEL_29;
  }
  catch ( ComError v89 )
  {
    ReturnLength[0] = v90[4];
    v89 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(v90);
    return ReturnLength[0];
  }
  return v16;
}

```

## disassembly

```asm
0x18000d1f0  push    rbx
0x18000d1f2  push    rsi
0x18000d1f3  push    rdi
0x18000d1f4  push    r12
0x18000d1f6  push    r13
0x18000d1f8  push    r14
0x18000d1fa  push    r15
0x18000d1fc  sub     rsp, 420h
0x18000d203  mov     rax, cs:__security_cookie
0x18000d20a  xor     rax, rsp
0x18000d20d  mov     [rsp+458h+var_48], rax
0x18000d215  mov     r13, r9
0x18000d218  mov     r14, rcx
0x18000d21b  mov     [rsp+458h+AccessMask], edx
0x18000d21f  xor     edi, edi
0x18000d221  mov     [rsp+458h+var_408], edi
0x18000d225  mov     [rsp+458h+var_3C8], edi
0x18000d22c  lea     rbx, [rsp+458h+var_3C8]
0x18000d234  test    r8, r8
0x18000d237  cmovnz  rbx, r8
0x18000d23b  test    r9, r9
0x18000d23e  jnz     loc_18000D900
0x18000d244  lea     rdx, ?s_AccessMapping@CJob@@2U_GENERIC_MAPPING@@A; GenericMapping
0x18000d24b  lea     rcx, [rsp+458h+AccessMask]; AccessMask
0x18000d250  call    cs:__imp_MapGenericMask
0x18000d256  nop
0x18000d257  mov     eax, cs:?s_AccessMapping@CJob@@2U_GENERIC_MAPPING@@A.GenericRead; _GENERIC_MAPPING CJob::s_AccessMapping ...
0x18000d25d  not     eax
0x18000d25f  test    [rsp+458h+AccessMask], eax
0x18000d263  jnz     loc_18000D34D
0x18000d269  lea     rcx, [rsp+458h+var_400]; this
0x18000d26e  call    ??0CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::CNestedImpersonation(void)
0x18000d273  nop
0x18000d274  lea     rax, [rsp+458h+var_408]
0x18000d279  mov     [rsp+458h+var_430], rax; int *
0x18000d27e  mov     [rsp+458h+ReturnLength], rbx; unsigned int *
0x18000d283  lea     r9, ?s_AccessMapping@CJob@@2U_GENERIC_MAPPING@@A; struct _GENERIC_MAPPING *
0x18000d28a  mov     r8d, [rsp+458h+AccessMask]; unsigned int
0x18000d28f  mov     rdx, [rsp+458h+var_3F0]
0x18000d294  mov     rdx, [rdx]; void *
0x18000d297  mov     rcx, [r14+340h]; this
0x18000d29e  call    ?CheckTokenAccess@CJobSecurityDescriptor@@QEAAJPEAXKPEAU_GENERIC_MAPPING@@PEAKPEAH@Z; CJobSecurityDescriptor::CheckTokenAccess(void *,ulong,_GENERIC_MAPPING *,ulong *,int *)
0x18000d2a3  test    eax, eax
0x18000d2a5  js      loc_18000D908
0x18000d2ab  mov     ecx, [rsp+458h+var_408]
0x18000d2af  test    ecx, ecx
0x18000d2b1  jz      loc_18000D3E2
0x18000d2b7  mov     eax, [rsp+458h+AccessMask]
0x18000d2bb  cmp     eax, 2000000h
0x18000d2c0  jnz     loc_18000D3DA
0x18000d2c6  mov     [rsp+458h+var_420], edi
0x18000d2ca  mov     [rsp+458h+TokenInformation], edi
0x18000d2ce  lea     rax, [rsp+458h+var_420]
0x18000d2d3  mov     [rsp+458h+ReturnLength], rax; ReturnLength
0x18000d2d8  mov     r9d, 4; TokenInformationLength
0x18000d2de  lea     r8, [rsp+458h+TokenInformation]; TokenInformation
0x18000d2e3  mov     edx, 14h; TokenInformationClass
0x18000d2e8  mov     rcx, [rsp+458h+var_3F0]
0x18000d2ed  mov     rcx, [rcx]; TokenHandle
0x18000d2f0  call    cs:__imp_GetTokenInformation
0x18000d2f6  test    eax, eax
0x18000d2f8  jz      loc_18000D953
0x18000d2fe  cmp     [rsp+458h+var_3D8], 0
0x18000d307  jz      loc_18000D7D7
0x18000d30d  mov     ecx, 48h ; 'H'; dwBytes
0x18000d312  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d317  mov     [rsp+458h+var_3C0], rax
0x18000d31f  test    rax, rax
0x18000d322  jnz     loc_18000D863
0x18000d328  mov     rbx, rdi
0x18000d32b  mov     [rsp+458h+var_3C0], rdi
0x18000d333  mov     qword ptr [rsp+458h+var_420], rbx
0x18000d338  lea     rcx, [rsp+458h+var_3C0]
0x18000d340  call    ??1?$unique_ptr@UAppPackageInfo@@U?$default_delete@UAppPackageInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<AppPackageInfo>::~unique_ptr<AppPackageInfo>(void)
0x18000d345  mov     rdi, rbx
0x18000d348  jmp     loc_18000D82D
0x18000d34d  mov     eax, [r14+294h]
0x18000d354  sub     eax, 7
0x18000d357  cmp     eax, 1
0x18000d35a  ja      loc_18000D269
0x18000d360  lea     rdx, WPP_GLOBAL_Control
0x18000d367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d36e  cmp     rcx, rdx
0x18000d371  jz      short loc_18000D38E
0x18000d373  test    byte ptr [rcx+1Ch], 4
0x18000d377  jz      short loc_18000D38E
0x18000d379  mov     edx, 68h ; 'h'
0x18000d37e  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18000d385  mov     rcx, [rcx+10h]
0x18000d389  call    WPP_SF_
0x18000d38e  xorps   xmm0, xmm0
0x18000d391  movups  [rsp+458h+var_3A0], xmm0
0x18000d399  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000d3a0  mov     [rsp+458h+pExceptionObject], rcx
0x18000d3a8  mov     [rsp+458h+var_390], 80200002h
0x18000d3b3  mov     [rsp+458h+var_38C], edi
0x18000d3ba  mov     [rsp+458h+var_388], 1
0x18000d3c5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000d3cc  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x18000d3d4  call    _CxxThrowException_0
0x18000d3da  cmp     [rbx], eax
0x18000d3dc  jz      loc_18000D2C6
0x18000d3e2  lea     rdx, WPP_GLOBAL_Control
0x18000d3e9  mov     r10, cs:WPP_GLOBAL_Control
0x18000d3f0  cmp     r10, rdx
0x18000d3f3  jz      short loc_18000D42B
0x18000d3f5  test    byte ptr [r10+1Ch], 2
0x18000d3fa  jz      short loc_18000D42B
0x18000d3fc  mov     eax, [rbx]
0x18000d3fe  lea     r9, aTrue_1; "TRUE"
0x18000d405  lea     rdx, aFalse_1; "FALSE"
0x18000d40c  test    ecx, ecx
0x18000d40e  cmovz   r9, rdx
0x18000d412  mov     edx, 69h ; 'i'
0x18000d417  mov     dword ptr [rsp+458h+ReturnLength], eax
0x18000d41b  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18000d422  mov     rcx, [r10+10h]
0x18000d426  call    WPP_SF_sd
0x18000d42b  xorps   xmm0, xmm0
0x18000d42e  movups  [rsp+458h+var_100], xmm0
0x18000d436  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000d43d  mov     [rsp+458h+var_108], rcx
0x18000d445  mov     [rsp+458h+var_F0], 80070005h
0x18000d450  mov     [rsp+458h+var_EC], edi
0x18000d457  mov     [rsp+458h+var_E8], 1
0x18000d462  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000d469  lea     rcx, [rsp+458h+var_108]; pExceptionObject
0x18000d471  call    _CxxThrowException_0
0x18000d477  mov     r12, [r14+2E0h]
0x18000d47e  test    rdi, rdi
0x18000d481  jnz     loc_18000D9D2
0x18000d487  test    r12, r12
0x18000d48a  jz      loc_18000D8EE
0x18000d490  xor     r12b, r12b
0x18000d493  mov     rcx, [r15+8]
0x18000d497  mov     edi, 0FFFFFFFFh
0x18000d49c  mov     eax, edi
0x18000d49e  lock xadd [rcx], eax
0x18000d4a2  cmp     eax, 1
0x18000d4a5  jz      loc_18000D6EF
0x18000d4ab  test    rbx, rbx
0x18000d4ae  jnz     loc_18000D9FD
0x18000d4b4  test    r12b, r12b
0x18000d4b7  jnz     loc_18000D5DF
0x18000d4bd  test    esi, esi
0x18000d4bf  jz      loc_18000DA14
0x18000d4c5  xor     esi, esi
0x18000d4c7  mov     [rsp+458h+var_420], esi
0x18000d4cb  mov     [rsp+458h+TokenInformation], esi
0x18000d4cf  lea     rax, [rsp+458h+var_420]
0x18000d4d4  mov     [rsp+458h+ReturnLength], rax; ReturnLength
0x18000d4d9  mov     r9d, 4; TokenInformationLength
0x18000d4df  lea     r8, [rsp+458h+TokenInformation]; TokenInformation
0x18000d4e4  mov     edx, 12h; TokenInformationClass
0x18000d4e9  mov     rcx, [rsp+458h+var_3F0]
0x18000d4ee  mov     rcx, [rcx]; TokenHandle
0x18000d4f1  call    cs:__imp_GetTokenInformation
0x18000d4f7  test    eax, eax
0x18000d4f9  jz      loc_18000DA91
0x18000d4ff  mov     ebx, [rsp+458h+TokenInformation]
0x18000d503  cmp     ebx, 3
0x18000d506  jnz     loc_18000D745
0x18000d50c  mov     ebx, esi
0x18000d50e  cmp     [rsp+458h+var_3F8], 0
0x18000d513  jz      short loc_18000D52A
0x18000d515  mov     rdx, [rsp+458h+var_400]
0x18000d51a  mov     rdx, [rdx]; Token
0x18000d51d  xor     ecx, ecx; Thread
0x18000d51f  call    cs:__imp_SetThreadToken
0x18000d525  mov     [rsp+458h+var_3F8], 0
0x18000d52a  mov     rcx, [rsp+458h+var_3D0]
0x18000d532  test    rcx, rcx
0x18000d535  jz      short loc_18000D55D
0x18000d537  mov     eax, edi
0x18000d539  lock xadd [rcx+8], eax
0x18000d53e  cmp     eax, 1
0x18000d541  jnz     short loc_18000D555
0x18000d543  mov     edx, 10h; unsigned __int64
0x18000d548  mov     rcx, [rsp+458h+var_3D0]; void *
0x18000d550  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d555  mov     [rsp+458h+var_3D0], rsi
0x18000d55d  mov     rdx, [rsp+458h+var_3D8]
0x18000d565  test    rdx, rdx
0x18000d568  jnz     loc_18000DAFD
0x18000d56e  mov     rax, [rsp+458h+var_3E0]
0x18000d573  mov     ecx, edi
0x18000d575  lock xadd [rax], ecx
0x18000d579  cmp     ecx, 1
0x18000d57c  jz      loc_18000D71B
0x18000d582  mov     rcx, [rsp+458h+var_3F0]
0x18000d587  mov     eax, edi
0x18000d589  lock xadd [rcx+8], eax
0x18000d58e  cmp     eax, 1
0x18000d591  jz      loc_18000D67C
0x18000d597  mov     rdx, [rsp+458h+var_400]
0x18000d59c  mov     rdx, [rdx]; Token
0x18000d59f  xor     ecx, ecx; Thread
0x18000d5a1  call    cs:__imp_SetThreadToken
0x18000d5a7  mov     rax, [rsp+458h+var_400]
0x18000d5ac  lock xadd [rax+8], edi
0x18000d5b1  cmp     edi, 1
0x18000d5b4  jz      loc_18000D6B8
0x18000d5ba  mov     eax, ebx
0x18000d5bc  mov     rcx, [rsp+458h+var_48]
0x18000d5c4  xor     rcx, rsp; StackCookie
0x18000d5c7  call    __security_check_cookie
0x18000d5cc  add     rsp, 420h
0x18000d5d3  pop     r15
0x18000d5d5  pop     r14
0x18000d5d7  pop     r13
0x18000d5d9  pop     r12
0x18000d5db  pop     rdi
0x18000d5dc  pop     rsi
0x18000d5dd  pop     rbx
0x18000d5de  retn
0x18000d5df  test    r13, r13
0x18000d5e2  jnz     loc_18000DA0A
0x18000d5e8  mov     eax, [r14+2F0h]
0x18000d5ef  cmp     esi, eax
0x18000d5f1  jge     loc_18000D4C5
0x18000d5f7  lea     rdx, WPP_GLOBAL_Control
0x18000d5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d605  cmp     rcx, rdx
0x18000d608  jz      short loc_18000D62C
0x18000d60a  test    byte ptr [rcx+1Ch], 2
0x18000d60e  jz      short loc_18000D62C
0x18000d610  mov     edx, 6Ah ; 'j'
0x18000d615  mov     dword ptr [rsp+458h+ReturnLength], eax
0x18000d619  mov     r9d, esi
0x18000d61c  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18000d623  mov     rcx, [rcx+10h]
0x18000d627  call    WPP_SF_Dd
0x18000d62c  xorps   xmm0, xmm0
0x18000d62f  movups  [rsp+458h+var_280], xmm0
0x18000d637  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000d63e  mov     [rsp+458h+var_288], rcx
0x18000d646  mov     [rsp+458h+var_270], 80070005h
0x18000d651  mov     [rsp+458h+var_26C], 0
0x18000d65c  mov     [rsp+458h+var_268], 1
0x18000d667  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000d66e  lea     rcx, [rsp+458h+var_288]; pExceptionObject
0x18000d676  call    _CxxThrowException_0
0x18000d67c  mov     rcx, [rsp+458h+var_3F0]
0x18000d681  mov     rdx, [rcx]
0x18000d684  lea     rax, [rdx-1]
0x18000d688  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d68c  ja      short loc_18000D6A4
0x18000d68e  mov     rcx, rdx; hObject
0x18000d691  call    cs:__imp_CloseHandle
0x18000d697  mov     rax, [rsp+458h+var_3F0]
0x18000d69c  mov     [rax], rsi
0x18000d69f  mov     rcx, [rsp+458h+var_3F0]; void *
0x18000d6a4  mov     edx, 10h; unsigned __int64
0x18000d6a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d6ae  mov     [rsp+458h+var_3F0], rsi
0x18000d6b3  jmp     loc_18000D597
0x18000d6b8  mov     rcx, [rsp+458h+var_400]
0x18000d6bd  mov     rdx, [rcx]
0x18000d6c0  lea     rax, [rdx-1]
0x18000d6c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d6c8  ja      short loc_18000D6E0
0x18000d6ca  mov     rcx, rdx; hObject
0x18000d6cd  call    cs:__imp_CloseHandle
0x18000d6d3  mov     rax, [rsp+458h+var_400]
0x18000d6d8  mov     [rax], rsi
0x18000d6db  mov     rcx, [rsp+458h+var_400]; void *
0x18000d6e0  mov     edx, 10h; unsigned __int64
0x18000d6e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d6ea  jmp     loc_18000D5BA
0x18000d6ef  mov     edx, 4; unsigned __int64
0x18000d6f4  mov     rcx, [r15+8]; void *
0x18000d6f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d6fd  xor     edx, edx; unsigned __int64
0x18000d6ff  mov     rcx, [r15]; void *
0x18000d702  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d707  mov     qword ptr [r15+8], 0
0x18000d70f  mov     qword ptr [r15], 0
0x18000d716  jmp     loc_18000D4AB
0x18000d71b  mov     edx, 4; unsigned __int64
0x18000d720  mov     rcx, [rsp+458h+var_3E0]; void *
0x18000d725  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d72a  xor     edx, edx; unsigned __int64
0x18000d72c  mov     rcx, [rsp+458h+var_3E8]; void *
0x18000d731  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d736  mov     [rsp+458h+var_3E0], rsi
0x18000d73b  mov     [rsp+458h+var_3E8], rsi
0x18000d740  jmp     loc_18000D582
0x18000d745  mov     rcx, [rsp+458h+var_3F0]
0x18000d74a  mov     rcx, [rcx]; TokenHandle
0x18000d74d  call    cs:__imp_IsTokenRestricted
0x18000d753  test    eax, eax
0x18000d755  jz      loc_18000D50C
0x18000d75b  lea     rdx, WPP_GLOBAL_Control
0x18000d762  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d769  cmp     rcx, rdx
0x18000d76c  jz      short loc_18000D78C
0x18000d76e  test    byte ptr [rcx+1Ch], 2
0x18000d772  jz      short loc_18000D78C
0x18000d774  mov     edx, 6Ch ; 'l'
0x18000d779  mov     r9d, ebx
  ... truncated ...
```
