# ??$?RPEAVdatabase@sqlite3pp@@@_lambda_2_@?1??Index@Walker@DBTools@RepoMan@@SAXAEA_JPEAVSchema@4@1@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z

- ea: `0x180016164`
- end: `0x180016848`
- name: `??$?RPEAVdatabase@sqlite3pp@@@_lambda_2_@?1??Index@Walker@DBTools@RepoMan@@SAXAEA_JPEAVSchema@4@1@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z`
- size: `1764`
- prototype: `void __fastcall(__int64, struct sqlite3pp::database *)`
- caller_count: `1`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x18001609c`

## callees

- `0x180002010`
- `0x180002874`
- `0x1800028e8`
- `0x1800029c0`
- `0x180002a20`
- `0x180002aec`
- `0x180003710`
- `0x1800038ac`
- `0x180013b14`
- `0x180016164`
- `0x180024398`
- `0x1800245b4`
- `0x180024d6c`
- `0x180024de8`
- `0x180027e50`
- `0x18002854c`
- `0x180028cd8`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x180045350`
- `0x1800ddca8`
- `0x1800ddcbc`
- `0x1800ddccc`
- `0x1800ddce0`
- `0x1800ddd4c`
- `0x1800ddea0`
- `0x1800ddf04`
- `0x1800ddf18`
- `0x1800ddf7c`
- `0x1800ddff0`
- `0x1800de030`
- `0x1800dfffc`
- `0x1801094f0`
- `0x180109a80`
- `0x1801369d0`
- `0x180198f88`
- `0x18019a840`
- `0x18019a984`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180016244`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001645d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180016244`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001645d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001661f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001661f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800162c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800164cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180016618`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800162c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800164cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180016618`

## string_xrefs

