# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180022850`
- end: `0x180022c6e`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `1054`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x1800029c9`
- `0x1800029d5`
- `0x1800188e8`
- `0x1800219b0`
- `0x180022818`
- `0x180022850`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800229c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800229c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c5b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800228aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800228aa`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800229d9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800229d9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180022a81`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180022a81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800228f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022ab1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800228f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180022ab1`
- `bcrypt!BCryptFinishHash` at `0x180022b47`
- `bcrypt!BCryptFinishHash` at `0x180022b47`

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
    || memcmp_0(&Buffer, &qword_18002C510, 4u)
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
0x180022850  push    rbp
0x180022852  push    rbx
0x180022853  push    rsi
0x180022854  push    rdi
0x180022855  push    r12
0x180022857  push    r13
0x180022859  push    r14
0x18002285b  push    r15
0x18002285d  lea     rbp, [rsp-38h]
0x180022862  sub     rsp, 138h
0x180022869  mov     rax, cs:__security_cookie
0x180022870  xor     rax, rsp
0x180022873  mov     [rbp+70h+var_50], rax
0x180022877  mov     r15, rdx
0x18002287a  xor     r14d, r14d
0x18002287d  mov     rbx, r9
0x180022880  mov     [rsp+170h+hTemplateFile], r14; hTemplateFile
0x180022885  mov     rdi, r8
0x180022888  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180022890  mov     r13, rcx
0x180022893  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x18002289b  mov     rcx, [r15]; lpFileName
0x18002289e  lea     r8d, [r14+7]; dwShareMode
0x1800228a2  xor     r9d, r9d; lpSecurityAttributes
0x1800228a5  mov     edx, 80000000h; dwDesiredAccess
0x1800228aa  call    cs:__imp_CreateFileW
0x1800228b1  nop     dword ptr [rax+rax+00h]
0x1800228b6  mov     rsi, rax
0x1800228b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800228bd  jz      loc_180022B73
0x1800228c3  xorps   xmm0, xmm0
0x1800228c6  mov     [rsp+170h+NumberOfBytesRead], r14d
0x1800228cb  xor     eax, eax
0x1800228cd  mov     qword ptr [rsp+170h+dwCreationDisposition], r14; lpOverlapped
0x1800228d2  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800228d7  mov     [rbp+70h+var_E0], eax
0x1800228da  lea     r8d, [r14+34h]; nNumberOfBytesToRead
0x1800228de  mov     rcx, rsi; hFile
0x1800228e1  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x1800228e6  movups  [rsp+170h+Buffer], xmm0
0x1800228eb  movups  xmmword ptr [rsp+170h+lDistanceToMove], xmm0
0x1800228f0  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x1800228f4  call    cs:__imp_ReadFile
0x1800228fb  nop     dword ptr [rax+rax+00h]
0x180022900  test    eax, eax
0x180022902  jz      loc_180022B64
0x180022908  cmp     [rsp+170h+NumberOfBytesRead], 34h ; '4'
0x18002290d  jnz     loc_180022B64
0x180022913  lea     r8d, [r14+4]; Size
0x180022917  lea     rdx, qword_18002C510; Buf2
0x18002291e  lea     rcx, [rsp+170h+Buffer]; Buf1
0x180022923  call    memcmp_0
0x180022928  test    eax, eax
0x18002292a  jnz     loc_180022B64
0x180022930  cmp     byte ptr [rsp+170h+Buffer+4], 1
0x180022935  jnz     loc_180022B64
0x18002293b  cmp     byte ptr [rsp+170h+Buffer+5], 1
0x180022940  jnz     loc_180022B64
0x180022946  cmp     byte ptr [rsp+170h+Buffer+6], 1
0x18002294b  jnz     loc_180022B64
0x180022951  lea     eax, [r14+20h]
0x180022955  cmp     ax, word ptr [rbp+70h+var_F0+0Ah]
0x180022959  jnz     loc_180022B64
0x18002295f  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180022963  lea     r8, [rsp+170h+var_130]
0x180022968  mov     rax, [r15]
0x18002296b  xorps   xmm0, xmm0
0x18002296e  shl     ecx, 5
0x180022971  mov     [rsp+170h+var_130], r14b
0x180022976  add     ecx, [rax-10h]
0x180022979  movdqu  [rsp+170h+var_128], xmm0
0x18002297f  mov     [rsp+170h+var_118], r14
0x180022984  lea     edx, ds:5Eh[rcx*2]
0x18002298b  lea     rcx, [rsp+170h+var_128]
0x180022990  call    ??$_Construct_n@AEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBD@Z; std::vector<char>::_Construct_n<char const &>(unsigned __int64,char const &)
0x180022995  mov     rax, [r15]
0x180022998  mov     r12, qword ptr [rsp+170h+var_128]
0x18002299d  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x1800229a1  shl     rcx, 6
0x1800229a5  movzx   edx, word ptr [rax-10h]
0x1800229a9  inc     dx
0x1800229ac  lea     r14, [r12+1Ch]
0x1800229b1  movzx   edx, dx
0x1800229b4  add     rcx, r14
0x1800229b7  mov     [r12+1Ah], dx
0x1800229bd  mov     r8, [r15]
0x1800229c0  call    cs:__imp__o_wcscpy_s
0x1800229c7  nop     dword ptr [rax+rax+00h]
0x1800229cc  xor     edx, edx; lpFileSizeHigh
0x1800229ce  mov     dword ptr [r12], 0
0x1800229d6  mov     rcx, rsi; hFile
0x1800229d9  call    cs:__imp_GetFileSize
0x1800229e0  nop     dword ptr [rax+rax+00h]
0x1800229e5  mov     [r12+4], eax
0x1800229ea  cmp     eax, 0FFFFFFFFh
0x1800229ed  jz      loc_180022B5A
0x1800229f3  movzx   eax, word ptr [rbp+70h+var_F0+0Ch]
0x1800229f7  lea     rdx, [rsp+170h+Buffer]; unsigned __int8 *
0x1800229fc  mov     r8d, 10h; unsigned int
0x180022a02  mov     [r12+18h], ax
0x180022a08  mov     rcx, rdi; this
0x180022a0b  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180022a10  mov     r8d, 2; unsigned int
0x180022a16  lea     rdx, [rsp+170h+lDistanceToMove+2]; unsigned __int8 *
0x180022a1b  mov     rcx, rdi; this
0x180022a1e  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180022a23  mov     r15d, 4
0x180022a29  lea     rdx, [rsp+170h+lDistanceToMove+4]; unsigned __int8 *
0x180022a2e  mov     r8d, r15d; unsigned int
0x180022a31  mov     rcx, rdi; this
0x180022a34  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180022a39  mov     r8d, r15d; unsigned int
0x180022a3c  lea     rdx, [rbp+70h+var_F0+4]; unsigned __int8 *
0x180022a40  mov     rcx, rdi; this
0x180022a43  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180022a48  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180022a4d  mov     r15d, r8d
0x180022a50  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180022a54  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x180022a58  movzx   eax, dx
0x180022a5b  imul    ecx, eax
0x180022a5e  add     ecx, r8d
0x180022a61  cmp     r15d, ecx
0x180022a64  jz      loc_180022B30
0x180022a6a  xorps   xmm0, xmm0
0x180022a6d  xor     r9d, r9d; dwMoveMethod
0x180022a70  xor     r8d, r8d; lpDistanceToMoveHigh
0x180022a73  mov     edx, r15d; lDistanceToMove
0x180022a76  mov     rcx, rsi; hFile
0x180022a79  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x180022a7d  movups  [rbp+70h+var_60], xmm0
0x180022a81  call    cs:__imp_SetFilePointer
0x180022a88  nop     dword ptr [rax+rax+00h]
0x180022a8d  cmp     eax, 0FFFFFFFFh
0x180022a90  jz      loc_180022B26
0x180022a96  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180022a9b  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x180022aa4  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x180022aaa  lea     rdx, [rbp+70h+var_70]; lpBuffer
0x180022aae  mov     rcx, rsi; hFile
0x180022ab1  call    cs:__imp_ReadFile
0x180022ab8  nop     dword ptr [rax+rax+00h]
0x180022abd  test    eax, eax
0x180022abf  jz      short loc_180022B26
0x180022ac1  cmp     [rsp+170h+NumberOfBytesRead], 20h ; ' '
0x180022ac6  jnz     short loc_180022B26
0x180022ac8  mov     eax, dword ptr [rbp+70h+var_70]
0x180022acb  lea     rdx, [rbp+70h+var_70]; unsigned __int8 *
0x180022acf  mov     [r14], rax
0x180022ad2  mov     r8d, 20h ; ' '; unsigned int
0x180022ad8  mov     eax, dword ptr [rbp+70h+var_70+4]
0x180022adb  mov     rcx, rdi; this
0x180022ade  mov     [r14+10h], rax
0x180022ae2  mov     eax, dword ptr [rbp+70h+var_70+8]
0x180022ae5  mov     [r14+18h], rax
0x180022ae9  mov     eax, dword ptr [rbp+70h+var_70+0Ch]
0x180022aec  mov     [r14+20h], rax
0x180022af0  mov     eax, dword ptr [rbp+70h+var_60]
0x180022af3  mov     [r14+28h], rax
0x180022af7  mov     eax, dword ptr [rbp+70h+var_60+4]
0x180022afa  mov     [r14+30h], rax
0x180022afe  mov     eax, dword ptr [rbp+70h+var_60+8]
0x180022b01  mov     [r14+8], rax
0x180022b05  mov     eax, dword ptr [rbp+70h+var_60+0Ch]
0x180022b08  mov     [r14+38h], rax
0x180022b0c  add     r14, 40h ; '@'
0x180022b10  call    ?Hash@CryptographicHasher@Performance@Windows@Microsoft@@QEAA_NPEBEK@Z; Microsoft::Windows::Performance::CryptographicHasher::Hash(uchar const *,ulong)
0x180022b15  movzx   edx, word ptr [rbp+70h+var_F0+0Ah]
0x180022b19  mov     r8d, [rsp+170h+lDistanceToMove+0Ch]
0x180022b1e  add     r15d, edx
0x180022b21  jmp     loc_180022A54
0x180022b26  mov     ebx, 80004005h
0x180022b2b  jmp     loc_180022C2E
0x180022b30  xor     r15d, r15d
0x180022b33  cmp     [rdi], r15b
0x180022b36  jz      short loc_180022B5A
0x180022b38  mov     r8d, [rdi+28h]; cbOutput
0x180022b3c  xor     r9d, r9d; dwFlags
0x180022b3f  mov     rdx, [rdi+20h]; pbOutput
0x180022b43  mov     rcx, [rdi+10h]; hHash
0x180022b47  call    cs:__imp_BCryptFinishHash
0x180022b4e  nop     dword ptr [rax+rax+00h]
0x180022b53  test    eax, eax
0x180022b55  jns     short loc_180022B99
0x180022b57  mov     [rdi], r15b
0x180022b5a  lea     rcx, [rsp+170h+var_128]
0x180022b5f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022b64  mov     rcx, rsi; hObject
0x180022b67  call    cs:__imp_CloseHandle
0x180022b6e  nop     dword ptr [rax+rax+00h]
0x180022b73  mov     eax, 80004005h
0x180022b78  mov     rcx, [rbp+70h+var_50]
0x180022b7c  xor     rcx, rsp; StackCookie
0x180022b7f  call    __security_check_cookie
0x180022b84  add     rsp, 138h
0x180022b8b  pop     r15
0x180022b8d  pop     r14
0x180022b8f  pop     r13
0x180022b91  pop     r12
0x180022b93  pop     rdi
0x180022b94  pop     rsi
0x180022b95  pop     rbx
0x180022b96  pop     rbp
0x180022b97  retn
0x180022b99  cmp     [rdi], r15b
0x180022b9c  jz      short loc_180022B5A
0x180022b9e  cmp     dword ptr [rdi+28h], 10h
0x180022ba2  mov     r14d, 10h
0x180022ba8  ja      short loc_180022BAE
0x180022baa  mov     r14d, [rdi+28h]
0x180022bae  mov     rdx, [rdi+20h]; Src
0x180022bb2  lea     rcx, [r12+8]; void *
0x180022bb7  mov     r8, r14; Size
0x180022bba  call    memcpy_0
0x180022bbf  cmp     r14, 10h
0x180022bc3  jnz     short loc_180022B5A
0x180022bc5  xor     edx, edx; Val
0x180022bc7  lea     r8d, [r14+46h]; Size
0x180022bcb  lea     rcx, [rbp+70h+var_CE]; void *
0x180022bcf  call    memset_0
0x180022bd4  mov     rcx, qword ptr [rsp+170h+var_128]
0x180022bd9  lea     eax, [r14-0Ch]
0x180022bdd  movups  xmm0, cs:ElfImageGuid
0x180022be4  mov     [rbp+70h+var_D0], ax
0x180022be8  lea     rdx, [rbp+70h+var_D0]
0x180022bec  mov     eax, dword ptr [rsp+170h+var_128+8]
0x180022bf0  xor     r9d, r9d
0x180022bf3  sub     eax, ecx
0x180022bf5  mov     [rbp+70h+var_88], rcx
0x180022bf9  mov     rcx, [r13+10h]
0x180022bfd  xor     r8d, r8d
0x180022c00  mov     [rbp+70h+var_80], eax
0x180022c03  mov     eax, [rbp+70h+arg_20]
0x180022c09  mov     [rbp+70h+var_7C], eax
0x180022c0c  mov     [rbp+70h+var_C0], rbx
0x180022c10  movdqu  [rbp+70h+var_B8], xmm0
0x180022c15  mov     [rbp+70h+var_CC], r15d
0x180022c19  mov     rax, [rcx]
0x180022c1c  mov     rax, [rax+0C0h]
0x180022c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c28  mov     ebx, eax
0x180022c2a  test    eax, eax
0x180022c2c  jns     short loc_180022C4E
0x180022c2e  lea     rcx, [rsp+170h+var_128]
0x180022c33  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022c38  mov     rcx, rsi; hObject
0x180022c3b  call    cs:__imp_CloseHandle
0x180022c42  nop     dword ptr [rax+rax+00h]
0x180022c47  mov     eax, ebx
0x180022c49  jmp     loc_180022B78
0x180022c4e  lea     rcx, [rsp+170h+var_128]
0x180022c53  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022c58  mov     rcx, rsi; hObject
0x180022c5b  call    cs:__imp_CloseHandle
0x180022c62  nop     dword ptr [rax+rax+00h]
0x180022c67  xor     eax, eax
0x180022c69  jmp     loc_180022B78
```
