# write_string_2

- ea: `0x180045188`
- end: `0x1800451f8`
- name: `write_string_2`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180045280`
- `0x180045e80`
- `0x1800472a0`

## callees

- `0x180007f00`
- `0x18001e648`
- `0x180045188`

## pseudocode

```c
void __fastcall write_string_2(wchar_t *a1, int a2, _DWORD *a3)
{
  int v4; // edi

  if ( a2 > 0 )
  {
    v4 = a2;
    while ( putwch_nolock(*a1) != 0xFFFF )
    {
      if ( ++*a3 == -1 )
        goto LABEL_6;
LABEL_10:
      --v4;
      ++a1;
      if ( v4 <= 0 )
        return;
    }
    *a3 = -1;
LABEL_6:
    if ( *errno() != 42 )
      return;
    if ( putwch_nolock(0x3Fu) == 0xFFFF )
      *a3 = -1;
    else
      ++*a3;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x180045188  test    edx, edx
0x18004518a  jle     short locret_1800451F7
0x18004518c  push    rbx
0x18004518d  push    rsi
0x18004518e  push    rdi
0x18004518f  push    r14
0x180045191  sub     rsp, 28h
0x180045195  mov     rbx, r8
0x180045198  mov     edi, edx
0x18004519a  mov     rsi, rcx
0x18004519d  mov     r14d, 0FFFFh
0x1800451a3  movzx   ecx, word ptr [rsi]; Character
0x1800451a6  call    _putwch_nolock
0x1800451ab  cmp     ax, r14w
0x1800451af  jnz     short loc_1800451B9
0x1800451b1  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800451b7  jmp     short loc_1800451C0
0x1800451b9  inc     dword ptr [rbx]
0x1800451bb  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800451be  jnz     short loc_1800451E4
0x1800451c0  call    _errno
0x1800451c5  cmp     dword ptr [rax], 2Ah ; '*'
0x1800451c8  jnz     short loc_1800451EE
0x1800451ca  mov     ecx, 3Fh ; '?'; Character
0x1800451cf  call    _putwch_nolock
0x1800451d4  cmp     ax, r14w
0x1800451d8  jnz     short loc_1800451E2
0x1800451da  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800451e0  jmp     short loc_1800451E4
0x1800451e2  inc     dword ptr [rbx]
0x1800451e4  dec     edi
0x1800451e6  add     rsi, 2
0x1800451ea  test    edi, edi
0x1800451ec  jg      short loc_1800451A3
0x1800451ee  add     rsp, 28h
0x1800451f2  pop     r14
0x1800451f4  pop     rdi
0x1800451f5  pop     rsi
0x1800451f6  pop     rbx
0x1800451f7  retn
```
