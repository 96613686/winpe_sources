# _tlgKeywordOn

- ea: `0x1400012dc`
- end: `0x14000130a`
- name: `_tlgKeywordOn`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000237c`
- `0x14000244c`
- `0x140002548`
- `0x140003fec`

## callees

- `0x1400012dc`

## pseudocode

```c
bool tlgKeywordOn()
{
  return (qword_14000A010 & 0x400000000000LL) != 0 && (qword_14000A018 & 0x400000000000LL) == qword_14000A018;
}

```

## disassembly

```asm
0x1400012dc  mov     rcx, cs:qword_14000A018
0x1400012e3  mov     rdx, 400000000000h
0x1400012ed  mov     rax, cs:qword_14000A010
0x1400012f4  test    rdx, rax
0x1400012f7  jz      short loc_140001307
0x1400012f9  mov     rax, rcx
0x1400012fc  and     rax, rdx
0x1400012ff  cmp     rax, rcx
0x140001302  jnz     short loc_140001307
0x140001304  mov     al, 1
0x140001306  retn
0x140001307  xor     al, al
0x140001309  retn
```
