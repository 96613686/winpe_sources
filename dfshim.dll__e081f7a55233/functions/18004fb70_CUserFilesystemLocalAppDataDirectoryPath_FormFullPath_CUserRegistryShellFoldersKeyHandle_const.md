# CUserFilesystemLocalAppDataDirectoryPath::FormFullPath(CUserRegistryShellFoldersKeyHandle const &)

- ea: `0x18004fb70`
- end: `0x18004fe8f`
- name: `?FormFullPath@CUserFilesystemLocalAppDataDirectoryPath@@QEAAJAEBVCUserRegistryShellFoldersKeyHandle@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(CUserFilesystemLocalAppDataDirectoryPath *__hidden this, const struct CUserRegistryShellFoldersKeyHandle *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004fe98`

## callees

- `0x1800069cd`
- `0x1800069d9`
- `0x1800069fd`
- `0x18000e944`
- `0x18000e970`
- `0x18001fc6c`
- `0x18003fae0`
- `0x18004fb70`
- `0x180053394`
- `0x1800fe440`
- `0x18010a220`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004fbcb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004fbcb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004fc8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004fca5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004fc8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004fca5`

## string_xrefs

- `0x18004fbc4`: `shell32.dll`
- `0x18004fbdd`: `SHGetSpecialFolderPathW`

## pseudocode

```c
__int64 __fastcall CUserFilesystemLocalAppDataDirectoryPath::FormFullPath(
        CUserFilesystemLocalAppDataDirectoryPath *this,
        const struct CUserRegistryShellFoldersKeyHandle *a2)
{
  LPCWSTR v2; // r8
  void *v3; // rbx
  HMODULE LibraryW; // rax
  HMODULE v7; // rsi
  int v8; // r14d
  BOOL (__stdcall *SHGetSpecialFolderPathW)(HWND, LPWSTR, int, BOOL); // r15
  void *v10; // rax
  void *v11; // rdi
  __int64 v12; // rsi
  int v13; // eax
  LPCWSTR v14; // r14
  __int64 v15; // rdi
  int v16; // r8d
  const struct _LUNICODE_STRING *v17; // r9
  int PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable; // edi
  int v19; // r8d
  void *v20; // rcx
  void *v22; // rcx
  __m128i v23; // [rsp+40h] [rbp-89h] BYREF
  void *lpMem; // [rsp+50h] [rbp-79h]
  __m128i v25; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR v26; // [rsp+68h] [rbp-61h]
  _OWORD v27[2]; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int64 v28[2]; // [rsp+90h] [rbp-39h] BYREF
  const wchar_t *v29; // [rsp+A0h] [rbp-29h]
  __int64 v30; // [rsp+A8h] [rbp-21h]
  __int64 v31; // [rsp+B0h] [rbp-19h]
  LPCWSTR v32; // [rsp+B8h] [rbp-11h]
  __int128 v33; // [rsp+C0h] [rbp-9h]
  const wchar_t *v34; // [rsp+D0h] [rbp+7h]
  char v35; // [rsp+140h] [rbp+77h] BYREF

  v2 = AppDataPath;
  v3 = 0;
  lpMem = 0;
  v23 = 0u;
  v35 = 0;
  if ( AppDataPath )
    goto LABEL_15;
  if ( (GetVersion_0() & 0x80000000) == 0 )
  {
    LibraryW = LoadLibraryW(L"shell32.dll");
    v7 = LibraryW;
    if ( LibraryW )
    {
      v8 = 0;
      SHGetSpecialFolderPathW = (BOOL (__stdcall *)(HWND, LPWSTR, int, BOOL))GetProcAddress_0(
                                                                               LibraryW,
                                                                               "SHGetSpecialFolderPathW");
      if ( SHGetSpecialFolderPathW )
      {
        v10 = operator new(0x20Au);
        v11 = v10;
        if ( v10 )
        {
          *((_WORD *)v10 + 260) = 0;
          if ( ((unsigned int (__fastcall *)(_QWORD, void *, __int64, _QWORD))SHGetSpecialFolderPathW)(0, v10, 28, 0) )
          {
            if ( _InterlockedCompareExchange64((volatile signed __int64 *)&AppDataPath, (signed __int64)v11, 0) )
            {
              operator delete(v11);
            }
            else if ( !AppDataPathHolder )
            {
              AppDataPathHolder = v11;
            }
            v8 = 1;
          }
          else
          {
            operator delete(v11);
          }
        }
      }
      FreeLibrary_0(v7);
      if ( v8 )
      {
        v2 = AppDataPath;
LABEL_15:
        *((_WORD *)v2 + 260) = 0;
        v12 = 2LL * lstrlenW(AppDataPath);
        v25.m128i_i64[0] = v12;
        v13 = lstrlenW(AppDataPath);
        v14 = AppDataPath;
        v15 = 2LL * (v13 + 1);
        v26 = AppDataPath;
        v25.m128i_i64[1] = v15;
        goto LABEL_16;
      }
    }
  }
  PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = Windows::Isolation::Implementation::Rtl::QueryValue(
                                                                             *(_QWORD *)a2,
                                                                             g_LUNICODE_STRING_Local_space_AppData,
                                                                             &v35,
                                                                             &v23);
  if ( PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable < 0 )
    goto LABEL_28;
  if ( !v35 )
  {
    v22 = lpMem;
    if ( lpMem )
    {
      v23 = 0u;
      lpMem = 0;
      IsolationFreeStringRoutine(v22);
    }
    PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = GetPerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable((struct _LUNICODE_STRING *)&v23);
    if ( PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable < 0 )
    {
LABEL_28:
      v20 = lpMem;
      if ( !lpMem )
        return (unsigned int)PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable;
      goto LABEL_25;
    }
  }
  v26 = (LPCWSTR)lpMem;
  v3 = lpMem;
  v14 = (LPCWSTR)lpMem;
  v12 = v23.m128i_i64[0];
  v15 = _mm_srli_si128(v23, 8).m128i_u64[0];
  v25 = v23;
LABEL_16:
  if ( (unsigned __int8)GetVersion_0() >= 6u )
  {
LABEL_21:
    *(_OWORD *)v28 = g_LUNICODE_STRING__bslash__q__q__bslash_;
    v30 = v12;
    v29 = L"\\??\\";
    v33 = g_LUNICODE_STRING__bslash_Apps_bslash_;
    v31 = v15;
    v32 = v14;
    v34 = L"\\Apps\\";
    PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = Windows::Rtl::Concatenate(
                                                                               this,
                                                                               (struct _LUNICODE_STRING *)3,
                                                                               (unsigned __int64)v28,
                                                                               v17);
    if ( PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable >= 0 )
    {
      PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = 0;
      if ( !v3 )
        return (unsigned int)PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable;
    }
    goto LABEL_23;
  }
  lpMem = 0;
  v23 = 0;
  v27[0] = 0;
  PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = RtlSplitLUnicodeString(
                                                                             2,
                                                                             (unsigned int)&v25,
                                                                             v16,
                                                                             0,
                                                                             92,
                                                                             (__int64)&v23,
                                                                             (__int64)v27);
  if ( PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable >= 0 )
  {
    if ( *(_QWORD *)&v27[0]
      || (v26 = (LPCWSTR)lpMem,
          v25 = v23,
          PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable = RtlSplitLUnicodeString(
                                                                                     2,
                                                                                     (unsigned int)&v25,
                                                                                     v19,
                                                                                     0,
                                                                                     92,
                                                                                     (__int64)&v23,
                                                                                     (__int64)v27),
          PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable >= 0) )
    {
      v14 = (LPCWSTR)lpMem;
      v12 = v23.m128i_i64[0];
      v15 = _mm_srli_si128(v23, 8).m128i_u64[0];
      goto LABEL_21;
    }
  }
LABEL_23:
  if ( v3 )
  {
    v20 = v3;
LABEL_25:
    IsolationFreeStringRoutine(v20);
  }
  return (unsigned int)PerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable;
}

