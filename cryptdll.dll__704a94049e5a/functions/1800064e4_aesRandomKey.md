# aesRandomKey

- ea: `0x1800064e4`
- end: `0x180006528`
- name: `aesRandomKey`
- size: `68`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ae0`
- `0x180005b20`

## callees

- `0x180005800`
- `0x1800064e4`
- `0x180008415`

## pseudocode

```c
__int64 __fastcall aesRandomKey(void *Src, int a2, void *a3, unsigned int a4)
{
  if ( !a2 )
    return (unsigned __int8)CDGenerateRandomBits() == 0 ? 0xC00000E5 : 0;
  if ( a2 != a4 )
    return 3221225659LL;
  memcpy_0(a3, Src, a4);
  return 0;
}

```

## disassembly

```asm
0x1800064e4  sub     rsp, 28h
0x1800064e8  mov     rax, r8
0x1800064eb  test    edx, edx
0x1800064ed  jnz     short loc_180006507
0x1800064ef  mov     edx, r9d
0x1800064f2  mov     rcx, rax
0x1800064f5  call    CDGenerateRandomBits
0x1800064fa  neg     al
0x1800064fc  sbb     eax, eax
0x1800064fe  not     eax
0x180006500  and     eax, 0C00000E5h
0x180006505  jmp     short loc_180006523
0x180006507  cmp     edx, r9d
0x18000650a  jnz     short loc_18000651E
0x18000650c  mov     rdx, rcx; Src
0x18000650f  mov     r8d, r9d; Size
0x180006512  mov     rcx, rax; void *
0x180006515  call    memcpy_0
0x18000651a  xor     eax, eax
0x18000651c  jmp     short loc_180006523
0x18000651e  mov     eax, 0C00000BBh
0x180006523  add     rsp, 28h
0x180006527  retn
```
