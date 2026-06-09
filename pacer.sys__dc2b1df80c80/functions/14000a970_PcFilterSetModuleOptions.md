# PcFilterSetModuleOptions

- ea: `0x14000a970`
- end: `0x14000aa36`
- name: `PcFilterSetModuleOptions`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a970`

## import_xrefs

- `NDIS!NdisSetOptionalHandlers` at `0x14000a9e4`
- `NDIS!NdisSetOptionalHandlers` at `0x14000a9e4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a9b3`
- `NDIS!NdisAcquireRWLockRead` at `0x14000a9b3`
- `NDIS!NdisReleaseRWLock` at `0x14000a9d0`
- `NDIS!NdisReleaseRWLock` at `0x14000a9d0`

## pseudocode

```c
NDIS_STATUS __fastcall PcFilterSetModuleOptions(__int64 a1)
{
  bool v3; // zf
  void (__fastcall *v4)(__int64, struct _NET_BUFFER_LIST *, NDIS_PORT_NUMBER, ULONG, ULONG); // rax
  _NDIS_DRIVER_OPTIONAL_HANDLERS OptionalHandlers[4]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v6; // [rsp+30h] [rbp-20h]
  __int128 v7; // [rsp+40h] [rbp-10h]
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  *(_OWORD *)&OptionalHandlers[0].Header.Type = 0;
  LockState.Flags = 0;
  OptionalHandlers[0].Header.Size = 48;
  v6 = 0;
  OptionalHandlers[0].Header.Type = -116;
  v7 = 0;
  NdisAcquireRWLockRead(PcgFilterDriverContext, &LockState, 0);
  if ( !*(_BYTE *)(a1 + 28) )
  {
    v3 = *(_DWORD *)(a1 + 16) == 3;
    *(_QWORD *)&OptionalHandlers[2].Header.Type = PcFilterSendNetBufferLists;
    *(_QWORD *)&v6 = PcFilterSendNetBufferListsComplete;
    *((_QWORD *)&v6 + 1) = PcFilterCancelSend;
    v4 = (void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, NDIS_PORT_NUMBER, ULONG, ULONG))v7;
    if ( v3 )
      v4 = PcFilterReceiveNetBufferLists;
    *(_QWORD *)&v7 = v4;
  }
  NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
  return NdisSetOptionalHandlers(*(NDIS_HANDLE *)(a1 + 40), OptionalHandlers);
}

```

## disassembly

```asm
0x14000a970  mov     [rsp-8+arg_8], rbx
0x14000a975  push    rbp
0x14000a976  mov     rbp, rsp
0x14000a979  sub     rsp, 50h
0x14000a97d  xor     eax, eax
0x14000a97f  lea     rdx, [rbp+LockState]; LockState
0x14000a983  xorps   xmm0, xmm0
0x14000a986  mov     word ptr [rbp+LockState.OldIrql], ax
0x14000a98a  movups  xmmword ptr [rbp+OptionalHandlers.Header.Type], xmm0
0x14000a98e  mov     [rbp+LockState.Flags], al
0x14000a991  mov     rbx, rcx
0x14000a994  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000a99b  mov     eax, 30h ; '0'
0x14000a9a0  xor     r8d, r8d; Flags
0x14000a9a3  mov     [rbp+OptionalHandlers.Header.Size], ax
0x14000a9a7  movups  [rbp+var_20], xmm0
0x14000a9ab  mov     [rbp+OptionalHandlers.Header.Type], 8Ch
0x14000a9af  movups  [rbp+var_10], xmm0
0x14000a9b3  call    cs:__imp_NdisAcquireRWLockRead
0x14000a9ba  nop     dword ptr [rax+rax+00h]
0x14000a9bf  cmp     byte ptr [rbx+1Ch], 0
0x14000a9c3  jz      short loc_14000A9FC
0x14000a9c5  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000a9cc  lea     rdx, [rbp+LockState]; LockState
0x14000a9d0  call    cs:__imp_NdisReleaseRWLock
0x14000a9d7  nop     dword ptr [rax+rax+00h]
0x14000a9dc  mov     rcx, [rbx+28h]; NdisHandle
0x14000a9e0  lea     rdx, [rbp+OptionalHandlers]; OptionalHandlers
0x14000a9e4  call    cs:__imp_NdisSetOptionalHandlers
0x14000a9eb  nop     dword ptr [rax+rax+00h]
0x14000a9f0  mov     rbx, [rsp+50h+arg_8]
0x14000a9f5  add     rsp, 50h
0x14000a9f9  pop     rbp
0x14000a9fa  retn
0x14000a9fc  cmp     dword ptr [rbx+10h], 3
0x14000aa00  lea     rax, PcFilterSendNetBufferLists
0x14000aa07  mov     qword ptr [rbp+OptionalHandlers.Header.Type+8], rax
0x14000aa0b  lea     rcx, PcFilterReceiveNetBufferLists
0x14000aa12  lea     rax, PcFilterSendNetBufferListsComplete
0x14000aa19  mov     qword ptr [rbp+var_20], rax
0x14000aa1d  lea     rax, PcFilterCancelSend
0x14000aa24  mov     qword ptr [rbp+var_20+8], rax
0x14000aa28  mov     rax, qword ptr [rbp+var_10]
0x14000aa2c  cmovz   rax, rcx
0x14000aa30  mov     qword ptr [rbp+var_10], rax
0x14000aa34  jmp     short loc_14000A9C5
```
