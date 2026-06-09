# SCHEMA_FILE_LIST::Initialize(void)

- ea: `0x180055d04`
- end: `0x180056068`
- name: `?Initialize@SCHEMA_FILE_LIST@@QEAAJXZ`
- size: `868`
- prototype: `__int64 __fastcall(SCHEMA_FILE_LIST *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003b1ec`

## callees

- `0x180010468`
- `0x180011130`
- `0x18001c250`
- `0x18004127c`
- `0x180055d04`
- `0x180056128`
- `0x1800561b0`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f9e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055fd2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055ff0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055fd2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055ff0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055f90`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055f90`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180055e2f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180055e2f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056028`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056032`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005603d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056028`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056032`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005603d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055e0d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055ef9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055f3c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056009`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055e0d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055ef9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055f3c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056009`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055d5e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055d83`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055db8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055d5e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055d83`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055db8`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180055e8c`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180055f63`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180055e8c`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180055f63`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055df9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055ebd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055df9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055ebd`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055dde`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055ea4`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055dde`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055ea4`

## string_xrefs

- `0x180055dee`: `*.xml`
- `0x180055f58`: `IIS_schema.xml`

## pseudocode

```c
__int64 __fastcall SCHEMA_FILE_LIST::Initialize(SCHEMA_FILE_LIST *this)
{
  signed int SchemaDirectory; // ebx
  const WCHAR *Str; // rax
  HANDLE FirstFile; // rsi
  signed int LastError; // eax
  int v6; // r14d
  __int64 v7; // rax
  _QWORD *v8; // rdi
  DWORD nFileSizeLow; // ebx
  const unsigned __int16 *v10; // rax
  unsigned int v11; // eax
  int v12; // edx
  bool v13; // al
  signed int v14; // eax
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  DWORD v18; // [rsp+30h] [rbp-D0h]
  _BYTE v19[56]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[56]; // [rsp+A8h] [rbp-58h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v23[264]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v24[264]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v25[264]; // [rsp+750h] [rbp+650h] BYREF

  memset_0(v23, 0, 0x208u);
  STRU::STRU((STRU *)v20, v23, 0x104u);
  memset_0(v24, 0, 0x208u);
  STRU::STRU((STRU *)v21, v24, 0x104u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v25, 0, 0x208u);
  STRU::STRU((STRU *)v19, v25, 0x104u);
  SchemaDirectory = SCHEMA_FILE_LIST::QuerySchemaDirectory((struct STRU *)v20);
  if ( SchemaDirectory >= 0 )
  {
    SchemaDirectory = STRU::Copy((STRU *)v21, (const struct STRU *)v20);
    if ( SchemaDirectory >= 0 )
    {
      SchemaDirectory = STRU::Append((STRU *)v21, L"*.xml");
      if ( SchemaDirectory >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v21);
        FirstFile = FindFirstFileExW(Str, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
        if ( FirstFile == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          SchemaDirectory = LastError;
          if ( LastError > 0 )
            SchemaDirectory = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v6 = 0;
          do
          {
            if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
            {
              v7 = -1;
              do
                ++v7;
              while ( FindFileData.cFileName[v7] );
              if ( IsStringEqualOrdinalIgnoreCase(
                     (const unsigned __int16 *)&FindFileData.dwReserved0 + (unsigned int)v7,
                     L".xml") )
              {
                SchemaDirectory = STRU::Copy((STRU *)v19, (const struct STRU *)v20);
                if ( SchemaDirectory < 0 )
                  goto LABEL_29;
                SchemaDirectory = STRU::Append((STRU *)v19, FindFileData.cFileName);
                if ( SchemaDirectory < 0 )
                  goto LABEL_29;
                v8 = operator new(0x20u);
                if ( !v8 )
                {
                  SchemaDirectory = -2147024888;
                  goto LABEL_29;
                }
                *v8 = &SCHEMA_FILE_ENTRY::`vftable';
                v8[1] = 0;
                nFileSizeLow = FindFileData.nFileSizeLow;
                v10 = STRU::QueryStr((STRU *)v19);
                v8[2] = FindFileData.ftLastWriteTime;
                *((_DWORD *)v8 + 6) = nFileSizeLow;
                SchemaDirectory = SMALL_STRU::Copy((SMALL_STRU *)(v8 + 1), v10);
                if ( SchemaDirectory < 0 )
                  goto LABEL_30;
                v18 = FindFileData.nFileSizeLow;
                if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
                {
                  v11 = (unsigned int)STRU::QueryStr((STRU *)v19);
                  McTemplateU0zmx_EtwEventWriteTransfer(v18, v12, v11, (unsigned int)&FindFileData.ftLastWriteTime, v18);
                }
                v13 = IsStringEqualOrdinalIgnoreCase(FindFileData.cFileName, L"IIS_schema.xml");
                if ( v13 )
                  v6 = 1;
                SchemaDirectory = ARRAY_LIST::AddEntry(
                                    (SCHEMA_FILE_LIST *)((char *)this + 16),
                                    (struct IArrayListEntry *)v8,
                                    -!v13);
                if ( SchemaDirectory < 0 )
                  goto LABEL_30;
              }
            }
          }
          while ( FindNextFileW(FirstFile, &FindFileData) );
          v14 = GetLastError();
          if ( !v14 )
          {
            SchemaDirectory = -2147024883;
LABEL_29:
            v8 = 0;
LABEL_30:
            FindClose(FirstFile);
            if ( v8 )
              (*(void (__fastcall **)(_QWORD *))*v8)(v8);
            goto LABEL_36;
          }
          if ( v14 != 18 )
          {
            if ( v14 > 0 )
              SchemaDirectory = (unsigned __int16)v14 | 0x80070000;
            else
              SchemaDirectory = v14;
            goto LABEL_29;
          }
          FindClose(FirstFile);
          if ( !v6 )
          {
            if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
            {
              v15 = STRU::QueryStr((STRU *)v20);
              McTemplateU0z_EtwEventWriteTransfer(v16, NATIVERD_EVENT_MISSING_IIS_SCHEMA, v15);
            }
            SchemaDirectory = -2147024894;
          }
        }
      }
    }
  }
