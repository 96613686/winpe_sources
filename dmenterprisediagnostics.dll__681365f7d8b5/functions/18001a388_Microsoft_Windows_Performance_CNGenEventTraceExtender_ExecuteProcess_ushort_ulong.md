# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x18001a388`
- end: `0x18001a4a1`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `281`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a090`

## callees

- `0x1800023e0`
- `0x180009e70`
- `0x18001a388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a423`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a423`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001a43d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001a43d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001a404`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001a404`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a481`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(
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
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a388  mov     [rsp+arg_0], rbx
0x18001a38d  push    rdi
0x18001a38e  sub     rsp, 0E0h
0x18001a395  mov     rbx, rdx
0x18001a398  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18001a3a1  xor     edx, edx; Val
0x18001a3a3  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x18001a3a8  mov     rdi, r8
0x18001a3ab  lea     r8d, [rdx+60h]; Size
0x18001a3af  call    memset_0
0x18001a3b4  xor     eax, eax
0x18001a3b6  xorps   xmm0, xmm0
0x18001a3b9  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18001a3be  xor     r9d, r9d; lpThreadAttributes
0x18001a3c1  lea     rax, [rsp+0E8h+ProcessInformation]
0x18001a3c6  xor     r8d, r8d; lpProcessAttributes
0x18001a3c9  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18001a3ce  mov     rdx, rbx; lpCommandLine
0x18001a3d1  lea     rax, [rsp+0E8h+StartupInfo]
0x18001a3d6  xor     ecx, ecx; lpApplicationName
0x18001a3d8  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18001a3dd  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001a3e6  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18001a3ef  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18001a3f7  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x18001a3ff  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18001a404  call    cs:__imp_CreateProcessW
0x18001a40b  nop     dword ptr [rax+rax+00h]
0x18001a410  test    eax, eax
0x18001a412  jnz     short loc_18001A41B
0x18001a414  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a419  jmp     short loc_18001A48F
0x18001a41b  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x18001a420  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a423  call    cs:__imp_WaitForSingleObject
0x18001a42a  nop     dword ptr [rax+rax+00h]
0x18001a42f  test    eax, eax
0x18001a431  jnz     short loc_18001A44D
0x18001a433  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x18001a438  mov     rdx, rdi; lpExitCode
0x18001a43b  mov     [rdi], eax
0x18001a43d  call    cs:__imp_GetExitCodeProcess
0x18001a444  nop     dword ptr [rax+rax+00h]
0x18001a449  test    eax, eax
0x18001a44b  jnz     short loc_18001A45F
0x18001a44d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a452  mov     ebx, eax
0x18001a454  test    eax, eax
0x18001a456  js      short loc_18001A46B
0x18001a458  mov     ebx, 8000FFFFh
0x18001a45d  jmp     short loc_18001A46B
0x18001a45f  mov     eax, [rdi]
0x18001a461  neg     eax
0x18001a463  sbb     ebx, ebx
0x18001a465  and     ebx, 80004005h
0x18001a46b  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18001a470  call    cs:__imp_CloseHandle
0x18001a477  nop     dword ptr [rax+rax+00h]
0x18001a47c  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18001a481  call    cs:__imp_CloseHandle
0x18001a488  nop     dword ptr [rax+rax+00h]
0x18001a48d  mov     eax, ebx
0x18001a48f  mov     rbx, [rsp+0E8h+arg_0]
0x18001a497  add     rsp, 0E0h
0x18001a49e  pop     rdi
0x18001a49f  retn
```
