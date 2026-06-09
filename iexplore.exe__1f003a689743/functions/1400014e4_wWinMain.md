# wWinMain

- ea: `0x1400014e4`
- end: `0x1400017eb`
- name: `wWinMain`
- size: `775`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001970`

## callees

- `0x140001184`
- `0x140001234`
- `0x1400014e4`
- `0x1400017f4`
- `0x14000237c`
- `0x14000244c`
- `0x140002548`
- `0x140003260`
- `0x140003394`
- `0x140003fec`
- `0x1400040c8`
- `0x140004128`
- `0x140004a3c`
- `0x140004ebc`
- `0x140005598`
- `0x1400055c8`
- `0x14000566c`
- `0x140005710`
- `0x1400059b0`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x1400015f4`
- `KERNEL32!HeapSetInformation` at `0x1400015f4`
- `KERNEL32!IsDebuggerPresent` at `0x14000159b`
- `KERNEL32!IsDebuggerPresent` at `0x14000159b`
- `KERNEL32!DeleteCriticalSection` at `0x140001788`
- `KERNEL32!DeleteCriticalSection` at `0x140001788`
- `KERNEL32!GetCurrentProcess` at `0x1400017ab`
- `KERNEL32!GetCurrentProcess` at `0x1400017ab`
- `KERNEL32!TerminateProcess` at `0x1400017b6`
- `KERNEL32!TerminateProcess` at `0x1400017b6`
- `KERNEL32!InitializeCriticalSection` at `0x14000153f`
- `KERNEL32!InitializeCriticalSection` at `0x14000153f`
- `KERNEL32!SetErrorMode` at `0x1400015d3`
- `KERNEL32!SetErrorMode` at `0x1400015d3`
- `KERNEL32!LocalFree` at `0x1400016f1`
- `KERNEL32!LocalFree` at `0x1400016f1`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x14000161e`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x14000161e`
- `iertutil!__imp_GetValue` at `0x140001733`
- `iertutil!__imp_GetValue` at `0x140001758`
- `iertutil!__imp_GetValue` at `0x140001733`
- `iertutil!__imp_GetValue` at `0x140001758`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x140001604`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x140001604`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x1400015ba`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x1400015ba`
- `iertutil!__imp_?IEConfiguration_SetApplicationUniqueInternetExplorerCLSID@@YAJXZ` at `0x140001550`
- `iertutil!__imp_?IEConfiguration_SetApplicationUniqueInternetExplorerCLSID@@YAJXZ` at `0x140001550`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x14000156c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x14000156c`
- `IEFRAME!__imp_ClearDestinationList` at `0x14000164f`
- `IEFRAME!__imp_ClearDestinationList` at `0x14000164f`
- `IEFRAME!__imp_LCIEStartAsContentProcess` at `0x140001689`
- `IEFRAME!__imp_LCIEStartAsContentProcess` at `0x140001689`
- `IEFRAME!__imp_DesktopFrameProcess` at `0x1400016e3`
- `IEFRAME!__imp_DesktopFrameProcess` at `0x1400016e3`
- `IEFRAME!__imp_AutomationFrameProcess` at `0x1400016cf`
- `IEFRAME!__imp_AutomationFrameProcess` at `0x1400016cf`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140001587`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140001591`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140001587`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140001591`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  UINT v9; // ebx
  GUID v10; // xmm6
  char v11; // r14
  unsigned __int16 *Arguments; // rdi
  char Bool; // al
  const WCHAR *v14; // rcx
  __int64 v15; // rdx
  UINT v16; // eax
  const unsigned __int16 *v17; // rdx
  HKEY v18; // rcx
  const unsigned __int16 *v19; // r8
  HANDLE CurrentProcess; // rax
  int v22; // [rsp+40h] [rbp-40h] BYREF
  int v23; // [rsp+44h] [rbp-3Ch] BYREF
  BOOL v24; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+4Ch] [rbp-34h] BYREF
  GUID pguid; // [rsp+50h] [rbp-30h] BYREF

  McGenEventRegister_EventRegister(hInstance, hPrevInstance, lpCmdLine);
  if ( (Microsoft_IEFRAMEEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, v5, v7, v8, (PEVENT_DATA_DESCRIPTOR)&pguid);
  InitializeCriticalSection(&g_csDll);
  v9 = 1;
  v23 = 1;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  if ( IEConfiguration_SetApplicationUniqueInternetExplorerCLSID() < 0 )
  {
    v9 = 0;
    goto LABEL_30;
  }
  pguid = 0;
  if ( CoCreateGuid(&pguid) >= 0 )
  {
    v10 = pguid;
  }
  else
  {
    v10 = GUID_NULL;
    pguid = GUID_NULL;
  }
  *(GUID *)GlobalThreadState() = v10;
  *((_BYTE *)GlobalThreadState() + 16) = 1;
  v24 = IsDebuggerPresent();
  BrowserTelemetry::IEApplicationStart<int>(&v24);
  if ( (int)IEConfiguration_SetBrowserAppProfile(L"Internet Explorer", 1u, 0) < 0 )
  {
    v9 = 0;
    v23 = 0;
    goto LABEL_28;
  }
  v11 = 0;
  InitSearchPaths();
  SetErrorMode(1u);
  v22 = 0;
  Arguments = GetArguments(&v22);
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  EnableUser32ExceptionHandlerHardening();
  Bool = IEConfiguration_GetBool(268435505);
  v14 = L"Microsoft.InternetExplorer.Preview";
  if ( !Bool )
    v14 = L"Microsoft.InternetExplorer.Default";
  SetCurrentProcessExplicitAppUserModelID(v14);
  v15 = -1;
  do
    ++v15;
  while ( Arguments[v15] );
  if ( FindOrRemoveCommandSwitch(Arguments, v15 + 1, L"-ResetDestinationList", 1) )
  {
    BrowserTelemetry::IEShortLivedProcess<unsigned short const (&)[21]>();
    ClearDestinationList();
    v9 = 0;
LABEL_19:
    v23 = v9;
    goto LABEL_25;
  }
  if ( (unsigned int)IsNewTabSwitchHandled(Arguments) )
    goto LABEL_25;
  if ( !(unsigned int)ThisIsATabProcess(Arguments) )
  {
    if ( v22 )
    {
      v9 = 5;
    }
    else
    {
      BrowserTelemetry::IESessionIDInvalidated();
      v11 = 1;
      v9 = LCIEStartAsContentProcess(Arguments, (unsigned int)nShowCmd);
    }
    goto LABEL_19;
  }
  if ( IsCommandSwitchPresent(Arguments, L"-embedding") && IsCommandSwitchPresent(Arguments, L"-startmanager") )
    v16 = AutomationFrameProcess(Arguments, (unsigned int)nShowCmd, 1, (unsigned int)v22);
  else
    v16 = DesktopFrameProcess(Arguments, (unsigned int)nShowCmd, 1, (unsigned int)v22);
  v23 = v16;
  v9 = v16;
LABEL_25:
  LocalFree(Arguments);
  if ( !v11 )
  {
LABEL_28:
    v24 = 0;
    v22 = 0;
    GetValue((__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow[0], 1, 1, &v24, 4, 0, 0);
    GetValue((__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh, 1, 1, &v22, 4, 0, 0);
    pguid.Data1 = v24;
    *(_DWORD *)&pguid.Data2 = v22;
    BrowserTelemetry::IEApplicationExit<unsigned long &,__int64 &>(&v23, &pguid);
  }
LABEL_30:
  DeleteCriticalSection(&g_csDll);
  McGenEventUnregister_EventUnregister();
  TraceLoggingUnregister_EventUnregister();
  v25 = 0;
  SHRegGetDWORD(v18, v17, v19, &v25);
  if ( v25 )
  {
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1400014e4  mov     [rsp-28h+arg_0], rbx
0x1400014e9  mov     [rsp-28h+arg_8], rsi
0x1400014ee  push    rbp
0x1400014ef  push    rdi
0x1400014f0  push    r12
0x1400014f2  push    r14
0x1400014f4  push    r15
0x1400014f6  mov     rbp, rsp
0x1400014f9  sub     rsp, 80h
0x140001500  movaps  [rsp+80h+var_10], xmm6
0x140001505  mov     rax, cs:__security_cookie
0x14000150c  xor     rax, rsp
0x14000150f  mov     [rbp+var_20], rax
0x140001513  mov     esi, r9d
0x140001516  call    McGenEventRegister_EventRegister
0x14000151b  mov     r12d, 1
0x140001521  test    cs:Microsoft_IEFRAMEEnableBits, r12b
0x140001528  jz      short loc_140001538
0x14000152a  lea     rax, [rbp+pguid]
0x14000152e  mov     [rsp+80h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x140001533  call    McGenEventWrite_EventWriteTransfer
0x140001538  lea     rcx, g_csDll; lpCriticalSection
0x14000153f  call    cs:__imp_InitializeCriticalSection
0x140001545  mov     ebx, r12d
0x140001548  mov     [rbp+var_3C], ebx
0x14000154b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140001550  call    cs:__imp_?IEConfiguration_SetApplicationUniqueInternetExplorerCLSID@@YAJXZ; IEConfiguration_SetApplicationUniqueInternetExplorerCLSID(void)
0x140001556  xor     r15d, r15d
0x140001559  test    eax, eax
0x14000155b  js      loc_14000177E
0x140001561  xorps   xmm0, xmm0
0x140001564  lea     rcx, [rbp+pguid]; pguid
0x140001568  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x14000156c  call    cs:__imp_CoCreateGuid
0x140001572  test    eax, eax
0x140001574  jns     short loc_140001583
0x140001576  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x14000157d  movaps  xmmword ptr [rbp+pguid.Data1], xmm6
0x140001581  jmp     short loc_140001587
0x140001583  movaps  xmm6, xmmword ptr [rbp+pguid.Data1]
0x140001587  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x14000158d  movdqu  xmmword ptr [rax], xmm6
0x140001591  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x140001597  mov     [rax+10h], r12b
0x14000159b  call    cs:__imp_IsDebuggerPresent
0x1400015a1  lea     rcx, [rbp+var_38]
0x1400015a5  mov     [rbp+var_38], eax
0x1400015a8  call    ??$IEApplicationStart@H@BrowserTelemetry@@SAX$$QEAH@Z; BrowserTelemetry::IEApplicationStart<int>(int &&)
0x1400015ad  xor     r8d, r8d
0x1400015b0  lea     rcx, aInternetExplor; "Internet Explorer"
0x1400015b7  mov     edx, r12d
0x1400015ba  call    cs:__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z; IEConfiguration_SetBrowserAppProfile(ushort const *,ulong,ulong)
0x1400015c0  test    eax, eax
0x1400015c2  js      loc_140001701
0x1400015c8  mov     r14b, r15b
0x1400015cb  call    ?InitSearchPaths@@YAXXZ; InitSearchPaths(void)
0x1400015d0  mov     ecx, r12d; uMode
0x1400015d3  call    cs:__imp_SetErrorMode
0x1400015d9  lea     rcx, [rbp+var_40]; int *
0x1400015dd  mov     [rbp+var_40], r15d
0x1400015e1  call    ?GetArguments@@YAPEAGPEAH@Z; GetArguments(int *)
0x1400015e6  xor     r9d, r9d; HeapInformationLength
0x1400015e9  xor     r8d, r8d; HeapInformation
0x1400015ec  mov     edx, r12d; HeapInformationClass
0x1400015ef  xor     ecx, ecx; HeapHandle
0x1400015f1  mov     rdi, rax
0x1400015f4  call    cs:__imp_HeapSetInformation
0x1400015fa  call    ?EnableUser32ExceptionHandlerHardening@@YAHXZ; EnableUser32ExceptionHandlerHardening(void)
0x1400015ff  mov     ecx, 10000031h
0x140001604  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x14000160a  test    al, al
0x14000160c  lea     rdx, AppID; "Microsoft.InternetExplorer.Default"
0x140001613  lea     rcx, aMicrosoftInter; "Microsoft.InternetExplorer.Preview"
0x14000161a  cmovz   rcx, rdx; AppID
0x14000161e  call    cs:__imp_SetCurrentProcessExplicitAppUserModelID
0x140001624  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001628  inc     rdx
0x14000162b  cmp     [rdi+rdx*2], r15w
0x140001630  jnz     short loc_140001628
0x140001632  inc     edx; unsigned int
0x140001634  lea     r8, aResetdestinati; "-ResetDestinationList"
0x14000163b  mov     r9b, r12b; bool
0x14000163e  mov     rcx, rdi; unsigned __int16 *
0x140001641  call    ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
0x140001646  test    al, al
0x140001648  jz      short loc_14000165A
0x14000164a  call    ??$IEShortLivedProcess@AEAY0BF@$$CBG@BrowserTelemetry@@SAXAEAY0BF@$$CBG@Z; BrowserTelemetry::IEShortLivedProcess<ushort const (&)[21]>(ushort const (&)[21])
0x14000164f  call    cs:__imp_ClearDestinationList
0x140001655  mov     ebx, r15d
0x140001658  jmp     short loc_140001698
0x14000165a  mov     rcx, rdi; unsigned __int16 *
0x14000165d  call    ?IsNewTabSwitchHandled@@YAHPEAG@Z; IsNewTabSwitchHandled(ushort *)
0x140001662  test    eax, eax
0x140001664  jnz     loc_1400016EE
0x14000166a  mov     rcx, rdi; unsigned __int16 *
0x14000166d  call    ?ThisIsATabProcess@@YAJPEAG@Z; ThisIsATabProcess(ushort *)
0x140001672  test    eax, eax
0x140001674  jnz     short loc_14000169D
0x140001676  cmp     [rbp+var_40], r15d
0x14000167a  jnz     short loc_140001693
0x14000167c  call    ?IESessionIDInvalidated@BrowserTelemetry@@SAXXZ; BrowserTelemetry::IESessionIDInvalidated(void)
0x140001681  mov     edx, esi
0x140001683  mov     rcx, rdi
0x140001686  mov     r14b, r12b
0x140001689  call    cs:__imp_LCIEStartAsContentProcess
0x14000168f  mov     ebx, eax
0x140001691  jmp     short loc_140001698
0x140001693  mov     ebx, 5
0x140001698  mov     [rbp+var_3C], ebx
0x14000169b  jmp     short loc_1400016EE
0x14000169d  lea     rdx, aEmbedding; "-embedding"
0x1400016a4  mov     rcx, rdi; unsigned __int16 *
0x1400016a7  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1400016ac  test    al, al
0x1400016ae  jz      short loc_1400016D7
0x1400016b0  lea     rdx, aStartmanager; "-startmanager"
0x1400016b7  mov     rcx, rdi; unsigned __int16 *
0x1400016ba  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1400016bf  test    al, al
0x1400016c1  jz      short loc_1400016D7
0x1400016c3  mov     r9d, [rbp+var_40]
0x1400016c7  mov     r8d, r12d
0x1400016ca  mov     edx, esi
0x1400016cc  mov     rcx, rdi
0x1400016cf  call    cs:__imp_AutomationFrameProcess
0x1400016d5  jmp     short loc_1400016E9
0x1400016d7  mov     r9d, [rbp+var_40]
0x1400016db  mov     r8d, r12d
0x1400016de  mov     edx, esi
0x1400016e0  mov     rcx, rdi
0x1400016e3  call    cs:__imp_DesktopFrameProcess
0x1400016e9  mov     [rbp+var_3C], eax
0x1400016ec  mov     ebx, eax
0x1400016ee  mov     rcx, rdi; hMem
0x1400016f1  call    cs:__imp_LocalFree
0x1400016f7  test    r14b, r14b
0x1400016fa  jz      short loc_140001707
0x1400016fc  jmp     loc_140001781
0x140001701  mov     ebx, r15d
0x140001704  mov     [rbp+var_3C], ebx
0x140001707  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionLow@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow
0x14000170e  lea     r9, [rbp+var_38]
0x140001712  mov     [rsp+80h+var_50], r15
0x140001717  mov     edi, 4
0x14000171c  mov     [rsp+80h+var_58], r15
0x140001721  mov     r8d, r12d
0x140001724  mov     edx, r12d
0x140001727  mov     dword ptr [rsp+80h+var_60], edi
0x14000172b  mov     [rbp+var_38], r15d
0x14000172f  mov     [rbp+var_40], r15d
0x140001733  call    cs:__imp_GetValue
0x140001739  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionHigh@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh
0x140001740  lea     r9, [rbp+var_40]
0x140001744  mov     [rsp+80h+var_50], r15
0x140001749  mov     r8d, r12d
0x14000174c  mov     [rsp+80h+var_58], r15
0x140001751  mov     edx, r12d
0x140001754  mov     dword ptr [rsp+80h+var_60], edi
0x140001758  call    cs:__imp_GetValue
0x14000175e  mov     ecx, [rbp+var_40]
0x140001761  lea     rdx, [rbp+pguid]
0x140001765  mov     eax, [rbp+var_38]
0x140001768  shl     rcx, 20h
0x14000176c  or      rcx, rax
0x14000176f  mov     qword ptr [rbp+pguid.Data1], rcx
0x140001773  lea     rcx, [rbp+var_3C]
0x140001777  call    ??$IEApplicationExit@AEAKAEA_J@BrowserTelemetry@@SAXAEAKAEA_J@Z; BrowserTelemetry::IEApplicationExit<ulong &,__int64 &>(ulong &,__int64 &)
0x14000177c  jmp     short loc_140001781
0x14000177e  mov     ebx, r15d
0x140001781  lea     rcx, g_csDll; lpCriticalSection
0x140001788  call    cs:__imp_DeleteCriticalSection
0x14000178e  call    McGenEventUnregister_EventUnregister
0x140001793  call    TraceLoggingUnregister_EventUnregister
0x140001798  lea     r9, [rbp+var_34]; unsigned int *
0x14000179c  mov     [rbp+var_34], r15d
0x1400017a0  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400017a5  cmp     [rbp+var_34], r15d
0x1400017a9  jz      short loc_1400017BC
0x1400017ab  call    cs:__imp_GetCurrentProcess
0x1400017b1  mov     rcx, rax; hProcess
0x1400017b4  mov     edx, ebx; uExitCode
0x1400017b6  call    cs:__imp_TerminateProcess
0x1400017bc  mov     eax, ebx
0x1400017be  mov     rcx, [rbp+var_20]
0x1400017c2  xor     rcx, rsp; StackCookie
0x1400017c5  call    __security_check_cookie
0x1400017ca  lea     r11, [rsp+80h+var_s0]
0x1400017d2  mov     rbx, [r11+30h]
0x1400017d6  mov     rsi, [r11+38h]
0x1400017da  movaps  xmm6, [rsp+80h+var_10]
0x1400017df  mov     rsp, r11
0x1400017e2  pop     r15
0x1400017e4  pop     r14
0x1400017e6  pop     r12
0x1400017e8  pop     rdi
0x1400017e9  pop     rbp
0x1400017ea  retn
```
