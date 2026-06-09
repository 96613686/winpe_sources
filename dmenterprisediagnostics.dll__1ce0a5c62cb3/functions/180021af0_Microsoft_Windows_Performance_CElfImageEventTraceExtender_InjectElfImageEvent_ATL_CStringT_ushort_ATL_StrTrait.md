# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180021af0`
- end: `0x180021ed1`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `993`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x1800029a9`
- `0x1800029b5`
- `0x180017ea4`
- `0x180020ca0`
- `0x180021abc`
- `0x180021af0`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180021c54`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180021c54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ec4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021b4a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021b4a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021c67`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021c67`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180021d09`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180021d09`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021b8e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021d33`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021b8e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021d33`
- `bcrypt!BCryptFinishHash` at `0x180021dc3`
- `bcrypt!BCryptFinishHash` at `0x180021dc3`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HANDLE FileW; // rsi
  LPCWSTR v10; // rax
  int v11; // ecx
  __int64 v12; // r12
  _QWORD *v13; // r14
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  DWORD FileSize; // eax
  LONG v17; // r8d
  LONG v18; // r15d
  unsigned __int16 v19; // dx
  int v20; // ebx
  size_t v22; // r14
  __int64 v23; // rcx
  _BYTE v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int128 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  LONG lDistanceToMove[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v30[16]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+90h] [rbp-70h]
  __int16 v32; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[2]; // [rsp+A2h] [rbp-5Eh] BYREF
  int v34; // [rsp+A4h] [rbp-5Ch]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  int v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F4h] [rbp-Ch]
  unsigned __int8 v40[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v41; // [rsp+110h] [rbp+10h]

  FileW = CreateFileW(*a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  NumberOfBytesRead = 0;
  v31 = 0;
  Buffer = 0;
  *(_OWORD *)lDistanceToMove = 0;
  *(_OWORD *)v30 = 0;
  if ( !ReadFile(FileW, &Buffer, 0x34u, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != 52
    || memcmp_0(&Buffer, &qword_18002B518, 4u)
    || WORD2(Buffer) != 257
    || BYTE6(Buffer) != 1
    || *(_WORD *)&v30[10] != 32 )
  {
LABEL_20:
    CloseHandle(FileW);
    return 2147500037LL;
  }
  v10 = *a2;
  v24[0] = 0;
  v11 = *((_DWORD *)v10 - 4) + 32 * *(unsigned __int16 *)&v30[12];
  v26 = 0;
  v27 = 0;
  std::vector<char>::_Construct_n<char const &>(&v26, (unsigned int)(2 * v11 + 94), v24);
  v12 = v26;
  v13 = (_QWORD *)(v26 + 28);
  v14 = (unsigned __int16)(*(*a2 - 8) + 1);
  v15 = v26 + 28 + ((unsigned __int64)*(unsigned __int16 *)&v30[12] << 6);
  *(_WORD *)(v26 + 26) = v14;
  _o_wcscpy_s(v15, v14, *a2);
  *(_DWORD *)v12 = 0;
  FileSize = GetFileSize(FileW, 0);
  *(_DWORD *)(v12 + 4) = FileSize;
  if ( FileSize == -1 )
    goto LABEL_19;
  *(_WORD *)(v12 + 24) = *(_WORD *)&v30[12];
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)&Buffer,
    0x10u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)lDistanceToMove + 2,
    2u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    (const unsigned __int8 *)&lDistanceToMove[1],
    4u);
  Microsoft::Windows::Performance::CryptographicHasher::Hash(
    (Microsoft::Windows::Performance::CryptographicHasher *)a3,
    &v30[4],
    4u);
  v17 = lDistanceToMove[3];
  v18 = lDistanceToMove[3];
  v19 = *(_WORD *)&v30[10];
  while ( v18 != v17 + v19 * *(unsigned __int16 *)&v30[12] )
  {
    *(_OWORD *)v40 = 0;
    v41 = 0;
    if ( SetFilePointer(FileW, v18, 0, 0) == -1
      || !ReadFile(FileW, v40, 0x20u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 32 )
    {
      v20 = -2147467259;
LABEL_27:
      std::vector<unsigned char>::_Tidy(&v26);
      CloseHandle(FileW);
      return (unsigned int)v20;
    }
    *v13 = *(unsigned int *)v40;
    v13[2] = *(unsigned int *)&v40[4];
    v13[3] = *(unsigned int *)&v40[8];
    v13[4] = *(unsigned int *)&v40[12];
    v13[5] = (unsigned int)v41;
    v13[6] = DWORD1(v41);
    v13[1] = DWORD2(v41);
    v13[7] = HIDWORD(v41);
    v13 += 8;
    Microsoft::Windows::Performance::CryptographicHasher::Hash(
      (Microsoft::Windows::Performance::CryptographicHasher *)a3,
      v40,
      0x20u);
    v19 = *(_WORD *)&v30[10];
    v17 = lDistanceToMove[3];
    v18 += *(unsigned __int16 *)&v30[10];
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_19;
  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), *(PUCHAR *)(a3 + 32), *(_DWORD *)(a3 + 40), 0) < 0 )
  {
    *(_BYTE *)a3 = 0;
    goto LABEL_19;
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_19;
  v22 = 16;
  if ( *(_DWORD *)(a3 + 40) <= 0x10u )
    v22 = *(unsigned int *)(a3 + 40);
  memcpy_0((void *)(v12 + 8), *(const void **)(a3 + 32), v22);
  if ( v22 != 16 )
  {
LABEL_19:
    std::vector<unsigned char>::_Tidy(&v26);
    goto LABEL_20;
  }
  memset_0(v33, 0, 0x56u);
  v32 = 4;
  v37 = v26;
  v23 = *(_QWORD *)(a1 + 16);
  v38 = DWORD2(v26) - v26;
  v39 = a5;
  v35 = a4;
  v36 = ElfImageGuid;
  v34 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD))(*(_QWORD *)v23 + 192LL))(v23, &v32, 0, 0);
  if ( v20 < 0 )
    goto LABEL_27;
  std::vector<unsigned char>::_Tidy(&v26);
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x180021af0  push    rbp
0x180021af2  push    rbx
0x180021af3  push    rsi
0x180021af4  push    rdi
0x180021af5  push    r12
0x180021af7  push    r13
0x180021af9  push    r14
0x180021afb  push    r15
0x180021afd  lea     rbp, [rsp-38h]
0x180021b02  sub     rsp, 138h
0x180021b09  mov     rax, cs:__security_cookie
0x180021b10  xor     rax, rsp
0x180021b13  mov     [rbp+70h+var_50], rax
0x180021b17  mov     r15, rdx
0x180021b1a  xor     r14d, r14d
0x180021b1d  mov     rbx, r9
0x180021b20  mov     [rsp+170h+hTemplateFile], r14; hTemplateFile
0x180021b25  mov     rdi, r8
0x180021b28  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180021b30  mov     r13, rcx
0x180021b33  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x180021b3b  mov     rcx, [r15]; lpFileName
0x180021b3e  lea     r8d, [r14+7]; dwShareMode
0x180021b42  xor     r9d, r9d; lpSecurityAttributes
0x180021b45  mov     edx, 80000000h; dwDesiredAccess
0x180021b4a  call    cs:__imp_CreateFileW
0x180021b50  mov     rsi, rax
0x180021b53  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021b57  jz      loc_180021DE3
0x180021b5d  xorps   xmm0, xmm0
0x180021b60  mov     [rsp+170h+NumberOfBytesRead], r14d
0x180021b65  xor     eax, eax
0x180021b67  mov     qword ptr [rsp+170h+dwCreationDisposition], r14; lpOverlapped
0x180021b6c  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021b71  mov     [rbp+70h+var_E0], eax
0x180021b74  lea     r8d, [r14+34h]; nNumberOfBytesToRead
0x180021b78  mov     rcx, rsi; hFile
0x180021b7b  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x180021b80  movups  [rsp+170h+Buffer], xmm0
0x180021b85  movups  xmmword ptr [rsp+170h+lDistanceToMove], xmm0
0x180021b8a  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x180021b8e  call    cs:__imp_ReadFile
0x180021b94  test    eax, eax
0x180021b96  jz      loc_180021DDA
0x180021b9c  cmp     [rsp+170h+NumberOfBytesRead], 34h ; '4'
0x180021ba1  jnz     loc_180021DDA
0x180021ba7  lea     r8d, [r14+4]; Size
0x180021bab  lea     rdx, qword_18002B518; Buf2
0x180021bb2  lea     rcx, [rsp+170h+Buffer]; Buf1
0x180021bb7  call    memcmp_0
0x180021bbc  test    eax, eax
0x180021bbe  jnz     loc_180021DDA
0x180021bc4  cmp     byte ptr [rsp+170h+Buffer+4], 1
0x180021bc9  jnz     loc_180021DDA
0x180021bcf  cmp     byte ptr [rsp+170h+Buffer+5], 1
0x180021bd4  jnz     loc_180021DDA
0x180021bda  cmp     byte ptr [rsp+170h+Buffer+6], 1
0x180021bdf  jnz     loc_180021DDA
0x180021be5  lea     eax, [r14+20h]
0x180021be9  cmp     ax, word ptr [rbp+70h+var_F0+0Ah]
0x180021bed  jnz     loc_180021DDA
0x180021bf3  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180021bf7  lea     r8, [rsp+170h+var_130]
0x180021bfc  mov     rax, [r15]
0x180021bff  xorps   xmm0, xmm0
0x180021c02  shl     ecx, 5
0x180021c05  mov     [rsp+170h+var_130], r14b
0x180021c0a  add     ecx, [rax-10h]
0x180021c0d  movdqu  [rsp+170h+var_128], xmm0
0x180021c13  mov     [rsp+170h+var_118], r14
0x180021c18  lea     edx, ds:5Eh[rcx*2]
0x180021c1f  lea     rcx, [rsp+170h+var_128]
0x180021c24  call    ??$_Construct_n@AEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBD@Z; std::vector<char>::_Construct_n<char const &>(unsigned __int64,char const &)
0x180021c29  mov     rax, [r15]
0x180021c2c  mov     r12, qword ptr [rsp+170h+var_128]
0x180021c31  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180021c35  shl     rcx, 6
0x180021c39  movzx   edx, word ptr [rax-10h]
0x180021c3d  inc     dx
0x180021c40  lea     r14, [r12+1Ch]
0x180021c45  movzx   edx, dx
0x180021c48  add     rcx, r14
0x180021c4b  mov     [r12+1Ah], dx
0x180021c51  mov     r8, [r15]
0x180021c54  call    cs:__imp__o_wcscpy_s
0x180021c5a  xor     edx, edx; lpFileSizeHigh
0x180021c5c  mov     dword ptr [r12], 0
0x180021c64  mov     rcx, rsi; hFile
0x180021c67  call    cs:__imp_GetFileSize
0x180021c6d  mov     [r12+4], eax
0x180021c72  cmp     eax, 0FFFFFFFFh
0x180021c75  jz      loc_180021DD0
0x180021c7b  movzx   eax, word ptr [rbp+70h+var_F0+0Ch]
0x180021c7f  lea     rdx, [rsp+170h+Buffer]; unsigned __int8 *
0x180021c84  mov     r8d, 10h; unsigned int
0x180021c8a  mov     [r12+18h], ax
0x180021c90  mov     rcx, rdi; this
0x180021c93  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180021c98  mov     r8d, 2; unsigned int
0x180021c9e  lea     rdx, [rsp+170h+lDistanceToMove+2]; unsigned __int8 *
0x180021ca3  mov     rcx, rdi; this
0x180021ca6  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180021cab  mov     r15d, 4
0x180021cb1  lea     rdx, [rsp+170h+lDistanceToMove+4]; unsigned __int8 *
0x180021cb6  mov     r8d, r15d; unsigned int
0x180021cb9  mov     rcx, rdi; this
0x180021cbc  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180021cc1  mov     r8d, r15d; unsigned int
0x180021cc4  lea     rdx, [rbp+70h+var_F0+4]; unsigned __int8 *
0x180021cc8  mov     rcx, rdi; this
0x180021ccb  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180021cd0  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180021cd5  mov     r15d, r8d
0x180021cd8  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180021cdc  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180021ce0  movzx   eax, dx
0x180021ce3  imul    ecx, eax
0x180021ce6  add     ecx, r8d
0x180021ce9  cmp     r15d, ecx
0x180021cec  jz      loc_180021DAC
0x180021cf2  xorps   xmm0, xmm0
0x180021cf5  xor     r9d, r9d; dwMoveMethod
0x180021cf8  xor     r8d, r8d; lpDistanceToMoveHigh
0x180021cfb  mov     edx, r15d; lDistanceToMove
0x180021cfe  mov     rcx, rsi; hFile
0x180021d01  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x180021d05  movups  [rbp+70h+var_60], xmm0
0x180021d09  call    cs:__imp_SetFilePointer
0x180021d0f  cmp     eax, 0FFFFFFFFh
0x180021d12  jz      loc_180021DA2
0x180021d18  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021d1d  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x180021d26  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x180021d2c  lea     rdx, [rbp+70h+var_70]; lpBuffer
0x180021d30  mov     rcx, rsi; hFile
0x180021d33  call    cs:__imp_ReadFile
0x180021d39  test    eax, eax
0x180021d3b  jz      short loc_180021DA2
0x180021d3d  cmp     [rsp+170h+NumberOfBytesRead], 20h ; ' '
0x180021d42  jnz     short loc_180021DA2
0x180021d44  mov     eax, dword ptr [rbp+70h+var_70]
0x180021d47  lea     rdx, [rbp+70h+var_70]; unsigned __int8 *
0x180021d4b  mov     [r14], rax
0x180021d4e  mov     r8d, 20h ; ' '; unsigned int
0x180021d54  mov     eax, dword ptr [rbp+70h+var_70+4]
0x180021d57  mov     rcx, rdi; this
0x180021d5a  mov     [r14+10h], rax
0x180021d5e  mov     eax, dword ptr [rbp+70h+var_70+8]
0x180021d61  mov     [r14+18h], rax
0x180021d65  mov     eax, dword ptr [rbp+70h+var_70+0Ch]
0x180021d68  mov     [r14+20h], rax
0x180021d6c  mov     eax, dword ptr [rbp+70h+var_60]
0x180021d6f  mov     [r14+28h], rax
0x180021d73  mov     eax, dword ptr [rbp+70h+var_60+4]
0x180021d76  mov     [r14+30h], rax
0x180021d7a  mov     eax, dword ptr [rbp+70h+var_60+8]
0x180021d7d  mov     [r14+8], rax
0x180021d81  mov     eax, dword ptr [rbp+70h+var_60+0Ch]
0x180021d84  mov     [r14+38h], rax
0x180021d88  add     r14, 40h ; '@'
0x180021d8c  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180021d91  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180021d95  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180021d9a  add     r15d, edx
0x180021d9d  jmp     loc_180021CDC
0x180021da2  mov     ebx, 80004005h
0x180021da7  jmp     loc_180021E9D
0x180021dac  xor     r15d, r15d
0x180021daf  cmp     [rdi], r15b
0x180021db2  jz      short loc_180021DD0
0x180021db4  mov     r8d, [rdi+28h]; cbOutput
0x180021db8  xor     r9d, r9d; dwFlags
0x180021dbb  mov     rdx, [rdi+20h]; pbOutput
0x180021dbf  mov     rcx, [rdi+10h]; hHash
0x180021dc3  call    cs:__imp_BCryptFinishHash
0x180021dc9  test    eax, eax
0x180021dcb  jns     short loc_180021E08
0x180021dcd  mov     [rdi], r15b
0x180021dd0  lea     rcx, [rsp+170h+var_128]
0x180021dd5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021dda  mov     rcx, rsi; hObject
0x180021ddd  call    cs:__imp_CloseHandle
0x180021de3  mov     eax, 80004005h
0x180021de8  mov     rcx, [rbp+70h+var_50]
0x180021dec  xor     rcx, rsp; StackCookie
0x180021def  call    __security_check_cookie
0x180021df4  add     rsp, 138h
0x180021dfb  pop     r15
0x180021dfd  pop     r14
0x180021dff  pop     r13
0x180021e01  pop     r12
0x180021e03  pop     rdi
0x180021e04  pop     rsi
0x180021e05  pop     rbx
0x180021e06  pop     rbp
0x180021e07  retn
0x180021e08  cmp     [rdi], r15b
0x180021e0b  jz      short loc_180021DD0
0x180021e0d  cmp     dword ptr [rdi+28h], 10h
0x180021e11  mov     r14d, 10h
0x180021e17  ja      short loc_180021E1D
0x180021e19  mov     r14d, [rdi+28h]
0x180021e1d  mov     rdx, [rdi+20h]; Src
0x180021e21  lea     rcx, [r12+8]; void *
0x180021e26  mov     r8, r14; Size
0x180021e29  call    memcpy_0
0x180021e2e  cmp     r14, 10h
0x180021e32  jnz     short loc_180021DD0
0x180021e34  xor     edx, edx; Val
0x180021e36  lea     r8d, [r14+46h]; Size
0x180021e3a  lea     rcx, [rbp+70h+var_CE]; void *
0x180021e3e  call    memset_0
0x180021e43  mov     rcx, qword ptr [rsp+170h+var_128]
0x180021e48  lea     eax, [r14-0Ch]
0x180021e4c  movups  xmm0, cs:ElfImageGuid
0x180021e53  mov     [rbp+70h+var_D0], ax
0x180021e57  lea     rdx, [rbp+70h+var_D0]
0x180021e5b  mov     eax, dword ptr [rsp+170h+var_128+8]
0x180021e5f  xor     r9d, r9d
0x180021e62  sub     eax, ecx
0x180021e64  mov     [rbp+70h+var_88], rcx
0x180021e68  mov     rcx, [r13+10h]
0x180021e6c  xor     r8d, r8d
0x180021e6f  mov     [rbp+70h+var_80], eax
0x180021e72  mov     eax, [rbp+70h+arg_20]
0x180021e78  mov     [rbp+70h+var_7C], eax
0x180021e7b  mov     [rbp+70h+var_C0], rbx
0x180021e7f  movdqu  [rbp+70h+var_B8], xmm0
0x180021e84  mov     [rbp+70h+var_CC], r15d
0x180021e88  mov     rax, [rcx]
0x180021e8b  mov     rax, [rax+0C0h]
0x180021e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e97  mov     ebx, eax
0x180021e99  test    eax, eax
0x180021e9b  jns     short loc_180021EB7
0x180021e9d  lea     rcx, [rsp+170h+var_128]
0x180021ea2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021ea7  mov     rcx, rsi; hObject
0x180021eaa  call    cs:__imp_CloseHandle
0x180021eb0  mov     eax, ebx
0x180021eb2  jmp     loc_180021DE8
0x180021eb7  lea     rcx, [rsp+170h+var_128]
0x180021ebc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021ec1  mov     rcx, rsi; hObject
0x180021ec4  call    cs:__imp_CloseHandle
0x180021eca  xor     eax, eax
0x180021ecc  jmp     loc_180021DE8
```
