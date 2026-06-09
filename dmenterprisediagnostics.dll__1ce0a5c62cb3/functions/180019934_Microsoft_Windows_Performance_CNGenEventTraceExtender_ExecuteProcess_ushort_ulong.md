# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x180019934`
- end: `0x180019a2e`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `250`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001964c`

## callees

- `0x1800023c0`
- `0x180009994`
- `0x180019934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800199c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800199c9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800199dd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800199dd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800199b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800199b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a15`

## pseudocode

```c
int __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE hProcess; // rcx
  signed int Error; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF

  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, a2, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    return ATL::AtlHresultFromLastError();
  if ( !WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF)
    && (hProcess = ProcessInformation.hProcess, *a3 = 0, GetExitCodeProcess(hProcess, a3)) )
  {
    Error = *a3 != 0 ? 0x80004005 : 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error >= 0 )
      Error = -2147418113;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  return Error;
}

```

## disassembly

```asm
0x180019934  mov     [rsp+arg_0], rbx
0x180019939  push    rdi
0x18001993a  sub     rsp, 0E0h
0x180019941  mov     rbx, rdx
0x180019944  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18001994d  xor     edx, edx; Val
0x18001994f  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x180019954  mov     rdi, r8
0x180019957  lea     r8d, [rdx+60h]; Size
0x18001995b  call    memset_0
0x180019960  xor     eax, eax
0x180019962  xorps   xmm0, xmm0
0x180019965  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18001996a  xor     r9d, r9d; lpThreadAttributes
0x18001996d  lea     rax, [rsp+0E8h+ProcessInformation]
0x180019972  xor     r8d, r8d; lpProcessAttributes
0x180019975  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18001997a  mov     rdx, rbx; lpCommandLine
0x18001997d  lea     rax, [rsp+0E8h+StartupInfo]
0x180019982  xor     ecx, ecx; lpApplicationName
0x180019984  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x180019989  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180019992  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18001999b  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x1800199a3  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x1800199ab  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x1800199b0  call    cs:__imp_CreateProcessW
0x1800199b6  test    eax, eax
0x1800199b8  jnz     short loc_1800199C1
0x1800199ba  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800199bf  jmp     short loc_180019A1D
0x1800199c1  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x1800199c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800199c9  call    cs:__imp_WaitForSingleObject
0x1800199cf  test    eax, eax
0x1800199d1  jnz     short loc_1800199E7
0x1800199d3  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x1800199d8  mov     rdx, rdi; lpExitCode
0x1800199db  mov     [rdi], eax
0x1800199dd  call    cs:__imp_GetExitCodeProcess
0x1800199e3  test    eax, eax
0x1800199e5  jnz     short loc_1800199F9
0x1800199e7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800199ec  mov     ebx, eax
0x1800199ee  test    eax, eax
0x1800199f0  js      short loc_180019A05
0x1800199f2  mov     ebx, 8000FFFFh
0x1800199f7  jmp     short loc_180019A05
0x1800199f9  mov     eax, [rdi]
0x1800199fb  neg     eax
0x1800199fd  sbb     ebx, ebx
0x1800199ff  and     ebx, 80004005h
0x180019a05  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x180019a0a  call    cs:__imp_CloseHandle
0x180019a10  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x180019a15  call    cs:__imp_CloseHandle
0x180019a1b  mov     eax, ebx
0x180019a1d  mov     rbx, [rsp+0E8h+arg_0]
0x180019a25  add     rsp, 0E0h
0x180019a2c  pop     rdi
0x180019a2d  retn
```
