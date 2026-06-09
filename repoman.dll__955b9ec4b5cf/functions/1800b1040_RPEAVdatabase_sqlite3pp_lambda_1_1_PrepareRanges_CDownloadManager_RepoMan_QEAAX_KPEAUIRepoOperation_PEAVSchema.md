# ??$?RPEAVdatabase@sqlite3pp@@@_lambda_1_@?1??PrepareRanges@CDownloadManager@RepoMan@@QEAAX_KPEAUIRepoOperation@@PEAVSchema@3@W4_REPOMAN_OPERATION_STATE@@W4_REPOMAN_FILE_DISPOSITIONS@@@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z

- ea: `0x1800b1040`
- end: `0x1800b14a3`
- name: `??$?RPEAVdatabase@sqlite3pp@@@_lambda_1_@?1??PrepareRanges@CDownloadManager@RepoMan@@QEAAX_KPEAUIRepoOperation@@PEAVSchema@3@W4_REPOMAN_OPERATION_STATE@@W4_REPOMAN_FILE_DISPOSITIONS@@@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z`
- size: `1123`
- prototype: `__int64 __fastcall(int **, struct sqlite3pp::database *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800b0f78`

## callees

- `0x180001ffc`
- `0x180013b14`
- `0x180030f20`
- `0x18003386c`
- `0x1800385d8`
- `0x180039980`
- `0x18003e038`
- `0x1800b1040`
- `0x1800ba7d0`
- `0x1800bb878`
- `0x1800ddce0`
- `0x1800ddd4c`
- `0x1800dddcc`
- `0x1800ddea0`
- `0x1800ddf18`
- `0x1800dfffc`
- `0x1801094f0`
- `0x180198860`
- `0x1801992e0`
- `0x1801992e8`
- `0x1801996ac`
- `0x18019f800`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1114`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1307`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1114`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1307`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1170`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1170`

## string_xrefs

- `0x1800b1463`: `Failed to add query to cache`
- `0x1800b112a`: `SELECT Files.file_id AS file_id, Files.media_id, DstHash.Offset AS dst_off, SrcHash.Offset AS src_off, SrcHash.Size AS src_size FROM Files JOIN Blocks ON Files.file_id == Blocks.file_id JOIN Hashes AS DstHash ON DstHash.hash_id == Blocks.hash_id JOIN BlockSource on BlockSource.block_id == Blocks.block_id JOIN Hashes AS SrcHash ON SrcHash.hash_id == BlockSource.hash_id WHERE Files.file_id in (SELECT file_id FROM FileTasks WHERE FileTasks.operation_id = ?1 AND FileTasks.Disposition & ?2 AND FileTa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall `RepoMan::CDownloadManager::PrepareRanges'::`2'::_lambda_1_::operator()<sqlite3pp::database *>(
        int **a1,
        struct sqlite3pp::database *a2)
{
  __int64 v4; // r13
  __int64 v5; // rbx
  __int64 v6; // r14
  struct _Mtx_internal_imp_t *v7; // rdi
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rbx
  void *v11; // rax
  void *v12; // rbx
  __int64 v13; // rax
  char v14; // r12
  void *v15; // rsi
  sqlite3pp::statement *v16; // rbx
  __int64 v17; // rdx
  sqlite3pp::statement *v18; // r14
  __int64 v19; // rbx
  __int64 v20; // r12
  __int64 v21; // r13
  __int64 v22; // rdi
  int *v23; // r8
  int *v24; // rcx
  __int64 *v25; // rdx
  __int64 *v26; // rax
  __int64 *v27; // rcx
  __int64 *v28; // rsi
  __int64 v29; // rbx
  __int64 v30; // rcx
  BOOL v31; // r8d
  __int64 inserted; // rdx
  __int64 v33; // rax
  __int64 v34; // r9
  char v35; // al
  _QWORD *v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rdi
  void *v39; // rbx
  int *v40; // rax
  __int64 v41; // rcx
  __int64 *v42; // rdx
  __int64 v44; // [rsp+30h] [rbp-79h] BYREF
  int v45; // [rsp+38h] [rbp-71h]
  __int64 v46; // [rsp+40h] [rbp-69h] BYREF
  BOOL v47; // [rsp+48h] [rbp-61h]
  int v48; // [rsp+4Ch] [rbp-5Dh]
  __int64 *v49; // [rsp+60h] [rbp-49h]
  __int64 v50; // [rsp+68h] [rbp-41h]
  _QWORD v51[2]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v52[3]; // [rsp+80h] [rbp-29h] BYREF
  int v53; // [rsp+98h] [rbp-11h]
  sqlite3pp::statement *v54; // [rsp+A0h] [rbp-9h]
  __int128 v55; // [rsp+A8h] [rbp-1h]
  __int64 v56; // [rsp+B8h] [rbp+Fh]
  char v57; // [rsp+110h] [rbp+67h] BYREF
  DWORD CurrentThreadId; // [rsp+118h] [rbp+6Fh] BYREF
  void *Block; // [rsp+120h] [rbp+77h] BYREF
  __int64 v60; // [rsp+128h] [rbp+7Fh]

