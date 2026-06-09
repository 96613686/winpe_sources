# RepoMan::Meta::Key<RepoMan::Meta::Text::Source_Path,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::A>::BuildMappedJoin(std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>> &,unsigned __int64,CommandFlags,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180074a18`
- end: `0x180074c29`
- name: `?BuildMappedJoin@?$Key@USource_Path@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UA@Alias@34@@Meta@RepoMan@@SA_NAEAV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KW4CommandFlags@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@3@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006bce8`

## callees

- `0x1800136dc`
- `0x180027e50`
- `0x18002f9b0`
- `0x18003ff74`
- `0x180074a18`
- `0x18019a840`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074b20`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074c02`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074b20`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074c02`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180074b19`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180074bfb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180074b19`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180074bfb`

## string_xrefs

- `0x180074ba0`: `source_path`
- `0x180074b69`: `.incoming = `

## pseudocode

```c
char __fastcall RepoMan::Meta::Key<RepoMan::Meta::Text::Source_Path,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::A>::BuildMappedJoin(
        __int64 a1,
        __int64 a2,
        char a3,
        _QWORD *a4)
{
  __int64 v5; // rdi
  __int64 v6; // rsi
  _QWORD *v7; // rax
  unsigned __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  void *v19; // rcx
  void *Block[2]; // [rsp+38h] [rbp-48h] BYREF
  __m128i si128; // [rsp+48h] [rbp-38h]
  _OWORD v23[2]; // [rsp+58h] [rbp-28h] BYREF

  if ( a3 >= 0 )
  {
    v5 = a1 + 16;
    v6 = std::operator<<<std::char_traits<char>>(a1 + 16, (__int64)" JOIN ");
    v7 = (_QWORD *)RepoMan::Meta::Key<RepoMan::Meta::Text::Source_Path,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::A>::MapTable(v23);
    v8 = v7[2];
    if ( v7[3] > 0xFu )
      v7 = (_QWORD *)*v7;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v6, (__int64)v7, v8);
    std::string::_Tidy_deallocate(v23);
    v9 = std::operator<<<std::char_traits<char>>(v5, (__int64)" AS ");
    v23[0] = 0;
    LOWORD(v23[0]) = 65;
    *(_OWORD *)Block = v23[0];
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v10 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v9, (__int64)Block, 1u);
    std::operator<<<std::char_traits<char>>(v10, (__int64)" ");
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v11 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v11 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v11);
    }
    v12 = std::operator<<<std::char_traits<char>>(v5, (__int64)" ON ");
    v23[0] = 0;
    LOWORD(v23[0]) = 65;
    *(_OWORD *)Block = v23[0];
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v13 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, (__int64)Block, 1u);
    v14 = std::operator<<<std::char_traits<char>>(v13, (__int64)".incoming = ");
    v15 = a4[2];
    if ( a4[3] > 0xFu )
      a4 = (_QWORD *)*a4;
    v16 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v14, (__int64)a4, v15);
    v17 = std::operator<<<std::char_traits<char>>(v16, (__int64)".");
    v18 = std::operator<<<std::char_traits<char>>(v17, (__int64)"source_path");
    std::operator<<<std::char_traits<char>>(v18, (__int64)" ");
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v19 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v19 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v19 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v19);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180074a18  mov     [rsp-18h+arg_8], rbx
0x180074a1d  push    rbp
0x180074a1e  push    rsi
0x180074a1f  push    rdi
0x180074a20  mov     rbp, rsp
0x180074a23  sub     rsp, 80h
0x180074a2a  mov     rax, cs:__security_cookie
0x180074a31  xor     rax, rsp
0x180074a34  mov     [rbp+var_8], rax
0x180074a38  mov     rbx, r9
0x180074a3b  test    r8b, r8b
0x180074a3e  js      loc_180074C08
0x180074a44  lea     rdi, [rcx+10h]
0x180074a48  lea     rdx, aJoin; " JOIN "
0x180074a4f  mov     rcx, rdi
0x180074a52  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074a57  mov     rsi, rax
0x180074a5a  lea     rcx, [rbp+var_28]
0x180074a5e  call    ?MapTable@?$Key@USource_Path@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UPaths@234@UA@Alias@34@@Meta@RepoMan@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Meta::Key<RepoMan::Meta::Text::Source_Path,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Paths,RepoMan::Meta::Alias::A>::MapTable(void)
0x180074a63  mov     r8, [rax+10h]
0x180074a67  cmp     qword ptr [rax+18h], 0Fh
0x180074a6c  jbe     short loc_180074A71
0x180074a6e  mov     rax, [rax]
0x180074a71  mov     rdx, rax
0x180074a74  mov     rcx, rsi
0x180074a77  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180074a7c  lea     rcx, [rbp+var_28]
0x180074a80  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180074a85  lea     rdx, aAs; " AS "
0x180074a8c  mov     rcx, rdi
0x180074a8f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074a94  nop
0x180074a95  xorps   xmm0, xmm0
0x180074a98  movups  [rbp+var_28], xmm0
0x180074a9c  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000001
0x180074aa4  mov     word ptr [rbp+var_28], 41h ; 'A'
0x180074aaa  movups  xmm0, [rbp+var_28]
0x180074aae  movups  xmmword ptr [rbp+Block], xmm0
0x180074ab2  movups  [rbp+var_38], xmm1
0x180074ab6  lea     rdx, [rbp+Block]
0x180074aba  mov     r8d, 1
0x180074ac0  mov     rcx, rax
0x180074ac3  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180074ac8  lea     rdx, asc_1801D0D08; " "
0x180074acf  mov     rcx, rax
0x180074ad2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074ad7  mov     esi, 1000h
0x180074adc  mov     rax, qword ptr [rbp+var_38+8]
0x180074ae0  cmp     rax, 0Fh
0x180074ae4  jbe     short loc_180074B26
0x180074ae6  mov     rcx, [rbp+Block]; Block
0x180074aea  mov     rdx, rcx
0x180074aed  inc     rax
0x180074af0  cmp     rax, rsi
0x180074af3  jb      short loc_180074B20
0x180074af5  mov     rcx, [rcx-8]
0x180074af9  sub     rdx, rcx
0x180074afc  lea     rax, [rdx-8]
0x180074b00  cmp     rax, 1Fh
0x180074b04  jbe     short loc_180074B20
0x180074b06  mov     [rsp+80h+Reserved], 0; Reserved
0x180074b0f  xor     r9d, r9d; LineNo
0x180074b12  xor     r8d, r8d; FileName
0x180074b15  xor     edx, edx; FunctionName
0x180074b17  xor     ecx, ecx; Expression
0x180074b19  call    cs:__imp__invoke_watson
0x180074b20  call    cs:__imp_free
0x180074b26  lea     rdx, aOn_0; " ON "
0x180074b2d  mov     rcx, rdi
0x180074b30  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074b35  nop
0x180074b36  xorps   xmm0, xmm0
0x180074b39  movups  [rbp+var_28], xmm0
0x180074b3d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000001
0x180074b45  mov     word ptr [rbp+var_28], 41h ; 'A'
0x180074b4b  movups  xmm0, [rbp+var_28]
0x180074b4f  movups  xmmword ptr [rbp+Block], xmm0
0x180074b53  movups  [rbp+var_38], xmm1
0x180074b57  lea     rdx, [rbp+Block]
0x180074b5b  mov     r8d, 1
0x180074b61  mov     rcx, rax
0x180074b64  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180074b69  lea     rdx, aIncoming; ".incoming = "
0x180074b70  mov     rcx, rax
0x180074b73  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074b78  mov     r8, [rbx+10h]
0x180074b7c  cmp     qword ptr [rbx+18h], 0Fh
0x180074b81  jbe     short loc_180074B86
0x180074b83  mov     rbx, [rbx]
0x180074b86  mov     rdx, rbx
0x180074b89  mov     rcx, rax
0x180074b8c  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180074b91  lea     rdx, asc_1801D0CE8; "."
0x180074b98  mov     rcx, rax
0x180074b9b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074ba0  lea     rdx, aSourcePath; "source_path"
0x180074ba7  mov     rcx, rax
0x180074baa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074baf  mov     rcx, rax
0x180074bb2  lea     rdx, asc_1801D0D08; " "
0x180074bb9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180074bbe  mov     rax, qword ptr [rbp+var_38+8]
0x180074bc2  cmp     rax, 0Fh
0x180074bc6  jbe     short loc_180074C08
0x180074bc8  mov     rcx, [rbp+Block]; Block
0x180074bcc  mov     rdx, rcx
0x180074bcf  inc     rax
0x180074bd2  cmp     rax, rsi
0x180074bd5  jb      short loc_180074C02
0x180074bd7  mov     rcx, [rcx-8]
0x180074bdb  sub     rdx, rcx
0x180074bde  lea     rax, [rdx-8]
0x180074be2  cmp     rax, 1Fh
0x180074be6  jbe     short loc_180074C02
0x180074be8  mov     [rsp+80h+Reserved], 0; Reserved
0x180074bf1  xor     r9d, r9d; LineNo
0x180074bf4  xor     r8d, r8d; FileName
0x180074bf7  xor     edx, edx; FunctionName
0x180074bf9  xor     ecx, ecx; Expression
0x180074bfb  call    cs:__imp__invoke_watson
0x180074c02  call    cs:__imp_free
0x180074c08  xor     al, al
0x180074c0a  mov     rcx, [rbp+var_8]
0x180074c0e  xor     rcx, rsp; StackCookie
0x180074c11  call    __security_check_cookie
0x180074c16  mov     rbx, [rsp+80h+arg_8]
0x180074c1e  add     rsp, 80h
0x180074c25  pop     rdi
0x180074c26  pop     rsi
0x180074c27  pop     rbp
0x180074c28  retn
```