```

## disassembly

```asm
0x18004fb70  push    rbp
0x18004fb72  push    rbx
0x18004fb73  push    rsi
0x18004fb74  push    rdi
0x18004fb75  push    r12
0x18004fb77  push    r13
0x18004fb79  push    r14
0x18004fb7b  push    r15
0x18004fb7d  lea     rbp, [rsp-1Fh]
0x18004fb82  sub     rsp, 0E8h
0x18004fb89  mov     r8, cs:?AppDataPath@@3PEAGEA; ushort * AppDataPath
0x18004fb90  xor     r15d, r15d
0x18004fb93  mov     qword ptr [rsp+120h+var_E0+8], r15
0x18004fb98  mov     ebx, r15d
0x18004fb9b  mov     [rbp+57h+lpMem], rbx
0x18004fb9f  mov     r12, rdx
0x18004fba2  mov     qword ptr [rsp+120h+var_E0], r15
0x18004fba7  mov     r13, rcx
0x18004fbaa  mov     [rbp+57h+arg_10], r15b
0x18004fbae  test    r8, r8
0x18004fbb1  jnz     loc_18004FC7F
0x18004fbb7  call    GetVersion_0
0x18004fbbc  test    eax, eax
0x18004fbbe  js      loc_18004FDFE
0x18004fbc4  lea     rcx, aShell32Dll_0; "shell32.dll"
0x18004fbcb  call    cs:__imp_LoadLibraryW
0x18004fbd1  mov     rsi, rax
0x18004fbd4  test    rax, rax
0x18004fbd7  jz      loc_18004FDFE
0x18004fbdd  lea     rdx, aShgetspecialfo; "SHGetSpecialFolderPathW"
0x18004fbe4  mov     rcx, rax; hModule
0x18004fbe7  mov     r14d, r15d
0x18004fbea  call    GetProcAddress_0
0x18004fbef  mov     r15, rax
0x18004fbf2  test    rax, rax
0x18004fbf5  jz      short loc_18004FC64
0x18004fbf7  mov     ecx, 20Ah; unsigned __int64
0x18004fbfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fc01  mov     rdi, rax
0x18004fc04  test    rax, rax
0x18004fc07  jz      short loc_18004FC64
0x18004fc09  xor     ecx, ecx
0x18004fc0b  lea     r8d, [rbx+1Ch]
0x18004fc0f  mov     [rax+208h], cx
0x18004fc16  mov     rdx, rax
0x18004fc19  mov     rax, r15
0x18004fc1c  xor     r9d, r9d
0x18004fc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc24  xor     r15d, r15d
0x18004fc27  test    eax, eax
0x18004fc29  jnz     short loc_18004FC35
0x18004fc2b  mov     rcx, rdi; void *
0x18004fc2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fc33  jmp     short loc_18004FC67
0x18004fc35  xor     eax, eax
0x18004fc37  lock cmpxchg cs:?AppDataPath@@3PEAGEA, rdi; ushort * AppDataPath
0x18004fc40  jnz     short loc_18004FC54
0x18004fc42  cmp     cs:?AppDataPathHolder@@3VStringHolder@@A, r15; StringHolder AppDataPathHolder
0x18004fc49  jnz     short loc_18004FC5C
0x18004fc4b  mov     cs:?AppDataPathHolder@@3VStringHolder@@A, rdi; StringHolder AppDataPathHolder
0x18004fc52  jmp     short loc_18004FC5C
0x18004fc54  mov     rcx, rdi; void *
0x18004fc57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004fc5c  mov     r14d, 1
0x18004fc62  jmp     short loc_18004FC67
0x18004fc64  xor     r15d, r15d
0x18004fc67  mov     rcx, rsi; hLibModule
0x18004fc6a  call    FreeLibrary_0
0x18004fc6f  test    r14d, r14d
0x18004fc72  jz      loc_18004FDFE
0x18004fc78  mov     r8, cs:?AppDataPath@@3PEAGEA; ushort * AppDataPath
0x18004fc7f  mov     [r8+208h], r15w
0x18004fc87  mov     rcx, cs:?AppDataPath@@3PEAGEA; lpString
0x18004fc8e  call    cs:__imp_lstrlenW
0x18004fc94  mov     rcx, cs:?AppDataPath@@3PEAGEA; lpString
0x18004fc9b  movsxd  rsi, eax
0x18004fc9e  add     rsi, rsi
0x18004fca1  mov     qword ptr [rbp+57h+var_C8], rsi
0x18004fca5  call    cs:__imp_lstrlenW
0x18004fcab  mov     r14, cs:?AppDataPath@@3PEAGEA; ushort * AppDataPath
0x18004fcb2  inc     eax
0x18004fcb4  movsxd  rdi, eax
0x18004fcb7  add     rdi, rdi
0x18004fcba  mov     [rbp+57h+var_B8], r14
0x18004fcbe  mov     qword ptr [rbp+57h+var_C8+8], rdi
0x18004fcc2  call    GetVersion_0
0x18004fcc7  cmp     al, 6
0x18004fcc9  jnb     loc_18004FD80
0x18004fccf  xor     eax, eax
0x18004fcd1  lea     rdx, [rbp+57h+var_C8]
0x18004fcd5  mov     [rbp+57h+lpMem], rax
0x18004fcd9  mov     esi, 5Ch ; '\'
0x18004fcde  lea     rax, [rbp+57h+var_B0]
0x18004fce2  xorps   xmm0, xmm0
0x18004fce5  mov     [rsp+120h+var_F0], rax
0x18004fcea  xorps   xmm1, xmm1
0x18004fced  lea     rax, [rsp+120h+var_E0]
0x18004fcf2  xor     r9d, r9d
0x18004fcf5  mov     [rsp+120h+var_F8], rax
0x18004fcfa  lea     r14d, [rsi-5Ah]
0x18004fcfe  mov     ecx, r14d
0x18004fd01  mov     [rsp+120h+var_100], rsi
0x18004fd06  movups  [rsp+120h+var_E0], xmm0
0x18004fd0b  movups  [rbp+57h+var_B0], xmm1
0x18004fd0f  call    RtlSplitLUnicodeString
0x18004fd14  mov     edi, eax
0x18004fd16  test    eax, eax
0x18004fd18  js      loc_18004FDDB
0x18004fd1e  cmp     qword ptr [rbp+57h+var_B0], r15
0x18004fd22  jnz     short loc_18004FD64
0x18004fd24  movups  xmm0, [rsp+120h+var_E0]
0x18004fd29  lea     rax, [rbp+57h+var_B0]
0x18004fd2d  xor     r9d, r9d
0x18004fd30  movsd   xmm1, [rbp+57h+lpMem]
0x18004fd35  lea     rdx, [rbp+57h+var_C8]
0x18004fd39  mov     [rsp+120h+var_F0], rax
0x18004fd3e  mov     ecx, r14d
0x18004fd41  lea     rax, [rsp+120h+var_E0]
0x18004fd46  movsd   [rbp+57h+var_B8], xmm1
0x18004fd4b  mov     [rsp+120h+var_F8], rax
0x18004fd50  mov     [rsp+120h+var_100], rsi
0x18004fd55  movups  [rbp+57h+var_C8], xmm0
0x18004fd59  call    RtlSplitLUnicodeString
0x18004fd5e  mov     edi, eax
0x18004fd60  test    eax, eax
0x18004fd62  js      short loc_18004FDDB
0x18004fd64  movups  xmm2, [rsp+120h+var_E0]
0x18004fd69  mov     r14, [rbp+57h+lpMem]
0x18004fd6d  movdqa  xmm1, xmm2
0x18004fd71  movq    rsi, xmm2
0x18004fd76  psrldq  xmm1, 8
0x18004fd7b  movq    rdi, xmm1
0x18004fd80  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x18004fd87  lea     r8, [rbp+57h+var_90]; unsigned __int64
0x18004fd8b  mov     edx, 3; struct _LUNICODE_STRING *
0x18004fd90  movsd   xmm1, cs:off_180137778; "\\??\\"
0x18004fd98  mov     rcx, r13; this
0x18004fd9b  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x18004fd9f  movups  xmm0, cs:g_LUNICODE_STRING__bslash_Apps_bslash_
0x18004fda6  mov     [rbp+57h+var_78], rsi
0x18004fdaa  movsd   [rbp+57h+var_80], xmm1
0x18004fdaf  movsd   xmm1, cs:off_180138300; "\\Apps\\"
0x18004fdb7  movaps  [rbp+57h+var_60], xmm0
0x18004fdbb  mov     [rbp+57h+var_70], rdi
0x18004fdbf  mov     [rbp+57h+var_68], r14
0x18004fdc3  movsd   [rbp+57h+var_50], xmm1
0x18004fdc8  call    ?Concatenate@Rtl@Windows@@YAJPEAU_LUNICODE_STRING@@_KQEBU3@@Z; Windows::Rtl::Concatenate(_LUNICODE_STRING *,unsigned __int64,_LUNICODE_STRING const * const)
0x18004fdcd  mov     edi, eax
0x18004fdcf  test    eax, eax
0x18004fdd1  js      short loc_18004FDDB
0x18004fdd3  mov     edi, r15d
0x18004fdd6  test    rbx, rbx
0x18004fdd9  jz      short loc_18004FDE8
0x18004fddb  test    rbx, rbx
0x18004fdde  jz      short loc_18004FDE8
0x18004fde0  mov     rcx, rbx; lpMem
0x18004fde3  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18004fde8  mov     eax, edi
0x18004fdea  add     rsp, 0E8h
0x18004fdf1  pop     r15
0x18004fdf3  pop     r14
0x18004fdf5  pop     r13
0x18004fdf7  pop     r12
0x18004fdf9  pop     rdi
0x18004fdfa  pop     rsi
0x18004fdfb  pop     rbx
0x18004fdfc  pop     rbp
0x18004fdfd  retn
0x18004fdfe  mov     rcx, [r12]
0x18004fe02  lea     r9, [rsp+120h+var_E0]
0x18004fe07  lea     r8, [rbp+57h+arg_10]
0x18004fe0b  lea     rdx, g_LUNICODE_STRING_Local_space_AppData
0x18004fe12  call    ?QueryValue@Rtl@Implementation@Isolation@Windows@@YAJU_ISOLATED_KEY@134@PEBU_LUNICODE_STRING@@AEAEPEAU6@PEAK@Z; Windows::Isolation::Implementation::Rtl::QueryValue(Windows::Isolation::Rtl::_ISOLATED_KEY,_LUNICODE_STRING const *,uchar &,_LUNICODE_STRING *,ulong *)
0x18004fe17  mov     edi, eax
0x18004fe19  test    eax, eax
0x18004fe1b  jns     short loc_18004FE28
0x18004fe1d  mov     rcx, [rbp+57h+lpMem]
0x18004fe21  test    rcx, rcx
0x18004fe24  jz      short loc_18004FDE8
0x18004fe26  jmp     short loc_18004FDE3
0x18004fe28  cmp     [rbp+57h+arg_10], r15b
0x18004fe2c  jnz     short loc_18004FE5A
0x18004fe2e  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18004fe32  test    rcx, rcx
0x18004fe35  jz      short loc_18004FE4A
0x18004fe37  mov     qword ptr [rsp+120h+var_E0+8], r15
0x18004fe3c  mov     qword ptr [rsp+120h+var_E0], r15
0x18004fe41  mov     [rbp+57h+lpMem], r15
0x18004fe45  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18004fe4a  lea     rcx, [rsp+120h+var_E0]; this
0x18004fe4f  call    ?GetPerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable@@YAJPEAU_LUNICODE_STRING@@@Z; GetPerUserLocalAppDataShellFolderWin32FullPathFromFromEnvironmentVariable(_LUNICODE_STRING *)
0x18004fe54  mov     edi, eax
0x18004fe56  test    eax, eax
0x18004fe58  js      short loc_18004FE1D
0x18004fe5a  movsd   xmm0, [rbp+57h+lpMem]
0x18004fe5f  movups  xmm1, [rsp+120h+var_E0]
0x18004fe64  movsd   [rbp+57h+var_B8], xmm0
0x18004fe69  movq    rbx, xmm0
0x18004fe6e  movq    r14, xmm0
0x18004fe73  movq    rsi, xmm1
0x18004fe78  movdqa  xmm0, xmm1
0x18004fe7c  psrldq  xmm0, 8
0x18004fe81  movq    rdi, xmm0
0x18004fe86  movups  [rbp+57h+var_C8], xmm1
0x18004fe8a  jmp     loc_18004FCC2
```
