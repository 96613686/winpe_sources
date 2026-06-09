# ProcessPackagedStartupTask(IUnknown *,Windows::ApplicationModel::Internal::IStartupTaskInternal *)

- ea: `0x140067014`
- end: `0x140067308`
- name: `?ProcessPackagedStartupTask@@YAJPEAUIUnknown@@PEAUIStartupTaskInternal@Internal@ApplicationModel@Windows@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(IUnknown *punk, struct Windows::ApplicationModel::Internal::IStartupTaskInternal *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140066d38`

## callees

- `0x14000c870`
- `0x14000d750`
- `0x14000d7e0`
- `0x140067014`
- `0x1400954e0`
- `0x1401040e0`
- `0x140104cbc`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400672cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400672cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400672fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400672fc`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x140067221`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x140067221`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140067203`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140067203`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400670bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400670bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400670b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400670b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006704b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140067086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140067296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006704b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140067086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140067296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400670f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400670f3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006711d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006711d`

## string_xrefs

- `0x1400670ec`: `Windows.ApplicationModel.Internal.StartupTaskActivator`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProcessPackagedStartupTask(
        IUnknown *punk,
        struct Windows::ApplicationModel::Internal::IStartupTaskInternal *a2)
{
  __int64 (__fastcall *v4)(struct Windows::ApplicationModel::Internal::IStartupTaskInternal *, HSTRING *); // rbx
  int v5; // eax
  int v6; // ebx
  const WCHAR *StringRawBuffer; // rax
  LPWSTR FileNameW; // rax
  __int64 v10; // rcx
  LPWSTR v11; // rdi
  HRESULT v12; // eax
  HSTRING v13; // rbx
  void *v14; // rcx
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  char *v18; // rbx
  void *v19; // rcx
  DWORD dwProcessId; // [rsp+20h] [rbp-50h] BYREF
  void *v21; // [rsp+28h] [rbp-48h] BYREF
  void *ppvOut; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Internal::IStartupTaskInternal *, HSTRING *))(*(_QWORD *)a2 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"shell\\lib\\runonce\\runonce.cpp",
      (const char *)(unsigned int)v5,
      dwProcessId);
LABEL_3:
    WindowsDeleteString(string);
    return (unsigned int)v6;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  FileNameW = PathFindFileNameW(StringRawBuffer);
  v11 = FileNameW;
  if ( byte_140253B84 < 0 )
    McTemplateU0z_EventWriteTransfer(v10, &ShellTraceId_Explorer_ExecutingPackagedStartupApp_Start, FileNameW);
  dwProcessId = 0;
  v21 = 0;
  v25 = 0;
  v12 = WindowsCreateStringReference(
          L"Windows.ApplicationModel.Internal.StartupTaskActivator",
          0x36u,
          &hstringHeader,
          &v25);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  v13 = v25;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v21);
  v21 = 0;
  ppvOut = 0;
  v6 = RoActivateInstance(v13, &ppvOut);
  if ( v6 < 0 )
    goto LABEL_8;
  v15 = memcmp_0(&GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v16 = ppvOut;
  if ( v15 )
  {
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppvOut)(
           ppvOut,
           &GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218,
           &v21);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( v6 < 0 )
    {
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"shell\\lib\\runonce\\runonce.cpp",
        (const char *)(unsigned int)v6,
        dwProcessId);
      v14 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      goto LABEL_10;
    }
    v16 = v21;
  }
  else
  {
    v21 = ppvOut;
  }
  v17 = (*(__int64 (__fastcall **)(void *, struct Windows::ApplicationModel::Internal::IStartupTaskInternal *, DWORD *))(*(_QWORD *)v16 + 48LL))(
          v16,
          a2,
          &dwProcessId);
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"shell\\lib\\runonce\\runonce.cpp",
      (const char *)(unsigned int)v17,
      dwProcessId);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v21);
LABEL_10:
    if ( byte_140253B84 < 0 )
      McTemplateU0qz_EventWriteTransfer(v14, &ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop, dwProcessId, v11);
    goto LABEL_3;
  }
  v18 = (char *)OpenProcess(0x400u, 1, dwProcessId);
  ppvOut = 0;
  if ( IUnknown_QueryService(
         punk,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &ppvOut) >= 0 )
  {
    (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v18);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v18);
  v19 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( byte_140253B84 < 0 )
    McTemplateU0qz_EventWriteTransfer(v19, &ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop, dwProcessId, v11);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x140067014  mov     [rsp-28h+arg_10], rbx
