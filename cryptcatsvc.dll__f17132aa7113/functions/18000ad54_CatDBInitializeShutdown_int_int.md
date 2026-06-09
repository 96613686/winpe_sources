# _CatDBInitializeShutdown(int,int)

- ea: `0x18000ad54`
- end: `0x18000af68`
- name: `?_CatDBInitializeShutdown@@YAHHH@Z`
- size: `532`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800091a0`
- `0x1800091f8`
- `0x18001344c`

## callees

- `0x180004a20`
- `0x18000a59c`
- `0x18000ad54`
- `0x1800131b8`
- `0x180013320`
- `0x180017328`
- `0x180017928`
- `0x180019e84`
- `0x18001ae08`
- `0x18001b1c4`
- `0x18001b320`
- `0x18001d2b0`
- `0x18001ea80`
- `0x18001eb28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae04`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae11`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae2b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae04`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae11`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae2b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ae3a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ae3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ade9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ade9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000af41`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000af41`
- `ntdll!EtwEventRegister` at `0x18000addd`
- `ntdll!EtwEventRegister` at `0x18000addd`

## pseudocode

```c
__int64 __fastcall _CatDBInitializeShutdown(int a1, int a2)
{
  unsigned int v3; // edi
  DWORD v4; // eax
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  int v8; // ebp
  DWORD LastError; // ebx
  __int64 *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  int v15; // [rsp+28h] [rbp-20h]
  char v16; // [rsp+60h] [rbp+18h] BYREF

  v3 = 1;
  if ( a1 )
  {
    if ( g_fDBSvcInitialized )
    {
      g_fShuttingDown = 1;
      if ( a2 )
      {
        CatDBServiceStopJet();
      }
      else
      {
        CSystemWriter::Shutdown();
        _CatDBStopChangeNotifications();
        CatDBServiceStopJet();
        _CatDBCleanupTempFiles();
      }
      _CatDBReleaseResources(a2 != 0, 1);
      g_fDBSvcInitialized = 0;
    }
    return v3;
  }
  g_fShuttingDown = 0;
  if ( !a2 )
  {
    v4 = EtwEventRegister(CAPI2_PROVIDER, 0, 0, &qword_180032A08);
    if ( v4 )
    {
      SetLastError(v4);
      v7 = 4187;
      v8 = 0;
LABEL_18:
      ErrLog_LogError(v6, v5, v7, 0, 0, v15);
      LastError = GetLastError();
      _CatDBReleaseResources(a2 != 0, v8 != 0);
      SetLastError(LastError);
      return 0;
    }
  }
  InitializeCriticalSection(&g_CatDBAddDeleteCS);
  InitializeCriticalSection(&g_CatDirCashCS);
  InitializeCriticalSection(&g_JetDBOpenCS);
  InitializeCriticalSection(&g_CleanupTempFilesCS);
  v8 = 1;
  InitializeSRWLock(&g_CatDirCashSRW);
  _CatDBInitConfigPara();
  if ( a2 )
    LODWORD(qword_180032708) = -1;
  g_pwszCatalogFileBaseDirectory = _CatDBGetCatrootDirW(0);
  if ( !g_pwszCatalogFileBaseDirectory )
  {
    v7 = 4211;
    goto LABEL_18;
  }
  g_pwszDatabaseFileBaseDirectory = _CatDBGetCatrootDirW(1);
  if ( !g_pwszDatabaseFileBaseDirectory )
  {
    v7 = 4218;
    goto LABEL_18;
  }
  dword_1800327A0 = 0;
  g_CatalogDBCacheList = 0;
  if ( !(unsigned int)CatDBServiceStartJet() )
  {
    v7 = 4226;
    goto LABEL_18;
  }
  g_fDBSvcInitialized = 1;
  v10 = (__int64 *)RateLimiter::CreateNewForGarrulousEvents(&v16);
  v11 = *v10;
  *v10 = 0;
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&g_pWintrustTelemetryRateLimiter, v11);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v16, 0);
  if ( !a2 )
  {
    if ( (unsigned int)_CatDBStartChangeNotifications() )
    {
      if ( dword_18003271C )
      {
        g_CatrootChangesSyncInFlight = 1;
        SubmitThreadpoolWork(g_CatrootSyncWork);
        dword_18003271C = 0;
      }
    }
    else
    {
      ErrLog_LogError(v13, v12, 0x1092u, 0, 0, v15);
    }
    CSystemWriter::Startup();
  }
  return v3;
}

```

