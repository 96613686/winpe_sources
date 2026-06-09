# write_text_ansi_nolock

- ea: `0x18001d32c`
- end: `0x18001d431`
- name: `write_text_ansi_nolock`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001d7b0`

## callees

- `0x180012bd0`
- `0x18001d32c`
- `0x18001ee90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d3fe`
- `KERNEL32!GetLastError` at `0x18001d3fe`
- `KERNEL32!WriteFile` at `0x18001d3e2`
- `KERNEL32!WriteFile` at `0x18001d3e2`

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
0x18001d32c  mov     [rsp+arg_0], rbx
0x18001d331  mov     [rsp+arg_10], rbp
0x18001d336  push    rsi
0x18001d337  push    rdi
0x18001d338  push    r14
0x18001d33a  mov     eax, 1450h
0x18001d33f  call    _alloca_probe
0x18001d344  sub     rsp, rax
0x18001d347  mov     rax, cs:__security_cookie
0x18001d34e  xor     rax, rsp
0x18001d351  mov     [rsp+1468h+var_28], rax
0x18001d359  mov     rbx, rcx
0x18001d35c  movsxd  r10, edx
0x18001d35f  mov     rax, r10
0x18001d362  mov     ebp, r9d
0x18001d365  sar     rax, 6
0x18001d369  lea     rcx, __pioinfo
0x18001d370  and     r10d, 3Fh
0x18001d374  add     rbp, r8
0x18001d377  and     dword ptr [rbx], 0
0x18001d37a  mov     rsi, r8
0x18001d37d  and     dword ptr [rbx+4], 0
0x18001d381  mov     rax, [rcx+rax*8]
0x18001d385  and     dword ptr [rbx+8], 0
0x18001d389  shl     r10, 6
0x18001d38d  mov     r14, [rax+r10+28h]
0x18001d392  cmp     r8, rbp
0x18001d395  jnb     short loc_18001D406
0x18001d397  lea     rdi, [rsp+1468h+Buffer]
0x18001d39c  cmp     rsi, rbp
0x18001d39f  jnb     short loc_18001D3C5
0x18001d3a1  mov     al, [rsi]
0x18001d3a3  inc     rsi
0x18001d3a6  cmp     al, 0Ah
0x18001d3a8  jnz     short loc_18001D3B3
0x18001d3aa  inc     dword ptr [rbx+8]
0x18001d3ad  mov     byte ptr [rdi], 0Dh
0x18001d3b0  inc     rdi
0x18001d3b3  mov     [rdi], al
0x18001d3b5  inc     rdi
0x18001d3b8  lea     rax, [rsp+1468h+var_29]
0x18001d3c0  cmp     rdi, rax
0x18001d3c3  jb      short loc_18001D39C
0x18001d3c5  and     [rsp+1468h+var_1448], 0
0x18001d3cb  lea     rax, [rsp+1468h+Buffer]
0x18001d3d0  sub     edi, eax
0x18001d3d2  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d3d7  mov     r8d, edi; nNumberOfBytesToWrite
0x18001d3da  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18001d3df  mov     rcx, r14; hFile
0x18001d3e2  call    cs:__imp_WriteFile
0x18001d3e8  test    eax, eax
0x18001d3ea  jz      short loc_18001D3FE
0x18001d3ec  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18001d3f0  add     [rbx+4], eax
0x18001d3f3  cmp     eax, edi
0x18001d3f5  jb      short loc_18001D406
0x18001d3f7  cmp     rsi, rbp
0x18001d3fa  jb      short loc_18001D397
0x18001d3fc  jmp     short loc_18001D406
0x18001d3fe  call    cs:__imp_GetLastError
0x18001d404  mov     [rbx], eax
0x18001d406  mov     rax, rbx
0x18001d409  mov     rcx, [rsp+1468h+var_28]
0x18001d411  xor     rcx, rsp; StackCookie
0x18001d414  call    __security_check_cookie
0x18001d419  lea     r11, [rsp+1468h+var_18]
0x18001d421  mov     rbx, [r11+20h]
0x18001d425  mov     rbp, [r11+30h]
0x18001d429  mov     rsp, r11
0x18001d42c  pop     r14
0x18001d42e  pop     rdi
0x18001d42f  pop     rsi
0x18001d430  retn
```
