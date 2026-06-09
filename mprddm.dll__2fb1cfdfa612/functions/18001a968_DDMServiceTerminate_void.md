# DDMServiceTerminate(void)

- ea: `0x18001a968`
- end: `0x18001aa80`
- name: `?DDMServiceTerminate@@YAXXZ`
- size: `280`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ab50`

## callees

- `0x18000b078`
- `0x18000b2b0`
- `0x18001a7b0`
- `0x18001a968`
- `0x18003a9dc`
- `0x18003b8f4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001aa65`
- `KERNEL32!CloseHandle` at `0x18001aa65`
- `KERNEL32!GetLastError` at `0x18001a9c4`
- `KERNEL32!GetLastError` at `0x18001a9c4`
- `ADVAPI32!PerfStopProvider` at `0x18001aa36`
- `ADVAPI32!PerfStopProvider` at `0x18001aa36`
- `ADVAPI32!PerfDeleteInstance` at `0x18001a9e8`
- `ADVAPI32!PerfDeleteInstance` at `0x18001a9e8`
- `rasman!RasRegisterPnPHandler` at `0x18001a9a8`
- `rasman!RasRegisterPnPHandler` at `0x18001a9a8`

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

  dword_1800C84E0 |= 0x40u;
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
0x18001a968  sub     rsp, 28h
0x18001a96c  or      cs:dword_1800C84E0, 40h
0x18001a973  lea     rax, ??_7DeviceStartClosing@@6B@; const DeviceStartClosing::`vftable'
0x18001a97a  mov     ecx, 11h; unsigned int
0x18001a97f  mov     [rsp+28h+arg_0], rax
0x18001a984  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001a989  xor     r9d, r9d; void *
0x18001a98c  lea     rdx, [rsp+28h+arg_0]; struct DdmDeviceVisitor *
0x18001a991  xor     r8d, r8d; int
0x18001a994  mov     rcx, rax; this
0x18001a997  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x18001a99c  xor     r8d, r8d
0x18001a99f  lea     rcx, ?DdmDevicePnpHandler@@YAKPEAX@Z; DdmDevicePnpHandler(void *)
0x18001a9a6  xor     edx, edx
0x18001a9a8  call    cs:__imp_RasRegisterPnPHandler
0x18001a9ae  mov     r8d, 115h; unsigned int
0x18001a9b4  lea     rdx, aUninitializepe; "UninitializePerfmonCounters"
0x18001a9bb  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001a9c0  test    eax, eax
0x18001a9c2  jnz     short loc_18001A9CC
0x18001a9c4  call    cs:__imp_GetLastError
0x18001a9ca  jmp     short loc_18001AA0B
0x18001a9cc  cmp     cs:?PerfmonCounterInitialization@@3KA, 0; ulong PerfmonCounterInitialization
0x18001a9d3  jnz     short loc_18001A9F9
0x18001a9d5  mov     rdx, cs:Instance; InstanceBlock
0x18001a9dc  test    rdx, rdx
0x18001a9df  jz      short loc_18001A9F9
0x18001a9e1  mov     rcx, cs:DdmCounters; Provider
0x18001a9e8  call    cs:__imp_PerfDeleteInstance
0x18001a9ee  mov     cs:Instance, 0
0x18001a9f9  mov     r8d, 129h; unsigned int
0x18001a9ff  lea     rdx, aUninitializepe; "UninitializePerfmonCounters"
0x18001aa06  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001aa0b  mov     r8d, 0B0h; unsigned int
0x18001aa11  lea     rdx, aStopperfmoncou; "StopPerfmonCounters"
0x18001aa18  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001aa1d  test    eax, eax
0x18001aa1f  jz      short loc_18001AA59
0x18001aa21  cmp     cs:?PerfmonCounterInitialization@@3KA, 0; ulong PerfmonCounterInitialization
0x18001aa28  jnz     short loc_18001AA47
0x18001aa2a  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001aa31  test    rcx, rcx
0x18001aa34  jz      short loc_18001AA47
0x18001aa36  call    cs:__imp_PerfStopProvider
0x18001aa3c  mov     cs:DdmCounters, 0
0x18001aa47  mov     r8d, 0BBh; unsigned int
0x18001aa4d  lea     rdx, aStopperfmoncou; "StopPerfmonCounters"
0x18001aa54  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001aa59  mov     rcx, cs:g_PerfmonLock; hObject
0x18001aa60  test    rcx, rcx
0x18001aa63  jz      short loc_18001AA76
0x18001aa65  call    cs:__imp_CloseHandle
0x18001aa6b  mov     cs:g_PerfmonLock, 0
0x18001aa76  call    ?DDMServiceStopComplete@@YAXPEAX@Z; DDMServiceStopComplete(void *)
0x18001aa7b  add     rsp, 28h
0x18001aa7f  retn
```
