# DfsWorkerThread(void *)

- ea: `0x14001a040`
- end: `0x14001a6ba`
- name: `?DfsWorkerThread@@YAKPEAX@Z`
- size: `1658`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x140005a94`
- `0x1400068b8`
- `0x140006ab0`
- `0x140006bf0`
- `0x1400096ac`
- `0x14000abc4`
- `0x14001179c`
- `0x140015f64`
- `0x140017628`
- `0x1400186c4`
- `0x140018bb0`
- `0x14001a040`
- `0x140026230`
- `0x14005b0c4`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a222`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a222`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14001a24b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14001a40b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14001a24b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14001a40b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a659`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a57c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a60e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a57c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a60e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14001a387`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14001a387`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a59e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a63f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a59e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a63f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a3e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a3e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001a11c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001a4ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001a11c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001a4ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a1e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a0de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a46d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a0de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a46d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a671`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14001a559`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14001a559`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001a0cb`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001a0cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001a685`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001a685`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001a082`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001a082`

## string_xrefs

- `0x14001a214`: `System\CurrentControlSet\Services\Dfs\Parameters`

## pseudocode

```c
__int64 __fastcall DfsWorkerThread(PVOID Parameter)
{
  int v1; // edi
  unsigned int v2; // ebx
  DWORD v3; // ecx
  int v4; // eax
  unsigned int v5; // eax
  unsigned int *v6; // rcx
  unsigned int *v7; // rcx
  CConfigurationSettings *Instance; // rax
  unsigned int *v9; // rcx
  CConfigurationSettings *v10; // rax
  unsigned int v11; // eax
  DfsGeneric *v12; // rbx
  _QWORD *v13; // r8
  DfsGeneric *v14; // rdi
  DfsGeneric *v15; // rcx
  DfsFolder *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  hKey = 0;
  v1 = 5;
  ScavengeTime = 15000;
  CoInitializeEx(0, 4u);
  v2 = DfsRecognize();
  DfsLogDfsEvent(0x400038C5u, 0, 0, 0);
  byte_140071514 = 1;
  DfsLogDfsEvent(0x400038C3u, 0, 0, 0);
  ResumeThread(hObject);
  CloseHandle(hObject);
  hObject = 0;
  v3 = ScavengeTime;
  while ( 1 )
  {
    if ( !v2 || (v4 = v1, --v1, !v4) )
    {
      if ( !qword_140071638 )
      {
        qword_140071638 = CreateEventW(0, 1, 0, 0);
        if ( !qword_140071638 )
          goto LABEL_32;
      }
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Dfs\\Parameters",
             0,
             0x20019u,
             &hKey) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)pWppControl + 2), 35, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
        }
      }
      else
      {
        if ( !RegNotifyChangeKeyValue(hKey, 1, 0x1000000Fu, qword_140071638, 1) )
        {
LABEL_32:
          ScavengeTime = 1000 * *((_DWORD *)CConfigurationSettings::_GetInstance(v6) + 1);
          while ( 1 )
          {
            while ( 1 )
            {
              DfsRemoveOrphanedReparsePoints();
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x20) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_D(
                  *((_QWORD *)pWppControl + 2),
                  36,
                  WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids,
                  ScavengeTime);
              }
              if ( qword_140071638 )
                break;
              WaitForSingleObject(hEvent, ScavengeTime);
LABEL_56:
              if ( HIBYTE(word_140071515) == 1 )
                goto LABEL_77;
              ++dword_1400716A0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x20) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_(*((_QWORD *)pWppControl + 2), 39, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
              }
              v11 = DfsRecognize();
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x20) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_D(*((_QWORD *)pWppControl + 2), 40, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v11);
              }
              SystemTime = 0;
              GetLocalTime(&SystemTime);
              DfsSqmService::gm_wDay = SystemTime.wDay;
              DfsDumpStatistics();
              EnterCriticalSection(&CriticalSection);
              v12 = qword_140071548;
              qword_140071548 = 0;
              LeaveCriticalSection(&CriticalSection);
              while ( v12 )
              {
                v13 = (_QWORD *)((char *)v12 + 88);
                v14 = v12;
                v15 = (DfsGeneric *)*((_QWORD *)v12 + 11);
                if ( v15 == v12 )
                {
                  v12 = 0;
                }
                else
                {
                  v12 = (DfsGeneric *)*((_QWORD *)v12 + 11);
                  *((_QWORD *)v15 + 10) = *((_QWORD *)v14 + 10);
                  *(_QWORD *)(*((_QWORD *)v14 + 10) + 88LL) = *v13;
                }
                v16 = (DfsFolder *)*((_QWORD *)v14 + 9);
                if ( v16 )
                  DfsFolder::RemoveReferralData(v16, v14, 0);
                DfsGeneric::ReleaseReference(v14);
              }
              if ( (unsigned int)DfsIsLocalMachineDc() )
              {
                v17 = qword_1400715F0;
                EnterCriticalSection(*(LPCRITICAL_SECTION *)(qword_1400715F0 + 24));
                ++*(_DWORD *)(v17 + 16);
                DfsEnumerateAndPurgePrefixTableLocked(qword_1400715F0, DfsPurgeRootReferralPrefixTableCallback);
                v18 = qword_1400715F0;
                --*(_DWORD *)(qword_1400715F0 + 16);
                LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v18 + 24));
              }
            }
            Handles[1] = qword_140071638;
            Handles[0] = hEvent;
            if ( WaitForMultipleObjectsEx(2u, Handles, 0, ScavengeTime, 0) != 1 )
              goto LABEL_56;
            if ( HIBYTE(word_140071515) == 1 )
              goto LABEL_77;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x20) != 0
              && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              WPP_SF_(*((_QWORD *)pWppControl + 2), 37, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
            }
            ResetEvent(qword_140071638);
            if ( RegNotifyChangeKeyValue(hKey, 1, 0x1000000Fu, qword_140071638, 1) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x20) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_(*((_QWORD *)pWppControl + 2), 38, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
              }
              RegCloseKey(hKey);
              hKey = 0;
              CloseHandle(qword_140071638);
              qword_140071638 = 0;
            }
            Instance = CConfigurationSettings::_GetInstance(v7);
            CConfigurationSettings::LoadDfsSkipResyncSetting(Instance);
            if ( !(unsigned int)DfsIsLocalMachineDc() )
            {
              v10 = CConfigurationSettings::_GetInstance(v9);
              CConfigurationSettings::LoadServerConsolidationSettings(v10);
            }
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)pWppControl + 2), 34, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
        }
        RegCloseKey(hKey);
        hKey = 0;
      }
      CloseHandle(qword_140071638);
      qword_140071638 = 0;
      goto LABEL_32;
    }
    WaitForSingleObject(hEvent, v3);
    if ( HIBYTE(word_140071515) == 1 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 32, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, ScavengeTime / 0x3E8);
    }
    v5 = DfsRecognize();
    v2 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && pWppControl && (pWppControl[7] & 0x20) != 0 )
    {
      if ( *((_BYTE *)pWppControl + 25) )
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 33, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v5);
    }
    v3 = 2 * ScavengeTime;
    ScavengeTime *= 2;
  }
LABEL_77:
  if ( hKey )
    RegCloseKey(hKey);
  if ( qword_140071638 )
  {
    CloseHandle(qword_140071638);
    qword_140071638 = 0;
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x14001a040  mov     rax, rsp
0x14001a043  mov     [rax+8], rbx
0x14001a047  mov     [rax+10h], rdi
0x14001a04b  mov     [rax+18h], r12
0x14001a04f  mov     [rax+20h], r14
0x14001a053  push    rbp
0x14001a054  mov     rbp, rsp
0x14001a057  sub     rsp, 60h
0x14001a05b  mov     rax, cs:__security_cookie
0x14001a062  xor     rax, rsp
0x14001a065  mov     [rbp+var_8], rax
0x14001a069  and     [rbp+hKey], 0
0x14001a06e  mov     edi, 5
0x14001a073  xor     ecx, ecx; pvReserved
0x14001a075  mov     cs:?ScavengeTime@@3KA, 3A98h; ulong ScavengeTime
0x14001a07f  lea     edx, [rdi-1]; dwCoInit
0x14001a082  call    cs:__imp_CoInitializeEx
0x14001a089  nop     dword ptr [rax+rax+00h]
0x14001a08e  call    ?DfsRecognize@@YAKXZ; DfsRecognize(void)
0x14001a093  xor     edx, edx; unsigned __int16
0x14001a095  xor     r9d, r9d; unsigned int
0x14001a098  xor     r8d, r8d; unsigned __int16 **
0x14001a09b  mov     ecx, 400038C5h; unsigned int
0x14001a0a0  mov     ebx, eax
0x14001a0a2  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x14001a0a7  lea     r14d, [rdi-4]
0x14001a0ab  xor     edx, edx; unsigned __int16
0x14001a0ad  xor     r9d, r9d; unsigned int
0x14001a0b0  mov     cs:byte_140071514, r14b
0x14001a0b7  xor     r8d, r8d; unsigned __int16 **
0x14001a0ba  mov     ecx, 400038C3h; unsigned int
0x14001a0bf  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x14001a0c4  mov     rcx, cs:hObject; hThread
0x14001a0cb  call    cs:__imp_ResumeThread
0x14001a0d2  nop     dword ptr [rax+rax+00h]
0x14001a0d7  mov     rcx, cs:hObject; hObject
0x14001a0de  call    cs:__imp_CloseHandle
0x14001a0e5  nop     dword ptr [rax+rax+00h]
0x14001a0ea  and     cs:hObject, 0
0x14001a0f2  lea     r12, WPP_GLOBAL_Control
0x14001a0f9  mov     ecx, cs:?ScavengeTime@@3KA; ulong ScavengeTime
0x14001a0ff  test    ebx, ebx
0x14001a101  jz      loc_14001A1D1
0x14001a107  mov     eax, edi
0x14001a109  dec     edi
0x14001a10b  test    eax, eax
0x14001a10d  jz      loc_14001A1D1
0x14001a113  mov     edx, ecx; dwMilliseconds
0x14001a115  mov     rcx, cs:hEvent; hHandle
0x14001a11c  call    cs:__imp_WaitForSingleObject
0x14001a123  nop     dword ptr [rax+rax+00h]
0x14001a128  cmp     byte ptr cs:word_140071515+1, r14b
0x14001a12f  jz      loc_14001A650
0x14001a135  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a13c  jz      short loc_14001A17D
0x14001a13e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a145  test    rcx, rcx
0x14001a148  jz      short loc_14001A17D
0x14001a14a  test    byte ptr [rcx+1Ch], 20h
0x14001a14e  jz      short loc_14001A17D
0x14001a150  cmp     [rcx+19h], r14b
0x14001a154  jb      short loc_14001A17D
0x14001a156  mov     rcx, [rcx+10h]
0x14001a15a  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a161  mov     eax, 10624DD3h
0x14001a166  mul     cs:?ScavengeTime@@3KA; ulong ScavengeTime
0x14001a16c  mov     r9d, edx
0x14001a16f  mov     edx, 20h ; ' '
0x14001a174  shr     r9d, 6
0x14001a178  call    WPP_SF_D
0x14001a17d  call    ?DfsRecognize@@YAKXZ; DfsRecognize(void)
0x14001a182  mov     ebx, eax
0x14001a184  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a18b  jz      short loc_14001A1BD
0x14001a18d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a194  test    rcx, rcx
0x14001a197  jz      short loc_14001A1BD
0x14001a199  test    byte ptr [rcx+1Ch], 20h
0x14001a19d  jz      short loc_14001A1BD
0x14001a19f  cmp     [rcx+19h], r14b
0x14001a1a3  jb      short loc_14001A1BD
0x14001a1a5  mov     rcx, [rcx+10h]
0x14001a1a9  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a1b0  mov     edx, 21h ; '!'
0x14001a1b5  mov     r9d, eax
0x14001a1b8  call    WPP_SF_D
0x14001a1bd  mov     eax, cs:?ScavengeTime@@3KA; ulong ScavengeTime
0x14001a1c3  lea     ecx, [rax+rax]
0x14001a1c6  mov     cs:?ScavengeTime@@3KA, ecx; ulong ScavengeTime
0x14001a1cc  jmp     loc_14001A0FF
0x14001a1d1  cmp     cs:qword_140071638, 0
0x14001a1d9  jnz     short loc_14001A202
0x14001a1db  xor     r9d, r9d; lpName
0x14001a1de  xor     r8d, r8d; bInitialState
0x14001a1e1  mov     edx, r14d; bManualReset
0x14001a1e4  xor     ecx, ecx; lpEventAttributes
0x14001a1e6  call    cs:__imp_CreateEventW
0x14001a1ed  nop     dword ptr [rax+rax+00h]
0x14001a1f2  mov     cs:qword_140071638, rax
0x14001a1f9  test    rax, rax
0x14001a1fc  jz      loc_14001A2FD
0x14001a202  lea     rax, [rbp+hKey]
0x14001a206  mov     r9d, 20019h; samDesired
0x14001a20c  xor     r8d, r8d; ulOptions
0x14001a20f  mov     [rsp+60h+phkResult], rax; bAlertable
0x14001a214  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Df"...
0x14001a21b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a222  call    cs:__imp_RegOpenKeyExW
0x14001a229  nop     dword ptr [rax+rax+00h]
0x14001a22e  test    eax, eax
0x14001a230  jnz     short loc_14001A2AC
0x14001a232  mov     r9, cs:qword_140071638; hEvent
0x14001a239  mov     r8d, 1000000Fh; dwNotifyFilter
0x14001a23f  mov     rcx, [rbp+hKey]; hKey
0x14001a243  mov     edx, r14d; bWatchSubtree
0x14001a246  mov     dword ptr [rsp+60h+phkResult], r14d; fAsynchronous
0x14001a24b  call    cs:__imp_RegNotifyChangeKeyValue
0x14001a252  nop     dword ptr [rax+rax+00h]
0x14001a257  test    eax, eax
0x14001a259  jz      loc_14001A2FD
0x14001a25f  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a266  jz      short loc_14001A295
0x14001a268  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a26f  test    rcx, rcx
0x14001a272  jz      short loc_14001A295
0x14001a274  test    byte ptr [rcx+1Ch], 20h
0x14001a278  jz      short loc_14001A295
0x14001a27a  cmp     byte ptr [rcx+19h], 3
0x14001a27e  jb      short loc_14001A295
0x14001a280  mov     rcx, [rcx+10h]
0x14001a284  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a28b  mov     edx, 22h ; '"'
0x14001a290  call    WPP_SF_
0x14001a295  mov     rcx, [rbp+hKey]; hKey
0x14001a299  call    cs:__imp_RegCloseKey
0x14001a2a0  nop     dword ptr [rax+rax+00h]
0x14001a2a5  and     [rbp+hKey], 0
0x14001a2aa  jmp     short loc_14001A2E2
0x14001a2ac  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a2b3  jz      short loc_14001A2E2
0x14001a2b5  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a2bc  test    rcx, rcx
0x14001a2bf  jz      short loc_14001A2E2
0x14001a2c1  test    byte ptr [rcx+1Ch], 20h
0x14001a2c5  jz      short loc_14001A2E2
0x14001a2c7  cmp     byte ptr [rcx+19h], 3
0x14001a2cb  jb      short loc_14001A2E2
0x14001a2cd  mov     rcx, [rcx+10h]
0x14001a2d1  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a2d8  mov     edx, 23h ; '#'
0x14001a2dd  call    WPP_SF_
0x14001a2e2  mov     rcx, cs:qword_140071638; hObject
0x14001a2e9  call    cs:__imp_CloseHandle
0x14001a2f0  nop     dword ptr [rax+rax+00h]
0x14001a2f5  and     cs:qword_140071638, 0
0x14001a2fd  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14001a302  imul    ecx, [rax+4], 3E8h
0x14001a309  mov     cs:?ScavengeTime@@3KA, ecx; ulong ScavengeTime
0x14001a30f  call    ?DfsRemoveOrphanedReparsePoints@@YAXXZ; DfsRemoveOrphanedReparsePoints(void)
0x14001a314  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a31b  jz      short loc_14001A351
0x14001a31d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a324  test    rcx, rcx
0x14001a327  jz      short loc_14001A351
0x14001a329  test    byte ptr [rcx+1Ch], 20h
0x14001a32d  jz      short loc_14001A351
0x14001a32f  cmp     byte ptr [rcx+19h], 3
0x14001a333  jb      short loc_14001A351
0x14001a335  mov     r9d, cs:?ScavengeTime@@3KA; ulong ScavengeTime
0x14001a33c  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a343  mov     rcx, [rcx+10h]
0x14001a347  mov     edx, 24h ; '$'
0x14001a34c  call    WPP_SF_D
0x14001a351  mov     rcx, cs:qword_140071638
0x14001a358  test    rcx, rcx
0x14001a35b  jz      loc_14001A4AD
0x14001a361  mov     rax, cs:hEvent
0x14001a368  lea     rdx, [rbp+Handles]; lpHandles
0x14001a36c  mov     r9d, cs:?ScavengeTime@@3KA; dwMilliseconds
0x14001a373  xor     r8d, r8d; bWaitAll
0x14001a376  and     dword ptr [rsp+60h+phkResult], 0
0x14001a37b  mov     [rbp+var_20], rcx
0x14001a37f  mov     [rbp+Handles], rax
0x14001a383  lea     ecx, [r8+2]; nCount
0x14001a387  call    cs:__imp_WaitForMultipleObjectsEx
0x14001a38e  nop     dword ptr [rax+rax+00h]
0x14001a393  cmp     eax, r14d
0x14001a396  jnz     loc_14001A4C6
0x14001a39c  cmp     byte ptr cs:word_140071515+1, r14b
0x14001a3a3  jz      loc_14001A650
0x14001a3a9  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a3b0  jz      short loc_14001A3DF
0x14001a3b2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a3b9  test    rcx, rcx
0x14001a3bc  jz      short loc_14001A3DF
0x14001a3be  test    byte ptr [rcx+1Ch], 20h
0x14001a3c2  jz      short loc_14001A3DF
0x14001a3c4  cmp     byte ptr [rcx+19h], 3
0x14001a3c8  jb      short loc_14001A3DF
0x14001a3ca  mov     rcx, [rcx+10h]
0x14001a3ce  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a3d5  mov     edx, 25h ; '%'
0x14001a3da  call    WPP_SF_
0x14001a3df  mov     rcx, cs:qword_140071638; hEvent
0x14001a3e6  call    cs:__imp_ResetEvent
0x14001a3ed  nop     dword ptr [rax+rax+00h]
0x14001a3f2  mov     r9, cs:qword_140071638; hEvent
0x14001a3f9  mov     r8d, 1000000Fh; dwNotifyFilter
0x14001a3ff  mov     rcx, [rbp+hKey]; hKey
0x14001a403  mov     edx, r14d; bWatchSubtree
0x14001a406  mov     dword ptr [rsp+60h+phkResult], r14d; fAsynchronous
0x14001a40b  call    cs:__imp_RegNotifyChangeKeyValue
0x14001a412  nop     dword ptr [rax+rax+00h]
0x14001a417  test    eax, eax
0x14001a419  jz      short loc_14001A481
0x14001a41b  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a422  jz      short loc_14001A451
0x14001a424  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a42b  test    rcx, rcx
0x14001a42e  jz      short loc_14001A451
0x14001a430  test    byte ptr [rcx+1Ch], 20h
0x14001a434  jz      short loc_14001A451
0x14001a436  cmp     byte ptr [rcx+19h], 3
0x14001a43a  jb      short loc_14001A451
0x14001a43c  mov     rcx, [rcx+10h]
0x14001a440  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a447  mov     edx, 26h ; '&'
0x14001a44c  call    WPP_SF_
0x14001a451  mov     rcx, [rbp+hKey]; hKey
0x14001a455  call    cs:__imp_RegCloseKey
0x14001a45c  nop     dword ptr [rax+rax+00h]
0x14001a461  mov     rcx, cs:qword_140071638; hObject
0x14001a468  and     [rbp+hKey], 0
0x14001a46d  call    cs:__imp_CloseHandle
0x14001a474  nop     dword ptr [rax+rax+00h]
0x14001a479  and     cs:qword_140071638, 0
0x14001a481  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14001a486  mov     rcx, rax; this
0x14001a489  call    ?LoadDfsSkipResyncSetting@CConfigurationSettings@@QEAAXXZ; CConfigurationSettings::LoadDfsSkipResyncSetting(void)
0x14001a48e  call    ?DfsIsLocalMachineDc@@YAHXZ; DfsIsLocalMachineDc(void)
0x14001a493  test    eax, eax
0x14001a495  jnz     loc_14001A30F
0x14001a49b  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14001a4a0  mov     rcx, rax; this
0x14001a4a3  call    ?LoadServerConsolidationSettings@CConfigurationSettings@@QEAAXXZ; CConfigurationSettings::LoadServerConsolidationSettings(void)
0x14001a4a8  jmp     loc_14001A30F
0x14001a4ad  mov     edx, cs:?ScavengeTime@@3KA; dwMilliseconds
0x14001a4b3  mov     rcx, cs:hEvent; hHandle
0x14001a4ba  call    cs:__imp_WaitForSingleObject
0x14001a4c1  nop     dword ptr [rax+rax+00h]
0x14001a4c6  cmp     byte ptr cs:word_140071515+1, r14b
0x14001a4cd  jz      loc_14001A650
0x14001a4d3  add     cs:dword_1400716A0, r14d
0x14001a4da  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a4e1  jz      short loc_14001A510
0x14001a4e3  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a4ea  test    rcx, rcx
0x14001a4ed  jz      short loc_14001A510
0x14001a4ef  test    byte ptr [rcx+1Ch], 20h
0x14001a4f3  jz      short loc_14001A510
0x14001a4f5  cmp     byte ptr [rcx+19h], 3
0x14001a4f9  jb      short loc_14001A510
0x14001a4fb  mov     rcx, [rcx+10h]
0x14001a4ff  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a506  mov     edx, 27h ; '''
0x14001a50b  call    WPP_SF_
0x14001a510  call    ?DfsRecognize@@YAKXZ; DfsRecognize(void)
0x14001a515  cmp     cs:WPP_GLOBAL_Control, r12
0x14001a51c  jz      short loc_14001A54E
0x14001a51e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001a525  test    rcx, rcx
0x14001a528  jz      short loc_14001A54E
0x14001a52a  test    byte ptr [rcx+1Ch], 20h
0x14001a52e  jz      short loc_14001A54E
0x14001a530  cmp     byte ptr [rcx+19h], 3
0x14001a534  jb      short loc_14001A54E
0x14001a536  mov     rcx, [rcx+10h]
0x14001a53a  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x14001a541  mov     edx, 28h ; '('
0x14001a546  mov     r9d, eax
0x14001a549  call    WPP_SF_D
0x14001a54e  xorps   xmm0, xmm0
0x14001a551  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x14001a555  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x14001a559  call    cs:__imp_GetLocalTime
0x14001a560  nop     dword ptr [rax+rax+00h]
0x14001a565  movzx   eax, [rbp+SystemTime.wDay]
0x14001a569  mov     cs:?gm_wDay@DfsSqmService@@2GA, ax; ushort DfsSqmService::gm_wDay
0x14001a570  call    ?DfsDumpStatistics@@YAXXZ; DfsDumpStatistics(void)
0x14001a575  lea     rcx, CriticalSection; lpCriticalSection
0x14001a57c  call    cs:__imp_EnterCriticalSection
0x14001a583  nop     dword ptr [rax+rax+00h]
0x14001a588  mov     rbx, cs:qword_140071548
0x14001a58f  lea     rcx, CriticalSection; lpCriticalSection
0x14001a596  and     cs:qword_140071548, 0
0x14001a59e  call    cs:__imp_LeaveCriticalSection
0x14001a5a5  nop     dword ptr [rax+rax+00h]
0x14001a5aa  jmp     short loc_14001A5F1
0x14001a5ac  lea     r8, [rbx+58h]
0x14001a5b0  mov     rdi, rbx
  ... truncated ...
```
