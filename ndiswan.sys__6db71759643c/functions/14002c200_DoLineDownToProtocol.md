# DoLineDownToProtocol

- ea: `0x14002c200`
- end: `0x14002c3ee`
- name: `DoLineDownToProtocol`
- size: `494`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d0c0`
- `0x1400254c8`
- `0x140027a50`

## callees

- `0x14000c930`
- `0x1400161f0`
- `0x140016700`
- `0x14002c200`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002c37c`
- `ntoskrnl!KeSetEvent` at `0x14002c37c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c29e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c391`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c29e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c391`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c330`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c3b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c330`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c3b5`
- `NDIS!NdisResetEvent` at `0x14002c31a`
- `NDIS!NdisResetEvent` at `0x14002c31a`
- `NDIS!NdisWaitEvent` at `0x14002c30a`
- `NDIS!NdisWaitEvent` at `0x14002c30a`
- `NDIS!NdisInitializeEvent` at `0x14002c2ae`
- `NDIS!NdisInitializeEvent` at `0x14002c2ae`
- `NDIS!NdisMIndicateStatusEx` at `0x14002c2f2`
- `NDIS!NdisMIndicateStatusEx` at `0x14002c2f2`

## pseudocode

```c
__int64 __fastcall DoLineDownToProtocol(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // r14
  __int64 v4; // r9
  _QWORD *v5; // r8
  struct _NDIS_STATUS_INDICATION StatusIndication; // [rsp+20h] [rbp-79h] BYREF
  int v8; // [rsp+90h] [rbp-9h] BYREF
  __int16 v9; // [rsp+94h] [rbp-5h]
  int v10; // [rsp+96h] [rbp-3h]
  __int16 v11; // [rsp+9Ah] [rbp+1h]
  struct _NDIS_EVENT Event; // [rsp+9Ch] [rbp+3h] BYREF
  int v13; // [rsp+B4h] [rbp+1Bh]

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_QWORD *)(a1 + 64);
  v13 = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&StatusIndication, 0, sizeof(StatusIndication));
  v8 = *(_DWORD *)(a1 + 244);
  v9 = *(_WORD *)(a1 + 248);
  v10 = *(_DWORD *)(a1 + 250);
  v11 = *(_WORD *)(a1 + 254);
  *(_DWORD *)(a1 + 240) = 0;
  *(_DWORD *)(a1 + 20) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 1768), *(_BYTE *)(v2 + 1776));
  NdisInitializeEvent((PNDIS_EVENT)&Event.Event.Header.SignalState);
  Event.Event.Header.Type = 0;
  StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
  StatusIndication.SourceHandle = *(NDIS_HANDLE *)(v1 + 40);
  StatusIndication.StatusBuffer = &v8;
  StatusIndication.PortNumber = 0;
  StatusIndication.StatusCode = 1073807369;
  StatusIndication.StatusBufferSize = 12;
  NdisMIndicateStatusEx(*(NDIS_HANDLE *)(v1 + 40), &StatusIndication);
  if ( Event.Event.Header.Type )
  {
    NdisWaitEvent((PNDIS_EVENT)&Event.Event.Header.SignalState, 0);
    NdisResetEvent((PNDIS_EVENT)&Event.Event.Header.SignalState);
  }
  *(_BYTE *)(v1 + 168) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 160));
  v4 = *(_QWORD *)(a1 + 88);
  if ( *(_QWORD *)(v4 + 8) != a1 + 88 || (v5 = *(_QWORD **)(a1 + 96), *v5 != a1 + 88) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  if ( (*(_DWORD *)(v1 + 88) & 8) != 0 )
    KeSetEvent((PRKEVENT)(v1 + 136), 1, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 160), *(_BYTE *)(v1 + 168));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
    NdisWanFreeMiniportCB((PVOID)v1);
  *(_BYTE *)(v2 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 1768));
  return 0;
}

```

## disassembly

