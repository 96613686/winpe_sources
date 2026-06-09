# ValidateHiveAndRecoverFromLog

- ea: `0x18003d768`
- end: `0x18003db8c`
- name: `ValidateHiveAndRecoverFromLog`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18003b6f4`

## callees

- `0x180002690`
- `0x180003166`
- `0x180003172`
- `0x1800032b8`
- `0x180003bb5`
- `0x18003d01c`
- `0x18003d768`
- `0x18003e93c`
- `0x18003e97c`
- `0x180045240`
- `0x18004529c`
- `0x180045784`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003d908`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003d908`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003d99b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003d99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9ab`
- `ntdll!RtlNtStatusToDosError` at `0x18003da5c`
- `ntdll!RtlNtStatusToDosError` at `0x18003da5c`

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
  __int64 v18; // r8
  __int64 v19; // r13
  __int64 v20; // r14
  unsigned int v21; // eax
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
  v19 = 0;
  v20 = 0;
  do
  {
    v21 = ORCreateFile((const WCHAR *)Block[v20], 1u, v18, 1u, &nNumberOfBytesToRead[2 * v19 - 4]);
    LastError = v21;
    if ( v21 == 2 )
    {
      v8 = 1;
    }
    else
    {
      if ( v21 )
        goto LABEL_55;
      hFile = *(HANDLE *)&nNumberOfBytesToRead[2 * v19 - 4];
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
      v23 = (LPVOID *)&nNumberOfBytesToRead[4 * (unsigned int)v19];
      nNumberOfBytesToRead[4 * (unsigned int)v19 + 2] = LowPart;
      if ( LowPart )
      {
        v24 = LowPart;
        v25 = o__aligned_malloc_0(LowPart, 0x10u);
        *v23 = v25;
        if ( !v25 )
          goto LABEL_40;
        memset_0(v25, 0, v24);
        LastError = 0;
        if ( !ReadFile(hFile, *v23, nNumberOfBytesToRead[4 * (unsigned int)v19 + 2], &NumberOfBytesRead, 0) )
          LastError = GetLastError();
        if ( LastError )
          goto LABEL_55;
      }
      v8 = 1;
      v26 = 3 * v19;
      *((_QWORD *)&v50 + v26 + 1) = HiveRecoverReadRoutine;
      *((_QWORD *)v51 + v26) = v23;
      *((_DWORD *)&v51[-1] + 2 * v26) = ((_DWORD)v20 != 0) + 4;
      v19 = (unsigned int)(v19 + 1);
    }
    v20 = (unsigned int)(v20 + 1);
  }
  while ( (unsigned int)v20 < 2 );
  if ( (_DWORD)v19 )
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
    LOBYTE(v18) = v39 ^ 1;
    v28 = HvAnalyzeLogFiles((unsigned int)&v42, v27, v18, (unsigned int)&v50, v19, (__int64)v52, v9);
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
    LastError = RtlNtStatusToDosError(v28);
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
0x18003d768  push    rbp
0x18003d76a  push    rbx
0x18003d76b  push    rsi
0x18003d76c  push    rdi
0x18003d76d  push    r12
0x18003d76f  push    r13
0x18003d771  push    r14
0x18003d773  push    r15
0x18003d775  lea     rbp, [rsp-58h]
0x18003d77a  sub     rsp, 158h
0x18003d781  mov     rax, cs:__security_cookie
0x18003d788  xor     rax, rsp
0x18003d78b  mov     [rbp+90h+var_50], rax
0x18003d78f  xorps   xmm0, xmm0
0x18003d792  mov     [rsp+190h+var_128], rdx
0x18003d797  xorps   xmm1, xmm1
0x18003d79a  mov     [rsp+190h+var_130], rcx
0x18003d79f  mov     r15, rdx
0x18003d7a2  mov     [rsp+190h+NumberOfBytesRead], 0
0x18003d7aa  xor     edx, edx; Val
0x18003d7ac  mov     qword ptr [rsp+190h+FileSize], 0
0x18003d7b5  mov     rbx, r8
0x18003d7b8  mov     r14, rcx
0x18003d7bb  lea     rcx, [rbp+90h+var_B0]; void *
0x18003d7bf  mov     r12, r9
0x18003d7c2  movups  [rbp+90h+var_110], xmm0
0x18003d7c6  lea     r8d, [rdx+5Ch]; Size
0x18003d7ca  movups  [rbp+90h+var_E0], xmm1
0x18003d7ce  movups  [rbp+90h+var_D0], xmm1
0x18003d7d2  movups  [rbp+90h+var_C0], xmm1
0x18003d7d6  movups  xmmword ptr [rbp+90h+nNumberOfBytesToRead], xmm0
0x18003d7da  movups  [rbp+90h+var_F0], xmm0
0x18003d7de  movups  xmmword ptr [rsp+190h+Block], xmm0
0x18003d7e3  call    memset_0
0x18003d7e8  mov     eax, 1000h
0x18003d7ed  mov     r10d, 1
0x18003d7f3  cmp     [r15], eax
0x18003d7f6  jb      short loc_18003D876
0x18003d7f8  mov     rdi, [r14]
0x18003d7fb  mov     esi, [rdi+28h]
0x18003d7fe  lea     r9d, [rsi+1000h]
0x18003d805  cmp     r9d, eax
0x18003d808  jb      short loc_18003D876
0x18003d80a  mov     rcx, rdi
0x18003d80d  call    HvIsInPlaceBaseBlockValid
0x18003d812  mov     edx, 0FFFFFFFFh
0x18003d817  test    al, al
0x18003d819  jz      short loc_18003D83C
0x18003d81b  mov     rax, [rdi+0Ch]
0x18003d81f  mov     [rsp+190h+var_140], rax
0x18003d824  mov     eax, [rdi+8]
0x18003d827  mov     [rsp+190h+var_150], r10b
0x18003d82c  cmp     [rdi+4], eax
0x18003d82f  jnz     short loc_18003D89E
0x18003d831  cmp     r9d, [r15]
0x18003d834  jbe     loc_18003DA80
0x18003d83a  jmp     short loc_18003D876
0x18003d83c  xor     al, al
0x18003d83e  xor     esi, esi
0x18003d840  mov     [rsp+190h+var_150], al
0x18003d844  xor     eax, eax
0x18003d846  xor     ecx, ecx
0x18003d848  xor     eax, [rdi+rcx*4]
0x18003d84b  add     rcx, r10
0x18003d84e  cmp     rcx, 7Fh
0x18003d852  jnz     short loc_18003D848
0x18003d854  cmp     eax, edx
0x18003d856  jnz     short loc_18003D85F
0x18003d858  mov     eax, 0FFFFFFFEh
0x18003d85d  jmp     short loc_18003D865
0x18003d85f  test    eax, eax
0x18003d861  cmovz   eax, r10d
0x18003d865  cmp     eax, [rdi+1FCh]
0x18003d86b  jz      short loc_18003D895
0x18003d86d  cmp     dword ptr [r15], 1020h
0x18003d874  jnb     short loc_18003D880
0x18003d876  mov     ebx, 3F1h
0x18003d87b  jmp     loc_18003DAFE
0x18003d880  cmp     dword ptr [rdi+1000h], 6E696268h
0x18003d88a  jnz     short loc_18003D876
0x18003d88c  mov     rax, [rdi+1014h]
0x18003d893  jmp     short loc_18003D899
0x18003d895  mov     rax, [rdi+0Ch]
0x18003d899  mov     [rsp+190h+var_140], rax
0x18003d89e  lea     r8, [rsp+190h+Block]
0x18003d8a3  mov     rdx, rbx; Source
0x18003d8a6  mov     rcx, r12; hFile
0x18003d8a9  call    ConstructLogPaths
0x18003d8ae  mov     ebx, eax
0x18003d8b0  mov     r10d, 1
0x18003d8b6  test    eax, eax
0x18003d8b8  jnz     loc_18003DAFE
0x18003d8be  xor     r13d, r13d
0x18003d8c1  xor     r14d, r14d
0x18003d8c4  mov     rcx, [rsp+r14*8+190h+Block]
0x18003d8c9  lea     r12, [rbp+90h+var_110]
0x18003d8cd  lea     r12, [r12+r13*8]
0x18003d8d1  mov     r15d, r13d
0x18003d8d4  mov     r9d, r10d
0x18003d8d7  mov     [rsp+190h+lpOverlapped], r12
0x18003d8dc  mov     edx, r10d
0x18003d8df  call    ORCreateFile
0x18003d8e4  mov     ebx, eax
0x18003d8e6  cmp     eax, 2
0x18003d8e9  jz      loc_18003D9F8
0x18003d8ef  test    eax, eax
0x18003d8f1  jnz     loc_18003DAF8
0x18003d8f7  mov     rax, [r12]
0x18003d8fb  lea     rdx, [rsp+190h+FileSize]; lpFileSize
0x18003d900  mov     rcx, rax; hFile
0x18003d903  mov     [rsp+190h+hFile], rax
0x18003d908  call    cs:__imp_GetFileSizeEx
0x18003d90f  nop     dword ptr [rax+rax+00h]
0x18003d914  test    eax, eax
0x18003d916  jnz     short loc_18003D926
0x18003d918  call    cs:__imp_GetLastError
0x18003d91f  nop     dword ptr [rax+rax+00h]
0x18003d924  mov     ebx, eax
0x18003d926  test    ebx, ebx
0x18003d928  jnz     loc_18003DAF8
0x18003d92e  mov     rax, qword ptr [rsp+190h+FileSize]
0x18003d933  mov     ecx, 0FFFFFFFFh
0x18003d938  cmp     rax, rcx
0x18003d93b  jle     short loc_18003D944
0x18003d93d  mov     eax, ecx
0x18003d93f  mov     qword ptr [rsp+190h+FileSize], rcx
0x18003d944  mov     r12, r15
0x18003d947  lea     r15, [rbp+90h+nNumberOfBytesToRead]
0x18003d94b  shl     r12, 4
0x18003d94f  add     r15, r12
0x18003d952  mov     [rbp+r12+90h+nNumberOfBytesToRead+8], eax
0x18003d957  test    eax, eax
0x18003d959  jz      short loc_18003D9C1
0x18003d95b  mov     edx, 10h; Alignment
0x18003d960  mov     ecx, eax; Size
0x18003d962  mov     ebx, eax
0x18003d964  call    _o__aligned_malloc_0
0x18003d969  mov     [r15], rax
0x18003d96c  test    rax, rax
0x18003d96f  jz      loc_18003DA20
0x18003d975  mov     r8d, ebx; Size
0x18003d978  xor     edx, edx; Val
0x18003d97a  mov     rcx, rax; void *
0x18003d97d  call    memset_0
0x18003d982  mov     r8d, [rbp+r12+90h+nNumberOfBytesToRead+8]; nNumberOfBytesToRead
0x18003d987  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003d98c  mov     rdx, [r15]; lpBuffer
0x18003d98f  xor     ebx, ebx
0x18003d991  mov     rcx, [rsp+190h+hFile]; hFile
0x18003d996  mov     [rsp+190h+lpOverlapped], rbx; lpOverlapped
0x18003d99b  call    cs:__imp_ReadFile
0x18003d9a2  nop     dword ptr [rax+rax+00h]
0x18003d9a7  test    eax, eax
0x18003d9a9  jnz     short loc_18003D9B9
0x18003d9ab  call    cs:__imp_GetLastError
0x18003d9b2  nop     dword ptr [rax+rax+00h]
0x18003d9b7  mov     ebx, eax
0x18003d9b9  test    ebx, ebx
0x18003d9bb  jnz     loc_18003DAF8
0x18003d9c1  lea     rdx, ds:0[r13*2]
0x18003d9c9  mov     r10d, 1
0x18003d9cf  add     rdx, r13
0x18003d9d2  lea     rax, HiveRecoverReadRoutine
0x18003d9d9  mov     qword ptr [rbp+rdx*8+90h+var_E0+8], rax
0x18003d9de  mov     eax, r14d
0x18003d9e1  neg     eax
0x18003d9e3  mov     qword ptr [rbp+rdx*8+90h+var_D0], r15
0x18003d9e8  sbb     ecx, ecx
0x18003d9ea  neg     ecx
0x18003d9ec  add     ecx, 4
0x18003d9ef  mov     dword ptr [rbp+rdx*8+90h+var_E0], ecx
0x18003d9f3  add     r13d, r10d
0x18003d9f6  jmp     short loc_18003D9FE
0x18003d9f8  mov     r10d, 1
0x18003d9fe  add     r14d, r10d
0x18003da01  cmp     r14d, 2
0x18003da05  jb      loc_18003D8C4
0x18003da0b  test    r13d, r13d
0x18003da0e  jz      loc_18003D876
0x18003da14  mov     al, [rsp+190h+var_150]
0x18003da18  test    al, al
0x18003da1a  jnz     short loc_18003DA2A
0x18003da1c  xor     edx, edx
0x18003da1e  jmp     short loc_18003DA2F
0x18003da20  mov     ebx, 0Eh
0x18003da25  jmp     loc_18003DAF8
0x18003da2a  mov     edx, [rdi+8]
0x18003da2d  xor     edi, edi
0x18003da2f  lea     rcx, [rbp+90h+var_B0]
0x18003da33  mov     [rsp+190h+var_160], rdi
0x18003da38  mov     [rsp+190h+var_168], rcx
0x18003da3d  lea     r9, [rbp+90h+var_E0]
0x18003da41  xor     al, r10b
0x18003da44  mov     dword ptr [rsp+190h+lpOverlapped], r13d
0x18003da49  lea     rcx, [rsp+190h+var_140]
0x18003da4e  mov     r8b, al
0x18003da51  call    HvAnalyzeLogFiles
0x18003da56  test    eax, eax
0x18003da58  jns     short loc_18003DA6F
0x18003da5a  mov     ecx, eax; Status
0x18003da5c  call    cs:__imp_RtlNtStatusToDosError
0x18003da63  nop     dword ptr [rax+rax+00h]
0x18003da68  mov     ebx, eax
0x18003da6a  jmp     loc_18003DAF8
0x18003da6f  cmp     esi, [rbp+90h+var_70]
0x18003da72  mov     r14, [rsp+190h+var_130]
0x18003da77  cmovb   esi, [rbp+90h+var_70]
0x18003da7b  mov     r15, [rsp+190h+var_128]
0x18003da80  add     esi, 1000h
0x18003da86  cmp     [r15], esi
0x18003da89  jnb     short loc_18003DAD3
0x18003da8b  mov     edx, 10h; Alignment
0x18003da90  mov     ecx, esi; Size
0x18003da92  mov     edi, esi
0x18003da94  call    _o__aligned_malloc_0
0x18003da99  mov     rbx, rax
0x18003da9c  test    rax, rax
0x18003da9f  jz      loc_18003DA20
0x18003daa5  mov     r8d, edi; Size
0x18003daa8  xor     edx, edx; Val
0x18003daaa  mov     rcx, rax; void *
0x18003daad  call    memset_0
0x18003dab2  mov     r8d, [r15]; Size
0x18003dab5  mov     rcx, rbx; void *
0x18003dab8  mov     rdx, [r14]; Src
0x18003dabb  call    memcpy_0
0x18003dac0  mov     rcx, [r14]; Block
0x18003dac3  test    rcx, rcx
0x18003dac6  jz      short loc_18003DACD
0x18003dac8  call    _aligned_free
0x18003dacd  mov     [r14], rbx
0x18003dad0  mov     [r15], esi
0x18003dad3  cmp     [rbp+90h+var_74], 0
0x18003dad7  jbe     short loc_18003DAF6
0x18003dad9  mov     rcx, [r14]
0x18003dadc  lea     rax, [rbp+90h+var_B0]
0x18003dae0  lea     r8, [rbp+90h+var_E0]
0x18003dae4  mov     [rsp+190h+lpOverlapped], rax
0x18003dae9  call    HvApplyLogFilesToHiveImage
0x18003daee  test    eax, eax
0x18003daf0  js      loc_18003DA5A
0x18003daf6  xor     ebx, ebx
0x18003daf8  mov     r10d, 1
0x18003dafe  xor     edi, edi
0x18003db00  mov     rax, rdi
0x18003db03  add     rax, rax
0x18003db06  mov     rcx, qword ptr [rbp+rax*8+90h+nNumberOfBytesToRead]; Block
0x18003db0b  test    rcx, rcx
0x18003db0e  jz      short loc_18003DB1B
0x18003db10  call    _aligned_free
0x18003db15  mov     r10d, 1
0x18003db1b  add     rdi, r10
0x18003db1e  cmp     rdi, 2
0x18003db22  jnz     short loc_18003DB00
0x18003db24  xor     edi, edi
0x18003db26  mov     rcx, qword ptr [rbp+rdi*8+90h+var_110]
0x18003db2b  lea     rax, [rcx-1]
0x18003db2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003db33  ja      short loc_18003DB40
0x18003db35  call    ORCloseFile
0x18003db3a  mov     r10d, 1
0x18003db40  add     rdi, r10
0x18003db43  cmp     rdi, 2
0x18003db47  jnz     short loc_18003DB26
0x18003db49  xor     edi, edi
0x18003db4b  mov     rcx, [rsp+rdi*8+190h+Block]; Block
0x18003db50  test    rcx, rcx
0x18003db53  jz      short loc_18003DB60
0x18003db55  call    _aligned_free
0x18003db5a  mov     r10d, 1
0x18003db60  add     rdi, r10
0x18003db63  cmp     rdi, 2
0x18003db67  jnz     short loc_18003DB4B
0x18003db69  mov     eax, ebx
0x18003db6b  mov     rcx, [rbp+90h+var_50]
0x18003db6f  xor     rcx, rsp; StackCookie
0x18003db72  call    __security_check_cookie
0x18003db77  add     rsp, 158h
0x18003db7e  pop     r15
0x18003db80  pop     r14
0x18003db82  pop     r13
0x18003db84  pop     r12
0x18003db86  pop     rdi
0x18003db87  pop     rsi
0x18003db88  pop     rbx
0x18003db89  pop     rbp
0x18003db8a  retn
```
