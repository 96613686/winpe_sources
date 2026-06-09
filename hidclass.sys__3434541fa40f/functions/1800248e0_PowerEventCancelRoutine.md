# PowerEventCancelRoutine

- ea: `0x1800248e0`
- end: `0x180024975`
- name: `PowerEventCancelRoutine`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18002491d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180024947`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180024947`
- `ntoskrnl!IofCompleteRequest` at `0x18002495f`
- `ntoskrnl!IofCompleteRequest` at `0x18002495f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024938`
- `ntoskrnl!KeReleaseSpinLock` at `0x180024938`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024911`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180024911`

## pseudocode

```c
void __fastcall PowerEventCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v3; // rdi
  KIRQL v4; // al

  v3 = 424LL * *(unsigned int *)(*(_QWORD *)(a1 + 64) + 44LL)
     + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 96LL) + 184LL);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 328));
  *(_QWORD *)(v3 + 320) = MmBadPointer;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 328), v4);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x1800248e0  push    rbx
0x1800248e2  push    rbp
0x1800248e3  push    rsi
0x1800248e4  push    rdi
0x1800248e5  sub     rsp, 28h
0x1800248e9  mov     r8, [rcx+40h]
0x1800248ed  mov     rbp, rdx
0x1800248f0  mov     eax, [r8+2Ch]
0x1800248f4  imul    rsi, rax, 1A8h
0x1800248fb  mov     rax, [r8+60h]
0x1800248ff  mov     rbx, [rax+0B8h]
0x180024906  lea     rdi, [rsi+rbx]
0x18002490a  lea     rcx, [rdi+148h]; SpinLock
0x180024911  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180024918  nop     dword ptr [rax+rax+00h]
0x18002491d  mov     r8, cs:MmBadPointer
0x180024924  lea     rcx, [rdi+148h]; SpinLock
0x18002492b  mov     dl, al; NewIrql
0x18002492d  mov     r9, [r8]
0x180024930  mov     [rsi+rbx+140h], r9
0x180024938  call    cs:__imp_KeReleaseSpinLock
0x18002493f  nop     dword ptr [rax+rax+00h]
0x180024944  mov     cl, [rbp+45h]; Irql
0x180024947  call    cs:__imp_IoReleaseCancelSpinLock
0x18002494e  nop     dword ptr [rax+rax+00h]
0x180024953  xor     edx, edx; PriorityBoost
0x180024955  mov     dword ptr [rbp+30h], 0C0000120h
0x18002495c  mov     rcx, rbp; Irp
0x18002495f  call    cs:__imp_IofCompleteRequest
0x180024966  nop     dword ptr [rax+rax+00h]
0x18002496b  add     rsp, 28h
0x18002496f  pop     rdi
0x180024970  pop     rsi
0x180024971  pop     rbp
0x180024972  pop     rbx
0x180024973  retn
```