- `0x180016300`: `SELECT client FROM map_Builds WHERE incoming == ?1`
- `0x1800167ef`: `Only one incoming build can be processed at a time.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall `RepoMan::DBTools::Walker::Index'::`2'::_lambda_2_::operator()<sqlite3pp::database *>(
        __int64 a1,
        struct sqlite3pp::database *a2)
{
  bool v4; // r8
  bool v5; // r9
  _QWORD *v6; // rax
  unsigned __int64 v7; // rcx
  __int64 v8; // rbx
  unsigned __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rdx
  void *v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rsi
  _QWORD *i; // rbx
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rsi
  _QWORD *v27; // rdx
  void *v28; // rcx
  __int64 v29; // rcx
  __int64 *v30; // rdx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  void *v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  const char *v37; // rax
  int v38; // eax
  unsigned int v39; // ebx
  const char *v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  const char *v43; // rax
  int v44; // edx
  int v45; // r9d
  int v46; // eax
  unsigned int v47; // ebx
  const char *v48; // rax
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+48h] [rbp-B8h]
  __int128 v51; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v52[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h]
  _BYTE v54[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v55[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v56[128]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v58; // [rsp+180h] [rbp+80h] BYREF
  __int64 v59; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int64 v60; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v61; // [rsp+198h] [rbp+98h] BYREF
  __int64 v62; // [rsp+1A0h] [rbp+A0h] BYREF
  int v63; // [rsp+1A8h] [rbp+A8h]
  void *Block[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __m128i si128; // [rsp+1C0h] [rbp+C0h]
  __int64 v66; // [rsp+1D0h] [rbp+D0h]
  int v67; // [rsp+1D8h] [rbp+D8h]
  _BYTE v68[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v69; // [rsp+208h] [rbp+108h]

  RepoMan::Tracer::Tracer(v68, 1, "client.Index");
  sqlite3pp::transaction::transaction((sqlite3pp::transaction *)v54, a2, v4, v5);
  v6 = *(_QWORD **)a1;
  *(_QWORD *)&v51 = v68;
  *((_QWORD *)&v51 + 1) = v6;
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(&v58);
  v63 = 2;
  v7 = v60;
  if ( v60 <= v62 + 1 )
  {
    std::deque<std::function<void (void)>>::_Growmap(&v58);
    v7 = v60;
  }
  v8 = (v7 - 1) & v61;
  v61 = v8;
  if ( !v8 )
    v8 = v7;
  v9 = v8 - 1;
  v10 = v9 & (v7 - 1);
  v11 = v59;
  if ( !*(_QWORD *)(v59 + 8 * v10) )
  {
    v12 = malloc(0x40u);
    if ( !v12 )
      std::_Xbad_alloc();
    *(_QWORD *)(v59 + 8 * v10) = v12;
    v7 = v60;
    v11 = v59;
  }
  v13 = *(_QWORD *)(v11 + 8 * (v9 & (v7 - 1)));
  *(_QWORD *)v13 = ___7___Func_impl_no_alloc_V_lambda_1___2_____RPEAVdatabase_sqlite3pp____lambda_2___1__Index_Walker_DBTools_RepoMan__SAXAEA_JPEAVSchema_6_1_Z_QEBA_A_PPEAVdatabase_sqlite3pp___Z_X__V_std__6B_;
  *(_OWORD *)(v13 + 8) = v51;
  *(_QWORD *)(v13 + 56) = v13;
  v61 = v9;
  if ( !++v62 )
    _invoke_watson(0, 0, 0, 0, 0);
  v14 = *(_QWORD **)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 24LL) > 0xFu )
    v14 = (_QWORD *)*v14;
  v15 = sqlite3_exec(*(_QWORD *)a2, (_DWORD)v14, 0, 0, 0);
  if ( v15 )
  {
    if ( v15 == 14 )
      v38 = sqlite3pp::database::open_error_code(a2);
    else
      v38 = sqlite3pp::database::extended_error_code(a2);
    v39 = v38 - 2063532032;
    v40 = sqlite3pp::database::error_msg(a2);
    RepoMan::RaiseException<RepoMan::Exception,long>(279, "src\\repoman\\src\\inc\\DBTools.hpp", v40, v39);
  }
  RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)&v58);
  sqlite3pp::statement::statement((sqlite3pp::statement *)v52, a2, "SELECT client FROM map_Builds WHERE incoming == ?1");
  v16 = sqlite3_bind_int64(v53, 1, **(_QWORD **)(a1 + 8));
  if ( v16 )
  {
    if ( v16 == 14 )
      v41 = sqlite3pp::database::open_error_code(a2);
    else
      v41 = sqlite3pp::database::extended_error_code(a2);
    v42 = v41 - 2063532032;
    v43 = sqlite3pp::database::error_msg(a2);
    RepoMan::RaiseException<RepoMan::Exception,long>(285, "src\\repoman\\src\\inc\\DBTools.hpp", v43, v42);
  }
  sqlite3pp::query::begin(v52, &v49);
  while ( v50 != 101 )
  {
    v17 = sqlite3_column_int64(*(_QWORD *)(v49 + 8), 0);
    *(_QWORD *)&v51 = v17;
    v18 = *(__int64 **)(a1 + 16);
    if ( *v18 && *v18 != v17 )
    {
      RepoMan::Logger::Now(&v58);
      RepoMan::Logger::GitSha1(&v59);
      RepoMan::Logger::Version(&v60);
      LODWORD(v49) = sqlite3pp::query::column_count((sqlite3pp::query *)v52);
      RepoMan::Logger::Message<char const (&)[7],int,char const (&)[18],__int64 &,char const (&)[13],__int64 &>(
        (unsigned int)&v61,
        v44,
        (unsigned int)&v49,
        v45,
        *(_QWORD *)(a1 + 16));
      v51 = *(_OWORD *)std::initializer_list<RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>>::initializer_list<RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>>(
                         Block,
                         &v58,
                         &v62);
      RepoMan::Logger::WriteEvent(8, &v51);
      `eh vector destructor iterator'(
        &v58,
        8u,
        4u,
        RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        298,
        (unsigned int)"src\\repoman\\src\\inc\\DBTools.hpp",
        (unsigned int)"Only one incoming build can be processed at a time.",
        -1941503423,
        8);
    }
    *v18 = v17;
    sqlite3pp::query::query_iterator::operator++(&v49);
  }
  std::ostringstream::ostringstream(v55);
  v19 = *(_QWORD *)(a1 + 24);
  v20 = *(_QWORD **)(v19 + 264);
  for ( i = *(_QWORD **)(v19 + 256); i != v20; i += 4 )
  {
    v22 = i;
    if ( i[3] > 0xFu )
      v22 = (_QWORD *)*i;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v55, v22, i[2]);
  }
  std::stringbuf::str(v56, &v58);
  *(_QWORD *)&v51 = v68;
  *((_QWORD *)&v51 + 1) = &v58;
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(Block);
  v67 = 2;
  v23 = si128.m128i_i64[0];
  if ( si128.m128i_i64[0] <= (unsigned __int64)(v66 + 1) )
  {
    std::deque<std::function<void (void)>>::_Growmap(Block);
    v23 = si128.m128i_i64[0];
  }
  v24 = (v23 - 1) & si128.m128i_i64[1];
  si128.m128i_i64[1] = v24;
  if ( !v24 )
    v24 = v23;
  v25 = v24 - 1;
  v26 = v25 & (v23 - 1);
  v27 = Block[1];
  if ( !*((_QWORD *)Block[1] + v26) )
  {
    v28 = malloc(0x40u);
    if ( !v28 )
      std::_Xbad_alloc();
    *((_QWORD *)Block[1] + v26) = v28;
    v23 = si128.m128i_i64[0];
    v27 = Block[1];
  }
  v29 = v27[v25 & (v23 - 1)];
  *(_QWORD *)v29 = ___7___Func_impl_no_alloc_V_lambda_2___BI______RPEAVdatabase_sqlite3pp___1_1__Index_Walker_DBTools_RepoMan__SAXAEA_JPEAVSchema_5_1_Z_QEBA_A_PPEAVdatabase_sqlite3pp___Z_X__V_std__6B_;
  *(_OWORD *)(v29 + 8) = v51;
  *(_QWORD *)(v29 + 56) = v29;
  si128.m128i_i64[1] = v25;
  if ( !++v66 )
    _invoke_watson(0, 0, 0, 0, 0);
  v30 = &v58;
  if ( v61 > 0xF )
    LODWORD(v30) = v58;
  v31 = sqlite3_exec(*(_QWORD *)a2, (_DWORD)v30, 0, 0, 0);
  if ( v31 )
  {
    if ( v31 == 14 )
      v46 = sqlite3pp::database::open_error_code(a2);
    else
      v46 = sqlite3pp::database::extended_error_code(a2);
    v47 = v46 - 2063532032;
    v48 = sqlite3pp::database::error_msg(a2);
    RepoMan::RaiseException<RepoMan::Exception,long>(318, "src\\repoman\\src\\inc\\DBTools.hpp", v48, v47);
  }
  RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)Block);
  std::string::_Tidy_deallocate(&v58);
  v32 = sqlite3pp::transaction::commit((sqlite3pp::transaction *)v54);
  if ( v32 )
  {
    if ( v32 == 14 )
      v35 = sqlite3pp::database::open_error_code(a2);
    else
      v35 = sqlite3pp::database::extended_error_code(a2);
    v36 = v35 - 2063532032;
    v37 = sqlite3pp::database::error_msg(a2);
    RepoMan::RaiseException<RepoMan::Exception,long>(320, "src\\repoman\\src\\inc\\DBTools.hpp", v37, v36);
  }
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(Block[0]) = *(_DWORD *)"bytes";
  WORD2(Block[0]) = (unsigned __int8)aBytes[4];
  RepoMan::Logger::CreateValue((unsigned int)&v49, 3, 11, (unsigned int)Block, *(_QWORD *)(*(_QWORD *)a1 + 16LL));
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 48LL))(v69, &v49);
  v33 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  }
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v34 = Block[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v34 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v34 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v34);
  }
  std::ostringstream::~ostringstream(v57);
  v57[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v57);
  sqlite3pp::statement::~statement((sqlite3pp::statement *)v52);
  sqlite3pp::transaction::~transaction((sqlite3pp::transaction *)v54);
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v68);
}

```

## disassembly

```asm
0x180016164  mov     [rsp-8+arg_10], rbx
0x180016169  mov     [rsp-8+arg_18], rsi
0x18001616e  push    rbp
0x18001616f  push    rdi
0x180016170  push    r14
0x180016172  lea     rbp, [rsp-120h]
0x18001617a  sub     rsp, 220h
0x180016181  mov     rax, cs:__security_cookie
0x180016188  xor     rax, rsp
0x18001618b  mov     [rbp+130h+var_20], rax
0x180016192  mov     rdi, rdx
0x180016195  mov     r14, rcx
0x180016198  lea     r8, aClientIndex; "client.Index"
0x18001619f  mov     edx, 1
0x1800161a4  lea     rcx, [rbp+130h+var_50]
0x1800161ab  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800161b0  nop
0x1800161b1  mov     rdx, rdi; struct sqlite3pp::database *
0x1800161b4  lea     rcx, [rsp+230h+var_1B8]; this
0x1800161b9  call    ??0transaction@sqlite3pp@@QEAA@AEAVdatabase@1@_N1@Z; sqlite3pp::transaction::transaction(sqlite3pp::database &,bool,bool)
0x1800161be  nop
0x1800161bf  mov     rax, [r14]
0x1800161c2  lea     rcx, [rbp+130h+var_50]
0x1800161c9  mov     qword ptr [rsp+230h+var_1E0], rcx
0x1800161ce  mov     qword ptr [rsp+230h+var_1E0+8], rax
0x1800161d3  lea     rcx, [rbp+130h+var_B0]
0x1800161da  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x1800161df  mov     [rbp+130h+var_88], 2
0x1800161e9  mov     rax, [rbp+130h+var_90]
0x1800161f0  inc     rax
0x1800161f3  mov     rcx, [rbp+130h+var_A0]
0x1800161fa  cmp     rcx, rax
0x1800161fd  ja      short loc_180016212
0x1800161ff  lea     rcx, [rbp+130h+var_B0]
0x180016206  call    ?_Growmap@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<void (void)>>::_Growmap(unsigned __int64)
0x18001620b  mov     rcx, [rbp+130h+var_A0]
0x180016212  lea     rsi, [rcx-1]
0x180016216  mov     rbx, [rbp+130h+var_98]
0x18001621d  and     rbx, rsi
0x180016220  mov     [rbp+130h+var_98], rbx
0x180016227  cmovz   rbx, rcx
0x18001622b  dec     rbx
0x18001622e  and     rsi, rbx
0x180016231  mov     rdx, [rbp+130h+var_A8]
0x180016238  cmp     qword ptr [rdx+rsi*8], 0
0x18001623d  jnz     short loc_18001626F
0x18001623f  mov     ecx, 40h ; '@'; Size
0x180016244  call    cs:__imp_malloc
0x18001624a  mov     rcx, rax
0x18001624d  test    rax, rax
0x180016250  jz      loc_1800166C8
0x180016256  mov     rax, [rbp+130h+var_A8]
0x18001625d  mov     [rax+rsi*8], rcx
0x180016261  mov     rcx, [rbp+130h+var_A0]
0x180016268  mov     rdx, [rbp+130h+var_A8]
0x18001626f  lea     rax, [rcx-1]
0x180016273  and     rax, rbx
0x180016276  mov     rcx, [rdx+rax*8]
0x18001627a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?2???$?RPEAVdatabase@sqlite3pp@@@_lambda_2_@?1??Index@Walker@DBTools@RepoMan@@SAXAEA_JPEAVSchema@6@1@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z@X$$V@std@@6B@
0x180016281  mov     [rcx], rax
0x180016284  movups  xmm0, [rsp+230h+var_1E0]
0x180016289  movdqu  xmmword ptr [rcx+8], xmm0
0x18001628e  mov     [rcx+38h], rcx
0x180016292  mov     [rbp+130h+var_98], rbx
0x180016299  mov     rax, [rbp+130h+var_90]
0x1800162a0  add     rax, 1
0x1800162a4  mov     [rbp+130h+var_90], rax
0x1800162ab  jnz     short loc_1800162C7
0x1800162ad  mov     [rsp+230h+Reserved], 0; Reserved
0x1800162b6  xor     r9d, r9d; LineNo
0x1800162b9  xor     r8d, r8d; FileName
0x1800162bc  xor     edx, edx; FunctionName
0x1800162be  xor     ecx, ecx; Expression
0x1800162c0  call    cs:__imp__invoke_watson
0x1800162c7  mov     rdx, [r14]
0x1800162ca  cmp     qword ptr [rdx+18h], 0Fh
0x1800162cf  jbe     short loc_1800162D4
0x1800162d1  mov     rdx, [rdx]
0x1800162d4  mov     [rsp+230h+Reserved], 0
0x1800162dd  xor     r9d, r9d
0x1800162e0  xor     r8d, r8d
0x1800162e3  mov     rcx, [rdi]
0x1800162e6  call    sqlite3_exec
0x1800162eb  nop
0x1800162ec  test    eax, eax
0x1800162ee  jnz     loc_1800166CE
0x1800162f4  lea     rcx, [rbp+130h+var_B0]; this
0x1800162fb  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x180016300  lea     r8, aSelectClientFr; "SELECT client FROM map_Builds WHERE inc"...
0x180016307  mov     rdx, rdi; struct sqlite3pp::database *
0x18001630a  lea     rcx, [rsp+230h+var_1D0]; this
0x18001630f  call    ??0statement@sqlite3pp@@IEAA@AEAVdatabase@1@PEBD@Z; sqlite3pp::statement::statement(sqlite3pp::database &,char const *)
0x180016314  nop
0x180016315  mov     rax, [r14+8]
0x180016319  mov     r8, [rax]
0x18001631c  mov     edx, 1
0x180016321  mov     rcx, [rsp+230h+var_1C8]
0x180016326  call    sqlite3_bind_int64
0x18001632b  nop
0x18001632c  test    eax, eax
0x18001632e  jnz     loc_180016708
0x180016334  lea     rdx, [rsp+230h+var_1F0]
0x180016339  lea     rcx, [rsp+230h+var_1D0]
0x18001633e  call    ?begin@query@sqlite3pp@@QEAA?AVquery_iterator@12@XZ; sqlite3pp::query::begin(void)
0x180016343  jmp     short loc_18001637B
0x180016345  mov     rax, [rsp+230h+var_1F0]
0x18001634a  xor     edx, edx
0x18001634c  mov     rcx, [rax+8]
0x180016350  call    sqlite3_column_int64
0x180016355  nop
0x180016356  mov     qword ptr [rsp+230h+var_1E0], rax
0x18001635b  mov     rcx, [r14+10h]
0x18001635f  cmp     qword ptr [rcx], 0
0x180016363  jz      short loc_18001636E
0x180016365  cmp     [rcx], rax
0x180016368  jnz     loc_180016742
0x18001636e  mov     [rcx], rax
0x180016371  lea     rcx, [rsp+230h+var_1F0]
0x180016376  call    ??Equery_iterator@query@sqlite3pp@@QEAAAEAV012@XZ; sqlite3pp::query::query_iterator::operator++(void)
0x18001637b  cmp     [rsp+230h+var_1E8], 65h ; 'e'
0x180016380  jnz     short loc_180016345
0x180016382  lea     rcx, [rbp+130h+var_1A0]
0x180016386  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18001638b  nop
0x18001638c  mov     rax, [r14+18h]
0x180016390  mov     rsi, [rax+108h]
0x180016397  mov     rbx, [rax+100h]
0x18001639e  jmp     short loc_1800163BE
0x1800163a0  mov     rdx, rbx
0x1800163a3  cmp     qword ptr [rbx+18h], 0Fh
0x1800163a8  jbe     short loc_1800163AD
0x1800163aa  mov     rdx, [rbx]
0x1800163ad  mov     r8, [rbx+10h]
0x1800163b1  lea     rcx, [rbp+130h+var_1A0]
0x1800163b5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800163ba  add     rbx, 20h ; ' '
0x1800163be  cmp     rbx, rsi
0x1800163c1  jnz     short loc_1800163A0
0x1800163c3  lea     rdx, [rbp+130h+var_B0]
0x1800163ca  lea     rcx, [rbp+130h+var_198]
0x1800163ce  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800163d3  nop
0x1800163d4  lea     rax, [rbp+130h+var_50]
0x1800163db  mov     qword ptr [rsp+230h+var_1E0], rax
0x1800163e0  lea     rax, [rbp+130h+var_B0]
0x1800163e7  mov     qword ptr [rsp+230h+var_1E0+8], rax
0x1800163ec  lea     rcx, [rbp+130h+Block]
0x1800163f3  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x1800163f8  mov     [rbp+130h+var_58], 2
0x180016402  mov     rax, [rbp+130h+var_60]
0x180016409  inc     rax
0x18001640c  mov     rcx, qword ptr [rbp+130h+var_70]
0x180016413  cmp     rcx, rax
0x180016416  ja      short loc_18001642B
0x180016418  lea     rcx, [rbp+130h+Block]
0x18001641f  call    ?_Growmap@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<void (void)>>::_Growmap(unsigned __int64)
0x180016424  mov     rcx, qword ptr [rbp+130h+var_70]
0x18001642b  lea     rsi, [rcx-1]
0x18001642f  mov     rbx, qword ptr [rbp+130h+var_70+8]
0x180016436  and     rbx, rsi
0x180016439  mov     qword ptr [rbp+130h+var_70+8], rbx
0x180016440  cmovz   rbx, rcx
0x180016444  dec     rbx
0x180016447  and     rsi, rbx
0x18001644a  mov     rdx, [rbp+130h+Block+8]
0x180016451  cmp     qword ptr [rdx+rsi*8], 0
0x180016456  jnz     short loc_180016488
0x180016458  mov     ecx, 40h ; '@'; Size
0x18001645d  call    cs:__imp_malloc
0x180016463  mov     rcx, rax
0x180016466  test    rax, rax
0x180016469  jz      loc_180016808
0x18001646f  mov     rax, [rbp+130h+Block+8]
0x180016476  mov     [rax+rsi*8], rcx
0x18001647a  mov     rcx, qword ptr [rbp+130h+var_70]
0x180016481  mov     rdx, [rbp+130h+Block+8]
0x180016488  lea     rax, [rcx-1]
0x18001648c  and     rax, rbx
0x18001648f  mov     rcx, [rdx+rax*8]
0x180016493  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2_@?BI@???$?RPEAVdatabase@sqlite3pp@@@1?1??Index@Walker@DBTools@RepoMan@@SAXAEA_JPEAVSchema@5@1@Z@QEBA?A_PPEAVdatabase@sqlite3pp@@@Z@X$$V@std@@6B@
0x18001649a  mov     [rcx], rax
0x18001649d  movups  xmm0, [rsp+230h+var_1E0]
0x1800164a2  movdqu  xmmword ptr [rcx+8], xmm0
0x1800164a7  mov     [rcx+38h], rcx
0x1800164ab  mov     qword ptr [rbp+130h+var_70+8], rbx
0x1800164b2  add     [rbp+130h+var_60], 1
0x1800164ba  jnz     short loc_1800164D6
0x1800164bc  mov     [rsp+230h+Reserved], 0; Reserved
0x1800164c5  xor     r9d, r9d; LineNo
0x1800164c8  xor     r8d, r8d; FileName
0x1800164cb  xor     edx, edx; FunctionName
0x1800164cd  xor     ecx, ecx; Expression
0x1800164cf  call    cs:__imp__invoke_watson
0x1800164d6  lea     rdx, [rbp+130h+var_B0]
0x1800164dd  cmp     [rbp+130h+var_98], 0Fh
0x1800164e5  cmova   rdx, [rbp+130h+var_B0]
0x1800164ed  mov     [rsp+230h+Reserved], 0
0x1800164f6  xor     r9d, r9d
0x1800164f9  xor     r8d, r8d
0x1800164fc  mov     rcx, [rdi]
0x1800164ff  call    sqlite3_exec
0x180016504  nop
0x180016505  test    eax, eax
0x180016507  jnz     loc_18001680E
0x18001650d  lea     rcx, [rbp+130h+Block]; this
0x180016514  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x180016519  nop
0x18001651a  lea     rcx, [rbp+130h+var_B0]
0x180016521  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016526  lea     rcx, [rsp+230h+var_1B8]; this
0x18001652b  call    ?commit@transaction@sqlite3pp@@QEAAHXZ; sqlite3pp::transaction::commit(void)
0x180016530  test    eax, eax
0x180016532  jnz     loc_18001668E
0x180016538  xorps   xmm0, xmm0
0x18001653b  movups  xmmword ptr [rbp+130h+Block], xmm0
0x180016542  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000005
0x18001654a  movdqu  [rbp+130h+var_70], xmm0
0x180016552  mov     eax, dword ptr cs:aBytes; "bytes"
0x180016558  mov     dword ptr [rbp+130h+Block], eax
0x18001655e  mov     al, byte ptr cs:aBytes+4; "s"
0x180016564  mov     byte ptr [rbp+130h+Block+4], al
0x18001656a  mov     byte ptr [rbp+130h+Block+5], 0
0x180016571  mov     rax, [r14]
0x180016574  mov     rcx, [rax+10h]
0x180016578  mov     [rsp+230h+Reserved], rcx
0x18001657d  lea     r9, [rbp+130h+Block]
0x180016584  mov     edx, 3
0x180016589  lea     r8d, [rdx+8]
0x18001658d  lea     rcx, [rsp+230h+var_1F0]
0x180016592  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x180016597  mov     rcx, [rbp+130h+var_28]
0x18001659e  mov     rax, [rcx]
0x1800165a1  lea     rdx, [rsp+230h+var_1F0]
0x1800165a6  mov     rax, [rax+30h]
0x1800165aa  call    cs:__guard_dispatch_icall_fptr
0x1800165b0  nop
0x1800165b1  mov     rcx, [rsp+230h+var_1F0]
0x1800165b6  test    rcx, rcx
0x1800165b9  jz      short loc_1800165D2
0x1800165bb  mov     [rsp+230h+var_1F0], 0
0x1800165c4  mov     rax, [rcx]
0x1800165c7  mov     rax, [rax+8]
0x1800165cb  call    cs:__guard_dispatch_icall_fptr
0x1800165d1  nop
0x1800165d2  mov     rax, qword ptr [rbp+130h+var_70+8]
0x1800165d9  cmp     rax, 0Fh
0x1800165dd  jbe     short loc_180016626
0x1800165df  mov     rcx, [rbp+130h+Block]; Block
0x1800165e6  mov     rdx, rcx
0x1800165e9  inc     rax
0x1800165ec  cmp     rax, 1000h
0x1800165f2  jb      short loc_18001661F
0x1800165f4  mov     rcx, [rcx-8]
0x1800165f8  sub     rdx, rcx
0x1800165fb  lea     rax, [rdx-8]
0x1800165ff  cmp     rax, 1Fh
0x180016603  jbe     short loc_18001661F
0x180016605  mov     [rsp+230h+Reserved], 0; Reserved
0x18001660e  xor     r9d, r9d; LineNo
0x180016611  xor     r8d, r8d; FileName
0x180016614  xor     edx, edx; FunctionName
0x180016616  xor     ecx, ecx; Expression
0x180016618  call    cs:__imp__invoke_watson
0x18001661f  call    cs:__imp_free
0x180016625  nop
0x180016626  lea     rcx, [rbp+130h+var_118]
0x18001662a  call    ??1?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::ostringstream::~ostringstream(void)
0x18001662f  nop
0x180016630  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x180016637  mov     [rbp+130h+var_118], rax
0x18001663b  lea     rcx, [rbp+130h+var_118]; this
0x18001663f  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x180016644  nop
0x180016645  lea     rcx, [rsp+230h+var_1D0]; this
0x18001664a  call    ??1statement@sqlite3pp@@IEAA@XZ; sqlite3pp::statement::~statement(void)
0x18001664f  nop
0x180016650  lea     rcx, [rsp+230h+var_1B8]; this
0x180016655  call    ??1transaction@sqlite3pp@@QEAA@XZ; sqlite3pp::transaction::~transaction(void)
0x18001665a  nop
0x18001665b  lea     rcx, [rbp+130h+var_50]; this
0x180016662  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x180016667  mov     rcx, [rbp+130h+var_20]
0x18001666e  xor     rcx, rsp; StackCookie
0x180016671  call    __security_check_cookie
0x180016676  lea     r11, [rsp+230h+var_10]
0x18001667e  mov     rbx, [r11+30h]
0x180016682  mov     rsi, [r11+38h]
0x180016686  mov     rsp, r11
0x180016689  pop     r14
0x18001668b  pop     rdi
0x18001668c  pop     rbp
0x18001668d  retn
0x18001668e  mov     rcx, rdi; this
0x180016691  cmp     eax, 0Eh
0x180016694  jnz     short loc_18001669D
0x180016696  call    ?open_error_code@database@sqlite3pp@@QEBAHXZ; sqlite3pp::database::open_error_code(void)
0x18001669b  jmp     short loc_1800166A2
0x18001669d  call    ?extended_error_code@database@sqlite3pp@@QEBAHXZ; sqlite3pp::database::extended_error_code(void)
0x1800166a2  lea     ebx, [rax-7AFF0000h]
0x1800166a8  mov     rcx, rdi; this
  ... truncated ...
```
