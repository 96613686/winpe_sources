# XdrNextMod4Boundary

- ea: `0x140014c30`
- end: `0x140014c5c`
- name: `XdrNextMod4Boundary`
- size: `44`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000adb0`
- `0x14000d9f0`
- `0x140014bdc`
- `0x140014c64`
- `0x140014d04`
- `0x140014d98`
- `0x140014e1c`
- `0x140014ff4`
- `0x14002372c`
- `0x140023dd0`
- `0x140024720`
- `0x140038a68`

## callees

- `0x140014c30`

## pseudocode

```c
__int64 __fastcall XdrNextMod4Boundary(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 72);
  if ( !v1 )
    return 0;
  result = ((unsigned __int8)*(_QWORD *)(v1 + 56) - (unsigned __int8)*(_QWORD *)(v1 + 64)) & 3;
  *(_QWORD *)(v1 + 64) += result;
  return result;
}

```

## disassembly

```asm
0x140014c30  mov     rdx, [rcx+48h]
0x140014c34  test    rdx, rdx
0x140014c37  jnz     short loc_140014C49
0x140014c39  xor     eax, eax
0x140014c3b  xor     ecx, ecx
0x140014c3d  sub     rax, rcx
0x140014c40  and     eax, 3
0x140014c43  add     [rdx+40h], rax
0x140014c47  retn
0x140014c49  mov     rax, [rdx+38h]
0x140014c4d  mov     rcx, [rdx+40h]
0x140014c51  sub     rax, rcx
0x140014c54  and     eax, 3
0x140014c57  add     [rdx+40h], rax
0x140014c5b  retn
```
