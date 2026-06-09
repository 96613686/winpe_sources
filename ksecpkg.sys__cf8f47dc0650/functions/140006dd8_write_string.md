# write_string

- ea: `0x140006dd8`
- end: `0x140006e29`
- name: `write_string`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006308`

## callees

- `0x140006d88`
- `0x140006dd8`

## pseudocode

```c
int __fastcall write_string(char *a1, int a2, FILE *a3, _DWORD *a4)
{
  int result; // eax
  int v7; // ebx

  result = a3->_flag;
  v7 = a2;
  if ( (result & 0x40) == 0 || a3->_base )
  {
    if ( a2 > 0 )
    {
      do
      {
        result = write_char(*a1, a3, a4);
        if ( *a4 == -1 )
          break;
        --v7;
        ++a1;
      }
      while ( v7 > 0 );
    }
  }
  else
  {
    *a4 += a2;
  }
  return result;
}

```

## disassembly

```asm
0x140006dd8  push    rbx
0x140006dda  push    rbp
0x140006ddb  push    rsi
0x140006ddc  push    rdi
0x140006ddd  sub     rsp, 28h
0x140006de1  mov     eax, [r8+18h]
0x140006de5  mov     rdi, r9
0x140006de8  mov     rbp, r8
0x140006deb  mov     ebx, edx
0x140006ded  mov     rsi, rcx
0x140006df0  test    al, 40h
0x140006df2  jz      short loc_140006E00
0x140006df4  cmp     qword ptr [r8+10h], 0
0x140006df9  jnz     short loc_140006E00
0x140006dfb  add     [r9], edx
0x140006dfe  jmp     short loc_140006E1F
0x140006e00  test    edx, edx
0x140006e02  jle     short loc_140006E1F
0x140006e04  mov     cl, [rsi]
0x140006e06  mov     r8, rdi
0x140006e09  mov     rdx, rbp
0x140006e0c  call    write_char
0x140006e11  cmp     dword ptr [rdi], 0FFFFFFFFh
0x140006e14  jz      short loc_140006E1F
0x140006e16  dec     ebx
0x140006e18  inc     rsi
0x140006e1b  test    ebx, ebx
0x140006e1d  jg      short loc_140006E04
0x140006e1f  add     rsp, 28h
0x140006e23  pop     rdi
0x140006e24  pop     rsi
0x140006e25  pop     rbp
0x140006e26  pop     rbx
0x140006e27  retn
```
