# SNIInitializeEx

- ea: `0x1004171e8`
- end: `0x10041775f`
- name: `SNIInitializeEx`
- size: `1399`
- prototype: `__int64 __fastcall(enum ProviderNum *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x10045ff60`

## callees

- `0x100412dc4`
- `0x1004136ac`
- `0x100413d10`
- `0x100414170`
- `0x1004167a4`
- `0x100416c30`
- `0x1004171e8`
- `0x10041a108`
- `0x1004310dc`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043edc8`
- `0x10043f80c`
- `0x10044b004`
- `0x10044b2e0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x100417436`
- `KERNEL32!GetComputerNameW` at `0x100417436`
- `KERNEL32!GetVersionExW` at `0x100417498`
- `KERNEL32!GetVersionExW` at `0x100417498`
- `KERNEL32!CreateEventW` at `0x10041728e`
- `KERNEL32!CreateEventW` at `0x10041728e`
- `KERNEL32!CreateIoCompletionPort` at `0x10041755b`
- `KERNEL32!CreateIoCompletionPort` at `0x10041755b`
- `KERNEL32!GetLastError` at `0x1004172a0`
- `KERNEL32!GetLastError` at `0x100417440`
- `KERNEL32!GetLastError` at `0x1004174a2`
- `KERNEL32!GetLastError` at `0x10041756d`
- `KERNEL32!GetLastError` at `0x10041767c`
- `KERNEL32!GetLastError` at `0x1004172a0`
- `KERNEL32!GetLastError` at `0x100417440`
- `KERNEL32!GetLastError` at `0x1004174a2`
- `KERNEL32!GetLastError` at `0x10041756d`
- `KERNEL32!GetLastError` at `0x10041767c`
- `KERNEL32!CloseHandle` at `0x100417664`
- `KERNEL32!CloseHandle` at `0x1004176b0`
- `KERNEL32!CloseHandle` at `0x100417664`
- `KERNEL32!CloseHandle` at `0x1004176b0`

## pseudocode

```c
__int64 __fastcall SNIInitializeEx(enum ProviderNum *a1, unsigned int a2, int a3)
{
  struct CCriticalSectionNT_SNI *v6; // r14
  DWORD ClusterResourceLibraryIfNeeded; // ebx
  LastConnectCache *v8; // rcx
  wchar_t *v9; // r8
  __int64 v10; // rdx
  struct SNI_NodeIOCompletionQueues *v11; // rax
  wchar_t *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  BOOL v15; // eax
  LastConnectCache *v16; // rcx
  _QWORD v18[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+88h] [rbp+20h] BYREF

  v18[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7760[0] )
    bidScopeEnterW(v18, off_1005E7760[0], a1);
  v6 = g_csInitialize;
  ClusterResourceLibraryIfNeeded = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( _InterlockedIncrement(&gcSNIInitialized) == 1 )
  {
    hObject = CreateEventW(0, 1, 1, 0);
    if ( hObject )
      ghWaitClose = 0;
    else
      GetLastError();
    gpmo = (struct ISOSHost_MemObj *)g_pMO;
    g_fSandbox = a3;
    if ( !a3 )
      LastConnectCache::Initialize(v8);
    SNI_MemRegions::s_pClientMemRegions = SNI_MemRegions::Init();
    if ( !SNI_MemRegions::s_pClientMemRegions )
    {
      ClusterResourceLibraryIfNeeded = 14;
      if ( (bidGblFlags & 2) == 0 || !off_1005E4588[0] )
        goto LABEL_52;
      SniErrorIdFromStringId(0xC3B4u);
      v9 = off_1005E4588[0];
      v10 = 1052672;
LABEL_51:
      bidTraceW(0, v10, v9, 9);
LABEL_52:
      v14 = 14;
      goto LABEL_53;
    }
    v11 = (struct SNI_NodeIOCompletionQueues *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(
                                                 gpmo,
                                                 16);
    if ( !v11 )
    {
      SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
      ClusterResourceLibraryIfNeeded = 14;
      if ( (bidGblFlags & 2) == 0 || !off_1005E4590[0] )
        goto LABEL_52;
      SniErrorIdFromStringId(0xC3B4u);
      v9 = off_1005E4590[0];
      v10 = 1068032;
      goto LABEL_51;
    }
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 1) = 0;
    SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = v11;
    ClusterResourceLibraryIfNeeded = SNI_NodeIOCompletionQueues::Init(v11);
    if ( ClusterResourceLibraryIfNeeded )
    {
      if ( (bidGblFlags & 2) == 0 || !off_1005E4598[0] )
        goto LABEL_20;
      SniErrorIdFromStringId(0xC3B4u);
      v12 = off_1005E4598[0];
      v13 = 1076224;
    }
    else
    {
      ClusterResourceLibraryIfNeeded = CCriticalSectionNT_SNI::Initialize(&g_csLocalDBInitialize);
      if ( ClusterResourceLibraryIfNeeded )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E45A0[0] )
          bidTraceW(0, 1087488, off_1005E45A0[0], ClusterResourceLibraryIfNeeded);
        if ( (bidGblFlags & 2) == 0 || !off_1005E45A8[0] )
          goto LABEL_20;
        SniErrorIdFromStringId(0xC3B4u);
        v12 = off_1005E45A8[0];
        v13 = 1088512;
      }
      else
      {
        nSize = 255;
        if ( GetComputerNameW(&gwszComputerName, &nSize) )
        {
          g_osviSNI.dwOSVersionInfoSize = 284;
          if ( GetVersionExW(&g_osviSNI) )
          {
            if ( (unsigned int)FVistaSP1orLater() )
            {
              if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E45C0[0] && bidID != -1 )
                ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
                  bidID,
                  0,
                  1122304,
                  off_1005E45C0[0],
                  0);
              Tcp::s_fAutoTuning = 1;
            }
            g_fTerminate = 0;
            ghIoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
            if ( ghIoCompletionPort )
            {
              ClusterResourceLibraryIfNeeded = SNICreateWaitThread((LPTHREAD_START_ROUTINE)SNIAsyncWait, 0);
              if ( !ClusterResourceLibraryIfNeeded )
              {
                gClusApi = 0;
                qword_1005D8078 = 0;
                ClusterResourceLibraryIfNeeded = LoadClusterResourceLibraryIfNeeded((struct CLUSTER_API *)&gClusApi);
                DNSCache::Initialize();
                SNI_Provider::InitProviders(a1, a2);
                goto LABEL_64;
              }
              goto LABEL_54;
            }
            ClusterResourceLibraryIfNeeded = GetLastError();
            if ( (bidGblFlags & 2) == 0 || !off_1005E45C8[0] )
              goto LABEL_20;
            SniErrorIdFromStringId(0xC3B4u);
            v12 = off_1005E45C8[0];
            v13 = 1148928;
          }
          else
          {
            ClusterResourceLibraryIfNeeded = GetLastError();
            if ( (bidGblFlags & 2) == 0 || !off_1005E45B8[0] )
              goto LABEL_20;
            SniErrorIdFromStringId(0xC3B4u);
            v12 = off_1005E45B8[0];
            v13 = 1115136;
          }
        }
        else
        {
          ClusterResourceLibraryIfNeeded = GetLastError();
          if ( (bidGblFlags & 2) == 0 || !off_1005E45B0[0] )
            goto LABEL_20;
          SniErrorIdFromStringId(0xC3B4u);
          v12 = off_1005E45B0[0];
          v13 = 1101824;
        }
      }
    }
    bidTraceW(0, v13, v12, 9);
