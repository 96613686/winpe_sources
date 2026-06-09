# ValidateHiveAndRecoverFromLog

- ea: `0x140027b04`
- end: `0x140027f23`
- name: `ValidateHiveAndRecoverFromLog`
- size: `1055`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x140023544`

## callees

- `0x1400020b0`
- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x140002d72`
- `0x1400273a4`
- `0x140027b04`
- `0x140028dd0`
- `0x140028e10`
- `0x14002e8cc`
- `0x140030240`
- `0x14003029c`
- `0x140030784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027d4d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140027caa`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140027caa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140027d3d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140027d3d`

## pseudocode

```c
__int64 __fastcall ValidateHiveAndRecoverFromLog(const void **a1, unsigned int *a2, wchar_t *a3, void *a4)
{
  unsigned int *v4; // r15
  const void **v6; // r14
  __int64 v8; // r10
  __int64 v9; // rdi
  unsigned int v10; // esi
  char v11; // al
  unsigned int v12; // r9d
  int v13; // edx
  int v14; // eax
  __int64 i; // rcx
  unsigned int LastError; // ebx
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // r14
  unsigned int v20; // eax
  int v21; // r8d
  DWORD LowPart; // eax
  LPVOID *v23; // r15
  DWORD v24; // ebx
  void *v25; // rax
  __int64 v26; // rdx
  int v27; // edx
  NTSTATUS v28; // eax
  unsigned int v29; // esi
  void *v30; // rax
  void *v31; // rbx
  __int64 j; // rdi
  void *v33; // rcx
  __int64 k; // rdi
  __int64 v35; // rcx
  __int64 m; // rdi
  void *v37; // rcx
  char v39; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h]
  const void **v44; // [rsp+60h] [rbp-A0h]
  unsigned int *v45; // [rsp+68h] [rbp-98h]
  void *Block[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v47; // [rsp+80h] [rbp-80h] BYREF
  DWORD nNumberOfBytesToRead[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-60h]
  __int128 v50; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v51[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v52[60]; // [rsp+E0h] [rbp-20h] BYREF
  int v53; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v54; // [rsp+120h] [rbp+20h]

  v45 = a2;
  v44 = a1;
  v4 = a2;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  v6 = a1;
  v47 = 0;
  v50 = 0;
  memset(v51, 0, sizeof(v51));
  *(_OWORD *)nNumberOfBytesToRead = 0;
  v49 = 0;
  *(_OWORD *)Block = 0;
  memset_0(v52, 0, 0x5Cu);
  v8 = 1;
  if ( *v4 < 0x1000 )
    goto LABEL_15;
  v9 = (__int64)*v6;
  v10 = *((_DWORD *)*v6 + 10);
  if ( v10 + 4096 < 0x1000 )
    goto LABEL_15;
  v11 = HvIsInPlaceBaseBlockValid(v9);
  v13 = -1;
  if ( v11 )
  {
    v42 = *(_QWORD *)(v9 + 12);
    v39 = v8;
    if ( *(_DWORD *)(v9 + 4) == *(_DWORD *)(v9 + 8) )
    {
      if ( v12 > *v4 )
        goto LABEL_15;
      goto LABEL_47;
    }
  }
  else
  {
    v10 = 0;
    v39 = 0;
    v14 = 0;
    for ( i = 0; i != 127; i += v8 )
      v14 ^= *(_DWORD *)(v9 + 4 * i);
    if ( v14 == -1 )
    {
      v14 = -2;
    }
    else if ( !v14 )
    {
      v14 = v8;
    }
    if ( v14 == *(_DWORD *)(v9 + 508) )
    {
      v17 = *(_QWORD *)(v9 + 12);
    }
    else
    {
      if ( *v4 < 0x1020 || *(_DWORD *)(v9 + 4096) != 1852400232 )
        goto LABEL_15;
      v17 = *(_QWORD *)(v9 + 4116);
    }
    v42 = v17;
  }
  LastError = ConstructLogPaths(a4, a3, Block);
  v8 = 1;
  if ( LastError )
    goto LABEL_56;
  v18 = 0;
  v19 = 0;
  do
  {
    v20 = ORCreateFile((const WCHAR *)Block[v19], 1u, 3u, 1u, &nNumberOfBytesToRead[2 * v18 - 4]);
    LastError = v20;
    if ( v20 == 2 )
    {
      v8 = 1;
    }
    else
    {
      if ( v20 )
        goto LABEL_55;
      hFile = *(HANDLE *)&nNumberOfBytesToRead[2 * v18 - 4];
      if ( !GetFileSizeEx(hFile, &FileSize) )
        LastError = GetLastError();
      if ( LastError )
        goto LABEL_55;
      LowPart = FileSize.LowPart;
      if ( FileSize.QuadPart > 0xFFFFFFFFLL )
      {
        LowPart = -1;
        FileSize.QuadPart = 0xFFFFFFFFLL;
      }
      v23 = (LPVOID *)&nNumberOfBytesToRead[4 * (unsigned int)v18];
      nNumberOfBytesToRead[4 * (unsigned int)v18 + 2] = LowPart;
      if ( LowPart )
      {
        v24 = LowPart;
        v25 = o__aligned_malloc_0(LowPart, 0x10u);
        *v23 = v25;
        if ( !v25 )
          goto LABEL_40;
        memset_0(v25, 0, v24);
        LastError = 0;
        if ( !ReadFile(hFile, *v23, nNumberOfBytesToRead[4 * (unsigned int)v18 + 2], &NumberOfBytesRead, 0) )
          LastError = GetLastError();
        if ( LastError )
          goto LABEL_55;
      }
      v8 = 1;
      v26 = 3 * v18;
      *((_QWORD *)&v50 + v26 + 1) = HiveRecoverReadRoutine;
      *((_QWORD *)v51 + v26) = v23;
      *((_DWORD *)&v51[-1] + 2 * v26) = ((_DWORD)v19 != 0) + 4;
      v18 = (unsigned int)(v18 + 1);
    }
    v19 = (unsigned int)(v19 + 1);
  }
  while ( (unsigned int)v19 < 2 );
  if ( (_DWORD)v18 )
  {
    if ( v39 )
    {
      v27 = *(_DWORD *)(v9 + 8);
      v9 = 0;
    }
    else
    {
      v27 = 0;
    }
    LOBYTE(v21) = v39 ^ 1;
    v28 = HvAnalyzeLogFiles((unsigned int)&v42, v27, v21, (unsigned int)&v50, v18, (__int64)v52, v9);
    if ( v28 < 0 )
      goto LABEL_43;
    v6 = v44;
    if ( v10 < v54 )
      v10 = v54;
    v4 = v45;
LABEL_47:
    v29 = v10 + 4096;
    if ( *v4 < v29 )
    {
      v30 = o__aligned_malloc_0(v29, 0x10u);
      v31 = v30;
      if ( !v30 )
      {
LABEL_40:
        LastError = 14;
LABEL_55:
        v8 = 1;
        goto LABEL_56;
      }
      memset_0(v30, 0, v29);
      memcpy_0(v31, *v6, *v4);
      if ( *v6 )
        aligned_free((void *)*v6);
      *v6 = v31;
      *v4 = v29;
    }
    if ( !v53
      || (v28 = HvApplyLogFilesToHiveImage((unsigned int)*v6, v13, (unsigned int)&v50, v12, (__int64)v52), v28 >= 0) )
    {
      LastError = 0;
      goto LABEL_55;
    }
LABEL_43:
    LastError = RtlNtStatusToDosError_0(v28);
    goto LABEL_55;
  }
LABEL_15:
  LastError = 1009;
LABEL_56:
  for ( j = 0; j != 2; j += v8 )
  {
    v33 = *(void **)&nNumberOfBytesToRead[4 * j];
    if ( v33 )
    {
      aligned_free(v33);
      v8 = 1;
    }
  }
  for ( k = 0; k != 2; k += v8 )
  {
    v35 = *(_QWORD *)&nNumberOfBytesToRead[2 * k - 4];
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      ORCloseFile(v35);
      v8 = 1;
    }
  }
  for ( m = 0; m != 2; m += v8 )
  {
    v37 = Block[m];
    if ( v37 )
    {
      aligned_free(v37);
      v8 = 1;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x140027b04  push    rbp
0x140027b06  push    rbx
0x140027b07  push    rsi
0x140027b08  push    rdi
0x140027b09  push    r12
0x140027b0b  push    r13
0x140027b0d  push    r14
0x140027b0f  push    r15
0x140027b11  lea     rbp, [rsp-58h]
0x140027b16  sub     rsp, 158h
0x140027b1d  mov     rax, cs:__security_cookie
0x140027b24  xor     rax, rsp
0x140027b27  mov     [rbp+90h+var_50], rax
0x140027b2b  xorps   xmm0, xmm0
0x140027b2e  mov     [rsp+190h+var_128], rdx
0x140027b33  xorps   xmm1, xmm1
0x140027b36  mov     [rsp+190h+var_130], rcx
0x140027b3b  mov     r15, rdx
0x140027b3e  mov     [rsp+190h+NumberOfBytesRead], 0
0x140027b46  xor     edx, edx; Val
0x140027b48  mov     qword ptr [rsp+190h+FileSize], 0
0x140027b51  mov     rbx, r8
0x140027b54  mov     r14, rcx
0x140027b57  lea     rcx, [rbp+90h+var_B0]; void *
0x140027b5b  mov     r12, r9
0x140027b5e  movups  [rbp+90h+var_110], xmm0
0x140027b62  lea     r8d, [rdx+5Ch]; Size
0x140027b66  movups  [rbp+90h+var_E0], xmm1
0x140027b6a  movups  [rbp+90h+var_D0], xmm1
0x140027b6e  movups  [rbp+90h+var_C0], xmm1
0x140027b72  movups  xmmword ptr [rbp+90h+nNumberOfBytesToRead], xmm0
0x140027b76  movups  [rbp+90h+var_F0], xmm0
0x140027b7a  movups  xmmword ptr [rsp+190h+Block], xmm0
0x140027b7f  call    memset_0
0x140027b84  mov     eax, 1000h
0x140027b89  mov     r10d, 1
0x140027b8f  cmp     [r15], eax
0x140027b92  jb      short loc_140027C12
0x140027b94  mov     rdi, [r14]
0x140027b97  mov     esi, [rdi+28h]
0x140027b9a  lea     r9d, [rsi+1000h]
0x140027ba1  cmp     r9d, eax
0x140027ba4  jb      short loc_140027C12
0x140027ba6  mov     rcx, rdi
0x140027ba9  call    HvIsInPlaceBaseBlockValid
0x140027bae  mov     edx, 0FFFFFFFFh
0x140027bb3  test    al, al
0x140027bb5  jz      short loc_140027BD8
0x140027bb7  mov     rax, [rdi+0Ch]
0x140027bbb  mov     [rsp+190h+var_140], rax
0x140027bc0  mov     eax, [rdi+8]
0x140027bc3  mov     [rsp+190h+var_150], r10b
0x140027bc8  cmp     [rdi+4], eax
0x140027bcb  jnz     short loc_140027C3A
0x140027bcd  cmp     r9d, [r15]
0x140027bd0  jbe     loc_140027E1B
0x140027bd6  jmp     short loc_140027C12
0x140027bd8  xor     al, al
0x140027bda  xor     esi, esi
0x140027bdc  mov     [rsp+190h+var_150], al
0x140027be0  xor     eax, eax
0x140027be2  xor     ecx, ecx
0x140027be4  xor     eax, [rdi+rcx*4]
0x140027be7  add     rcx, r10
0x140027bea  cmp     rcx, 7Fh
0x140027bee  jnz     short loc_140027BE4
0x140027bf0  cmp     eax, edx
0x140027bf2  jnz     short loc_140027BFB
0x140027bf4  mov     eax, 0FFFFFFFEh
0x140027bf9  jmp     short loc_140027C01
0x140027bfb  test    eax, eax
0x140027bfd  cmovz   eax, r10d
0x140027c01  cmp     eax, [rdi+1FCh]
0x140027c07  jz      short loc_140027C31
0x140027c09  cmp     dword ptr [r15], 1020h
0x140027c10  jnb     short loc_140027C1C
0x140027c12  mov     ebx, 3F1h
0x140027c17  jmp     loc_140027E95
0x140027c1c  cmp     dword ptr [rdi+1000h], 6E696268h
0x140027c26  jnz     short loc_140027C12
0x140027c28  mov     rax, [rdi+1014h]
0x140027c2f  jmp     short loc_140027C35
0x140027c31  mov     rax, [rdi+0Ch]
0x140027c35  mov     [rsp+190h+var_140], rax
0x140027c3a  lea     r8, [rsp+190h+Block]
0x140027c3f  mov     rdx, rbx; Source
0x140027c42  mov     rcx, r12; hFile
0x140027c45  call    ConstructLogPaths
0x140027c4a  mov     ebx, eax
0x140027c4c  mov     r10d, 1
0x140027c52  test    eax, eax
0x140027c54  jnz     loc_140027E95
0x140027c5a  xor     r13d, r13d
0x140027c5d  xor     r14d, r14d
0x140027c60  mov     rcx, [rsp+r14*8+190h+Block]
0x140027c65  lea     r12, [rbp+90h+var_110]
0x140027c69  lea     r12, [r12+r13*8]
0x140027c6d  mov     r15d, r13d
0x140027c70  mov     r9d, r10d
0x140027c73  mov     [rsp+190h+lpOverlapped], r12
0x140027c78  mov     r8d, 3
0x140027c7e  mov     edx, r10d
0x140027c81  call    ORCreateFile
0x140027c86  mov     ebx, eax
0x140027c88  cmp     eax, 2
0x140027c8b  jz      loc_140027D9A
0x140027c91  test    eax, eax
0x140027c93  jnz     loc_140027E8F
0x140027c99  mov     rax, [r12]
0x140027c9d  lea     rdx, [rsp+190h+FileSize]; lpFileSize
0x140027ca2  mov     rcx, rax; hFile
0x140027ca5  mov     [rsp+190h+hFile], rax
0x140027caa  call    cs:__imp_GetFileSizeEx
0x140027cb1  nop     dword ptr [rax+rax+00h]
0x140027cb6  test    eax, eax
0x140027cb8  jnz     short loc_140027CC8
0x140027cba  call    cs:__imp_GetLastError
0x140027cc1  nop     dword ptr [rax+rax+00h]
0x140027cc6  mov     ebx, eax
0x140027cc8  test    ebx, ebx
0x140027cca  jnz     loc_140027E8F
0x140027cd0  mov     rax, qword ptr [rsp+190h+FileSize]
0x140027cd5  mov     ecx, 0FFFFFFFFh
0x140027cda  cmp     rax, rcx
0x140027cdd  jle     short loc_140027CE6
0x140027cdf  mov     eax, ecx
0x140027ce1  mov     qword ptr [rsp+190h+FileSize], rcx
0x140027ce6  mov     r12, r15
0x140027ce9  lea     r15, [rbp+90h+nNumberOfBytesToRead]
0x140027ced  shl     r12, 4
0x140027cf1  add     r15, r12
0x140027cf4  mov     [rbp+r12+90h+nNumberOfBytesToRead+8], eax
0x140027cf9  test    eax, eax
0x140027cfb  jz      short loc_140027D63
0x140027cfd  mov     edx, 10h; Alignment
0x140027d02  mov     ecx, eax; Size
0x140027d04  mov     ebx, eax
0x140027d06  call    _o__aligned_malloc_0
0x140027d0b  mov     [r15], rax
0x140027d0e  test    rax, rax
0x140027d11  jz      loc_140027DC2
0x140027d17  mov     r8d, ebx; Size
0x140027d1a  xor     edx, edx; Val
0x140027d1c  mov     rcx, rax; void *
0x140027d1f  call    memset_0
0x140027d24  mov     r8d, [rbp+r12+90h+nNumberOfBytesToRead+8]; nNumberOfBytesToRead
0x140027d29  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140027d2e  mov     rdx, [r15]; lpBuffer
0x140027d31  xor     ebx, ebx
0x140027d33  mov     rcx, [rsp+190h+hFile]; hFile
0x140027d38  mov     [rsp+190h+lpOverlapped], rbx; lpOverlapped
0x140027d3d  call    cs:__imp_ReadFile
0x140027d44  nop     dword ptr [rax+rax+00h]
0x140027d49  test    eax, eax
0x140027d4b  jnz     short loc_140027D5B
0x140027d4d  call    cs:__imp_GetLastError
0x140027d54  nop     dword ptr [rax+rax+00h]
0x140027d59  mov     ebx, eax
0x140027d5b  test    ebx, ebx
0x140027d5d  jnz     loc_140027E8F
0x140027d63  lea     rdx, ds:0[r13*2]
0x140027d6b  mov     r10d, 1
0x140027d71  add     rdx, r13
0x140027d74  lea     rax, HiveRecoverReadRoutine
0x140027d7b  mov     qword ptr [rbp+rdx*8+90h+var_E0+8], rax
0x140027d80  mov     eax, r14d
0x140027d83  neg     eax
0x140027d85  mov     qword ptr [rbp+rdx*8+90h+var_D0], r15
0x140027d8a  sbb     ecx, ecx
0x140027d8c  neg     ecx
0x140027d8e  add     ecx, 4
0x140027d91  mov     dword ptr [rbp+rdx*8+90h+var_E0], ecx
0x140027d95  add     r13d, r10d
0x140027d98  jmp     short loc_140027DA0
0x140027d9a  mov     r10d, 1
0x140027da0  add     r14d, r10d
0x140027da3  cmp     r14d, 2
0x140027da7  jb      loc_140027C60
0x140027dad  test    r13d, r13d
0x140027db0  jz      loc_140027C12
0x140027db6  mov     al, [rsp+190h+var_150]
0x140027dba  test    al, al
0x140027dbc  jnz     short loc_140027DCC
0x140027dbe  xor     edx, edx
0x140027dc0  jmp     short loc_140027DD1
0x140027dc2  mov     ebx, 0Eh
0x140027dc7  jmp     loc_140027E8F
0x140027dcc  mov     edx, [rdi+8]
0x140027dcf  xor     edi, edi
0x140027dd1  lea     rcx, [rbp+90h+var_B0]
0x140027dd5  mov     [rsp+190h+var_160], rdi
0x140027dda  mov     [rsp+190h+var_168], rcx
0x140027ddf  lea     r9, [rbp+90h+var_E0]
0x140027de3  xor     al, r10b
0x140027de6  mov     dword ptr [rsp+190h+lpOverlapped], r13d
0x140027deb  lea     rcx, [rsp+190h+var_140]
0x140027df0  mov     r8b, al
0x140027df3  call    HvAnalyzeLogFiles
0x140027df8  test    eax, eax
0x140027dfa  jns     short loc_140027E0A
0x140027dfc  mov     ecx, eax; Status
0x140027dfe  call    RtlNtStatusToDosError_0
0x140027e03  mov     ebx, eax
0x140027e05  jmp     loc_140027E8F
0x140027e0a  cmp     esi, [rbp+90h+var_70]
0x140027e0d  mov     r14, [rsp+190h+var_130]
0x140027e12  cmovb   esi, [rbp+90h+var_70]
0x140027e16  mov     r15, [rsp+190h+var_128]
0x140027e1b  add     esi, 1000h
0x140027e21  cmp     [r15], esi
0x140027e24  jnb     short loc_140027E6A
0x140027e26  mov     edx, 10h; Alignment
0x140027e2b  mov     ecx, esi; Size
0x140027e2d  mov     edi, esi
0x140027e2f  call    _o__aligned_malloc_0
0x140027e34  mov     rbx, rax
0x140027e37  test    rax, rax
0x140027e3a  jz      short loc_140027DC2
0x140027e3c  mov     r8d, edi; Size
0x140027e3f  xor     edx, edx; Val
0x140027e41  mov     rcx, rax; void *
0x140027e44  call    memset_0
0x140027e49  mov     r8d, [r15]; Size
0x140027e4c  mov     rcx, rbx; void *
0x140027e4f  mov     rdx, [r14]; Src
0x140027e52  call    memcpy_0
0x140027e57  mov     rcx, [r14]; Block
0x140027e5a  test    rcx, rcx
0x140027e5d  jz      short loc_140027E64
0x140027e5f  call    _aligned_free
0x140027e64  mov     [r14], rbx
0x140027e67  mov     [r15], esi
0x140027e6a  cmp     [rbp+90h+var_74], 0
0x140027e6e  jbe     short loc_140027E8D
0x140027e70  mov     rcx, [r14]
0x140027e73  lea     rax, [rbp+90h+var_B0]
0x140027e77  lea     r8, [rbp+90h+var_E0]
0x140027e7b  mov     [rsp+190h+lpOverlapped], rax
0x140027e80  call    HvApplyLogFilesToHiveImage
0x140027e85  test    eax, eax
0x140027e87  js      loc_140027DFC
0x140027e8d  xor     ebx, ebx
0x140027e8f  mov     r10d, 1
0x140027e95  xor     edi, edi
0x140027e97  mov     rax, rdi
0x140027e9a  add     rax, rax
0x140027e9d  mov     rcx, qword ptr [rbp+rax*8+90h+nNumberOfBytesToRead]; Block
0x140027ea2  test    rcx, rcx
0x140027ea5  jz      short loc_140027EB2
0x140027ea7  call    _aligned_free
0x140027eac  mov     r10d, 1
0x140027eb2  add     rdi, r10
0x140027eb5  cmp     rdi, 2
0x140027eb9  jnz     short loc_140027E97
0x140027ebb  xor     edi, edi
0x140027ebd  mov     rcx, qword ptr [rbp+rdi*8+90h+var_110]
0x140027ec2  lea     rax, [rcx-1]
0x140027ec6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140027eca  ja      short loc_140027ED7
0x140027ecc  call    ORCloseFile
0x140027ed1  mov     r10d, 1
0x140027ed7  add     rdi, r10
0x140027eda  cmp     rdi, 2
0x140027ede  jnz     short loc_140027EBD
0x140027ee0  xor     edi, edi
0x140027ee2  mov     rcx, [rsp+rdi*8+190h+Block]; Block
0x140027ee7  test    rcx, rcx
0x140027eea  jz      short loc_140027EF7
0x140027eec  call    _aligned_free
0x140027ef1  mov     r10d, 1
0x140027ef7  add     rdi, r10
0x140027efa  cmp     rdi, 2
0x140027efe  jnz     short loc_140027EE2
0x140027f00  mov     eax, ebx
0x140027f02  mov     rcx, [rbp+90h+var_50]
0x140027f06  xor     rcx, rsp; StackCookie
0x140027f09  call    __security_check_cookie
0x140027f0e  add     rsp, 158h
0x140027f15  pop     r15
0x140027f17  pop     r14
0x140027f19  pop     r13
0x140027f1b  pop     r12
0x140027f1d  pop     rdi
0x140027f1e  pop     rsi
0x140027f1f  pop     rbx
0x140027f20  pop     rbp
0x140027f21  retn
```
