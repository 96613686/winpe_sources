# lldpQueueChangeNotificationEx

- ea: `0x140003d80`
- end: `0x140003e29`
- name: `lldpQueueChangeNotificationEx`
- size: `169`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002fe0`
- `0x140004720`
- `0x1400049a0`
- `0x140006298`
- `0x140010150`
- `0x140010560`
- `0x140010aec`
- `0x140010c40`
- `0x1400114d0`
- `0x140011aa0`
- `0x140011e30`
- `0x140012640`

## callees

- `0x140003d80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003db6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003db6`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140003e18`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140003e18`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003de3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003de3`

## pseudocode

```c
void __fastcall lldpQueueChangeNotificationEx(PVOID Context, __int64 a2, unsigned int a3)
{
  __int64 i; // rax

  if ( a2 )
  {
    _InterlockedOr((volatile signed __int32 *)(a2 + 32), a3);
  }
  else
  {
    if ( !*((_QWORD *)Context + 11) )
      return;
    *((_BYTE *)Context + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 9);
    for ( i = *((_QWORD *)Context + 11); i; i = *(_QWORD *)(i + 8) )
      _InterlockedOr((volatile signed __int32 *)(i + 32), a3);
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 9, *((_BYTE *)Context + 80));
  }
  if ( !_InterlockedExchange((volatile __int32 *)Context + 24, 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)Context + 12);
    IoQueueWorkItemEx(*((PIO_WORKITEM *)Context + 13), lldpDeliverChangeNotifications, DelayedWorkQueue, Context);
  }
}

```

## disassembly

```asm
0x140003d80  mov     [rsp+arg_8], rbx
0x140003d85  push    rdi
0x140003d86  sub     rsp, 20h
0x140003d8a  mov     edi, r8d
0x140003d8d  mov     rbx, rcx
0x140003d90  test    rdx, rdx
0x140003d93  jnz     short loc_140003DA7
0x140003d95  cmp     [rcx+58h], rdx
0x140003d99  jnz     short loc_140003DAD
0x140003d9b  mov     rbx, [rsp+28h+arg_8]
0x140003da0  add     rsp, 20h
0x140003da4  pop     rdi
0x140003da5  retn
0x140003da7  lock or [rdx+20h], edi
0x140003dab  jmp     short loc_140003DF4
0x140003dad  add     rcx, 48h ; 'H'; SpinLock
0x140003db1  mov     [rsp+28h+arg_0], rsi
0x140003db6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003dbd  nop     dword ptr [rax+rax+00h]
0x140003dc2  mov     [rbx+50h], al
0x140003dc5  mov     rax, [rbx+58h]
0x140003dc9  test    rax, rax
0x140003dcc  jz      short loc_140003DDB
0x140003dce  lock or [rax+20h], edi
0x140003dd2  mov     rax, [rax+8]
0x140003dd6  test    rax, rax
0x140003dd9  jnz     short loc_140003DCE
0x140003ddb  movzx   edx, byte ptr [rbx+50h]; NewIrql
0x140003ddf  lea     rcx, [rbx+48h]; SpinLock
0x140003de3  call    cs:__imp_KeReleaseSpinLock
0x140003dea  nop     dword ptr [rax+rax+00h]
0x140003def  mov     rsi, [rsp+28h+arg_0]
0x140003df4  mov     eax, 1
0x140003df9  xchg    eax, [rbx+60h]
0x140003dfc  test    eax, eax
0x140003dfe  jnz     short loc_140003D9B
0x140003e00  lock inc dword ptr [rbx+30h]
0x140003e04  mov     rcx, [rbx+68h]; IoWorkItem
0x140003e08  lea     rdx, lldpDeliverChangeNotifications; WorkerRoutine
0x140003e0f  mov     r9, rbx; Context
0x140003e12  mov     r8d, 1; QueueType
0x140003e18  call    cs:__imp_IoQueueWorkItemEx
0x140003e1f  nop     dword ptr [rax+rax+00h]
0x140003e24  jmp     loc_140003D9B
```
