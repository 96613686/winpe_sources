# BrbDenyConnectComplete

- ea: `0x14000d5f0`
- end: `0x14000d64d`
- name: `BrbDenyConnectComplete`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d630`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d630`
- `ntoskrnl!IoFreeIrp` at `0x14000d613`
- `ntoskrnl!IoFreeIrp` at `0x14000d613`

## pseudocode

```c
__int64 __fastcall BrbDenyConnectComplete(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a3 + 72);
  (*(void (__fastcall **)(__int64))(v3 + 320))(a3);
  IoFreeIrp(a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 40), &BrbDenyConnectComplete, 0x20u);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000d5f0  mov     [rsp+arg_0], rbx
0x14000d5f5  push    rdi
0x14000d5f6  sub     rsp, 20h
0x14000d5fa  mov     rbx, [r8+48h]
0x14000d5fe  mov     rcx, r8
0x14000d601  mov     rdi, rdx
0x14000d604  mov     rax, [rbx+140h]
0x14000d60b  call    _guard_dispatch_icall
0x14000d610  mov     rcx, rdi; Irp
0x14000d613  call    cs:__imp_IoFreeIrp
0x14000d61a  nop     dword ptr [rax+rax+00h]
0x14000d61f  lea     rcx, [rbx+28h]; RemoveLock
0x14000d623  mov     r8d, 20h ; ' '; RemlockSize
0x14000d629  lea     rdx, BrbDenyConnectComplete; Tag
0x14000d630  call    cs:__imp_IoReleaseRemoveLockEx
0x14000d637  nop     dword ptr [rax+rax+00h]
0x14000d63c  mov     rbx, [rsp+28h+arg_0]
0x14000d641  mov     eax, 0C0000016h
0x14000d646  add     rsp, 20h
0x14000d64a  pop     rdi
0x14000d64b  retn
```
