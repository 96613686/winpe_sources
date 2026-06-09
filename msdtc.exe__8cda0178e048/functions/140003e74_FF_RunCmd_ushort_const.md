# FF_RunCmd(ushort const *,...)

- ea: `0x140003e74`
- end: `0x140003fe6`
- name: `?FF_RunCmd@@YAJPEBGZZ`
- size: `370`
- prototype: `signed int(wchar_t *Format, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400037ac`

## callees

- `0x1400019cf`
- `0x140003e74`
- `0x140006f10`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140003ecc`
- `msvcrt!_vsnwprintf` at `0x140003ecc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140003f69`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140003f69`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140003f93`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140003f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003f7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa9`

## pseudocode

```c
signed int FF_RunCmd(wchar_t *Format, ...)
{
  unsigned int v1; // eax
  signed int result; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v4; // [rsp+70h] [rbp-98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+78h] [rbp-90h] BYREF
  wchar_t Buffer[519]; // [rsp+E8h] [rbp-20h] BYREF
  __int16 v7; // [rsp+4F6h] [rbp+3EEh]
  va_list Args; // [rsp+520h] [rbp+418h] BYREF

  va_start(Args, Format);
  Buffer[0] = 0;
  ProcessInformation.hProcess = 0;
  v7 = 0;
  v1 = _vsnwprintf(Buffer, 0x207u, Format, Args);
  if ( v1 >= 0x208 )
    return -2147024774;
  if ( v1 == 519 )
    v7 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.wShowWindow = 6;
  StartupInfo.dwFlags = 129;
  v4 = 0;
  *(_OWORD *)&ProcessInformation.hThread = 0;
  if ( CreateProcessW(0, Buffer, 0, 0, 0, 8u, 0, 0, &StartupInfo, (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
  {
    WaitForSingleObject(ProcessInformation.hThread, 0xFFFFFFFF);
    LODWORD(ProcessInformation.hProcess) = 0;
    GetExitCodeProcess(ProcessInformation.hThread, (LPDWORD)&ProcessInformation);
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(*(HANDLE *)&ProcessInformation.dwProcessId);
    result = (signed int)ProcessInformation.hProcess;
  }
  else
  {
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140003e74  mov     rax, rsp
0x140003e77  mov     [rax+8], rcx
0x140003e7b  mov     [rax+10h], rdx
0x140003e7f  mov     [rax+18h], r8
0x140003e83  mov     [rax+20h], r9
0x140003e87  push    rbp
0x140003e88  lea     rbp, [rax-408h]
0x140003e8f  sub     rsp, 500h
0x140003e96  mov     rax, cs:__security_cookie
0x140003e9d  xor     rax, rsp
0x140003ea0  mov     [rbp+400h+var_10], rax
0x140003ea7  xor     eax, eax
0x140003ea9  lea     r9, [rbp+400h+Args]; Args
0x140003eb0  mov     r8, rcx; Format
0x140003eb3  mov     [rbp+400h+Buffer], ax
0x140003eb7  lea     rcx, [rbp+400h+Buffer]; Buffer
0x140003ebb  mov     [rsp+500h+ProcessInformation.hProcess], rax
0x140003ec0  mov     edx, 207h; BufferCount
0x140003ec5  mov     [rbp+400h+var_12], ax
0x140003ecc  call    cs:__imp__vsnwprintf
0x140003ed2  test    eax, eax
0x140003ed4  js      loc_140003FC9
0x140003eda  cmp     eax, 207h
0x140003edf  ja      loc_140003FC9
0x140003ee5  jnz     short loc_140003EF0
0x140003ee7  xor     eax, eax
0x140003ee9  mov     [rbp+400h+var_12], ax
0x140003ef0  xor     edx, edx; Val
0x140003ef2  lea     rcx, [rsp+500h+StartupInfo]; void *
0x140003ef7  lea     r8d, [rdx+68h]; Size
0x140003efb  call    memset_0
0x140003f00  mov     eax, 6
0x140003f05  mov     [rsp+500h+StartupInfo.cb], 68h ; 'h'
0x140003f0d  mov     [rbp+400h+StartupInfo.wShowWindow], ax
0x140003f11  lea     rdx, [rbp+400h+Buffer]; lpCommandLine
0x140003f15  xor     eax, eax
0x140003f17  mov     [rbp+400h+StartupInfo.dwFlags], 81h
0x140003f1e  mov     [rsp+500h+var_498], rax
0x140003f23  xorps   xmm0, xmm0
0x140003f26  lea     rax, [rsp+500h+ProcessInformation.hThread]
0x140003f2b  xor     r9d, r9d; lpThreadAttributes
0x140003f2e  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x140003f33  xor     r8d, r8d; lpProcessAttributes
0x140003f36  lea     rax, [rsp+500h+StartupInfo]
0x140003f3b  xor     ecx, ecx; lpApplicationName
0x140003f3d  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x140003f42  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140003f4b  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x140003f54  mov     [rsp+500h+dwCreationFlags], 8; dwCreationFlags
0x140003f5c  mov     [rsp+500h+bInheritHandles], 0; bInheritHandles
0x140003f64  movups  xmmword ptr [rsp+500h+ProcessInformation.hThread], xmm0
0x140003f69  call    cs:__imp_CreateProcessW
0x140003f6f  test    eax, eax
0x140003f71  jz      short loc_140003FB5
0x140003f73  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hHandle
0x140003f78  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003f7b  call    cs:__imp_WaitForSingleObject
0x140003f81  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hProcess
0x140003f86  lea     rdx, [rsp+500h+ProcessInformation]; lpExitCode
0x140003f8b  mov     dword ptr [rsp+500h+ProcessInformation.hProcess], 0
0x140003f93  call    cs:__imp_GetExitCodeProcess
0x140003f99  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x140003f9e  call    cs:__imp_CloseHandle
0x140003fa4  mov     rcx, qword ptr [rsp+500h+ProcessInformation.dwProcessId]; hObject
0x140003fa9  call    cs:__imp_CloseHandle
0x140003faf  mov     eax, dword ptr [rsp+500h+ProcessInformation.hProcess]
0x140003fb3  jmp     short loc_140003FBB
0x140003fb5  call    cs:__imp_GetLastError
0x140003fbb  test    eax, eax
0x140003fbd  jle     short loc_140003FCE
0x140003fbf  movzx   eax, ax
0x140003fc2  or      eax, 80070000h
0x140003fc7  jmp     short loc_140003FCE
0x140003fc9  mov     eax, 8007007Ah
0x140003fce  mov     rcx, [rbp+400h+var_10]
0x140003fd5  xor     rcx, rsp; StackCookie
0x140003fd8  call    __security_check_cookie
0x140003fdd  add     rsp, 500h
0x140003fe4  pop     rbp
0x140003fe5  retn
```
