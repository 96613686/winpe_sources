# write_text_ansi_nolock

- ea: `0x18001c764`
- end: `0x18001c86f`
- name: `write_text_ansi_nolock`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001cc4c`

## callees

- `0x180018ac0`
- `0x18001c764`
- `0x180024ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c83c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c820`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c820`

## pseudocode

```c
__int64 __fastcall write_text_ansi_nolock(__int64 a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  char v9; // al
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v15; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  v6 = a3;
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          ++*(_DWORD *)(a1 + 8);
          *v8++ = 13;
        }
        *v8++ = v9;
      }
      while ( v8 < &v15 );
      NumberOfBytesWritten = 0;
      v10 = (_DWORD)v8 - (unsigned int)Buffer;
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18001c764  mov     [rsp+arg_0], rbx
0x18001c769  mov     [rsp+arg_10], rbp
0x18001c76e  push    rsi
0x18001c76f  push    rdi
0x18001c770  push    r14
0x18001c772  mov     eax, 1450h
0x18001c777  call    _alloca_probe
0x18001c77c  sub     rsp, rax
0x18001c77f  mov     rax, cs:__security_cookie
0x18001c786  xor     rax, rsp
0x18001c789  mov     [rsp+1468h+var_28], rax
0x18001c791  mov     eax, edx
0x18001c793  movsxd  r10, edx
0x18001c796  and     eax, 3Fh
0x18001c799  sar     r10, 6
0x18001c79d  mov     rdi, rcx
0x18001c7a0  mov     ebp, r9d
0x18001c7a3  lea     rcx, __pioinfo
0x18001c7aa  add     rbp, r8
0x18001c7ad  mov     rsi, r8
0x18001c7b0  lea     rdx, [rax+rax*8]
0x18001c7b4  mov     rax, [rcx+r10*8]
0x18001c7b8  mov     r14, [rax+rdx*8+28h]
0x18001c7bd  xor     eax, eax
0x18001c7bf  mov     [rdi], rax
0x18001c7c2  mov     [rdi+8], eax
0x18001c7c5  cmp     r8, rbp
0x18001c7c8  jnb     short loc_18001C844
0x18001c7ca  lea     rbx, [rsp+1468h+Buffer]
0x18001c7cf  cmp     rsi, rbp
0x18001c7d2  jnb     short loc_18001C7F8
0x18001c7d4  mov     al, [rsi]
0x18001c7d6  inc     rsi
0x18001c7d9  cmp     al, 0Ah
0x18001c7db  jnz     short loc_18001C7E6
0x18001c7dd  inc     dword ptr [rdi+8]
0x18001c7e0  mov     byte ptr [rbx], 0Dh
0x18001c7e3  inc     rbx
0x18001c7e6  mov     [rbx], al
0x18001c7e8  inc     rbx
0x18001c7eb  lea     rax, [rsp+1468h+var_29]
0x18001c7f3  cmp     rbx, rax
0x18001c7f6  jb      short loc_18001C7CF
0x18001c7f8  lea     rax, [rsp+1468h+Buffer]
0x18001c7fd  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x18001c805  sub     ebx, eax
0x18001c807  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x18001c810  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001c813  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001c818  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18001c81d  mov     rcx, r14; hFile
0x18001c820  call    cs:__imp_WriteFile
0x18001c826  test    eax, eax
0x18001c828  jz      short loc_18001C83C
0x18001c82a  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18001c82e  add     [rdi+4], eax
0x18001c831  cmp     eax, ebx
0x18001c833  jb      short loc_18001C844
0x18001c835  cmp     rsi, rbp
0x18001c838  jb      short loc_18001C7CA
0x18001c83a  jmp     short loc_18001C844
0x18001c83c  call    cs:__imp_GetLastError
0x18001c842  mov     [rdi], eax
0x18001c844  mov     rax, rdi
0x18001c847  mov     rcx, [rsp+1468h+var_28]
0x18001c84f  xor     rcx, rsp; StackCookie
0x18001c852  call    __security_check_cookie
0x18001c857  lea     r11, [rsp+1468h+var_18]
0x18001c85f  mov     rbx, [r11+20h]
0x18001c863  mov     rbp, [r11+30h]
0x18001c867  mov     rsp, r11
0x18001c86a  pop     r14
0x18001c86c  pop     rdi
0x18001c86d  pop     rsi
0x18001c86e  retn
```
