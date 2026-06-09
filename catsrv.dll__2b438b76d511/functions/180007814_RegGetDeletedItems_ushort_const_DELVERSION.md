# _RegGetDeletedItems(ushort const *,DELVERSION * &)

- ea: `0x180007814`
- end: `0x180007c23`
- name: `?_RegGetDeletedItems@@YAJPEBGAEAPEAUDELVERSION@@@Z`
- size: `1039`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct DELVERSION **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002f5f8`

## callees

- `0x180007814`
- `0x180007c2c`
- `0x180009ee0`
- `0x18000a090`
- `0x18000a0d0`
- `0x18000b134`
- `0x18000b578`
- `0x18002f420`
- `0x18002f82c`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!swscanf` at `0x18000790b`
- `msvcrt!swscanf` at `0x18000790b`
- `CLBCatQ!OpenComponentLibraryEx` at `0x180007a81`
- `CLBCatQ!OpenComponentLibraryEx` at `0x180007a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078c3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007be3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007be3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007945`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007945`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800078af`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800078af`
- `KERNEL32!MoveFileW` at `0x180007bb6`
- `KERNEL32!MoveFileW` at `0x180007bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bf2`

## pseudocode

```c
__int64 __fastcall _RegGetDeletedItems(unsigned __int16 *a1, struct DELVERSION **a2)
{
  _QWORD *v3; // rsi
  signed int v4; // edi
  HANDLE FirstFileW; // r13
  signed int LastError; // eax
  void *v7; // rcx
  unsigned int v8; // r14d
  unsigned int i; // r12d
  unsigned int j; // r15d
  __int64 v11; // r15
  unsigned int k; // r12d
  __int64 *v13; // r14
  __int64 v14; // rdx
  unsigned int v15; // r14d
  struct DELVERSION **v16; // r12
  __int64 v17; // r9
  struct DELVERSION *Entry; // rax
  __int64 v20; // [rsp+30h] [rbp-908h] BYREF
  __int64 v21; // [rsp+38h] [rbp-900h]
  _QWORD *v22; // [rsp+40h] [rbp-8F8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-8F0h]
  void **v24; // [rsp+50h] [rbp-8E8h] BYREF
  _QWORD *v25; // [rsp+58h] [rbp-8E0h]
  int v26; // [rsp+60h] [rbp-8D8h]
  int v27; // [rsp+64h] [rbp-8D4h]
  __int64 v28; // [rsp+68h] [rbp-8D0h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-8C8h]
  struct DELVERSION **v30; // [rsp+78h] [rbp-8C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-8B8h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+2D0h] [rbp-668h] BYREF
  WCHAR FileName[264]; // [rsp+4E0h] [rbp-458h] BYREF
  WCHAR NewFileName[264]; // [rsp+6F0h] [rbp-248h] BYREF

  v30 = a2;
  v29 = a1;
  v3 = 0;
  v22 = 0;
  v23 = 0;
  v28 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = StringCchPrintfW(FileName, 0x104u, L"%s%s", a1, L"\\R????????????.clb");
  if ( v4 < 0 )
    goto LABEL_5;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v21 = (__int64)FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 2 )
    {
      v4 = 0;
LABEL_5:
      Array<__int64>::~Array<__int64>((void **)&v22);
      return (unsigned int)v4;
    }
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    do
    {
      swscanf(FindFileData.cFileName, L"R%012I64x.clb", &v28);
      try
      {
        Array<__int64>::setSize();
        v11 = (int)v23;
        v3 = v22;
        v22[(int)v23 - 1] = v28;
        v7 = FirstFileW;
      }
      catch ( ... )
      {
        LODWORD(v20) = -2147024882;
        goto LABEL_44;
      }
    }
    while ( FindNextFileW(v7, &FindFileData) );
    v25 = v3;
    v26 = v11;
    v27 = 8;
    v24 = &SortDescVersions::`vftable';
    CQuickSort<__int64>::SortRange(&v24, 0, (unsigned int)(v11 - 1));
    if ( (_DWORD)v11 != 1 )
    {
      v8 = 0;
      do
      {
        if ( (__int64)(v3[v8] - v3[v11 - 1]) <= 0x7FFFFFFFFFFFLL )
          break;
        ++v8;
      }
      while ( v8 < (int)v11 - 1 );
      if ( v8 )
      {
        v24 = 0;
        v25 = 0;
        try
        {
          for ( i = v8; i < (unsigned int)v11; ++i )
            Array<__int64>::append(&v24, &v3[i]);
          for ( j = 0; j < v8; ++j )
            Array<__int64>::append(&v24, &v3[j]);
        }
        catch ( ... )
        {
          LODWORD(v20) = -2147024882;
          Array<__int64>::~Array<__int64>((void **)&v24);
LABEL_44:
          v4 = v20;
          FirstFileW = (HANDLE)v21;
          v3 = v22;
          goto LABEL_45;
        }
        Array<__int64>::operator=((__int64)&v22, (__int64)&v24);
        Array<__int64>::~Array<__int64>((void **)&v24);
        LODWORD(v11) = v23;
        v3 = v22;
      }
    }
    v21 = 0;
    for ( k = 0; k < (unsigned int)v11; ++k )
    {
      v24 = 0;
      v13 = &v3[k];
      GetDBName(ExistingFileName, 0x104u, v29, *v13);
      v20 = 0;
      v4 = OpenComponentLibraryEx(ExistingFileName, 1, &v20);
      if ( v4 >= 0 )
        v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, void ***))v20)(v20, &IID_ITSComponentRecords, &v24);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v4 < 0 )
      {
        if ( v4 != -2147217387 )
          goto LABEL_45;
        v4 = StringCchPrintfW(NewFileName, 0x104u, L"%s%s", ExistingFileName, L".corrupt");
        if ( v4 < 0 )
          goto LABEL_45;
        MoveFileW(ExistingFileName, NewFileName);
      }
      else
      {
        (*((void (__fastcall **)(void **))*v24 + 2))(v24);
        v14 = v21;
        if ( !v21 )
        {
          v14 = *v13;
          v21 = *v13;
        }
        if ( v14 - *v13 >= *(unsigned int *)&Data )
        {
          *v13 = -1;
          break;
        }
      }
      *v13 = -1;
    }
    v15 = 0;
    v16 = v30;
    while ( v15 < (unsigned int)v11 )
    {
      v17 = v3[v15];
      if ( v17 != -1 )
      {
        GetDBName(ExistingFileName, 0x104u, v29, v17);
        Entry = _RegAllocateEntry(ExistingFileName);
        if ( !Entry )
        {
          v4 = -2147024882;
          break;
        }
        *(_QWORD *)Entry = *v16;
        *v16 = Entry;
      }
      ++v15;
    }
LABEL_45:
    FindClose(FirstFileW);
  }
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007814  mov     [rsp+arg_10], rsi
0x180007819  push    rdi
0x18000781a  push    r12
0x18000781c  push    r13
0x18000781e  push    r14
0x180007820  push    r15
0x180007822  sub     rsp, 910h
0x180007829  mov     rax, cs:__security_cookie
0x180007830  xor     rax, rsp
0x180007833  mov     [rsp+938h+var_38], rax
0x18000783b  mov     [rsp+938h+var_8C0], rdx
0x180007840  mov     rdi, rcx
0x180007843  mov     [rsp+938h+var_8C8], rcx
0x180007848  xor     esi, esi
0x18000784a  mov     [rsp+938h+var_8F8], rsi
0x18000784f  mov     [rsp+938h+var_8F0], rsi
0x180007854  xor     r15d, r15d
0x180007857  mov     [rsp+938h+var_8D0], r15
0x18000785c  xor     edx, edx; Val
0x18000785e  mov     r8d, 250h; Size
0x180007864  lea     rcx, [rsp+938h+FindFileData]; void *
0x18000786c  call    memset_0
0x180007871  lea     rax, aRClb_0; "\\R????????????.clb"
0x180007878  mov     [rsp+938h+var_918], rax
0x18000787d  mov     r9, rdi
0x180007880  lea     r8, aSS_0; "%s%s"
0x180007887  mov     edx, 104h; unsigned __int64
0x18000788c  lea     rcx, [rsp+938h+FileName]; unsigned __int16 *
0x180007894  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007899  mov     edi, eax
0x18000789b  test    eax, eax
0x18000789d  js      short loc_1800078D2
0x18000789f  lea     rdx, [rsp+938h+FindFileData]; lpFindFileData
0x1800078a7  lea     rcx, [rsp+938h+FileName]; lpFileName
0x1800078af  call    cs:__imp_FindFirstFileW
0x1800078b5  mov     r13, rax
0x1800078b8  mov     [rsp+938h+var_900], rax
0x1800078bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800078c1  jnz     short loc_1800078F7
0x1800078c3  call    cs:__imp_GetLastError
0x1800078c9  mov     edi, eax
0x1800078cb  cmp     eax, 2
0x1800078ce  jnz     short loc_1800078E1
0x1800078d0  xor     edi, edi
0x1800078d2  lea     rcx, [rsp+938h+var_8F8]
0x1800078d7  call    ??1?$Array@_J@@QEAA@XZ; Array<__int64>::~Array<__int64>(void)
0x1800078dc  jmp     loc_180007BF8
0x1800078e1  test    eax, eax
0x1800078e3  jle     loc_180007BEA
0x1800078e9  movzx   edi, ax
0x1800078ec  or      edi, 80070000h
0x1800078f2  jmp     loc_180007BEA
0x1800078f7  lea     r8, [rsp+938h+var_8D0]
0x1800078fc  lea     rdx, aR012i64xClb; "R%012I64x.clb"
0x180007903  lea     rcx, [rsp+938h+FindFileData.cFileName]; Buffer
0x18000790b  call    cs:__imp_swscanf
0x180007911  nop
0x180007912  lea     edx, [r15+1]
0x180007916  lea     rcx, [rsp+938h+var_8F8]
0x18000791b  call    ?setSize@?$Array@_J@@QEAAXI@Z; Array<__int64>::setSize(uint)
0x180007920  movsxd  r15, dword ptr [rsp+938h+var_8F0]
0x180007925  lea     eax, [r15-1]
0x180007929  movsxd  rcx, eax
0x18000792c  mov     rsi, [rsp+938h+var_8F8]
0x180007931  mov     rax, [rsp+938h+var_8D0]
0x180007936  mov     [rsi+rcx*8], rax
0x18000793a  lea     rdx, [rsp+938h+FindFileData]; lpFindFileData
0x180007942  mov     rcx, r13; hFindFile
0x180007945  call    cs:__imp_FindNextFileW
0x18000794b  test    eax, eax
0x18000794d  jnz     short loc_1800078F7
0x18000794f  mov     [rsp+938h+var_8E0], rsi
0x180007954  mov     [rsp+938h+var_8D8], r15d
0x180007959  mov     [rsp+938h+var_8D4], 8
0x180007961  lea     rax, ??_7SortDescVersions@@6B@; const SortDescVersions::`vftable'
0x180007968  mov     [rsp+938h+var_8E8], rax
0x18000796d  lea     r12d, [r15-1]
0x180007971  mov     r8d, r12d
0x180007974  xor     edx, edx
0x180007976  lea     rcx, [rsp+938h+var_8E8]
0x18000797b  call    ?SortRange@?$CQuickSort@_J@@AEAAXHH@Z; CQuickSort<__int64>::SortRange(int,int)
0x180007980  test    r12d, r12d
0x180007983  jz      loc_180007A29
0x180007989  xor     r14d, r14d
0x18000798c  mov     rdx, [rsi+r15*8-8]
0x180007991  movsxd  rax, r14d
0x180007994  mov     rcx, [rsi+rax*8]
0x180007998  sub     rcx, rdx
0x18000799b  mov     rax, 7FFFFFFFFFFFh
0x1800079a5  cmp     rcx, rax
0x1800079a8  jle     short loc_1800079B2
0x1800079aa  inc     r14d
0x1800079ad  cmp     r14d, r12d
0x1800079b0  jb      short loc_180007991
0x1800079b2  test    r14d, r14d
0x1800079b5  jz      short loc_180007A29
0x1800079b7  mov     [rsp+938h+var_8E8], 0
0x1800079c0  mov     [rsp+938h+var_8E0], 0
0x1800079c9  mov     r12d, r14d
0x1800079cc  cmp     r12d, r15d
0x1800079cf  jnb     short loc_1800079E7
0x1800079d1  movsxd  rax, r12d
0x1800079d4  lea     rdx, [rsi+rax*8]
0x1800079d8  lea     rcx, [rsp+938h+var_8E8]
0x1800079dd  call    ?append@?$Array@_J@@QEAAXAEB_J@Z; Array<__int64>::append(__int64 const &)
0x1800079e2  inc     r12d
0x1800079e5  jmp     short loc_1800079CC
0x1800079e7  xor     r15d, r15d
0x1800079ea  cmp     r15d, r14d
0x1800079ed  jnb     short loc_180007A05
0x1800079ef  movsxd  rax, r15d
0x1800079f2  lea     rdx, [rsi+rax*8]
0x1800079f6  lea     rcx, [rsp+938h+var_8E8]
0x1800079fb  call    ?append@?$Array@_J@@QEAAXAEB_J@Z; Array<__int64>::append(__int64 const &)
0x180007a00  inc     r15d
0x180007a03  jmp     short loc_1800079EA
0x180007a05  lea     rdx, [rsp+938h+var_8E8]
0x180007a0a  lea     rcx, [rsp+938h+var_8F8]
0x180007a0f  call    ??4?$Array@_J@@QEAAAEAV0@AEBV0@@Z; Array<__int64>::operator=(Array<__int64> const &)
0x180007a14  nop
0x180007a15  lea     rcx, [rsp+938h+var_8E8]
0x180007a1a  call    ??1?$Array@_J@@QEAA@XZ; Array<__int64>::~Array<__int64>(void)
0x180007a1f  mov     r15d, dword ptr [rsp+938h+var_8F0]
0x180007a24  mov     rsi, [rsp+938h+var_8F8]
0x180007a29  xor     edx, edx
0x180007a2b  mov     [rsp+938h+var_900], rdx
0x180007a30  xor     r12d, r12d
0x180007a33  cmp     r12d, r15d
0x180007a36  jnb     loc_180007B08
0x180007a3c  mov     [rsp+938h+var_8E8], 0
0x180007a45  movsxd  rax, r12d
0x180007a48  lea     r14, [rsi+rax*8]
0x180007a4c  mov     r9, [r14]; __int64
0x180007a4f  mov     r8, [rsp+938h+var_8C8]; unsigned __int16 *
0x180007a54  mov     edx, 104h; unsigned __int64
0x180007a59  lea     rcx, [rsp+938h+ExistingFileName]; unsigned __int16 *
0x180007a61  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x180007a66  mov     [rsp+938h+var_908], 0
0x180007a6f  lea     r8, [rsp+938h+var_908]
0x180007a74  mov     edx, 1
0x180007a79  lea     rcx, [rsp+938h+ExistingFileName]
0x180007a81  call    cs:__imp_OpenComponentLibraryEx
0x180007a87  mov     edi, eax
0x180007a89  test    eax, eax
0x180007a8b  js      short loc_180007AAB
0x180007a8d  mov     rcx, [rsp+938h+var_908]
0x180007a92  mov     rax, [rcx]
0x180007a95  lea     r8, [rsp+938h+var_8E8]
0x180007a9a  lea     rdx, ?IID_ITSComponentRecords@@3U_GUID@@B; _GUID const IID_ITSComponentRecords
0x180007aa1  mov     rax, [rax]
0x180007aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa9  mov     edi, eax
0x180007aab  mov     rcx, [rsp+938h+var_908]
0x180007ab0  test    rcx, rcx
0x180007ab3  jz      short loc_180007AC1
0x180007ab5  mov     rax, [rcx]
0x180007ab8  mov     rax, [rax+10h]
0x180007abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac1  test    edi, edi
0x180007ac3  js      loc_180007B6B
0x180007ac9  mov     rcx, [rsp+938h+var_8E8]
0x180007ace  mov     rax, [rcx]
0x180007ad1  mov     rax, [rax+10h]
0x180007ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ada  mov     rdx, [rsp+938h+var_900]
0x180007adf  test    rdx, rdx
0x180007ae2  jnz     short loc_180007AEC
0x180007ae4  mov     rdx, [r14]
0x180007ae7  mov     [rsp+938h+var_900], rdx
0x180007aec  mov     rcx, rdx
0x180007aef  sub     rcx, [r14]
0x180007af2  mov     eax, cs:Data
0x180007af8  cmp     rcx, rax
0x180007afb  jl      loc_180007BBC
0x180007b01  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180007b08  xor     r14d, r14d
0x180007b0b  mov     r12, [rsp+938h+var_8C0]
0x180007b10  cmp     r14d, r15d
0x180007b13  jnb     loc_180007BE0
0x180007b19  movsxd  rax, r14d
0x180007b1c  mov     r9, [rsi+rax*8]; __int64
0x180007b20  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180007b24  jz      short loc_180007B5A
0x180007b26  mov     r8, [rsp+938h+var_8C8]; unsigned __int16 *
0x180007b2b  mov     edx, 104h; unsigned __int64
0x180007b30  lea     rcx, [rsp+938h+ExistingFileName]; unsigned __int16 *
0x180007b38  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x180007b3d  lea     rcx, [rsp+938h+ExistingFileName]; unsigned __int16 *
0x180007b45  call    ?_RegAllocateEntry@@YAPEAUDELVERSION@@PEBG@Z; _RegAllocateEntry(ushort const *)
0x180007b4a  test    rax, rax
0x180007b4d  jz      short loc_180007BCB
0x180007b4f  mov     rcx, [r12]
0x180007b53  mov     [rax], rcx
0x180007b56  mov     [r12], rax
0x180007b5a  inc     r14d
0x180007b5d  jmp     short loc_180007B10
0x180007b5f  lea     rcx, [rsp+938h+var_8E8]
0x180007b64  call    ??1?$Array@_J@@QEAA@XZ; Array<__int64>::~Array<__int64>(void)
0x180007b69  jmp     short loc_180007BD2
0x180007b6b  cmp     edi, 80041015h
0x180007b71  jnz     short loc_180007BE0
0x180007b73  lea     rax, aCorrupt_0; ".corrupt"
0x180007b7a  mov     [rsp+938h+var_918], rax
0x180007b7f  lea     r9, [rsp+938h+ExistingFileName]
0x180007b87  lea     r8, aSS_0; "%s%s"
0x180007b8e  mov     edx, 104h; unsigned __int64
0x180007b93  lea     rcx, [rsp+938h+NewFileName]; unsigned __int16 *
0x180007b9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007ba0  mov     edi, eax
0x180007ba2  test    eax, eax
0x180007ba4  js      short loc_180007BE0
0x180007ba6  lea     rdx, [rsp+938h+NewFileName]; lpNewFileName
0x180007bae  lea     rcx, [rsp+938h+ExistingFileName]; lpExistingFileName
0x180007bb6  call    cs:__imp_MoveFileW
0x180007bbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007bc0  mov     [r14], rax
0x180007bc3  inc     r12d
0x180007bc6  jmp     loc_180007A33
0x180007bcb  mov     edi, 8007000Eh
0x180007bd0  jmp     short loc_180007BE0
0x180007bd2  mov     edi, dword ptr [rsp+938h+var_908]
0x180007bd6  mov     r13, [rsp+938h+var_900]
0x180007bdb  mov     rsi, [rsp+938h+var_8F8]
0x180007be0  mov     rcx, r13; hFindFile
0x180007be3  call    cs:__imp_FindClose
0x180007be9  nop
0x180007bea  test    rsi, rsi
0x180007bed  jz      short loc_180007BF8
0x180007bef  mov     rcx, rsi; pv
0x180007bf2  call    cs:__imp_CoTaskMemFree
0x180007bf8  mov     eax, edi
0x180007bfa  mov     rcx, [rsp+938h+var_38]
0x180007c02  xor     rcx, rsp; StackCookie
0x180007c05  call    __security_check_cookie
0x180007c0a  mov     rsi, [rsp+938h+arg_10]
0x180007c12  add     rsp, 910h
0x180007c19  pop     r15
0x180007c1b  pop     r14
0x180007c1d  pop     r13
0x180007c1f  pop     r12
0x180007c21  pop     rdi
0x180007c22  retn
```
