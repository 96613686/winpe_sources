# CRepository::Initialize(void)

- ea: `0x18003b064`
- end: `0x18003b44a`
- name: `?Initialize@CRepository@@IEAAJXZ`
- size: `998`
- prototype: `__int64 __fastcall(CRepository *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b630`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800161e0`
- `0x18001c038`
- `0x18001e134`
- `0x180023170`
- `0x180026248`
- `0x180028990`
- `0x180029fbc`
- `0x180032b24`
- `0x18003a730`
- `0x18003ad0c`
- `0x18003b064`
- `0x18003b9c0`
- `0x18003d184`
- `0x18003d9fc`
- `0x18003db10`
- `0x18003defc`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b0b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b2e8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b0b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b2e8`
- `wbemcomn!?GetPersistentCfgValue@CPersistentConfig@@QEAAHKAEAK@Z` at `0x18003b187`
- `wbemcomn!?GetPersistentCfgValue@CPersistentConfig@@QEAAHKAEAK@Z` at `0x18003b187`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003b14b`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003b14b`
- `wbemcomn!GetMemLogObject` at `0x18003b218`
- `wbemcomn!GetMemLogObject` at `0x18003b282`
- `wbemcomn!GetMemLogObject` at `0x18003b3da`
- `wbemcomn!GetMemLogObject` at `0x18003b218`
- `wbemcomn!GetMemLogObject` at `0x18003b282`
- `wbemcomn!GetMemLogObject` at `0x18003b3da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b224`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b28e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b3e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b224`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b28e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b3e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b1af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b1af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b116`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall CRepository::Initialize(struct CLifeControl **this)
{
  _QWORD *v2; // rax
  unsigned int v3; // edx
  unsigned int v4; // r8d
  unsigned int v5; // r9d
  signed int result; // eax
  unsigned int v7; // eax
  int RepositoryDirectory; // eax
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  CMemoryLog *v16; // rax
  CNamespaceHandle *v17; // rax
  CNamespaceHandle *v18; // rcx
  CNamespaceHandle *v19; // rcx
  CMemoryLog *v20; // rax
  __int128 *v21; // [rsp+20h] [rbp-30h] BYREF
  int v22; // [rsp+28h] [rbp-28h]
  char v23[8]; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall *v24)(EventHandler *); // [rsp+38h] [rbp-18h]
  PVOID v25; // [rsp+40h] [rbp-10h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v27; // [rsp+80h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  v2 = CWin32DefaultArena::WbemMemAlloc(0x48u);
  SystemTimeAsFileTime = (struct _FILETIME)v2;
  if ( !v2 )
  {
    g_checkpointTimer = 0;
    return -2147217402;
  }
  v2[3] = 1;
  v2[4] = 0;
  *((_DWORD *)v2 + 10) = 0;
  v2[6] = 0;
  v2[1] = 0;
  v2[2] = 0;
  *v2 = &CheckPointTimer::`vftable';
  v2[8] = 0;
  g_checkpointTimer = v2;
  if ( !(unsigned int)Dispatcher::scheduleTimer((struct EventHandler *)&CheckPointTimer::`vftable', v3, v4, v5) )
  {
    EventHandler::Release((EventHandler *)g_checkpointTimer);
    g_checkpointTimer = 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v23[0] = 0;
  v24 = CancelCheckPointTimer;
  v25 = g_checkpointTimer;
  if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    *(_OWORD *)&g_SA.nLength = *(_OWORD *)&g_OfflineSA.nLength;
    *(_QWORD *)&g_SA.bInheritHandle = 0;
  }
  v27 = 0;
  LOBYTE(SystemTimeAsFileTime.dwLowDateTime) = 0;
  CPersistentConfig::GetPersistentCfgValue((CPersistentConfig *)&SystemTimeAsFileTime, 3u, &v27);
  v7 = v27;
  if ( !v27 )
    v7 = 8;
  g_dwOldRepositoryVersion = v7;
  g_dwCurrentRepositoryVersion = 8;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  g_nCurrentTime = SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32);
  RepositoryDirectory = CRepository::GetRepositoryDirectory((CRepository *)g_nCurrentTime);
  v9 = 0;
  if ( RepositoryDirectory < 0 )
    v9 = RepositoryDirectory;
  if ( v9 >= 0 )
  {
    g_bShuttingDown = 0;
    v10 = CFileCache::Initialize((CFileCache *)byte_180058AF8, &FileName);
    v11 = v10;
    if ( !v10 )
      goto LABEL_53;
    if ( v10 == 1358 )
    {
      CRepositoryCorruption::SetRepositoryCorrupted(0, 1, 0);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 1358);
      }
    }
    else
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -1);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, v11);
      }
    }
    v15 = A51TranslateErrorCode(v11, v13, v14);
    v9 = v15;
    if ( v15 == -2147217407 )
      goto LABEL_23;
    if ( v15 >= 0 )
    {
LABEL_53:
      if ( (unsigned int)CGlobals::Initialize((CGlobals *)&g_Glob) )
      {
LABEL_23:
        v9 = -2147217388;
        goto LABEL_40;
      }
      v17 = (CNamespaceHandle *)CWin32DefaultArena::WbemMemAlloc(0x70u);
      SystemTimeAsFileTime = (struct _FILETIME)v17;
      if ( v17 )
        v18 = CNamespaceHandle::CNamespaceHandle(v17, this[2], (struct CRepository *)this);
      else
        v18 = 0;
      g_pSystemClassNamespace = v18;
      if ( v18 )
      {
        (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v18 + 8LL))(v18);
        v9 = CNamespaceHandle::Initialize(g_pSystemClassNamespace, L"__SYSTEMCLASS", 0);
        if ( v9 >= 0 )
        {
          g_bShuttingDown = 0;
          v21 = &g_readWriteLock;
          v22 = 0;
          v9 = CAutoWriteLock::Lock((CAutoWriteLock *)&v21)
             ? CNamespaceHandle::CreateSystemClasses(v19, (struct CFlexArray *)(this + 3))
             : -2147217407;
          CAutoWriteLock::Unlock((CAutoWriteLock *)&v21);
          if ( v9 >= 0 )
          {
LABEL_43:
            v23[0] = 1;
            goto LABEL_45;
          }
        }
      }
      else
      {
        v9 = -2147217402;
      }
    }
  }
