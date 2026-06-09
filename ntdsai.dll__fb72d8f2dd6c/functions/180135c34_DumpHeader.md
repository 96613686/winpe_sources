# DumpHeader

- ea: `0x180135c34`
- end: `0x18013602d`
- name: `DumpHeader`
- size: `1017`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1801340f8`
- `0x180138cb8`
- `0x18013c6d4`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x18001ea60`
- `0x180135c34`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135e62`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135cfb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135d67`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135dab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135f09`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135f5f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135fa7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135fe2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135cfb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135d67`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135dab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135f09`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135f5f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135fa7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135fe2`

## string_xrefs

- `0x180135e37`: `WriteFile`

## pseudocode

```c
__int64 __fastcall DumpHeader(__int64 a1, void *a2, __int64 a3, __int64 a4, __int64 a5, int a6, _BYTE *lpBuffer)
{
  int v7; // r14d
  _BYTE *v9; // r15
  int *v10; // rdi
  int v11; // r13d
  __int64 v12; // r8
  int i; // r15d
  int v14; // eax
  _BYTE *v15; // rdx
  __int64 v16; // rbx
  unsigned int v17; // r8d
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  LPOVERLAPPED v21; // rbx
  int j; // r14d
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  _BYTE *v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+68h] [rbp-98h]
  DWORD Offset; // [rsp+6Ch] [rbp-94h]
  int v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+7Ch] [rbp-84h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  int v40; // [rsp+A8h] [rbp-58h]
  int *v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+C0h] [rbp-40h] BYREF
  const char *v43; // [rsp+C8h] [rbp-38h]
  int v44; // [rsp+E0h] [rbp-20h]
  __int64 LastError; // [rsp+F8h] [rbp-8h]

  v7 = a6;
  v9 = lpBuffer;
  v26 = a5;
  v28 = a3;
  v27 = a1;
  v25 = a6;
  v29 = lpBuffer;
  NumberOfBytesWritten = 0;
  v10 = (int *)THAlloc_(a1, 1, 4 * a6, 1, 0, 52495517);
  memset_0(v10, 0, 4LL * a6);
  while ( 2 )
  {
    v11 = 1;
    v12 = -1;
    do
      ++v12;
    while ( v9[v12] );
    WriteFile(a2, v9, v12, &NumberOfBytesWritten, 0);
    for ( i = 0; i < v7; ++i )
    {
      v14 = 0;
      v15 = (_BYTE *)(v10[i] + *(_QWORD *)(v28 + 8LL * i));
      if ( !*v15 )
        v14 = v11;
      v16 = -1;
      v11 = v14;
      do
        ++v16;
      while ( v15[v16] );
      v17 = *((_DWORD *)DefaultSyntaxWidths + *(int *)(v26 + 4LL * i));
      if ( (unsigned int)v16 <= v17 )
      {
        if ( !WriteFile(a2, v15, v16, &NumberOfBytesWritten, 0) || NumberOfBytesWritten < (unsigned int)v16 )
          goto LABEL_15;
        v10[i] += v16;
        for ( j = 0; j < *((_DWORD *)DefaultSyntaxWidths + *(int *)(v26 + 4LL * i)) - (int)v16; ++j )
        {
          if ( !WriteFile(a2, " ", 1u, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten )
            goto LABEL_15;
        }
        v7 = v25;
      }
      else
      {
        if ( !WriteFile(a2, v15, v17 - 1, &NumberOfBytesWritten, 0) )
          goto LABEL_15;
        v20 = *((_DWORD *)DefaultSyntaxWidths + *(int *)(v26 + 4LL * i));
        if ( NumberOfBytesWritten < v20 - 1 )
          goto LABEL_15;
        v10[i] += v20 - 1;
        if ( !WriteFile(a2, "-", 1u, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten )
          goto LABEL_15;
      }
      if ( i != v7 - 1 && (!WriteFile(a2, " ", 1u, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten) )
        goto LABEL_15;
    }
    if ( !WriteFile(a2, "\r\n", 2u, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten )
    {
LABEL_15:
      v21 = gpDsEventConfig;
      if ( gpDsEventConfig )
      {
        if ( (gpDsEventConfig[4].OffsetHigh & 0x80000000) == 0
          || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(801, 0) )
        {
          goto LABEL_21;
        }
        if ( (unsigned int)DoLogMsgOverride(3221226875LL) )
        {
          v21 = gpDsEventConfig;
LABEL_21:
          memset_0(&v30, 0, 0x60u);
          Offset = v21[4].Offset;
          v41 = &v42;
          v43 = "WriteFile";
          v33 = 0;
          v31 = -1073740421;
          v34 = 0;
          v35 = 1;
          v42 = 0;
          v30 = 1;
          v44 = 3;
          LastError = GetLastError();
          *(_QWORD *)&v41[8 * v30 + 2] = &v41[8 * v30 + 6];
          ++v30;
          v38 = 0;
          v37 = 801;
          v36 = 1;
          v39 = 0;
          v40 = 0;
          DoLogEventAndTrace(&v30);
        }
      }
      if ( v10 )
        THFreeAux(v27, (_DWORD)v10, v18, v19, 52495634);
      return 0;
    }
    v9 = v29;
    if ( !v11 )
      continue;
    break;
  }
  if ( v10 )
    THFreeAux(v27, (_DWORD)v10, v18, v19, 52495618);
  return 1;
}

```

