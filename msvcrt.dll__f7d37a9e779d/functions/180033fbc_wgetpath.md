# _wgetpath

- ea: `0x180033fbc`
- end: `0x18003407d`
- name: `_wgetpath`
- size: `193`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b0e0`
- `0x180031940`
- `0x18004f410`

## callees

- `0x180007f00`
- `0x180033fbc`

## pseudocode

```c
_WORD *__fastcall wgetpath(_WORD *a1, _WORD *a2, __int64 a3)
{
  _WORD *v5; // rbp
  __int64 v6; // r8
  __int16 v7; // ax
  __int16 v8; // ax
  _WORD *result; // rax

  while ( *a1 == 59 )
    ++a1;
  v5 = a1;
  v6 = a3 - 1;
  if ( v6 )
  {
    v7 = *a1;
    if ( *a1 )
    {
      while ( v7 != 59 )
      {
        ++a1;
        if ( v7 == 34 )
        {
          while ( 1 )
          {
            v8 = *a1;
            if ( !*a1 || v8 == 34 )
              break;
            *a2 = v8;
            ++a1;
            ++a2;
            if ( !--v6 )
              goto LABEL_10;
          }
          if ( !*a1 )
            break;
          ++a1;
        }
        else
        {
          *a2++ = v7;
          if ( !--v6 )
          {
LABEL_10:
            v5 = a1;
            *errno() = 34;
            goto LABEL_20;
          }
        }
        v7 = *a1;
        if ( !*a1 )
          break;
      }
    }
    while ( *a1 == 59 )
      ++a1;
  }
  else
  {
    *errno() = 34;
  }
LABEL_20:
  *a2 = 0;
  result = 0;
  if ( v5 != a1 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180033fbc  push    rbx
0x180033fbe  push    rbp
0x180033fbf  push    rsi
0x180033fc0  push    rdi
0x180033fc1  push    r14
0x180033fc3  sub     rsp, 20h
0x180033fc7  mov     rbx, rcx
0x180033fca  mov     rsi, rdx
0x180033fcd  mov     cx, 3Bh ; ';'
0x180033fd1  jmp     short loc_180033FD7
0x180033fd3  add     rbx, 2
0x180033fd7  cmp     [rbx], cx
0x180033fda  jz      short loc_180033FD3
0x180033fdc  xor     r14d, r14d
0x180033fdf  mov     rbp, rbx
0x180033fe2  sub     r8, 1
0x180033fe6  jnz     short loc_180033FF5
0x180033fe8  call    _errno
0x180033fed  mov     dword ptr [rax], 22h ; '"'
0x180033ff3  jmp     short loc_180034064
0x180033ff5  movzx   eax, word ptr [rbx]
0x180033ff8  test    ax, ax
0x180033ffb  jz      short loc_18003405F
0x180033ffd  mov     edi, 22h ; '"'
0x180034002  cmp     ax, cx
0x180034005  jz      short loc_18003405F
0x180034007  add     rbx, 2
0x18003400b  cmp     ax, di
0x18003400e  jz      short loc_18003403F
0x180034010  mov     [rsi], ax
0x180034013  add     rsi, 2
0x180034017  sub     r8, 1
0x18003401b  jnz     short loc_180034051
0x18003401d  mov     rbp, rbx
0x180034020  call    _errno
0x180034025  mov     [rax], edi
0x180034027  jmp     short loc_180034064
0x180034029  cmp     ax, di
0x18003402c  jz      short loc_180034047
0x18003402e  mov     [rsi], ax
0x180034031  add     rbx, 2
0x180034035  add     rsi, 2
0x180034039  sub     r8, 1
0x18003403d  jz      short loc_18003401D
0x18003403f  movzx   eax, word ptr [rbx]
0x180034042  test    ax, ax
0x180034045  jnz     short loc_180034029
0x180034047  cmp     [rbx], r14w
0x18003404b  jz      short loc_18003405F
0x18003404d  add     rbx, 2
0x180034051  movzx   eax, word ptr [rbx]
0x180034054  test    ax, ax
0x180034057  jnz     short loc_180034002
0x180034059  jmp     short loc_18003405F
0x18003405b  add     rbx, 2
0x18003405f  cmp     [rbx], cx
0x180034062  jz      short loc_18003405B
0x180034064  cmp     rbp, rbx
0x180034067  mov     [rsi], r14w
0x18003406b  mov     rax, r14
0x18003406e  cmovnz  rax, rbx
0x180034072  add     rsp, 20h
0x180034076  pop     r14
0x180034078  pop     rdi
0x180034079  pop     rsi
0x18003407a  pop     rbp
0x18003407b  pop     rbx
0x18003407c  retn
```
