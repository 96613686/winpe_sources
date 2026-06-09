# WaitForOnlinesToComplete

- ea: `0x140002afc`
- end: `0x140002bba`
- name: `WaitForOnlinesToComplete`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c730`

## callees

- `0x140002afc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b9d`
- `ntoskrnl!KeInitializeEvent` at `0x140002b1d`
- `ntoskrnl!KeInitializeEvent` at `0x140002b1d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002b77`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002b77`

## pseudocode

```c
void __fastcall WaitForOnlinesToComplete(__int64 a1)
{
  void *v1; // rsi
  KIRQL v3; // dl
  KSPIN_LOCK *v4; // rcx
  int v5; // eax
  KIRQL v6; // al

  v1 = (void *)(a1 + 312);
  KeInitializeEvent((PRKEVENT)(a1 + 312), NotificationEvent, 0);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 256));
  v4 = (KSPIN_LOCK *)(a1 + 256);
  v5 = *(_DWORD *)(a1 + 308);
  if ( v5 != 1 )
  {
    *(_DWORD *)(a1 + 308) = v5 - 1;
    KeReleaseSpinLock(v4, v3);
    KeWaitForSingleObject(v1, Executive, 0, 0, 0);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 256));
    ++*(_DWORD *)(a1 + 308);
    v4 = (KSPIN_LOCK *)(a1 + 256);
    v3 = v6;
  }
  KeReleaseSpinLock(v4, v3);
}

```

## disassembly

```asm
0x140002afc  mov     [rsp+arg_0], rbx
0x140002b01  mov     [rsp+arg_8], rsi
0x140002b06  push    rdi
0x140002b07  sub     rsp, 30h
0x140002b0b  lea     rsi, [rcx+138h]
0x140002b12  mov     rbx, rcx
0x140002b15  mov     rcx, rsi; Event
0x140002b18  xor     r8d, r8d; State
0x140002b1b  xor     edx, edx; Type
0x140002b1d  call    cs:__imp_KeInitializeEvent
0x140002b24  nop     dword ptr [rax+rax+00h]
0x140002b29  lea     rdi, [rbx+100h]
0x140002b30  mov     rcx, rdi; SpinLock
0x140002b33  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b3a  nop     dword ptr [rax+rax+00h]
0x140002b3f  mov     dl, al; NewIrql
0x140002b41  mov     rcx, rdi; SpinLock
0x140002b44  mov     eax, [rbx+134h]
0x140002b4a  cmp     eax, 1
0x140002b4d  jz      short loc_140002B9D
0x140002b4f  dec     eax
0x140002b51  mov     [rbx+134h], eax
0x140002b57  call    cs:__imp_KeReleaseSpinLock
0x140002b5e  nop     dword ptr [rax+rax+00h]
0x140002b63  xor     r9d, r9d; Alertable
0x140002b66  mov     [rsp+38h+Timeout], 0; Timeout
0x140002b6f  xor     r8d, r8d; WaitMode
0x140002b72  xor     edx, edx; WaitReason
0x140002b74  mov     rcx, rsi; Object
0x140002b77  call    cs:__imp_KeWaitForSingleObject
0x140002b7e  nop     dword ptr [rax+rax+00h]
0x140002b83  mov     rcx, rdi; SpinLock
0x140002b86  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b8d  nop     dword ptr [rax+rax+00h]
0x140002b92  inc     dword ptr [rbx+134h]
0x140002b98  mov     rcx, rdi; SpinLock
0x140002b9b  mov     dl, al; NewIrql
0x140002b9d  call    cs:__imp_KeReleaseSpinLock
0x140002ba4  nop     dword ptr [rax+rax+00h]
0x140002ba9  mov     rbx, [rsp+38h+arg_0]
0x140002bae  mov     rsi, [rsp+38h+arg_8]
0x140002bb3  add     rsp, 30h
0x140002bb7  pop     rdi
0x140002bb8  retn
```
