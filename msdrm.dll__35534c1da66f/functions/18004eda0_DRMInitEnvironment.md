# DRMInitEnvironment

- ea: `0x18004eda0`
- end: `0x18004efab`
- name: `DRMInitEnvironment`
- size: `523`
- prototype: `HRESULT __stdcall(DRMSECURITYPROVIDERTYPE eSecurityProviderType, DRMSPECTYPE eSpecification, PWSTR wszSecurityProvider, PWSTR wszManifestCredentials, PWSTR wszMachineCredentials, DRMENVHANDLE *phEnv, DRMHANDLE *phDefaultLibrary)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800046c8`
- `0x18001f3ac`
- `0x18004d134`
- `0x18004eda0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ee40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ee40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004ee25`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004ee25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004eea4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004eedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ef1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004eea4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004eedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ef1b`

## string_xrefs

- `0x18004eecf`: `[msdrm]:SPCreateSecurityProcessor failed with HR=0x%x\n`
- `0x18004eee5`: `[msdrm]:SPCreateSecurityProcessor took %d milliseconds\n`

## pseudocode

```c
HRESULT __stdcall DRMInitEnvironment(
        DRMSECURITYPROVIDERTYPE eSecurityProviderType,
        DRMSPECTYPE eSpecification,
        PWSTR wszSecurityProvider,
        PWSTR wszManifestCredentials,
        PWSTR wszMachineCredentials,
        DRMENVHANDLE *phEnv,
        DRMHANDLE *phDefaultLibrary)
{
  HRESULT result; // eax
  HRESULT v10; // ebx
  DWORD TickCount; // r15d
  int v12; // eax
  DWORD v13; // esi
  CHandlesTable *v14; // rcx
  CHandlesTable *v15; // rcx
  DWORD v16; // eax
  unsigned int v17; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-40h] BYREF
  __int128 v20; // [rsp+40h] [rbp-38h] BYREF
  __int128 v21; // [rsp+50h] [rbp-28h] BYREF
  __int128 v22; // [rsp+60h] [rbp-18h] BYREF

  _RTLTRACE("[msdrm]:+DRMInitEnvironment \n", eSpecification, wszSecurityProvider);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  if ( !wszMachineCredentials )
    return -2147024809;
  if ( !phEnv )
    return -2147024809;
  if ( !phDefaultLibrary )
    return -2147024809;
  *phEnv = 0;
  if ( eSecurityProviderType )
    return -2147024809;
  if ( !g_fGlobalOptionUseServerProc && IsDebuggerPresent() )
    return -2147168416;
  EnterCriticalSection(&g_csOptions);
  if ( g_fEnvInitialized == 1 )
  {
    v10 = -2147168500;
    goto LABEL_21;
  }
  v10 = _InitializeSpProcs();
  if ( v10 < 0 )
    goto LABEL_18;
  *((_QWORD *)&v21 + 1) = 0x1000000000LL;
  *(_QWORD *)&v21 = wszMachineCredentials;
  if ( !wszManifestCredentials )
  {
    v10 = -2147024809;
    goto LABEL_18;
  }
  *((_QWORD *)&v20 + 1) = 0x4300000000LL;
  *((_QWORD *)&v22 + 1) = &v20;
  *(_QWORD *)&v20 = wszManifestCredentials;
  LODWORD(v22) = 1;
  TickCount = GetTickCount();
  v12 = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int128 *, unsigned int *))g_pfnSPCreateSecurityProcessor)(
          0,
          &v21,
          &v22,
          &v17);
  v10 = v12;
  if ( v12 < 0 )
  {
    _RTLTRACE("[msdrm]:SPCreateSecurityProcessor failed with HR=0x%x\n", v12);
    goto LABEL_18;
  }
  v13 = GetTickCount();
  _RTLTRACE("[msdrm]:SPCreateSecurityProcessor took %d milliseconds\n", v13 - TickCount);
  v10 = CHandlesTable::CreateHandle(v14, &v18, v17);
  if ( v10 < 0 || (v10 = CHandlesTable::CreateHandle(v15, &v19, 0), v10 < 0) )
  {
LABEL_18:
    if ( g_pfnSPCloseHandle && v17 )
      g_pfnSPCloseHandle(v17);
    goto LABEL_21;
  }
  v16 = GetTickCount();
  _RTLTRACE("[msdrm]:Environment Handle Creation took %d milliseconds\n", v16 - v13);
  *phEnv = v18;
  *phDefaultLibrary = v19;
  g_fEnvInitialized = 1;
