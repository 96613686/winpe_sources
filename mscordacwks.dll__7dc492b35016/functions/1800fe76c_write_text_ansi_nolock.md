# write_text_ansi_nolock

- ea: `0x1800fe76c`
- end: `0x1800fe871`
- name: `write_text_ansi_nolock`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800febf0`

## callees

- `0x1800f0d20`
- `0x1800fe76c`
- `0x180105e80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fe83e`
- `KERNEL32!GetLastError` at `0x1800fe83e`
- `KERNEL32!WriteFile` at `0x1800fe822`
- `KERNEL32!WriteFile` at `0x1800fe822`

## pseudocode

```c
DWORD *__fastcall write_text_ansi_nolock(DWORD *a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  __int64 v7; // rax
  void *v8; // r14
  char *v9; // rdi
  char v10; // al
  DWORD v11; // edi
  DWORD v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v16; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  *a1 = 0;
  v6 = a3;
  a1[1] = 0;
  v7 = _pioinfo[(__int64)a2 >> 6];
  a1[2] = 0;
  v8 = *(void **)(v7 + ((unsigned __int64)(a2 & 0x3F) << 6) + 40);
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v9 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v10 = *v6++;
        if ( v10 == 10 )
        {
          ++a1[2];
          *v9++ = 13;
        }
        *v9++ = v10;
      }
      while ( v9 < &v16 );
      v11 = (_DWORD)v9 - (unsigned int)Buffer;
      if ( !WriteFile(v8, Buffer, v11, &NumberOfBytesWritten, 0) )
        break;
      v12 = NumberOfBytesWritten;
      a1[1] += NumberOfBytesWritten;
      if ( v12 < v11 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x1800fe76c  mov     [rsp+arg_0], rbx
0x1800fe771  mov     [rsp+arg_10], rbp
0x1800fe776  push    rsi
0x1800fe777  push    rdi
0x1800fe778  push    r14
0x1800fe77a  mov     eax, 1450h
0x1800fe77f  call    _alloca_probe
0x1800fe784  sub     rsp, rax
0x1800fe787  mov     rax, cs:__security_cookie
0x1800fe78e  xor     rax, rsp
0x1800fe791  mov     [rsp+1468h+var_28], rax
0x1800fe799  mov     rbx, rcx
0x1800fe79c  movsxd  r10, edx
0x1800fe79f  mov     rax, r10
0x1800fe7a2  mov     ebp, r9d
0x1800fe7a5  sar     rax, 6
0x1800fe7a9  lea     rcx, __pioinfo
0x1800fe7b0  and     r10d, 3Fh
0x1800fe7b4  add     rbp, r8
0x1800fe7b7  and     dword ptr [rbx], 0
0x1800fe7ba  mov     rsi, r8
0x1800fe7bd  and     dword ptr [rbx+4], 0
0x1800fe7c1  mov     rax, [rcx+rax*8]
0x1800fe7c5  and     dword ptr [rbx+8], 0
0x1800fe7c9  shl     r10, 6
0x1800fe7cd  mov     r14, [rax+r10+28h]
0x1800fe7d2  cmp     r8, rbp
0x1800fe7d5  jnb     short loc_1800FE846
0x1800fe7d7  lea     rdi, [rsp+1468h+Buffer]
0x1800fe7dc  cmp     rsi, rbp
0x1800fe7df  jnb     short loc_1800FE805
0x1800fe7e1  mov     al, [rsi]
0x1800fe7e3  inc     rsi
0x1800fe7e6  cmp     al, 0Ah
0x1800fe7e8  jnz     short loc_1800FE7F3
0x1800fe7ea  inc     dword ptr [rbx+8]
0x1800fe7ed  mov     byte ptr [rdi], 0Dh
0x1800fe7f0  inc     rdi
0x1800fe7f3  mov     [rdi], al
0x1800fe7f5  inc     rdi
0x1800fe7f8  lea     rax, [rsp+1468h+var_29]
0x1800fe800  cmp     rdi, rax
0x1800fe803  jb      short loc_1800FE7DC
0x1800fe805  and     [rsp+1468h+var_1448], 0
0x1800fe80b  lea     rax, [rsp+1468h+Buffer]
0x1800fe810  sub     edi, eax
0x1800fe812  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fe817  mov     r8d, edi; nNumberOfBytesToWrite
0x1800fe81a  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800fe81f  mov     rcx, r14; hFile
0x1800fe822  call    cs:__imp_WriteFile
0x1800fe828  test    eax, eax
0x1800fe82a  jz      short loc_1800FE83E
0x1800fe82c  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800fe830  add     [rbx+4], eax
0x1800fe833  cmp     eax, edi
0x1800fe835  jb      short loc_1800FE846
0x1800fe837  cmp     rsi, rbp
0x1800fe83a  jb      short loc_1800FE7D7
0x1800fe83c  jmp     short loc_1800FE846
0x1800fe83e  call    cs:__imp_GetLastError
0x1800fe844  mov     [rbx], eax
0x1800fe846  mov     rax, rbx
0x1800fe849  mov     rcx, [rsp+1468h+var_28]
0x1800fe851  xor     rcx, rsp; StackCookie
0x1800fe854  call    __security_check_cookie
0x1800fe859  lea     r11, [rsp+1468h+var_18]
0x1800fe861  mov     rbx, [r11+20h]
0x1800fe865  mov     rbp, [r11+30h]
0x1800fe869  mov     rsp, r11
0x1800fe86c  pop     r14
0x1800fe86e  pop     rdi
0x1800fe86f  pop     rsi
0x1800fe870  retn
```
