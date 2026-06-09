# Microsoft::Windows::MDM::OmadmClient::ScheduleDeviceEnroller

- ea: `0x140053e74`
- end: `0x140053f91`
- name: `Microsoft::Windows::MDM::OmadmClient::ScheduleDeviceEnroller`
- size: `285`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140052300`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x1400525f8`
- `0x140053e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053f50`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140053ebc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140053ebc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140053f44`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140053f44`

## string_xrefs

- `0x140053eb5`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::ScheduleDeviceEnroller(LPWSTR lpCommandLine)
{
  signed int LastError; // eax
  struct _PROCESS_INFORMATION *v4; // rdx
  unsigned int v5; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-2B8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-298h] BYREF
  WCHAR Dst[264]; // [rsp+E0h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
    return 2147500037LL;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  CreateProcessW(Dst, lpCommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v4);
  return v5;
}

```

## disassembly

```asm
0x140053e74  push    rbx
0x140053e76  sub     rsp, 300h
0x140053e7d  mov     rax, cs:__security_cookie
0x140053e84  xor     rax, rsp
0x140053e87  mov     [rsp+308h+var_18], rax
0x140053e8f  mov     rbx, rcx
0x140053e92  xor     edx, edx; Val
0x140053e94  lea     rcx, [rsp+308h+Dst]; void *
0x140053e9c  mov     r8d, 208h; Size
0x140053ea2  call    memset_0
0x140053ea7  mov     r8d, 104h; nSize
0x140053ead  lea     rdx, [rsp+308h+Dst]; lpDst
0x140053eb5  lea     rcx, aWindirSystem32; "%windir%\\system32\\deviceenroller.exe"
0x140053ebc  call    cs:__imp_ExpandEnvironmentStringsW
0x140053ec3  nop     dword ptr [rax+rax+00h]
0x140053ec8  test    eax, eax
0x140053eca  jnz     short loc_140053ED6
0x140053ecc  mov     eax, 80004005h
0x140053ed1  jmp     loc_140053F77
0x140053ed6  xor     eax, eax
0x140053ed8  lea     rcx, [rsp+308h+StartupInfo+4]; void *
0x140053edd  xorps   xmm0, xmm0
0x140053ee0  mov     qword ptr [rsp+308h+ProcessInformation.dwProcessId], rax
0x140053ee5  xor     edx, edx; Val
0x140053ee7  movups  xmmword ptr [rsp+308h+ProcessInformation.hProcess], xmm0
0x140053eec  lea     r8d, [rax+64h]; Size
0x140053ef0  call    memset_0
0x140053ef5  lea     rax, [rsp+308h+ProcessInformation]
0x140053efa  mov     [rsp+308h+StartupInfo.cb], 68h ; 'h'
0x140053f02  mov     [rsp+308h+lpProcessInformation], rax; lpProcessInformation
0x140053f07  lea     rcx, [rsp+308h+Dst]; lpApplicationName
0x140053f0f  lea     rax, [rsp+308h+StartupInfo]
0x140053f14  xor     r9d, r9d; lpThreadAttributes
0x140053f17  mov     [rsp+308h+lpStartupInfo], rax; lpStartupInfo
0x140053f1c  xor     r8d, r8d; lpProcessAttributes
0x140053f1f  mov     [rsp+308h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140053f28  mov     rdx, rbx; lpCommandLine
0x140053f2b  mov     [rsp+308h+lpEnvironment], 0; lpEnvironment
0x140053f34  mov     [rsp+308h+dwCreationFlags], 8000000h; dwCreationFlags
0x140053f3c  mov     [rsp+308h+bInheritHandles], 0; bInheritHandles
0x140053f44  call    cs:__imp_CreateProcessW
0x140053f4b  nop     dword ptr [rax+rax+00h]
0x140053f50  call    cs:__imp_GetLastError
0x140053f57  nop     dword ptr [rax+rax+00h]
0x140053f5c  mov     ebx, eax
0x140053f5e  test    eax, eax
0x140053f60  jle     short loc_140053F6B
0x140053f62  movzx   ebx, ax
0x140053f65  or      ebx, 80070000h
0x140053f6b  lea     rcx, [rsp+308h+ProcessInformation]; this
0x140053f70  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x140053f75  mov     eax, ebx
0x140053f77  mov     rcx, [rsp+308h+var_18]
0x140053f7f  xor     rcx, rsp; StackCookie
0x140053f82  call    __security_check_cookie
0x140053f87  add     rsp, 300h
0x140053f8e  pop     rbx
0x140053f8f  retn
```
