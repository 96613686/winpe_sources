# write_string_4

- ea: `0x180055b98`
- end: `0x180055c06`
- name: `write_string_4`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180055c10`
- `0x180059b90`
- `0x18005cd90`

## callees

- `0x180007f00`
- `0x180055b40`
- `0x180055b98`

## pseudocode

```c
void __fastcall write_string_4(wchar_t *a1, int a2, __int64 a3, _DWORD *a4)
{
  int v6; // ebx

  v6 = a2;
  if ( (*(_BYTE *)(a3 + 24) & 0x40) == 0 || *(_QWORD *)(a3 + 16) )
  {
    if ( a2 > 0 )
    {
      do
      {
        write_char_2(*a1, a3, a4);
        if ( *a4 == -1 )
        {
          if ( *errno() != 42 )
            return;
          write_char_2(0x3Fu, a3, a4);
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
0x180055b98  push    rbx
0x180055b9a  push    rsi
0x180055b9b  push    rdi
0x180055b9c  push    r14
0x180055b9e  sub     rsp, 28h
0x180055ba2  test    byte ptr [r8+18h], 40h
0x180055ba7  mov     rdi, r9
0x180055baa  mov     rsi, r8
0x180055bad  mov     ebx, edx
0x180055baf  mov     r14, rcx
0x180055bb2  jz      short loc_180055BC0
0x180055bb4  cmp     qword ptr [r8+10h], 0
0x180055bb9  jnz     short loc_180055BC0
0x180055bbb  add     [r9], edx
0x180055bbe  jmp     short loc_180055BFC
0x180055bc0  test    edx, edx
0x180055bc2  jle     short loc_180055BFC
0x180055bc4  movzx   ecx, word ptr [r14]
0x180055bc8  mov     r8, rdi
0x180055bcb  mov     rdx, rsi
0x180055bce  call    write_char_2
0x180055bd3  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180055bd6  jnz     short loc_180055BF2
0x180055bd8  call    _errno
0x180055bdd  cmp     dword ptr [rax], 2Ah ; '*'
0x180055be0  jnz     short loc_180055BFC
0x180055be2  mov     ecx, 3Fh ; '?'
0x180055be7  mov     r8, rdi
0x180055bea  mov     rdx, rsi
0x180055bed  call    write_char_2
0x180055bf2  dec     ebx
0x180055bf4  add     r14, 2
0x180055bf8  test    ebx, ebx
0x180055bfa  jg      short loc_180055BC4
0x180055bfc  add     rsp, 28h
0x180055c00  pop     r14
0x180055c02  pop     rdi
0x180055c03  pop     rsi
0x180055c04  pop     rbx
0x180055c05  retn
```
