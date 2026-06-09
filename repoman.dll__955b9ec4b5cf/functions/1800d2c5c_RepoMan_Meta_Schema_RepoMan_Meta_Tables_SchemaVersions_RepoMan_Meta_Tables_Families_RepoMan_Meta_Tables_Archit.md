# RepoMan::Meta::Schema<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::Tables::Families,RepoMan::Meta::Tables::Architectures,RepoMan::Meta::Tables::Flavors,RepoMan::Meta::Tables::Cultures,RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::Tables::Builds,RepoMan::Meta::Tables::Media,RepoMan::Meta::Tables::SKUs,RepoMan::Meta::Tables::Apps,RepoMan::Meta::Tables::Packages,RepoMan::Meta::Tables::Digests,RepoMan::Meta::Tables::Hashes,RepoMan::Meta::Tables::Directories,RepoMan::Meta::Tables::Paths,RepoMan::Meta::Tables::Files,RepoMan::Meta::Tables::Blocks,RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::Tables::Patches,RepoMan::Meta::Tables::PackagesToPaths,RepoMan::Meta::Tables::PackagesToApps,RepoMan::Meta::Tables::AppsToSKUs,RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::Tables::Operations,RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::Tables::FileTasks>::GetQuery<RepoMan::Meta::Query<48,RepoMan::Meta::Queries::Text::PathIdByRelativeName,RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>(sqlite3pp::database *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800d2c5c`
- end: `0x1800d2f08`
- name: `??$GetQuery@V?$Query@$0DA@UPathIdByRelativeName@Text@Queries@Meta@RepoMan@@V?$InputType@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Meta@RepoMan@@@45@@Meta@RepoMan@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$Schema@VSchemaVersions@Tables@Meta@RepoMan@@VFamilies@234@VArchitectures@234@VFlavors@234@VCultures@234@VAlgorithms@234@VBuilds@234@VMedia@234@VSKUs@234@VApps@234@VPackages@234@VDigests@234@VHashes@234@VDirectories@234@VPaths@234@VFiles@234@VBlocks@234@VBlockSource@234@VPatches@234@VPackagesToPaths@234@VPackagesToApps@234@VAppsToSKUs@234@VPackageSources@234@VOperations@234@VPackageTasks@234@VFileTasks@234@@Meta@RepoMan@@QEAA?AV?$Query@$0DA@UPathIdByRelativeName@Text@Queries@Meta@RepoMan@@V?$InputType@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Meta@RepoMan@@@45@@12@PEAVdatabase@sqlite3pp@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d127c`

## callees

