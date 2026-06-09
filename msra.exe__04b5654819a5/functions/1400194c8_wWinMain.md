# wWinMain

- ea: `0x1400194c8`
- end: `0x140019b12`
- name: `wWinMain`
- size: `1610`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001800`

## callees

- `0x140001cc4`
- `0x140002463`
- `0x14000b99c`
- `0x14000ea24`
- `0x140012794`
- `0x1400137ac`
- `0x140016bd4`
- `0x1400187cc`
- `0x1400194c8`
- `0x14002c0a4`
- `0x14002fbe0`
- `0x1400300d0`
- `0x1400302a0`
- `0x140030f70`
- `0x1400311b8`
- `0x140034ce4`
- `0x140034eac`
- `0x14003500c`
- `0x1400373f4`
- `0x1400374c8`
- `0x140037c8c`
- `0x1400387e0`
- `0x140039e2c`
- `0x140040390`
- `0x140040458`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x140019618`
- `ADVAPI32!EventRegister` at `0x140019618`
- `KERNEL32!RegisterApplicationRestart` at `0x140019770`
- `KERNEL32!RegisterApplicationRestart` at `0x140019770`
- `KERNEL32!QueueUserWorkItem` at `0x1400197ee`
- `KERNEL32!QueueUserWorkItem` at `0x1400197ee`
- `KERNEL32!GetCommandLineW` at `0x14001991d`
- `KERNEL32!GetCommandLineW` at `0x14001991d`
- `KERNEL32!SetErrorMode` at `0x1400195b2`
- `KERNEL32!SetErrorMode` at `0x1400195b2`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001952f`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001954e`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001956a`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140019589`
- `KERNEL32!SetProcessMitigationPolicy` at `0x1400195a4`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001952f`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001954e`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14001956a`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140019589`
- `KERNEL32!SetProcessMitigationPolicy` at `0x1400195a4`
- `KERNEL32!HeapSetInformation` at `0x14001950e`
- `KERNEL32!HeapSetInformation` at `0x14001950e`
- `USER32!LoadIconW` at `0x14001974d`
- `USER32!LoadIconW` at `0x14001974d`
- `USER32!LoadAcceleratorsW` at `0x14001985f`
- `USER32!LoadAcceleratorsW` at `0x14001985f`
- `USER32!CopyAcceleratorTableW` at `0x1400198a3`
- `USER32!CopyAcceleratorTableW` at `0x1400198ea`
- `USER32!CopyAcceleratorTableW` at `0x1400198a3`
- `USER32!CopyAcceleratorTableW` at `0x1400198ea`
- `msvcrt!calloc` at `0x1400198be`
- `msvcrt!calloc` at `0x1400198be`
- `ole32!CoUninitialize` at `0x140019adc`
- `ole32!CoUninitialize` at `0x140019adc`
- `ole32!CoInitialize` at `0x140019634`
- `ole32!CoInitialize` at `0x140019634`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtReleaseTeredoConsumerHandle` at `0x140019a36`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtReleaseTeredoConsumerHandle` at `0x140019a36`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x14001980c`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x14001980c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v6; // ebx
  CRemoteAssistanceApp *v7; // rax
  CRATicket *v8; // rax
  CRATicket *v9; // rcx
  CEventLogger *v10; // rax
  int v11; // edi
  HRESULT v12; // eax
  CEventLogger *v13; // rcx
  unsigned __int16 *v14; // r8
  CRemoteAssistanceApp *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  HACCEL AcceleratorsW; // rax
  CEventLogger *v19; // rcx
  int v20; // eax
  int v21; // ebx
  struct tagACCEL *v22; // rax
  CEventLogger *v23; // rcx
  CRemoteAssistanceApp *v24; // rbx
  LPWSTR CommandLineW; // rax
  __int64 v26; // rcx
  struct CRATicket *v27; // rdi
  int v28; // esi
  CEventLogger *v29; // rcx
  HWND v30; // r8
  int v31; // edx
  struct CRATicket *v32; // rcx
  signed int v33; // eax
  CEventLogger *v34; // rcx
  unsigned int v35; // r9d
  signed int v36; // eax
  CEventLogger *v37; // rcx
  CEventLogger *v38; // rcx
  CEventLogger *v39; // rcx
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+34h] [rbp-CCh] BYREF
  int v44; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+3Ch] [rbp-C4h] BYREF
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  HCRYPTPROV phProv[6]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v49[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v47 = 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v42 = 1;
  v6 = 8;
  SetProcessMitigationPolicy(8, &v42, 4);
  v43 = 1;
  SetProcessMitigationPolicy(2, &v43, 4);
  v44 = 2;
  SetProcessMitigationPolicy(9, &v44, 4);
  v45 = 3;
  SetProcessMitigationPolicy(10, &v45, 4);
  v46 = 1;
  SetProcessMitigationPolicy(6, &v46, 4);
  SetErrorMode(1u);
  v7 = (CRemoteAssistanceApp *)operator new(0x428u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    _AtlModule = 0;
LABEL_38:
    v6 = 11;
    goto LABEL_39;
  }
  _AtlModule = CRemoteAssistanceApp::CRemoteAssistanceApp(v7);
  if ( !_AtlModule )
    goto LABEL_38;
  EventRegister(&RemoteAssistanceGUID, 0, 0, &g_Logger);
  *((_QWORD *)_AtlModule + 76) = hInstance;
  if ( CoInitialize(0) < 0 )
    goto LABEL_38;
  v8 = (CRATicket *)operator new(0x230u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
    v9 = CRATicket::CRATicket(v8);
  else
    v9 = 0;
  v10 = _AtlModule;
  *((_QWORD *)_AtlModule + 104) = v9;
  if ( v9 )
  {
    if ( *((_DWORD *)v10 + 211) )
      goto LABEL_68;
    memset(phProv, 0, sizeof(phProv));
    v11 = CRAEncryption::AcquireContext(phProv);
    if ( v11 == -2146893788 )
      ShowErrorMessage(545, 543, 0, 0, (const unsigned __int16 *)0xFFFE, 0);
    else
      v11 = 0;
    CRAEncryption::~CRAEncryption((CRAEncryption *)phProv);
    if ( v11 >= 0 )
    {
LABEL_68:
      if ( (int)CSettingsManager::Initialize((CEventLogger *)((char *)_AtlModule + 696)) < 0
        || (int)CSettingsManager::LoadUserSettings((CEventLogger *)((char *)_AtlModule + 696)) < 0 )
      {
        goto LABEL_15;
      }
      *((_QWORD *)_AtlModule + 75) = LoadIconW(*((HINSTANCE *)_AtlModule + 76), (LPCWSTR)0xFA3);
      v12 = RegisterApplicationRestart(L" -RecoverDesktop", 0);
      v13 = retaddr;
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x953,
          (unsigned int)"base\\diagnosis\\ra\\ui\\app.cpp",
          (const char *)(unsigned int)v12,
          v41);
      v14 = (unsigned __int16 *)&String;
      if ( lpCmdLine )
        v14 = lpCmdLine;
      CEventLogger::LogEvent(v13, &RA_Starting, v14);
      if ( (int)CReadWriteLock::Initialize((CEventLogger *)((char *)_AtlModule + 672)) < 0 )
      {
LABEL_15:
        v6 = 5;
      }
      else
      {
        CRemoteAssistanceApp::CheckAndRestoreDesktop(v15);
        if ( QueueUserWorkItem(CanUsePNRP, (char *)_AtlModule + 1008, 0x10u) )
        {
          v16 = TeredoExtAcquireTeredoConsumerHandle(3, &v47);
          if ( v16 < 0 )
            CEventLogger::LogError(
              v17,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\app.cpp",
              0x979u,
              L"wWinMain",
              v16);
          if ( !lpCmdLine || (v6 = 0, CRemoteAssistanceApp::ParseCmdLine(_AtlModule, lpCmdLine)) )
          {
            AcceleratorsW = LoadAcceleratorsW(hInstance, L"RA_APP");
            v19 = _AtlModule;
            *((_QWORD *)_AtlModule + 109) = AcceleratorsW;
            if ( AcceleratorsW )
            {
              v20 = CopyAcceleratorTableW(AcceleratorsW, 0, 0);
              v21 = v20;
              if ( v20 > 0 )
              {
                v22 = (struct tagACCEL *)calloc(v20, 6u);
                v23 = _AtlModule;
                *((_QWORD *)_AtlModule + 110) = v22;
                if ( v22 )
                  *((_DWORD *)_AtlModule + 222) = CopyAcceleratorTableW(*((HACCEL *)v23 + 109), v22, v21);
              }
            }
            else
            {
              CEventLogger::LogError(
                v19,
                &Recoverable_Error,
                L"base\\diagnosis\\ra\\ui\\app.cpp",
                0x992u,
                L"wWinMain",
                0);
            }
            if ( ATL::CAtlBaseModule::m_bInitFailed )
            {
              v6 = -1;
            }
            else
            {
              v24 = _AtlModule;
              v42 = 0;
              CommandLineW = GetCommandLineW();
              if ( (unsigned __int8)ATL::CAtlExeModuleT<CRemoteAssistanceApp>::ParseCommandLine(v26, CommandLineW, &v42) == 1 )
                v6 = CRemoteAssistanceApp::Run(v24);
              else
                v6 = v42;
            }
          }
        }
      }
    }
    else
    {
      v6 = 0;
    }
  }
LABEL_39:
  v27 = (struct CRATicket *)*((_QWORD *)_AtlModule + 104);
  v28 = *((_DWORD *)_AtlModule + 251);
  memset_0(v49, 0, sizeof(v49));
  switch ( v28 )
  {
    case 1:
      DiagnoseRASystemHealth((HWND)v29);
      break;
    case 2:
    case 3:
      v33 = InitializeDiagData((struct _RADIAG_DATA *)v49, v27, v28);
      if ( v33 >= 0 )
      {
        v33 = RunDiagnosisLoop((struct _RADIAG_DATA *)v49);
        if ( v33 >= 0 )
        {
          CleanupDiagData((struct _RADIAG_DATA *)v49);
          break;
        }
        v35 = 2824;
      }
      else
      {
        v35 = 2823;
      }
      CEventLogger::LogError(
        v34,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        v35,
        L"CheckForDiagnosis",
        v33);
      break;
    case 4:
      v31 = 4;
      v32 = 0;
      goto LABEL_48;
    default:
      if ( (unsigned int)(v28 - 5) <= 1 )
      {
        if ( !v27 )
        {
          CEventLogger::LogError(
            v29,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\app.cpp",
            0xB15u,
            L"CheckForDiagnosis",
            0x80004003);
          break;
        }
        v31 = v28;
        v32 = v27;
LABEL_48:
        DiagnosePNRPFailure(v32, v31, v30);
      }
      break;
  }
  if ( v47 )
  {
    v36 = TeredoExtReleaseTeredoConsumerHandle(&v47);
    if ( v36 < 0 )
      CEventLogger::LogError(v37, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\app.cpp", 0x9C1u, L"wWinMain", v36);
  }
  CSqmManager::ProcessRAEvent((char *)_AtlModule + 496, 2);
  if ( v6 )
    ShowErrorMessage(531, 650, 0, 0, (const unsigned __int16 *)0xFFFE, 0);
  CEventLogger::LogEvent(v38, &RA_Ending);
  v39 = _AtlModule;
  if ( _AtlModule )
  {
    if ( *((_QWORD *)_AtlModule + 77) )
      *((_QWORD *)_AtlModule + 77) = 0;
    (**(void (__fastcall ***)(CEventLogger *, __int64))v39)(v39, 1);
  }
  CoUninitialize();
  return v6;
}

```

