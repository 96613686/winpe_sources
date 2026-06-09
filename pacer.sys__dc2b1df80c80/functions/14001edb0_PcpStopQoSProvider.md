# PcpStopQoSProvider

- ea: `0x14001edb0`
- end: `0x14001ee05`
- name: `PcpStopQoSProvider`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000feb0`
- `0x14001edb0`

## import_xrefs

- `NDIS!NdisFreeRWLock` at `0x14001edf3`
- `NDIS!NdisFreeRWLock` at `0x14001edf3`
- `NETIO!NmrDeregisterProvider` at `0x14001edc3`
- `NETIO!NmrDeregisterProvider` at `0x14001edc3`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14001eddb`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14001eddb`

## pseudocode

```c
void PcpStopQoSProvider()
{
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 &= ~1uLL;
  NmrDeregisterProvider(PcgQoSProviderHandle);
  if ( PcgQoSProviderHandle )
  {
    NmrWaitForProviderDeregisterComplete(PcgQoSProviderHandle);
    PcDeregisterQoSProviderComplete();
  }
  NdisFreeRWLock(PcgQoSClientListLock);
}

```

## disassembly

```asm
0x14001edb0  sub     rsp, 28h
0x14001edb4  mov     rcx, cs:PcgQoSProviderHandle; NmrProviderHandle
0x14001edbb  and     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0FFFFFFFFFFFFFFFEh
0x14001edc3  call    cs:__imp_NmrDeregisterProvider
0x14001edca  nop     dword ptr [rax+rax+00h]
0x14001edcf  mov     rcx, cs:PcgQoSProviderHandle; NmrProviderHandle
0x14001edd6  test    rcx, rcx
0x14001edd9  jz      short loc_14001EDEC
0x14001eddb  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14001ede2  nop     dword ptr [rax+rax+00h]
0x14001ede7  call    PcDeregisterQoSProviderComplete
0x14001edec  mov     rcx, cs:PcgQoSClientListLock; Lock
0x14001edf3  call    cs:__imp_NdisFreeRWLock
0x14001edfa  nop     dword ptr [rax+rax+00h]
0x14001edff  add     rsp, 28h
0x14001ee03  retn
```