- `0x180008770`
- `0x180013b14`
- `0x18002854c`
- `0x180030f20`
- `0x180039088`
- `0x180039980`
- `0x1800d2c5c`
- `0x1800ddce0`
- `0x1800ddd4c`
- `0x1800dddf4`
- `0x1800dfffc`
- `0x180198860`
- `0x1801992e0`
- `0x1801992e8`
- `0x1801996ac`
- `0x18019a840`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800d2daa`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800d2daa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d2d0e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d2e06`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d2d0e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800d2e06`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d2d07`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800d2d07`

## string_xrefs

- `0x1800d2eef`: `Failed to add query to cache`
- `0x1800d2dc0`: `SELECT Paths.path_id, Directories.Name || '' || Paths.Name as relName from Directories JOIN Paths ON Paths.directory_id = Directories.directory_id where relName like ?1;`

## pseudocode

```c
__int64 __fastcall RepoMan::Meta::Schema<RepoMan::Meta::Tables::SchemaVersions,RepoMan::Meta::Tables::Families,RepoMan::Meta::Tables::Architectures,RepoMan::Meta::Tables::Flavors,RepoMan::Meta::Tables::Cultures,RepoMan::Meta::Tables::Algorithms,RepoMan::Meta::Tables::Builds,RepoMan::Meta::Tables::Media,RepoMan::Meta::Tables::SKUs,RepoMan::Meta::Tables::Apps,RepoMan::Meta::Tables::Packages,RepoMan::Meta::Tables::Digests,RepoMan::Meta::Tables::Hashes,RepoMan::Meta::Tables::Directories,RepoMan::Meta::Tables::Paths,RepoMan::Meta::Tables::Files,RepoMan::Meta::Tables::Blocks,RepoMan::Meta::Tables::BlockSource,RepoMan::Meta::Tables::Patches,RepoMan::Meta::Tables::PackagesToPaths,RepoMan::Meta::Tables::PackagesToApps,RepoMan::Meta::Tables::AppsToSKUs,RepoMan::Meta::Tables::PackageSources,RepoMan::Meta::Tables::Operations,RepoMan::Meta::Tables::PackageTasks,RepoMan::Meta::Tables::FileTasks>::GetQuery<RepoMan::Meta::Query<48,RepoMan::Meta::Queries::Text::PathIdByRelativeName,RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>>,std::string &>(
        __int64 a1,
        __int64 a2,
        struct sqlite3pp::database *a3,
        __int64 **a4)
{
  unsigned __int64 v7; // r8
  void *v8; // rcx
  struct _Mtx_internal_imp_t *v9; // rdi
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  sqlite3pp::statement *v14; // rax
  sqlite3pp::statement *v15; // rbx
  __int64 v16; // rax
  char v17; // r15
  sqlite3pp::statement *v18; // rsi
  __int64 v19; // rbx
  unsigned int v20; // eax
  char v22[8]; // [rsp+30h] [rbp-49h] BYREF
  sqlite3pp::statement *v23; // [rsp+38h] [rbp-41h] BYREF
  DWORD CurrentThreadId; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h]
  void *Block[2]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v27; // [rsp+68h] [rbp-11h]
  __int128 v28; // [rsp+78h] [rbp-1h] BYREF
  __m128i si128; // [rsp+88h] [rbp+Fh]
  int v30; // [rsp+98h] [rbp+1Fh]

  v23 = (sqlite3pp::statement *)a2;
  *(_OWORD *)Block = 0;
  v27 = 0;
  v7 = (unsigned __int64)a4[2];
  if ( (unsigned __int64)a4[3] > 0xF )
    a4 = (__int64 **)*a4;
  std::string::_Construct<2,char const *>(Block, a4, v7);
  RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>(
    &v28,
    Block);
  if ( *((_QWORD *)&v27 + 1) > 0xFu )
  {
    v8 = Block[0];
    if ( (unsigned __int64)(*((_QWORD *)&v27 + 1) + 1LL) >= 0x1000 )
    {
      v8 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v8 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v8);
  }
  v22[0] = 48;
  v9 = (struct _Mtx_internal_imp_t *)(a1 + 13200);
  v25 = a1 + 13200;
  if ( Mtx_lock((_Mtx_t)(a1 + 13200)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 13276) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 13276) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId();
  v10 = (_QWORD *)std::map<std::thread::id,std::unordered_map<unsigned char,std::unique_ptr<sqlite3pp::query>>>::operator[](
                    a1 + 13112,
                    &CurrentThreadId);
  v11 = v10[3];
  v12 = *(_QWORD *)(v11 + 16 * (v10[6] & 0xAF63AD4C86019CAFuLL) + 8);
  if ( v12 == v10[1] )
  {
LABEL_16:
    v12 = 0;
  }
  else
  {
    v13 = *(_QWORD *)(v11 + 16 * (v10[6] & 0xAF63AD4C86019CAFuLL));
    while ( *(_BYTE *)(v12 + 16) != 48 )
    {
      if ( v12 == v13 )
        goto LABEL_16;
      v12 = *(_QWORD *)(v12 + 8);
    }
  }
  if ( !v12 )
    v12 = v10[1];
  if ( v12 == v10[1] )
  {
    v14 = (sqlite3pp::statement *)malloc(0x18u);
    v15 = v14;
    if ( !v14 )
      std::_Xbad_alloc();
    sqlite3pp::statement::statement(
      v14,
      a3,
      "SELECT Paths.path_id, Directories.Name || '' || Paths.Name as relName from Directories JOIN Paths ON Paths.directo"
      "ry_id = Directories.directory_id where relName like ?1;");
    v23 = v15;
    v16 = std::_Hash<std::_Umap_traits<unsigned char,std::unique_ptr<sqlite3pp::query>,std::_Uhash_compare<unsigned char,std::hash<unsigned char>,std::equal_to<unsigned char>>,std::allocator<std::pair<unsigned char const,std::unique_ptr<sqlite3pp::query>>>,0>>::emplace<unsigned char &,std::unique_ptr<sqlite3pp::query>>(
            (__int64)v10,
            (__int64)Block,
            v22,
            (__int64 *)&v23);
    v12 = *(_QWORD *)v16;
    v17 = *(_BYTE *)(v16 + 8);
    v18 = v23;
    if ( v23 )
    {
      sqlite3pp::statement::~statement(v23);
      free(v18);
    }
    if ( !v17 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1112,
        (unsigned int)"src\\repoman\\src\\inc\\ObjectBase.hpp",
        (unsigned int)"Failed to add query to cache",
        -2147024882,
        8);
  }
  v19 = *(_QWORD *)(v12 + 24);
  Mtx_unlock(v9);
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_OWORD *)a2 = v28;
  *(__m128i *)(a2 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v28) = 0;
  *(_DWORD *)(a2 + 32) = v30;
  *(_QWORD *)(a2 + 40) = v19;
  v20 = sqlite3pp::statement::bind(v19, 1);
  if ( v20 )
    RepoMan::RaiseException<RepoMan::Exception,long>(401, "src\\repoman\\src\\inc\\ObjectBase.hpp", "bind failed.", v20);
  return a2;
}

