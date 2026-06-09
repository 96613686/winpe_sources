# FF_RunCmd(ushort const *,...)

- ea: `0x18000f4dc`
- end: `0x18000f64e`
- name: `?FF_RunCmd@@YAJPEBGZZ`
- size: `370`
- prototype: `signed int(wchar_t *Format, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ee14`

## callees

- `0x18000f4dc`
- `0x18001280a`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f61d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f5e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000f5fb`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000f5fb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000f5d1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000f5d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f611`
- `msvcrt!_vsnwprintf` at `0x18000f534`
- `msvcrt!_vsnwprintf` at `0x18000f534`

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
0x18000f4dc  mov     rax, rsp
0x18000f4df  mov     [rax+8], rcx
0x18000f4e3  mov     [rax+10h], rdx
0x18000f4e7  mov     [rax+18h], r8
0x18000f4eb  mov     [rax+20h], r9
0x18000f4ef  push    rbp
0x18000f4f0  lea     rbp, [rax-408h]
0x18000f4f7  sub     rsp, 500h
0x18000f4fe  mov     rax, cs:__security_cookie
0x18000f505  xor     rax, rsp
0x18000f508  mov     [rbp+400h+var_10], rax
0x18000f50f  xor     eax, eax
0x18000f511  lea     r9, [rbp+400h+Args]; Args
0x18000f518  mov     r8, rcx; Format
0x18000f51b  mov     [rbp+400h+Buffer], ax
0x18000f51f  lea     rcx, [rbp+400h+Buffer]; Buffer
0x18000f523  mov     [rsp+500h+ProcessInformation.hProcess], rax
0x18000f528  mov     edx, 207h; BufferCount
0x18000f52d  mov     [rbp+400h+var_12], ax
0x18000f534  call    cs:__imp__vsnwprintf
0x18000f53a  test    eax, eax
0x18000f53c  js      loc_18000F631
0x18000f542  cmp     eax, 207h
0x18000f547  ja      loc_18000F631
0x18000f54d  jnz     short loc_18000F558
0x18000f54f  xor     eax, eax
0x18000f551  mov     [rbp+400h+var_12], ax
0x18000f558  xor     edx, edx; Val
0x18000f55a  lea     rcx, [rsp+500h+StartupInfo]; void *
0x18000f55f  lea     r8d, [rdx+68h]; Size
0x18000f563  call    memset_0
0x18000f568  mov     eax, 6
0x18000f56d  mov     [rsp+500h+StartupInfo.cb], 68h ; 'h'
0x18000f575  mov     [rbp+400h+StartupInfo.wShowWindow], ax
0x18000f579  lea     rdx, [rbp+400h+Buffer]; lpCommandLine
0x18000f57d  xor     eax, eax
0x18000f57f  mov     [rbp+400h+StartupInfo.dwFlags], 81h
0x18000f586  mov     [rsp+500h+var_498], rax
0x18000f58b  xorps   xmm0, xmm0
0x18000f58e  lea     rax, [rsp+500h+ProcessInformation.hThread]
0x18000f593  xor     r9d, r9d; lpThreadAttributes
0x18000f596  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x18000f59b  xor     r8d, r8d; lpProcessAttributes
0x18000f59e  lea     rax, [rsp+500h+StartupInfo]
0x18000f5a3  xor     ecx, ecx; lpApplicationName
0x18000f5a5  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x18000f5aa  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000f5b3  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x18000f5bc  mov     [rsp+500h+dwCreationFlags], 8; dwCreationFlags
0x18000f5c4  mov     [rsp+500h+bInheritHandles], 0; bInheritHandles
0x18000f5cc  movups  xmmword ptr [rsp+500h+ProcessInformation.hThread], xmm0
0x18000f5d1  call    cs:__imp_CreateProcessW
0x18000f5d7  test    eax, eax
0x18000f5d9  jz      short loc_18000F61D
0x18000f5db  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hHandle
0x18000f5e0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f5e3  call    cs:__imp_WaitForSingleObject
0x18000f5e9  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hProcess
0x18000f5ee  lea     rdx, [rsp+500h+ProcessInformation]; lpExitCode
0x18000f5f3  mov     dword ptr [rsp+500h+ProcessInformation.hProcess], 0
0x18000f5fb  call    cs:__imp_GetExitCodeProcess
0x18000f601  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x18000f606  call    cs:__imp_CloseHandle
0x18000f60c  mov     rcx, qword ptr [rsp+500h+ProcessInformation.dwProcessId]; hObject
0x18000f611  call    cs:__imp_CloseHandle
0x18000f617  mov     eax, dword ptr [rsp+500h+ProcessInformation.hProcess]
0x18000f61b  jmp     short loc_18000F623
0x18000f61d  call    cs:__imp_GetLastError
0x18000f623  test    eax, eax
0x18000f625  jle     short loc_18000F636
0x18000f627  movzx   eax, ax
0x18000f62a  or      eax, 80070000h
0x18000f62f  jmp     short loc_18000F636
0x18000f631  mov     eax, 8007007Ah
0x18000f636  mov     rcx, [rbp+400h+var_10]
0x18000f63d  xor     rcx, rsp; StackCookie
0x18000f640  call    __security_check_cookie
0x18000f645  add     rsp, 500h
0x18000f64c  pop     rbp
0x18000f64d  retn
```