## disassembly

```asm
0x180135c34  mov     [rsp-8+arg_18], rbx
0x180135c39  push    rbp
0x180135c3a  push    rsi
0x180135c3b  push    rdi
0x180135c3c  push    r12
0x180135c3e  push    r13
0x180135c40  push    r14
0x180135c42  push    r15
0x180135c44  lea     rbp, [rsp-1F0h]
0x180135c4c  sub     rsp, 2F0h
0x180135c53  mov     rax, cs:__security_cookie
0x180135c5a  xor     rax, rsp
0x180135c5d  mov     [rbp+220h+var_40], rax
0x180135c64  movsxd  r14, [rbp+220h+arg_28]
0x180135c6b  mov     r12, rdx
0x180135c6e  mov     rax, [rbp+220h+arg_20]
0x180135c75  mov     rbx, r14
0x180135c78  mov     r15, [rbp+220h+lpBuffer]
0x180135c7f  mov     [rsp+320h+var_2E8], rax
0x180135c84  mov     eax, 1
0x180135c89  mov     [rsp+320h+var_2D8], r8
0x180135c8e  mov     r9d, eax
0x180135c91  shl     rbx, 2
0x180135c95  mov     edx, eax
0x180135c97  mov     r8, rbx
0x180135c9a  mov     [rsp+320h+var_2F8], 321049Dh
0x180135ca2  mov     [rsp+320h+var_2E0], rcx
0x180135ca7  mov     [rsp+320h+var_2EC], r14d
0x180135cac  mov     [rsp+320h+var_2D0], r15
0x180135cb1  mov     [rsp+320h+NumberOfBytesWritten], 0
0x180135cb9  mov     dword ptr [rsp+320h+lpOverlapped], 0
0x180135cc1  call    THAlloc_
0x180135cc6  mov     r8, rbx; Size
0x180135cc9  xor     edx, edx; Val
0x180135ccb  mov     rcx, rax; void *
0x180135cce  mov     rdi, rax
0x180135cd1  call    memset_0
0x180135cd6  xor     ebx, ebx
0x180135cd8  mov     r13d, 1
0x180135cde  or      r8, 0FFFFFFFFFFFFFFFFh
0x180135ce2  inc     r8; nNumberOfBytesToWrite
0x180135ce5  cmp     [r15+r8], bl
0x180135ce9  jnz     short loc_180135CE2
0x180135ceb  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135cf0  mov     [rsp+320h+lpOverlapped], rbx; lpOverlapped
0x180135cf5  mov     rdx, r15; lpBuffer
0x180135cf8  mov     rcx, r12; hFile
0x180135cfb  call    cs:__imp_WriteFile
0x180135d01  mov     r15d, ebx
0x180135d04  cmp     r15d, r14d
0x180135d07  jge     loc_180135FC8
0x180135d0d  mov     rax, [rsp+320h+var_2D8]
0x180135d12  movsxd  rsi, r15d
0x180135d15  mov     rdx, [rax+rsi*8]
0x180135d19  mov     eax, ebx
0x180135d1b  movsxd  rcx, dword ptr [rdi+rsi*4]
0x180135d1f  add     rdx, rcx; lpBuffer
0x180135d22  cmp     [rdx], bl
0x180135d24  cmovz   eax, r13d
0x180135d28  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180135d2c  mov     r13d, eax
0x180135d2f  inc     rbx
0x180135d32  cmp     byte ptr [rdx+rbx], 0
0x180135d36  jnz     short loc_180135D2F
0x180135d38  mov     rax, [rsp+320h+var_2E8]
0x180135d3d  lea     r8, DefaultSyntaxWidths
0x180135d44  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135d49  mov     rcx, r12; hFile
0x180135d4c  movsxd  rax, dword ptr [rax+rsi*4]
0x180135d50  mov     r8d, [r8+rax*4]
0x180135d54  cmp     ebx, r8d
0x180135d57  jbe     loc_180135EFD
0x180135d5d  xor     ebx, ebx
0x180135d5f  dec     r8d; nNumberOfBytesToWrite
0x180135d62  mov     [rsp+320h+lpOverlapped], rbx; lpOverlapped
0x180135d67  call    cs:__imp_WriteFile
0x180135d6d  test    eax, eax
0x180135d6f  jz      short loc_180135DC0
0x180135d71  mov     rax, [rsp+320h+var_2E8]
0x180135d76  lea     rcx, DefaultSyntaxWidths
0x180135d7d  movsxd  rax, dword ptr [rax+rsi*4]
0x180135d81  mov     ecx, [rcx+rax*4]
0x180135d84  lea     eax, [rcx-1]
0x180135d87  cmp     [rsp+320h+NumberOfBytesWritten], eax
0x180135d8b  jb      short loc_180135DC0
0x180135d8d  lea     eax, [rcx-1]
0x180135d90  mov     [rsp+320h+lpOverlapped], rbx; lpOverlapped
0x180135d95  add     [rdi+rsi*4], eax
0x180135d98  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135d9d  mov     rcx, r12; hFile
0x180135da0  lea     r8d, [rbx+1]; nNumberOfBytesToWrite
0x180135da4  lea     rdx, asc_18049ED08; "-"
0x180135dab  call    cs:__imp_WriteFile
0x180135db1  test    eax, eax
0x180135db3  jz      short loc_180135DC0
0x180135db5  cmp     [rsp+320h+NumberOfBytesWritten], 1
0x180135dba  jnb     loc_180135F84
0x180135dc0  mov     rbx, cs:gpDsEventConfig
0x180135dc7  xor     esi, esi
0x180135dc9  test    rbx, rbx
0x180135dcc  jz      loc_180135EB7
0x180135dd2  mov     r15d, 321h
0x180135dd8  mov     r14d, 0C000057Bh
0x180135dde  cmp     [rbx+94h], esi
0x180135de4  jge     short loc_180135E10
0x180135de6  cmp     [rbx+4], esi
0x180135de9  jz      short loc_180135DF9
0x180135deb  xor     edx, edx
0x180135ded  mov     ecx, r15d
0x180135df0  call    DoLogOverride
0x180135df5  test    eax, eax
0x180135df7  jnz     short loc_180135E10
0x180135df9  mov     ecx, r14d
0x180135dfc  call    DoLogMsgOverride
0x180135e01  test    eax, eax
0x180135e03  jz      loc_180135EB7
0x180135e09  mov     rbx, cs:gpDsEventConfig
0x180135e10  xor     edx, edx; Val
0x180135e12  lea     rcx, [rsp+320h+var_2C0]; void *
0x180135e17  lea     r8d, [rdx+60h]; Size
0x180135e1b  call    memset_0
0x180135e20  mov     eax, [rbx+90h]
0x180135e26  mov     ebx, 1
0x180135e2b  mov     [rsp+320h+var_2B4], eax
0x180135e2f  lea     rax, [rbp+220h+var_260]
0x180135e33  mov     [rbp+220h+var_268], rax
0x180135e37  lea     rax, aWritefile; "WriteFile"
0x180135e3e  mov     [rbp+220h+var_258], rax
0x180135e42  mov     [rsp+320h+var_2B0], esi
0x180135e46  mov     [rsp+320h+var_2B8], r14d
0x180135e4b  mov     [rsp+320h+var_2A8], esi
0x180135e4f  mov     [rsp+320h+var_2A4], ebx
0x180135e53  mov     [rbp+220h+var_260], esi
0x180135e56  mov     [rsp+320h+var_2C0], rbx
0x180135e5b  mov     [rbp+220h+var_240], 3
0x180135e62  call    cs:__imp_GetLastError
0x180135e68  mov     rcx, [rsp+320h+var_2C0]
0x180135e6d  mov     edx, eax
0x180135e6f  mov     rax, [rbp+220h+var_268]
0x180135e73  shl     rcx, 5
0x180135e77  mov     [rcx+rax+18h], rdx
0x180135e7c  mov     rcx, [rbp+220h+var_268]
0x180135e80  mov     rdx, [rsp+320h+var_2C0]
0x180135e85  shl     rdx, 5
0x180135e89  lea     rax, [rcx+18h]
0x180135e8d  add     rax, rdx
0x180135e90  mov     [rdx+rcx+8], rax
0x180135e95  lea     rcx, [rsp+320h+var_2C0]
0x180135e9a  add     [rsp+320h+var_2C0], rbx
0x180135e9f  mov     [rbp+220h+var_290], rsi
0x180135ea3  mov     [rbp+220h+var_298], r15
0x180135ea7  mov     [rbp+220h+var_2A0], rbx
0x180135eab  mov     [rbp+220h+var_280], rsi
0x180135eaf  mov     [rbp+220h+var_278], esi
0x180135eb2  call    DoLogEventAndTrace
0x180135eb7  test    rdi, rdi
0x180135eba  jz      short loc_180135ED1
0x180135ebc  mov     rcx, [rsp+320h+var_2E0]
0x180135ec1  mov     rdx, rdi
0x180135ec4  mov     dword ptr [rsp+320h+lpOverlapped], 3210512h
0x180135ecc  call    THFreeAux
0x180135ed1  xor     eax, eax
0x180135ed3  mov     rcx, [rbp+220h+var_40]
0x180135eda  xor     rcx, rsp; StackCookie
0x180135edd  call    __security_check_cookie
0x180135ee2  mov     rbx, [rsp+320h+arg_18]
0x180135eea  add     rsp, 2F0h
0x180135ef1  pop     r15
0x180135ef3  pop     r14
0x180135ef5  pop     r13
0x180135ef7  pop     r12
0x180135ef9  pop     rdi
0x180135efa  pop     rsi
0x180135efb  pop     rbp
0x180135efc  retn
0x180135efd  mov     r8d, ebx; nNumberOfBytesToWrite
0x180135f00  mov     [rsp+320h+lpOverlapped], 0; lpOverlapped
0x180135f09  call    cs:__imp_WriteFile
0x180135f0f  test    eax, eax
0x180135f11  jz      loc_180135DC0
0x180135f17  cmp     [rsp+320h+NumberOfBytesWritten], ebx
0x180135f1b  jb      loc_180135DC0
0x180135f21  add     [rdi+rsi*4], ebx
0x180135f24  xor     r14d, r14d
0x180135f27  mov     rax, [rsp+320h+var_2E8]
0x180135f2c  lea     rcx, DefaultSyntaxWidths
0x180135f33  movsxd  rax, dword ptr [rax+rsi*4]
0x180135f37  mov     ecx, [rcx+rax*4]
0x180135f3a  sub     ecx, ebx
0x180135f3c  cmp     r14d, ecx
0x180135f3f  jge     short loc_180135F7D
0x180135f41  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135f46  mov     [rsp+320h+lpOverlapped], 0; lpOverlapped
0x180135f4f  mov     r8d, 1; nNumberOfBytesToWrite
0x180135f55  lea     rdx, asc_1804AF15C; " "
0x180135f5c  mov     rcx, r12; hFile
0x180135f5f  call    cs:__imp_WriteFile
0x180135f65  test    eax, eax
0x180135f67  jz      loc_180135DC0
0x180135f6d  cmp     [rsp+320h+NumberOfBytesWritten], 1
0x180135f72  jb      loc_180135DC0
0x180135f78  inc     r14d
0x180135f7b  jmp     short loc_180135F27
0x180135f7d  mov     r14d, [rsp+320h+var_2EC]
0x180135f82  xor     ebx, ebx
0x180135f84  lea     eax, [r14-1]
0x180135f88  cmp     r15d, eax
0x180135f8b  jz      short loc_180135FC0
0x180135f8d  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135f92  mov     [rsp+320h+lpOverlapped], rbx; lpOverlapped
0x180135f97  mov     r8d, 1; nNumberOfBytesToWrite
0x180135f9d  lea     rdx, asc_1804AF15C; " "
0x180135fa4  mov     rcx, r12; hFile
0x180135fa7  call    cs:__imp_WriteFile
0x180135fad  test    eax, eax
0x180135faf  jz      loc_180135DC0
0x180135fb5  cmp     [rsp+320h+NumberOfBytesWritten], 1
0x180135fba  jb      loc_180135DC0
0x180135fc0  inc     r15d
0x180135fc3  jmp     loc_180135D04
0x180135fc8  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180135fcd  mov     [rsp+320h+lpOverlapped], rbx; lpOverlapped
0x180135fd2  mov     r8d, 2; nNumberOfBytesToWrite
0x180135fd8  lea     rdx, asc_1804AF12C; "\r\n"
0x180135fdf  mov     rcx, r12; hFile
0x180135fe2  call    cs:__imp_WriteFile
0x180135fe8  test    eax, eax
0x180135fea  jz      loc_180135DC0
0x180135ff0  cmp     [rsp+320h+NumberOfBytesWritten], 1
0x180135ff5  jb      loc_180135DC0
0x180135ffb  mov     r15, [rsp+320h+var_2D0]
0x180136000  test    r13d, r13d
0x180136003  jz      loc_180135CD8
0x180136009  test    rdi, rdi
0x18013600c  jz      short loc_180136023
0x18013600e  mov     rcx, [rsp+320h+var_2E0]
0x180136013  mov     rdx, rdi
0x180136016  mov     dword ptr [rsp+320h+lpOverlapped], 3210502h
0x18013601e  call    THFreeAux
0x180136023  mov     eax, 1
0x180136028  jmp     loc_180135ED3
```
