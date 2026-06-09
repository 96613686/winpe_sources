# ProvOperations::PublishDeviceProvisioningLogs(ushort const *)

- ea: `0x1800145a0`
- end: `0x180014b04`
- name: `?PublishDeviceProvisioningLogs@ProvOperations@@UEAAJPEBG@Z`
- size: `1380`
- prototype: `int __fastcall(ProvOperations *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18000d0fc`
- `0x18000d498`
- `0x1800120bc`
- `0x1800145a0`
- `0x180018944`
- `0x180020710`
- `0x180020c5c`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180014673`
- `msvcrt!wcscat_s` at `0x18001468b`
- `msvcrt!wcscat_s` at `0x1800146a4`
- `msvcrt!wcscat_s` at `0x1800146b8`
- `msvcrt!wcscat_s` at `0x180014941`
- `msvcrt!wcscat_s` at `0x180014959`
- `msvcrt!wcscat_s` at `0x180014972`
- `msvcrt!wcscat_s` at `0x180014986`
- `msvcrt!wcscat_s` at `0x180014673`
- `msvcrt!wcscat_s` at `0x18001468b`
- `msvcrt!wcscat_s` at `0x1800146a4`
- `msvcrt!wcscat_s` at `0x1800146b8`
- `msvcrt!wcscat_s` at `0x180014941`
- `msvcrt!wcscat_s` at `0x180014959`
- `msvcrt!wcscat_s` at `0x180014972`
- `msvcrt!wcscat_s` at `0x180014986`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001473c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014a0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001473c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a41`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001472a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800149f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001472a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800149f8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180014751`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180014a1f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180014751`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180014a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001475c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001475c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a35`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001464a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180014918`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001464a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180014918`

## string_xrefs

- `0x180014643`: `%windir%\System32\MdmDiagnosticsTool.exe`
- `0x180014911`: `%windir%\System32\MdmDiagnosticsTool.exe`

## pseudocode

```c
int __fastcall ProvOperations::PublishDeviceProvisioningLogs(ProvOperations *this, const unsigned __int16 *a2)
{
  const char *v4; // r9
  unsigned int v5; // r8d
  const char *v6; // r9
  int result; // eax
  const char *v8; // r9
  signed int LastError; // eax
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-A18h] BYREF
  DWORD ExitCode; // [rsp+50h] [rbp-9C8h] BYREF
  int v15; // [rsp+54h] [rbp-9C4h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-9C0h] BYREF
  _QWORD v17[3]; // [rsp+70h] [rbp-9A8h] BYREF
  char v18; // [rsp+88h] [rbp-990h]
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-988h] BYREF
  wchar_t v20[8]; // [rsp+100h] [rbp-918h] BYREF
  wchar_t Source[8]; // [rsp+110h] [rbp-908h] BYREF
  WCHAR Dst[4]; // [rsp+120h] [rbp-8F8h] BYREF
  int v23; // [rsp+128h] [rbp-8F0h] BYREF
  char v24; // [rsp+12Ch] [rbp-8ECh]
  int v25; // [rsp+150h] [rbp-8C8h] BYREF
  const char *v26; // [rsp+158h] [rbp-8C0h]
  __int64 v27; // [rsp+160h] [rbp-8B8h]
  char v28; // [rsp+168h] [rbp-8B0h]
  int v29; // [rsp+170h] [rbp-8A8h]
  _BYTE v30[152]; // [rsp+178h] [rbp-8A0h] BYREF
  __int128 v31; // [rsp+210h] [rbp-808h]
  int v32; // [rsp+220h] [rbp-7F8h]
  __int64 v33; // [rsp+228h] [rbp-7F0h]
  int *v34; // [rsp+230h] [rbp-7E8h]
  __int64 v35; // [rsp+238h] [rbp-7E0h]
  __int64 v36; // [rsp+240h] [rbp-7D8h]
  WCHAR *v37; // [rsp+248h] [rbp-7D0h]
  __int64 v38; // [rsp+250h] [rbp-7C8h]
  int v39; // [rsp+258h] [rbp-7C0h]
  int *v40; // [rsp+260h] [rbp-7B8h]
  char v41; // [rsp+268h] [rbp-7B0h]
  WCHAR Destination[560]; // [rsp+580h] [rbp-498h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A18h] [rbp+0h]

  v15 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl'::`2'::impl) )
  {
    v23 = 0;
    v24 = 0;
    v28 = 0;
    v25 = 0;
    v26 = "ProvOpsPublishDeviceProvisioningLogs";
    v27 = 0;
    v29 = 0;
    v31 = 0;
    memset_0(v30, 0, sizeof(v30));
    v32 = 1;
    v33 = 0;
    v34 = &v23;
    v35 = 0;
    v36 = 0;
    v37 = Dst;
    v38 = 0;
    v39 = 0;
    v40 = &v25;
    v41 = 0;
    *(_QWORD *)Dst = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::`vftable';
    Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *)Dst);
    v17[0] = this;
    v17[1] = &v15;
    v17[2] = Dst;
    v18 = 1;
    wcscpy(Source, L" -area ");
    wcscpy(v20, L" -cab ");
    memset_0(Destination, 0, 0x454u);
    if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\MdmDiagnosticsTool.exe", Destination, 0x22Au) )
    {
      try
      {
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x3B6,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          v8);
      }
      catch ( ... )
      {
        v12 = &v13;
        *((_DWORD *)v12 + 20) = wil::details::in1diag3::Return_CaughtException(
                                  (wil::details::in1diag3 *)v12[323],
                                  (void *)0x3CF,
                                  v10,
                                  v11);
        wil::details::ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___::_ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___(v17);
        *(_QWORD *)Dst = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::`vftable';
        wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(Dst);
        wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(Dst);
        goto LABEL_17;
      }
    }
    wcscat_s(Destination, 0x22Au, Source);
    wcscat_s(Destination, 0x22Au, L"DeviceProvisioning");
    wcscat_s(Destination, 0x22Au, v20);
    wcscat_s(Destination, 0x22Au, a2);
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, Destination, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      ExitCode = 0;
      GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
      LastError = ExitCode;
    }
    else
    {
      LastError = GetLastError();
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = LastError;
    wil::details::ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___::_ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___(v17);
    *(_QWORD *)Dst = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::`vftable';
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(Dst);
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(Dst);
    result = v15;
  }
  else
  {
    wcscpy(Source, L" -area ");
    wcscpy(v20, L" -cab ");
    memset_0(Dst, 0, 0x454u);
    if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\MdmDiagnosticsTool.exe", Dst, 0x22Au) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3E1,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        v4);
    wcscat_s(Dst, 0x22Au, Source);
    wcscat_s(Dst, 0x22Au, L"DeviceProvisioning");
    wcscat_s(Dst, 0x22Au, v20);
    wcscat_s(Dst, 0x22Au, a2);
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, Dst, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      ExitCode = 0;
      GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
      result = ExitCode;
      if ( (int)ExitCode > 0 )
        result = (unsigned __int16)ExitCode | 0x80070000;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
    }
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      ExitCode = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3FA, v5, v6);
LABEL_17:
      result = ExitCode;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800145a0  push    rbx
0x1800145a2  push    rsi
0x1800145a3  push    rdi
0x1800145a4  push    r14
0x1800145a6  sub     rsp, 9F8h
0x1800145ad  mov     rax, cs:__security_cookie
0x1800145b4  xor     rax, rsp
0x1800145b7  mov     [rsp+0A18h+var_38], rax
0x1800145bf  mov     rsi, rdx
0x1800145c2  mov     rdi, rcx
0x1800145c5  xor     r14d, r14d
0x1800145c8  mov     [rsp+0A18h+var_9C4], r14d
0x1800145cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::GetImpl(void)'::`2'::impl
0x1800145d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OOBEDiagnostigsCleanupFix>::__private_IsEnabled(void)
0x1800145d9  test    al, al
0x1800145db  jnz     loc_18001479E
0x1800145e1  movups  xmm0, xmmword ptr cs:aArea; " -area "
0x1800145e8  movdqu  xmmword ptr [rsp+0A18h+Source], xmm0
0x1800145f1  movsd   xmm1, qword ptr cs:aCab; " -cab "
0x1800145f9  movsd   qword ptr [rsp+0A18h+var_918], xmm1
0x180014602  mov     eax, dword ptr cs:aCab+8; "b "
0x180014608  mov     [rsp+0A18h+var_910], eax
0x18001460f  movzx   eax, word ptr cs:aCab+0Ch; ""
0x180014616  mov     [rsp+0A18h+var_90C], ax
0x18001461e  xor     edx, edx; Val
0x180014620  mov     r8d, 454h; Size
0x180014626  lea     rcx, [rsp+0A18h+Dst]; void *
0x18001462e  call    memset_0
0x180014633  mov     edi, 22Ah
0x180014638  mov     r8d, edi; nSize
0x18001463b  lea     rdx, [rsp+0A18h+Dst]; lpDst
0x180014643  lea     rcx, Src; "%windir%\\System32\\MdmDiagnosticsTool."...
0x18001464a  call    cs:__imp_ExpandEnvironmentStringsW
0x180014650  mov     rcx, [rsp+0A18h]; this
0x180014658  test    eax, eax
0x18001465a  jz      loc_180014ADF
0x180014660  lea     r8, [rsp+0A18h+Source]; Source
0x180014668  mov     rdx, rdi; SizeInWords
0x18001466b  lea     rcx, [rsp+0A18h+Dst]; Destination
0x180014673  call    cs:__imp_wcscat_s
0x180014679  lea     r8, aDeviceprovisio; "DeviceProvisioning"
0x180014680  mov     rdx, rdi; SizeInWords
0x180014683  lea     rcx, [rsp+0A18h+Dst]; Destination
0x18001468b  call    cs:__imp_wcscat_s
0x180014691  lea     r8, [rsp+0A18h+var_918]; Source
0x180014699  mov     rdx, rdi; SizeInWords
0x18001469c  lea     rcx, [rsp+0A18h+Dst]; Destination
0x1800146a4  call    cs:__imp_wcscat_s
0x1800146aa  mov     r8, rsi; Source
0x1800146ad  mov     rdx, rdi; SizeInWords
0x1800146b0  lea     rcx, [rsp+0A18h+Dst]; Destination
0x1800146b8  call    cs:__imp_wcscat_s
0x1800146be  mov     qword ptr [rsp+0A18h+StartupInfo.cb], 68h ; 'h'
0x1800146ca  xor     edx, edx; Val
0x1800146cc  lea     r8d, [rdx+60h]; Size
0x1800146d0  lea     rcx, [rsp+0A18h+StartupInfo.lpReserved]; void *
0x1800146d8  call    memset_0
0x1800146dd  xorps   xmm0, xmm0
0x1800146e0  xor     eax, eax
0x1800146e2  movups  xmmword ptr [rsp+0A18h+ProcessInformation.hProcess], xmm0
0x1800146e7  mov     qword ptr [rsp+0A18h+ProcessInformation.dwProcessId], rax
0x1800146ec  lea     rax, [rsp+0A18h+ProcessInformation]
0x1800146f1  mov     [rsp+0A18h+lpProcessInformation], rax; lpProcessInformation
0x1800146f6  lea     rax, [rsp+0A18h+StartupInfo]
0x1800146fe  mov     [rsp+0A18h+lpStartupInfo], rax; lpStartupInfo
0x180014703  mov     [rsp+0A18h+lpCurrentDirectory], r14; lpCurrentDirectory
0x180014708  mov     [rsp+0A18h+lpEnvironment], r14; lpEnvironment
0x18001470d  mov     [rsp+0A18h+dwCreationFlags], 8000000h; dwCreationFlags
0x180014715  mov     [rsp+0A18h+bInheritHandles], r14d; bInheritHandles
0x18001471a  xor     r9d, r9d; lpThreadAttributes
0x18001471d  xor     r8d, r8d; lpProcessAttributes
0x180014720  lea     rdx, [rsp+0A18h+Dst]; lpCommandLine
0x180014728  xor     ecx, ecx; lpApplicationName
0x18001472a  call    cs:__imp_CreateProcessW
0x180014730  test    eax, eax
0x180014732  jz      short loc_180014782
0x180014734  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014737  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hHandle
0x18001473c  call    cs:__imp_WaitForSingleObject
0x180014742  mov     [rsp+0A18h+ExitCode], r14d
0x180014747  lea     rdx, [rsp+0A18h+ExitCode]; lpExitCode
0x18001474c  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hProcess
0x180014751  call    cs:__imp_GetExitCodeProcess
0x180014757  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hObject
0x18001475c  call    cs:__imp_CloseHandle
0x180014762  mov     rcx, [rsp+0A18h+ProcessInformation.hThread]; hObject
0x180014767  call    cs:__imp_CloseHandle
0x18001476d  mov     eax, [rsp+0A18h+ExitCode]
0x180014771  test    eax, eax
0x180014773  jle     short loc_18001477D
0x180014775  movzx   eax, ax
0x180014778  or      eax, 80070000h
0x18001477d  jmp     loc_180014AC2
0x180014782  call    cs:__imp_GetLastError
0x180014788  test    eax, eax
0x18001478a  jle     short loc_180014794
0x18001478c  movzx   eax, ax
0x18001478f  or      eax, 80070000h
0x180014794  jmp     loc_180014AC2
0x180014799  jmp     loc_180014ABE
0x18001479e  mov     [rsp+0A18h+var_8F0], r14d
0x1800147a6  mov     [rsp+0A18h+var_8EC], r14b
0x1800147ae  mov     [rsp+0A18h+var_8B0], r14b
0x1800147b6  mov     [rsp+0A18h+var_8C8], r14d
0x1800147be  lea     rax, aProvopspublish; "ProvOpsPublishDeviceProvisioningLogs"
0x1800147c5  mov     [rsp+0A18h+var_8C0], rax
0x1800147cd  mov     [rsp+0A18h+var_8B8], r14
0x1800147d5  mov     [rsp+0A18h+var_8A8], r14d
0x1800147dd  xorps   xmm0, xmm0
0x1800147e0  movdqa  [rsp+0A18h+var_808], xmm0
0x1800147e9  xor     edx, edx; Val
0x1800147eb  mov     r8d, 98h; Size
0x1800147f1  lea     rcx, [rsp+0A18h+var_8A0]; void *
0x1800147f9  call    memset_0
0x1800147fe  mov     [rsp+0A18h+var_7F8], 1
0x180014809  xor     eax, eax
0x18001480b  mov     [rsp+0A18h+var_7F0], rax
0x180014813  lea     rax, [rsp+0A18h+var_8F0]
0x18001481b  mov     [rsp+0A18h+var_7E8], rax
0x180014823  mov     [rsp+0A18h+var_7E0], r14
0x18001482b  mov     [rsp+0A18h+var_7D8], r14
0x180014833  lea     rax, [rsp+0A18h+Dst]
0x18001483b  mov     [rsp+0A18h+var_7D0], rax
0x180014843  mov     [rsp+0A18h+var_7C8], r14
0x18001484b  mov     [rsp+0A18h+var_7C0], r14d
0x180014853  lea     rax, [rsp+0A18h+var_8C8]
0x18001485b  mov     [rsp+0A18h+var_7B8], rax
0x180014863  mov     [rsp+0A18h+var_7B0], r14b
0x18001486b  lea     rbx, ??_7ProvOpsPublishDeviceProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::`vftable'
0x180014872  mov     qword ptr [rsp+0A18h+Dst], rbx
0x18001487a  lea     rcx, [rsp+0A18h+Dst]; this
0x180014882  call    ?StartActivity@ProvOpsPublishDeviceProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StartActivity(void)
0x180014887  nop
0x180014888  mov     [rsp+0A18h+var_9A8], rdi
0x18001488d  lea     rax, [rsp+0A18h+var_9C4]
0x180014892  mov     [rsp+0A18h+var_9A0], rax
0x180014897  lea     rax, [rsp+0A18h+Dst]
0x18001489f  mov     [rsp+0A18h+var_998], rax
0x1800148a7  mov     [rsp+0A18h+var_990], 1
0x1800148af  movups  xmm0, xmmword ptr cs:aArea; " -area "
0x1800148b6  movdqu  xmmword ptr [rsp+0A18h+Source], xmm0
0x1800148bf  movsd   xmm1, qword ptr cs:aCab; " -cab "
0x1800148c7  movsd   qword ptr [rsp+0A18h+var_918], xmm1
0x1800148d0  mov     eax, dword ptr cs:aCab+8; "b "
0x1800148d6  mov     [rsp+0A18h+var_910], eax
0x1800148dd  movzx   eax, word ptr cs:aCab+0Ch; ""
0x1800148e4  mov     [rsp+0A18h+var_90C], ax
0x1800148ec  xor     edx, edx; Val
0x1800148ee  mov     r8d, 454h; Size
0x1800148f4  lea     rcx, [rsp+0A18h+Destination]; void *
0x1800148fc  call    memset_0
0x180014901  mov     edi, 22Ah
0x180014906  mov     r8d, edi; nSize
0x180014909  lea     rdx, [rsp+0A18h+Destination]; lpDst
0x180014911  lea     rcx, Src; "%windir%\\System32\\MdmDiagnosticsTool."...
0x180014918  call    cs:__imp_ExpandEnvironmentStringsW
0x18001491e  mov     rcx, [rsp+0A18h]; this
0x180014926  test    eax, eax
0x180014928  jz      loc_180014AF1
0x18001492e  lea     r8, [rsp+0A18h+Source]; Source
0x180014936  mov     rdx, rdi; SizeInWords
0x180014939  lea     rcx, [rsp+0A18h+Destination]; Destination
0x180014941  call    cs:__imp_wcscat_s
0x180014947  lea     r8, aDeviceprovisio; "DeviceProvisioning"
0x18001494e  mov     rdx, rdi; SizeInWords
0x180014951  lea     rcx, [rsp+0A18h+Destination]; Destination
0x180014959  call    cs:__imp_wcscat_s
0x18001495f  lea     r8, [rsp+0A18h+var_918]; Source
0x180014967  mov     rdx, rdi; SizeInWords
0x18001496a  lea     rcx, [rsp+0A18h+Destination]; Destination
0x180014972  call    cs:__imp_wcscat_s
0x180014978  mov     r8, rsi; Source
0x18001497b  mov     rdx, rdi; SizeInWords
0x18001497e  lea     rcx, [rsp+0A18h+Destination]; Destination
0x180014986  call    cs:__imp_wcscat_s
0x18001498c  mov     qword ptr [rsp+0A18h+StartupInfo.cb], 68h ; 'h'
0x180014998  xor     edx, edx; Val
0x18001499a  lea     r8d, [rdx+60h]; Size
0x18001499e  lea     rcx, [rsp+0A18h+StartupInfo.lpReserved]; void *
0x1800149a6  call    memset_0
0x1800149ab  xorps   xmm0, xmm0
0x1800149ae  xor     eax, eax
0x1800149b0  movups  xmmword ptr [rsp+0A18h+ProcessInformation.hProcess], xmm0
0x1800149b5  mov     qword ptr [rsp+0A18h+ProcessInformation.dwProcessId], rax
0x1800149ba  lea     rax, [rsp+0A18h+ProcessInformation]
0x1800149bf  mov     [rsp+0A18h+lpProcessInformation], rax; lpProcessInformation
0x1800149c4  lea     rax, [rsp+0A18h+StartupInfo]
0x1800149cc  mov     [rsp+0A18h+lpStartupInfo], rax; lpStartupInfo
0x1800149d1  mov     [rsp+0A18h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800149d6  mov     [rsp+0A18h+lpEnvironment], r14; lpEnvironment
0x1800149db  mov     [rsp+0A18h+dwCreationFlags], 8000000h; dwCreationFlags
0x1800149e3  mov     [rsp+0A18h+bInheritHandles], r14d; bInheritHandles
0x1800149e8  xor     r9d, r9d; lpThreadAttributes
0x1800149eb  xor     r8d, r8d; lpProcessAttributes
0x1800149ee  lea     rdx, [rsp+0A18h+Destination]; lpCommandLine
0x1800149f6  xor     ecx, ecx; lpApplicationName
0x1800149f8  call    cs:__imp_CreateProcessW
0x1800149fe  test    eax, eax
0x180014a00  jz      short loc_180014A41
0x180014a02  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014a05  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hHandle
0x180014a0a  call    cs:__imp_WaitForSingleObject
0x180014a10  mov     [rsp+0A18h+ExitCode], r14d
0x180014a15  lea     rdx, [rsp+0A18h+ExitCode]; lpExitCode
0x180014a1a  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hProcess
0x180014a1f  call    cs:__imp_GetExitCodeProcess
0x180014a25  mov     rcx, [rsp+0A18h+ProcessInformation.hProcess]; hObject
0x180014a2a  call    cs:__imp_CloseHandle
0x180014a30  mov     rcx, [rsp+0A18h+ProcessInformation.hThread]; hObject
0x180014a35  call    cs:__imp_CloseHandle
0x180014a3b  mov     eax, [rsp+0A18h+ExitCode]
0x180014a3f  jmp     short loc_180014A47
0x180014a41  call    cs:__imp_GetLastError
0x180014a47  test    eax, eax
0x180014a49  jle     short loc_180014A53
0x180014a4b  movzx   eax, ax
0x180014a4e  or      eax, 80070000h
0x180014a53  mov     [rsp+0A18h+var_9C4], eax
0x180014a57  lea     rcx, [rsp+0A18h+var_9A8]
0x180014a5c  call    wil__details__ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0______ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___
0x180014a61  nop
0x180014a62  mov     qword ptr [rsp+0A18h+Dst], rbx
0x180014a6a  lea     rcx, [rsp+0A18h+Dst]
0x180014a72  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014a77  lea     rcx, [rsp+0A18h+Dst]
0x180014a7f  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014a84  mov     eax, [rsp+0A18h+var_9C4]
0x180014a88  jmp     short loc_180014AC2
0x180014a8a  lea     rcx, [rsp+0A18h+var_9A8]
0x180014a8f  call    wil__details__ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0______ScopeExitFn__lambda_513c286dd4c0f516bdd44aeb5000e9b0___
0x180014a94  nop
0x180014a95  lea     rbx, ??_7ProvOpsPublishDeviceProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::`vftable'
0x180014a9c  mov     qword ptr [rsp+0A18h+Dst], rbx
0x180014aa4  lea     rcx, [rsp+0A18h+Dst]
0x180014aac  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014ab1  lea     rcx, [rsp+0A18h+Dst]
0x180014ab9  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014abe  mov     eax, [rsp+0A18h+ExitCode]
0x180014ac2  mov     rcx, [rsp+0A18h+var_38]
0x180014aca  xor     rcx, rsp; StackCookie
0x180014acd  call    __security_check_cookie
0x180014ad2  add     rsp, 9F8h
0x180014ad9  pop     r14
0x180014adb  pop     rdi
0x180014adc  pop     rsi
0x180014add  pop     rbx
0x180014ade  retn
0x180014adf  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180014ae6  mov     edx, 3E1h; void *
0x180014aeb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180014af1  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180014af8  mov     edx, 3B6h; void *
0x180014afd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