  v4 = **a1;
  v60 = *a1[1];
  v5 = *(_QWORD *)a1[2];
  v6 = *(_QWORD *)a1[3];
  v57 = 61;
  v7 = (struct _Mtx_internal_imp_t *)(v5 + 13200);
  v49 = (__int64 *)(v5 + 13200);
  if ( Mtx_lock((_Mtx_t)(v5 + 13200)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v5 + 13276) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v5 + 13276) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId();
  v8 = (_QWORD *)std::map<std::thread::id,std::unordered_map<unsigned char,std::unique_ptr<sqlite3pp::query>>>::operator[](
                   v5 + 13112,
                   &CurrentThreadId);
  v9 = v8[3];
  v10 = *(_QWORD *)(v9 + 16 * (v8[6] & 0xAF63B04C8601A1C8uLL) + 8);
  if ( v10 == v8[1] )
  {
LABEL_9:
    v10 = 0;
  }
  else
  {
    while ( *(_BYTE *)(v10 + 16) != 61 )
    {
      if ( v10 == *(_QWORD *)(v9 + 16 * (v8[6] & 0xAF63B04C8601A1C8uLL)) )
        goto LABEL_9;
      v10 = *(_QWORD *)(v10 + 8);
    }
  }
  if ( !v10 )
    v10 = v8[1];
  if ( v10 == v8[1] )
  {
    v11 = malloc(0x18u);
    v12 = v11;
    if ( !v11 )
      std::_Xbad_alloc();
    Block = v11;
    sqlite3pp::statement::statement(
      (sqlite3pp::statement *)v11,
      a2,
      "SELECT Files.file_id AS file_id, Files.media_id, DstHash.Offset AS dst_off, SrcHash.Offset AS src_off, SrcHash.Siz"
      "e AS src_size FROM Files JOIN Blocks ON Files.file_id == Blocks.file_id JOIN Hashes AS DstHash ON DstHash.hash_id "
      "== Blocks.hash_id JOIN BlockSource on BlockSource.block_id == Blocks.block_id JOIN Hashes AS SrcHash ON SrcHash.ha"
      "sh_id == BlockSource.hash_id WHERE Files.file_id in (SELECT file_id FROM FileTasks WHERE FileTasks.operation_id = "
      "?1 AND FileTasks.Disposition & ?2 AND FileTasks.State & ?3 AND FileTasks.HardLinkFlags & 3) ORDER BY file_id, dst_off;");
    Block = v12;
    v13 = std::_Hash<std::_Umap_traits<unsigned char,std::unique_ptr<sqlite3pp::query>,std::_Uhash_compare<unsigned char,std::hash<unsigned char>,std::equal_to<unsigned char>>,std::allocator<std::pair<unsigned char const,std::unique_ptr<sqlite3pp::query>>>,0>>::emplace<unsigned char &,std::unique_ptr<sqlite3pp::query>>(
            v8,
            &v46,
            &v57,
            &Block);
    v10 = *(_QWORD *)v13;
    v14 = *(_BYTE *)(v13 + 8);
    v15 = Block;
    if ( Block )
    {
      sqlite3pp::statement::~statement((sqlite3pp::statement *)Block);
      free(v15);
    }
    if ( !v14 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1112,
        (unsigned int)"src\\repoman\\src\\inc\\ObjectBase.hpp",
        (unsigned int)"Failed to add query to cache",
        -2147024882,
        8);
  }
  v16 = *(sqlite3pp::statement **)(v10 + 24);
  Mtx_unlock(v7);
  v52[0] = v60;
  v52[1] = v4;
  v52[2] = v6;
  v53 = 0;
  v54 = v16;
  RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Ignored,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>>::Bind<sqlite3pp::query>(
    v52,
    v17,
    v16);
  v18 = v54;
  sqlite3pp::query::begin(v54, &v44);
  while ( v45 != 101 )
  {
    v19 = *(_QWORD *)(v44 + 8);
    v20 = sqlite3_column_int64(v19, 4);
    v21 = sqlite3_column_int64(v19, 3);
    sqlite3_column_int64(v19, 2);
    v22 = sqlite3_column_int64(v19, 1);
    sqlite3_column_int64(v19, 0);
    v23 = a1[4];
    v24 = a1[5];
    v25 = *(__int64 **)v24;
    if ( *(_QWORD *)v23 == *(_QWORD *)v24 || *(_QWORD *)(*(_QWORD *)v23 + 32LL) != v22 )
    {
      v26 = (__int64 *)v25[1];
      v27 = *(__int64 **)v24;
      while ( !*((_BYTE *)v26 + 25) )
      {
        if ( v26[4] >= v22 )
          v27 = v26;
        else
          v26 += 2;
        v26 = (__int64 *)*v26;
      }
      if ( *((_BYTE *)v27 + 25) || v22 < v27[4] )
        v27 = v25;
      *(_QWORD *)v23 = v27;
      v28 = (__int64 *)a1[5];
      v29 = *v28;
      if ( *(_QWORD *)a1[4] == *v28 )
      {
        v55 = 0;
        v56 = 0;
        v30 = *(_QWORD *)(v29 + 8);
        v31 = 0;
        inserted = v29;
        if ( !*(_BYTE *)(v30 + 25) )
        {
          v33 = *(_QWORD *)(v29 + 8);
          do
          {
            v30 = v33;
            v34 = *(_QWORD *)(v33 + 32);
            if ( v34 >= v22 )
              inserted = v33;
            else
              v33 += 16;
            v31 = v34 >= v22;
            v33 = *(_QWORD *)v33;
          }
          while ( !*(_BYTE *)(v33 + 25) );
        }
        v46 = v30;
        v47 = v31;
        v48 = HIDWORD(v55);
        if ( *(_BYTE *)(inserted + 25) || v22 < *(_QWORD *)(inserted + 32) )
        {
          if ( v28[1] == 0x3FFFFFFFFFFFFFFLL )
            std::_Throw_tree_length_error();
          v49 = v28;
          v50 = 0;
          v36 = malloc(0x40u);
          if ( !v36 )
            std::_Xbad_alloc();
          v36[4] = v22;
          v36[5] = 0;
          v36[6] = 0;
          v36[7] = 0;
          *v36 = v29;
          v36[1] = v29;
          v36[2] = v29;
          *((_WORD *)v36 + 12) = 0;
          v50 = 0;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(
                       v28,
                       &v46,
                       v36);
          v35 = 1;
        }
        else
        {
          v35 = 0;
        }
        *(_QWORD *)a1[4] = inserted;
        if ( !v35 )
          RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
            1250,
            (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
            (unsigned int)"failed to reserve sufficient memory to prepare ranges.",
            -2147024882,
            8);
        v37 = *(_QWORD *)a1[4];
        if ( (unsigned __int64)((__int64)(*(_QWORD *)(v37 + 56) - *(_QWORD *)(v37 + 40)) >> 4) < 0x2710 )
        {
          v38 = (__int64)(*(_QWORD *)(v37 + 48) - *(_QWORD *)(v37 + 40)) >> 4;
          v39 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(160000);
          memmove(v39, *(const void **)(v37 + 40), *(_QWORD *)(v37 + 48) - *(_QWORD *)(v37 + 40));
          std::vector<_REPO_RANGE>::_Change_array(v37 + 40, v39, v38, 10000);
        }
      }
    }
    v51[0] = v21;
    v51[1] = v20;
    v40 = a1[4];
    v41 = *(_QWORD *)v40 + 40LL;
    v42 = *(__int64 **)(*(_QWORD *)v40 + 48LL);
    if ( v42 == *(__int64 **)(*(_QWORD *)v40 + 56LL) )
    {
      std::vector<_REPO_RANGE>::_Emplace_reallocate<_REPO_RANGE const &>(v41, v42, v51);
    }
    else
    {
      *v42 = v21;
      v42[1] = v20;
      *(_QWORD *)(v41 + 8) += 16LL;
    }
    sqlite3pp::query::query_iterator::operator++(&v44);
  }
  return sqlite3pp::statement::reset_and_clear_bindings(v18);
}

