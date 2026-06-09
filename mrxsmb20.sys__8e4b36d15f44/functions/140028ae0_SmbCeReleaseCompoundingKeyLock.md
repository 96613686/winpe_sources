# SmbCeReleaseCompoundingKeyLock

- ea: `0x140028ae0`
- end: `0x140028b13`
- name: `SmbCeReleaseCompoundingKeyLock`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140025df0`
- `0x140033a30`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140028af1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028af1`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140028b00`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140028b00`

## pseudocode

```c
__int64 __fastcall SmbCeReleaseCompoundingKeyLock(__int64 a1)
{
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  return SmbCseDereferenceCompoundingKey(a1);
}

```

## disassembly

```asm
0x140028ae0  push    rbx
0x140028ae2  sub     rsp, 20h
0x140028ae6  mov     rbx, rcx
0x140028ae9  add     rcx, 8; SpinLock
0x140028aed  movzx   edx, byte ptr [rbx+10h]; NewIrql
0x140028af1  call    cs:__imp_KeReleaseSpinLock
0x140028af8  nop     dword ptr [rax+rax+00h]
0x140028afd  mov     rcx, rbx
0x140028b00  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140028b07  nop     dword ptr [rax+rax+00h]
0x140028b0c  add     rsp, 20h
0x140028b10  pop     rbx
0x140028b11  retn
```
