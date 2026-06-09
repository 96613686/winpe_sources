# MRxDAVUpdateNetRootState

- ea: `0x14001ac00`
- end: `0x14001ac14`
- name: `MRxDAVUpdateNetRootState`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall MRxDAVUpdateNetRootState(__int64 a1)
{
  __int64 result; // rax

  result = 0;
  *(_BYTE *)(a1 + 76) = *(_QWORD *)(a1 + 40) == 0 ? 3 : 0;
  return result;
}

```

## disassembly

```asm
0x14001ac00  mov     rax, [rcx+28h]
0x14001ac04  neg     rax
0x14001ac07  sbb     dl, dl
0x14001ac09  xor     eax, eax
0x14001ac0b  not     dl
0x14001ac0d  and     dl, 3
0x14001ac10  mov     [rcx+4Ch], dl
0x14001ac13  retn
```
