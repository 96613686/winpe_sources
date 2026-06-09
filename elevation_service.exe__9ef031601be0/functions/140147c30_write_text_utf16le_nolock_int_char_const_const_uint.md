# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x140147c30`
- end: `0x140147d4b`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140147244`

## callees

- `0x14012fc30`
- `0x14012fc90`
- `0x140147c30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140147d18`
- `KERNEL32!GetLastError` at `0x140147d18`
- `KERNEL32!WriteFile` at `0x140147cfc`
- `KERNEL32!WriteFile` at `0x140147cfc`

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
  v7 = *(void **)(qword_14038C5D0[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x140147c30  mov     [rsp+arg_0], rbx
0x140147c35  mov     [rsp+arg_10], rbp
0x140147c3a  push    rsi
0x140147c3b  push    rdi
0x140147c3c  push    r14
0x140147c3e  mov     eax, 1450h
0x140147c43  call    __alloca_probe
0x140147c48  sub     rsp, rax
0x140147c4b  mov     rax, cs:__security_cookie
0x140147c52  xor     rax, rsp
0x140147c55  mov     [rsp+1468h+var_28], rax
0x140147c5d  movsxd  r10, edx
0x140147c60  mov     rdi, rcx
0x140147c63  mov     rax, r10
0x140147c66  mov     ebp, r9d
0x140147c69  sar     rax, 6
0x140147c6d  lea     rcx, qword_14038C5D0
0x140147c74  and     r10d, 3Fh
0x140147c78  add     rbp, r8
0x140147c7b  mov     rsi, r8
0x140147c7e  mov     rax, [rcx+rax*8]
0x140147c82  lea     rdx, [r10+r10*8]
0x140147c86  mov     r14, [rax+rdx*8+28h]
0x140147c8b  xor     eax, eax
0x140147c8d  mov     [rdi], rax
0x140147c90  mov     [rdi+8], eax
0x140147c93  cmp     r8, rbp
0x140147c96  jnb     loc_140147D20
0x140147c9c  lea     rbx, [rsp+1468h+Buffer]
0x140147ca1  cmp     rsi, rbp
0x140147ca4  jnb     short loc_140147CD4
0x140147ca6  movzx   eax, word ptr [rsi]
0x140147ca9  add     rsi, 2
0x140147cad  cmp     ax, 0Ah
0x140147cb1  jnz     short loc_140147CC0
0x140147cb3  add     dword ptr [rdi+8], 2
0x140147cb7  mov     word ptr [rbx], 0Dh
0x140147cbc  add     rbx, 2
0x140147cc0  mov     [rbx], ax
0x140147cc3  add     rbx, 2
0x140147cc7  lea     rax, [rsp+1468h+var_2A]
0x140147ccf  cmp     rbx, rax
0x140147cd2  jb      short loc_140147CA1
0x140147cd4  and     [rsp+1468h+NumberOfBytesWritten], 0
0x140147cd9  lea     rax, [rsp+1468h+Buffer]
0x140147cde  and     [rsp+1468h+var_1448], 0
0x140147ce4  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140147ce9  sub     rbx, rax
0x140147cec  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x140147cf1  sar     rbx, 1
0x140147cf4  mov     rcx, r14; hFile
0x140147cf7  add     ebx, ebx
0x140147cf9  mov     r8d, ebx; nNumberOfBytesToWrite
0x140147cfc  call    cs:WriteFile
0x140147d02  test    eax, eax
0x140147d04  jz      short loc_140147D18
0x140147d06  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140147d0a  add     [rdi+4], eax
0x140147d0d  cmp     eax, ebx
0x140147d0f  jb      short loc_140147D20
0x140147d11  cmp     rsi, rbp
0x140147d14  jb      short loc_140147C9C
0x140147d16  jmp     short loc_140147D20
0x140147d18  call    cs:__imp_GetLastError
0x140147d1e  mov     [rdi], eax
0x140147d20  mov     rax, rdi
0x140147d23  mov     rcx, [rsp+1468h+var_28]
0x140147d2b  xor     rcx, rsp; StackCookie
0x140147d2e  call    __security_check_cookie
0x140147d33  lea     r11, [rsp+1468h+var_18]
0x140147d3b  mov     rbx, [r11+20h]
0x140147d3f  mov     rbp, [r11+30h]
0x140147d43  mov     rsp, r11
0x140147d46  pop     r14
0x140147d48  pop     rdi
0x140147d49  pop     rsi
0x140147d4a  retn
```
