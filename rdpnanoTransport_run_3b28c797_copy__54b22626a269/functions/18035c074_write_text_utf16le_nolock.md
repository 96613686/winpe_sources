# write_text_utf16le_nolock

- ea: `0x18035c074`
- end: `0x18035c18f`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18035c424`

## callees

- `0x18032f050`
- `0x18032f0b0`
- `0x18035c074`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18035c15c`
- `KERNEL32!GetLastError` at `0x18035c15c`
- `KERNEL32!WriteFile` at `0x18035c140`
- `KERNEL32!WriteFile` at `0x18035c140`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
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
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      NumberOfBytesWritten = 0;
      v10 = 2 * ((v8 - Buffer) >> 1);
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
0x18035c074  mov     [rsp+arg_0], rbx
0x18035c079  mov     [rsp+arg_10], rbp
0x18035c07e  push    rsi
0x18035c07f  push    rdi
0x18035c080  push    r14
0x18035c082  mov     eax, 1450h
0x18035c087  call    _alloca_probe
0x18035c08c  sub     rsp, rax
0x18035c08f  mov     rax, cs:__security_cookie
0x18035c096  xor     rax, rsp
0x18035c099  mov     [rsp+1468h+var_28], rax
0x18035c0a1  movsxd  r10, edx
0x18035c0a4  mov     rdi, rcx
0x18035c0a7  mov     rax, r10
0x18035c0aa  mov     ebp, r9d
0x18035c0ad  sar     rax, 6
0x18035c0b1  lea     rcx, __pioinfo
0x18035c0b8  and     r10d, 3Fh
0x18035c0bc  add     rbp, r8
0x18035c0bf  mov     rsi, r8
0x18035c0c2  mov     rax, [rcx+rax*8]
0x18035c0c6  lea     rdx, [r10+r10*8]
0x18035c0ca  mov     r14, [rax+rdx*8+28h]
0x18035c0cf  xor     eax, eax
0x18035c0d1  mov     [rdi], rax
0x18035c0d4  mov     [rdi+8], eax
0x18035c0d7  cmp     r8, rbp
0x18035c0da  jnb     loc_18035C164
0x18035c0e0  lea     rbx, [rsp+1468h+Buffer]
0x18035c0e5  cmp     rsi, rbp
0x18035c0e8  jnb     short loc_18035C118
0x18035c0ea  movzx   eax, word ptr [rsi]
0x18035c0ed  add     rsi, 2
0x18035c0f1  cmp     ax, 0Ah
0x18035c0f5  jnz     short loc_18035C104
0x18035c0f7  add     dword ptr [rdi+8], 2
0x18035c0fb  mov     word ptr [rbx], 0Dh
0x18035c100  add     rbx, 2
0x18035c104  mov     [rbx], ax
0x18035c107  add     rbx, 2
0x18035c10b  lea     rax, [rsp+1468h+var_2A]
0x18035c113  cmp     rbx, rax
0x18035c116  jb      short loc_18035C0E5
0x18035c118  and     [rsp+1468h+NumberOfBytesWritten], 0
0x18035c11d  lea     rax, [rsp+1468h+Buffer]
0x18035c122  and     [rsp+1468h+var_1448], 0
0x18035c128  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18035c12d  sub     rbx, rax
0x18035c130  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18035c135  sar     rbx, 1
0x18035c138  mov     rcx, r14; hFile
0x18035c13b  add     ebx, ebx
0x18035c13d  mov     r8d, ebx; nNumberOfBytesToWrite
0x18035c140  call    cs:__imp_WriteFile
0x18035c146  test    eax, eax
0x18035c148  jz      short loc_18035C15C
0x18035c14a  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18035c14e  add     [rdi+4], eax
0x18035c151  cmp     eax, ebx
0x18035c153  jb      short loc_18035C164
0x18035c155  cmp     rsi, rbp
0x18035c158  jb      short loc_18035C0E0
0x18035c15a  jmp     short loc_18035C164
0x18035c15c  call    cs:__imp_GetLastError
0x18035c162  mov     [rdi], eax
0x18035c164  mov     rax, rdi
0x18035c167  mov     rcx, [rsp+1468h+var_28]
0x18035c16f  xor     rcx, rsp; StackCookie
0x18035c172  call    __security_check_cookie
0x18035c177  lea     r11, [rsp+1468h+var_18]
0x18035c17f  mov     rbx, [r11+20h]
0x18035c183  mov     rbp, [r11+30h]
0x18035c187  mov     rsp, r11
0x18035c18a  pop     r14
0x18035c18c  pop     rdi
0x18035c18d  pop     rsi
0x18035c18e  retn
```
