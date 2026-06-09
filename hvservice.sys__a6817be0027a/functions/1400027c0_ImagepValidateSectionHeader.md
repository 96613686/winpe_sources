# ImagepValidateSectionHeader

- ea: `0x1400027c0`
- end: `0x1400027da`
- name: `ImagepValidateSectionHeader`
- size: `26`
- prototype: `bool __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002534`
- `0x140002654`

## callees

- `0x1400027c0`

## pseudocode

```c
bool __fastcall ImagepValidateSectionHeader(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // r8

  v2 = *(unsigned int *)(a1 + 20);
  return v2 < a2 && v2 + *(unsigned int *)(a1 + 16) <= a2;
}

```

## disassembly

```asm
0x1400027c0  mov     r8d, [rcx+14h]
0x1400027c4  cmp     r8, rdx
0x1400027c7  jnb     short loc_1400027D7
0x1400027c9  mov     eax, [rcx+10h]
0x1400027cc  add     rax, r8
0x1400027cf  cmp     rax, rdx
0x1400027d2  setbe   al
0x1400027d5  retn
0x1400027d7  xor     al, al
0x1400027d9  retn
```
