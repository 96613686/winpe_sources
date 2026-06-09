# IsTapiLineValid

- ea: `0x1400112d8`
- end: `0x140011397`
- name: `IsTapiLineValid`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ad0`
- `0x140011850`
- `0x140012880`
- `0x140013610`
- `0x140013bc0`
- `0x140014ca0`

## callees

- `0x1400112d8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001135b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001135b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011348`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011348`
- `NDIS!NdisReleaseRWLock` at `0x140011373`
- `NDIS!NdisReleaseRWLock` at `0x140011373`
- `NDIS!NdisAcquireRWLockRead` at `0x140011309`
- `NDIS!NdisAcquireRWLockRead` at `0x140011309`

## pseudocode

```c
bool __fastcall IsTapiLineValid(int a1, struct _SINGLE_LIST_ENTRY **a2)
{
  __int64 v4; // r8
  struct _SINGLE_LIST_ENTRY *Next; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
  v4 = 0;
  if ( *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) )
  {
    while ( 1 )
    {
      Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next[v4].Next;
      if ( Next )
      {
        if ( LODWORD(Next[6].Next) == a1 )
          break;
      }
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) )
        goto LABEL_7;
    }
    *a2 = Next;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&Next[15]);
    ++LODWORD(Next[2].Next);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&Next[15]);
  }
LABEL_7:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
  return *a2 != 0;
}

```

## disassembly

```asm
0x1400112d8  mov     [rsp+arg_0], rbx
0x1400112dd  mov     [rsp+arg_10], rsi
0x1400112e2  push    rdi
0x1400112e3  sub     rsp, 20h
0x1400112e7  xor     eax, eax
0x1400112e9  mov     rsi, rdx
0x1400112ec  mov     [rdx], rax
0x1400112ef  mov     ebx, ecx
0x1400112f1  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x1400112f8  lea     rdx, [rsp+28h+LockState]; LockState
0x1400112fd  xor     r8d, r8d; Flags
0x140011300  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140011305  mov     [rsp+28h+LockState.Flags], al
0x140011309  call    cs:__imp_NdisAcquireRWLockRead
0x140011310  nop     dword ptr [rax+rax+00h]
0x140011315  mov     edx, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x14001131b  xor     r8d, r8d
0x14001131e  test    edx, edx
0x140011320  jz      short loc_140011367
0x140011322  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140011329  mov     rdi, [rax+r8*8]
0x14001132d  test    rdi, rdi
0x140011330  jz      short loc_140011337
0x140011332  cmp     [rdi+30h], ebx
0x140011335  jz      short loc_140011341
0x140011337  inc     r8d
0x14001133a  cmp     r8d, edx
0x14001133d  jb      short loc_140011322
0x14001133f  jmp     short loc_140011367
0x140011341  lea     rcx, [rdi+78h]; SpinLock
0x140011345  mov     [rsi], rdi
0x140011348  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001134f  nop     dword ptr [rax+rax+00h]
0x140011354  inc     dword ptr [rdi+10h]
0x140011357  lea     rcx, [rdi+78h]; SpinLock
0x14001135b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011362  nop     dword ptr [rax+rax+00h]
0x140011367  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x14001136e  lea     rdx, [rsp+28h+LockState]; LockState
0x140011373  call    cs:__imp_NdisReleaseRWLock
0x14001137a  nop     dword ptr [rax+rax+00h]
0x14001137f  cmp     qword ptr [rsi], 0
0x140011383  mov     rbx, [rsp+28h+arg_0]
0x140011388  mov     rsi, [rsp+28h+arg_10]
0x14001138d  setnz   al
0x140011390  add     rsp, 20h
0x140011394  pop     rdi
0x140011395  retn
```
