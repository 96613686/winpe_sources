# SharedSocket::CleanupTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180027a60`
- end: `0x180027a8b`
- name: `?CleanupTimerCallback@SharedSocket@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `43`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000264c`
- `0x180027a60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180027a6d`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180027a6d`

## pseudocode

```c
void __fastcall SharedSocket::CleanupTimerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  SocketBrokerContext *v4; // rcx

  if ( Context )
  {
    DisassociateCurrentThreadFromCallback(Instance);
    v4 = (SocketBrokerContext *)*((_QWORD *)Context + 10);
    if ( v4 )
      SocketBrokerContext::CompleteRetrieveSocket(v4, *((const unsigned __int16 **)Context + 13));
  }
}

```

## disassembly

```asm
0x180027a60  test    rdx, rdx
0x180027a63  jz      short locret_180027A8A
0x180027a65  push    rbx
0x180027a66  sub     rsp, 20h
0x180027a6a  mov     rbx, rdx
0x180027a6d  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x180027a73  mov     rcx, [rbx+50h]; this
0x180027a77  test    rcx, rcx
0x180027a7a  jz      short loc_180027A85
0x180027a7c  mov     rdx, [rbx+68h]; unsigned __int16 *
0x180027a80  call    ?CompleteRetrieveSocket@SocketBrokerContext@@QEAAKPEBG@Z; SocketBrokerContext::CompleteRetrieveSocket(ushort const *)
0x180027a85  add     rsp, 20h
0x180027a89  pop     rbx
0x180027a8a  retn
```
