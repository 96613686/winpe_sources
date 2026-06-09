# DoNewLineUpToProtocol

- ea: `0x14002c3f4`
- end: `0x14002c684`
- name: `DoNewLineUpToProtocol`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140026c80`

## callees

- `0x14000a290`
- `0x14000c930`
- `0x14000e400`
- `0x14002c3f4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002c629`
- `ntoskrnl!KeSetEvent` at `0x14002c629`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c4bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c59c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c5b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c63e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c653`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c4bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c59c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c5b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c63e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c653`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c447`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c556`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c5d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c5e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c447`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c556`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c5d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c5e9`

## pseudocode

```c
__int64 __fastcall DoNewLineUpToProtocol(__int64 a1)
{
  __int64 v1; // rsi
  KIRQL v3; // al
  struct _LIST_ENTRY *Blink; // rbx
  unsigned int v5; // edi
  struct _LIST_ENTRY *Flink; // rcx
  _QWORD *v8; // rsi
  __int64 v9; // r8
  _QWORD *v10; // rax

  v1 = *(_QWORD *)(a1 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
  LOBYTE(WPP_MAIN_CB.DeviceType) = v3;
  if ( (struct _LIST_ENTRY **)WPP_MAIN_CB.Queue.ListEntry.Blink == &WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink )
  {
LABEL_8:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, WPP_MAIN_CB.DeviceType);
    v5 = 603;
  }
  else
  {
    while ( WORD2(Blink[8].Flink) != *(_WORD *)(a1 + 212) )
    {
      Blink = Blink->Flink;
      if ( Blink == (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink )
        goto LABEL_8;
    }
    *(_DWORD *)(a1 + 244) = Blink[7].Blink;
    *(_WORD *)(a1 + 248) = WORD2(Blink[7].Blink);
    *(_BYTE *)(a1 + 247) = *(_BYTE *)(v1 + 33);
    *(_BYTE *)(a1 + 248) = *(_BYTE *)(v1 + 32);
    *(_BYTE *)(a1 + 249) = *(_BYTE *)(a1 + 48);
    *(_DWORD *)(a1 + 250) = 0;
    *(_WORD *)(a1 + 254) = 0;
    LOBYTE(Blink[10].Blink) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Blink[10]);
    Flink = Blink[5].Flink;
    if ( Flink->Flink != (struct _LIST_ENTRY *)&Blink[4].Blink )
      goto LABEL_26;
    v8 = (_QWORD *)(a1 + 88);
    *(_QWORD *)(a1 + 88) = (char *)Blink + 72;
    *(_QWORD *)(a1 + 96) = Flink;
    Flink->Flink = (struct _LIST_ENTRY *)(a1 + 88);
    Blink[5].Flink = (struct _LIST_ENTRY *)(a1 + 88);
    *(_QWORD *)(a1 + 56) = Blink;
    _InterlockedIncrement((volatile signed __int32 *)&Blink[1]);
    KeReleaseSpinLock((PKSPIN_LOCK)&Blink[10], (KIRQL)Blink[10].Blink);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, WPP_MAIN_CB.DeviceType);
    v5 = DoLineUpToProtocol(a1, 1);
    if ( !v5 )
      goto LABEL_13;
    LOBYTE(WPP_MAIN_CB.DeviceType) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
    LOBYTE(Blink[10].Blink) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Blink[10]);
    v9 = *v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
LABEL_26:
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    if ( ((__int64)Blink[5].Blink & 8) != 0 )
      KeSetEvent((PRKEVENT)&Blink[8].Blink, 1, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)&Blink[10], (KIRQL)Blink[10].Blink);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, WPP_MAIN_CB.DeviceType);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Blink[1], 0xFFFFFFFF) == 1 )
      NdisWanFreeMiniportCB(Blink);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x14002c3f4  push    rbx
0x14002c3f6  push    rbp
0x14002c3f7  push    rsi
0x14002c3f8  push    rdi
0x14002c3f9  push    r12
0x14002c3fb  push    r14
0x14002c3fd  sub     rsp, 28h
0x14002c401  mov     rsi, [rcx+40h]
0x14002c405  mov     rdi, rcx
0x14002c408  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c40f  lea     r12, WPP_GLOBAL_Control
0x14002c416  cmp     rcx, r12
0x14002c419  jz      short loc_14002C43D
0x14002c41b  mov     eax, [rcx+2Ch]
0x14002c41e  test    al, 4
0x14002c420  jz      short loc_14002C43D
0x14002c422  cmp     byte ptr [rcx+29h], 5
0x14002c426  jb      short loc_14002C43D
0x14002c428  mov     rcx, [rcx+18h]
0x14002c42c  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14002c433  mov     edx, 3Dh ; '='
0x14002c438  call    WPP_SF_
0x14002c43d  lea     r14, WPP_MAIN_CB.DeviceExtension
0x14002c444  mov     rcx, r14; SpinLock
0x14002c447  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c44e  nop     dword ptr [rax+rax+00h]
0x14002c453  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002c45a  lea     rcx, WPP_MAIN_CB.Queue+8
0x14002c461  mov     byte ptr cs:WPP_MAIN_CB.DeviceType, al
0x14002c467  cmp     rbx, rcx
0x14002c46a  jz      short loc_14002C488
0x14002c46c  movzx   eax, word ptr [rdi+0D4h]
0x14002c473  cmp     [rbx+84h], ax
0x14002c47a  jz      loc_14002C50E
0x14002c480  mov     rbx, [rbx]
0x14002c483  cmp     rbx, rcx
0x14002c486  jnz     short loc_14002C473
0x14002c488  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c48f  cmp     rcx, r12
0x14002c492  jz      short loc_14002C4B6
0x14002c494  mov     eax, [rcx+2Ch]
0x14002c497  test    al, 4
0x14002c499  jz      short loc_14002C4B6
0x14002c49b  cmp     byte ptr [rcx+29h], 3
0x14002c49f  jb      short loc_14002C4B6
0x14002c4a1  mov     rcx, [rcx+18h]
0x14002c4a5  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14002c4ac  mov     edx, 3Eh ; '>'
0x14002c4b1  call    WPP_SF_
0x14002c4b6  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceType; NewIrql
0x14002c4bc  mov     rcx, r14; SpinLock
0x14002c4bf  call    cs:__imp_KeReleaseSpinLock
0x14002c4c6  nop     dword ptr [rax+rax+00h]
0x14002c4cb  mov     edi, 25Bh
0x14002c4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c4d7  cmp     rcx, r12
0x14002c4da  jz      short loc_14002C4FE
0x14002c4dc  mov     eax, [rcx+2Ch]
0x14002c4df  test    al, 4
0x14002c4e1  jz      short loc_14002C4FE
0x14002c4e3  cmp     byte ptr [rcx+29h], 5
0x14002c4e7  jb      short loc_14002C4FE
0x14002c4e9  mov     rcx, [rcx+18h]
0x14002c4ed  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14002c4f4  mov     edx, 3Fh ; '?'
0x14002c4f9  call    WPP_SF_
0x14002c4fe  mov     eax, edi
0x14002c500  add     rsp, 28h
0x14002c504  pop     r14
0x14002c506  pop     r12
0x14002c508  pop     rdi
0x14002c509  pop     rsi
0x14002c50a  pop     rbp
0x14002c50b  pop     rbx
0x14002c50c  retn
0x14002c50e  mov     eax, [rbx+78h]
0x14002c511  lea     rbp, [rbx+0A0h]
0x14002c518  mov     [rdi+0F4h], eax
0x14002c51e  mov     rcx, rbp; SpinLock
0x14002c521  movzx   eax, word ptr [rbx+7Ch]
0x14002c525  mov     [rdi+0F8h], ax
0x14002c52c  mov     al, [rsi+21h]
0x14002c52f  mov     [rdi+0F7h], al
0x14002c535  mov     al, [rsi+20h]
0x14002c538  mov     [rdi+0F8h], al
0x14002c53e  mov     al, [rdi+30h]
0x14002c541  mov     [rdi+0F9h], al
0x14002c547  xor     eax, eax
0x14002c549  mov     [rdi+0FAh], eax
0x14002c54f  mov     [rdi+0FEh], ax
0x14002c556  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c55d  nop     dword ptr [rax+rax+00h]
0x14002c562  mov     [rbx+0A8h], al
0x14002c568  lea     rax, [rbx+48h]
0x14002c56c  mov     rcx, [rax+8]
0x14002c570  cmp     [rcx], rax
0x14002c573  jnz     loc_14002C67D
0x14002c579  lea     rsi, [rdi+58h]
0x14002c57d  mov     [rsi], rax
0x14002c580  mov     [rsi+8], rcx
0x14002c584  mov     [rcx], rsi
0x14002c587  mov     [rax+8], rsi
0x14002c58b  mov     [rdi+38h], rbx
0x14002c58f  lock inc dword ptr [rbx+10h]
0x14002c593  mov     dl, [rbx+0A8h]; NewIrql
0x14002c599  mov     rcx, rbp; SpinLock
0x14002c59c  call    cs:__imp_KeReleaseSpinLock
0x14002c5a3  nop     dword ptr [rax+rax+00h]
0x14002c5a8  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceType; NewIrql
0x14002c5ae  mov     rcx, r14; SpinLock
0x14002c5b1  call    cs:__imp_KeReleaseSpinLock
0x14002c5b8  nop     dword ptr [rax+rax+00h]
0x14002c5bd  mov     dl, 1
0x14002c5bf  mov     rcx, rdi
0x14002c5c2  call    DoLineUpToProtocol
0x14002c5c7  mov     edi, eax
0x14002c5c9  test    eax, eax
0x14002c5cb  jz      loc_14002C4D0
0x14002c5d1  mov     rcx, r14; SpinLock
0x14002c5d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c5db  nop     dword ptr [rax+rax+00h]
0x14002c5e0  mov     rcx, rbp; SpinLock
0x14002c5e3  mov     byte ptr cs:WPP_MAIN_CB.DeviceType, al
0x14002c5e9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c5f0  nop     dword ptr [rax+rax+00h]
0x14002c5f5  mov     [rbx+0A8h], al
0x14002c5fb  mov     r8, [rsi]
0x14002c5fe  cmp     [r8+8], rsi
0x14002c602  jnz     short loc_14002C67D
0x14002c604  mov     rax, [rsi+8]
0x14002c608  cmp     [rax], rsi
0x14002c60b  jnz     short loc_14002C67D
0x14002c60d  mov     [rax], r8
0x14002c610  mov     [r8+8], rax
0x14002c614  mov     eax, [rbx+58h]
0x14002c617  test    al, 8
0x14002c619  jz      short loc_14002C635
0x14002c61b  xor     r8d, r8d; Wait
0x14002c61e  lea     rcx, [rbx+88h]; Event
0x14002c625  lea     edx, [r8+1]; Increment
0x14002c629  call    cs:__imp_KeSetEvent
0x14002c630  nop     dword ptr [rax+rax+00h]
0x14002c635  mov     dl, [rbx+0A8h]; NewIrql
0x14002c63b  mov     rcx, rbp; SpinLock
0x14002c63e  call    cs:__imp_KeReleaseSpinLock
0x14002c645  nop     dword ptr [rax+rax+00h]
0x14002c64a  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceType; NewIrql
0x14002c650  mov     rcx, r14; SpinLock
0x14002c653  call    cs:__imp_KeReleaseSpinLock
0x14002c65a  nop     dword ptr [rax+rax+00h]
0x14002c65f  or      eax, 0FFFFFFFFh
0x14002c662  lock xadd [rbx+10h], eax
0x14002c667  cmp     eax, 1
0x14002c66a  jnz     loc_14002C4D0
0x14002c670  mov     rcx, rbx; P
0x14002c673  call    NdisWanFreeMiniportCB
0x14002c678  jmp     loc_14002C4D0
0x14002c67d  mov     ecx, 3
0x14002c682  int     29h; Win8: RtlFailFast(ecx)
```
