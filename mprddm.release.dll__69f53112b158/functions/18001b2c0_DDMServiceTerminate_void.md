# DDMServiceTerminate(void)

- ea: `0x18001b2c0`
- end: `0x18001b3ee`
- name: `?DDMServiceTerminate@@YAXXZ`
- size: `302`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b4c0`

## callees

- `0x18000b358`
- `0x18000b594`
- `0x18001b0c0`
- `0x18001b2c0`
- `0x18003c2c8`
- `0x18003d278`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001b3cf`
- `KERNEL32!CloseHandle` at `0x18001b3cf`
- `KERNEL32!GetLastError` at `0x18001b322`
- `KERNEL32!GetLastError` at `0x18001b322`
- `ADVAPI32!PerfStopProvider` at `0x18001b39d`
- `ADVAPI32!PerfStopProvider` at `0x18001b39d`
- `ADVAPI32!PerfDeleteInstance` at `0x18001b34c`
- `ADVAPI32!PerfDeleteInstance` at `0x18001b34c`
- `rasman!RasRegisterPnPHandler` at `0x18001b300`
- `rasman!RasRegisterPnPHandler` at `0x18001b300`

## pseudocode

```c
void DDMServiceTerminate(void)
{
  DdmDeviceTable *Instance; // rax
  const char *v1; // rcx
  void *v2; // r9
  const char *v3; // rcx
  void *v4; // r9
  const char *v5; // rcx
  void *v6; // r9
  const char *v7; // rcx
  void *v8; // r9
  HANDLE v9; // rcx
  void **v10; // [rsp+30h] [rbp+8h] BYREF

  dword_1800CF4E0 |= 0x40u;
  v10 = &DeviceStartClosing::`vftable';
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&v10, 0, 0);
  RasRegisterPnPHandler(DdmDevicePnpHandler, 0, 0);
  if ( (unsigned int)GetAndTraceLock(v1, "UninitializePerfmonCounters", 0x115u, v2) )
  {
    if ( !PerfmonCounterInitialization && ::Instance )
    {
      PerfDeleteInstance(DdmCounters, ::Instance);
      ::Instance = 0;
    }
    ReleaseAndTraceLock(v3, "UninitializePerfmonCounters", 0x129u, v4);
  }
  else
  {
    GetLastError();
  }
  if ( (unsigned int)GetAndTraceLock(v5, "StopPerfmonCounters", 0xB0u, v6) )
  {
    if ( !PerfmonCounterInitialization )
    {
      v7 = (const char *)DdmCounters;
      if ( DdmCounters )
      {
        PerfStopProvider(DdmCounters);
        DdmCounters = 0;
      }
    }
    ReleaseAndTraceLock(v7, "StopPerfmonCounters", 0xBBu, v8);
  }
  v9 = g_PerfmonLock;
  if ( g_PerfmonLock )
  {
    CloseHandle(g_PerfmonLock);
    g_PerfmonLock = 0;
  }
  DDMServiceStopComplete(v9);
}

```

## disassembly

```asm
0x18001b2c0  sub     rsp, 28h
0x18001b2c4  or      cs:dword_1800CF4E0, 40h
0x18001b2cb  lea     rax, ??_7DeviceStartClosing@@6B@; const DeviceStartClosing::`vftable'
0x18001b2d2  mov     ecx, 11h; unsigned int
0x18001b2d7  mov     [rsp+28h+arg_0], rax
0x18001b2dc  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001b2e1  xor     r9d, r9d; void *
0x18001b2e4  lea     rdx, [rsp+28h+arg_0]; struct DdmDeviceVisitor *
0x18001b2e9  xor     r8d, r8d; int
0x18001b2ec  mov     rcx, rax; this
0x18001b2ef  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x18001b2f4  xor     r8d, r8d
0x18001b2f7  lea     rcx, ?DdmDevicePnpHandler@@YAKPEAX@Z; DdmDevicePnpHandler(void *)
0x18001b2fe  xor     edx, edx
0x18001b300  call    cs:__imp_RasRegisterPnPHandler
0x18001b307  nop     dword ptr [rax+rax+00h]
0x18001b30c  mov     r8d, 115h; unsigned int
0x18001b312  lea     rdx, aUninitializepe; "UninitializePerfmonCounters"
0x18001b319  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001b31e  test    eax, eax
0x18001b320  jnz     short loc_18001B330
0x18001b322  call    cs:__imp_GetLastError
0x18001b329  nop     dword ptr [rax+rax+00h]
0x18001b32e  jmp     short loc_18001B372
0x18001b330  cmp     cs:?PerfmonCounterInitialization@@3KA, 0; ulong PerfmonCounterInitialization
0x18001b337  jnz     short loc_18001B360
0x18001b339  mov     rdx, cs:Instance; InstanceBlock
0x18001b340  test    rdx, rdx
0x18001b343  jz      short loc_18001B360
0x18001b345  mov     rcx, cs:DdmCounters; Provider
0x18001b34c  call    cs:__imp_PerfDeleteInstance
0x18001b353  nop     dword ptr [rax+rax+00h]
0x18001b358  and     cs:Instance, 0
0x18001b360  mov     r8d, 129h; unsigned int
0x18001b366  lea     rdx, aUninitializepe; "UninitializePerfmonCounters"
0x18001b36d  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001b372  mov     r8d, 0B0h; unsigned int
0x18001b378  lea     rdx, aStopperfmoncou; "StopPerfmonCounters"
0x18001b37f  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001b384  test    eax, eax
0x18001b386  jz      short loc_18001B3C3
0x18001b388  cmp     cs:?PerfmonCounterInitialization@@3KA, 0; ulong PerfmonCounterInitialization
0x18001b38f  jnz     short loc_18001B3B1
0x18001b391  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b398  test    rcx, rcx
0x18001b39b  jz      short loc_18001B3B1
0x18001b39d  call    cs:__imp_PerfStopProvider
0x18001b3a4  nop     dword ptr [rax+rax+00h]
0x18001b3a9  and     cs:DdmCounters, 0
0x18001b3b1  mov     r8d, 0BBh; unsigned int
0x18001b3b7  lea     rdx, aStopperfmoncou; "StopPerfmonCounters"
0x18001b3be  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001b3c3  mov     rcx, cs:g_PerfmonLock; hObject
0x18001b3ca  test    rcx, rcx
0x18001b3cd  jz      short loc_18001B3E3
0x18001b3cf  call    cs:__imp_CloseHandle
0x18001b3d6  nop     dword ptr [rax+rax+00h]
0x18001b3db  and     cs:g_PerfmonLock, 0
0x18001b3e3  call    ?DDMServiceStopComplete@@YAXPEAX@Z; DDMServiceStopComplete(void *)
0x18001b3e8  add     rsp, 28h
0x18001b3ec  retn
```