## disassembly

```asm
0x18000ad54  mov     [rsp+arg_0], rbx
0x18000ad59  mov     [rsp+arg_8], rbp
0x18000ad5e  push    rsi
0x18000ad5f  push    rdi
0x18000ad60  push    r14
0x18000ad62  sub     rsp, 30h
0x18000ad66  xor     r14d, r14d
0x18000ad69  mov     esi, edx
0x18000ad6b  mov     edi, 1
0x18000ad70  test    ecx, ecx
0x18000ad72  jz      short loc_18000ADBF
0x18000ad74  cmp     cs:?g_fDBSvcInitialized@@3HA, r14d; int g_fDBSvcInitialized
0x18000ad7b  jz      loc_18000AF53
0x18000ad81  mov     cs:?g_fShuttingDown@@3HA, edi; int g_fShuttingDown
0x18000ad87  test    edx, edx
0x18000ad89  jnz     short loc_18000ADA1
0x18000ad8b  call    ?Shutdown@CSystemWriter@@SAXXZ; CSystemWriter::Shutdown(void)
0x18000ad90  call    ?_CatDBStopChangeNotifications@@YAXXZ; _CatDBStopChangeNotifications(void)
0x18000ad95  call    _CatDBServiceStopJet
0x18000ad9a  call    ?_CatDBCleanupTempFiles@@YAXXZ; _CatDBCleanupTempFiles(void)
0x18000ad9f  jmp     short loc_18000ADA6
0x18000ada1  call    _CatDBServiceStopJet
0x18000ada6  test    esi, esi
0x18000ada8  mov     dl, dil; bool
0x18000adab  setnz   cl; bool
0x18000adae  call    ?_CatDBReleaseResources@@YAX_N0@Z; _CatDBReleaseResources(bool,bool)
0x18000adb3  mov     cs:?g_fDBSvcInitialized@@3HA, r14d; int g_fDBSvcInitialized
0x18000adba  jmp     loc_18000AF53
0x18000adbf  mov     cs:?g_fShuttingDown@@3HA, r14d; int g_fShuttingDown
0x18000adc6  test    esi, esi
0x18000adc8  jnz     short loc_18000ADFD
0x18000adca  lea     r9, qword_180032A08
0x18000add1  xor     r8d, r8d
0x18000add4  xor     edx, edx
0x18000add6  lea     rcx, CAPI2_PROVIDER
0x18000addd  call    cs:__imp_EtwEventRegister
0x18000ade3  test    eax, eax
0x18000ade5  jz      short loc_18000ADFD
0x18000ade7  mov     ecx, eax; dwErrCode
0x18000ade9  call    cs:__imp_SetLastError
0x18000adef  mov     r8d, 105Bh
0x18000adf5  mov     ebp, r14d
0x18000adf8  jmp     loc_18000AEAA
0x18000adfd  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae04  call    cs:__imp_InitializeCriticalSection
0x18000ae0a  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae11  call    cs:__imp_InitializeCriticalSection
0x18000ae17  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae1e  call    cs:__imp_InitializeCriticalSection
0x18000ae24  lea     rcx, ?g_CleanupTempFilesCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae2b  call    cs:__imp_InitializeCriticalSection
0x18000ae31  lea     rcx, ?g_CatDirCashSRW@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ae38  mov     ebp, edi
0x18000ae3a  call    cs:__imp_InitializeSRWLock
0x18000ae40  call    ?_CatDBInitConfigPara@@YAXXZ; _CatDBInitConfigPara(void)
0x18000ae45  test    esi, esi
0x18000ae47  jz      short loc_18000AE53
0x18000ae49  mov     dword ptr cs:qword_180032708, 0FFFFFFFFh
0x18000ae53  xor     ecx, ecx; int
0x18000ae55  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x18000ae5a  mov     cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA, rax; ushort * g_pwszCatalogFileBaseDirectory
0x18000ae61  test    rax, rax
0x18000ae64  jnz     short loc_18000AE6E
0x18000ae66  mov     r8d, 1073h
0x18000ae6c  jmp     short loc_18000AEAA
0x18000ae6e  mov     ecx, edi; int
0x18000ae70  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x18000ae75  mov     cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA, rax; ushort * g_pwszDatabaseFileBaseDirectory
0x18000ae7c  test    rax, rax
0x18000ae7f  jnz     short loc_18000AE89
0x18000ae81  mov     r8d, 107Ah
0x18000ae87  jmp     short loc_18000AEAA
0x18000ae89  xorps   xmm0, xmm0
0x18000ae8c  mov     cs:dword_1800327A0, r14d
0x18000ae93  movdqu  cs:?g_CatalogDBCacheList@@3ULIST_@@A, xmm0; LIST_ g_CatalogDBCacheList
0x18000ae9b  call    _CatDBServiceStartJet
0x18000aea0  test    eax, eax
0x18000aea2  jnz     short loc_18000AEDB
0x18000aea4  mov     r8d, 1082h; unsigned int
0x18000aeaa  xor     r9d, r9d; unsigned int
0x18000aead  mov     [rsp+48h+var_28], r14d; int
0x18000aeb2  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000aeb7  call    cs:__imp_GetLastError
0x18000aebd  cmp     ebp, edi
0x18000aebf  mov     ebx, eax
0x18000aec1  setnb   dl; bool
0x18000aec4  test    esi, esi
0x18000aec6  setnz   cl; bool
0x18000aec9  call    ?_CatDBReleaseResources@@YAX_N0@Z; _CatDBReleaseResources(bool,bool)
0x18000aece  mov     ecx, ebx; dwErrCode
0x18000aed0  call    cs:__imp_SetLastError
0x18000aed6  mov     edi, r14d
0x18000aed9  jmp     short loc_18000AF53
0x18000aedb  lea     rcx, [rsp+48h+arg_10]
0x18000aee0  mov     cs:?g_fDBSvcInitialized@@3HA, edi; int g_fDBSvcInitialized
0x18000aee6  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x18000aeeb  lea     rcx, ?g_pWintrustTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pWintrustTelemetryRateLimiter
0x18000aef2  mov     rdx, [rax]
0x18000aef5  mov     [rax], r14
0x18000aef8  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x18000aefd  xor     edx, edx
0x18000aeff  lea     rcx, [rsp+48h+arg_10]
0x18000af04  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x18000af09  test    esi, esi
0x18000af0b  jnz     short loc_18000AF53
0x18000af0d  call    ?_CatDBStartChangeNotifications@@YAHXZ; _CatDBStartChangeNotifications(void)
0x18000af12  test    eax, eax
0x18000af14  jnz     short loc_18000AF2B
0x18000af16  xor     r9d, r9d; unsigned int
0x18000af19  mov     [rsp+48h+var_28], r14d; int
0x18000af1e  mov     r8d, 1092h; unsigned int
0x18000af24  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000af29  jmp     short loc_18000AF4E
0x18000af2b  cmp     cs:dword_18003271C, r14d
0x18000af32  jz      short loc_18000AF4E
0x18000af34  mov     rcx, cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA; pwk
0x18000af3b  mov     cs:?g_CatrootChangesSyncInFlight@@3JA, edi; long g_CatrootChangesSyncInFlight
0x18000af41  call    cs:__imp_SubmitThreadpoolWork
0x18000af47  mov     cs:dword_18003271C, r14d
0x18000af4e  call    ?Startup@CSystemWriter@@SA_NXZ; CSystemWriter::Startup(void)
0x18000af53  mov     rbx, [rsp+48h+arg_0]
0x18000af58  mov     eax, edi
0x18000af5a  mov     rbp, [rsp+48h+arg_8]
0x18000af5f  add     rsp, 30h
0x18000af63  pop     r14
0x18000af65  pop     rdi
0x18000af66  pop     rsi
0x18000af67  retn
```
