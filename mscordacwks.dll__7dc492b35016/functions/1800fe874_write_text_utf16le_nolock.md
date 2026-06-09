# write_text_utf16le_nolock

- ea: `0x1800fe874`
- end: `0x1800fe990`
- name: `write_text_utf16le_nolock`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800febf0`

## callees

- `0x1800f0d20`
- `0x1800fe874`
- `0x180105e80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fe95d`
- `KERNEL32!GetLastError` at `0x1800fe95d`
- `KERNEL32!WriteFile` at `0x1800fe941`
- `KERNEL32!WriteFile` at `0x1800fe941`

## pseudocode

```c
DWORD *__fastcall write_text_utf16le_nolock(DWORD *a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  __int64 v7; // rax
  void *v8; // r14
  char *v9; // rbx
  __int16 v10; // ax
  DWORD v11; // ebx
  DWORD v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v16; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
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
          a1[2] += 2;
          *(_WORD *)v9 = 13;
          v9 += 2;
        }
        *(_WORD *)v9 = v10;
        v9 += 2;
      }
      while ( v9 < (char *)&v16 );
      v11 = 2 * ((v9 - Buffer) >> 1);
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
0x1800fe874  mov     [rsp+arg_0], rbx
0x1800fe879  mov     [rsp+arg_10], rbp
0x1800fe87e  push    rsi
0x1800fe87f  push    rdi
0x1800fe880  push    r14
0x1800fe882  mov     eax, 1450h
0x1800fe887  call    _alloca_probe
0x1800fe88c  sub     rsp, rax
0x1800fe88f  mov     rax, cs:__security_cookie
0x1800fe896  xor     rax, rsp
0x1800fe899  mov     [rsp+1468h+var_28], rax
0x1800fe8a1  mov     rdi, rcx
0x1800fe8a4  movsxd  r10, edx
0x1800fe8a7  mov     rax, r10
0x1800fe8aa  mov     ebp, r9d
0x1800fe8ad  sar     rax, 6
0x1800fe8b1  lea     rcx, __pioinfo
0x1800fe8b8  and     r10d, 3Fh
0x1800fe8bc  add     rbp, r8
0x1800fe8bf  and     dword ptr [rdi], 0
0x1800fe8c2  mov     rsi, r8
0x1800fe8c5  and     dword ptr [rdi+4], 0
0x1800fe8c9  mov     rax, [rcx+rax*8]
0x1800fe8cd  and     dword ptr [rdi+8], 0
0x1800fe8d1  shl     r10, 6
0x1800fe8d5  mov     r14, [rax+r10+28h]
0x1800fe8da  cmp     r8, rbp
0x1800fe8dd  jnb     loc_1800FE965
0x1800fe8e3  lea     rbx, [rsp+1468h+Buffer]
0x1800fe8e8  cmp     rsi, rbp
0x1800fe8eb  jnb     short loc_1800FE91E
0x1800fe8ed  movzx   eax, word ptr [rsi]
0x1800fe8f0  add     rsi, 2
0x1800fe8f4  cmp     ax, 0Ah
0x1800fe8f8  jnz     short loc_1800FE90A
0x1800fe8fa  add     dword ptr [rdi+8], 2
0x1800fe8fe  mov     ecx, 0Dh
0x1800fe903  mov     [rbx], cx
0x1800fe906  add     rbx, 2
0x1800fe90a  mov     [rbx], ax
0x1800fe90d  add     rbx, 2
0x1800fe911  lea     rax, [rsp+1468h+var_2A]
0x1800fe919  cmp     rbx, rax
0x1800fe91c  jb      short loc_1800FE8E8
0x1800fe91e  and     [rsp+1468h+var_1448], 0
0x1800fe924  lea     rax, [rsp+1468h+Buffer]
0x1800fe929  sub     rbx, rax
0x1800fe92c  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fe931  sar     rbx, 1
0x1800fe934  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800fe939  add     ebx, ebx
0x1800fe93b  mov     rcx, r14; hFile
0x1800fe93e  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800fe941  call    cs:__imp_WriteFile
0x1800fe947  test    eax, eax
0x1800fe949  jz      short loc_1800FE95D
0x1800fe94b  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800fe94f  add     [rdi+4], eax
0x1800fe952  cmp     eax, ebx
0x1800fe954  jb      short loc_1800FE965
0x1800fe956  cmp     rsi, rbp
0x1800fe959  jb      short loc_1800FE8E3
0x1800fe95b  jmp     short loc_1800FE965
0x1800fe95d  call    cs:__imp_GetLastError
0x1800fe963  mov     [rdi], eax
0x1800fe965  mov     rax, rdi
0x1800fe968  mov     rcx, [rsp+1468h+var_28]
0x1800fe970  xor     rcx, rsp; StackCookie
0x1800fe973  call    __security_check_cookie
0x1800fe978  lea     r11, [rsp+1468h+var_18]
0x1800fe980  mov     rbx, [r11+20h]
0x1800fe984  mov     rbp, [r11+30h]
0x1800fe988  mov     rsp, r11
0x1800fe98b  pop     r14
0x1800fe98d  pop     rdi
0x1800fe98e  pop     rsi
0x1800fe98f  retn
```