LABEL_20:
    v14 = ClusterResourceLibraryIfNeeded;
LABEL_53:
    SNISetLastError(9, v14, 50100);
LABEL_54:
    if ( hObject )
    {
      v15 = CloseHandle(hObject);
      hObject = 0;
      ghWaitClose = 0;
      if ( !v15 )
        GetLastError();
    }
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
    if ( SNI_MemRegions::s_pClientMemRegions )
    {
      SNI_MemRegions::Terminate(SNI_MemRegions::s_pClientMemRegions);
      SNI_MemRegions::s_pClientMemRegions = 0;
    }
    SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues);
    SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
    LastConnectCache::Shutdown(v16);
    _InterlockedDecrement(&gcSNIInitialized);
  }
LABEL_64:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v6 + 2) + 32LL) + 24LL))(*((_QWORD *)v6 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E45D0[0] )
    bidTraceW(0, 1227776, off_1005E45D0[0], ClusterResourceLibraryIfNeeded);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v18);
  return ClusterResourceLibraryIfNeeded;
}

```

## disassembly

```asm
0x1004171e8  mov     r11, rsp
0x1004171eb  mov     [r11+8], rbx
0x1004171ef  mov     [r11+10h], rbp
0x1004171f3  push    rsi
0x1004171f4  push    rdi
0x1004171f5  push    r12
0x1004171f7  push    r14
0x1004171f9  push    r15
0x1004171fb  sub     rsp, 40h
0x1004171ff  mov     eax, cs:_bidGblFlags
0x100417205  mov     rbp, rcx
0x100417208  or      qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x10041720d  mov     ecx, 20004h
0x100417212  and     eax, ecx
0x100417214  xor     r15d, r15d
0x100417217  mov     edi, r8d
0x10041721a  mov     esi, edx
0x10041721c  cmp     eax, ecx
0x10041721e  jnz     short loc_100417247
0x100417220  mov     rax, cs:off_1005E7760; "<SNIInitializeEx|API|SNI> rgProviders: "...
0x100417227  test    rax, rax
0x10041722a  jz      short loc_100417247
0x10041722c  mov     dword ptr [rsp+68h+var_48], r8d
0x100417231  lea     rcx, [r11-38h]
0x100417235  mov     r9d, edx
0x100417238  mov     r8, rbp
0x10041723b  mov     rdx, cs:off_1005E7760; "<SNIInitializeEx|API|SNI> rgProviders: "...
0x100417242  call    _bidScopeEnterW
0x100417247  mov     r14, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x10041724e  mov     ebx, r15d
0x100417251  mov     rcx, [r14+10h]
0x100417255  add     rcx, 20h ; ' '
0x100417259  mov     rax, [rcx]
0x10041725c  mov     rax, [rax+8]
0x100417260  call    cs:__guard_dispatch_icall_fptr
0x100417266  mov     r12d, 1
0x10041726c  mov     eax, r12d
0x10041726f  lock xadd cs:?gcSNIInitialized@@3JA, eax; long gcSNIInitialized
0x100417277  add     eax, r12d
0x10041727a  cmp     eax, r12d
0x10041727d  jnz     loc_1004176F4
0x100417283  xor     r9d, r9d; lpName
0x100417286  mov     r8d, r12d; bInitialState
0x100417289  mov     edx, r12d; bManualReset
0x10041728c  xor     ecx, ecx; lpEventAttributes
0x10041728e  call    cs:__imp_CreateEventW
0x100417294  mov     cs:hObject, rax
0x10041729b  test    rax, rax
0x10041729e  jnz     short loc_1004172A8
0x1004172a0  call    cs:__imp_GetLastError
0x1004172a6  jmp     short loc_1004172AF
0x1004172a8  mov     cs:?ghWaitClose@@3VEventHandle@@A, r15; EventHandle ghWaitClose
0x1004172af  mov     rax, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004172b6  mov     cs:?gpmo@@3PEAUISOSHost_MemObj@@EA, rax; ISOSHost_MemObj * gpmo
0x1004172bd  mov     cs:?g_fSandbox@@3HA, edi; int g_fSandbox
0x1004172c3  test    edi, edi
0x1004172c5  jnz     short loc_1004172CC
0x1004172c7  call    ?Initialize@LastConnectCache@@YAXXZ; LastConnectCache::Initialize(void)
0x1004172cc  call    ?Init@SNI_MemRegions@@SAPEAV1@XZ; SNI_MemRegions::Init(void)
0x1004172d1  mov     cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA, rax; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x1004172d8  test    rax, rax
0x1004172db  jnz     short loc_10041731F
0x1004172dd  test    byte ptr cs:_bidGblFlags, 2
0x1004172e4  lea     ebp, [rax+0Eh]
0x1004172e7  mov     ebx, ebp
0x1004172e9  lea     esi, [rax+9]
0x1004172ec  mov     edi, 0C3B4h
0x1004172f1  jz      loc_10041764C
0x1004172f7  mov     rax, cs:off_1005E4588; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x1004172fe  test    rax, rax
0x100417301  jz      loc_10041764C
0x100417307  mov     ecx, edi; unsigned int
0x100417309  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041730e  mov     r8, cs:off_1005E4588; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417315  mov     edx, 101000h
0x10041731a  jmp     loc_10041763A
0x10041731f  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100417326  mov     edx, 10h
0x10041732b  mov     rax, [rcx]
0x10041732e  mov     rax, [rax+58h]
0x100417332  call    cs:__guard_dispatch_icall_fptr
0x100417338  test    rax, rax
0x10041733b  jz      loc_1004175FC
0x100417341  mov     [rax], r15
0x100417344  mov     rcx, rax; this
0x100417347  mov     [rax+8], r15
0x10041734b  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, rax; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x100417352  call    ?Init@SNI_NodeIOCompletionQueues@@QEAAKXZ; SNI_NodeIOCompletionQueues::Init(void)
0x100417357  mov     ebx, eax
0x100417359  test    eax, eax
0x10041735b  jz      short loc_1004173A8
0x10041735d  test    byte ptr cs:_bidGblFlags, 2
0x100417364  mov     edi, 0C3B4h
0x100417369  mov     esi, 9
0x10041736e  jz      short loc_1004173A1
0x100417370  mov     rcx, cs:off_1005E4598; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417377  test    rcx, rcx
0x10041737a  jz      short loc_1004173A1
0x10041737c  mov     ecx, edi; unsigned int
0x10041737e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100417383  mov     r8, cs:off_1005E4598; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x10041738a  mov     edx, 106C00h
0x10041738f  mov     [rsp+68h+var_40], ebx
0x100417393  mov     r9d, esi
0x100417396  xor     ecx, ecx
0x100417398  mov     dword ptr [rsp+68h+var_48], eax
0x10041739c  call    _bidTraceW
0x1004173a1  mov     edx, ebx
0x1004173a3  jmp     loc_10041764E
0x1004173a8  lea     rcx, ?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; struct CCriticalSectionNT_SNI **
0x1004173af  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x1004173b4  mov     ebx, eax
0x1004173b6  test    eax, eax
0x1004173b8  jz      short loc_10041741C
0x1004173ba  test    byte ptr cs:_bidGblFlags, 2
0x1004173c1  jz      short loc_1004173E5
0x1004173c3  mov     rax, cs:off_1005E45A0; "<SNIInitializeEx|ERR|SNI> Initialize g_"...
0x1004173ca  test    rax, rax
0x1004173cd  jz      short loc_1004173E5
0x1004173cf  mov     r8, cs:off_1005E45A0; "<SNIInitializeEx|ERR|SNI> Initialize g_"...
0x1004173d6  mov     r9d, ebx
0x1004173d9  mov     edx, 109800h
0x1004173de  xor     ecx, ecx
0x1004173e0  call    _bidTraceW
0x1004173e5  test    byte ptr cs:_bidGblFlags, 2
0x1004173ec  mov     edi, 0C3B4h
0x1004173f1  mov     esi, 9
0x1004173f6  jz      short loc_1004173A1
0x1004173f8  mov     rax, cs:off_1005E45A8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x1004173ff  test    rax, rax
0x100417402  jz      short loc_1004173A1
0x100417404  mov     ecx, edi; unsigned int
0x100417406  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041740b  mov     r8, cs:off_1005E45A8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417412  mov     edx, 109C00h
0x100417417  jmp     loc_10041738F
0x10041741c  lea     rdx, [rsp+68h+nSize]; nSize
0x100417424  mov     [rsp+68h+nSize], 0FFh
0x10041742f  lea     rcx, ?gwszComputerName@@3PAGA; lpBuffer
0x100417436  call    cs:__imp_GetComputerNameW
0x10041743c  test    eax, eax
0x10041743e  jnz     short loc_100417487
0x100417440  call    cs:__imp_GetLastError
0x100417446  test    byte ptr cs:_bidGblFlags, 2
0x10041744d  mov     edi, 0C3B4h
0x100417452  mov     ebx, eax
0x100417454  mov     esi, 9
0x100417459  jz      loc_1004173A1
0x10041745f  mov     rax, cs:off_1005E45B0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417466  test    rax, rax
0x100417469  jz      loc_1004173A1
0x10041746f  mov     ecx, edi; unsigned int
0x100417471  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100417476  mov     r8, cs:off_1005E45B0; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x10041747d  mov     edx, 10D000h
0x100417482  jmp     loc_10041738F
0x100417487  lea     rcx, ?g_osviSNI@@3U_OSVERSIONINFOEXW@@A; lpVersionInformation
0x10041748e  mov     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwOSVersionInfoSize, 11Ch; _OSVERSIONINFOEXW g_osviSNI ...
0x100417498  call    cs:__imp_GetVersionExW
0x10041749e  test    eax, eax
0x1004174a0  jnz     short loc_1004174E9
0x1004174a2  call    cs:__imp_GetLastError
0x1004174a8  test    byte ptr cs:_bidGblFlags, 2
0x1004174af  mov     edi, 0C3B4h
0x1004174b4  mov     ebx, eax
0x1004174b6  mov     esi, 9
0x1004174bb  jz      loc_1004173A1
0x1004174c1  mov     rax, cs:off_1005E45B8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x1004174c8  test    rax, rax
0x1004174cb  jz      loc_1004173A1
0x1004174d1  mov     ecx, edi; unsigned int
0x1004174d3  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004174d8  mov     r8, cs:off_1005E45B8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x1004174df  mov     edx, 110400h
0x1004174e4  jmp     loc_10041738F
0x1004174e9  call    ?FVistaSP1orLater@@YAHXZ; FVistaSP1orLater(void)
0x1004174ee  test    eax, eax
0x1004174f0  jz      short loc_100417548
0x1004174f2  mov     eax, cs:_bidGblFlags
0x1004174f8  mov     ecx, 20002h
0x1004174fd  and     eax, ecx
0x1004174ff  cmp     eax, ecx
0x100417501  jnz     short loc_100417541
0x100417503  mov     rax, cs:off_1005E45C0; "<SNIInitializeEx|SNI> Vista versions wh"...
0x10041750a  test    rax, rax
0x10041750d  jz      short loc_100417541
0x10041750f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100417517  jz      short loc_100417541
0x100417519  mov     r9, cs:off_1005E45C0; "<SNIInitializeEx|SNI> Vista versions wh"...
0x100417520  xor     edx, edx
0x100417522  mov     rcx, cs:_bidID
0x100417529  mov     r8d, 112000h
0x10041752f  mov     rax, cs:off_1005D39E0
0x100417536  mov     [rsp+68h+var_48], r15
0x10041753b  call    cs:__guard_dispatch_icall_fptr
0x100417541  mov     cs:?s_fAutoTuning@Tcp@@2HA, r12d; int Tcp::s_fAutoTuning
0x100417548  xor     r9d, r9d; NumberOfConcurrentThreads
0x10041754b  mov     cs:?g_fTerminate@@3_NA, r15b; bool g_fTerminate
0x100417552  xor     r8d, r8d; CompletionKey
0x100417555  xor     edx, edx; ExistingCompletionPort
0x100417557  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x10041755b  call    cs:__imp_CreateIoCompletionPort
0x100417561  mov     cs:?ghIoCompletionPort@@3PEAXEA, rax; void * ghIoCompletionPort
0x100417568  test    rax, rax
0x10041756b  jnz     short loc_1004175B4
0x10041756d  call    cs:__imp_GetLastError
0x100417573  test    byte ptr cs:_bidGblFlags, 2
0x10041757a  mov     edi, 0C3B4h
0x10041757f  mov     ebx, eax
0x100417581  mov     esi, 9
0x100417586  jz      loc_1004173A1
0x10041758c  mov     rax, cs:off_1005E45C8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417593  test    rax, rax
0x100417596  jz      loc_1004173A1
0x10041759c  mov     ecx, edi; unsigned int
0x10041759e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004175a3  mov     r8, cs:off_1005E45C8; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x1004175aa  mov     edx, 118800h
0x1004175af  jmp     loc_10041738F
0x1004175b4  xor     edx, edx; lpParameter
0x1004175b6  lea     rcx, ?SNIAsyncWait@@YAKPEAX@Z; lpStartAddress
0x1004175bd  call    SNICreateWaitThread
0x1004175c2  mov     ebx, eax
0x1004175c4  test    eax, eax
0x1004175c6  jnz     loc_100417658
0x1004175cc  lea     rcx, ?gClusApi@@3UCLUSTER_API@@A; struct CLUSTER_API *
0x1004175d3  mov     cs:?gClusApi@@3UCLUSTER_API@@A, r15; CLUSTER_API gClusApi
0x1004175da  mov     cs:qword_1005D8078, r15
0x1004175e1  call    ?LoadClusterResourceLibraryIfNeeded@@YAKPEAUCLUSTER_API@@@Z; LoadClusterResourceLibraryIfNeeded(CLUSTER_API *)
0x1004175e6  mov     ebx, eax
0x1004175e8  call    ?Initialize@DNSCache@@SAXXZ; DNSCache::Initialize(void)
0x1004175ed  mov     edx, esi; unsigned int
0x1004175ef  mov     rcx, rbp; enum ProviderNum *
0x1004175f2  call    ?InitProviders@SNI_Provider@@SAXPEBW4ProviderNum@@K@Z; SNI_Provider::InitProviders(ProviderNum const *,ulong)
0x1004175f7  jmp     loc_1004176F4
0x1004175fc  test    byte ptr cs:_bidGblFlags, 2
0x100417603  mov     ebp, 0Eh
0x100417608  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, r15; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x10041760f  mov     ebx, ebp
0x100417611  mov     edi, 0C3B4h
0x100417616  lea     esi, [rbp-5]
0x100417619  jz      short loc_10041764C
0x10041761b  mov     rax, cs:off_1005E4590; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417622  test    rax, rax
0x100417625  jz      short loc_10041764C
0x100417627  mov     ecx, edi; unsigned int
0x100417629  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041762e  mov     r8, cs:off_1005E4590; "<SNIInitializeEx|ERR|SNI> ProviderNum: "...
0x100417635  mov     edx, 104C00h
0x10041763a  mov     [rsp+68h+var_40], ebp
0x10041763e  mov     r9d, esi
0x100417641  xor     ecx, ecx
0x100417643  mov     dword ptr [rsp+68h+var_48], eax
0x100417647  call    _bidTraceW
0x10041764c  mov     edx, ebp
0x10041764e  mov     r8d, edi
0x100417651  mov     ecx, esi
0x100417653  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100417658  mov     rcx, cs:hObject; hObject
0x10041765f  test    rcx, rcx
0x100417662  jz      short loc_100417682
0x100417664  call    cs:__imp_CloseHandle
0x10041766a  mov     cs:hObject, r15
0x100417671  mov     cs:?ghWaitClose@@3VEventHandle@@A, r15; EventHandle ghWaitClose
0x100417678  test    eax, eax
0x10041767a  jnz     short loc_100417682
0x10041767c  call    cs:__imp_GetLastError
0x100417682  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x100417689  test    rcx, rcx
0x10041768c  jz      short loc_1004176A4
0x10041768e  mov     rax, [rcx]
0x100417691  mov     edx, r12d
0x100417694  mov     rax, [rax]
0x100417697  call    cs:__guard_dispatch_icall_fptr
0x10041769d  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, r15; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x1004176a4  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x1004176ab  test    rcx, rcx
0x1004176ae  jz      short loc_1004176BD
0x1004176b0  call    cs:__imp_CloseHandle
0x1004176b6  mov     cs:?ghIoCompletionPort@@3PEAXEA, r15; void * ghIoCompletionPort
0x1004176bd  mov     rcx, cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA; this
0x1004176c4  test    rcx, rcx
0x1004176c7  jz      short loc_1004176D5
0x1004176c9  call    ?Terminate@SNI_MemRegions@@SAXPEAV1@@Z; SNI_MemRegions::Terminate(SNI_MemRegions *)
0x1004176ce  mov     cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA, r15; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x1004176d5  mov     rcx, cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA; struct SNI_NodeIOCompletionQueues *
0x1004176dc  call    ?Terminate@SNI_NodeIOCompletionQueues@@SAXPEAV1@@Z; SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues *)
0x1004176e1  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, r15; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x1004176e8  call    ?Shutdown@LastConnectCache@@YAXXZ; LastConnectCache::Shutdown(void)
0x1004176ed  lock dec cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x1004176f4  mov     rcx, [r14+10h]
0x1004176f8  add     rcx, 20h ; ' '
0x1004176fc  mov     rax, [rcx]
0x1004176ff  mov     rax, [rax+18h]
0x100417703  call    cs:__guard_dispatch_icall_fptr
0x100417709  mov     eax, cs:_bidGblFlags
0x10041770f  mov     ecx, 20002h
0x100417714  and     eax, ecx
0x100417716  cmp     eax, ecx
0x100417718  jnz     short loc_10041773C
  ... truncated ...
```
