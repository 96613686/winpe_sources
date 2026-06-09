# SNIInitialize

- ea: `0x180156f90`
- end: `0x180157616`
- name: `SNIInitialize`
- size: `1670`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180194370`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180151a60`
- `0x1801525d0`
- `0x1801529a0`
- `0x180153190`
- `0x180153310`
- `0x1801569a0`
- `0x180156f90`
- `0x18015a6f0`
- `0x18015a880`
- `0x18015ba10`
- `0x18015c2b0`
- `0x18015c6e0`
- `0x18015d690`
- `0x18015e230`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x1801572c1`
- `ntdll!VerSetConditionMask` at `0x1801572d0`
- `ntdll!VerSetConditionMask` at `0x1801572e1`
- `ntdll!VerSetConditionMask` at `0x1801572f2`
- `ntdll!VerSetConditionMask` at `0x1801572c1`
- `ntdll!VerSetConditionMask` at `0x1801572d0`
- `ntdll!VerSetConditionMask` at `0x1801572e1`
- `ntdll!VerSetConditionMask` at `0x1801572f2`
- `KERNEL32!GetLastError` at `0x180157183`
- `KERNEL32!GetLastError` at `0x1801571e5`
- `KERNEL32!GetLastError` at `0x1801573a0`
- `KERNEL32!GetLastError` at `0x180157183`
- `KERNEL32!GetLastError` at `0x1801571e5`
- `KERNEL32!GetLastError` at `0x1801573a0`
- `KERNEL32!GetVersionExW` at `0x1801571db`
- `KERNEL32!GetVersionExW` at `0x1801571db`
- `KERNEL32!CreateIoCompletionPort` at `0x18015738e`
- `KERNEL32!CreateIoCompletionPort` at `0x18015738e`
- `KERNEL32!VerifyVersionInfoW` at `0x180157305`
- `KERNEL32!VerifyVersionInfoW` at `0x180157305`
- `KERNEL32!CloseHandle` at `0x18015753a`
- `KERNEL32!CloseHandle` at `0x18015753a`
- `KERNEL32!GetComputerNameW` at `0x180157179`
- `KERNEL32!GetComputerNameW` at `0x180157179`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNIInitialize()
{
  DWORD LastError; // ebx
  struct CCriticalSectionNT_SNI *v1; // rsi
  LastConnectCache *v2; // rcx
  wchar_t *v3; // r8
  __int64 v4; // rdx
  char *v5; // rcx
  struct SNI_NodeIOCompletionQueues *v6; // rax
  ULONGLONG v7; // rax
  ULONGLONG v8; // rax
  ULONGLONG v9; // rax
  ULONGLONG v10; // rax
  BOOL v11; // ebx
  __int64 v12; // r9
  SNI_MemRegions *v13; // rdi
  LastConnectCache *v14; // rcx
  DWORD nSize[4]; // [rsp+40h] [rbp-148h] BYREF
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+50h] [rbp-138h] BYREF

  LastError = 0;
  v1 = g_csInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( _InterlockedIncrement(&gcSNIInitialized) != 1 )
    goto LABEL_60;
  gpmo = g_pMO;
  LastConnectCache::Initialize(v2);
  SNI_MemRegions::s_pClientMemRegions = SNI_MemRegions::Init();
  if ( !SNI_MemRegions::s_pClientMemRegions )
  {
    LastError = 14;
    if ( (bidGblFlags & 2) == 0 || !off_180263CB0[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CB0[0];
    v4 = 1017856;
    v5 = off_180260968[0];
LABEL_51:
    bidTraceW(v5, v4, v3, 8);
LABEL_52:
    SNISetLastError(8, LastError, 50100);
    goto LABEL_53;
  }
  v6 = (struct SNI_NodeIOCompletionQueues *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(
                                              gpmo,
                                              16);
  if ( !v6 )
  {
    SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
    LastError = 14;
    if ( (bidGblFlags & 2) == 0 || !off_180263CB8[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CB8[0];
    v4 = 1033216;
    v5 = off_180260970[0];
    goto LABEL_51;
  }
  *(_QWORD *)v6 = 0;
  *((_QWORD *)v6 + 1) = 0;
  SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = v6;
  LastError = SNI_NodeIOCompletionQueues::Init(v6);
  if ( LastError )
  {
    if ( (bidGblFlags & 2) == 0 || !off_180263CC0[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CC0[0];
    v4 = 1041408;
    v5 = off_180260978[0];
    goto LABEL_51;
  }
  LastError = CCriticalSectionNT_SNI::Initialize(&g_csLocalDBInitialize);
  if ( LastError )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_52;
    if ( off_180263CC8[0] )
      bidTraceW(off_180260980[0], 1052672, off_180263CC8[0], LastError);
    if ( (bidGblFlags & 2) == 0 || !off_180263CD0[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CD0[0];
    v4 = 1053696;
    v5 = off_180260988[0];
    goto LABEL_51;
  }
  nSize[0] = 255;
  if ( !GetComputerNameW(&gwszComputerName, nSize) )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_180263CD8[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CD8[0];
    v4 = 1067008;
    v5 = off_180260990[0];
    goto LABEL_51;
  }
  g_osviSNI.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&g_osviSNI) )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_180263CE0[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CE0[0];
    v4 = 1080320;
    v5 = off_180260998[0];
    goto LABEL_51;
  }
  *(_QWORD *)nSize = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266748[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, DWORD *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      nSize,
      off_180266748[0],
      0);
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_QWORD *)&VersionInformation.dwMajorVersion = 6;
  *(_DWORD *)&VersionInformation.wServicePackMajor = 1;
  v7 = VerSetConditionMask(0, 2u, 3u);
  v8 = VerSetConditionMask(v7, 1u, 3u);
  v9 = VerSetConditionMask(v8, 0x20u, 3u);
  v10 = VerSetConditionMask(v9, 0x10u, 3u);
  v11 = VerifyVersionInfoW(&VersionInformation, 0x33u, v10);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)nSize);
  if ( v11 )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263CE8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_1802609A0[0],
        1087488,
        off_180263CE8[0],
        0);
    Tcp::s_fAutoTuning = 1;
  }
  g_fTerminate = 0;
  ghIoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( !ghIoCompletionPort )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) == 0 || !off_180263CF0[0] )
      goto LABEL_52;
    SniErrorIdFromStringId(0xC3B4u);
    v3 = off_180263CF0[0];
    v4 = 1113088;
    v5 = off_1802609A8[0];
    goto LABEL_51;
  }
  LastError = SNICreateWaitThread((LPTHREAD_START_ROUTINE)SNIAsyncWait, 0);
  if ( LastError )
  {
LABEL_53:
    if ( g_csLocalDBInitialize )
    {
      (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_csLocalDBInitialize)(
        g_csLocalDBInitialize,
        1);
      g_csLocalDBInitialize = 0;
    }
    if ( ghIoCompletionPort )
    {
      CloseHandle(ghIoCompletionPort);
      ghIoCompletionPort = 0;
    }
    v13 = SNI_MemRegions::s_pClientMemRegions;
    if ( SNI_MemRegions::s_pClientMemRegions )
    {
      SNI_MemRegions::Flush(SNI_MemRegions::s_pClientMemRegions);
      SNI_MemRegions::`scalar deleting destructor'(v13, 1u);
      SNI_MemRegions::s_lMaxMemRegionProvider = 0;
      SNI_MemRegions::s_pClientMemRegions = 0;
    }
    SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues);
    SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
    LastConnectCache::Shutdown(v14);
    _InterlockedDecrement(&gcSNIInitialized);
    goto LABEL_60;
  }
  gClusApi = 0;
  qword_18024F338 = 0;
  *(_QWORD *)nSize = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266710[0] )
    bidScopeEnterW(nSize, off_180266710[0], &gClusApi, v12);
  LoadClusterResourceLibraries((struct CLUSTER_API *)&gClusApi);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263C08[0] )
    bidTraceW(off_1802608C0[0], 280576, off_180263C08[0], 0);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)nSize);
  LastError = 0;
  SNI_Provider::InitProviders();