```

## disassembly

```asm
0x1800d2c5c  mov     [rsp-8+arg_0], rbx
0x1800d2c61  push    rbp
0x1800d2c62  push    rsi
0x1800d2c63  push    rdi
0x1800d2c64  push    r14
0x1800d2c66  push    r15
0x1800d2c68  lea     rbp, [rsp-37h]
0x1800d2c6d  sub     rsp, 0B0h
0x1800d2c74  mov     rax, cs:__security_cookie
0x1800d2c7b  xor     rax, rsp
0x1800d2c7e  mov     [rbp+57h+var_30], rax
0x1800d2c82  mov     r15, r8
0x1800d2c85  mov     r14, rdx
0x1800d2c88  mov     rbx, rcx
0x1800d2c8b  mov     [rbp+57h+var_98], rdx
0x1800d2c8f  xorps   xmm0, xmm0
0x1800d2c92  movups  xmmword ptr [rbp+57h+Block], xmm0
0x1800d2c96  xorps   xmm1, xmm1
0x1800d2c99  movdqu  [rbp+57h+var_68], xmm1
0x1800d2c9e  mov     r8, [r9+10h]
0x1800d2ca2  cmp     qword ptr [r9+18h], 0Fh
0x1800d2ca7  jbe     short loc_1800D2CAC
0x1800d2ca9  mov     r9, [r9]
0x1800d2cac  mov     rdx, r9
0x1800d2caf  lea     rcx, [rbp+57h+Block]
0x1800d2cb3  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d2cb8  nop
0x1800d2cb9  lea     rdx, [rbp+57h+Block]
0x1800d2cbd  lea     rcx, [rbp+57h+var_58]
0x1800d2cc1  call    ??0?$InputType@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Meta@RepoMan@@@Meta@RepoMan@@QEAA@$$QEAU?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@12@@Z; RepoMan::Meta::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>::InputType<RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string>>(RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::NotNull>,std::string> &&)
0x1800d2cc6  nop
0x1800d2cc7  mov     rax, qword ptr [rbp+57h+var_68+8]
0x1800d2ccb  cmp     rax, 0Fh
0x1800d2ccf  jbe     short loc_1800D2D14
0x1800d2cd1  mov     rcx, [rbp+57h+Block]; Block
0x1800d2cd5  mov     rdx, rcx
0x1800d2cd8  inc     rax
0x1800d2cdb  cmp     rax, 1000h
0x1800d2ce1  jb      short loc_1800D2D0E
0x1800d2ce3  mov     rcx, [rcx-8]
0x1800d2ce7  sub     rdx, rcx
0x1800d2cea  lea     rax, [rdx-8]
0x1800d2cee  cmp     rax, 1Fh
0x1800d2cf2  jbe     short loc_1800D2D0E
0x1800d2cf4  mov     [rsp+0D0h+Reserved], 0; Reserved
0x1800d2cfd  xor     r9d, r9d; LineNo
0x1800d2d00  xor     r8d, r8d; FileName
0x1800d2d03  xor     edx, edx; FunctionName
0x1800d2d05  xor     ecx, ecx; Expression
0x1800d2d07  call    cs:__imp__invoke_watson
0x1800d2d0e  call    cs:__imp_free
0x1800d2d14  mov     [rbp+57h+var_A0], 30h ; '0'
0x1800d2d18  lea     rdi, [rbx+3390h]
0x1800d2d1f  mov     [rbp+57h+var_88], rdi
0x1800d2d23  mov     rcx, rdi; _Mtx_t
0x1800d2d26  call    _Mtx_lock
0x1800d2d2b  test    eax, eax
0x1800d2d2d  jnz     loc_1800D2EBE
0x1800d2d33  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800d2d3a  jz      loc_1800D2EC9
0x1800d2d40  call    ?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800d2d45  mov     [rbp+57h+var_90], eax
0x1800d2d48  lea     rcx, [rbx+3338h]
0x1800d2d4f  lea     rdx, [rbp+57h+var_90]
0x1800d2d53  call    ??A?$map@Vid@thread@std@@V?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@3@U?$less@Vid@thread@std@@@3@V?$allocator@U?$pair@$$CBVid@thread@std@@V?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@3@@std@@@3@@std@@QEAAAEAV?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@1@$$QEAVid@thread@1@@Z; std::map<std::thread::id,std::unordered_map<uchar,std::unique_ptr<sqlite3pp::query>>>::operator[](std::thread::id &&)
0x1800d2d58  mov     rsi, rax
0x1800d2d5b  mov     rcx, [rax+30h]
0x1800d2d5f  mov     rax, 0AF63AD4C86019CAFh
0x1800d2d69  and     rcx, rax
0x1800d2d6c  add     rcx, rcx
0x1800d2d6f  mov     rax, [rsi+18h]
0x1800d2d73  mov     rbx, [rax+rcx*8+8]
0x1800d2d78  cmp     rbx, [rsi+8]
0x1800d2d7c  jz      short loc_1800D2D95
0x1800d2d7e  mov     rax, [rax+rcx*8]
0x1800d2d82  jmp     short loc_1800D2D8D
0x1800d2d84  cmp     rbx, rax
0x1800d2d87  jz      short loc_1800D2D95
0x1800d2d89  mov     rbx, [rbx+8]
0x1800d2d8d  cmp     byte ptr [rbx+10h], 30h ; '0'
0x1800d2d91  jnz     short loc_1800D2D84
0x1800d2d93  jmp     short loc_1800D2D97
0x1800d2d95  xor     ebx, ebx
0x1800d2d97  test    rbx, rbx
0x1800d2d9a  cmovz   rbx, [rsi+8]
0x1800d2d9f  cmp     rbx, [rsi+8]
0x1800d2da3  jnz     short loc_1800D2E15
0x1800d2da5  mov     ecx, 18h; Size
0x1800d2daa  call    cs:__imp_malloc
0x1800d2db0  mov     rbx, rax
0x1800d2db3  test    rax, rax
0x1800d2db6  jz      loc_1800D2EDB
0x1800d2dbc  mov     [rbp+57h+var_98], rax
0x1800d2dc0  lea     r8, aSelectPathsPat; "SELECT Paths.path_id, Directories.Name "...
0x1800d2dc7  mov     rdx, r15; struct sqlite3pp::database *
0x1800d2dca  mov     rcx, rax; this
0x1800d2dcd  call    ??0statement@sqlite3pp@@IEAA@AEAVdatabase@1@PEBD@Z; sqlite3pp::statement::statement(sqlite3pp::database &,char const *)
0x1800d2dd2  nop
0x1800d2dd3  mov     [rbp+57h+var_98], rbx
0x1800d2dd7  lea     r9, [rbp+57h+var_98]
0x1800d2ddb  lea     r8, [rbp+57h+var_A0]
0x1800d2ddf  lea     rdx, [rbp+57h+Block]
0x1800d2de3  mov     rcx, rsi
0x1800d2de6  call    ??$emplace@AEAEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@?$_Hash@V?$_Umap_traits@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@V?$_Uhash_compare@EU?$hash@E@std@@U?$equal_to@E@2@@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAE$$QEAV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<uchar,std::unique_ptr<sqlite3pp::query>,std::_Uhash_compare<uchar,std::hash<uchar>,std::equal_to<uchar>>,std::allocator<std::pair<uchar const,std::unique_ptr<sqlite3pp::query>>>,0>>::emplace<uchar &,std::unique_ptr<sqlite3pp::query>>(uchar &,std::unique_ptr<sqlite3pp::query> &&)
0x1800d2deb  mov     rbx, [rax]
0x1800d2dee  mov     r15b, [rax+8]
0x1800d2df2  mov     rsi, [rbp+57h+var_98]
0x1800d2df6  test    rsi, rsi
0x1800d2df9  jz      short loc_1800D2E0C
0x1800d2dfb  mov     rcx, rsi; this
0x1800d2dfe  call    ??1statement@sqlite3pp@@IEAA@XZ; sqlite3pp::statement::~statement(void)
0x1800d2e03  mov     rcx, rsi; Block
0x1800d2e06  call    cs:__imp_free
0x1800d2e0c  test    r15b, r15b
0x1800d2e0f  jz      loc_1800D2EE1
0x1800d2e15  mov     rbx, [rbx+18h]
0x1800d2e19  mov     rcx, rdi; _Mtx_t
0x1800d2e1c  call    _Mtx_unlock
0x1800d2e21  mov     qword ptr [r14+10h], 0
0x1800d2e29  mov     qword ptr [r14+18h], 0
0x1800d2e31  movups  xmm0, [rbp+57h+var_58]
0x1800d2e35  movups  xmmword ptr [r14], xmm0
0x1800d2e39  movups  xmm1, [rbp+57h+var_48]
0x1800d2e3d  movups  xmmword ptr [r14+10h], xmm1
0x1800d2e42  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d2e4a  movdqu  [rbp+57h+var_48], xmm0
0x1800d2e4f  mov     byte ptr [rbp+57h+var_58], 0
0x1800d2e53  mov     eax, [rbp+57h+var_38]
0x1800d2e56  mov     [r14+20h], eax
0x1800d2e5a  mov     [r14+28h], rbx
0x1800d2e5e  mov     r8, r14
0x1800d2e61  cmp     qword ptr [r14+18h], 0Fh
0x1800d2e66  jbe     short loc_1800D2E6B
0x1800d2e68  mov     r8, [r14]
0x1800d2e6b  mov     edx, 1
0x1800d2e70  mov     rcx, rbx
0x1800d2e73  call    ?bind@statement@sqlite3pp@@QEAAHHPEBDW4copy_semantic@2@@Z; sqlite3pp::statement::bind(int,char const *,sqlite3pp::copy_semantic)
0x1800d2e78  test    eax, eax
0x1800d2e7a  jnz     short loc_1800D2EA2
0x1800d2e7c  mov     rax, r14
0x1800d2e7f  mov     rcx, [rbp+57h+var_30]
0x1800d2e83  xor     rcx, rsp; StackCookie
0x1800d2e86  call    __security_check_cookie
0x1800d2e8b  mov     rbx, [rsp+0D0h+arg_0]
0x1800d2e93  add     rsp, 0B0h
0x1800d2e9a  pop     r15
0x1800d2e9c  pop     r14
0x1800d2e9e  pop     rdi
0x1800d2e9f  pop     rsi
0x1800d2ea0  pop     rbp
0x1800d2ea1  retn
0x1800d2ea2  mov     r9d, eax
0x1800d2ea5  lea     r8, aBindFailed; "bind failed."
0x1800d2eac  lea     rdx, aSrcRepomanSrcI_18; "src\\repoman\\src\\inc\\ObjectBase.hpp"
0x1800d2eb3  mov     ecx, 191h
0x1800d2eb8  call    ??$RaiseException@VException@RepoMan@@J@RepoMan@@YAXHQEBDPEBDJW4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,long>(int,char const * const,char const *,long,RepoMan::ILogger::Verbosity)
0x1800d2ebe  mov     ecx, 5; int
0x1800d2ec3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d2ec9  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800d2ed0  mov     ecx, 6; int
0x1800d2ed5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d2edb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800d2ee1  mov     dword ptr [rsp+0D0h+Reserved], 8
0x1800d2ee9  mov     r9d, 8007000Eh
0x1800d2eef  lea     r8, aFailedToAddQue; "Failed to add query to cache"
0x1800d2ef6  lea     rdx, aSrcRepomanSrcI_18; "src\\repoman\\src\\inc\\ObjectBase.hpp"
0x1800d2efd  mov     ecx, 458h
0x1800d2f02  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
