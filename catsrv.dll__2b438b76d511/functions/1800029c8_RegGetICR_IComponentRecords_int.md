# _RegGetICR(IComponentRecords * *,int)

- ea: `0x1800029c8`
- end: `0x180002f17`
- name: `?_RegGetICR@@YAJPEAPEAUIComponentRecords@@H@Z`
- size: `1359`
- prototype: `__int64 __fastcall(struct IComponentRecords **, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002464`

## callees

- `0x1800029c8`
- `0x180002f20`
- `0x180002fb8`
- `0x180005ae0`
- `0x180007c2c`
- `0x180009098`
- `0x18000997c`
- `0x18005550e`
- `0x18005551a`
- `0x180055550`
- `0x180055610`
- `0x180058010`

## import_xrefs

- `CLBCatQ!OpenComponentLibraryEx` at `0x180002cb0`
- `CLBCatQ!OpenComponentLibraryEx` at `0x180002cb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005567a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005567a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b7d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002c1f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002c1f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002c0a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002c0a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002b6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002b6f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180002e65`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180002e65`

## string_xrefs

- `0x180002ea2`: `com\complus\src\comcat\regdb\regdbapi\regdbapi.cpp`

## pseudocode

```c
__int64 __fastcall _RegGetICR(struct IComponentRecords **a1, int a2)
{
  int v2; // edi
  struct IComponentRecords **v3; // r12
  signed int CatalogVersionFromRegistry; // esi
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  void *v14; // rsp
  HANDLE FirstFileW; // rbx
  DWORD LastError; // eax
  __int64 VersionFromClbName; // rax
  __int64 *v18; // rbx
  FILETIME *p_ftLastWriteTime; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  __int64 v25; // rbx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+0h] [rbp-250h] BYREF
  WCHAR FileName[2]; // [rsp+250h] [rbp+0h] BYREF
  int v28; // [rsp+254h] [rbp+4h]
  int v29; // [rsp+258h] [rbp+8h]
  __int64 v30; // [rsp+260h] [rbp+10h] BYREF
  __int64 v31; // [rsp+268h] [rbp+18h] BYREF
  struct IComponentRecords **v32; // [rsp+270h] [rbp+20h]
  int v33; // [rsp+278h] [rbp+28h] BYREF
  __int16 v34; // [rsp+27Ch] [rbp+2Ch]
  int v35; // [rsp+280h] [rbp+30h]
  __int128 v36; // [rsp+288h] [rbp+38h]
  __int64 v37; // [rsp+298h] [rbp+48h]
  int v38; // [rsp+2A0h] [rbp+50h]
  int v39; // [rsp+2A4h] [rbp+54h]
  FILETIME ftLastWriteTime; // [rsp+2B0h] [rbp+60h] BYREF
  BYTE Data[8]; // [rsp+2B8h] [rbp+68h] BYREF
  DWORD nFileSizeLow; // [rsp+2C0h] [rbp+70h]
  unsigned __int16 v43[262]; // [rsp+2C4h] [rbp+74h] BYREF

  v2 = a2;
  LODWORD(v30) = a2;
  v3 = a1;
  v32 = a1;
  v31 = 0;
  memset_0(&ftLastWriteTime, 0, 0x220u);
  if ( !dword_180072FE8 )
    return 2148598898LL;
  EnterCriticalSection(&CriticalSection);
  v29 = 1;
  CatalogVersionFromRegistry = InitializeCatalogSectionIfNeeded();
  v28 = CatalogVersionFromRegistry;
  if ( CatalogVersionFromRegistry < 0 )
  {
LABEL_59:
    if ( CatalogVersionFromRegistry >= 0 )
      goto LABEL_60;
LABEL_61:
    if ( qword_1800731F8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800731F8 + 16LL))(qword_1800731F8);
    qword_1800731F8 = 0;
    qword_180072DA8 = 0;
    goto LABEL_64;
  }
  CatalogVersionFromRegistry = 0;
  *(_DWORD *)FileName = 0;
  if ( v2 )
  {
    *(_QWORD *)Data = 0;
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( *(&dword_180072FEC + v7) );
    v8 = v7;
    v9 = 2 * v7 + 38;
    v10 = v9 + 15;
    if ( v9 + 15 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    memcpy_0(FileName, &dword_180072FEC, v8 * 2);
    *(_OWORD *)&FileName[v8] = *(_OWORD *)L"\\R????????????.clb";
    *(_OWORD *)&FileName[v8 + 8] = *(_OWORD *)L"??????.clb";
    *(_QWORD *)&FileName[v8 + 15] = *(_QWORD *)L"clb";
    v14 = alloca(592);
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        CatalogVersionFromRegistry = 0;
        *(_DWORD *)FileName = 0;
      }
      else
      {
        if ( LastError == 8 || LastError == 1455 || LastError == 1450 )
          CatalogVersionFromRegistry = (unsigned __int16)LastError | 0x80070000;
        else
          CatalogVersionFromRegistry = -2146368396;
        *(_DWORD *)FileName = CatalogVersionFromRegistry;
      }
    }
    else
    {
      do
      {
        VersionFromClbName = GetVersionFromClbName(FindFileData.cFileName);
        if ( (unsigned __int64)(VersionFromClbName - *(_QWORD *)Data + 0x7FFFFFFFFFFFLL) > 0x7FFFFFFFFFFFLL
          && VersionFromClbName - *(_QWORD *)Data < 0x7FFFFFFFFFFFLL
          || !*(_QWORD *)Data )
        {
          *(_QWORD *)Data = VersionFromClbName;
          ftLastWriteTime = FindFileData.ftLastWriteTime;
          nFileSizeLow = FindFileData.nFileSizeLow;
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
    }
    if ( FirstFileW != (HANDLE)-1LL )
      FindClose(FirstFileW);
    if ( CatalogVersionFromRegistry >= 0 )
    {
      if ( !*(_QWORD *)Data )
        CatalogVersionFromRegistry = -2147418113;
      *(_DWORD *)FileName = CatalogVersionFromRegistry;
      GetDBName(v43, 0x104u, &dword_180072FEC, *(__int64 *)Data);
    }
    v2 = v30;
  }
  else
  {
    CatalogVersionFromRegistry = GetCatalogVersionFromRegistry(Data);
    *(_DWORD *)FileName = CatalogVersionFromRegistry;
    if ( CatalogVersionFromRegistry < 0 )
    {
      v6 = -1;
      goto LABEL_34;
    }
    GetDBName(v43, 0x104u, &dword_180072FEC, *(__int64 *)Data);
    CatalogVersionFromRegistry = 0;
    v6 = -1;
  }
  v3 = v32;
LABEL_34:
  v28 = CatalogVersionFromRegistry;
  if ( CatalogVersionFromRegistry < 0 )
    goto LABEL_61;
  if ( !qword_1800731F8 || qword_180072DA8 < *(__int64 *)Data )
  {
    LeaveCriticalSection(&CriticalSection);
    v29 = 0;
    if ( v43[0] )
    {
      v30 = 0;
      CatalogVersionFromRegistry = OpenComponentLibraryEx(v43, 1, &v30);
      if ( CatalogVersionFromRegistry >= 0 )
        CatalogVersionFromRegistry = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(
                                       v30,
                                       &IID_ITSComponentRecords,
                                       &v31);
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v28 = CatalogVersionFromRegistry;
    }
    else
    {
      CatalogVersionFromRegistry = -2147418113;
      v28 = -2147418113;
    }
    EnterCriticalSection(&CriticalSection);
    v29 = 1;
    if ( CatalogVersionFromRegistry < 0 )
    {
      if ( CatalogVersionFromRegistry == -2147217387 && v2 )
      {
        do
          ++v6;
        while ( *(&ExistingFileName + v6) );
        v21 = 2 * v6 + 33;
        if ( v21 <= 2 * v6 + 18 )
          v21 = 0xFFFFFFFFFFFFFF0LL;
        v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
        v23 = alloca(v22);
        v24 = alloca(v22);
        v25 = v6;
        memcpy_0(FileName, &ExistingFileName, 2 * v6);
        *(_OWORD *)&FileName[v25] = *(_OWORD *)L".corrupt";
        FileName[v25 + 8] = aCorrupt[8];
        MoveFileExW(&ExistingFileName, FileName, 1u);
        v33 = -2147217387;
        v34 = 22;
        v35 = -1073737032;
        v36 = 0;
        v37 = 0;
        v38 = 0;
        v39 = 1;
        CError::WriteToLog((CError *)&v33, L"com\\complus\\src\\comcat\\regdb\\regdbapi\\regdbapi.cpp", 0x18Cu, 0);
      }
    }
    else if ( qword_1800731F8 && qword_180072DA8 >= *(__int64 *)Data )
    {
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
    }
    else
    {
      v18 = &qword_180072DA0;
      _RegReleaseReference((struct REGAPI_STATE *)&qword_180072DA0);
      p_ftLastWriteTime = &ftLastWriteTime;
      v20 = 4;
      do
      {
        *(_OWORD *)v18 = *(_OWORD *)&p_ftLastWriteTime->dwLowDateTime;
        *((_OWORD *)v18 + 1) = *(_OWORD *)&p_ftLastWriteTime[2].dwLowDateTime;
        *((_OWORD *)v18 + 2) = *(_OWORD *)&p_ftLastWriteTime[4].dwLowDateTime;
        *((_OWORD *)v18 + 3) = *(_OWORD *)&p_ftLastWriteTime[6].dwLowDateTime;
        *((_OWORD *)v18 + 4) = *(_OWORD *)&p_ftLastWriteTime[8].dwLowDateTime;
        *((_OWORD *)v18 + 5) = *(_OWORD *)&p_ftLastWriteTime[10].dwLowDateTime;
        *((_OWORD *)v18 + 6) = *(_OWORD *)&p_ftLastWriteTime[12].dwLowDateTime;
        *((_OWORD *)v18 + 7) = *(_OWORD *)&p_ftLastWriteTime[14].dwLowDateTime;
        v18 += 16;
        p_ftLastWriteTime += 16;
        --v20;
      }
      while ( v20 );
      *(_OWORD *)v18 = *(_OWORD *)&p_ftLastWriteTime->dwLowDateTime;
      *((_OWORD *)v18 + 1) = *(_OWORD *)&p_ftLastWriteTime[2].dwLowDateTime;
      qword_1800731F8 = v31;
      CatalogVersionFromRegistry = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v31 + 360LL))(
                                     v31,
                                     &COMRegSchemaBlob);
      v28 = CatalogVersionFromRegistry;
    }
    goto LABEL_59;
  }
  CatalogVersionFromRegistry = 0;
  v28 = 0;
