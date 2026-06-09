# WorkerThread(void *)

- ea: `0x14003eb60`
- end: `0x14003f314`
- name: `?WorkerThread@@YAKPEAX@Z`
- size: `1972`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14001c890`
- `0x14001ccc0`
- `0x14001cf6c`
- `0x140020420`
- `0x140020854`
- `0x140032b60`
- `0x14003ceb0`
- `0x14003d0a8`
- `0x14003d424`
- `0x14003d4ac`
- `0x14003d56c`
- `0x14003d6dc`
- `0x14003d7a0`
- `0x14003d82c`
- `0x14003d954`
- `0x14003d9f0`
- `0x14003dad0`
- `0x14003ddc8`
- `0x14003e040`
- `0x14003e5f0`
- `0x14003e700`
- `0x14003e7f8`
- `0x14003ea28`
- `0x14003eb60`
- `0x140043a14`
- `0x140045788`
- `0x140046950`
- `0x140048508`
- `0x140048d70`
- `0x14004933c`
- `0x14004a33c`
- `0x14004a970`
- `0x14004ac48`
- `0x14004b718`
- `0x14004bd84`
- `0x14004db14`
- `0x14004e148`
- `0x14004fd30`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003f04e`
- `KERNEL32!GetLastError` at `0x14003f04e`
- `KERNEL32!WaitForMultipleObjects` at `0x14003ebd2`
- `KERNEL32!WaitForMultipleObjects` at `0x14003ebd2`
- `ole32!CoUninitialize` at `0x14003f2f0`
- `ole32!CoUninitialize` at `0x14003f2f0`
- `ole32!CoInitializeEx` at `0x14003eb82`
- `ole32!CoInitializeEx` at `0x14003eb82`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003f17c`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003f17c`

## string_xrefs