LABEL_60:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v1 + 2) + 32LL) + 24LL))(*((_QWORD *)v1 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263CF8[0] )
    bidTraceW(off_1802609B0[0], 1188864, off_180263CF8[0], LastError);
  return LastError;
}

```

## disassembly

```asm
0x180156f90  mov     [rsp+arg_0], rbx
0x180156f95  mov     [rsp+arg_8], rbp
0x180156f9a  mov     [rsp+arg_10], rsi
0x180156f9f  mov     [rsp+arg_18], rdi
0x180156fa4  push    r14
0x180156fa6  sub     rsp, 180h
0x180156fad  mov     rax, cs:__security_cookie
0x180156fb4  xor     rax, rsp
0x180156fb7  mov     [rsp+188h+var_18], rax
0x180156fbf  xor     ebp, ebp
0x180156fc1  mov     ebx, ebp
0x180156fc3  mov     rsi, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x180156fca  mov     rcx, [rsi+10h]
0x180156fce  add     rcx, 20h ; ' '
0x180156fd2  mov     rax, [rcx]
0x180156fd5  mov     rax, [rax+8]
0x180156fd9  call    cs:__guard_dispatch_icall_fptr
0x180156fdf  mov     r14d, 1
0x180156fe5  mov     eax, r14d
0x180156fe8  lock xadd cs:?gcSNIInitialized@@3JA, eax; long gcSNIInitialized
0x180156ff0  inc     eax
0x180156ff2  cmp     eax, r14d
0x180156ff5  jnz     loc_180157597
0x180156ffb  mov     rax, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180157002  mov     cs:?gpmo@@3PEAUISOSHost_MemObj@@EA, rax; ISOSHost_MemObj * gpmo
0x180157009  call    ?Initialize@LastConnectCache@@YAXXZ; LastConnectCache::Initialize(void)
0x18015700e  call    ?Init@SNI_MemRegions@@SAPEAV1@XZ; SNI_MemRegions::Init(void)
0x180157013  mov     cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA, rax; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x18015701a  test    rax, rax
0x18015701d  jnz     short loc_180157063
0x18015701f  mov     ebx, 0Eh
0x180157024  test    byte ptr cs:_bidGblFlags, 2
0x18015702b  jz      loc_1801574FA
0x180157031  mov     rax, cs:off_180263CB0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x180157038  test    rax, rax
0x18015703b  jz      loc_1801574FA
0x180157041  mov     ecx, 0C3B4h; unsigned int
0x180157046  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015704b  mov     r8, cs:off_180263CB0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x180157052  mov     edx, 0F8800h
0x180157057  mov     rcx, cs:off_180260968; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015705e  jmp     loc_1801574E7
0x180157063  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x18015706a  mov     rax, [rcx]
0x18015706d  mov     edx, 10h
0x180157072  mov     rax, [rax+58h]
0x180157076  call    cs:__guard_dispatch_icall_fptr
0x18015707c  test    rax, rax
0x18015707f  jz      loc_1801574A9
0x180157085  mov     [rax], rbp
0x180157088  mov     [rax+8], rbp
0x18015708c  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, rax; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x180157093  mov     rcx, rax; this
0x180157096  call    ?Init@SNI_NodeIOCompletionQueues@@QEAAKXZ; SNI_NodeIOCompletionQueues::Init(void)
0x18015709b  mov     ebx, eax
0x18015709d  test    eax, eax
0x18015709f  jz      short loc_1801570E0
0x1801570a1  test    byte ptr cs:_bidGblFlags, 2
0x1801570a8  jz      loc_1801574FA
0x1801570ae  mov     rcx, cs:off_180263CC0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801570b5  test    rcx, rcx
0x1801570b8  jz      loc_1801574FA
0x1801570be  mov     ecx, 0C3B4h; unsigned int
0x1801570c3  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801570c8  mov     r8, cs:off_180263CC0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801570cf  mov     edx, 0FE400h
0x1801570d4  mov     rcx, cs:off_180260978; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801570db  jmp     loc_1801574E7
0x1801570e0  lea     rcx, ?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; struct CCriticalSectionNT_SNI **
0x1801570e7  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x1801570ec  mov     ebx, eax
0x1801570ee  test    eax, eax
0x1801570f0  jz      short loc_180157165
0x1801570f2  test    byte ptr cs:_bidGblFlags, 2
0x1801570f9  jz      loc_1801574FA
0x1801570ff  mov     rax, cs:off_180263CC8; "<SNIInitialize|ERR|SNI> Initialize g_cs"...
0x180157106  test    rax, rax
0x180157109  jz      short loc_180157126
0x18015710b  mov     r9d, ebx
0x18015710e  mov     r8, cs:off_180263CC8; "<SNIInitialize|ERR|SNI> Initialize g_cs"...
0x180157115  mov     edx, 101000h
0x18015711a  mov     rcx, cs:off_180260980; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180157121  call    _bidTraceW
0x180157126  test    byte ptr cs:_bidGblFlags, 2
0x18015712d  jz      loc_1801574FA
0x180157133  mov     rax, cs:off_180263CD0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x18015713a  test    rax, rax
0x18015713d  jz      loc_1801574FA
0x180157143  mov     ecx, 0C3B4h; unsigned int
0x180157148  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015714d  mov     r8, cs:off_180263CD0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x180157154  mov     edx, 101400h
0x180157159  mov     rcx, cs:off_180260988; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180157160  jmp     loc_1801574E7
0x180157165  mov     [rsp+188h+nSize], 0FFh
0x18015716d  lea     rdx, [rsp+188h+nSize]; nSize
0x180157172  lea     rcx, ?gwszComputerName@@3PA_WA; lpBuffer
0x180157179  call    cs:__imp_GetComputerNameW
0x18015717f  test    eax, eax
0x180157181  jnz     short loc_1801571CA
0x180157183  call    cs:__imp_GetLastError
0x180157189  mov     ebx, eax
0x18015718b  test    byte ptr cs:_bidGblFlags, 2
0x180157192  jz      loc_1801574FA
0x180157198  mov     rax, cs:off_180263CD8; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x18015719f  test    rax, rax
0x1801571a2  jz      loc_1801574FA
0x1801571a8  mov     ecx, 0C3B4h; unsigned int
0x1801571ad  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801571b2  mov     r8, cs:off_180263CD8; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801571b9  mov     edx, 104800h
0x1801571be  mov     rcx, cs:off_180260990; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801571c5  jmp     loc_1801574E7
0x1801571ca  mov     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwOSVersionInfoSize, 11Ch; _OSVERSIONINFOEXW g_osviSNI ...
0x1801571d4  lea     rcx, ?g_osviSNI@@3U_OSVERSIONINFOEXW@@A; lpVersionInformation
0x1801571db  call    cs:__imp_GetVersionExW
0x1801571e1  test    eax, eax
0x1801571e3  jnz     short loc_18015722C
0x1801571e5  call    cs:__imp_GetLastError
0x1801571eb  mov     ebx, eax
0x1801571ed  test    byte ptr cs:_bidGblFlags, 2
0x1801571f4  jz      loc_1801574FA
0x1801571fa  mov     rax, cs:off_180263CE0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x180157201  test    rax, rax
0x180157204  jz      loc_1801574FA
0x18015720a  mov     ecx, 0C3B4h; unsigned int
0x18015720f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180157214  mov     r8, cs:off_180263CE0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x18015721b  mov     edx, 107C00h
0x180157220  mov     rcx, cs:off_180260998; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180157227  jmp     loc_1801574E7
0x18015722c  mov     qword ptr [rsp+188h+nSize], 0FFFFFFFFFFFFFFFFh
0x180157235  mov     eax, cs:_bidGblFlags
0x18015723b  and     eax, 20004h
0x180157240  cmp     eax, 20004h
0x180157245  jnz     short loc_18015728C
0x180157247  mov     rax, cs:off_180266748; "<FVistaSP1orLater|API|SNI> \n"
0x18015724e  test    rax, rax
0x180157251  jz      short loc_18015728C
0x180157253  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015725b  jz      short loc_18015728C
0x18015725d  mov     rax, cs:off_180248060
0x180157264  mov     [rsp+188h+var_160], rbp
0x180157269  mov     rcx, cs:off_180266748; "<FVistaSP1orLater|API|SNI> \n"
0x180157270  mov     [rsp+188h+var_168], rcx
0x180157275  lea     r9, [rsp+188h+nSize]
0x18015727a  xor     r8d, r8d
0x18015727d  xor     edx, edx
0x18015727f  mov     rcx, cs:_bidID
0x180157286  call    cs:__guard_dispatch_icall_fptr
0x18015728c  xor     edx, edx; Val
0x18015728e  mov     r8d, 11Ch; Size
0x180157294  lea     rcx, [rsp+188h+VersionInformation]; void *
0x180157299  call    memset_0
0x18015729e  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1801572a6  mov     qword ptr [rsp+188h+VersionInformation.dwMajorVersion], 6
0x1801572af  mov     dword ptr [rsp+188h+VersionInformation.wServicePackMajor], r14d
0x1801572b7  mov     r8b, 3; Condition
0x1801572ba  mov     edx, 2; TypeMask
0x1801572bf  xor     ecx, ecx; ConditionMask
0x1801572c1  call    cs:__imp_VerSetConditionMask
0x1801572c7  mov     r8b, 3; Condition
0x1801572ca  mov     edx, r14d; TypeMask
0x1801572cd  mov     rcx, rax; ConditionMask
0x1801572d0  call    cs:__imp_VerSetConditionMask
0x1801572d6  mov     r8b, 3; Condition
0x1801572d9  mov     edx, 20h ; ' '; TypeMask
0x1801572de  mov     rcx, rax; ConditionMask
0x1801572e1  call    cs:__imp_VerSetConditionMask
0x1801572e7  mov     r8b, 3; Condition
0x1801572ea  mov     edx, 10h; TypeMask
0x1801572ef  mov     rcx, rax; ConditionMask
0x1801572f2  call    cs:__imp_VerSetConditionMask
0x1801572f8  mov     r8, rax; dwlConditionMask
0x1801572fb  mov     edx, 33h ; '3'; dwTypeMask
0x180157300  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x180157305  call    cs:__imp_VerifyVersionInfoW
0x18015730b  mov     ebx, eax
0x18015730d  lea     rcx, [rsp+188h+nSize]; this
0x180157312  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180157317  nop
0x180157318  test    ebx, ebx
0x18015731a  jz      short loc_180157378
0x18015731c  mov     eax, cs:_bidGblFlags
0x180157322  and     eax, 20002h
0x180157327  cmp     eax, 20002h
0x18015732c  jnz     short loc_180157371
0x18015732e  mov     rax, cs:off_180263CE8; "<SNIInitialize|SNI> Vista versions whic"...
0x180157335  test    rax, rax
0x180157338  jz      short loc_180157371
0x18015733a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180157342  jz      short loc_180157371
0x180157344  mov     rax, cs:off_180248050
0x18015734b  mov     [rsp+188h+var_168], rbp
0x180157350  mov     r9, cs:off_180263CE8; "<SNIInitialize|SNI> Vista versions whic"...
0x180157357  mov     r8d, 109800h
0x18015735d  mov     rdx, cs:off_1802609A0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180157364  mov     rcx, cs:_bidID
0x18015736b  call    cs:__guard_dispatch_icall_fptr
0x180157371  mov     cs:?s_fAutoTuning@Tcp@@2HA, r14d; int Tcp::s_fAutoTuning
0x180157378  mov     cs:?g_fTerminate@@3_NA, 0; bool g_fTerminate
0x18015737f  xor     r9d, r9d; NumberOfConcurrentThreads
0x180157382  xor     r8d, r8d; CompletionKey
0x180157385  xor     edx, edx; ExistingCompletionPort
0x180157387  mov     rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18015738e  call    cs:__imp_CreateIoCompletionPort
0x180157394  mov     cs:?ghIoCompletionPort@@3PEAXEA, rax; void * ghIoCompletionPort
0x18015739b  test    rax, rax
0x18015739e  jnz     short loc_1801573E7
0x1801573a0  call    cs:__imp_GetLastError
0x1801573a6  mov     ebx, eax
0x1801573a8  test    byte ptr cs:_bidGblFlags, 2
0x1801573af  jz      loc_1801574FA
0x1801573b5  mov     rax, cs:off_180263CF0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801573bc  test    rax, rax
0x1801573bf  jz      loc_1801574FA
0x1801573c5  mov     ecx, 0C3B4h; unsigned int
0x1801573ca  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801573cf  mov     r8, cs:off_180263CF0; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801573d6  mov     edx, 10FC00h
0x1801573db  mov     rcx, cs:off_1802609A8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801573e2  jmp     loc_1801574E7
0x1801573e7  xor     edx, edx; lpParameter
0x1801573e9  lea     rcx, ?SNIAsyncWait@@YAKPEAX@Z; lpStartAddress
0x1801573f0  call    SNICreateWaitThread
0x1801573f5  mov     ebx, eax
0x1801573f7  test    eax, eax
0x1801573f9  jnz     loc_18015750C
0x1801573ff  mov     cs:?gClusApi@@3UCLUSTER_API@@A, rbp; CLUSTER_API gClusApi
0x180157406  mov     cs:qword_18024F338, rbp
0x18015740d  mov     qword ptr [rsp+188h+nSize], 0FFFFFFFFFFFFFFFFh
0x180157416  mov     eax, cs:_bidGblFlags
0x18015741c  and     eax, 20004h
0x180157421  cmp     eax, 20004h
0x180157426  jnz     short loc_18015744C
0x180157428  mov     rax, cs:off_180266710; "<LoadClusterResourceLibraryIfNeeded|API"...
0x18015742f  test    rax, rax
0x180157432  jz      short loc_18015744C
0x180157434  lea     r8, ?gClusApi@@3UCLUSTER_API@@A; CLUSTER_API gClusApi
0x18015743b  mov     rdx, cs:off_180266710; "<LoadClusterResourceLibraryIfNeeded|API"...
0x180157442  lea     rcx, [rsp+188h+nSize]
0x180157447  call    _bidScopeEnterW
0x18015744c  lea     rcx, ?gClusApi@@3UCLUSTER_API@@A; struct CLUSTER_API *
0x180157453  call    ?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z; LoadClusterResourceLibraries(CLUSTER_API *)
0x180157458  mov     eax, cs:_bidGblFlags
0x18015745e  and     eax, 20002h
0x180157463  cmp     eax, 20002h
0x180157468  jnz     short loc_180157492
0x18015746a  mov     rax, cs:off_180263C08; "<LoadClusterResourceLibraryIfNeeded|RET"...
0x180157471  test    rax, rax
0x180157474  jz      short loc_180157492
0x180157476  xor     r9d, r9d
0x180157479  mov     r8, cs:off_180263C08; "<LoadClusterResourceLibraryIfNeeded|RET"...
0x180157480  mov     edx, 44800h
0x180157485  mov     rcx, cs:off_1802608C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015748c  call    _bidTraceW
0x180157491  nop
0x180157492  lea     rcx, [rsp+188h+nSize]; this
0x180157497  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015749c  nop
0x18015749d  mov     ebx, ebp
0x18015749f  call    ?InitProviders@SNI_Provider@@SAXXZ; SNI_Provider::InitProviders(void)
0x1801574a4  jmp     loc_180157597
0x1801574a9  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, rbp; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x1801574b0  mov     ebx, 0Eh
0x1801574b5  test    byte ptr cs:_bidGblFlags, 2
0x1801574bc  jz      short loc_1801574FA
0x1801574be  mov     rax, cs:off_180263CB8; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801574c5  test    rax, rax
0x1801574c8  jz      short loc_1801574FA
0x1801574ca  mov     ecx, 0C3B4h; unsigned int
0x1801574cf  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801574d4  mov     r8, cs:off_180263CB8; "<SNIInitialize|ERR|SNI> ProviderNum: %d"...
0x1801574db  mov     edx, 0FC400h
0x1801574e0  mov     rcx, cs:off_180260970; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801574e7  mov     dword ptr [rsp+188h+var_160], ebx
0x1801574eb  mov     dword ptr [rsp+188h+var_168], eax
0x1801574ef  mov     r9d, 8
0x1801574f5  call    _bidTraceW
0x1801574fa  mov     r8d, 0C3B4h
0x180157500  mov     edx, ebx
0x180157502  mov     ecx, 8
0x180157507  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015750c  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x180157513  test    rcx, rcx
0x180157516  jz      short loc_18015752E
0x180157518  mov     rax, [rcx]
0x18015751b  mov     edx, r14d
0x18015751e  mov     rax, [rax]
0x180157521  call    cs:__guard_dispatch_icall_fptr
0x180157527  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, rbp; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x18015752e  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x180157535  test    rcx, rcx
0x180157538  jz      short loc_180157547
0x18015753a  call    cs:__imp_CloseHandle
0x180157540  mov     cs:?ghIoCompletionPort@@3PEAXEA, rbp; void * ghIoCompletionPort
0x180157547  mov     rdi, cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x18015754e  test    rdi, rdi
0x180157551  jz      short loc_180157578
0x180157553  mov     rcx, rdi; struct SNI_MemRegions *
  ... truncated ...
```
