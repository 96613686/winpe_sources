# DhcpFirewallInit

- ea: `0x18002e500`
- end: `0x18002e6ce`
- name: `DhcpFirewallInit`
- size: `462`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002896c`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18001907c`
- `0x18002e500`
- `0x1800338c0`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e5c3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e5c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e67f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e67f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e5ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e5ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e662`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e592`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002e61e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002e61e`

## pseudocode

```c
__int64 DhcpFirewallInit()
{
  HANDLE v0; // rsi
  unsigned int LastErrorOrUnknown; // ebx
  _QWORD *v2; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v4; // rax
  __int64 v5; // rcx
  HMODULE phModule; // [rsp+68h] [rbp+28h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp+30h] BYREF
  __int64 v9; // [rsp+78h] [rbp+38h] BYREF

  v0 = Dhcpv6GlobalFirewallReadyEvent;
  v9 = 0;
  TargetHandle = 0;
  phModule = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 12, WPP_52380679383138217cb423d182f11bb5_Traceguids, 546);
  if ( v0 )
  {
    v9 = DhcpAlloc(24);
    v2 = (_QWORD *)v9;
    if ( v9 )
    {
      CurrentProcess = GetCurrentProcess();
      v4 = GetCurrentProcess();
      if ( DuplicateHandle(v4, v0, CurrentProcess, &TargetHandle, 0, 0, 2u)
        && GetModuleHandleExW(4u, (LPCWSTR)DhcpFirewallAddPortCallback, &phModule)
        && (*(_WORD *)v2 = 546,
            v2[1] = TargetHandle,
            v2[2] = phModule,
            TrySubmitThreadpoolCallback(DhcpFirewallAddPortCallback, v2, 0)) )
      {
        LastErrorOrUnknown = 0;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_(1028, 13, WPP_52380679383138217cb423d182f11bb5_Traceguids);
        phModule = 0;
        TargetHandle = 0;
        v9 = 0;
      }
      else
      {
        LastErrorOrUnknown = GetLastErrorOrUnknown(v5);
      }
    }
    else
    {
      LastErrorOrUnknown = 8;
    }
  }
  else
  {
    LastErrorOrUnknown = 87;
  }
  if ( phModule )
  {
    FreeLibrary(phModule);
    phModule = 0;
  }
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  DhcpFree((LPVOID *)&v9);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 14, WPP_52380679383138217cb423d182f11bb5_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x18002e500  mov     [rsp-18h+arg_0], rbx
0x18002e505  mov     [rsp-18h+phModule], rdx
0x18002e50a  push    rbp
0x18002e50b  push    rsi
0x18002e50c  push    rdi
0x18002e50d  mov     rbp, rsp
0x18002e510  sub     rsp, 40h
0x18002e514  mov     rsi, cs:Dhcpv6GlobalFirewallReadyEvent
0x18002e51b  mov     [rbp+arg_18], 0
0x18002e523  mov     [rbp+TargetHandle], 0
0x18002e52b  mov     [rbp+phModule], 0
0x18002e533  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e53a  jz      short loc_18002E558
0x18002e53c  mov     edx, 0Ch
0x18002e541  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e548  mov     ecx, 404h
0x18002e54d  mov     r9d, 222h
0x18002e553  call    WPP_SF_d
0x18002e558  test    rsi, rsi
0x18002e55b  jnz     short loc_18002E565
0x18002e55d  lea     ebx, [rsi+57h]
0x18002e560  jmp     loc_18002E659
0x18002e565  mov     ecx, 18h
0x18002e56a  call    DhcpAlloc
0x18002e56f  mov     [rbp+arg_18], rax
0x18002e573  mov     rdi, rax
0x18002e576  test    rax, rax
0x18002e579  jnz     short loc_18002E583
0x18002e57b  lea     ebx, [rax+8]
0x18002e57e  jmp     loc_18002E659
0x18002e583  call    cs:__imp_GetCurrentProcess
0x18002e58a  nop     dword ptr [rax+rax+00h]
0x18002e58f  mov     rbx, rax
0x18002e592  call    cs:__imp_GetCurrentProcess
0x18002e599  nop     dword ptr [rax+rax+00h]
0x18002e59e  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18002e5a6  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18002e5aa  mov     rcx, rax; hSourceProcessHandle
0x18002e5ad  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18002e5b5  mov     r8, rbx; hTargetProcessHandle
0x18002e5b8  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x18002e5c0  mov     rdx, rsi; hSourceHandle
0x18002e5c3  call    cs:__imp_DuplicateHandle
0x18002e5ca  nop     dword ptr [rax+rax+00h]
0x18002e5cf  test    eax, eax
0x18002e5d1  jnz     short loc_18002E5DC
0x18002e5d3  call    GetLastErrorOrUnknown
0x18002e5d8  mov     ebx, eax
0x18002e5da  jmp     short loc_18002E659
0x18002e5dc  lea     r8, [rbp+phModule]; phModule
0x18002e5e0  mov     ecx, 4; dwFlags
0x18002e5e5  lea     rdx, DhcpFirewallAddPortCallback; lpModuleName
0x18002e5ec  call    cs:__imp_GetModuleHandleExW
0x18002e5f3  nop     dword ptr [rax+rax+00h]
0x18002e5f8  test    eax, eax
0x18002e5fa  jz      short loc_18002E5D3
0x18002e5fc  mov     word ptr [rdi], 222h
0x18002e601  lea     rcx, DhcpFirewallAddPortCallback; pfns
0x18002e608  mov     rax, [rbp+TargetHandle]
0x18002e60c  xor     r8d, r8d; pcbe
0x18002e60f  mov     [rdi+8], rax
0x18002e613  mov     rdx, rdi; pv
0x18002e616  mov     rax, [rbp+phModule]
0x18002e61a  mov     [rdi+10h], rax
0x18002e61e  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002e625  nop     dword ptr [rax+rax+00h]
0x18002e62a  test    eax, eax
0x18002e62c  jz      short loc_18002E5D3
0x18002e62e  xor     ebx, ebx
0x18002e630  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e637  jz      short loc_18002E64D
0x18002e639  lea     edx, [rbx+0Dh]
0x18002e63c  mov     ecx, 404h
0x18002e641  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e648  call    WPP_SF_
0x18002e64d  mov     [rbp+phModule], rbx
0x18002e651  mov     [rbp+TargetHandle], rbx
0x18002e655  mov     [rbp+arg_18], rbx
0x18002e659  mov     rcx, [rbp+phModule]; hLibModule
0x18002e65d  test    rcx, rcx
0x18002e660  jz      short loc_18002E676
0x18002e662  call    cs:__imp_FreeLibrary
0x18002e669  nop     dword ptr [rax+rax+00h]
0x18002e66e  mov     [rbp+phModule], 0
0x18002e676  mov     rcx, [rbp+TargetHandle]; hObject
0x18002e67a  test    rcx, rcx
0x18002e67d  jz      short loc_18002E693
0x18002e67f  call    cs:__imp_CloseHandle
0x18002e686  nop     dword ptr [rax+rax+00h]
0x18002e68b  mov     [rbp+TargetHandle], 0
0x18002e693  lea     rcx, [rbp+arg_18]
0x18002e697  call    DhcpFree
0x18002e69c  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e6a3  jz      short loc_18002E6BE
0x18002e6a5  mov     edx, 0Eh
0x18002e6aa  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e6b1  mov     ecx, 404h
0x18002e6b6  mov     r9d, ebx
0x18002e6b9  call    WPP_SF_D
0x18002e6be  mov     eax, ebx
0x18002e6c0  mov     rbx, [rsp+40h+arg_0]
0x18002e6c5  add     rsp, 40h
0x18002e6c9  pop     rdi
0x18002e6ca  pop     rsi
0x18002e6cb  pop     rbp
0x18002e6cc  retn
```
