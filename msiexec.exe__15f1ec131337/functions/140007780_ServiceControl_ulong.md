# ServiceControl(ulong)

- ea: `0x140007780`
- end: `0x140007816`
- name: `?ServiceControl@@YAXK@Z`
- size: `150`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140005014`
- `0x140007374`
- `0x140007780`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400077ae`
- `KERNEL32!SetEvent` at `0x1400077ae`
- `USER32!PostThreadMessageW` at `0x1400077f2`

## pseudocode

```c
void __fastcall ServiceControl(DWORD dwControl)
{
  ServiceStatus *v1; // rcx

  v1 = (ServiceStatus *)(dwControl - 1);
  if ( !(_DWORD)v1 )
  {
    g_fWeWantToStop = 1;
    if ( g_cInstances > 0 || !(unsigned int)FCanStopService() )
    {
      g_fWeWantToStop = 0;
      goto LABEL_10;
    }
LABEL_8:
    ServiceStatus::ReportStatusToSCMgr(v1, 3u, 0, 0);
    PostThreadMessageW(g_dwThreadId, 0x12u, 0, 0);
    return;
  }
  if ( (_DWORD)v1 != 4 )
    goto LABEL_10;
  g_fWeWantToStop = 1;
  if ( !(unsigned int)FCanStopService() )
    goto LABEL_10;
  if ( g_cInstances <= 0 )
    goto LABEL_8;
  SetEvent(g_hCallbackEvent);
LABEL_10:
  ServiceStatus::ReportStatusToSCMgr(v1, ServiceStatus.dwCurrentState, 0, 0);
}

```

## disassembly

```asm
0x140007780  sub     rsp, 38h
0x140007784  sub     ecx, 1; this
0x140007787  jz      short loc_1400077B6
0x140007789  cmp     ecx, 4
0x14000778c  jnz     short loc_140007800
0x14000778e  mov     cs:?g_fWeWantToStop@@3_NA, 1; bool g_fWeWantToStop
0x140007795  call    ?FCanStopService@@YAHXZ; FCanStopService(void)
0x14000779a  test    eax, eax
0x14000779c  jz      short loc_140007800
0x14000779e  cmp     cs:?g_cInstances@@3JA, 0; long g_cInstances
0x1400077a5  jle     short loc_1400077CF
0x1400077a7  mov     rcx, cs:?g_hCallbackEvent@@3PEAXEA; hEvent
0x1400077ae  call    cs:__imp_SetEvent
0x1400077b4  jmp     short loc_140007800
0x1400077b6  cmp     cs:?g_cInstances@@3JA, 0; long g_cInstances
0x1400077bd  mov     cs:?g_fWeWantToStop@@3_NA, 1; bool g_fWeWantToStop
0x1400077c4  jg      short loc_1400077F9
0x1400077c6  call    ?FCanStopService@@YAHXZ; FCanStopService(void)
0x1400077cb  test    eax, eax
0x1400077cd  jz      short loc_1400077F9
0x1400077cf  xor     r9d, r9d; unsigned int
0x1400077d2  xor     r8d, r8d; unsigned int
0x1400077d5  lea     edx, [r9+3]; unsigned int
0x1400077d9  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x1400077de  mov     ecx, cs:?g_dwThreadId@@3KA; ulong g_dwThreadId
0x1400077e4  xor     r9d, r9d
0x1400077e7  xor     r8d, r8d
0x1400077ea  lea     edx, [r9+12h]
0x1400077ee  add     rsp, 38h
0x1400077f2  jmp     cs:__imp_PostThreadMessageW
0x1400077f9  mov     cs:?g_fWeWantToStop@@3_NA, 0; bool g_fWeWantToStop
0x140007800  mov     edx, cs:ServiceStatus.dwCurrentState; unsigned int
0x140007806  xor     r9d, r9d; unsigned int
0x140007809  xor     r8d, r8d; unsigned int
0x14000780c  call    ?ReportStatusToSCMgr@ServiceStatus@@QEAAHKKKK@Z; ServiceStatus::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x140007811  add     rsp, 38h
0x140007815  retn
```
