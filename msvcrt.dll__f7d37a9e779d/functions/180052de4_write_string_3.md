# write_string_3

- ea: `0x180052de4`
- end: `0x180052e4d`
- name: `write_string_3`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180052e60`
- `0x180053b40`
- `0x180054e40`

## callees

- `0x180007f00`
- `0x180052d94`
- `0x180052de4`

## pseudocode

```c
void __fastcall write_string_3(unsigned __int8 *a1, int a2, __int64 a3, _DWORD *a4)
{
  int v6; // ebx

  v6 = a2;
  if ( (*(_BYTE *)(a3 + 24) & 0x40) == 0 || *(_QWORD *)(a3 + 16) )
  {
    if ( a2 > 0 )
    {
      do
      {
        write_char_1(*a1, a3, a4);
        if ( *a4 == -1 )
        {
          if ( *errno() != 42 )
            return;
          write_char_1(0x3Fu, a3, a4);
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
0x180052de4  push    rbx
0x180052de6  push    rsi
0x180052de7  push    rdi
0x180052de8  push    r14
0x180052dea  sub     rsp, 28h
0x180052dee  test    byte ptr [r8+18h], 40h
0x180052df3  mov     rdi, r9
0x180052df6  mov     rsi, r8
0x180052df9  mov     ebx, edx
0x180052dfb  mov     r14, rcx
0x180052dfe  jz      short loc_180052E0C
0x180052e00  cmp     qword ptr [r8+10h], 0
0x180052e05  jnz     short loc_180052E0C
0x180052e07  add     [r9], edx
0x180052e0a  jmp     short loc_180052E43
0x180052e0c  test    edx, edx
0x180052e0e  jle     short loc_180052E43
0x180052e10  mov     cl, [r14]
0x180052e13  mov     r8, rdi
0x180052e16  mov     rdx, rsi
0x180052e19  call    write_char_1
0x180052e1e  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180052e21  jnz     short loc_180052E3A
0x180052e23  call    _errno
0x180052e28  cmp     dword ptr [rax], 2Ah ; '*'
0x180052e2b  jnz     short loc_180052E43
0x180052e2d  mov     r8, rdi
0x180052e30  mov     rdx, rsi
0x180052e33  mov     cl, 3Fh ; '?'
0x180052e35  call    write_char_1
0x180052e3a  dec     ebx
0x180052e3c  inc     r14
0x180052e3f  test    ebx, ebx
0x180052e41  jg      short loc_180052E10
0x180052e43  add     rsp, 28h
0x180052e47  pop     r14
0x180052e49  pop     rdi
0x180052e4a  pop     rsi
0x180052e4b  pop     rbx
0x180052e4c  retn
```