LABEL_21:
  LeaveCriticalSection(&g_csOptions);
  _RTLTRACE("[msdrm]:-DRMInitEnvironment HR=0x%x\n", v10);
  result = -2147024774;
  if ( v10 != -2147024774 )
  {
    result = -2147168468;
    if ( v10 != -1073426388 )
      return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18004eda0  push    rbp
0x18004eda2  push    rbx
0x18004eda3  push    rsi
0x18004eda4  push    rdi
0x18004eda5  push    r14
0x18004eda7  push    r15
0x18004eda9  mov     rbp, rsp
0x18004edac  sub     rsp, 78h
0x18004edb0  mov     ebx, ecx
0x18004edb2  mov     r15, r9
0x18004edb5  lea     rcx, aMsdrmDrminiten_0; "[msdrm]:+DRMInitEnvironment \n"
0x18004edbc  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004edc1  mov     rsi, [rbp+wszMachineCredentials]
0x18004edc5  xorps   xmm0, xmm0
0x18004edc8  mov     [rbp+var_48], 0
0x18004edcf  xorps   xmm1, xmm1
0x18004edd2  mov     [rbp+var_44], 0
0x18004edd9  mov     [rbp+var_40], 0
0x18004ede0  movups  [rbp+var_28], xmm0
0x18004ede4  movups  [rbp+var_38], xmm1
0x18004ede8  movups  [rbp+var_18], xmm0
0x18004edec  test    rsi, rsi
0x18004edef  jz      loc_18004EF99
0x18004edf5  mov     rdi, [rbp+phEnv]
0x18004edf9  test    rdi, rdi
0x18004edfc  jz      loc_18004EF99
0x18004ee02  mov     r14, [rbp+phDefaultLibrary]
0x18004ee06  test    r14, r14
0x18004ee09  jz      loc_18004EF99
0x18004ee0f  mov     dword ptr [rdi], 0
0x18004ee15  test    ebx, ebx
0x18004ee17  jnz     loc_18004EF99
0x18004ee1d  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, ebx; int g_fGlobalOptionUseServerProc
0x18004ee23  jnz     short loc_18004EE39
0x18004ee25  call    cs:__imp_IsDebuggerPresent
0x18004ee2b  test    eax, eax
0x18004ee2d  jz      short loc_18004EE39
0x18004ee2f  mov     eax, 8004CF60h
0x18004ee34  jmp     loc_18004EF9E
0x18004ee39  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004ee40  call    cs:__imp_EnterCriticalSection
0x18004ee46  cmp     cs:?g_fEnvInitialized@@3HA, 1; int g_fEnvInitialized
0x18004ee4d  jnz     short loc_18004EE59
0x18004ee4f  mov     ebx, 8004CF0Ch
0x18004ee54  jmp     loc_18004EF65
0x18004ee59  call    ?_InitializeSpProcs@@YAJXZ; _InitializeSpProcs(void)
0x18004ee5e  mov     ebx, eax
0x18004ee60  test    eax, eax
0x18004ee62  js      loc_18004EF4D
0x18004ee68  mov     dword ptr [rbp+var_28+8], 0
0x18004ee6f  mov     qword ptr [rbp+var_28], rsi
0x18004ee73  mov     dword ptr [rbp+var_28+0Ch], 10h
0x18004ee7a  test    r15, r15
0x18004ee7d  jz      loc_18004EF48
0x18004ee83  lea     rax, [rbp+var_38]
0x18004ee87  mov     dword ptr [rbp+var_38+8], 0
0x18004ee8e  mov     qword ptr [rbp+var_18+8], rax
0x18004ee92  mov     qword ptr [rbp+var_38], r15
0x18004ee96  mov     dword ptr [rbp+var_38+0Ch], 43h ; 'C'
0x18004ee9d  mov     dword ptr [rbp+var_18], 1
0x18004eea4  call    cs:__imp_GetTickCount
0x18004eeaa  lea     r9, [rbp+var_48]
0x18004eeae  xor     ecx, ecx
0x18004eeb0  mov     r15d, eax
0x18004eeb3  lea     r8, [rbp+var_18]
0x18004eeb7  mov     rax, cs:?g_pfnSPCreateSecurityProcessor@@3P6AJKPEAU_SPAPI_TOKEN@@PEAXPEAK@ZEA; long (*g_pfnSPCreateSecurityProcessor)(ulong,_SPAPI_TOKEN *,void *,ulong *)
0x18004eebe  lea     rdx, [rbp+var_28]
0x18004eec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eec7  mov     ebx, eax
0x18004eec9  test    eax, eax
0x18004eecb  jns     short loc_18004EEDD
0x18004eecd  mov     edx, eax
0x18004eecf  lea     rcx, aMsdrmSpcreates_0; "[msdrm]:SPCreateSecurityProcessor faile"...
0x18004eed6  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004eedb  jmp     short loc_18004EF4D
0x18004eedd  call    cs:__imp_GetTickCount
0x18004eee3  mov     edx, eax
0x18004eee5  lea     rcx, aMsdrmSpcreates; "[msdrm]:SPCreateSecurityProcessor took "...
0x18004eeec  sub     edx, r15d
0x18004eeef  mov     esi, eax
0x18004eef1  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004eef6  mov     r8d, [rbp+var_48]; unsigned int
0x18004eefa  lea     rdx, [rbp+var_44]; unsigned int *
0x18004eefe  call    ?CreateHandle@CHandlesTable@@QEAAJPEAKK@Z; CHandlesTable::CreateHandle(ulong *,ulong)
0x18004ef03  mov     ebx, eax
0x18004ef05  test    eax, eax
0x18004ef07  js      short loc_18004EF4D
0x18004ef09  xor     r8d, r8d; unsigned int
0x18004ef0c  lea     rdx, [rbp+var_40]; unsigned int *
0x18004ef10  call    ?CreateHandle@CHandlesTable@@QEAAJPEAKK@Z; CHandlesTable::CreateHandle(ulong *,ulong)
0x18004ef15  mov     ebx, eax
0x18004ef17  test    eax, eax
0x18004ef19  js      short loc_18004EF4D
0x18004ef1b  call    cs:__imp_GetTickCount
0x18004ef21  sub     eax, esi
0x18004ef23  lea     rcx, aMsdrmEnvironme; "[msdrm]:Environment Handle Creation too"...
0x18004ef2a  mov     edx, eax
0x18004ef2c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004ef31  mov     eax, [rbp+var_44]
0x18004ef34  mov     [rdi], eax
0x18004ef36  mov     eax, [rbp+var_40]
0x18004ef39  mov     [r14], eax
0x18004ef3c  mov     cs:?g_fEnvInitialized@@3HA, 1; int g_fEnvInitialized
0x18004ef46  jmp     short loc_18004EF65
0x18004ef48  mov     ebx, 80070057h
0x18004ef4d  mov     rax, cs:?g_pfnSPCloseHandle@@3P6AJK@ZEA; long (*g_pfnSPCloseHandle)(ulong)
0x18004ef54  test    rax, rax
0x18004ef57  jz      short loc_18004EF65
0x18004ef59  mov     ecx, [rbp+var_48]
0x18004ef5c  test    ecx, ecx
0x18004ef5e  jz      short loc_18004EF65
0x18004ef60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef65  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004ef6c  call    cs:__imp_LeaveCriticalSection
0x18004ef72  mov     edx, ebx
0x18004ef74  lea     rcx, aMsdrmDrminiten; "[msdrm]:-DRMInitEnvironment HR=0x%x\n"
0x18004ef7b  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004ef80  mov     eax, 8007007Ah
0x18004ef85  cmp     ebx, eax
0x18004ef87  jz      short loc_18004EF9E
0x18004ef89  cmp     ebx, 0C004D02Ch
0x18004ef8f  mov     eax, 8004CF2Ch
0x18004ef94  cmovnz  eax, ebx
0x18004ef97  jmp     short loc_18004EF9E
0x18004ef99  mov     eax, 80070057h
0x18004ef9e  add     rsp, 78h
0x18004efa2  pop     r15
0x18004efa4  pop     r14
0x18004efa6  pop     rdi
0x18004efa7  pop     rsi
0x18004efa8  pop     rbx
0x18004efa9  pop     rbp
0x18004efaa  retn
```
