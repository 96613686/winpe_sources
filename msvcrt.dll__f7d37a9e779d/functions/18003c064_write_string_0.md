# write_string_0

- ea: `0x18003c064`
- end: `0x18003c0cd`
- name: `write_string_0`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b204`

## callees

- `0x180007f00`
- `0x18003c014`
- `0x18003c064`

## pseudocode

```c
void __fastcall write_string_0(unsigned __int8 *a1, int a2, __int64 a3, _DWORD *a4)
{
  int v6; // ebx

  v6 = a2;
  if ( (*(_BYTE *)(a3 + 24) & 0x40) == 0 || *(_QWORD *)(a3 + 16) )
  {
    if ( a2 > 0 )
    {
      do
      {
        write_char_0(*a1, a3, a4);
        if ( *a4 == -1 )
        {
          if ( *errno() != 42 )
            return;
          write_char_0(0x3Fu, a3, a4);
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
0x18003c064  push    rbx
0x18003c066  push    rsi
0x18003c067  push    rdi
0x18003c068  push    r14
0x18003c06a  sub     rsp, 28h
0x18003c06e  test    byte ptr [r8+18h], 40h
0x18003c073  mov     rdi, r9
0x18003c076  mov     rsi, r8
0x18003c079  mov     ebx, edx
0x18003c07b  mov     r14, rcx
0x18003c07e  jz      short loc_18003C08C
0x18003c080  cmp     qword ptr [r8+10h], 0
0x18003c085  jnz     short loc_18003C08C
0x18003c087  add     [r9], edx
0x18003c08a  jmp     short loc_18003C0C3
0x18003c08c  test    edx, edx
0x18003c08e  jle     short loc_18003C0C3
0x18003c090  mov     cl, [r14]
0x18003c093  mov     r8, rdi
0x18003c096  mov     rdx, rsi
0x18003c099  call    write_char_0
0x18003c09e  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003c0a1  jnz     short loc_18003C0BA
0x18003c0a3  call    _errno
0x18003c0a8  cmp     dword ptr [rax], 2Ah ; '*'
0x18003c0ab  jnz     short loc_18003C0C3
0x18003c0ad  mov     r8, rdi
0x18003c0b0  mov     rdx, rsi
0x18003c0b3  mov     cl, 3Fh ; '?'
0x18003c0b5  call    write_char_0
0x18003c0ba  dec     ebx
0x18003c0bc  inc     r14
0x18003c0bf  test    ebx, ebx
0x18003c0c1  jg      short loc_18003C090
0x18003c0c3  add     rsp, 28h
0x18003c0c7  pop     r14
0x18003c0c9  pop     rdi
0x18003c0ca  pop     rsi
0x18003c0cb  pop     rbx
0x18003c0cc  retn
```