LABEL_60:
  *v3 = (struct IComponentRecords *)qword_1800731F8;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800731F8 + 8LL))(qword_1800731F8);
  v29 = 1;
LABEL_64:
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)CatalogVersionFromRegistry;
}

```

## disassembly

```asm
0x1800029c8  push    rbp
0x1800029ca  push    rbx
0x1800029cb  push    rsi
0x1800029cc  push    rdi
0x1800029cd  push    r12
0x1800029cf  push    r13
0x1800029d1  push    r14
0x1800029d3  push    r15
0x1800029d5  sub     rsp, 2B8h
0x1800029dc  lea     rbp, [rsp+20h]
0x1800029e1  mov     rax, cs:__security_cookie
0x1800029e8  xor     rax, rbp
0x1800029eb  mov     [rbp+2D0h+var_50], rax
0x1800029f2  mov     edi, edx
0x1800029f4  mov     dword ptr [rbp+2D0h+var_2C0], edx
0x1800029f7  mov     r12, rcx
0x1800029fa  mov     [rbp+2D0h+var_2B0], rcx
0x1800029fe  xor     r13d, r13d
0x180002a01  mov     [rbp+2D0h+var_2B8], r13
0x180002a05  xor     edx, edx; Val
0x180002a07  mov     r8d, 220h; Size
0x180002a0d  lea     rcx, [rbp+2D0h+var_270]; void *
0x180002a11  call    memset_0
0x180002a16  cmp     cs:dword_180072FE8, r13d
0x180002a1d  jnz     short loc_180002A47
0x180002a1f  mov     eax, 80110472h
0x180002a24  mov     rcx, [rbp+2D0h+var_50]
0x180002a2b  xor     rcx, rbp; StackCookie
0x180002a2e  call    __security_check_cookie
0x180002a33  lea     rsp, [rbp+298h]
0x180002a3a  pop     r15
0x180002a3c  pop     r14
0x180002a3e  pop     r13
0x180002a40  pop     r12
0x180002a42  pop     rdi
0x180002a43  pop     rsi
0x180002a44  pop     rbx
0x180002a45  pop     rbp
0x180002a46  retn
0x180002a47  lea     rcx, CriticalSection; lpCriticalSection
0x180002a4e  call    cs:__imp_EnterCriticalSection
0x180002a54  mov     [rbp+2D0h+var_2C8], 1
0x180002a5b  call    ?InitializeCatalogSectionIfNeeded@@YAJXZ; InitializeCatalogSectionIfNeeded(void)
0x180002a60  mov     esi, eax
0x180002a62  mov     [rbp+2D0h+var_2CC], eax
0x180002a65  test    eax, eax
0x180002a67  js      loc_180002EB2
0x180002a6d  mov     esi, r13d
0x180002a70  mov     dword ptr [rbp+2D0h+FileName], r13d
0x180002a74  test    edi, edi
0x180002a76  jnz     short loc_180002AD6
0x180002a78  lea     rcx, [rbp+2D0h+Data]; lpData
0x180002a7c  call    ?GetCatalogVersionFromRegistry@@YAJPEA_J@Z; GetCatalogVersionFromRegistry(__int64 *)
0x180002a81  mov     esi, eax
0x180002a83  mov     dword ptr [rbp+2D0h+FileName], eax
0x180002a86  test    eax, eax
0x180002a88  jns     short loc_180002AA2
0x180002a8a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002a8e  mov     ebx, 8000FFFFh
0x180002a93  mov     r15, 0FFFFFFFFFFFFFF0h
0x180002a9d  jmp     loc_180002C53
0x180002aa2  mov     r9, qword ptr [rbp+2D0h+Data]; __int64
0x180002aa6  lea     r8, dword_180072FEC; unsigned __int16 *
0x180002aad  mov     edx, 104h; unsigned __int64
0x180002ab2  lea     rcx, [rbp+2D0h+var_25C]; unsigned __int16 *
0x180002ab6  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x180002abb  mov     esi, r13d
0x180002abe  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002ac2  mov     ebx, 8000FFFFh
0x180002ac7  mov     r15, 0FFFFFFFFFFFFFF0h
0x180002ad1  jmp     loc_180002C4F
0x180002ad6  mov     qword ptr [rbp+2D0h+Data], r13
0x180002ada  lea     r12, dword_180072FEC
0x180002ae1  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002ae5  mov     rax, r14
0x180002ae8  inc     rax
0x180002aeb  cmp     [r12+rax*2], r13w
0x180002af0  jnz     short loc_180002AE8
0x180002af2  lea     rdi, [rax+rax]
0x180002af6  lea     rax, [rdi+26h]
0x180002afa  lea     rcx, [rax+0Fh]
0x180002afe  mov     r15, 0FFFFFFFFFFFFFF0h
0x180002b08  cmp     rcx, rax
0x180002b0b  ja      short loc_180002B10
0x180002b0d  mov     rcx, r15
0x180002b10  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180002b14  mov     rax, rcx
0x180002b17  call    _alloca_probe
0x180002b1c  sub     rsp, rcx
0x180002b1f  lea     rbx, [rsp+2F0h+FileName]
0x180002b24  mov     r8, rdi; Size
0x180002b27  mov     rdx, r12; Src
0x180002b2a  mov     rcx, rbx; void *
0x180002b2d  call    memcpy_0
0x180002b32  movups  xmm0, xmmword ptr cs:aRClb; "\\R????????????.clb"
0x180002b39  movups  xmmword ptr [rdi+rbx], xmm0
0x180002b3d  movups  xmm1, xmmword ptr cs:aRClb+10h; "??????.clb"
0x180002b44  movups  xmmword ptr [rdi+rbx+10h], xmm1
0x180002b49  movsd   xmm0, qword ptr cs:aRClb+1Eh; "clb"
0x180002b51  movsd   qword ptr [rdi+rbx+1Eh], xmm0
0x180002b57  mov     eax, dword ptr [rsp+2F0h+FindFileData.cFileName+204h]
0x180002b5a  mov     eax, 250h
0x180002b5f  sub     rsp, rax
0x180002b62  lea     rdi, [rsp+540h+FindFileData]
0x180002b67  mov     eax, [rdi]
0x180002b69  mov     rdx, rdi; lpFindFileData
0x180002b6c  mov     rcx, rbx; lpFileName
0x180002b6f  call    cs:__imp_FindFirstFileW
0x180002b75  mov     rbx, rax
0x180002b78  cmp     rax, r14
0x180002b7b  jnz     short loc_180002BC2
0x180002b7d  call    cs:__imp_GetLastError
0x180002b83  mov     esi, eax
0x180002b85  cmp     eax, 2
0x180002b88  jnz     short loc_180002B96
0x180002b8a  mov     esi, r13d
0x180002b8d  mov     dword ptr [rbp+2D0h+FileName], r13d
0x180002b91  jmp     loc_180002C17
0x180002b96  cmp     eax, 8
0x180002b99  jz      short loc_180002BB0
0x180002b9b  cmp     eax, 5AFh
0x180002ba0  jz      short loc_180002BB0
0x180002ba2  cmp     eax, 5AAh
0x180002ba7  jz      short loc_180002BB0
0x180002ba9  mov     esi, 80110474h
0x180002bae  jmp     short loc_180002BBD
0x180002bb0  test    eax, eax
0x180002bb2  jle     short loc_180002BBD
0x180002bb4  movzx   esi, ax
0x180002bb7  or      esi, 80070000h
0x180002bbd  mov     dword ptr [rbp+2D0h+FileName], esi
0x180002bc0  jmp     short loc_180002C17
0x180002bc2  lea     rcx, [rdi+2Ch]; unsigned __int16 *
0x180002bc6  call    ?GetVersionFromClbName@@YA_JPEAG@Z; GetVersionFromClbName(ushort *)
0x180002bcb  mov     rdx, rax
0x180002bce  mov     r8, qword ptr [rbp+2D0h+Data]
0x180002bd2  sub     rdx, r8
0x180002bd5  mov     r9, 7FFFFFFFFFFFh
0x180002bdf  lea     rcx, [rdx+r9]
0x180002be3  cmp     rcx, r9
0x180002be6  jbe     short loc_180002BED
0x180002be8  cmp     rdx, r9
0x180002beb  jl      short loc_180002BF2
0x180002bed  test    r8, r8
0x180002bf0  jnz     short loc_180002C04
0x180002bf2  mov     qword ptr [rbp+2D0h+Data], rax
0x180002bf6  mov     rax, [rdi+14h]
0x180002bfa  mov     [rbp+2D0h+var_270], rax
0x180002bfe  mov     eax, [rdi+20h]
0x180002c01  mov     [rbp+2D0h+var_260], eax
0x180002c04  mov     rdx, rdi; lpFindFileData
0x180002c07  mov     rcx, rbx; hFindFile
0x180002c0a  call    cs:__imp_FindNextFileW
0x180002c10  test    eax, eax
0x180002c12  jnz     short loc_180002BC2
0x180002c14  xor     r13d, r13d
0x180002c17  cmp     rbx, r14
0x180002c1a  jz      short loc_180002C25
0x180002c1c  mov     rcx, rbx; hFindFile
0x180002c1f  call    cs:__imp_FindClose
0x180002c25  mov     ebx, 8000FFFFh
0x180002c2a  test    esi, esi
0x180002c2c  js      short loc_180002C4C
0x180002c2e  mov     r9, qword ptr [rbp+2D0h+Data]; __int64
0x180002c32  test    r9, r9
0x180002c35  cmovz   esi, ebx
0x180002c38  mov     dword ptr [rbp+2D0h+FileName], esi
0x180002c3b  mov     r8, r12; unsigned __int16 *
0x180002c3e  mov     edx, 104h; unsigned __int64
0x180002c43  lea     rcx, [rbp+2D0h+var_25C]; unsigned __int16 *
0x180002c47  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x180002c4c  mov     edi, dword ptr [rbp+2D0h+var_2C0]
0x180002c4f  mov     r12, [rbp+2D0h+var_2B0]
0x180002c53  mov     [rbp+2D0h+var_2CC], esi
0x180002c56  test    esi, esi
0x180002c58  js      loc_180002EDD
0x180002c5e  cmp     cs:qword_1800731F8, r13
0x180002c65  jz      short loc_180002C80
0x180002c67  mov     rax, cs:qword_180072DA8
0x180002c6e  cmp     rax, qword ptr [rbp+2D0h+Data]
0x180002c72  jl      short loc_180002C80
0x180002c74  mov     esi, r13d
0x180002c77  mov     [rbp+2D0h+var_2CC], r13d
0x180002c7b  jmp     loc_180002EB6
0x180002c80  lea     rcx, CriticalSection; lpCriticalSection
0x180002c87  call    cs:__imp_LeaveCriticalSection
0x180002c8d  mov     [rbp+2D0h+var_2C8], r13d
0x180002c91  cmp     [rbp+2D0h+var_25C], r13w
0x180002c96  jnz     short loc_180002C9F
0x180002c98  mov     esi, ebx
0x180002c9a  mov     [rbp+2D0h+var_2CC], ebx
0x180002c9d  jmp     short loc_180002CF0
0x180002c9f  mov     [rbp+2D0h+var_2C0], r13
0x180002ca3  lea     r8, [rbp+2D0h+var_2C0]
0x180002ca7  mov     edx, 1
0x180002cac  lea     rcx, [rbp+2D0h+var_25C]
0x180002cb0  call    cs:__imp_OpenComponentLibraryEx
0x180002cb6  mov     esi, eax
0x180002cb8  test    eax, eax
0x180002cba  js      short loc_180002CD8
0x180002cbc  mov     rcx, [rbp+2D0h+var_2C0]
0x180002cc0  mov     rax, [rcx]
0x180002cc3  lea     r8, [rbp+2D0h+var_2B8]
0x180002cc7  lea     rdx, ?IID_ITSComponentRecords@@3U_GUID@@B; _GUID const IID_ITSComponentRecords
0x180002cce  mov     rax, [rax]
0x180002cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd6  mov     esi, eax
0x180002cd8  mov     rcx, [rbp+2D0h+var_2C0]
0x180002cdc  test    rcx, rcx
0x180002cdf  jz      short loc_180002CED
0x180002ce1  mov     rax, [rcx]
0x180002ce4  mov     rax, [rax+10h]
0x180002ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ced  mov     [rbp+2D0h+var_2CC], esi
0x180002cf0  lea     rcx, CriticalSection; lpCriticalSection
0x180002cf7  call    cs:__imp_EnterCriticalSection
0x180002cfd  mov     [rbp+2D0h+var_2C8], 1
0x180002d04  test    esi, esi
0x180002d06  js      loc_180002DE2
0x180002d0c  cmp     cs:qword_1800731F8, r13
0x180002d13  jz      short loc_180002D44
0x180002d15  mov     rax, cs:qword_180072DA8
0x180002d1c  cmp     rax, qword ptr [rbp+2D0h+Data]
0x180002d20  jl      short loc_180002D44
0x180002d22  mov     rcx, [rbp+2D0h+var_2B8]
0x180002d26  test    rcx, rcx
0x180002d29  jz      loc_180002EB2
0x180002d2f  mov     rax, [rcx]
0x180002d32  mov     rax, [rax+10h]
0x180002d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3b  mov     [rbp+2D0h+var_2B8], r13
0x180002d3f  jmp     loc_180002EB2
0x180002d44  lea     rbx, qword_180072DA0
0x180002d4b  mov     rcx, rbx; struct REGAPI_STATE *
0x180002d4e  call    ?_RegReleaseReference@@YAXPEAUREGAPI_STATE@@@Z; _RegReleaseReference(REGAPI_STATE *)
0x180002d53  lea     rax, [rbp+2D0h+var_270]
0x180002d57  mov     ecx, 4
0x180002d5c  lea     edx, [rcx+7Ch]
0x180002d5f  movups  xmm0, xmmword ptr [rax]
0x180002d62  movups  xmmword ptr [rbx], xmm0
0x180002d65  movups  xmm1, xmmword ptr [rax+10h]
0x180002d69  movups  xmmword ptr [rbx+10h], xmm1
0x180002d6d  movups  xmm0, xmmword ptr [rax+20h]
0x180002d71  movups  xmmword ptr [rbx+20h], xmm0
0x180002d75  movups  xmm1, xmmword ptr [rax+30h]
0x180002d79  movups  xmmword ptr [rbx+30h], xmm1
0x180002d7d  movups  xmm0, xmmword ptr [rax+40h]
0x180002d81  movups  xmmword ptr [rbx+40h], xmm0
0x180002d85  movups  xmm1, xmmword ptr [rax+50h]
0x180002d89  movups  xmmword ptr [rbx+50h], xmm1
0x180002d8d  movups  xmm0, xmmword ptr [rax+60h]
0x180002d91  movups  xmmword ptr [rbx+60h], xmm0
0x180002d95  movups  xmm1, xmmword ptr [rax+70h]
0x180002d99  movups  xmmword ptr [rbx+70h], xmm1
0x180002d9d  add     rbx, rdx
0x180002da0  add     rax, rdx
0x180002da3  sub     rcx, 1
0x180002da7  jnz     short loc_180002D5F
0x180002da9  movups  xmm0, xmmword ptr [rax]
0x180002dac  movups  xmmword ptr [rbx], xmm0
0x180002daf  movups  xmm1, xmmword ptr [rax+10h]
0x180002db3  movups  xmmword ptr [rbx+10h], xmm1
0x180002db7  mov     rcx, [rbp+2D0h+var_2B8]
0x180002dbb  mov     cs:qword_1800731F8, rcx
0x180002dc2  mov     rax, [rcx]
0x180002dc5  lea     rdx, ?COMRegSchemaBlob@@3U_tagCOMPLIBSCHEMABLOB@@B; _tagCOMPLIBSCHEMABLOB const COMRegSchemaBlob
0x180002dcc  mov     rax, [rax+168h]
0x180002dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd8  mov     esi, eax
0x180002dda  mov     [rbp+2D0h+var_2CC], eax
0x180002ddd  jmp     loc_180002EB2
0x180002de2  cmp     esi, 80041015h
0x180002de8  jnz     loc_180002EB2
0x180002dee  test    edi, edi
0x180002df0  jz      loc_180002EB2
0x180002df6  lea     rdx, ExistingFileName
0x180002dfd  inc     r14
0x180002e00  cmp     [rdx+r14*2], r13w
0x180002e05  jnz     short loc_180002DFD
0x180002e07  lea     rax, ds:12h[r14*2]
0x180002e0f  lea     rcx, [rax+0Fh]
0x180002e13  cmp     rcx, rax
0x180002e16  ja      short loc_180002E1B
0x180002e18  mov     rcx, r15
0x180002e1b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180002e1f  mov     rax, rcx
0x180002e22  call    _alloca_probe
0x180002e27  sub     rsp, rcx
0x180002e2a  lea     rdi, [rsp+2F0h+FileName]
0x180002e2f  lea     rbx, [r14+r14]
0x180002e33  mov     r8, rbx; Size
0x180002e36  mov     rcx, rdi; void *
0x180002e39  call    memcpy_0
0x180002e3e  movups  xmm0, xmmword ptr cs:aCorrupt; ".corrupt"
0x180002e45  movups  xmmword ptr [rbx+rdi], xmm0
0x180002e49  movzx   eax, word ptr cs:aCorrupt+10h; ""
0x180002e50  mov     [rbx+rdi+10h], ax
0x180002e55  mov     r8d, 1; dwFlags
0x180002e5b  mov     rdx, rdi; lpNewFileName
0x180002e5e  lea     rcx, ExistingFileName; lpExistingFileName
  ... truncated ...
```
