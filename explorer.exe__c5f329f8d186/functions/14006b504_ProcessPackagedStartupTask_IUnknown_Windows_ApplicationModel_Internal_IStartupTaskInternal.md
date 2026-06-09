# ProcessPackagedStartupTask(IUnknown *,Windows::ApplicationModel::Internal::IStartupTaskInternal *)

- ea: `0x14006b504`
- end: `0x14006b82a`
- name: `?ProcessPackagedStartupTask@@YAJPEAUIUnknown@@PEAUIStartupTaskInternal@Internal@ApplicationModel@Windows@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(IUnknown *punk, struct Windows::ApplicationModel::Internal::IStartupTaskInternal *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006b218`

## callees

- `0x140005d28`
- `0x14000b9e0`
- `0x14000ba70`
- `0x14006b504`
- `0x14009ac68`
- `0x1400baca0`
- `0x14010e160`
- `0x14010ed6c`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006b818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006b818`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14006b73c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14006b73c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006b718`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14006b718`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14006b5c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14006b5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006b5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006b5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b53b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b53b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006b7b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006b5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14006b5fc`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006b62c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14006b62c`

## string_xrefs

- `0x14006b5f5`: `Windows.ApplicationModel.Internal.StartupTaskActivator`

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
  int v13; // edx
  unsigned int v14; // r8d
  HSTRING v15; // rbx
  void *v16; // rcx
  int v17; // eax
  void *v18; // rcx
  int v19; // eax
  char *v20; // rbx
  void *v21; // rcx
  DWORD dwProcessId; // [rsp+20h] [rbp-50h] BYREF
  void *v23; // [rsp+28h] [rbp-48h] BYREF
  void *ppvOut; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-18h] BYREF
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
  if ( byte_14024FCC4 < 0 )
    McTemplateU0z_EventWriteTransfer(v10, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Start, FileNameW);
  dwProcessId = 0;
  v23 = 0;
  v27 = 0;
  v12 = WindowsCreateStringReference(
          L"Windows.ApplicationModel.Internal.StartupTaskActivator",
          0x36u,
          &hstringHeader,
          &v27);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  v15 = v27;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v23);
  v23 = 0;
  ppvOut = 0;
  v6 = RoActivateInstance(v15, &ppvOut);
  if ( v6 < 0 )
    goto LABEL_8;
  v17 = memcmp_0(&GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v18 = ppvOut;
  if ( v17 )
  {
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppvOut)(
           ppvOut,
           &GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218,
           &v23);
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
      v16 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_10;
    }
    v18 = v23;
  }
  else
  {
    v23 = ppvOut;
  }
  v19 = (*(__int64 (__fastcall **)(void *, struct Windows::ApplicationModel::Internal::IStartupTaskInternal *, DWORD *))(*(_QWORD *)v18 + 48LL))(
          v18,
          a2,
          &dwProcessId);
  v6 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"shell\\lib\\runonce\\runonce.cpp",
      (const char *)(unsigned int)v19,
      dwProcessId);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v23);
LABEL_10:
    if ( byte_14024FCC4 < 0 )
      McTemplateU0qz_EventWriteTransfer(v16, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop, dwProcessId, v11);
    goto LABEL_3;
  }
  v20 = (char *)OpenProcess(0x400u, 1, dwProcessId);
  ppvOut = 0;
  if ( IUnknown_QueryService(
         punk,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &ppvOut) >= 0 )
  {
    (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v20);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v20);
  v21 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( byte_14024FCC4 < 0 )
    McTemplateU0qz_EventWriteTransfer(v21, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop, dwProcessId, v11);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x14006b504  mov     [rsp-28h+arg_10], rbx
0x14006b509  push    rbp
0x14006b50a  push    rsi
0x14006b50b  push    rdi
0x14006b50c  push    r14
0x14006b50e  push    r15
0x14006b510  mov     rbp, rsp
0x14006b513  sub     rsp, 70h
0x14006b517  mov     rax, cs:__security_cookie
0x14006b51e  xor     rax, rsp
0x14006b521  mov     [rbp+var_10], rax
0x14006b525  mov     rsi, rdx
0x14006b528  mov     r14, rcx
0x14006b52b  xor     r15d, r15d
0x14006b52e  mov     [rbp+string], r15
0x14006b532  mov     rax, [rdx]
0x14006b535  mov     rbx, [rax+60h]
0x14006b539  xor     ecx, ecx; string
0x14006b53b  call    cs:__imp_WindowsDeleteString
0x14006b542  nop     dword ptr [rax+rax+00h]
0x14006b547  mov     [rbp+string], r15
0x14006b54b  lea     rdx, [rbp+string]
0x14006b54f  mov     rcx, rsi
0x14006b552  mov     rax, rbx
0x14006b555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b55a  mov     ebx, eax
0x14006b55c  test    eax, eax
0x14006b55e  jns     short loc_14006B5AB
0x14006b560  mov     rcx, [rbp+28h]; this
0x14006b564  mov     r9d, eax; char *
0x14006b567  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x14006b56e  mov     edx, 21Eh; void *
0x14006b573  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b578  mov     rcx, [rbp+string]; string
0x14006b57c  call    cs:__imp_WindowsDeleteString
0x14006b583  nop     dword ptr [rax+rax+00h]
0x14006b588  mov     eax, ebx
0x14006b58a  mov     rcx, [rbp+var_10]
0x14006b58e  xor     rcx, rsp; StackCookie
0x14006b591  call    __security_check_cookie
0x14006b596  mov     rbx, [rsp+70h+arg_10]
0x14006b59e  add     rsp, 70h
0x14006b5a2  pop     r15
0x14006b5a4  pop     r14
0x14006b5a6  pop     rdi
0x14006b5a7  pop     rsi
0x14006b5a8  pop     rbp
0x14006b5a9  retn
0x14006b5ab  xor     edx, edx; length
0x14006b5ad  mov     rcx, [rbp+string]; string
0x14006b5b1  call    cs:__imp_WindowsGetStringRawBuffer
0x14006b5b8  nop     dword ptr [rax+rax+00h]
0x14006b5bd  mov     rcx, rax; pszPath
0x14006b5c0  call    cs:__imp_PathFindFileNameW
0x14006b5c7  nop     dword ptr [rax+rax+00h]
0x14006b5cc  mov     rdi, rax
0x14006b5cf  cmp     cs:byte_14024FCC4, r15b
0x14006b5d6  jl      loc_14006B7D3
0x14006b5dc  mov     [rbp+dwProcessId], r15d
0x14006b5e0  mov     [rbp+var_48], r15
0x14006b5e4  mov     [rbp+var_18], r15
0x14006b5e8  lea     r9, [rbp+var_18]; string
0x14006b5ec  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14006b5f0  mov     edx, 36h ; '6'; length
0x14006b5f5  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Internal_StartupTaskActivator@@3QBGB; "Windows.ApplicationModel.Internal.Start"...
0x14006b5fc  call    cs:__imp_WindowsCreateStringReference
0x14006b603  nop     dword ptr [rax+rax+00h]
0x14006b608  test    eax, eax
0x14006b60a  js      loc_14006B7E7
0x14006b610  mov     rbx, [rbp+var_18]
0x14006b614  lea     rcx, [rbp+var_48]
0x14006b618  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x14006b61d  mov     [rbp+var_48], r15
0x14006b621  mov     [rbp+ppvOut], r15
0x14006b625  lea     rdx, [rbp+ppvOut]
0x14006b629  mov     rcx, rbx
0x14006b62c  call    cs:__imp_RoActivateInstance
0x14006b633  nop     dword ptr [rax+rax+00h]
0x14006b638  mov     ebx, eax
0x14006b63a  test    eax, eax
0x14006b63c  jns     short loc_14006B694
0x14006b63e  mov     rcx, [rbp+28h]; this
0x14006b642  mov     r9d, ebx; char *
0x14006b645  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x14006b64c  mov     edx, 22Bh; void *
0x14006b651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b656  mov     rcx, [rbp+var_48]
0x14006b65a  test    rcx, rcx
0x14006b65d  jz      short loc_14006B66F
0x14006b65f  mov     [rbp+var_48], r15
0x14006b663  mov     rax, [rcx]
0x14006b666  mov     rax, [rax+10h]
0x14006b66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b66f  cmp     cs:byte_14024FCC4, r15b
0x14006b676  jge     loc_14006B578
0x14006b67c  mov     r9, rdi
0x14006b67f  mov     r8d, [rbp+dwProcessId]
0x14006b683  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop
0x14006b68a  call    McTemplateU0qz_EventWriteTransfer
0x14006b68f  jmp     loc_14006B578
0x14006b694  mov     r8d, 10h; Size
0x14006b69a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14006b6a1  lea     rcx, _GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218; Buf1
0x14006b6a8  call    memcmp_0
0x14006b6ad  mov     rcx, [rbp+ppvOut]
0x14006b6b1  test    eax, eax
0x14006b6b3  jz      loc_14006B7CA
0x14006b6b9  mov     rax, [rcx]
0x14006b6bc  lea     r8, [rbp+var_48]
0x14006b6c0  lea     rdx, _GUID_104ba70f_4eed_4a8e_a5b5_cf4a5b86c218
0x14006b6c7  mov     rax, [rax]
0x14006b6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b6cf  mov     ebx, eax
0x14006b6d1  mov     rcx, [rbp+ppvOut]
0x14006b6d5  mov     rax, [rcx]
0x14006b6d8  mov     rax, [rax+10h]
0x14006b6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b6e1  test    ebx, ebx
0x14006b6e3  js      loc_14006B63E
0x14006b6e9  mov     rcx, [rbp+var_48]
0x14006b6ed  mov     rax, [rcx]
0x14006b6f0  lea     r8, [rbp+dwProcessId]
0x14006b6f4  mov     rdx, rsi
0x14006b6f7  mov     rax, [rax+30h]
0x14006b6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b700  mov     ebx, eax
0x14006b702  test    eax, eax
0x14006b704  js      loc_14006B7EF
0x14006b70a  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x14006b70e  mov     edx, 1; bInheritHandle
0x14006b713  mov     ecx, 400h; dwDesiredAccess
0x14006b718  call    cs:__imp_OpenProcess
0x14006b71f  nop     dword ptr [rax+rax+00h]
0x14006b724  mov     rbx, rax
0x14006b727  mov     [rbp+ppvOut], r15
0x14006b72b  lea     r9, [rbp+ppvOut]; ppvOut
0x14006b72f  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x14006b736  mov     r8, rdx; riid
0x14006b739  mov     rcx, r14; punk
0x14006b73c  call    cs:__imp_IUnknown_QueryService
0x14006b743  nop     dword ptr [rax+rax+00h]
0x14006b748  test    eax, eax
0x14006b74a  js      short loc_14006B770
0x14006b74c  mov     rcx, [rbp+ppvOut]
0x14006b750  mov     rax, [rcx]
0x14006b753  mov     rdx, rbx
0x14006b756  mov     rax, [rax+30h]
0x14006b75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b75f  mov     rcx, [rbp+ppvOut]
0x14006b763  mov     rax, [rcx]
0x14006b766  mov     rax, [rax+10h]
0x14006b76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b76f  nop
0x14006b770  lea     rax, [rbx-1]
0x14006b774  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006b778  jbe     loc_14006B815
0x14006b77e  mov     rcx, [rbp+var_48]
0x14006b782  test    rcx, rcx
0x14006b785  jz      short loc_14006B797
0x14006b787  mov     [rbp+var_48], r15
0x14006b78b  mov     rax, [rcx]
0x14006b78e  mov     rax, [rax+10h]
0x14006b792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b797  cmp     cs:byte_14024FCC4, r15b
0x14006b79e  jge     short loc_14006B7B3
0x14006b7a0  mov     r9, rdi
0x14006b7a3  mov     r8d, [rbp+dwProcessId]
0x14006b7a7  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Stop
0x14006b7ae  call    McTemplateU0qz_EventWriteTransfer
0x14006b7b3  mov     rcx, [rbp+string]; string
0x14006b7b7  call    cs:__imp_WindowsDeleteString
0x14006b7be  nop     dword ptr [rax+rax+00h]
0x14006b7c3  xor     eax, eax
0x14006b7c5  jmp     loc_14006B58A
0x14006b7ca  mov     [rbp+var_48], rcx
0x14006b7ce  jmp     loc_14006B6ED
0x14006b7d3  mov     r8, rdi
0x14006b7d6  lea     rdx, ShellTraceId_Explorer_ExecutingPackagedStartupApp_Start
0x14006b7dd  call    McTemplateU0z_EventWriteTransfer
0x14006b7e2  jmp     loc_14006B5DC
0x14006b7e7  mov     ecx, eax; this
0x14006b7e9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14006b7ee  int     3; Trap to Debugger
0x14006b7ef  mov     rcx, [rbp+28h]; this
0x14006b7f3  mov     r9d, eax; char *
0x14006b7f6  lea     r8, aShellLibRunonc; "shell\\lib\\runonce\\runonce.cpp"
0x14006b7fd  mov     edx, 22Dh; void *
0x14006b802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b807  lea     rcx, [rbp+var_48]
0x14006b80b  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x14006b810  jmp     loc_14006B66F
0x14006b815  mov     rcx, rbx; hObject
0x14006b818  call    cs:__imp_CloseHandle
0x14006b81f  nop     dword ptr [rax+rax+00h]
0x14006b824  jmp     loc_14006B77E
```
