# write_string

- ea: `0x180039f5c`
- end: `0x180039fca`
- name: `write_string`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180039390`

## callees

- `0x180007f00`
- `0x180039efc`
- `0x180039f5c`

## pseudocode

```c
void __fastcall write_string(__int16 *a1, int a2, __int64 a3, _DWORD *a4)
{
  int v6; // ebx

  v6 = a2;
  if ( (*(_BYTE *)(a3 + 24) & 0x40) == 0 || *(_QWORD *)(a3 + 16) )
  {
    if ( a2 > 0 )
    {
      do
      {
        write_char(*a1, (FILE *)a3, a4);
        if ( *a4 == -1 )
        {
          if ( *errno() != 42 )
            return;
          write_char(63, (FILE *)a3, a4);
        }
        --v6;
        ++a1;
      }
      while ( v6 > 0 );
    }
  }
  else
  {
    *a4 += a2;
  }
}

```

## disassembly

```asm
0x180039f5c  push    rbx
0x180039f5e  push    rsi
0x180039f5f  push    rdi
0x180039f60  push    r14
0x180039f62  sub     rsp, 28h
0x180039f66  test    byte ptr [r8+18h], 40h
0x180039f6b  mov     rdi, r9
0x180039f6e  mov     rsi, r8
0x180039f71  mov     ebx, edx
0x180039f73  mov     r14, rcx
0x180039f76  jz      short loc_180039F84
0x180039f78  cmp     qword ptr [r8+10h], 0
0x180039f7d  jnz     short loc_180039F84
0x180039f7f  add     [r9], edx
0x180039f82  jmp     short loc_180039FC0
0x180039f84  test    edx, edx
0x180039f86  jle     short loc_180039FC0
0x180039f88  movzx   ecx, word ptr [r14]
0x180039f8c  mov     r8, rdi
0x180039f8f  mov     rdx, rsi
0x180039f92  call    write_char
0x180039f97  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180039f9a  jnz     short loc_180039FB6
0x180039f9c  call    _errno
0x180039fa1  cmp     dword ptr [rax], 2Ah ; '*'
0x180039fa4  jnz     short loc_180039FC0
0x180039fa6  mov     ecx, 3Fh ; '?'
0x180039fab  mov     r8, rdi
0x180039fae  mov     rdx, rsi
0x180039fb1  call    write_char
0x180039fb6  dec     ebx
0x180039fb8  add     r14, 2
0x180039fbc  test    ebx, ebx
0x180039fbe  jg      short loc_180039F88
0x180039fc0  add     rsp, 28h
0x180039fc4  pop     r14
0x180039fc6  pop     rdi
0x180039fc7  pop     rsi
0x180039fc8  pop     rbx
0x180039fc9  retn
```