0x140067019  push    rbp
0x14006701a  push    rsi
0x14006701b  push    rdi
0x14006701c  push    r14
0x14006701e  push    r15
0x140067020  mov     rbp, rsp
0x140067023  sub     rsp, 70h
0x140067027  mov     rax, cs:__security_cookie
0x14006702e  xor     rax, rsp
0x140067031  mov     [rbp+var_10], rax
0x140067035  mov     rsi, rdx
0x140067038  mov     r14, rcx
0x14006703b  xor     r15d, r15d
0x14006703e  mov     [rbp+string], r15
0x140067042  mov     rax, [rdx]
0x140067045  mov     rbx, [rax+60h]
0x140067049  xor     ecx, ecx; string
0x14006704b  call    cs:__imp_WindowsDeleteString
0x140067051  mov     [rbp+string], r15
0x140067055  lea     rdx, [rbp+string]
0x140067059  mov     rcx, rsi
0x14006705c  mov     rax, rbx
0x14006705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067064  mov     ebx, eax
0x140067066  test    eax, eax
0x140067068  jns     short loc_1400670AE
0x14006706a  mov     rcx, [rbp+28h]; this
0x14006706e  mov     r9d, eax; char *
0x140067071  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x140067078  mov     edx, 21Eh; void *
0x14006707d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067082  mov     rcx, [rbp+string]; string
0x140067086  call    cs:__imp_WindowsDeleteString
0x14006708c  mov     eax, ebx
0x14006708e  mov     rcx, [rbp+var_10]
0x140067092  xor     rcx, rsp; StackCookie
0x140067095  call    __security_check_cookie
0x14006709a  mov     rbx, [rsp+70h+arg_10]
0x1400670a2  add     rsp, 70h
0x1400670a6  pop     r15
0x1400670a8  pop     r14
0x1400670aa  pop     rdi
0x1400670ab  pop     rsi
0x1400670ac  pop     rbp
0x1400670ad  retn
0x1400670ae  xor     edx, edx; length
0x1400670b0  mov     rcx, [rbp+string]; string
0x1400670b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1400670ba  mov     rcx, rax; pszPath
0x1400670bd  call    cs:__imp_PathFindFileNameW
0x1400670c3  mov     rdi, rax
0x1400670c6  cmp     cs:byte_140253B84, r15b
0x1400670cd  jl      loc_1400672AC
0x1400670d3  mov     [rbp+dwProcessId], r15d
0x1400670d7  mov     [rbp+var_48], r15
0x1400670db  mov     [rbp+var_18], r15
0x1400670df  lea     r9, [rbp+var_18]; string
0x1400670e3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400670e7  mov     edx, 36h ; '6'; length
0x1400670ec  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Internal_StartupTaskActivator@@3QBGB; "Windows.ApplicationModel.Internal.Start"...
0x1400670f3  call    cs:__imp_WindowsCreateStringReference
0x1400670f9  test    eax, eax
0x1400670fb  js      loc_1400672C0
0x140067101  mov     rbx, [rbp+var_18]
0x140067105  lea     rcx, [rbp+var_48]
0x140067109  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x14006710e  mov     [rbp+var_48], r15
0x140067112  mov     [rbp+ppvOut], r15
0x140067116  lea     rdx, [rbp+ppvOut]
0x14006711a  mov     rcx, rbx
0x14006711d  call    cs:__imp_RoActivateInstance
0x140067123  mov     ebx, eax
0x140067125  test    eax, eax
0x140067127  jns     short loc_14006717F
0x140067129  mov     rcx, [rbp+28h]; this
0x14006712d  mov     r9d, ebx; char *
0x140067130  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x140067137  mov     edx, 22Bh; void *
0x14006713c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067141  mov     rcx, [rbp+var_48]
0x140067145  test    rcx, rcx
0x140067148  jz      short loc_14006715A
0x14006714a  mov     [rbp+var_48], r15
0x14006714e  mov     rax, [rcx]
0x140067151  mov     rax, [rax+10h]
0x140067155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006715a  cmp     cs:byte_140253B84, r15b
0x140067161  jge     loc_140067082
0x140067167  mov     r9, rdi
0x14006716a  mov     r8d, [rbp+dwProcessId]
0x14006716e  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop
0x140067175  call    McTemplateU0qz_EventWriteTransfer
0x14006717a  jmp     loc_140067082
0x14006717f  mov     r8d, 10h; Size
0x140067185  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14006718c  lea     rcx, _GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218; Buf1
0x140067193  call    memcmp_0
0x140067198  mov     rcx, [rbp+ppvOut]
0x14006719c  test    eax, eax
0x14006719e  jz      loc_1400672A3
0x1400671a4  mov     rax, [rcx]
0x1400671a7  lea     r8, [rbp+var_48]
0x1400671ab  lea     rdx, _GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218
0x1400671b2  mov     rax, [rax]
0x1400671b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400671ba  mov     ebx, eax
0x1400671bc  mov     rcx, [rbp+ppvOut]
0x1400671c0  mov     rax, [rcx]
0x1400671c3  mov     rax, [rax+10h]
0x1400671c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400671cc  test    ebx, ebx
0x1400671ce  js      loc_140067129
0x1400671d4  mov     rcx, [rbp+var_48]
0x1400671d8  mov     rax, [rcx]
0x1400671db  lea     r8, [rbp+dwProcessId]
0x1400671df  mov     rdx, rsi
0x1400671e2  mov     rax, [rax+30h]
0x1400671e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400671eb  mov     ebx, eax
0x1400671ed  test    eax, eax
0x1400671ef  js      loc_1400672D3
0x1400671f5  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1400671f9  mov     edx, 1; bInheritHandle
0x1400671fe  mov     ecx, 400h; dwDesiredAccess
0x140067203  call    cs:__imp_OpenProcess
0x140067209  mov     rbx, rax
0x14006720c  mov     [rbp+ppvOut], r15
0x140067210  lea     r9, [rbp+ppvOut]; ppvOut
0x140067214  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x14006721b  mov     r8, rdx; riid
0x14006721e  mov     rcx, r14; punk
0x140067221  call    cs:__imp_IUnknown_QueryService
0x140067227  test    eax, eax
0x140067229  js      short loc_14006724F
0x14006722b  mov     rcx, [rbp+ppvOut]
0x14006722f  mov     rax, [rcx]
0x140067232  mov     rdx, rbx
0x140067235  mov     rax, [rax+30h]
0x140067239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006723e  mov     rcx, [rbp+ppvOut]
0x140067242  mov     rax, [rcx]
0x140067245  mov     rax, [rax+10h]
0x140067249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006724e  nop
0x14006724f  lea     rax, [rbx-1]
0x140067253  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140067257  jbe     loc_1400672F9
0x14006725d  mov     rcx, [rbp+var_48]
0x140067261  test    rcx, rcx
0x140067264  jz      short loc_140067276
0x140067266  mov     [rbp+var_48], r15
0x14006726a  mov     rax, [rcx]
0x14006726d  mov     rax, [rax+10h]
0x140067271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067276  cmp     cs:byte_140253B84, r15b
0x14006727d  jge     short loc_140067292
0x14006727f  mov     r9, rdi
0x140067282  mov     r8d, [rbp+dwProcessId]
0x140067286  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop
0x14006728d  call    McTemplateU0qz_EventWriteTransfer
0x140067292  mov     rcx, [rbp+string]; string
0x140067296  call    cs:__imp_WindowsDeleteString
0x14006729c  xor     eax, eax
0x14006729e  jmp     loc_14006708E
0x1400672a3  mov     [rbp+var_48], rcx
0x1400672a7  jmp     loc_1400671D8
0x1400672ac  mov     r8, rdi
0x1400672af  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Start
0x1400672b6  call    McTemplateU0z_EventWriteTransfer
0x1400672bb  jmp     loc_1400670D3
0x1400672c0  xor     r9d, r9d; lpArguments
0x1400672c3  xor     r8d, r8d; nNumberOfArguments
0x1400672c6  lea     edx, [r9+1]; dwExceptionFlags
0x1400672ca  mov     ecx, eax; dwExceptionCode
0x1400672cc  call    cs:__imp_RaiseException
0x1400672d2  int     3; Trap to Debugger
0x1400672d3  mov     rcx, [rbp+28h]; this
0x1400672d7  mov     r9d, eax; char *
0x1400672da  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x1400672e1  mov     edx, 22Dh; void *
0x1400672e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400672eb  lea     rcx, [rbp+var_48]
0x1400672ef  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1400672f4  jmp     loc_14006715A
0x1400672f9  mov     rcx, rbx; hObject
0x1400672fc  call    cs:__imp_CloseHandle
0x140067302  jmp     loc_14006725D
```
