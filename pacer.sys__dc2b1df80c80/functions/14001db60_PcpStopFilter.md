# PcpStopFilter

- ea: `0x14001db60`
- end: `0x14001dc11`
- name: `PcpStopFilter`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140005578`
- `0x14000c8c8`
- `0x1400120c8`
- `0x14001db60`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001dba1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001dba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dbbe`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14001db73`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14001db73`
- `NDIS!NdisFreeRWLock` at `0x14001dbec`
- `NDIS!NdisFreeRWLock` at `0x14001dbff`
- `NDIS!NdisFreeRWLock` at `0x14001dbec`
- `NDIS!NdisFreeRWLock` at `0x14001dbff`

## pseudocode

```c
void PcpStopFilter()
{
  __int64 v0; // rdx

  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 &= ~2uLL;
  NdisFDeregisterFilterDriver(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink);
  PcpDereferenceDriver();
  if ( *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
    PcpDeleteFlow(*(char **)&WPP_MAIN_CB.DeviceLock.Header.Lock, v0);
  QosTerminate();
  ExDeleteNPagedLookasideList(&PcgNblCadLookasideList);
  if ( PcgLineTable )
  {
    ExFreePoolWithTag(PcgLineTable, 0x746C6350u);
    PcgLineTable = 0;
  }
  PcgLineTableLen = 0;
  PcgLineTableNextId = 0;
  NdisFreeRWLock(PcgLineListLock);
  NdisFreeRWLock(PcgFilterDriverContext);
}

```

## disassembly

```asm
0x14001db60  sub     rsp, 28h
0x14001db64  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink; NdisFilterDriverHandle
0x14001db6b  and     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0FFFFFFFFFFFFFFFDh
0x14001db73  call    cs:__imp_NdisFDeregisterFilterDriver
0x14001db7a  nop     dword ptr [rax+rax+00h]
0x14001db7f  call    PcpDereferenceDriver
0x14001db84  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceLock.Header; P
0x14001db8b  test    rcx, rcx
0x14001db8e  jz      short loc_14001DB95
0x14001db90  call    PcpDeleteFlow
0x14001db95  call    QosTerminate
0x14001db9a  lea     rcx, PcgNblCadLookasideList; Lookaside
0x14001dba1  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001dba8  nop     dword ptr [rax+rax+00h]
0x14001dbad  mov     rcx, cs:PcgLineTable; P
0x14001dbb4  test    rcx, rcx
0x14001dbb7  jz      short loc_14001DBD5
0x14001dbb9  mov     edx, 746C6350h; Tag
0x14001dbbe  call    cs:__imp_ExFreePoolWithTag
0x14001dbc5  nop     dword ptr [rax+rax+00h]
0x14001dbca  mov     cs:PcgLineTable, 0
0x14001dbd5  mov     rcx, cs:PcgLineListLock; Lock
0x14001dbdc  xor     eax, eax
0x14001dbde  mov     cs:PcgLineTableLen, ax
0x14001dbe5  mov     cs:PcgLineTableNextId, ax
0x14001dbec  call    cs:__imp_NdisFreeRWLock
0x14001dbf3  nop     dword ptr [rax+rax+00h]
0x14001dbf8  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14001dbff  call    cs:__imp_NdisFreeRWLock
0x14001dc06  nop     dword ptr [rax+rax+00h]
0x14001dc0b  add     rsp, 28h
0x14001dc0f  retn
```
