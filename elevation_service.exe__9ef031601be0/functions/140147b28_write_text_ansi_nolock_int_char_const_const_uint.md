# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x140147b28`
- end: `0x140147c2f`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, int, char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140147244`

## callees

- `0x14012fc30`
- `0x14012fc90`
- `0x140147b28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140147bfc`
- `KERNEL32!GetLastError` at `0x140147bfc`
- `KERNEL32!WriteFile` at `0x140147be0`
- `KERNEL32!WriteFile` at `0x140147be0`

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
0x140147b28  mov     [rsp+arg_0], rbx
0x140147b2d  mov     [rsp+arg_10], rbp
0x140147b32  push    rsi
0x140147b33  push    rdi
0x140147b34  push    r14
0x140147b36  mov     eax, 1450h
0x140147b3b  call    __alloca_probe
0x140147b40  sub     rsp, rax
0x140147b43  mov     rax, cs:__security_cookie
0x140147b4a  xor     rax, rsp
0x140147b4d  mov     [rsp+1468h+var_28], rax
0x140147b55  movsxd  r10, edx
0x140147b58  mov     rdi, rcx
0x140147b5b  mov     rax, r10
0x140147b5e  mov     ebp, r9d
0x140147b61  sar     rax, 6
0x140147b65  lea     rcx, qword_14038C5D0
0x140147b6c  and     r10d, 3Fh
0x140147b70  add     rbp, r8
0x140147b73  mov     rsi, r8
0x140147b76  mov     rax, [rcx+rax*8]
0x140147b7a  lea     rdx, [r10+r10*8]
0x140147b7e  mov     r14, [rax+rdx*8+28h]
0x140147b83  xor     eax, eax
0x140147b85  mov     [rdi], rax
0x140147b88  mov     [rdi+8], eax
0x140147b8b  cmp     r8, rbp
0x140147b8e  jnb     short loc_140147C04
0x140147b90  lea     rbx, [rsp+1468h+Buffer]
0x140147b95  cmp     rsi, rbp
0x140147b98  jnb     short loc_140147BBE
0x140147b9a  mov     al, [rsi]
0x140147b9c  inc     rsi
0x140147b9f  cmp     al, 0Ah
0x140147ba1  jnz     short loc_140147BAC
0x140147ba3  inc     dword ptr [rdi+8]
0x140147ba6  mov     byte ptr [rbx], 0Dh
0x140147ba9  inc     rbx
0x140147bac  mov     [rbx], al
0x140147bae  inc     rbx
0x140147bb1  lea     rax, [rsp+1468h+var_29]
0x140147bb9  cmp     rbx, rax
0x140147bbc  jb      short loc_140147B95
0x140147bbe  and     [rsp+1468h+NumberOfBytesWritten], 0
0x140147bc3  lea     rax, [rsp+1468h+Buffer]
0x140147bc8  and     [rsp+1468h+var_1448], 0
0x140147bce  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140147bd3  sub     ebx, eax
0x140147bd5  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x140147bda  mov     r8d, ebx; nNumberOfBytesToWrite
0x140147bdd  mov     rcx, r14; hFile
0x140147be0  call    cs:WriteFile
0x140147be6  test    eax, eax
0x140147be8  jz      short loc_140147BFC
0x140147bea  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140147bee  add     [rdi+4], eax
0x140147bf1  cmp     eax, ebx
0x140147bf3  jb      short loc_140147C04
0x140147bf5  cmp     rsi, rbp
0x140147bf8  jb      short loc_140147B90
0x140147bfa  jmp     short loc_140147C04
0x140147bfc  call    cs:__imp_GetLastError
0x140147c02  mov     [rdi], eax
0x140147c04  mov     rax, rdi
0x140147c07  mov     rcx, [rsp+1468h+var_28]
0x140147c0f  xor     rcx, rsp; StackCookie
0x140147c12  call    __security_check_cookie
0x140147c17  lea     r11, [rsp+1468h+var_18]
0x140147c1f  mov     rbx, [r11+20h]
0x140147c23  mov     rbp, [r11+30h]
0x140147c27  mov     rsp, r11
0x140147c2a  pop     r14
0x140147c2c  pop     rdi
0x140147c2d  pop     rsi
0x140147c2e  retn
```
