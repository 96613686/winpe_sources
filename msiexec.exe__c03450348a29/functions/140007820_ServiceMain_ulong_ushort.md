# ServiceMain(ulong,ushort * *)

- ea: `0x140007820`
- end: `0x1400078de`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `190`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x140007110`
- `0x140007374`
- `0x140007820`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140007834`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140007834`
- `KERNEL32!GetLastError` at `0x140007846`
- `KERNEL32!GetLastError` at `0x1400078a5`
- `KERNEL32!GetLastError` at `0x140007846`
- `KERNEL32!GetLastError` at `0x1400078a5`
- `KERNEL32!CloseHandle` at `0x1400078cb`
- `KERNEL32!CloseHandle` at `0x1400078cb`
- `KERNEL32!CreateThread` at `0x140007897`
- `KERNEL32!CreateThread` at `0x140007897`

## string_xrefs

- `0x14000782d`: `MSIServer`
- `0x14000784e`: `RegisterServiceCtrlHandler failed.`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  ServiceStatus *v2; // rcx
  DWORD v3; // eax
  HANDLE Thread; // rbx
  DWORD LastError; // eax
  ServiceStatus *v6; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-18h]

  hServiceStatus = RegisterServiceCtrlHandlerW(L"MSIServer", ServiceControl);
  if ( hServiceStatus )
  {
    if ( (unsigned int)ServiceStatus::ReportStatusToSCMgr(v2, 2u, 0, 0x7530u, dwCreationFlags) )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ServiceThreadMain, 0, 0, &g_dwThreadId);
      if ( Thread )
      {
        if ( g_ohThread != (HANDLE)-1LL )
          CloseHandle(g_ohThread);
        g_ohThread = Thread;
      }
      else
      {
        LastError = GetLastError();
        ServiceStatus::ReportStatusToSCMgr(v6, 1u, LastError, 0x7530u, dwCreationFlagsa);
      }
    }
  }
  else
  {
    v3 = GetLastError();
    ReportErrorToDebugOutput((const WCHAR *)L"RegisterServiceCtrlHandler failed.", v3);
  }
}

```

## disassembly

```asm
0x140007820  push    rbx
0x140007822  sub     rsp, 30h
0x140007826  lea     rdx, ?ServiceControl@@YAXK@Z; lpHandlerProc
0x14000782d  lea     rcx, ServiceName; "MSIServer"
0x140007834  call    cs:__imp_RegisterServiceCtrlHandlerW
0x14000783a  mov     cs:hServiceStatus, rax
0x140007841  test    rax, rax
0x140007844  jnz     short loc_14000785F
0x140007846  call    cs:__imp_GetLastError
0x14000784c  mov     edx, eax; unsigned int
0x14000784e  lea     rcx, aRegisterservic; "RegisterServiceCtrlHandler failed."
0x140007855  add     rsp, 30h
0x140007859  pop     rbx
0x14000785a  jmp     ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x14000785f  xor     r8d, r8d; unsigned int
0x140007862  mov     r9d, 7530h; unsigned int
0x140007868  lea     edx, [r8+2]; unsigned int
0x14000786c  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007871  test    eax, eax
0x140007873  jz      short loc_1400078D8
0x140007875  lea     rax, ?g_dwThreadId@@3KA; ulong g_dwThreadId
0x14000787c  xor     r9d, r9d; lpParameter
0x14000787f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140007884  lea     r8, ?ServiceThreadMain@@YAKPEAX@Z; lpStartAddress
0x14000788b  xor     edx, edx; dwStackSize
0x14000788d  mov     [rsp+38h+dwCreationFlags], 0; unsigned int
0x140007895  xor     ecx, ecx; lpThreadAttributes
0x140007897  call    cs:__imp_CreateThread
0x14000789d  mov     rbx, rax
0x1400078a0  test    rax, rax
0x1400078a3  jnz     short loc_1400078BE
0x1400078a5  call    cs:__imp_GetLastError
0x1400078ab  lea     edx, [rbx+1]; unsigned int
0x1400078ae  mov     r9d, 7530h; unsigned int
0x1400078b4  mov     r8d, eax; unsigned int
0x1400078b7  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x1400078bc  jmp     short loc_1400078D8
0x1400078be  mov     rcx, cs:?g_ohThread@@3VCHandle@@A; hObject
0x1400078c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400078c9  jz      short loc_1400078D1
0x1400078cb  call    cs:__imp_CloseHandle
0x1400078d1  mov     cs:?g_ohThread@@3VCHandle@@A, rbx; CHandle g_ohThread
0x1400078d8  add     rsp, 30h
0x1400078dc  pop     rbx
0x1400078dd  retn
```
