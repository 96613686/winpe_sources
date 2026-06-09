# memmove_s

- ea: `0x1400062a4`
- end: `0x1400062ff`
- name: `memmove_s`
- size: `91`
- prototype: `errno_t __cdecl(void *, rsize_t DstSize, const void *Src, rsize_t MaxCount)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400052d0`

## callees

- `0x1400062a4`
- `0x140006e50`
- `0x1400102c0`

## pseudocode

```c
errno_t __cdecl memmove_s(void *a1, rsize_t DstSize, const void *Src, rsize_t MaxCount)
{
  if ( !MaxCount )
    return 0;
  if ( !a1 || !Src )
    return 22;
  if ( DstSize >= MaxCount )
  {
    memmove(a1, Src, MaxCount);
    return 0;
  }
  return 34;
}

```

## disassembly

```asm
0x1400062a4  push    rbx
0x1400062a6  sub     rsp, 30h
0x1400062aa  mov     rax, r8
0x1400062ad  test    r9, r9
0x1400062b0  jnz     short loc_1400062B6
0x1400062b2  xor     eax, eax
0x1400062b4  jmp     short loc_1400062F8
0x1400062b6  test    rcx, rcx
0x1400062b9  jz      short loc_1400062D9
0x1400062bb  test    rax, rax
0x1400062be  jz      short loc_1400062D9
0x1400062c0  cmp     rdx, r9
0x1400062c3  jnb     short loc_1400062CC
0x1400062c5  mov     ebx, 22h ; '"'
0x1400062ca  jmp     short loc_1400062DE
0x1400062cc  mov     r8, r9; Size
0x1400062cf  mov     rdx, rax; Src
0x1400062d2  call    memmove
0x1400062d7  jmp     short loc_1400062B2
0x1400062d9  mov     ebx, 16h
0x1400062de  xor     r9d, r9d
0x1400062e1  mov     [rsp+38h+var_18], 0
0x1400062ea  xor     r8d, r8d
0x1400062ed  xor     edx, edx
0x1400062ef  xor     ecx, ecx
0x1400062f1  call    _guard_check_icall_nop
0x1400062f6  mov     eax, ebx
0x1400062f8  add     rsp, 30h
0x1400062fc  pop     rbx
0x1400062fd  retn
```
