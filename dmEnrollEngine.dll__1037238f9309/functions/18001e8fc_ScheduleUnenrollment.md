# ScheduleUnenrollment

- ea: `0x18001e8fc`
- end: `0x18001ea7f`
- name: `ScheduleUnenrollment`
- size: `387`
- prototype: `int __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a390`

## callees

- `0x180007040`
- `0x18001e8fc`
- `0x18001ea88`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180032f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ea34`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001ea34`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e965`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e965`

## string_xrefs

- `0x18001e95e`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
int __fastcall ScheduleUnenrollment(unsigned __int16 *a1)
{
  int result; // eax
  signed int LastError; // eax
  struct _PROCESS_INFORMATION *v4; // rdx
  unsigned int v5; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Dst[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
    return -2147467259;
  result = StringCchCopyW(CommandLine, 0x104u, L"/C /n /d \"");
  if ( result >= 0 )
  {
    result = StringCchCatW(CommandLine, 0x104u, a1);
    if ( result >= 0 )
    {
      result = StringCchCatW(CommandLine, 0x104u, L"\"");
      if ( result >= 0 )
      {
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        CreateProcessW(Dst, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v4);
        return v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e8fc  mov     [rsp-8+arg_8], rbx
0x18001e901  mov     [rsp-8+arg_10], rsi
0x18001e906  push    rbp
0x18001e907  lea     rbp, [rsp-410h]
0x18001e90f  sub     rsp, 510h
0x18001e916  mov     rax, cs:__security_cookie
0x18001e91d  xor     rax, rsp
0x18001e920  mov     [rbp+410h+var_10], rax
0x18001e927  mov     rbx, rcx
0x18001e92a  xor     edx, edx; Val
0x18001e92c  lea     rcx, [rbp+410h+Dst]; void *
0x18001e933  mov     r8d, 208h; Size
0x18001e939  call    memset_0
0x18001e93e  xor     edx, edx; Val
0x18001e940  lea     rcx, [rbp+410h+CommandLine]; void *
0x18001e944  mov     r8d, 208h; Size
0x18001e94a  call    memset_0
0x18001e94f  mov     esi, 104h
0x18001e954  lea     rdx, [rbp+410h+Dst]; lpDst
0x18001e95b  mov     r8d, esi; nSize
0x18001e95e  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x18001e965  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e96b  test    eax, eax
0x18001e96d  jnz     short loc_18001E979
0x18001e96f  mov     eax, 80004005h
0x18001e974  jmp     loc_18001EA5B
0x18001e979  lea     r8, aCND; "/C /n /d \""
0x18001e980  mov     rdx, rsi; unsigned __int64
0x18001e983  lea     rcx, [rbp+410h+CommandLine]; unsigned __int16 *
0x18001e987  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e98c  test    eax, eax
0x18001e98e  js      loc_18001EA5B
0x18001e994  mov     r8, rbx; unsigned __int16 *
0x18001e997  lea     rcx, [rbp+410h+CommandLine]; unsigned __int16 *
0x18001e99b  mov     rdx, rsi; unsigned __int64
0x18001e99e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e9a3  test    eax, eax
0x18001e9a5  js      loc_18001EA5B
0x18001e9ab  lea     r8, asc_180081EC8; "\""
0x18001e9b2  mov     rdx, rsi; unsigned __int64
0x18001e9b5  lea     rcx, [rbp+410h+CommandLine]; unsigned __int16 *
0x18001e9b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e9be  test    eax, eax
0x18001e9c0  js      loc_18001EA5B
0x18001e9c6  xor     eax, eax
0x18001e9c8  lea     rcx, [rsp+510h+StartupInfo+4]; void *
0x18001e9cd  xorps   xmm0, xmm0
0x18001e9d0  mov     qword ptr [rsp+510h+ProcessInformation.dwProcessId], rax
0x18001e9d5  xor     edx, edx; Val
0x18001e9d7  movups  xmmword ptr [rsp+510h+ProcessInformation.hProcess], xmm0
0x18001e9dc  lea     r8d, [rax+64h]; Size
0x18001e9e0  call    memset_0
0x18001e9e5  lea     rax, [rsp+510h+ProcessInformation]
0x18001e9ea  mov     [rsp+510h+StartupInfo.cb], 68h ; 'h'
0x18001e9f2  mov     [rsp+510h+lpProcessInformation], rax; lpProcessInformation
0x18001e9f7  lea     rdx, [rbp+410h+CommandLine]; lpCommandLine
0x18001e9fb  lea     rax, [rsp+510h+StartupInfo]
0x18001ea00  xor     r9d, r9d; lpThreadAttributes
0x18001ea03  mov     [rsp+510h+lpStartupInfo], rax; lpStartupInfo
0x18001ea08  lea     rcx, [rbp+410h+Dst]; lpApplicationName
0x18001ea0f  mov     [rsp+510h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001ea18  xor     r8d, r8d; lpProcessAttributes
0x18001ea1b  mov     [rsp+510h+lpEnvironment], 0; lpEnvironment
0x18001ea24  mov     [rsp+510h+dwCreationFlags], 8000000h; dwCreationFlags
0x18001ea2c  mov     [rsp+510h+bInheritHandles], 0; bInheritHandles
0x18001ea34  call    cs:__imp_CreateProcessW
0x18001ea3a  call    cs:__imp_GetLastError
0x18001ea40  mov     ebx, eax
0x18001ea42  test    eax, eax
0x18001ea44  jle     short loc_18001EA4F
0x18001ea46  movzx   ebx, ax
0x18001ea49  or      ebx, 80070000h
0x18001ea4f  lea     rcx, [rsp+510h+ProcessInformation]; this
0x18001ea54  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18001ea59  mov     eax, ebx
0x18001ea5b  mov     rcx, [rbp+410h+var_10]
0x18001ea62  xor     rcx, rsp; StackCookie
0x18001ea65  call    __security_check_cookie
0x18001ea6a  lea     r11, [rsp+510h+var_s0]
0x18001ea72  mov     rbx, [r11+18h]
0x18001ea76  mov     rsi, [r11+20h]
0x18001ea7a  mov     rsp, r11
0x18001ea7d  pop     rbp
0x18001ea7e  retn
```
