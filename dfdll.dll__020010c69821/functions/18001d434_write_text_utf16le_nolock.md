# write_text_utf16le_nolock

- ea: `0x18001d434`
- end: `0x18001d550`
- name: `write_text_utf16le_nolock`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001d7b0`

## callees

- `0x180012bd0`
- `0x18001d434`
- `0x18001ee90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d51d`
- `KERNEL32!GetLastError` at `0x18001d51d`
- `KERNEL32!WriteFile` at `0x18001d501`
- `KERNEL32!WriteFile` at `0x18001d501`

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
0x18001d434  mov     [rsp+arg_0], rbx
0x18001d439  mov     [rsp+arg_10], rbp
0x18001d43e  push    rsi
0x18001d43f  push    rdi
0x18001d440  push    r14
0x18001d442  mov     eax, 1450h
0x18001d447  call    _alloca_probe
0x18001d44c  sub     rsp, rax
0x18001d44f  mov     rax, cs:__security_cookie
0x18001d456  xor     rax, rsp
0x18001d459  mov     [rsp+1468h+var_28], rax
0x18001d461  mov     rdi, rcx
0x18001d464  movsxd  r10, edx
0x18001d467  mov     rax, r10
0x18001d46a  mov     ebp, r9d
0x18001d46d  sar     rax, 6
0x18001d471  lea     rcx, __pioinfo
0x18001d478  and     r10d, 3Fh
0x18001d47c  add     rbp, r8
0x18001d47f  and     dword ptr [rdi], 0
0x18001d482  mov     rsi, r8
0x18001d485  and     dword ptr [rdi+4], 0
0x18001d489  mov     rax, [rcx+rax*8]
0x18001d48d  and     dword ptr [rdi+8], 0
0x18001d491  shl     r10, 6
0x18001d495  mov     r14, [rax+r10+28h]
0x18001d49a  cmp     r8, rbp
0x18001d49d  jnb     loc_18001D525
0x18001d4a3  lea     rbx, [rsp+1468h+Buffer]
0x18001d4a8  cmp     rsi, rbp
0x18001d4ab  jnb     short loc_18001D4DE
0x18001d4ad  movzx   eax, word ptr [rsi]
0x18001d4b0  add     rsi, 2
0x18001d4b4  cmp     ax, 0Ah
0x18001d4b8  jnz     short loc_18001D4CA
0x18001d4ba  add     dword ptr [rdi+8], 2
0x18001d4be  mov     ecx, 0Dh
0x18001d4c3  mov     [rbx], cx
0x18001d4c6  add     rbx, 2
0x18001d4ca  mov     [rbx], ax
0x18001d4cd  add     rbx, 2
0x18001d4d1  lea     rax, [rsp+1468h+var_2A]
0x18001d4d9  cmp     rbx, rax
0x18001d4dc  jb      short loc_18001D4A8
0x18001d4de  and     [rsp+1468h+var_1448], 0
0x18001d4e4  lea     rax, [rsp+1468h+Buffer]
0x18001d4e9  sub     rbx, rax
0x18001d4ec  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d4f1  sar     rbx, 1
0x18001d4f4  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18001d4f9  add     ebx, ebx
0x18001d4fb  mov     rcx, r14; hFile
0x18001d4fe  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001d501  call    cs:__imp_WriteFile
0x18001d507  test    eax, eax
0x18001d509  jz      short loc_18001D51D
0x18001d50b  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18001d50f  add     [rdi+4], eax
0x18001d512  cmp     eax, ebx
0x18001d514  jb      short loc_18001D525
0x18001d516  cmp     rsi, rbp
0x18001d519  jb      short loc_18001D4A3
0x18001d51b  jmp     short loc_18001D525
0x18001d51d  call    cs:__imp_GetLastError
0x18001d523  mov     [rdi], eax
0x18001d525  mov     rax, rdi
0x18001d528  mov     rcx, [rsp+1468h+var_28]
0x18001d530  xor     rcx, rsp; StackCookie
0x18001d533  call    __security_check_cookie
0x18001d538  lea     r11, [rsp+1468h+var_18]
0x18001d540  mov     rbx, [r11+20h]
0x18001d544  mov     rbp, [r11+30h]
0x18001d548  mov     rsp, r11
0x18001d54b  pop     r14
0x18001d54d  pop     rdi
0x18001d54e  pop     rsi
0x18001d54f  retn
```