```

## disassembly

```asm
0x1800b1040  push    rbp
0x1800b1042  push    rbx
0x1800b1043  push    rsi
0x1800b1044  push    rdi
0x1800b1045  push    r12
0x1800b1047  push    r13
0x1800b1049  push    r14
0x1800b104b  push    r15
0x1800b104d  lea     rbp, [rsp-1Fh]
0x1800b1052  sub     rsp, 0C8h
0x1800b1059  mov     r12, rdx
0x1800b105c  mov     r15, rcx
0x1800b105f  mov     rax, [rcx]
0x1800b1062  movsxd  r13, dword ptr [rax]
0x1800b1065  mov     rax, [rcx+8]
0x1800b1069  movsxd  rax, dword ptr [rax]
0x1800b106c  mov     [rbp+57h+arg_18], rax
0x1800b1070  mov     rax, [rcx+10h]
0x1800b1074  mov     rbx, [rax]
0x1800b1077  mov     r14, [rcx+18h]
0x1800b107b  mov     r14, [r14]
0x1800b107e  mov     [rbp+57h+arg_0], 3Dh ; '='
0x1800b1082  lea     rdi, [rbx+3390h]
0x1800b1089  mov     [rbp+57h+var_A0], rdi
0x1800b108d  mov     rcx, rdi; _Mtx_t
0x1800b1090  call    _Mtx_lock
0x1800b1095  test    eax, eax
0x1800b1097  jnz     loc_1800B1432
0x1800b109d  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800b10a4  jz      loc_1800B143D
0x1800b10aa  call    ?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800b10af  mov     [rbp+57h+arg_8], eax
0x1800b10b2  lea     rcx, [rbx+3338h]
0x1800b10b9  lea     rdx, [rbp+57h+arg_8]
0x1800b10bd  call    ??A?$map@Vid@thread@std@@V?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@3@U?$less@Vid@thread@std@@@3@V?$allocator@U?$pair@$$CBVid@thread@std@@V?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@3@@std@@@3@@std@@QEAAAEAV?$unordered_map@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@U?$hash@E@2@U?$equal_to@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@@1@$$QEAVid@thread@1@@Z; std::map<std::thread::id,std::unordered_map<uchar,std::unique_ptr<sqlite3pp::query>>>::operator[](std::thread::id &&)
0x1800b10c2  mov     rsi, rax
0x1800b10c5  mov     rcx, [rax+30h]
0x1800b10c9  mov     rax, 0AF63B04C8601A1C8h
0x1800b10d3  and     rcx, rax
0x1800b10d6  add     rcx, rcx
0x1800b10d9  mov     rax, [rsi+18h]
0x1800b10dd  mov     rbx, [rax+rcx*8+8]
0x1800b10e2  cmp     rbx, [rsi+8]
0x1800b10e6  jz      short loc_1800B10FF
0x1800b10e8  mov     rdx, [rax+rcx*8]
0x1800b10ec  jmp     short loc_1800B10F7
0x1800b10ee  cmp     rbx, rdx
0x1800b10f1  jz      short loc_1800B10FF
0x1800b10f3  mov     rbx, [rbx+8]
0x1800b10f7  cmp     byte ptr [rbx+10h], 3Dh ; '='
0x1800b10fb  jnz     short loc_1800B10EE
0x1800b10fd  jmp     short loc_1800B1101
0x1800b10ff  xor     ebx, ebx
0x1800b1101  test    rbx, rbx
0x1800b1104  cmovz   rbx, [rsi+8]
0x1800b1109  cmp     rbx, [rsi+8]
0x1800b110d  jnz     short loc_1800B117F
0x1800b110f  mov     ecx, 18h; Size
0x1800b1114  call    cs:__imp_malloc
0x1800b111a  mov     rbx, rax
0x1800b111d  test    rax, rax
0x1800b1120  jz      loc_1800B144F
0x1800b1126  mov     [rbp+57h+Block], rax
0x1800b112a  lea     r8, aSelectFilesFil; "SELECT Files.file_id AS file_id, Files."...
0x1800b1131  mov     rdx, r12; struct sqlite3pp::database *
0x1800b1134  mov     rcx, rax; this
0x1800b1137  call    ??0statement@sqlite3pp@@IEAA@AEAVdatabase@1@PEBD@Z; sqlite3pp::statement::statement(sqlite3pp::database &,char const *)
0x1800b113c  nop
0x1800b113d  mov     [rbp+57h+Block], rbx
0x1800b1141  lea     r9, [rbp+57h+Block]
0x1800b1145  lea     r8, [rbp+57h+arg_0]
0x1800b1149  lea     rdx, [rbp+57h+var_C0]
0x1800b114d  mov     rcx, rsi
0x1800b1150  call    ??$emplace@AEAEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@?$_Hash@V?$_Umap_traits@EV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@V?$_Uhash_compare@EU?$hash@E@std@@U?$equal_to@E@2@@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBEV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAE$$QEAV?$unique_ptr@Vquery@sqlite3pp@@U?$default_delete@Vquery@sqlite3pp@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<uchar,std::unique_ptr<sqlite3pp::query>,std::_Uhash_compare<uchar,std::hash<uchar>,std::equal_to<uchar>>,std::allocator<std::pair<uchar const,std::unique_ptr<sqlite3pp::query>>>,0>>::emplace<uchar &,std::unique_ptr<sqlite3pp::query>>(uchar &,std::unique_ptr<sqlite3pp::query> &&)
0x1800b1155  mov     rbx, [rax]
0x1800b1158  mov     r12b, [rax+8]
0x1800b115c  mov     rsi, [rbp+57h+Block]
0x1800b1160  test    rsi, rsi
0x1800b1163  jz      short loc_1800B1176
0x1800b1165  mov     rcx, rsi; this
0x1800b1168  call    ??1statement@sqlite3pp@@IEAA@XZ; sqlite3pp::statement::~statement(void)
0x1800b116d  mov     rcx, rsi; Block
0x1800b1170  call    cs:__imp_free
0x1800b1176  test    r12b, r12b
0x1800b1179  jz      loc_1800B1455
0x1800b117f  mov     rbx, [rbx+18h]
0x1800b1183  mov     rcx, rdi; _Mtx_t
0x1800b1186  call    _Mtx_unlock
0x1800b118b  mov     rax, [rbp+57h+arg_18]
0x1800b118f  mov     [rbp+57h+var_80], rax
0x1800b1193  mov     [rbp+57h+var_78], r13
0x1800b1197  mov     [rbp+57h+var_70], r14
0x1800b119b  mov     [rbp+57h+var_68], 0
0x1800b11a2  mov     [rbp+57h+var_60], rbx
0x1800b11a6  mov     r8, rbx
0x1800b11a9  lea     rcx, [rbp+57h+var_80]
0x1800b11ad  call    ??$Bind@Vquery@sqlite3pp@@@?$RowType@U?$Column@UIgnored@Meta@RepoMan@@H@Meta@RepoMan@@U?$Column@U?$Value@UNumber@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@_J@23@U423@U423@@Meta@RepoMan@@QEAAXW4BindFlags@12@AEAVquery@sqlite3pp@@@Z; RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Ignored,int>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Number,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull>,__int64>>::Bind<sqlite3pp::query>(RepoMan::Meta::BindFlags,sqlite3pp::query &)
0x1800b11b2  nop
0x1800b11b3  lea     rdx, [rbp+57h+var_D0]
0x1800b11b7  mov     r14, [rbp+57h+var_60]
0x1800b11bb  mov     rcx, r14
0x1800b11be  call    ?begin@query@sqlite3pp@@QEAA?AVquery_iterator@12@XZ; sqlite3pp::query::begin(void)
0x1800b11c3  jmp     loc_1800B1401
0x1800b11c8  mov     rax, [rbp+57h+var_D0]
0x1800b11cc  mov     rbx, [rax+8]
0x1800b11d0  mov     edx, 4
0x1800b11d5  mov     rcx, rbx
0x1800b11d8  call    sqlite3_column_int64
0x1800b11dd  mov     r12, rax
0x1800b11e0  mov     edx, 3
0x1800b11e5  mov     rcx, rbx
0x1800b11e8  call    sqlite3_column_int64
0x1800b11ed  mov     r13, rax
0x1800b11f0  mov     edx, 2
0x1800b11f5  mov     rcx, rbx
0x1800b11f8  call    sqlite3_column_int64
0x1800b11fd  nop
0x1800b11fe  mov     edx, 1
0x1800b1203  mov     rcx, rbx
0x1800b1206  call    sqlite3_column_int64
0x1800b120b  mov     rdi, rax
0x1800b120e  xor     edx, edx
0x1800b1210  mov     rcx, rbx
0x1800b1213  call    sqlite3_column_int64
0x1800b1218  nop
0x1800b1219  mov     r8, [r15+20h]
0x1800b121d  mov     rcx, [r15+28h]
0x1800b1221  mov     rdx, [rcx]
0x1800b1224  mov     rax, [r8]
0x1800b1227  cmp     rax, rdx
0x1800b122a  jz      short loc_1800B1236
0x1800b122c  cmp     [rax+20h], rdi
0x1800b1230  jz      loc_1800B13C4
0x1800b1236  mov     rax, [rdx+8]
0x1800b123a  mov     rcx, rdx
0x1800b123d  xor     r10d, r10d
0x1800b1240  jmp     short loc_1800B1254
0x1800b1242  cmp     [rax+20h], rdi
0x1800b1246  jge     short loc_1800B124E
0x1800b1248  add     rax, 10h
0x1800b124c  jmp     short loc_1800B1251
0x1800b124e  mov     rcx, rax
0x1800b1251  mov     rax, [rax]
0x1800b1254  cmp     [rax+19h], r10b
0x1800b1258  jz      short loc_1800B1242
0x1800b125a  cmp     [rcx+19h], r10b
0x1800b125e  jnz     short loc_1800B1266
0x1800b1260  cmp     rdi, [rcx+20h]
0x1800b1264  jge     short loc_1800B1269
0x1800b1266  mov     rcx, rdx
0x1800b1269  mov     [r8], rcx
0x1800b126c  mov     rax, [r15+20h]
0x1800b1270  mov     rsi, [r15+28h]
0x1800b1274  mov     rbx, [rsi]
0x1800b1277  cmp     [rax], rbx
0x1800b127a  jnz     loc_1800B13C4
0x1800b1280  xorps   xmm0, xmm0
0x1800b1283  movdqu  [rbp+57h+var_58], xmm0
0x1800b1288  mov     [rbp+57h+var_48], r10
0x1800b128c  mov     rcx, [rbx+8]
0x1800b1290  mov     r8d, r10d
0x1800b1293  mov     rdx, rbx
0x1800b1296  cmp     [rcx+19h], r10b
0x1800b129a  jnz     short loc_1800B12C7
0x1800b129c  mov     rax, rcx
0x1800b129f  mov     rcx, rax
0x1800b12a2  mov     r9, [rax+20h]
0x1800b12a6  cmp     r9, rdi
0x1800b12a9  jge     short loc_1800B12B1
0x1800b12ab  add     rax, 10h
0x1800b12af  jmp     short loc_1800B12B4
0x1800b12b1  mov     rdx, rax
0x1800b12b4  mov     r8d, r10d
0x1800b12b7  cmp     r9, rdi
0x1800b12ba  setnl   r8b
0x1800b12be  mov     rax, [rax]
0x1800b12c1  cmp     [rax+19h], r10b
0x1800b12c5  jz      short loc_1800B129F
0x1800b12c7  mov     qword ptr [rbp+57h+var_C0], rcx
0x1800b12cb  mov     dword ptr [rbp+57h+var_C0+8], r8d
0x1800b12cf  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x1800b12d2  mov     dword ptr [rbp+57h+var_C0+0Ch], eax
0x1800b12d5  cmp     [rdx+19h], r10b
0x1800b12d9  jnz     short loc_1800B12E6
0x1800b12db  cmp     rdi, [rdx+20h]
0x1800b12df  jl      short loc_1800B12E6
0x1800b12e1  mov     al, r10b
0x1800b12e4  jmp     short loc_1800B1358
0x1800b12e6  mov     rax, 3FFFFFFFFFFFFFFh
0x1800b12f0  cmp     [rsi+8], rax
0x1800b12f4  jz      loc_1800B142C
0x1800b12fa  mov     [rbp+57h+var_A0], rsi
0x1800b12fe  mov     [rbp+57h+var_98], r10
0x1800b1302  mov     ecx, 40h ; '@'; Size
0x1800b1307  call    cs:__imp_malloc
0x1800b130d  xor     ecx, ecx
0x1800b130f  test    rax, rax
0x1800b1312  jz      loc_1800B1426
0x1800b1318  mov     [rax+20h], rdi
0x1800b131c  mov     [rax+28h], rcx
0x1800b1320  mov     [rax+30h], rcx
0x1800b1324  mov     [rax+38h], rcx
0x1800b1328  mov     [rax], rbx
0x1800b132b  mov     [rax+8], rbx
0x1800b132f  mov     [rax+10h], rbx
0x1800b1333  mov     [rax+18h], cx
0x1800b1337  mov     [rbp+57h+var_98], rcx
0x1800b133b  movups  xmm0, [rbp+57h+var_C0]
0x1800b133f  movdqu  [rbp+57h+var_C0], xmm0
0x1800b1344  mov     r8, rax
0x1800b1347  lea     rdx, [rbp+57h+var_C0]
0x1800b134b  mov     rcx, rsi
0x1800b134e  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *> *>,std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *> * const)
0x1800b1353  mov     rdx, rax
0x1800b1356  mov     al, 1
0x1800b1358  mov     rcx, [r15+20h]
0x1800b135c  mov     [rcx], rdx
0x1800b135f  test    al, al
0x1800b1361  jz      loc_1800B147C
0x1800b1367  mov     rax, [r15+20h]
0x1800b136b  mov     rsi, [rax]
0x1800b136e  mov     rax, [rsi+38h]
0x1800b1372  sub     rax, [rsi+28h]
0x1800b1376  sar     rax, 4
0x1800b137a  cmp     rax, 2710h
0x1800b1380  jnb     short loc_1800B13C4
0x1800b1382  mov     rdi, [rsi+30h]
0x1800b1386  sub     rdi, [rsi+28h]
0x1800b138a  sar     rdi, 4
0x1800b138e  mov     ecx, 27100h
0x1800b1393  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1800b1398  mov     rbx, rax
0x1800b139b  mov     r8, [rsi+30h]
0x1800b139f  sub     r8, [rsi+28h]; Size
0x1800b13a3  mov     rdx, [rsi+28h]; Src
0x1800b13a7  mov     rcx, rax; void *
0x1800b13aa  call    memmove
0x1800b13af  mov     r9d, 2710h
0x1800b13b5  mov     r8, rdi
0x1800b13b8  mov     rdx, rbx
0x1800b13bb  lea     rcx, [rsi+28h]
0x1800b13bf  call    ?_Change_array@?$vector@U_REPO_RANGE@@V?$allocator@U_REPO_RANGE@@@std@@@std@@AEAAXQEAU_REPO_RANGE@@_K1@Z; std::vector<_REPO_RANGE>::_Change_array(_REPO_RANGE * const,unsigned __int64,unsigned __int64)
0x1800b13c4  mov     [rbp+57h+var_90], r13
0x1800b13c8  mov     [rbp+57h+var_88], r12
0x1800b13cc  mov     rax, [r15+20h]
0x1800b13d0  mov     rcx, [rax]
0x1800b13d3  add     rcx, 28h ; '('
0x1800b13d7  mov     rdx, [rcx+8]
0x1800b13db  cmp     rdx, [rcx+10h]
0x1800b13df  jz      short loc_1800B13EF
0x1800b13e1  mov     [rdx], r13
0x1800b13e4  mov     [rdx+8], r12
0x1800b13e8  add     qword ptr [rcx+8], 10h
0x1800b13ed  jmp     short loc_1800B13F8
0x1800b13ef  lea     r8, [rbp+57h+var_90]
0x1800b13f3  call    ??$_Emplace_reallocate@AEBU_REPO_RANGE@@@?$vector@U_REPO_RANGE@@V?$allocator@U_REPO_RANGE@@@std@@@std@@AEAAPEAU_REPO_RANGE@@QEAU2@AEBU2@@Z; std::vector<_REPO_RANGE>::_Emplace_reallocate<_REPO_RANGE const &>(_REPO_RANGE * const,_REPO_RANGE const &)
0x1800b13f8  lea     rcx, [rbp+57h+var_D0]
0x1800b13fc  call    ??Equery_iterator@query@sqlite3pp@@QEAAAEAV012@XZ; sqlite3pp::query::query_iterator::operator++(void)
0x1800b1401  cmp     [rbp+57h+var_C8], 65h ; 'e'
0x1800b1405  jnz     loc_1800B11C8
0x1800b140b  mov     rcx, r14; this
0x1800b140e  add     rsp, 0C8h
0x1800b1415  pop     r15
0x1800b1417  pop     r14
0x1800b1419  pop     r13
0x1800b141b  pop     r12
0x1800b141d  pop     rdi
0x1800b141e  pop     rsi
0x1800b141f  pop     rbx
0x1800b1420  pop     rbp
0x1800b1421  jmp     ?reset_and_clear_bindings@statement@sqlite3pp@@QEAAHXZ; sqlite3pp::statement::reset_and_clear_bindings(void)
0x1800b1426  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800b142c  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x1800b1432  mov     ecx, 5; int
0x1800b1437  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800b143d  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800b1444  mov     ecx, 6; int
0x1800b1449  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800b144f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800b1455  mov     [rsp+100h+var_E0], 8
0x1800b145d  mov     r9d, 8007000Eh
0x1800b1463  lea     r8, aFailedToAddQue; "Failed to add query to cache"
0x1800b146a  lea     rdx, aSrcRepomanSrcI_18; "src\\repoman\\src\\inc\\ObjectBase.hpp"
0x1800b1471  mov     ecx, 458h
0x1800b1476  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800b147c  mov     [rsp+100h+var_E0], 8
0x1800b1484  mov     r9d, 8007000Eh
0x1800b148a  lea     r8, aFailedToReserv_0; "failed to reserve sufficient memory to "...
0x1800b1491  lea     rdx, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800b1498  mov     ecx, 4E2h
0x1800b149d  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
