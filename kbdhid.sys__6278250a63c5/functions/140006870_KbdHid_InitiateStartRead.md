# KbdHid_InitiateStartRead

- ea: `0x140006870`
- end: `0x1400068b4`
- name: `KbdHid_InitiateStartRead`
- size: `68`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001a00`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006899`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006899`

## pseudocode

```c
void __fastcall KbdHid_InitiateStartRead(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeferredContext + 152), *((PVOID *)DeferredContext + 13), File, 1u, 0x20u);
  KbdHid_StartRead(DeferredContext);
}

```

## disassembly

```asm
0x140006870  push    rbx
0x140006872  sub     rsp, 30h
0x140006876  mov     rbx, rdx
0x140006879  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x140006881  lea     rcx, [rdx+98h]; RemoveLock
0x140006888  mov     r9d, 1; Line
0x14000688e  mov     rdx, [rdx+68h]; Tag
0x140006892  lea     r8, File; File
0x140006899  call    cs:__imp_IoAcquireRemoveLockEx
0x1400068a0  nop     dword ptr [rax+rax+00h]
0x1400068a5  mov     rcx, rbx; Context
0x1400068a8  call    KbdHid_StartRead
0x1400068ad  add     rsp, 30h
0x1400068b1  pop     rbx
0x1400068b2  retn
```
