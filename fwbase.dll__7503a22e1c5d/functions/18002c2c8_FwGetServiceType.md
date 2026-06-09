# FwGetServiceType

- ea: `0x18002c2c8`
- end: `0x18002c2ff`
- name: `FwGetServiceType`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180012288`
- `0x18002c400`

## callees

- `0x18002c2c8`

## pseudocode

```c
__int64 __fastcall FwGetServiceType(int a1, __int16 a2)
{
  unsigned __int64 v2; // rax
  unsigned int v3; // r9d
  __int64 v4; // r8

  v2 = 0;
  v3 = 3;
  while ( v2 < 7 )
  {
    v4 = 4 * v2;
    if ( WORD2(qword_1800312B0[4 * v2]) == a2 && LODWORD(qword_1800312B0[v4 + 1]) == a1 )
      return LODWORD(qword_1800312B0[v4 + 2]);
    ++v2;
  }
  return v3;
}

```

## disassembly

```asm
0x18002c2c8  xor     eax, eax
0x18002c2ca  lea     r10, qword_1800312B0
0x18002c2d1  lea     r9d, [rax+3]
0x18002c2d5  cmp     rax, 7
0x18002c2d9  jnb     short loc_18002C2FB
0x18002c2db  mov     r8, rax
0x18002c2de  shl     r8, 5
0x18002c2e2  cmp     [r8+r10+4], dx
0x18002c2e8  jnz     short loc_18002C2F1
0x18002c2ea  cmp     [r8+r10+8], ecx
0x18002c2ef  jz      short loc_18002C2F6
0x18002c2f1  inc     rax
0x18002c2f4  jmp     short loc_18002C2D5
0x18002c2f6  mov     r9d, [r8+r10+10h]
0x18002c2fb  mov     eax, r9d
0x18002c2fe  retn
```