LABEL_36:
  STRU::~STRU((STRU *)v19);
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)SchemaDirectory;
}

```

## disassembly

```asm
0x180055d04  push    rbp
0x180055d06  push    rbx
0x180055d07  push    rsi
0x180055d08  push    rdi
0x180055d09  push    r12
0x180055d0b  push    r13
0x180055d0d  push    r14
0x180055d0f  push    r15
0x180055d11  lea     rbp, [rsp-878h]
0x180055d19  sub     rsp, 978h
0x180055d20  mov     rax, cs:__security_cookie
0x180055d27  xor     rax, rsp
0x180055d2a  mov     [rbp+8B0h+var_50], rax
0x180055d31  mov     r15, rcx
0x180055d34  mov     edi, 208h
0x180055d39  mov     r8d, edi; Size
0x180055d3c  lea     rcx, [rbp+8B0h+var_680]; void *
0x180055d43  xor     edx, edx; Val
0x180055d45  call    memset_0
0x180055d4a  mov     ebx, 104h
0x180055d4f  lea     rdx, [rbp+8B0h+var_680]
0x180055d56  mov     r8d, ebx
0x180055d59  lea     rcx, [rsp+9B0h+var_940]
0x180055d5e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180055d64  mov     r8d, edi; Size
0x180055d67  lea     rcx, [rbp+8B0h+var_470]; void *
0x180055d6e  xor     edx, edx; Val
0x180055d70  call    memset_0
0x180055d75  mov     r8d, ebx
0x180055d78  lea     rdx, [rbp+8B0h+var_470]
0x180055d7f  lea     rcx, [rbp+8B0h+var_908]
0x180055d83  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180055d89  xor     edx, edx; Val
0x180055d8b  lea     r8d, [rdi+48h]; Size
0x180055d8f  lea     rcx, [rbp+8B0h+FindFileData]; void *
0x180055d93  call    memset_0
0x180055d98  mov     r8d, edi; Size
0x180055d9b  lea     rcx, [rbp+8B0h+var_260]; void *
0x180055da2  xor     edx, edx; Val
0x180055da4  call    memset_0
0x180055da9  mov     r8d, ebx
0x180055dac  lea     rdx, [rbp+8B0h+var_260]
0x180055db3  lea     rcx, [rsp+9B0h+var_978]
0x180055db8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180055dbe  lea     rcx, [rsp+9B0h+var_940]; struct STRU *
0x180055dc3  call    ?QuerySchemaDirectory@SCHEMA_FILE_LIST@@SAJPEAVSTRU@@@Z; SCHEMA_FILE_LIST::QuerySchemaDirectory(STRU *)
0x180055dc8  xor     r12d, r12d
0x180055dcb  mov     ebx, eax
0x180055dcd  test    eax, eax
0x180055dcf  js      loc_180056023
0x180055dd5  lea     rdx, [rsp+9B0h+var_940]
0x180055dda  lea     rcx, [rbp+8B0h+var_908]
0x180055dde  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180055de4  mov     ebx, eax
0x180055de6  test    eax, eax
0x180055de8  js      loc_180056023
0x180055dee  lea     rdx, aXml_0; "*.xml"
0x180055df5  lea     rcx, [rbp+8B0h+var_908]
0x180055df9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180055dff  mov     ebx, eax
0x180055e01  test    eax, eax
0x180055e03  js      loc_180056023
0x180055e09  lea     rcx, [rbp+8B0h+var_908]
0x180055e0d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180055e13  lea     r13d, [r12+1]
0x180055e18  mov     [rsp+9B0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x180055e1d  mov     rcx, rax; lpFileName
0x180055e20  mov     [rsp+9B0h+lpSearchFilter], r12; lpSearchFilter
0x180055e25  mov     edx, r13d; fInfoLevelId
0x180055e28  lea     r8, [rbp+8B0h+FindFileData]; lpFindFileData
0x180055e2c  xor     r9d, r9d; fSearchOp
0x180055e2f  call    cs:__imp_FindFirstFileExW
0x180055e35  mov     rsi, rax
0x180055e38  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055e3c  jnz     short loc_180055E5C
0x180055e3e  call    cs:__imp_GetLastError
0x180055e44  mov     ebx, eax
0x180055e46  test    eax, eax
0x180055e48  jle     loc_180056023
0x180055e4e  movzx   ebx, ax
0x180055e51  or      ebx, 80070000h
0x180055e57  jmp     loc_180056023
0x180055e5c  mov     r14d, r12d
0x180055e5f  test    [rbp+8B0h+FindFileData], 10h
0x180055e63  jnz     loc_180055F89
0x180055e69  lea     rcx, [rbp+8B0h+var_8A4]
0x180055e6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055e71  inc     rax
0x180055e74  cmp     [rcx+rax*2], r12w
0x180055e79  jnz     short loc_180055E71
0x180055e7b  mov     eax, eax
0x180055e7d  lea     rcx, [rbp+8B0h+var_8AC]
0x180055e81  lea     rdx, aXml; ".xml"
0x180055e88  lea     rcx, [rcx+rax*2]
0x180055e8c  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180055e92  test    al, al
0x180055e94  jz      loc_180055F89
0x180055e9a  lea     rdx, [rsp+9B0h+var_940]
0x180055e9f  lea     rcx, [rsp+9B0h+var_978]
0x180055ea4  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180055eaa  mov     ebx, eax
0x180055eac  test    eax, eax
0x180055eae  js      loc_180055FCC
0x180055eb4  lea     rdx, [rbp+8B0h+var_8A4]
0x180055eb8  lea     rcx, [rsp+9B0h+var_978]
0x180055ebd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180055ec3  mov     ebx, eax
0x180055ec5  test    eax, eax
0x180055ec7  js      loc_180055FCC
0x180055ecd  mov     ecx, 20h ; ' '; Size
0x180055ed2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055ed7  mov     rdi, rax
0x180055eda  test    rax, rax
0x180055edd  jz      loc_180055FAF
0x180055ee3  lea     rax, ??_7SCHEMA_FILE_ENTRY@@6B@; const SCHEMA_FILE_ENTRY::`vftable'
0x180055eea  mov     [rdi], rax
0x180055eed  lea     rcx, [rsp+9B0h+var_978]
0x180055ef2  mov     [rdi+8], r12
0x180055ef6  mov     ebx, [rbp+8B0h+var_8B0]
0x180055ef9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180055eff  mov     rcx, [rbp+8B0h+var_8BC]
0x180055f03  mov     rdx, rax; unsigned __int16 *
0x180055f06  mov     [rdi+10h], rcx
0x180055f0a  lea     rcx, [rdi+8]; this
0x180055f0e  mov     [rdi+18h], ebx
0x180055f11  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180055f16  mov     ebx, eax
0x180055f18  test    eax, eax
0x180055f1a  js      loc_180055FCF
0x180055f20  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 10h
0x180055f27  mov     eax, [rbp+8B0h+var_8B4]
0x180055f2a  mov     dword ptr [rsp+9B0h+var_980+4], eax
0x180055f2e  mov     eax, [rbp+8B0h+var_8B0]
0x180055f31  mov     dword ptr [rsp+9B0h+var_980], eax
0x180055f35  jz      short loc_180055F58
0x180055f37  lea     rcx, [rsp+9B0h+var_978]
0x180055f3c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180055f42  mov     rcx, [rsp+9B0h+var_980]
0x180055f47  lea     r9, [rbp+8B0h+var_8BC]
0x180055f4b  mov     r8, rax
0x180055f4e  mov     [rsp+9B0h+lpSearchFilter], rcx
0x180055f53  call    McTemplateU0zmx_EtwEventWriteTransfer
0x180055f58  lea     rdx, aIisSchemaXml; "IIS_schema.xml"
0x180055f5f  lea     rcx, [rbp+8B0h+var_8A4]
0x180055f63  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180055f69  mov     rdx, rdi; struct IArrayListEntry *
0x180055f6c  lea     rcx, [r15+10h]; this
0x180055f70  test    al, al
0x180055f72  cmovnz  r14d, r13d
0x180055f76  neg     al
0x180055f78  sbb     r8d, r8d
0x180055f7b  not     r8d; unsigned int
0x180055f7e  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180055f83  mov     ebx, eax
0x180055f85  test    eax, eax
0x180055f87  js      short loc_180055FCF
0x180055f89  lea     rdx, [rbp+8B0h+FindFileData]; lpFindFileData
0x180055f8d  mov     rcx, rsi; hFindFile
0x180055f90  call    cs:__imp_FindNextFileW
0x180055f96  test    eax, eax
0x180055f98  jnz     loc_180055E5F
0x180055f9e  call    cs:__imp_GetLastError
0x180055fa4  test    eax, eax
0x180055fa6  jnz     short loc_180055FB6
0x180055fa8  mov     ebx, 8007000Dh
0x180055fad  jmp     short loc_180055FCC
0x180055faf  mov     ebx, 80070008h
0x180055fb4  jmp     short loc_180055FCC
0x180055fb6  cmp     eax, 12h
0x180055fb9  jz      short loc_180055FED
0x180055fbb  test    eax, eax
0x180055fbd  jg      short loc_180055FC3
0x180055fbf  mov     ebx, eax
0x180055fc1  jmp     short loc_180055FCC
0x180055fc3  movzx   ebx, ax
0x180055fc6  or      ebx, 80070000h
0x180055fcc  mov     rdi, r12
0x180055fcf  mov     rcx, rsi; hFindFile
0x180055fd2  call    cs:__imp_FindClose
0x180055fd8  test    rdi, rdi
0x180055fdb  jz      short loc_180056023
0x180055fdd  mov     rax, [rdi]
0x180055fe0  mov     rcx, rdi
0x180055fe3  mov     rax, [rax]
0x180055fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055feb  jmp     short loc_180056023
0x180055fed  mov     rcx, rsi; hFindFile
0x180055ff0  call    cs:__imp_FindClose
0x180055ff6  test    r14d, r14d
0x180055ff9  jnz     short loc_180056023
0x180055ffb  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x180056002  jz      short loc_18005601E
0x180056004  lea     rcx, [rsp+9B0h+var_940]
0x180056009  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18005600f  mov     r8, rax
0x180056012  lea     rdx, NATIVERD_EVENT_MISSING_IIS_SCHEMA
0x180056019  call    McTemplateU0z_EtwEventWriteTransfer
0x18005601e  mov     ebx, 80070002h
0x180056023  lea     rcx, [rsp+9B0h+var_978]
0x180056028  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005602e  lea     rcx, [rbp+8B0h+var_908]
0x180056032  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180056038  lea     rcx, [rsp+9B0h+var_940]
0x18005603d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180056043  mov     eax, ebx
0x180056045  mov     rcx, [rbp+8B0h+var_50]
0x18005604c  xor     rcx, rsp; StackCookie
0x18005604f  call    __security_check_cookie
0x180056054  add     rsp, 978h
0x18005605b  pop     r15
0x18005605d  pop     r14
0x18005605f  pop     r13
0x180056061  pop     r12
0x180056063  pop     rdi
0x180056064  pop     rsi
0x180056065  pop     rbx
0x180056066  pop     rbp
0x180056067  retn
```