## disassembly

```asm
0x1400194c8  mov     [rsp-8+arg_8], rbx
0x1400194cd  push    rbp
0x1400194ce  push    rsi
0x1400194cf  push    rdi
0x1400194d0  push    r12
0x1400194d2  push    r13
0x1400194d4  push    r14
0x1400194d6  push    r15
0x1400194d8  lea     rbp, [rsp-10h]
0x1400194dd  sub     rsp, 110h
0x1400194e4  mov     rax, cs:__security_cookie
0x1400194eb  xor     rax, rsp
0x1400194ee  mov     [rbp+40h+var_40], rax
0x1400194f2  mov     rsi, r8
0x1400194f5  mov     r14, rcx
0x1400194f8  xor     r15d, r15d
0x1400194fb  mov     [rsp+140h+var_F8], r15
0x140019500  xor     r9d, r9d; HeapInformationLength
0x140019503  xor     r8d, r8d; HeapInformation
0x140019506  lea     edi, [r15+1]
0x14001950a  mov     edx, edi; HeapInformationClass
0x14001950c  xor     ecx, ecx; HeapHandle
0x14001950e  call    cs:__imp_HeapSetInformation
0x140019515  nop     dword ptr [rax+rax+00h]
0x14001951a  mov     [rsp+140h+var_110], edi
0x14001951e  lea     r12d, [r15+4]
0x140019522  mov     r8d, r12d
0x140019525  lea     rdx, [rsp+140h+var_110]
0x14001952a  lea     ebx, [rdi+7]
0x14001952d  mov     ecx, ebx
0x14001952f  call    cs:__imp_SetProcessMitigationPolicy
0x140019536  nop     dword ptr [rax+rax+00h]
0x14001953b  mov     [rsp+140h+var_10C], edi
0x14001953f  mov     r8d, r12d
0x140019542  lea     rdx, [rsp+140h+var_10C]
0x140019547  lea     r13d, [r15+2]
0x14001954b  mov     ecx, r13d
0x14001954e  call    cs:__imp_SetProcessMitigationPolicy
0x140019555  nop     dword ptr [rax+rax+00h]
0x14001955a  mov     [rsp+140h+var_108], r13d
0x14001955f  mov     r8d, r12d
0x140019562  lea     rdx, [rsp+140h+var_108]
0x140019567  lea     ecx, [rdi+8]
0x14001956a  call    cs:__imp_SetProcessMitigationPolicy
0x140019571  nop     dword ptr [rax+rax+00h]
0x140019576  mov     [rsp+140h+var_104], 3
0x14001957e  mov     r8d, r12d
0x140019581  lea     rdx, [rsp+140h+var_104]
0x140019586  lea     ecx, [rdi+9]
0x140019589  call    cs:__imp_SetProcessMitigationPolicy
0x140019590  nop     dword ptr [rax+rax+00h]
0x140019595  mov     [rsp+140h+var_100], edi
0x140019599  mov     r8d, r12d
0x14001959c  lea     rdx, [rsp+140h+var_100]
0x1400195a1  lea     ecx, [rdi+5]
0x1400195a4  call    cs:__imp_SetProcessMitigationPolicy
0x1400195ab  nop     dword ptr [rax+rax+00h]
0x1400195b0  mov     ecx, edi; uMode
0x1400195b2  call    cs:__imp_SetErrorMode
0x1400195b9  nop     dword ptr [rax+rax+00h]
0x1400195be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400195c5  mov     ecx, 428h; unsigned __int64
0x1400195ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400195cf  lea     rdi, aWwinmain; "wWinMain"
0x1400195d6  lea     r12, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x1400195dd  lea     r13, Recoverable_Error
0x1400195e4  test    rax, rax
0x1400195e7  jz      loc_14001994C
0x1400195ed  mov     rcx, rax; this
0x1400195f0  call    ??0CRemoteAssistanceApp@@QEAA@XZ; CRemoteAssistanceApp::CRemoteAssistanceApp(void)
0x1400195f5  mov     cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA, rax; CRemoteAssistanceApp * _AtlModule
0x1400195fc  test    rax, rax
0x1400195ff  jz      loc_140019953
0x140019605  lea     r9, ?g_Logger@@3VCEventLogger@@A; RegHandle
0x14001960c  xor     r8d, r8d; CallbackContext
0x14001960f  xor     edx, edx; EnableCallback
0x140019611  lea     rcx, RemoteAssistanceGUID; ProviderId
0x140019618  call    cs:__imp_EventRegister
0x14001961f  nop     dword ptr [rax+rax+00h]
0x140019624  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001962b  mov     [rax+260h], r14
0x140019632  xor     ecx, ecx; pvReserved
0x140019634  call    cs:__imp_CoInitialize
0x14001963b  nop     dword ptr [rax+rax+00h]
0x140019640  test    eax, eax
0x140019642  js      loc_140019953
0x140019648  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001964f  mov     ecx, 230h; unsigned __int64
0x140019654  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140019659  test    rax, rax
0x14001965c  jz      short loc_14001966B
0x14001965e  mov     rcx, rax; this
0x140019661  call    ??0CRATicket@@QEAA@XZ; CRATicket::CRATicket(void)
0x140019666  mov     rcx, rax
0x140019669  jmp     short loc_14001966E
0x14001966b  mov     rcx, r15
0x14001966e  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140019675  mov     [rax+340h], rcx
0x14001967c  test    rcx, rcx
0x14001967f  jz      loc_140019958
0x140019685  cmp     [rax+34Ch], r15d
0x14001968c  jnz     short loc_140019702
0x14001968e  mov     [rsp+140h+phProv], r15
0x140019693  mov     [rsp+140h+var_E8], r15
0x140019698  mov     [rsp+140h+var_E0], r15
0x14001969d  mov     [rsp+140h+var_D8], r15
0x1400196a2  mov     [rsp+140h+var_D0], r15
0x1400196a7  mov     [rsp+140h+var_C8], r15
0x1400196ac  lea     rcx, [rsp+140h+phProv]; phProv
0x1400196b1  call    ?AcquireContext@CRAEncryption@@QEAAJXZ; CRAEncryption::AcquireContext(void)
0x1400196b6  mov     edi, eax
0x1400196b8  cmp     eax, 80090024h
0x1400196bd  jz      short loc_1400196C4
0x1400196bf  mov     edi, r15d
0x1400196c2  jmp     short loc_1400196E5
0x1400196c4  mov     [rsp+140h+var_118], r15d; int
0x1400196c9  mov     [rsp+140h+var_120], 0FFFEh; int
0x1400196d2  xor     r9d, r9d; int
0x1400196d5  xor     r8d, r8d; HWND
0x1400196d8  mov     edx, 21Fh; int
0x1400196dd  lea     ecx, [rdx+2]; int
0x1400196e0  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x1400196e5  lea     rcx, [rsp+140h+phProv]; this
0x1400196ea  call    ??1CRAEncryption@@QEAA@XZ; CRAEncryption::~CRAEncryption(void)
0x1400196ef  test    edi, edi
0x1400196f1  jns     short loc_1400196FB
0x1400196f3  mov     ebx, r15d
0x1400196f6  jmp     loc_140019958
0x1400196fb  lea     rdi, aWwinmain; "wWinMain"
0x140019702  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140019709  add     rcx, 2B8h; this
0x140019710  call    ?Initialize@CSettingsManager@@QEAAJXZ; CSettingsManager::Initialize(void)
0x140019715  test    eax, eax
0x140019717  jns     short loc_140019723
0x140019719  mov     ebx, 5
0x14001971e  jmp     loc_140019958
0x140019723  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001972a  add     rcx, 2B8h; this
0x140019731  call    ?LoadUserSettings@CSettingsManager@@QEAAJXZ; CSettingsManager::LoadUserSettings(void)
0x140019736  test    eax, eax
0x140019738  js      short loc_140019719
0x14001973a  mov     edx, 0FA3h; lpIconName
0x14001973f  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140019746  mov     rcx, [rcx+260h]; hInstance
0x14001974d  call    cs:__imp_LoadIconW
0x140019754  nop     dword ptr [rax+rax+00h]
0x140019759  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140019760  mov     [rcx+258h], rax
0x140019767  xor     edx, edx; dwFlags
0x140019769  lea     rcx, pwzCommandline; " -RecoverDesktop"
0x140019770  call    cs:__imp_RegisterApplicationRestart
0x140019777  nop     dword ptr [rax+rax+00h]
0x14001977c  mov     rcx, [rbp+48h]; this
0x140019780  test    eax, eax
0x140019782  jns     short loc_140019798
0x140019784  mov     r9d, eax; char *
0x140019787  lea     r8, aBaseDiagnosisR_8; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14001978e  mov     edx, 953h; void *
0x140019793  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140019798  lea     rdx, RA_Starting; struct _EVENT_DESCRIPTOR *
0x14001979f  test    rsi, rsi
0x1400197a2  lea     r8, String
0x1400197a9  jz      short loc_1400197AE
0x1400197ab  mov     r8, rsi; unsigned __int16 *
0x1400197ae  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x1400197b3  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400197ba  add     rcx, 2A0h; this
0x1400197c1  call    ?Initialize@CReadWriteLock@@QEAAJXZ; CReadWriteLock::Initialize(void)
0x1400197c6  test    eax, eax
0x1400197c8  js      loc_140019719
0x1400197ce  call    ?CheckAndRestoreDesktop@CRemoteAssistanceApp@@QEAAXXZ; CRemoteAssistanceApp::CheckAndRestoreDesktop(void)
0x1400197d3  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400197da  add     rdx, 3F0h; Context
0x1400197e1  mov     r8d, 10h; Flags
0x1400197e7  lea     rcx, ?CanUsePNRP@@YAKPEAX@Z; Function
0x1400197ee  call    cs:__imp_QueueUserWorkItem
0x1400197f5  nop     dword ptr [rax+rax+00h]
0x1400197fa  test    eax, eax
0x1400197fc  jz      loc_140019958
0x140019802  lea     rdx, [rsp+140h+var_F8]
0x140019807  mov     ecx, 3
0x14001980c  call    cs:__imp_TeredoExtAcquireTeredoConsumerHandle
0x140019813  nop     dword ptr [rax+rax+00h]
0x140019818  test    eax, eax
0x14001981a  jns     short loc_140019836
0x14001981c  mov     [rsp+140h+var_118], eax; unsigned int
0x140019820  mov     [rsp+140h+var_120], rdi; unsigned __int16 *
0x140019825  mov     r9d, 979h; unsigned int
0x14001982b  mov     r8, r12; unsigned __int16 *
0x14001982e  mov     rdx, r13; struct _EVENT_DESCRIPTOR *
0x140019831  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140019836  test    rsi, rsi
0x140019839  jz      short loc_140019855
0x14001983b  mov     ebx, r15d
0x14001983e  mov     rdx, rsi; unsigned __int16 *
0x140019841  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; this
0x140019848  call    ?ParseCmdLine@CRemoteAssistanceApp@@QEAAHPEAG@Z; CRemoteAssistanceApp::ParseCmdLine(ushort *)
0x14001984d  test    eax, eax
0x14001984f  jz      loc_140019958
0x140019855  lea     rdx, TableName; "RA_APP"
0x14001985c  mov     rcx, r14; hInstance
0x14001985f  call    cs:__imp_LoadAcceleratorsW
0x140019866  nop     dword ptr [rax+rax+00h]
0x14001986b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; this
0x140019872  mov     [rcx+368h], rax
0x140019879  test    rax, rax
0x14001987c  jnz     short loc_14001989B
0x14001987e  mov     [rsp+140h+var_118], r15d; unsigned int
0x140019883  mov     [rsp+140h+var_120], rdi; unsigned __int16 *
0x140019888  mov     r9d, 992h; unsigned int
0x14001988e  mov     r8, r12; unsigned __int16 *
0x140019891  mov     rdx, r13; struct _EVENT_DESCRIPTOR *
0x140019894  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140019899  jmp     short loc_140019903
0x14001989b  xor     r8d, r8d; cAccelEntries
0x14001989e  xor     edx, edx; lpAccelDst
0x1400198a0  mov     rcx, rax; hAccelSrc
0x1400198a3  call    cs:__imp_CopyAcceleratorTableW
0x1400198aa  nop     dword ptr [rax+rax+00h]
0x1400198af  movsxd  rbx, eax
0x1400198b2  test    eax, eax
0x1400198b4  jle     short loc_140019903
0x1400198b6  mov     rcx, rbx; Count
0x1400198b9  mov     edx, 6; Size
0x1400198be  call    cs:__imp_calloc
0x1400198c5  nop     dword ptr [rax+rax+00h]
0x1400198ca  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400198d1  mov     [rcx+370h], rax
0x1400198d8  test    rax, rax
0x1400198db  jz      short loc_140019903
0x1400198dd  mov     r8d, ebx; cAccelEntries
0x1400198e0  mov     rdx, rax; lpAccelDst
0x1400198e3  mov     rcx, [rcx+368h]; hAccelSrc
0x1400198ea  call    cs:__imp_CopyAcceleratorTableW
0x1400198f1  nop     dword ptr [rax+rax+00h]
0x1400198f6  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400198fd  mov     [rcx+378h], eax
0x140019903  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, r15b; bool ATL::CAtlBaseModule::m_bInitFailed
0x14001990a  jz      short loc_140019911
0x14001990c  or      ebx, 0FFFFFFFFh
0x14001990f  jmp     short loc_14001994A
0x140019911  mov     rbx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140019918  mov     [rsp+140h+var_110], r15d
0x14001991d  call    cs:__imp_GetCommandLineW
0x140019924  nop     dword ptr [rax+rax+00h]
0x140019929  lea     r8, [rsp+140h+var_110]
0x14001992e  mov     rdx, rax
0x140019931  call    ?ParseCommandLine@?$CAtlExeModuleT@VCRemoteAssistanceApp@@@ATL@@QEAA_NPEBGPEAJ@Z; ATL::CAtlExeModuleT<CRemoteAssistanceApp>::ParseCommandLine(ushort const *,long *)
0x140019936  cmp     al, 1
0x140019938  jnz     short loc_140019946
0x14001993a  mov     rcx, rbx; this
0x14001993d  call    ?Run@CRemoteAssistanceApp@@QEAAJH@Z; CRemoteAssistanceApp::Run(int)
0x140019942  mov     ebx, eax
0x140019944  jmp     short loc_14001994A
0x140019946  mov     ebx, [rsp+140h+var_110]
0x14001994a  jmp     short loc_140019958
0x14001994c  mov     cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA, r15; CRemoteAssistanceApp * _AtlModule
0x140019953  mov     ebx, 0Bh
0x140019958  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001995f  mov     rdi, [rcx+340h]
0x140019966  mov     esi, [rcx+3ECh]
0x14001996c  xor     edx, edx; Val
0x14001996e  mov     r8d, 80h; Size
0x140019974  lea     rcx, [rbp+40h+var_C0]; void *
0x140019978  call    memset_0
0x14001997d  mov     eax, esi
0x14001997f  sub     eax, 1
0x140019982  jz      loc_140019A25
0x140019988  sub     eax, 1
0x14001998b  jz      short loc_1400199CF
0x14001998d  sub     eax, 1
0x140019990  jz      short loc_1400199CF
0x140019992  sub     eax, 1
0x140019995  jz      short loc_1400199C1
0x140019997  sub     eax, 1
0x14001999a  jz      short loc_1400199A5
0x14001999c  cmp     eax, 1
0x14001999f  jnz     loc_140019A2A
0x1400199a5  test    rdi, rdi
0x1400199a8  jnz     short loc_1400199BA
0x1400199aa  mov     [rsp+140h+var_118], 80004003h
0x1400199b2  mov     r9d, 0B15h
0x1400199b8  jmp     short loc_1400199EC
0x1400199ba  mov     edx, esi
0x1400199bc  mov     rcx, rdi
0x1400199bf  jmp     short loc_1400199C8
0x1400199c1  mov     edx, 4; unsigned int
0x1400199c6  xor     ecx, ecx; this
0x1400199c8  call    ?DiagnosePNRPFailure@@YAJPEAVCRATicket@@KPEAUHWND__@@@Z; DiagnosePNRPFailure(CRATicket *,ulong,HWND__ *)
0x1400199cd  jmp     short loc_140019A2A
0x1400199cf  mov     r8d, esi; unsigned int
0x1400199d2  mov     rdx, rdi; this
0x1400199d5  lea     rcx, [rbp+40h+var_C0]; struct _RADIAG_DATA *
0x1400199d9  call    ?InitializeDiagData@@YAJPEAU_RADIAG_DATA@@PEAVCRATicket@@K@Z; InitializeDiagData(_RADIAG_DATA *,CRATicket *,ulong)
0x1400199de  test    eax, eax
0x1400199e0  jns     short loc_140019A05
0x1400199e2  mov     r9d, 0B07h; unsigned int
0x1400199e8  mov     [rsp+140h+var_118], eax; unsigned int
0x1400199ec  lea     rax, aCheckfordiagno; "CheckForDiagnosis"
0x1400199f3  mov     [rsp+140h+var_120], rax; unsigned __int16 *
  ... truncated ...
```
