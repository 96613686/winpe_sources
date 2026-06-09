# SmbCeAcquireCompoundingKeyLock

- ea: `0x140028b20`
- end: `0x140028b4f`
- name: `SmbCeAcquireCompoundingKeyLock`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140025df0`
- `0x140033a30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028b39`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028b39`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140028b29`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140028b29`

## pseudocode

```c
KIRQL __fastcall SmbCeAcquireCompoundingKeyLock(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL result; // al

  SmbCseReferenceCompoundingKey(a1, a2, a3);
  result = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  *(_BYTE *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x140028b20  push    rbx
0x140028b22  sub     rsp, 20h
0x140028b26  mov     rbx, rcx
0x140028b29  call    cs:__imp_SmbCseReferenceCompoundingKey
0x140028b30  nop     dword ptr [rax+rax+00h]
0x140028b35  lea     rcx, [rbx+8]; SpinLock
0x140028b39  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028b40  nop     dword ptr [rax+rax+00h]
0x140028b45  mov     [rbx+10h], al
0x140028b48  add     rsp, 20h
0x140028b4c  pop     rbx
0x140028b4d  retn
```
