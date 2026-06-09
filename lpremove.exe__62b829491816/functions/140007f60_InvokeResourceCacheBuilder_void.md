# InvokeResourceCacheBuilder(void)

- ea: `0x140007f60`
- end: `0x140008093`
- name: `?InvokeResourceCacheBuilder@@YAKXZ`
- size: `307`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d8b8`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x140007f60`
- `0x14000bc1c`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x140008045`
- `KERNEL32!CreateProcessW` at `0x140008045`
- `KERNEL32!CloseHandle` at `0x140008054`
- `KERNEL32!CloseHandle` at `0x14000805f`
- `KERNEL32!CloseHandle` at `0x140008054`
- `KERNEL32!CloseHandle` at `0x14000805f`
- `KERNEL32!GetLastError` at `0x140008069`
- `KERNEL32!GetLastError` at `0x140008069`
- `api-ms-win-crt-private-l1-1-0!_o__wgetenv_s` at `0x140007faa`
- `api-ms-win-crt-private-l1-1-0!_o__wgetenv_s` at `0x140007faa`

## string_xrefs

- `0x140007fb8`: `\system32\mcbuilder.exe`

## pseudocode

```c
__int64 InvokeResourceCacheBuilder(void)
{
  unsigned int v0; // ebx
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rdx
  __int64 v4; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = 0;
  v0 = 50;
  if ( !(unsigned int)_o__wgetenv_s(&v4, CommandLine, 260, L"systemroot")
    && (int)StringCchCatW(CommandLine, v1, L"\\system32\\mcbuilder.exe") >= 0 )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( (int)StringCchCatW(CommandLine, v2, L" -s") >= 0 )
    {
      if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0x8000040u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
        return 0;
      }
      else
      {
        return GetLastError();
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140007f60  mov     [rsp-8+arg_0], rbx
0x140007f65  push    rbp
0x140007f66  lea     rbp, [rsp-200h]
0x140007f6e  sub     rsp, 300h
0x140007f75  mov     rax, cs:__security_cookie
0x140007f7c  xor     rax, rsp
0x140007f7f  mov     [rbp+200h+var_10], rax
0x140007f86  lea     r9, aSystemroot; "systemroot"
0x140007f8d  mov     [rsp+300h+var_2B0], 0
0x140007f96  mov     r8d, 104h
0x140007f9c  lea     rdx, [rbp+200h+CommandLine]
0x140007fa0  lea     rcx, [rsp+300h+var_2B0]
0x140007fa5  mov     ebx, 32h ; '2'
0x140007faa  call    cs:__imp__o__wgetenv_s
0x140007fb0  test    eax, eax
0x140007fb2  jnz     loc_140008071
0x140007fb8  lea     r8, aSystem32Mcbuil; "\\system32\\mcbuilder.exe"
0x140007fbf  lea     rcx, [rbp+200h+CommandLine]; unsigned __int16 *
0x140007fc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007fc8  test    eax, eax
0x140007fca  js      loc_140008071
0x140007fd0  xor     edx, edx; Val
0x140007fd2  lea     r8d, [rbx+36h]; Size
0x140007fd6  lea     rcx, [rsp+300h+StartupInfo]; void *
0x140007fdb  call    memset_0
0x140007fe0  xor     eax, eax
0x140007fe2  lea     r8, aS; " -s"
0x140007fe9  xorps   xmm0, xmm0
0x140007fec  mov     qword ptr [rsp+300h+ProcessInformation.dwProcessId], rax
0x140007ff1  lea     rcx, [rbp+200h+CommandLine]; unsigned __int16 *
0x140007ff5  movups  xmmword ptr [rsp+300h+ProcessInformation.hProcess], xmm0
0x140007ffa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007fff  test    eax, eax
0x140008001  js      short loc_140008071
0x140008003  lea     rax, [rsp+300h+ProcessInformation]
0x140008008  xor     r9d, r9d; lpThreadAttributes
0x14000800b  mov     [rsp+300h+lpProcessInformation], rax; lpProcessInformation
0x140008010  lea     rdx, [rbp+200h+CommandLine]; lpCommandLine
0x140008014  lea     rax, [rsp+300h+StartupInfo]
0x140008019  xor     r8d, r8d; lpProcessAttributes
0x14000801c  mov     [rsp+300h+lpStartupInfo], rax; lpStartupInfo
0x140008021  xor     ecx, ecx; lpApplicationName
0x140008023  mov     [rsp+300h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14000802c  mov     [rsp+300h+lpEnvironment], 0; lpEnvironment
0x140008035  mov     [rsp+300h+dwCreationFlags], 8000040h; dwCreationFlags
0x14000803d  mov     [rsp+300h+bInheritHandles], 0; bInheritHandles
0x140008045  call    cs:__imp_CreateProcessW
0x14000804b  test    eax, eax
0x14000804d  jz      short loc_140008069
0x14000804f  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hObject
0x140008054  call    cs:__imp_CloseHandle
0x14000805a  mov     rcx, [rsp+300h+ProcessInformation.hThread]; hObject
0x14000805f  call    cs:__imp_CloseHandle
0x140008065  xor     ebx, ebx
0x140008067  jmp     short loc_140008071
0x140008069  call    cs:__imp_GetLastError
0x14000806f  mov     ebx, eax
0x140008071  mov     eax, ebx
0x140008073  mov     rcx, [rbp+200h+var_10]
0x14000807a  xor     rcx, rsp; StackCookie
0x14000807d  call    __security_check_cookie
0x140008082  mov     rbx, [rsp+300h+arg_0]
0x14000808a  add     rsp, 300h
0x140008091  pop     rbp
0x140008092  retn
```
