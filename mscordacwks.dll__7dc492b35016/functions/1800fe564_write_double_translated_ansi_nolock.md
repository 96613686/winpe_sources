# write_double_translated_ansi_nolock

- ea: `0x1800fe564`
- end: `0x1800fe76c`
- name: `write_double_translated_ansi_nolock`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800febf0`

## callees

- `0x1800f0d20`
- `0x1800fc264`
- `0x1800fda70`
- `0x1800fe564`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fe73a`
- `KERNEL32!GetLastError` at `0x1800fe73a`
- `KERNEL32!WideCharToMultiByte` at `0x1800fe69d`
- `KERNEL32!WideCharToMultiByte` at `0x1800fe69d`
- `KERNEL32!WriteFile` at `0x1800fe6c3`
- `KERNEL32!WriteFile` at `0x1800fe702`
- `KERNEL32!WriteFile` at `0x1800fe6c3`
- `KERNEL32!WriteFile` at `0x1800fe702`
- `KERNEL32!GetConsoleCP` at `0x1800fe5c1`
- `KERNEL32!GetConsoleCP` at `0x1800fe5c1`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, const char *a3, int a4)
{
  __int64 v4; // r15
  unsigned __int64 v5; // rsi
  unsigned __int64 v8; // r12
  const char *v9; // rdi
  bool i; // cf
  char v11; // r13
  __int64 v12; // rdx
  char v13; // cl
  char v14; // al
  size_t v15; // r8
  const char *v16; // rdx
  DWORD v17; // eax
  DWORD v18; // r14d
  wchar_t DstCh[2]; // [rsp+40h] [rbp-40h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-38h] BYREF
  UINT CodePage; // [rsp+4Ch] [rbp-34h]
  HANDLE hFile; // [rsp+50h] [rbp-30h]
  const char *v25; // [rsp+58h] [rbp-28h]
  _BYTE v26[8]; // [rsp+60h] [rbp-20h] BYREF
  CHAR MultiByteStr[8]; // [rsp+68h] [rbp-18h] BYREF

  v4 = (__int64)a2 >> 6;
  v5 = (unsigned __int64)(a2 & 0x3F) << 6;
  v25 = a3;
  v8 = (unsigned __int64)&a3[a4];
  hFile = *(HANDLE *)(_pioinfo[v4] + v5 + 40);
  CodePage = GetConsoleCP();
  *(_QWORD *)a1 = 0;
  v9 = a3;
  *(_DWORD *)(a1 + 8) = 0;
  for ( i = (unsigned __int64)a3 < v8; i; i = (unsigned __int64)v9 < v8 )
  {
    v11 = *v9;
    DstCh[0] = 0;
    v12 = _pioinfo[v4];
    v13 = *(_BYTE *)(v12 + v5 + 61);
    if ( (v13 & 4) != 0 )
    {
      v14 = *(_BYTE *)(v12 + v5 + 62);
      *(_BYTE *)(v12 + v5 + 61) = v13 & 0xFB;
      v15 = 2;
      v16 = v26;
      v26[0] = v14;
      v26[1] = v11;
      goto LABEL_10;
    }
    if ( (_pctype_func()[*(unsigned __int8 *)v9] & 0x8000u) == 0 )
    {
      v15 = 1;
      v16 = v9;
LABEL_10:
      if ( mbtowc(DstCh, v16, v15) == -1 )
        return a1;
      goto LABEL_11;
    }
    if ( (unsigned __int64)v9 >= v8 )
    {
      *(_BYTE *)(_pioinfo[v4] + v5 + 62) = *v9;
      *(_BYTE *)(_pioinfo[v4] + v5 + 61) |= 4u;
      ++*(_DWORD *)(a1 + 4);
      return a1;
    }
    if ( mbtowc(DstCh, v9, 2u) == -1 )
      return a1;
    ++v9;
LABEL_11:
    ++v9;
    v17 = WideCharToMultiByte(CodePage, 0, DstCh, 1, MultiByteStr, 5, 0, 0);
    v18 = v17;
    if ( !v17 )
      return a1;
    if ( !WriteFile(hFile, MultiByteStr, v17, &NumberOfBytesWritten, 0) )
    {
LABEL_20:
      *(_DWORD *)a1 = GetLastError();
      return a1;
    }
    *(_DWORD *)(a1 + 4) = (_DWORD)v9 + *(_DWORD *)(a1 + 8) - (_DWORD)v25;
    if ( NumberOfBytesWritten < v18 )
      return a1;
    if ( v11 == 10 )
    {
      Buffer = 13;
      if ( !WriteFile(hFile, &Buffer, 1u, &NumberOfBytesWritten, 0) )
        goto LABEL_20;
      if ( !NumberOfBytesWritten )
        return a1;
      ++*(_DWORD *)(a1 + 8);
      ++*(_DWORD *)(a1 + 4);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800fe564  mov     [rsp-38h+arg_0], rbx
0x1800fe569  push    rbp
0x1800fe56a  push    rsi
0x1800fe56b  push    rdi
0x1800fe56c  push    r12
0x1800fe56e  push    r13
0x1800fe570  push    r14
0x1800fe572  push    r15
0x1800fe574  mov     rbp, rsp
0x1800fe577  sub     rsp, 80h
0x1800fe57e  mov     rax, cs:__security_cookie
0x1800fe585  xor     rax, rsp
0x1800fe588  mov     [rbp+var_10], rax
0x1800fe58c  movsxd  rsi, edx
0x1800fe58f  lea     rax, __pioinfo
0x1800fe596  mov     r15, rsi
0x1800fe599  mov     r12d, r9d
0x1800fe59c  sar     r15, 6
0x1800fe5a0  and     esi, 3Fh
0x1800fe5a3  shl     rsi, 6
0x1800fe5a7  mov     r14, r8
0x1800fe5aa  mov     [rbp+var_28], r8
0x1800fe5ae  mov     rbx, rcx
0x1800fe5b1  add     r12, r8
0x1800fe5b4  mov     rax, [rax+r15*8]
0x1800fe5b8  mov     rax, [rax+rsi+28h]
0x1800fe5bd  mov     [rbp+hFile], rax
0x1800fe5c1  call    cs:__imp_GetConsoleCP
0x1800fe5c7  xor     edx, edx
0x1800fe5c9  mov     [rbp+CodePage], eax
0x1800fe5cc  mov     [rbx], rdx
0x1800fe5cf  mov     rdi, r14
0x1800fe5d2  mov     [rbx+8], edx
0x1800fe5d5  cmp     r14, r12
0x1800fe5d8  jnb     loc_1800FE742
0x1800fe5de  mov     r13b, [rdi]
0x1800fe5e1  lea     r14, __pioinfo
0x1800fe5e8  mov     [rbp+DstCh], dx
0x1800fe5ec  mov     rdx, [r14+r15*8]
0x1800fe5f0  mov     cl, [rdx+rsi+3Dh]
0x1800fe5f4  test    cl, 4
0x1800fe5f7  jz      short loc_1800FE617
0x1800fe5f9  mov     al, [rdx+rsi+3Eh]
0x1800fe5fd  and     cl, 0FBh
0x1800fe600  mov     [rdx+rsi+3Dh], cl
0x1800fe604  mov     r8d, 2
0x1800fe60a  lea     rdx, [rbp+var_20]
0x1800fe60e  mov     [rbp+var_20], al
0x1800fe611  mov     [rbp+var_1F], r13b
0x1800fe615  jmp     short loc_1800FE65C
0x1800fe617  call    __pctype_func
0x1800fe61c  movzx   ecx, byte ptr [rdi]
0x1800fe61f  mov     edx, 8000h
0x1800fe624  test    [rax+rcx*2], dx
0x1800fe628  jz      short loc_1800FE653
0x1800fe62a  cmp     rdi, r12
0x1800fe62d  jnb     loc_1800FE722
0x1800fe633  mov     r8d, 2; SrcSizeInBytes
0x1800fe639  lea     rcx, [rbp+DstCh]; DstCh
0x1800fe63d  mov     rdx, rdi; SrcCh
0x1800fe640  call    mbtowc
0x1800fe645  cmp     eax, 0FFFFFFFFh
0x1800fe648  jz      loc_1800FE742
0x1800fe64e  inc     rdi
0x1800fe651  jmp     short loc_1800FE66E
0x1800fe653  mov     r8d, 1; SrcSizeInBytes
0x1800fe659  mov     rdx, rdi; SrcCh
0x1800fe65c  lea     rcx, [rbp+DstCh]; DstCh
0x1800fe660  call    mbtowc
0x1800fe665  cmp     eax, 0FFFFFFFFh
0x1800fe668  jz      loc_1800FE742
0x1800fe66e  and     [rsp+80h+var_48], 0
0x1800fe674  lea     rax, [rbp+MultiByteStr]
0x1800fe678  and     [rsp+80h+var_50], 0
0x1800fe67e  lea     r8, [rbp+DstCh]; lpWideCharStr
0x1800fe682  mov     ecx, [rbp+CodePage]; CodePage
0x1800fe685  mov     r9d, 1; cchWideChar
0x1800fe68b  mov     [rsp+80h+cbMultiByte], 5; cbMultiByte
0x1800fe693  xor     edx, edx; dwFlags
0x1800fe695  mov     [rsp+80h+lpMultiByteStr], rax; lpOverlapped
0x1800fe69a  inc     rdi
0x1800fe69d  call    cs:__imp_WideCharToMultiByte
0x1800fe6a3  mov     r14d, eax
0x1800fe6a6  test    eax, eax
0x1800fe6a8  jz      loc_1800FE742
0x1800fe6ae  mov     rcx, [rbp+hFile]; hFile
0x1800fe6b2  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fe6b6  and     [rsp+80h+lpMultiByteStr], 0
0x1800fe6bc  lea     rdx, [rbp+MultiByteStr]; lpBuffer
0x1800fe6c0  mov     r8d, eax; nNumberOfBytesToWrite
0x1800fe6c3  call    cs:__imp_WriteFile
0x1800fe6c9  xor     edx, edx
0x1800fe6cb  test    eax, eax
0x1800fe6cd  jz      short loc_1800FE73A
0x1800fe6cf  mov     ecx, [rbx+8]
0x1800fe6d2  sub     ecx, dword ptr [rbp+var_28]
0x1800fe6d5  add     ecx, edi
0x1800fe6d7  mov     [rbx+4], ecx
0x1800fe6da  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800fe6de  jb      short loc_1800FE742
0x1800fe6e0  cmp     r13b, 0Ah
0x1800fe6e4  jnz     short loc_1800FE71A
0x1800fe6e6  mov     rcx, [rbp+hFile]; hFile
0x1800fe6ea  lea     eax, [rdx+0Dh]
0x1800fe6ed  mov     [rsp+80h+lpMultiByteStr], rdx; lpOverlapped
0x1800fe6f2  lea     r8d, [rdx+1]; nNumberOfBytesToWrite
0x1800fe6f6  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800fe6fa  mov     [rbp+Buffer], ax
0x1800fe6fe  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fe702  call    cs:__imp_WriteFile
0x1800fe708  xor     edx, edx
0x1800fe70a  test    eax, eax
0x1800fe70c  jz      short loc_1800FE73A
0x1800fe70e  cmp     [rbp+NumberOfBytesWritten], 1
0x1800fe712  jb      short loc_1800FE742
0x1800fe714  inc     dword ptr [rbx+8]
0x1800fe717  inc     dword ptr [rbx+4]
0x1800fe71a  cmp     rdi, r12
0x1800fe71d  jmp     loc_1800FE5D8
0x1800fe722  mov     al, [rdi]
0x1800fe724  mov     rcx, [r14+r15*8]
0x1800fe728  mov     [rcx+rsi+3Eh], al
0x1800fe72c  mov     rax, [r14+r15*8]
0x1800fe730  or      byte ptr [rax+rsi+3Dh], 4
0x1800fe735  inc     dword ptr [rbx+4]
0x1800fe738  jmp     short loc_1800FE742
0x1800fe73a  call    cs:__imp_GetLastError
0x1800fe740  mov     [rbx], eax
0x1800fe742  mov     rax, rbx
0x1800fe745  mov     rcx, [rbp+var_10]
0x1800fe749  xor     rcx, rsp; StackCookie
0x1800fe74c  call    __security_check_cookie
0x1800fe751  mov     rbx, [rsp+80h+arg_0]
0x1800fe759  add     rsp, 80h
0x1800fe760  pop     r15
0x1800fe762  pop     r14
0x1800fe764  pop     r13
0x1800fe766  pop     r12
0x1800fe768  pop     rdi
0x1800fe769  pop     rsi
0x1800fe76a  pop     rbp
0x1800fe76b  retn
```
