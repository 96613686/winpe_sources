# CdAddToWorkque

- ea: `0x140002b10`
- end: `0x140002bf2`
- name: `CdAddToWorkque`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140017ab8`
- `0x14001a8c4`
- `0x14001a900`

## callees

- `0x140002b10`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b42`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b91`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002bad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b91`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002bad`
- `ntoskrnl!ExQueueWorkItem` at `0x140002bd5`
- `ntoskrnl!ExQueueWorkItem` at `0x140002bd5`

## pseudocode

```c
void __fastcall CdAddToWorkque(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rbx
  KIRQL v5; // r8
  unsigned int v6; // eax
  _QWORD *v7; // rdx

  v2 = *(_QWORD *)(a2 + 184);
  if ( !*(_QWORD *)(v2 + 48) )
    goto LABEL_7;
  v4 = *(_QWORD *)(v2 + 40);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 360));
  v6 = *(_DWORD *)(v4 + 336);
  if ( v6 <= 2 )
  {
    *(_DWORD *)(v4 + 336) = v6 + 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 360), v5);
LABEL_7:
    *(_QWORD *)(a1 + 104) = a1;
    *(_QWORD *)(a1 + 96) = CdFspDispatch;
    *(_QWORD *)(a1 + 80) = 0;
    ExQueueWorkItem((PWORK_QUEUE_ITEM)(a1 + 80), CriticalWorkQueue);
    return;
  }
  v7 = *(_QWORD **)(v4 + 352);
  if ( *v7 != v4 + 344 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 80) = v4 + 344;
  *(_QWORD *)(a1 + 88) = v7;
  *v7 = a1 + 80;
  *(_QWORD *)(v4 + 352) = a1 + 80;
  ++*(_DWORD *)(v4 + 340);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 360), v5);
}

```

## disassembly

```asm
0x140002b10  mov     [rsp+arg_0], rbx
0x140002b15  mov     [rsp+arg_8], rsi
0x140002b1a  push    rdi
0x140002b1b  sub     rsp, 20h
0x140002b1f  mov     rbx, [rdx+0B8h]
0x140002b26  mov     rdi, rcx
0x140002b29  cmp     qword ptr [rbx+30h], 0
0x140002b2e  jz      loc_140002BB9
0x140002b34  mov     rbx, [rbx+28h]
0x140002b38  lea     rsi, [rbx+168h]
0x140002b3f  mov     rcx, rsi; SpinLock
0x140002b42  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b49  nop     dword ptr [rax+rax+00h]
0x140002b4e  mov     r8b, al
0x140002b51  mov     eax, [rbx+150h]
0x140002b57  cmp     eax, 2
0x140002b5a  jbe     short loc_140002B9F
0x140002b5c  lea     rcx, [rbx+158h]
0x140002b63  mov     rdx, [rcx+8]
0x140002b67  cmp     [rdx], rcx
0x140002b6a  jz      short loc_140002B73
0x140002b6c  mov     ecx, 3
0x140002b71  int     29h; Win8: RtlFailFast(ecx)
0x140002b73  lea     rax, [rdi+50h]
0x140002b77  mov     [rax], rcx
0x140002b7a  mov     [rax+8], rdx
0x140002b7e  mov     [rdx], rax
0x140002b81  mov     dl, r8b; NewIrql
0x140002b84  mov     [rcx+8], rax
0x140002b88  mov     rcx, rsi; SpinLock
0x140002b8b  inc     dword ptr [rbx+154h]
0x140002b91  call    cs:__imp_KeReleaseSpinLock
0x140002b98  nop     dword ptr [rax+rax+00h]
0x140002b9d  jmp     short loc_140002BE1
0x140002b9f  inc     eax
0x140002ba1  mov     dl, r8b; NewIrql
0x140002ba4  mov     rcx, rsi; SpinLock
0x140002ba7  mov     [rbx+150h], eax
0x140002bad  call    cs:__imp_KeReleaseSpinLock
0x140002bb4  nop     dword ptr [rax+rax+00h]
0x140002bb9  lea     rcx, [rdi+50h]; WorkItem
0x140002bbd  xor     edx, edx; QueueType
0x140002bbf  lea     rax, CdFspDispatch
0x140002bc6  mov     [rcx+18h], rdi
0x140002bca  mov     [rcx+10h], rax
0x140002bce  mov     qword ptr [rcx], 0
0x140002bd5  call    cs:__imp_ExQueueWorkItem
0x140002bdc  nop     dword ptr [rax+rax+00h]
0x140002be1  mov     rbx, [rsp+28h+arg_0]
0x140002be6  mov     rsi, [rsp+28h+arg_8]
0x140002beb  add     rsp, 20h
0x140002bef  pop     rdi
0x140002bf0  retn
```
