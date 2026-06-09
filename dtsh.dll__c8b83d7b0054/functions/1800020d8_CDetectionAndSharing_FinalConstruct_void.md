# CDetectionAndSharing::FinalConstruct(void)

- ea: `0x1800020d8`
- end: `0x1800021db`
- name: `?FinalConstruct@CDetectionAndSharing@@QEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e48`

## callees

- `0x1800020d8`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180002197`
- `msvcrt!_beginthreadex` at `0x180002197`
- `ADVAPI32!OpenSCManagerW` at `0x1800020f1`
- `ADVAPI32!OpenSCManagerW` at `0x1800020f1`
- `KERNEL32!EnterCriticalSection` at `0x18000211c`
- `KERNEL32!EnterCriticalSection` at `0x18000211c`
- `KERNEL32!LeaveCriticalSection` at `0x1800021c8`
- `KERNEL32!LeaveCriticalSection` at `0x1800021c8`
- `KERNEL32!GetLastError` at `0x180002100`
- `KERNEL32!GetLastError` at `0x180002100`
- `KERNEL32!CreateEventW` at `0x180002166`
- `KERNEL32!CreateEventW` at `0x180002166`
- `KERNEL32!CloseHandle` at `0x1800021b0`
- `KERNEL32!CloseHandle` at `0x1800021b0`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::FinalConstruct(CDetectionAndSharing *this)
{
  unsigned int v2; // edi
  SC_HANDLE v3; // rax
  signed int LastError; // eax

  v2 = 0;
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  *((_QWORD *)this + 8) = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  EnterCriticalSection(&g_cs);
  if ( ++g_lDtshInstanceCount == 1 && !g_hFWMonitorThread && !g_hFWMonitorEvent && !g_bFWMonitorCancelled )
  {
    g_hFWMonitorEvent = CreateEventW(0, 0, 0, 0);
    if ( g_hFWMonitorEvent )
    {
      g_hFWMonitorThread = (HANDLE)_beginthreadex(0, 0, CDetectionAndSharing::FWMonitoringFunction, 0, 0, 0);
      if ( !g_hFWMonitorThread )
      {
        CloseHandle(g_hFWMonitorEvent);
        g_hFWMonitorEvent = 0;
      }
    }
  }
  LeaveCriticalSection(&g_cs);
  return v2;
}

```

## disassembly

```asm
0x1800020d8  mov     [rsp+arg_0], rbx
0x1800020dd  push    rdi
0x1800020de  sub     rsp, 30h
0x1800020e2  mov     rbx, rcx
0x1800020e5  xor     edx, edx; lpDatabaseName
0x1800020e7  xor     ecx, ecx; lpMachineName
0x1800020e9  mov     r8d, 80000000h; dwDesiredAccess
0x1800020ef  xor     edi, edi
0x1800020f1  call    cs:__imp_OpenSCManagerW
0x1800020f7  mov     [rbx+40h], rax
0x1800020fb  test    rax, rax
0x1800020fe  jnz     short loc_180002115
0x180002100  call    cs:__imp_GetLastError
0x180002106  mov     edi, eax
0x180002108  test    eax, eax
0x18000210a  jle     short loc_180002115
0x18000210c  movzx   edi, ax
0x18000210f  or      edi, 80070000h
0x180002115  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000211c  call    cs:__imp_EnterCriticalSection
0x180002122  mov     eax, cs:?g_lDtshInstanceCount@@3JC; long volatile g_lDtshInstanceCount
0x180002128  inc     eax
0x18000212a  mov     cs:?g_lDtshInstanceCount@@3JC, eax; long volatile g_lDtshInstanceCount
0x180002130  mov     eax, cs:?g_lDtshInstanceCount@@3JC; long volatile g_lDtshInstanceCount
0x180002136  cmp     eax, 1
0x180002139  jnz     loc_1800021C1
0x18000213f  cmp     cs:?g_hFWMonitorThread@@3PEAXEA, 0; void * g_hFWMonitorThread
0x180002147  jnz     short loc_1800021C1
0x180002149  cmp     cs:?g_hFWMonitorEvent@@3PEAXEA, 0; void * g_hFWMonitorEvent
0x180002151  jnz     short loc_1800021C1
0x180002153  cmp     cs:?g_bFWMonitorCancelled@@3EA, 0; uchar g_bFWMonitorCancelled
0x18000215a  jnz     short loc_1800021C1
0x18000215c  xor     r9d, r9d; lpName
0x18000215f  xor     r8d, r8d; bInitialState
0x180002162  xor     edx, edx; bManualReset
0x180002164  xor     ecx, ecx; lpEventAttributes
0x180002166  call    cs:__imp_CreateEventW
0x18000216c  mov     cs:?g_hFWMonitorEvent@@3PEAXEA, rax; void * g_hFWMonitorEvent
0x180002173  test    rax, rax
0x180002176  jz      short loc_1800021C1
0x180002178  mov     [rsp+38h+ThrdAddr], 0; ThrdAddr
0x180002181  lea     r8, ?FWMonitoringFunction@CDetectionAndSharing@@CAKPEAPEAX@Z; StartAddress
0x180002188  xor     r9d, r9d; ArgList
0x18000218b  mov     [rsp+38h+InitFlag], 0; InitFlag
0x180002193  xor     edx, edx; StackSize
0x180002195  xor     ecx, ecx; Security
0x180002197  call    cs:__imp__beginthreadex
0x18000219d  mov     cs:?g_hFWMonitorThread@@3PEAXEA, rax; void * g_hFWMonitorThread
0x1800021a4  test    rax, rax
0x1800021a7  jnz     short loc_1800021C1
0x1800021a9  mov     rcx, cs:?g_hFWMonitorEvent@@3PEAXEA; hObject
0x1800021b0  call    cs:__imp_CloseHandle
0x1800021b6  mov     cs:?g_hFWMonitorEvent@@3PEAXEA, 0; void * g_hFWMonitorEvent
0x1800021c1  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800021c8  call    cs:__imp_LeaveCriticalSection
0x1800021ce  mov     rbx, [rsp+38h+arg_0]
0x1800021d3  mov     eax, edi
0x1800021d5  add     rsp, 30h
0x1800021d9  pop     rdi
0x1800021da  retn
```
