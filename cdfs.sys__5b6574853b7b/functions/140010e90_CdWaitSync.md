# CdWaitSync

- ea: `0x140010e90`
- end: `0x140010ed9`
- name: `CdWaitSync`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f27c`
- `0x14000f618`
- `0x14001aa78`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140010eb2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010eb2`
- `ntoskrnl!KeClearEvent` at `0x140010ec6`
- `ntoskrnl!KeClearEvent` at `0x140010ec6`

## pseudocode

```c
void __fastcall CdWaitSync(__int64 a1)
{
  KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 48) + 24LL), Executive, 0, 0, 0);
  KeClearEvent((PRKEVENT)(*(_QWORD *)(a1 + 48) + 24LL));
}

```

## disassembly

```asm
0x140010e90  push    rbx
0x140010e92  sub     rsp, 30h
0x140010e96  mov     rbx, rcx
0x140010e99  mov     [rsp+38h+Timeout], 0; Timeout
0x140010ea2  mov     rcx, [rcx+30h]
0x140010ea6  xor     r9d, r9d; Alertable
0x140010ea9  add     rcx, 18h; Object
0x140010ead  xor     r8d, r8d; WaitMode
0x140010eb0  xor     edx, edx; WaitReason
0x140010eb2  call    cs:__imp_KeWaitForSingleObject
0x140010eb9  nop     dword ptr [rax+rax+00h]
0x140010ebe  mov     rcx, [rbx+30h]
0x140010ec2  add     rcx, 18h; Event
0x140010ec6  call    cs:__imp_KeClearEvent
0x140010ecd  nop     dword ptr [rax+rax+00h]
0x140010ed2  add     rsp, 30h
0x140010ed6  pop     rbx
0x140010ed7  retn
```