- `0x14003ebaa`: `WorkerThread`
- `0x14003ebb9`: `WorkerThread`
- `0x14003f20a`: `WorkerTaskComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WorkerThread(PVOID Parameter)
{
  HRESULT v1; // eax
  signed int v2; // ebx
  int v3; // r12d
  unsigned __int16 *v4; // rdx
  HKEY v5; // rcx
  unsigned __int64 v6; // r8
  unsigned __int16 *v7; // r9
  DWORD v8; // r14d
  int v9; // eax
  int v10; // eax
  int v11; // r9d
  int v12; // eax
  int v13; // eax
  DWORD v14; // r14d
  DWORD v15; // r14d
  DWORD v16; // r14d
  DWORD v17; // r14d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int Instance; // eax
  int v32; // eax
  int updated; // eax
  int HistoryDirectory; // eax
  int v35; // eax
  DWORD v36; // r14d
  DWORD v37; // r14d
  DWORD v38; // r14d
  DWORD v39; // r14d
  signed int LastError; // eax
  int v41; // eax
  signed int v42; // r14d
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // r9d
  int v47; // eax
  int v48; // r9d
  int v49; // r9d
  int v50; // eax
  int v51; // eax
  struct PageManager *v52; // rbx
  unsigned int v54; // [rsp+28h] [rbp-8h]
  struct PageManager *Data; // [rsp+78h] [rbp+48h] BYREF
  struct PageManager *v56; // [rsp+80h] [rbp+50h] BYREF

  v56 = 0;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 0;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 59, v1);
    goto LABEL_122;
  }
  v3 = 1;
  while ( 1 )
  {
    v8 = WaitForMultipleObjects(0x1Cu, &g_EventsToWorker, 0, 0xFFFFFFFF);
    if ( v8 >= 0x80 )
      break;
    if ( v8 > 0xF )
    {
      if ( v8 > 0x16 )
      {
        v36 = v8 - 23;
        if ( !v36 )
        {
          LODWORD(Data) = 1;
          v45 = DwzRegWriteValue(v5, v4, v6, v7, (BYTE *)&Data, v54);
          v42 = v45;
          if ( v45 < 0 )
          {
            v46 = 1521;
          }
          else
          {
            v45 = RelaunchPackageInstance();
            v42 = v45;
            if ( v45 >= 0 )
              goto LABEL_96;
            v46 = 1524;
          }
          v2 = v42;
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EnableLocalTroubleshooting", v46, v45);
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 293, v42);
          goto LABEL_122;
        }
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( v39 )
            {
              if ( v39 == 1 )
                goto LABEL_122;
              break;
            }
LABEL_75:
            v32 = ReloadPackages();
            v2 = v32;
            if ( v32 < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 248, v32);
              goto LABEL_122;
            }
          }
          else
          {
            v43 = SkipIntro();
            v2 = v43;
            if ( v43 < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 87, v43);
              goto LABEL_122;
            }
          }
        }
        else
        {
          v44 = RelaunchPackageInstance();
          v2 = v44;
          if ( v44 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 298, v44);
            goto LABEL_122;
          }
        }
      }
      else
      {
        switch ( v8 )
        {
          case 0x16u:
            v35 = LaunchSettingsInCPL();
            v2 = v35;
            if ( v35 < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 288, v35);
              goto LABEL_122;
            }
            break;
          case 0x10u:
          case 0x11u:
            g_ErrorContext = 405;
            updated = UpdateUITextByID(0x164u);
            v2 = updated;
            if ( updated < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 275, updated);
              goto LABEL_122;
            }
            HistoryDirectory = MakeHistoryDirectory(0);
            v2 = HistoryDirectory;
            if ( HistoryDirectory < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 278, HistoryDirectory);
              goto LABEL_122;
            }
            goto LABEL_92;
          case 0x12u:
            v10 = DwzSubmitWERReport();
            v2 = v10;
            if ( v10 < 0 )
            {
              v11 = 113;
LABEL_21:
              SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "WorkerThread", v11, v10);
              v2 = 0;
            }
            break;
          case 0x13u:
            v24 = ValidateSupportKey();
            v2 = v24;
            if ( v24 < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 129, v24);
              goto LABEL_122;
            }
            if ( *((_DWORD *)Config + 13) )
              goto LABEL_92;
            goto LABEL_51;
          case 0x15u:
            v23 = LaunchNetworkingPackage();
            v2 = v23;
            if ( v23 < 0 )
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 283, v23);
              goto LABEL_122;
            }
            break;
          default:
            goto LABEL_89;
        }
      }
    }
    else if ( v8 == 15 )
    {
LABEL_51:
      v25 = DownloadFile();
      v2 = v25;
      if ( v25 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 139, v25);
        goto LABEL_122;
      }
      if ( v25 == 1 )
      {
        v26 = RetryDownload();
        v2 = v26;
        if ( v26 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 143, v26);
          goto LABEL_122;
        }
      }
      else
      {
        if ( (unsigned int)(*((_DWORD *)Config + 66) - 1) <= 2 )
          goto LABEL_92;
        if ( (unsigned int)Packages_SameAsFirst() )
        {
LABEL_59:
          g_ErrorContext = 406;
          v28 = SetDiagnoseProgressText(0);
          v2 = v28;
          if ( v28 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 170, v28);
            goto LABEL_122;
          }
          v2 = Packages_Diagnose();
          if ( v2 < 0 )
          {
            v48 = 173;
            goto LABEL_121;
          }
          if ( *((_DWORD *)Config + 7) )
          {
            v47 = PageManager::Instance(&v56);
            v2 = v47;
            if ( v47 >= 0 )
            {
              DirectUI::TaskPage::PropSheet_SendMessage(*((DirectUI::TaskPage **)v56 + 1), 0x471u, 5u, 0);
              v2 = 0;
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 177, v47);
            }
            goto LABEL_122;
          }
          if ( v2 != 1 )
          {
            if ( *((_DWORD *)Config + 10) && (unsigned int)RCs_ResolutionsToChoose() )
              goto LABEL_92;
            Packages_SetResolveAll();
            goto LABEL_68;
          }
          v29 = NoRootCauses();
          v2 = v29;
          if ( v29 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 190, v29);
            goto LABEL_122;
          }
        }
        else
        {
          v27 = ForcePackagePage();
          v2 = v27;
          if ( v27 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 160, v27);
            goto LABEL_122;
          }
        }
      }
    }
    else if ( v8 > 7 )
    {
      v14 = v8 - 8;
      if ( v14 )
      {
        v15 = v14 - 3;
        if ( !v15 )
        {
          v21 = DefaultCabAndUpload();
          v2 = v21;
          if ( v21 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 258, v21);
            goto LABEL_122;
          }
          goto LABEL_92;
        }
        v16 = v15 - 1;
        if ( !v16 )
        {
          v20 = CabAndUploadFiles();
          v2 = v20;
          if ( v20 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 263, v20);
            goto LABEL_122;
          }
          goto LABEL_92;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v19 = UploadFile(*((unsigned __int16 **)Config + 18));
          v2 = v19;
          if ( v19 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 268, v19);
            goto LABEL_122;
          }
          goto LABEL_92;
        }
        if ( v17 == 1 )
        {
          v18 = ReuploadFiles();
          v2 = v18;
          if ( v18 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 253, v18);
            goto LABEL_122;
          }
          goto LABEL_92;
        }
        break;
      }
      v22 = UIF::CommunicateFeedbackContext((__int64)v5, v4, v6);
      v2 = v22;
      if ( v22 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 105, v22);
        goto LABEL_122;
      }
      v10 = DwzSubmitWERReport();
      v2 = v10;
      if ( v10 < 0 )
      {
        v11 = 108;
        goto LABEL_21;
      }
    }
    else if ( v8 == 7 )
    {
      v13 = UIF::CommunicateFeedbackContext((__int64)v5, v4, v6);
      v2 = v13;
      if ( v13 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 97, v13);
        goto LABEL_122;
      }
    }
    else if ( v8 < 2 )
    {
LABEL_68:
      g_ErrorContext = 406;
      v30 = Packages_Resolve(v8 != 0);
      v2 = v30;
      if ( v30 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 216, v30);
        goto LABEL_122;
      }
      if ( *((_DWORD *)Config + 10) || !(unsigned int)RCs_AnyResolutionsRun() )
        goto LABEL_92;
      Data = 0;
      Instance = TroubleshootingPackages::GetInstance(&Data);
      if ( Instance >= 0 )
      {
        if ( !*((_DWORD *)Data + 5) )
          goto LABEL_92;
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_DifferentRCs", 3690, Instance);
      }
      if ( *((_DWORD *)Config + 53) < 4u )
        goto LABEL_75;
LABEL_92:
      Data = 0;
      v41 = WaitForProgressPage();
      v42 = v41;
      if ( v41 < 0 )
      {
        v49 = 374;
        goto LABEL_119;
      }
      if ( v41 == 1 )
        goto LABEL_96;
      v41 = PageManager::Instance(&Data);
      v42 = v41;
      if ( v41 < 0 )
      {
        v49 = 380;
LABEL_119:
        v2 = v42;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerTaskComplete", v49, v41);
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 311, v42);
        goto LABEL_122;
      }
      PageManager::ProgressFinished(Data);
LABEL_96:
      v2 = v42;
    }
    else
    {
      switch ( v8 )
      {
        case 2u:
          v10 = Packages_Load();
          v2 = v10;
          if ( v10 < 0 )
          {
            v11 = 78;
            goto LABEL_21;
          }
          break;
        case 3u:
          goto LABEL_59;
        case 5u:
          v12 = CPL::CommunicateEscalationContext();
          v2 = v12;
          if ( v12 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 92, v12);
            goto LABEL_122;
          }
          break;
        case 6u:
          v9 = CPL::CommunicateEscalationContext();
          v2 = v9;
          if ( v9 < 0 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", 121, v9);
            goto LABEL_122;
          }
          v10 = DwzSubmitWERReport();
          v2 = v10;
          if ( v10 < 0 )
          {
            v11 = 124;
            goto LABEL_21;
          }
          break;
        default:
          goto LABEL_89;
      }
    }
  }
LABEL_89:
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
    goto LABEL_92;
  v48 = 307;
LABEL_121:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WorkerThread", v48, v2);
LABEL_122:
  MakeHistoryDirectory(1);
  if ( v2 < 0 && !g_Stop )
  {
    Data = 0;
    v50 = PageManager::Instance(&Data);
    if ( v50 >= 0 )
      PageManager::Error(Data, v2);
    else
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "KillUI", 488, v50);
  }
  DwzSqmExit();
  Data = 0;
  Packages_SqmRootCausesAndResolutions();
  v51 = TroubleshootingPackages::GetInstance(&Data);
  if ( v51 >= 0 )
  {
    Packages_FreeExtensions();
    v52 = Data;
    if ( *(_QWORD *)Data )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Data + 16LL))(*(_QWORD *)Data);
      *(_QWORD *)v52 = 0;
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_ReleaseEngine", 2338, v51);
  }
  if ( v3 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x14003eb60  mov     [rsp-38h+arg_0], rbx
0x14003eb65  push    rbp
0x14003eb66  push    rsi
0x14003eb67  push    rdi
0x14003eb68  push    r12
0x14003eb6a  push    r13
0x14003eb6c  push    r14
0x14003eb6e  push    r15
0x14003eb70  mov     rbp, rsp
0x14003eb73  sub     rsp, 30h
0x14003eb77  xor     r13d, r13d
0x14003eb7a  xor     edx, edx; dwCoInit
0x14003eb7c  xor     ecx, ecx; pvReserved
0x14003eb7e  mov     [rbp+arg_10], r13
0x14003eb82  call    cs:__imp_CoInitializeEx
0x14003eb89  nop     dword ptr [rax+rax+00h]
0x14003eb8e  lea     rsi, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003eb95  mov     ebx, eax
0x14003eb97  lea     edi, [r13+1]
0x14003eb9b  test    eax, eax
0x14003eb9d  jns     short loc_14003EBB6
0x14003eb9f  mov     r12d, r13d
0x14003eba2  mov     dword ptr [rsp+30h+lpData], eax
0x14003eba6  lea     r9d, [r13+3Bh]
0x14003ebaa  lea     r8, aWorkerthread; "WorkerThread"
0x14003ebb1  jmp     loc_14003F23C
0x14003ebb6  mov     r12d, edi
0x14003ebb9  lea     r15, aWorkerthread; "WorkerThread"
0x14003ebc0  xor     r8d, r8d; bWaitAll
0x14003ebc3  lea     rdx, ?g_EventsToWorker@@3PAPEAXA; lpHandles
0x14003ebca  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14003ebce  lea     ecx, [r8+1Ch]; nCount
0x14003ebd2  call    cs:__imp_WaitForMultipleObjects
0x14003ebd9  nop     dword ptr [rax+rax+00h]
0x14003ebde  mov     r14d, eax
0x14003ebe1  mov     eax, 80h
0x14003ebe6  cmp     r14d, eax
0x14003ebe9  ja      loc_14003F04E
0x14003ebef  jz      loc_14003F04E
0x14003ebf5  cmp     r14d, 0Fh
0x14003ebf9  ja      loc_14003EDA8
0x14003ebff  jz      loc_14003EE1F
0x14003ec05  cmp     r14d, 7
0x14003ec09  ja      loc_14003ECD6
0x14003ec0f  jz      loc_14003ECB8
0x14003ec15  mov     eax, r14d
0x14003ec18  test    r14d, r14d
0x14003ec1b  jz      loc_14003EF04
0x14003ec21  sub     eax, edi
0x14003ec23  jz      loc_14003EF04
0x14003ec29  sub     eax, edi
0x14003ec2b  jz      short loc_14003EC86
0x14003ec2d  sub     eax, edi
0x14003ec2f  jz      loc_14003EE8F
0x14003ec35  sub     eax, 2
0x14003ec38  jz      short loc_14003EC68
0x14003ec3a  cmp     eax, edi
0x14003ec3c  jnz     loc_14003F04E
0x14003ec42  call    ?CommunicateEscalationContext@CPL@@SAJXZ; CPL::CommunicateEscalationContext(void)
0x14003ec47  mov     ebx, eax
0x14003ec49  test    eax, eax
0x14003ec4b  js      loc_14003F11D
0x14003ec51  call    ?DwzSubmitWERReport@@YAJXZ; DwzSubmitWERReport(void)
0x14003ec56  mov     ebx, eax
0x14003ec58  test    eax, eax
0x14003ec5a  jns     loc_14003EBC0
0x14003ec60  mov     r9d, 7Ch ; '|'
0x14003ec66  jmp     short loc_14003EC9B
0x14003ec68  call    ?CommunicateEscalationContext@CPL@@SAJXZ; CPL::CommunicateEscalationContext(void)
0x14003ec6d  mov     ebx, eax
0x14003ec6f  test    eax, eax
0x14003ec71  jns     loc_14003EBC0
0x14003ec77  mov     dword ptr [rsp+30h+lpData], eax
0x14003ec7b  mov     r9d, 5Ch ; '\'
0x14003ec81  jmp     loc_14003F239
0x14003ec86  call    ?Packages_Load@@YAJXZ; Packages_Load(void)
0x14003ec8b  mov     ebx, eax
0x14003ec8d  test    eax, eax
0x14003ec8f  jns     loc_14003EBC0
0x14003ec95  mov     r9d, 4Eh ; 'N'
0x14003ec9b  mov     r8, r15
0x14003ec9e  mov     dword ptr [rsp+30h+lpData], eax
0x14003eca2  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14003eca9  mov     ecx, edi; Level
0x14003ecab  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003ecb0  mov     ebx, r13d
0x14003ecb3  jmp     loc_14003EBC0
0x14003ecb8  call    ?CommunicateFeedbackContext@UIF@@SAJXZ; UIF::CommunicateFeedbackContext(void)
0x14003ecbd  mov     ebx, eax
0x14003ecbf  test    eax, eax
0x14003ecc1  jns     loc_14003EBC0
0x14003ecc7  mov     dword ptr [rsp+30h+lpData], eax
0x14003eccb  mov     r9d, 61h ; 'a'
0x14003ecd1  jmp     loc_14003F239
0x14003ecd6  sub     r14d, 8
0x14003ecda  jz      loc_14003ED7F
0x14003ece0  sub     r14d, 3
0x14003ece4  jz      short loc_14003ED61
0x14003ece6  sub     r14d, edi
0x14003ece9  jz      short loc_14003ED43
0x14003eceb  sub     r14d, edi
0x14003ecee  jz      short loc_14003ED17
0x14003ecf0  cmp     r14d, edi
0x14003ecf3  jnz     loc_14003F04E
0x14003ecf9  call    ?ReuploadFiles@@YAJXZ; ReuploadFiles(void)
0x14003ecfe  mov     ebx, eax
0x14003ed00  test    eax, eax
0x14003ed02  jns     loc_14003F071
0x14003ed08  mov     dword ptr [rsp+30h+lpData], eax
0x14003ed0c  mov     r9d, 0FDh
0x14003ed12  jmp     loc_14003F239
0x14003ed17  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003ed1e  mov     rcx, [rcx+90h]; unsigned __int16 *
0x14003ed25  call    ?UploadFile@@YAJPEAG@Z; UploadFile(ushort *)
0x14003ed2a  mov     ebx, eax
0x14003ed2c  test    eax, eax
0x14003ed2e  jns     loc_14003F071
0x14003ed34  mov     dword ptr [rsp+30h+lpData], eax
0x14003ed38  mov     r9d, 10Ch
0x14003ed3e  jmp     loc_14003F239
0x14003ed43  call    ?CabAndUploadFiles@@YAJXZ; CabAndUploadFiles(void)
0x14003ed48  mov     ebx, eax
0x14003ed4a  test    eax, eax
0x14003ed4c  jns     loc_14003F071
0x14003ed52  mov     dword ptr [rsp+30h+lpData], eax
0x14003ed56  mov     r9d, 107h
0x14003ed5c  jmp     loc_14003F239
0x14003ed61  call    ?DefaultCabAndUpload@@YAJXZ; DefaultCabAndUpload(void)
0x14003ed66  mov     ebx, eax
0x14003ed68  test    eax, eax
0x14003ed6a  jns     loc_14003F071
0x14003ed70  mov     dword ptr [rsp+30h+lpData], eax
0x14003ed74  mov     r9d, 102h
0x14003ed7a  jmp     loc_14003F239
0x14003ed7f  call    ?CommunicateFeedbackContext@UIF@@SAJXZ; UIF::CommunicateFeedbackContext(void)
0x14003ed84  mov     ebx, eax
0x14003ed86  test    eax, eax
0x14003ed88  js      loc_14003F12C
0x14003ed8e  call    ?DwzSubmitWERReport@@YAJXZ; DwzSubmitWERReport(void)
0x14003ed93  mov     ebx, eax
0x14003ed95  test    eax, eax
0x14003ed97  jns     loc_14003EBC0
0x14003ed9d  mov     r9d, 6Ch ; 'l'
0x14003eda3  jmp     loc_14003EC9B
0x14003eda8  cmp     r14d, 16h
0x14003edac  ja      loc_14003F024
0x14003edb2  jz      loc_14003F006
0x14003edb8  mov     eax, r14d
0x14003edbb  sub     eax, 10h
0x14003edbe  jz      loc_14003EFCC
0x14003edc4  sub     eax, edi
0x14003edc6  jz      loc_14003EFCC
0x14003edcc  sub     eax, edi
0x14003edce  jz      loc_14003EFB2
0x14003edd4  sub     eax, edi
0x14003edd6  jz      short loc_14003EDFF
0x14003edd8  cmp     eax, 2
0x14003eddb  jnz     loc_14003F04E
0x14003ede1  call    ?LaunchNetworkingPackage@@YAJXZ; LaunchNetworkingPackage(void)
0x14003ede6  mov     ebx, eax
0x14003ede8  test    eax, eax
0x14003edea  jns     loc_14003EBC0
0x14003edf0  mov     dword ptr [rsp+30h+lpData], eax
0x14003edf4  mov     r9d, 11Bh
0x14003edfa  jmp     loc_14003F239
0x14003edff  call    ?ValidateSupportKey@@YAJXZ; ValidateSupportKey(void)
0x14003ee04  mov     ebx, eax
0x14003ee06  test    eax, eax
0x14003ee08  js      loc_14003F1B9
0x14003ee0e  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003ee15  cmp     [rax+34h], r13d
0x14003ee19  jnz     loc_14003F071
0x14003ee1f  call    ?DownloadFile@@YAJXZ; DownloadFile(void)
0x14003ee24  mov     ebx, eax
0x14003ee26  test    eax, eax
0x14003ee28  js      loc_14003F1AA
0x14003ee2e  cmp     eax, edi
0x14003ee30  jnz     short loc_14003EE50
0x14003ee32  call    ?RetryDownload@@YAJXZ; RetryDownload(void)
0x14003ee37  mov     ebx, eax
0x14003ee39  test    eax, eax
0x14003ee3b  jns     loc_14003EBC0
0x14003ee41  mov     dword ptr [rsp+30h+lpData], eax
0x14003ee45  mov     r9d, 8Fh
0x14003ee4b  jmp     loc_14003F239
0x14003ee50  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003ee57  mov     ecx, [rax+108h]
0x14003ee5d  sub     ecx, edi
0x14003ee5f  cmp     ecx, 2
0x14003ee62  jbe     loc_14003F071
0x14003ee68  call    ?Packages_SameAsFirst@@YAHXZ; Packages_SameAsFirst(void)
0x14003ee6d  test    eax, eax
0x14003ee6f  jnz     short loc_14003EE8F
0x14003ee71  call    ?ForcePackagePage@@YAJXZ; ForcePackagePage(void)
0x14003ee76  mov     ebx, eax
0x14003ee78  test    eax, eax
0x14003ee7a  jns     loc_14003EBC0
0x14003ee80  mov     dword ptr [rsp+30h+lpData], eax
0x14003ee84  mov     r9d, 0A0h
0x14003ee8a  jmp     loc_14003F239
0x14003ee8f  xor     ecx, ecx; int
0x14003ee91  mov     cs:?g_ErrorContext@@3IC, 196h; uint volatile g_ErrorContext
0x14003ee9b  call    ?SetDiagnoseProgressText@@YAJH@Z; SetDiagnoseProgressText(int)
0x14003eea0  mov     ebx, eax
0x14003eea2  test    eax, eax
0x14003eea4  js      loc_14003F19B
0x14003eeaa  call    ?Packages_Diagnose@@YAJXZ; Packages_Diagnose(void)
0x14003eeaf  mov     ebx, eax
0x14003eeb1  test    eax, eax
0x14003eeb3  js      loc_14003F190
0x14003eeb9  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003eec0  cmp     [rax+1Ch], r13d
0x14003eec4  jnz     loc_14003F14A
0x14003eeca  cmp     ebx, edi
0x14003eecc  jnz     short loc_14003EEEC
0x14003eece  call    ?NoRootCauses@@YAJXZ; NoRootCauses(void)
0x14003eed3  mov     ebx, eax
0x14003eed5  test    eax, eax
0x14003eed7  jns     loc_14003EBC0
0x14003eedd  mov     dword ptr [rsp+30h+lpData], eax
0x14003eee1  mov     r9d, 0BEh
0x14003eee7  jmp     loc_14003F239
0x14003eeec  cmp     [rax+28h], r13d
0x14003eef0  jz      short loc_14003EEFF
0x14003eef2  call    ?RCs_ResolutionsToChoose@@YAHXZ; RCs_ResolutionsToChoose(void)
0x14003eef7  test    eax, eax
0x14003eef9  jnz     loc_14003F071
0x14003eeff  call    ?Packages_SetResolveAll@@YAJXZ; Packages_SetResolveAll(void)
0x14003ef04  mov     ecx, r13d
0x14003ef07  mov     cs:?g_ErrorContext@@3IC, 196h; uint volatile g_ErrorContext
0x14003ef11  test    r14d, r14d
0x14003ef14  setnz   cl; int
0x14003ef17  call    ?Packages_Resolve@@YAJH@Z; Packages_Resolve(int)
0x14003ef1c  mov     ebx, eax
0x14003ef1e  test    eax, eax
0x14003ef20  js      loc_14003F13B
0x14003ef26  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003ef2d  cmp     [rax+28h], r13d
0x14003ef31  jnz     loc_14003F071
0x14003ef37  call    ?RCs_AnyResolutionsRun@@YAHXZ; RCs_AnyResolutionsRun(void)
0x14003ef3c  test    eax, eax
0x14003ef3e  jz      loc_14003F071
0x14003ef44  lea     rcx, [rbp+Data]; struct TroubleshootingPackages **
0x14003ef48  mov     [rbp+Data], r13
0x14003ef4c  call    ?GetInstance@TroubleshootingPackages@@SAJPEAPEAV1@@Z; TroubleshootingPackages::GetInstance(TroubleshootingPackages * *)
0x14003ef51  test    eax, eax
0x14003ef53  jns     short loc_14003EF72
0x14003ef55  mov     r9d, 0E6Ah
0x14003ef5b  mov     dword ptr [rsp+30h+lpData], eax
0x14003ef5f  lea     r8, aPackagesDiffer; "Packages_DifferentRCs"
0x14003ef66  mov     rdx, rsi; char *
0x14003ef69  mov     ecx, edi; Level
0x14003ef6b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003ef70  jmp     short loc_14003EF80
0x14003ef72  mov     rax, [rbp+Data]
0x14003ef76  cmp     [rax+14h], r13d
0x14003ef7a  jz      loc_14003F071
0x14003ef80  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003ef87  cmp     dword ptr [rax+0D4h], 4
0x14003ef8e  jnb     loc_14003F071
0x14003ef94  call    ?ReloadPackages@@YAJXZ; ReloadPackages(void)
0x14003ef99  mov     ebx, eax
0x14003ef9b  test    eax, eax
0x14003ef9d  jns     loc_14003EBC0
0x14003efa3  mov     dword ptr [rsp+30h+lpData], eax
0x14003efa7  mov     r9d, 0F8h
0x14003efad  jmp     loc_14003F239
0x14003efb2  call    ?DwzSubmitWERReport@@YAJXZ; DwzSubmitWERReport(void)
0x14003efb7  mov     ebx, eax
0x14003efb9  test    eax, eax
0x14003efbb  jns     loc_14003EBC0
0x14003efc1  mov     r9d, 71h ; 'q'
0x14003efc7  jmp     loc_14003EC9B
0x14003efcc  mov     ecx, 164h; uID
0x14003efd1  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x14003efdb  call    ?UpdateUITextByID@@YAJI@Z; UpdateUITextByID(uint)
0x14003efe0  mov     ebx, eax
0x14003efe2  test    eax, eax
0x14003efe4  js      loc_14003F1C5
0x14003efea  xor     ecx, ecx; int
0x14003efec  call    ?MakeHistoryDirectory@@YAJH@Z; MakeHistoryDirectory(int)
0x14003eff1  mov     ebx, eax
0x14003eff3  test    eax, eax
0x14003eff5  jns     short loc_14003F071
0x14003eff7  mov     dword ptr [rsp+30h+lpData], eax
0x14003effb  mov     r9d, 116h
0x14003f001  jmp     loc_14003F239
0x14003f006  call    ?LaunchSettingsInCPL@@YAJXZ; LaunchSettingsInCPL(void)
0x14003f00b  mov     ebx, eax
0x14003f00d  test    eax, eax
0x14003f00f  jns     loc_14003EBC0
0x14003f015  mov     dword ptr [rsp+30h+lpData], eax
0x14003f019  mov     r9d, 120h
0x14003f01f  jmp     loc_14003F239
0x14003f024  sub     r14d, 17h
0x14003f028  jz      loc_14003F0EA
0x14003f02e  sub     r14d, edi
0x14003f031  jz      loc_14003F0CC
0x14003f037  sub     r14d, edi
0x14003f03a  jz      short loc_14003F0AE
  ... truncated ...
```
