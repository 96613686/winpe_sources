# NetioTimerWorkItemShutdown

- ea: `0x14005c1a0`
- end: `0x14005c297`
- name: `NetioTimerWorkItemShutdown`
- size: `247`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14006ab9c`

## callees

- `0x14005c1a0`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14005c265`
- `ntoskrnl!ExDeleteTimer` at `0x14005c265`
- `ntoskrnl!ExCancelTimer` at `0x14005c1e2`
- `ntoskrnl!ExCancelTimer` at `0x14005c1e2`
- `ntoskrnl!KeInitializeEvent` at `0x14005c1fc`
- `ntoskrnl!KeInitializeEvent` at `0x14005c1fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c239`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c239`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c27a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005c217`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005c24d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005c217`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005c24d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005c1c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005c1c1`

## pseudocode

```c
void __fastcall NetioTimerWorkItemShutdown(PKSPIN_LOCK SpinLock)
{
  KIRQL v2; // al
  KIRQL v3; // si
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  v2 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  *((_DWORD *)SpinLock + 13) |= 2u;
  v3 = v2;
  if ( (*((_DWORD *)SpinLock + 13) & 1) == 0 || (unsigned __int8)ExCancelTimer(SpinLock[2], 0) )
  {
    KeReleaseSpinLock(SpinLock, v3);
  }
  else
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    SpinLock[3] = (KSPIN_LOCK)&Event;
    KeReleaseSpinLock(SpinLock, v3);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  ExDeleteTimer(SpinLock[2], 0, 0, 0);
  ExFreePoolWithTag((PVOID)SpinLock[1], 0x5157654Eu);
}

```

## disassembly

```asm
0x14005c1a0  mov     [rsp+arg_0], rbx
0x14005c1a5  mov     [rsp+arg_8], rsi
0x14005c1aa  push    rdi
0x14005c1ab  sub     rsp, 50h
0x14005c1af  xorps   xmm0, xmm0
0x14005c1b2  xor     eax, eax
0x14005c1b4  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14005c1b9  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x14005c1be  mov     rdi, rcx
0x14005c1c1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005c1c8  nop     dword ptr [rax+rax+00h]
0x14005c1cd  or      dword ptr [rdi+34h], 2
0x14005c1d1  mov     sil, al
0x14005c1d4  mov     edx, [rdi+34h]
0x14005c1d7  test    dl, 1
0x14005c1da  jz      short loc_14005C247
0x14005c1dc  mov     rcx, [rdi+10h]
0x14005c1e0  xor     edx, edx
0x14005c1e2  call    cs:__imp_ExCancelTimer
0x14005c1e9  nop     dword ptr [rax+rax+00h]
0x14005c1ee  test    al, al
0x14005c1f0  jnz     short loc_14005C247
0x14005c1f2  xor     r8d, r8d; State
0x14005c1f5  lea     rcx, [rsp+58h+Event]; Event
0x14005c1fa  xor     edx, edx; Type
0x14005c1fc  call    cs:__imp_KeInitializeEvent
0x14005c203  nop     dword ptr [rax+rax+00h]
0x14005c208  lea     rax, [rsp+58h+Event]
0x14005c20d  mov     dl, sil; NewIrql
0x14005c210  mov     rcx, rdi; SpinLock
0x14005c213  mov     [rdi+18h], rax
0x14005c217  call    cs:__imp_KeReleaseSpinLock
0x14005c21e  nop     dword ptr [rax+rax+00h]
0x14005c223  xor     r9d, r9d; Alertable
0x14005c226  mov     [rsp+58h+Timeout], 0; Timeout
0x14005c22f  xor     r8d, r8d; WaitMode
0x14005c232  lea     rcx, [rsp+58h+Event]; Object
0x14005c237  xor     edx, edx; WaitReason
0x14005c239  call    cs:__imp_KeWaitForSingleObject
0x14005c240  nop     dword ptr [rax+rax+00h]
0x14005c245  jmp     short loc_14005C259
0x14005c247  mov     dl, sil; NewIrql
0x14005c24a  mov     rcx, rdi; SpinLock
0x14005c24d  call    cs:__imp_KeReleaseSpinLock
0x14005c254  nop     dword ptr [rax+rax+00h]
0x14005c259  mov     rcx, [rdi+10h]
0x14005c25d  xor     r9d, r9d
0x14005c260  xor     r8d, r8d
0x14005c263  xor     edx, edx
0x14005c265  call    cs:__imp_ExDeleteTimer
0x14005c26c  nop     dword ptr [rax+rax+00h]
0x14005c271  mov     rcx, [rdi+8]; P
0x14005c275  mov     edx, 5157654Eh; Tag
0x14005c27a  call    cs:__imp_ExFreePoolWithTag
0x14005c281  nop     dword ptr [rax+rax+00h]
0x14005c286  mov     rbx, [rsp+58h+arg_0]
0x14005c28b  mov     rsi, [rsp+58h+arg_8]
0x14005c290  add     rsp, 50h
0x14005c294  pop     rdi
0x14005c295  retn
```