LABEL_40:
  g_bShuttingDown = 1;
  CFileCache::Uninitialize((CFileCache *)byte_180058AF8, 0);
  CForestCache::Deinitialize((CForestCache *)qword_180058A80);
  if ( g_pSystemClassNamespace )
  {
    (*(void (__fastcall **)(CNamespaceHandle *, __int64))(*(_QWORD *)g_pSystemClassNamespace + 32LL))(
      g_pSystemClassNamespace,
      1);
    g_pSystemClassNamespace = 0;
  }
  if ( v9 >= 0 )
    goto LABEL_43;
  v20 = GetMemLogObject();
  CMemoryLog::Write(v20, v9);
LABEL_45:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, (unsigned int)v9);
  }
  ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v23);
  return v9;
}

```

## disassembly

```asm
0x18003b064  mov     [rsp-18h+arg_0], rbx
0x18003b069  mov     [rsp-18h+arg_18], rsi
0x18003b06e  push    rbp
0x18003b06f  push    rdi
0x18003b070  push    r15
0x18003b072  mov     rbp, rsp
0x18003b075  sub     rsp, 50h
0x18003b079  mov     rdi, rcx
0x18003b07c  lea     r15, WPP_GLOBAL_Control
0x18003b083  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b08a  cmp     rcx, r15
0x18003b08d  jz      short loc_18003B0B0
0x18003b08f  test    byte ptr [rcx+1Ch], 1
0x18003b093  jz      short loc_18003B0B0
0x18003b095  cmp     byte ptr [rcx+19h], 5
0x18003b099  jb      short loc_18003B0B0
0x18003b09b  mov     edx, 2Dh ; '-'
0x18003b0a0  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b0a7  mov     rcx, [rcx+10h]
0x18003b0ab  call    WPP_SF_
0x18003b0b0  mov     ecx, 48h ; 'H'
0x18003b0b5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003b0bb  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003b0bf  xor     esi, esi
0x18003b0c1  test    rax, rax
0x18003b0c4  jz      loc_18003B429
0x18003b0ca  mov     qword ptr [rax+18h], 1
0x18003b0d2  mov     [rax+20h], rsi
0x18003b0d6  mov     [rax+28h], esi
0x18003b0d9  mov     [rax+30h], rsi
0x18003b0dd  mov     [rax+8], rsi
0x18003b0e1  mov     [rax+10h], rsi
0x18003b0e5  lea     rcx, ??_7CheckPointTimer@@6B@; struct EventHandler *
0x18003b0ec  mov     [rax], rcx
0x18003b0ef  mov     [rax+40h], rsi
0x18003b0f3  mov     cs:?g_checkpointTimer@@3PEAVCheckPointTimer@@EA, rax; CheckPointTimer * g_checkpointTimer
0x18003b0fa  call    ?scheduleTimer@Dispatcher@@SAHAEAVEventHandler@@KKK@Z; Dispatcher::scheduleTimer(EventHandler &,ulong,ulong,ulong)
0x18003b0ff  test    eax, eax
0x18003b101  jnz     short loc_18003B131
0x18003b103  mov     rcx, cs:?g_checkpointTimer@@3PEAVCheckPointTimer@@EA; this
0x18003b10a  call    ?Release@EventHandler@@UEAAJXZ; EventHandler::Release(void)
0x18003b10f  mov     cs:?g_checkpointTimer@@3PEAVCheckPointTimer@@EA, rsi; CheckPointTimer * g_checkpointTimer
0x18003b116  call    cs:__imp_GetLastError
0x18003b11c  test    eax, eax
0x18003b11e  jle     loc_18003B435
0x18003b124  movzx   eax, ax
0x18003b127  or      eax, 80070000h
0x18003b12c  jmp     loc_18003B435
0x18003b131  mov     rax, cs:?g_checkpointTimer@@3PEAVCheckPointTimer@@EA; CheckPointTimer * g_checkpointTimer
0x18003b138  mov     [rbp+var_20], sil
0x18003b13c  lea     rcx, ?CancelCheckPointTimer@@YAXPEAVCheckPointTimer@@@Z; CancelCheckPointTimer(CheckPointTimer *)
0x18003b143  mov     [rbp+var_18], rcx
0x18003b147  mov     [rbp+var_10], rax
0x18003b14b  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18003b151  test    al, al
0x18003b153  jz      short loc_18003B173
0x18003b155  movups  xmm0, cs:?g_OfflineSA@@3U_SECURITY_ATTRIBUTES@@A; _SECURITY_ATTRIBUTES g_OfflineSA
0x18003b15c  movups  xmmword ptr cs:?g_SA@@3U_SECURITY_ATTRIBUTES@@A.nLength, xmm0; _SECURITY_ATTRIBUTES g_SA ...
0x18003b163  movsd   xmm1, cs:qword_18004CF20
0x18003b16b  movsd   qword ptr cs:?g_SA@@3U_SECURITY_ATTRIBUTES@@A.bInheritHandle, xmm1; _SECURITY_ATTRIBUTES g_SA ...
0x18003b173  mov     [rbp+arg_10], esi
0x18003b176  mov     byte ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], sil
0x18003b17a  lea     r8, [rbp+arg_10]
0x18003b17e  mov     edx, 3
0x18003b183  lea     rcx, [rbp+SystemTimeAsFileTime]
0x18003b187  call    cs:__imp_?GetPersistentCfgValue@CPersistentConfig@@QEAAHKAEAK@Z; CPersistentConfig::GetPersistentCfgValue(ulong,ulong &)
0x18003b18d  mov     ecx, 8
0x18003b192  mov     eax, [rbp+arg_10]
0x18003b195  test    eax, eax
0x18003b197  jnz     short loc_18003B19B
0x18003b199  mov     eax, ecx
0x18003b19b  mov     cs:?g_dwOldRepositoryVersion@@3KA, eax; ulong g_dwOldRepositoryVersion
0x18003b1a1  mov     cs:?g_dwCurrentRepositoryVersion@@3KA, ecx; ulong g_dwCurrentRepositoryVersion
0x18003b1a7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18003b1ab  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b1af  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b1b5  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18003b1b8  shl     rcx, 20h
0x18003b1bc  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003b1bf  add     rcx, rax; this
0x18003b1c2  mov     cs:?g_nCurrentTime@@3_JA, rcx; __int64 g_nCurrentTime
0x18003b1c9  call    ?GetRepositoryDirectory@CRepository@@IEAAJXZ; CRepository::GetRepositoryDirectory(void)
0x18003b1ce  mov     ebx, esi
0x18003b1d0  test    eax, eax
0x18003b1d2  cmovs   ebx, eax
0x18003b1d5  test    ebx, ebx
0x18003b1d7  js      loc_18003B38B
0x18003b1dd  mov     cs:?g_bShuttingDown@@3_NA, sil; bool g_bShuttingDown
0x18003b1e4  lea     rdx, FileName; unsigned __int16 *
0x18003b1eb  lea     rcx, byte_180058AF8; this
0x18003b1f2  call    ?Initialize@CFileCache@@QEAAJPEBG@Z; CFileCache::Initialize(ushort const *)
0x18003b1f7  mov     ebx, eax
0x18003b1f9  test    eax, eax
0x18003b1fb  jz      loc_18003B2D5
0x18003b201  mov     r15d, 54Eh
0x18003b207  cmp     eax, r15d
0x18003b20a  jnz     short loc_18003B282
0x18003b20c  xor     r8d, r8d; unsigned int
0x18003b20f  mov     dl, 1; bool
0x18003b211  xor     ecx, ecx; int
0x18003b213  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18003b218  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b21e  or      edx, 0FFFFFFFFh
0x18003b221  mov     rcx, rax
0x18003b224  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b231  lea     rax, WPP_GLOBAL_Control
0x18003b238  cmp     rcx, rax
0x18003b23b  jz      short loc_18003B261
0x18003b23d  test    byte ptr [rcx+1Ch], 1
0x18003b241  jz      short loc_18003B261
0x18003b243  cmp     byte ptr [rcx+19h], 2
0x18003b247  jb      short loc_18003B261
0x18003b249  mov     edx, 2Eh ; '.'
0x18003b24e  mov     r9d, r15d
0x18003b251  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b258  mov     rcx, [rcx+10h]
0x18003b25c  call    WPP_SF_d
0x18003b261  lea     r15, WPP_GLOBAL_Control
0x18003b268  mov     ecx, ebx; int
0x18003b26a  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x18003b26f  mov     ebx, eax
0x18003b271  cmp     eax, 80041001h
0x18003b276  jnz     short loc_18003B2CD
0x18003b278  mov     ebx, 80041014h
0x18003b27d  jmp     loc_18003B38B
0x18003b282  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b288  or      edx, 0FFFFFFFFh
0x18003b28b  mov     rcx, rax
0x18003b28e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b294  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b29b  lea     r15, WPP_GLOBAL_Control
0x18003b2a2  cmp     rcx, r15
0x18003b2a5  jz      short loc_18003B268
0x18003b2a7  test    byte ptr [rcx+1Ch], 1
0x18003b2ab  jz      short loc_18003B268
0x18003b2ad  cmp     byte ptr [rcx+19h], 2
0x18003b2b1  jb      short loc_18003B268
0x18003b2b3  mov     edx, 2Fh ; '/'
0x18003b2b8  mov     r9d, ebx
0x18003b2bb  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b2c2  mov     rcx, [rcx+10h]
0x18003b2c6  call    WPP_SF_d
0x18003b2cb  jmp     short loc_18003B268
0x18003b2cd  test    eax, eax
0x18003b2cf  js      loc_18003B38B
0x18003b2d5  lea     rcx, ?g_Glob@@3VCGlobals@@A; this
0x18003b2dc  call    ?Initialize@CGlobals@@QEAAJXZ; CGlobals::Initialize(void)
0x18003b2e1  test    eax, eax
0x18003b2e3  jnz     short loc_18003B278
0x18003b2e5  lea     ecx, [rax+70h]
0x18003b2e8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003b2ee  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003b2f2  test    rax, rax
0x18003b2f5  jz      short loc_18003B30B
0x18003b2f7  mov     r8, rdi; struct CRepository *
0x18003b2fa  mov     rdx, [rdi+10h]; struct CLifeControl *
0x18003b2fe  mov     rcx, rax; this
0x18003b301  call    ??0CNamespaceHandle@@QEAA@PEAVCLifeControl@@PEAVCRepository@@@Z; CNamespaceHandle::CNamespaceHandle(CLifeControl *,CRepository *)
0x18003b306  mov     rcx, rax
0x18003b309  jmp     short loc_18003B30E
0x18003b30b  mov     rcx, rsi
0x18003b30e  mov     cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA, rcx; CNamespaceHandle * g_pSystemClassNamespace
0x18003b315  test    rcx, rcx
0x18003b318  jnz     short loc_18003B321
0x18003b31a  mov     ebx, 80041006h
0x18003b31f  jmp     short loc_18003B38B
0x18003b321  mov     rax, [rcx]
0x18003b324  mov     rax, [rax+8]
0x18003b328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b32d  xor     r8d, r8d; unsigned __int16 *
0x18003b330  lea     rdx, aSystemclass; "__SYSTEMCLASS"
0x18003b337  mov     rcx, cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA; this
0x18003b33e  call    ?Initialize@CNamespaceHandle@@QEAAJPEBG0@Z; CNamespaceHandle::Initialize(ushort const *,ushort const *)
0x18003b343  mov     ebx, eax
0x18003b345  test    eax, eax
0x18003b347  js      short loc_18003B38B
0x18003b349  mov     cs:?g_bShuttingDown@@3_NA, sil; bool g_bShuttingDown
0x18003b350  lea     rax, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18003b357  mov     [rbp+var_30], rax
0x18003b35b  mov     [rbp+var_28], esi
0x18003b35e  lea     rcx, [rbp+var_30]; this
0x18003b362  call    ?Lock@CAutoWriteLock@@QEAA_NXZ; CAutoWriteLock::Lock(void)
0x18003b367  test    al, al
0x18003b369  jnz     short loc_18003B372
0x18003b36b  mov     ebx, 80041001h
0x18003b370  jmp     short loc_18003B37D
0x18003b372  lea     rdx, [rdi+18h]; struct CFlexArray *
0x18003b376  call    ?CreateSystemClasses@CNamespaceHandle@@QEAAJAEAVCFlexArray@@@Z; CNamespaceHandle::CreateSystemClasses(CFlexArray &)
0x18003b37b  mov     ebx, eax
0x18003b37d  lea     rcx, [rbp+var_30]; this
0x18003b381  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18003b386  nop
0x18003b387  test    ebx, ebx
0x18003b389  jns     short loc_18003B3D4
0x18003b38b  mov     cs:?g_bShuttingDown@@3_NA, 1; bool g_bShuttingDown
0x18003b392  xor     edx, edx; unsigned int
0x18003b394  lea     rcx, byte_180058AF8; this
0x18003b39b  call    ?Uninitialize@CFileCache@@QEAAJK@Z; CFileCache::Uninitialize(ulong)
0x18003b3a0  lea     rcx, qword_180058A80; this
0x18003b3a7  call    ?Deinitialize@CForestCache@@QEAAJXZ; CForestCache::Deinitialize(void)
0x18003b3ac  mov     rcx, cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA; CNamespaceHandle * g_pSystemClassNamespace
0x18003b3b3  test    rcx, rcx
0x18003b3b6  jz      short loc_18003B3D0
0x18003b3b8  mov     rax, [rcx]
0x18003b3bb  mov     edx, 1
0x18003b3c0  mov     rax, [rax+20h]
0x18003b3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3c9  mov     cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA, rsi; CNamespaceHandle * g_pSystemClassNamespace
0x18003b3d0  test    ebx, ebx
0x18003b3d2  js      short loc_18003B3DA
0x18003b3d4  mov     [rbp+var_20], 1
0x18003b3d8  jmp     short loc_18003B3EB
0x18003b3da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b3e0  mov     edx, ebx
0x18003b3e2  mov     rcx, rax
0x18003b3e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3f2  cmp     rcx, r15
0x18003b3f5  jz      short loc_18003B41C
0x18003b3f7  test    byte ptr [rcx+1Ch], 1
0x18003b3fb  jz      short loc_18003B41C
0x18003b3fd  cmp     byte ptr [rcx+19h], 2
0x18003b401  jb      short loc_18003B41C
0x18003b403  mov     edx, 30h ; '0'
0x18003b408  mov     r9d, ebx
0x18003b40b  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b412  mov     rcx, [rcx+10h]
0x18003b416  call    WPP_SF_d
0x18003b41b  nop
0x18003b41c  lea     rcx, [rbp+var_20]
0x18003b420  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003b425  mov     eax, ebx
0x18003b427  jmp     short loc_18003B435
0x18003b429  mov     cs:?g_checkpointTimer@@3PEAVCheckPointTimer@@EA, rsi; CheckPointTimer * g_checkpointTimer
0x18003b430  mov     eax, 80041006h
0x18003b435  lea     r11, [rsp+50h+var_s0]
0x18003b43a  mov     rbx, [r11+20h]
0x18003b43e  mov     rsi, [r11+38h]
0x18003b442  mov     rsp, r11
0x18003b445  pop     r15
0x18003b447  pop     rdi
0x18003b448  pop     rbp
0x18003b449  retn
```
