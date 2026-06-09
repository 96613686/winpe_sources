# write_double_translated_ansi_nolock

- ea: `0x18001d124`
- end: `0x18001d32c`
- name: `write_double_translated_ansi_nolock`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001d7b0`

## callees

- `0x180012bd0`
- `0x18001b23c`
- `0x18001b4c8`
- `0x18001d124`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d2fa`
- `KERNEL32!GetLastError` at `0x18001d2fa`
- `KERNEL32!WideCharToMultiByte` at `0x18001d25d`
- `KERNEL32!WideCharToMultiByte` at `0x18001d25d`
- `KERNEL32!GetConsoleCP` at `0x18001d181`
- `KERNEL32!GetConsoleCP` at `0x18001d181`
- `KERNEL32!WriteFile` at `0x18001d283`
- `KERNEL32!WriteFile` at `0x18001d2c2`
- `KERNEL32!WriteFile` at `0x18001d283`
- `KERNEL32!WriteFile` at `0x18001d2c2`

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
0x18001d124  mov     [rsp-38h+arg_0], rbx
0x18001d129  push    rbp
0x18001d12a  push    rsi
0x18001d12b  push    rdi
0x18001d12c  push    r12
0x18001d12e  push    r13
0x18001d130  push    r14
0x18001d132  push    r15
0x18001d134  mov     rbp, rsp
0x18001d137  sub     rsp, 80h
0x18001d13e  mov     rax, cs:__security_cookie
0x18001d145  xor     rax, rsp
0x18001d148  mov     [rbp+var_10], rax
0x18001d14c  movsxd  rsi, edx
0x18001d14f  lea     rax, __pioinfo
0x18001d156  mov     r15, rsi
0x18001d159  mov     r12d, r9d
0x18001d15c  sar     r15, 6
0x18001d160  and     esi, 3Fh
0x18001d163  shl     rsi, 6
0x18001d167  mov     r14, r8
0x18001d16a  mov     [rbp+var_28], r8
0x18001d16e  mov     rbx, rcx
0x18001d171  add     r12, r8
0x18001d174  mov     rax, [rax+r15*8]
0x18001d178  mov     rax, [rax+rsi+28h]
0x18001d17d  mov     [rbp+hFile], rax
0x18001d181  call    cs:__imp_GetConsoleCP
0x18001d187  xor     edx, edx
0x18001d189  mov     [rbp+CodePage], eax
0x18001d18c  mov     [rbx], rdx
0x18001d18f  mov     rdi, r14
0x18001d192  mov     [rbx+8], edx
0x18001d195  cmp     r14, r12
0x18001d198  jnb     loc_18001D302
0x18001d19e  mov     r13b, [rdi]
0x18001d1a1  lea     r14, __pioinfo
0x18001d1a8  mov     [rbp+DstCh], dx
0x18001d1ac  mov     rdx, [r14+r15*8]
0x18001d1b0  mov     cl, [rdx+rsi+3Dh]
0x18001d1b4  test    cl, 4
0x18001d1b7  jz      short loc_18001D1D7
0x18001d1b9  mov     al, [rdx+rsi+3Eh]
0x18001d1bd  and     cl, 0FBh
0x18001d1c0  mov     [rdx+rsi+3Dh], cl
0x18001d1c4  mov     r8d, 2
0x18001d1ca  lea     rdx, [rbp+var_20]
0x18001d1ce  mov     [rbp+var_20], al
0x18001d1d1  mov     [rbp+var_1F], r13b
0x18001d1d5  jmp     short loc_18001D21C
0x18001d1d7  call    __pctype_func
0x18001d1dc  movzx   ecx, byte ptr [rdi]
0x18001d1df  mov     edx, 8000h
0x18001d1e4  test    [rax+rcx*2], dx
0x18001d1e8  jz      short loc_18001D213
0x18001d1ea  cmp     rdi, r12
0x18001d1ed  jnb     loc_18001D2E2
0x18001d1f3  mov     r8d, 2; SrcSizeInBytes
0x18001d1f9  lea     rcx, [rbp+DstCh]; DstCh
0x18001d1fd  mov     rdx, rdi; SrcCh
0x18001d200  call    mbtowc
0x18001d205  cmp     eax, 0FFFFFFFFh
0x18001d208  jz      loc_18001D302
0x18001d20e  inc     rdi
0x18001d211  jmp     short loc_18001D22E
0x18001d213  mov     r8d, 1; SrcSizeInBytes
0x18001d219  mov     rdx, rdi; SrcCh
0x18001d21c  lea     rcx, [rbp+DstCh]; DstCh
0x18001d220  call    mbtowc
0x18001d225  cmp     eax, 0FFFFFFFFh
0x18001d228  jz      loc_18001D302
0x18001d22e  and     [rsp+80h+var_48], 0
0x18001d234  lea     rax, [rbp+MultiByteStr]
0x18001d238  and     [rsp+80h+var_50], 0
0x18001d23e  lea     r8, [rbp+DstCh]; lpWideCharStr
0x18001d242  mov     ecx, [rbp+CodePage]; CodePage
0x18001d245  mov     r9d, 1; cchWideChar
0x18001d24b  mov     [rsp+80h+cbMultiByte], 5; cbMultiByte
0x18001d253  xor     edx, edx; dwFlags
0x18001d255  mov     [rsp+80h+lpMultiByteStr], rax; lpOverlapped
0x18001d25a  inc     rdi
0x18001d25d  call    cs:__imp_WideCharToMultiByte
0x18001d263  mov     r14d, eax
0x18001d266  test    eax, eax
0x18001d268  jz      loc_18001D302
0x18001d26e  mov     rcx, [rbp+hFile]; hFile
0x18001d272  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d276  and     [rsp+80h+lpMultiByteStr], 0
0x18001d27c  lea     rdx, [rbp+MultiByteStr]; lpBuffer
0x18001d280  mov     r8d, eax; nNumberOfBytesToWrite
0x18001d283  call    cs:__imp_WriteFile
0x18001d289  xor     edx, edx
0x18001d28b  test    eax, eax
0x18001d28d  jz      short loc_18001D2FA
0x18001d28f  mov     ecx, [rbx+8]
0x18001d292  sub     ecx, dword ptr [rbp+var_28]
0x18001d295  add     ecx, edi
0x18001d297  mov     [rbx+4], ecx
0x18001d29a  cmp     [rbp+NumberOfBytesWritten], r14d
0x18001d29e  jb      short loc_18001D302
0x18001d2a0  cmp     r13b, 0Ah
0x18001d2a4  jnz     short loc_18001D2DA
0x18001d2a6  mov     rcx, [rbp+hFile]; hFile
0x18001d2aa  lea     eax, [rdx+0Dh]
0x18001d2ad  mov     [rsp+80h+lpMultiByteStr], rdx; lpOverlapped
0x18001d2b2  lea     r8d, [rdx+1]; nNumberOfBytesToWrite
0x18001d2b6  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001d2ba  mov     [rbp+Buffer], ax
0x18001d2be  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001d2c2  call    cs:__imp_WriteFile
0x18001d2c8  xor     edx, edx
0x18001d2ca  test    eax, eax
0x18001d2cc  jz      short loc_18001D2FA
0x18001d2ce  cmp     [rbp+NumberOfBytesWritten], 1
0x18001d2d2  jb      short loc_18001D302
0x18001d2d4  inc     dword ptr [rbx+8]
0x18001d2d7  inc     dword ptr [rbx+4]
0x18001d2da  cmp     rdi, r12
0x18001d2dd  jmp     loc_18001D198
0x18001d2e2  mov     al, [rdi]
0x18001d2e4  mov     rcx, [r14+r15*8]
0x18001d2e8  mov     [rcx+rsi+3Eh], al
0x18001d2ec  mov     rax, [r14+r15*8]
0x18001d2f0  or      byte ptr [rax+rsi+3Dh], 4
0x18001d2f5  inc     dword ptr [rbx+4]
0x18001d2f8  jmp     short loc_18001D302
0x18001d2fa  call    cs:__imp_GetLastError
0x18001d300  mov     [rbx], eax
0x18001d302  mov     rax, rbx
0x18001d305  mov     rcx, [rbp+var_10]
0x18001d309  xor     rcx, rsp; StackCookie
0x18001d30c  call    __security_check_cookie
0x18001d311  mov     rbx, [rsp+80h+arg_0]
0x18001d319  add     rsp, 80h
0x18001d320  pop     r15
0x18001d322  pop     r14
0x18001d324  pop     r13
0x18001d326  pop     r12
0x18001d328  pop     rdi
0x18001d329  pop     rsi
0x18001d32a  pop     rbp
0x18001d32b  retn
```