```asm
0x14002c200  push    rbp
0x14002c202  push    rbx
0x14002c203  push    rsi
0x14002c204  push    rdi
0x14002c205  push    r14
0x14002c207  push    r15
0x14002c209  lea     rbp, [rsp-2Fh]
0x14002c20e  sub     rsp, 0C8h
0x14002c215  mov     rax, cs:__security_cookie
0x14002c21c  xor     rax, rsp
0x14002c21f  mov     [rbp+57h+var_38], rax
0x14002c223  mov     rbx, [rcx+38h]
0x14002c227  xor     edx, edx; Val
0x14002c229  mov     r14, [rcx+40h]
0x14002c22d  mov     rsi, rcx
0x14002c230  xorps   xmm0, xmm0
0x14002c233  mov     [rbp+57h+Event.Event.Header.WaitListHead.Blink], 0
0x14002c23b  lea     rcx, [rbp+57h+StatusIndication]; void *
0x14002c23f  mov     [rbp+57h+var_3C], 0
0x14002c246  lea     r8d, [rdx+70h]; Size
0x14002c24a  movdqu  xmmword ptr [rbp+57h+Event.Event.Header], xmm0
0x14002c24f  call    memset
0x14002c254  mov     eax, [rsi+0F4h]
0x14002c25a  lea     r15, [r14+6E8h]
0x14002c261  mov     [rbp+57h+var_60], eax
0x14002c264  mov     rcx, r15; SpinLock
0x14002c267  movzx   eax, word ptr [rsi+0F8h]
0x14002c26e  mov     [rbp+57h+var_5C], ax
0x14002c272  mov     eax, [rsi+0FAh]
0x14002c278  mov     [rbp+57h+var_5A], eax
0x14002c27b  movzx   eax, word ptr [rsi+0FEh]
0x14002c282  mov     [rbp+57h+var_56], ax
0x14002c286  mov     dword ptr [rsi+0F0h], 0
0x14002c290  mov     dword ptr [rsi+14h], 0
0x14002c297  mov     dl, [r14+6F0h]; NewIrql
0x14002c29e  call    cs:__imp_KeReleaseSpinLock
0x14002c2a5  nop     dword ptr [rax+rax+00h]
0x14002c2aa  lea     rcx, [rbp+57h+Event.Event.Header.SignalState]; Event
0x14002c2ae  call    cs:__imp_NdisInitializeEvent
0x14002c2b5  nop     dword ptr [rax+rax+00h]
0x14002c2ba  mov     byte ptr [rbp+57h+Event.Event.Header], 0
0x14002c2be  lea     rdx, [rbp+57h+StatusIndication]; StatusIndication
0x14002c2c2  mov     dword ptr [rbp+57h+StatusIndication.Header.Type], 700198h
0x14002c2c9  mov     rax, [rbx+28h]
0x14002c2cd  mov     [rbp+57h+StatusIndication.SourceHandle], rax
0x14002c2d1  lea     rax, [rbp+57h+var_60]
0x14002c2d5  mov     [rbp+57h+StatusIndication.StatusBuffer], rax
0x14002c2d9  mov     [rbp+57h+StatusIndication.PortNumber], 0
0x14002c2e0  mov     [rbp+57h+StatusIndication.StatusCode], 40010009h
0x14002c2e7  mov     [rbp+57h+StatusIndication.StatusBufferSize], 0Ch
0x14002c2ee  mov     rcx, [rbx+28h]; MiniportAdapterHandle
0x14002c2f2  call    cs:__imp_NdisMIndicateStatusEx
0x14002c2f9  nop     dword ptr [rax+rax+00h]
0x14002c2fe  cmp     byte ptr [rbp+57h+Event.Event.Header], 0
0x14002c302  jz      short loc_14002C326
0x14002c304  xor     edx, edx; MsToWait
0x14002c306  lea     rcx, [rbp+57h+Event.Event.Header.SignalState]; Event
0x14002c30a  call    cs:__imp_NdisWaitEvent
0x14002c311  nop     dword ptr [rax+rax+00h]
0x14002c316  lea     rcx, [rbp+57h+Event.Event.Header.SignalState]; Event
0x14002c31a  call    cs:__imp_NdisResetEvent
0x14002c321  nop     dword ptr [rax+rax+00h]
0x14002c326  lea     rdi, [rbx+0A0h]
0x14002c32d  mov     rcx, rdi; SpinLock
0x14002c330  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c337  nop     dword ptr [rax+rax+00h]
0x14002c33c  mov     [rbx+0A8h], al
0x14002c342  lea     rax, [rsi+58h]
0x14002c346  mov     r9, [rax]
0x14002c349  cmp     [r9+8], rax
0x14002c34d  jnz     loc_14002C3E7
0x14002c353  mov     r8, [rax+8]
0x14002c357  cmp     [r8], rax
0x14002c35a  jnz     loc_14002C3E7
0x14002c360  mov     [r8], r9
0x14002c363  mov     [r9+8], r8
0x14002c367  mov     eax, [rbx+58h]
0x14002c36a  test    al, 8
0x14002c36c  jz      short loc_14002C388
0x14002c36e  xor     r8d, r8d; Wait
0x14002c371  lea     rcx, [rbx+88h]; Event
0x14002c378  lea     edx, [r8+1]; Increment
0x14002c37c  call    cs:__imp_KeSetEvent
0x14002c383  nop     dword ptr [rax+rax+00h]
0x14002c388  mov     dl, [rbx+0A8h]; NewIrql
0x14002c38e  mov     rcx, rdi; SpinLock
0x14002c391  call    cs:__imp_KeReleaseSpinLock
0x14002c398  nop     dword ptr [rax+rax+00h]
0x14002c39d  or      eax, 0FFFFFFFFh
0x14002c3a0  lock xadd [rbx+10h], eax
0x14002c3a5  cmp     eax, 1
0x14002c3a8  jnz     short loc_14002C3B2
0x14002c3aa  mov     rcx, rbx; P
0x14002c3ad  call    NdisWanFreeMiniportCB
0x14002c3b2  mov     rcx, r15; SpinLock
0x14002c3b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c3bc  nop     dword ptr [rax+rax+00h]
0x14002c3c1  mov     [r14+6F0h], al
0x14002c3c8  xor     eax, eax
0x14002c3ca  mov     rcx, [rbp+57h+var_38]
0x14002c3ce  xor     rcx, rsp; StackCookie
0x14002c3d1  call    __security_check_cookie
0x14002c3d6  add     rsp, 0C8h
0x14002c3dd  pop     r15
0x14002c3df  pop     r14
0x14002c3e1  pop     rdi
0x14002c3e2  pop     rsi
0x14002c3e3  pop     rbx
0x14002c3e4  pop     rbp
0x14002c3e5  retn
0x14002c3e7  mov     ecx, 3
0x14002c3ec  int     29h; Win8: RtlFailFast(ecx)
```
