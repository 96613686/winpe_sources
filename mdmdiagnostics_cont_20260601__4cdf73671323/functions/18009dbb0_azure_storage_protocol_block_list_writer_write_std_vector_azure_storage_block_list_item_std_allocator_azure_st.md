# azure::storage::protocol::block_list_writer::write(std::vector<azure::storage::block_list_item,std::allocator<azure::storage::block_list_item>> const &)

- ea: `0x18009dbb0`
- end: `0x18009deea`
- name: `?write@block_list_writer@protocol@storage@azure@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@Vblock_list_item@storage@azure@@V?$allocator@Vblock_list_item@storage@azure@@@std@@@6@@Z`
- size: `826`
- prototype: `__int64 __fastcall(azure::storage::core::xml::xml_writer *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006fe10`

## callees

- `0x180019000`
- `0x180019508`
- `0x18009c460`
- `0x18009caf0`
- `0x18009d250`
- `0x18009d320`
- `0x18009dbb0`
- `0x1800a9e80`
- `0x1800e5248`
- `0x1800e533c`
- `0x1800e79ec`
- `0x1800f3efc`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009dea8`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009dea8`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dc55`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dc55`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009deb2`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009deb2`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18009dc21`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18009dc21`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dc02`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dc02`

## string_xrefs

- `0x18009dde3`: `Committed`
- `0x18009ddef`: `Committed`
- `0x18009ddce`: `Uncommitted`
- `0x18009ddda`: `Uncommitted`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall azure::storage::protocol::block_list_writer::write(void **this, __int64 a2, __int64 *a3)
{
  size_t v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rbx
  int v10; // ecx
  int v11; // ecx
  size_t v12; // rax
  const wchar_t *v13; // rdx
  void *v14; // rcx
  __int64 v16; // [rsp+28h] [rbp-D8h]
  __int64 *v17; // [rsp+30h] [rbp-D0h] BYREF
  void **v18; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[96]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  int v21; // [rsp+A8h] [rbp-58h]
  _BYTE v22[104]; // [rsp+B8h] [rbp-48h] BYREF
  void *Block[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v24; // [rsp+130h] [rbp+30h]
  unsigned __int64 v25; // [rsp+138h] [rbp+38h]
  void *v26[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v27; // [rsp+150h] [rbp+50h]
  unsigned __int64 v28; // [rsp+158h] [rbp+58h]

  v16 = a2;
  v17 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
  std::ios::ios(v22);
  std::ostream::ostream(&v17, &v18, 0, 0, 2, v16);
  *(__int64 **)((char *)&v17 + *((int *)v17 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(_DWORD *)((char *)&v16 + *((int *)v17 + 1) + 4) = *((_DWORD *)v17 + 1) - 136;
  std::streambuf::streambuf(&v18);
  v18 = &std::stringbuf::`vftable';
  v20 = 0;
  v21 = 4;
  azure::storage::core::xml::xml_writer::initialize(this, (__int64)&v17);
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v26, &Name, 0);
  *(_OWORD *)Block = 0;
  v24 = 0;
  v25 = 0;
  v6 = wcslen_0(L"BlockList");
  std::wstring::_Construct<1,unsigned short const *>(Block, L"BlockList", v6);
  azure::storage::core::xml::xml_writer::write_start_element(this, Block, v26);
  if ( v25 > 7 )
  {
    if ( 2 * v25 + 2 < 0x1000 )
    {
      v7 = Block[0];
    }
    else
    {
      v7 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
  }
  v24 = 0;
  v25 = 7;
  LOWORD(Block[0]) = 0;
  if ( v28 > 7 )
  {
    if ( 2 * v28 + 2 < 0x1000 )
    {
      v8 = v26[0];
    }
    else
    {
      v8 = (void *)*((_QWORD *)v26[0] - 1);
      if ( (unsigned __int64)((char *)v26[0] - (char *)v8 - 8) > 0x1F )
LABEL_28:
        __fastfail(5u);
    }
    operator delete(v8);
  }
  v9 = *a3;
  if ( *a3 != a3[1] )
  {
    while ( 1 )
    {
      *(_OWORD *)Block = 0;
      v24 = 0;
      v25 = 7;
      LOWORD(Block[0]) = 0;
      v10 = *(_DWORD *)(v9 + 40);
      if ( !v10 )
      {
        v12 = wcslen_0(L"Committed");
        v13 = L"Committed";
        goto LABEL_20;
      }
      v11 = v10 - 1;
      if ( !v11 )
        break;
      if ( v11 == 1 )
      {
        v12 = wcslen_0(L"Latest");
        v13 = L"Latest";
LABEL_20:
        std::wstring::_Assign<unsigned short>(Block, v13, v12);
      }
      azure::storage::core::xml::xml_writer::write_element(this, Block, v9);
      if ( v25 > 7 )
      {
        v14 = Block[0];
        if ( 2 * v25 + 2 >= 0x1000 )
        {
          if ( (unsigned __int64)Block[0] - *((_QWORD *)Block[0] - 1) - 8 > 0x1F )
            goto LABEL_28;
          v14 = (void *)*((_QWORD *)Block[0] - 1);
        }
        operator delete(v14);
      }
      v9 += 48;
      if ( v9 == a3[1] )
        goto LABEL_27;
    }
    v12 = wcslen_0(L"Uncommitted");
    v13 = L"Uncommitted";
    goto LABEL_20;
  }
LABEL_27:
  azure::storage::core::xml::xml_writer::finalize((azure::storage::core::xml::xml_writer *)this);
  std::ostringstream::str(&v17, a2);
  *(__int64 **)((char *)&v17 + *((int *)v17 + 1)) = (__int64 *)&std::ostringstream::`vftable';
  *(_DWORD *)((char *)&v16 + *((int *)v17 + 1) + 4) = *((_DWORD *)v17 + 1) - 136;
  std::stringbuf::~stringbuf(&v18);
  std::ostream::~ostream<char,std::char_traits<char>>(v19);
  std::ios::~ios<char,std::char_traits<char>>(v22);
  return a2;
}

```

## disassembly

```asm
0x18009dbb0  mov     [rsp-8+arg_10], rbx
0x18009dbb5  mov     [rsp-8+arg_18], rsi
0x18009dbba  push    rbp
0x18009dbbb  push    rdi
0x18009dbbc  push    r12
0x18009dbbe  push    r14
0x18009dbc0  push    r15
0x18009dbc2  lea     rbp, [rsp-70h]
0x18009dbc7  sub     rsp, 170h
0x18009dbce  mov     rax, cs:__security_cookie
0x18009dbd5  xor     rax, rsp
0x18009dbd8  mov     [rbp+90h+var_30], rax
0x18009dbdc  mov     rdi, r8
0x18009dbdf  mov     r14, rdx
0x18009dbe2  mov     rsi, rcx
0x18009dbe5  mov     [rsp+190h+var_168], rdx
0x18009dbea  xor     r15d, r15d
0x18009dbed  mov     [rsp+190h+var_170], r15d
0x18009dbf2  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x18009dbf9  mov     [rsp+190h+var_160], rax
0x18009dbfe  lea     rcx, [rbp+90h+var_D8]
0x18009dc02  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x18009dc08  nop
0x18009dc09  mov     [rsp+190h+var_170], 2
0x18009dc11  xor     r9d, r9d
0x18009dc14  xor     r8d, r8d
0x18009dc17  lea     rdx, [rsp+190h+var_158]
0x18009dc1c  lea     rcx, [rsp+190h+var_160]
0x18009dc21  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x18009dc27  nop
0x18009dc28  mov     rax, [rsp+190h+var_160]
0x18009dc2d  movsxd  rcx, dword ptr [rax+4]
0x18009dc31  lea     r12, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x18009dc38  mov     [rsp+rcx+190h+var_160], r12
0x18009dc3d  mov     rax, [rsp+190h+var_160]
0x18009dc42  movsxd  rcx, dword ptr [rax+4]
0x18009dc46  lea     edx, [rcx-88h]
0x18009dc4c  mov     dword ptr [rsp+rcx+190h+var_168+4], edx
0x18009dc50  lea     rcx, [rsp+190h+var_158]
0x18009dc55  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x18009dc5b  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x18009dc62  mov     [rsp+190h+var_158], rax
0x18009dc67  mov     [rbp+90h+var_F0], r15
0x18009dc6b  mov     [rbp+90h+var_E8], 4
0x18009dc72  lea     rdx, [rsp+190h+var_160]
0x18009dc77  mov     rcx, rsi
0x18009dc7a  call    ?initialize@xml_writer@xml@core@storage@azure@@IEAAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z; azure::storage::core::xml::xml_writer::initialize(std::ostream &)
0x18009dc7f  xorps   xmm0, xmm0
0x18009dc82  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x18009dc86  mov     [rbp+90h+var_40], r15
0x18009dc8a  mov     [rbp+90h+var_38], r15
0x18009dc8e  xor     r8d, r8d
0x18009dc91  lea     rdx, Name
0x18009dc98  lea     rcx, [rbp+90h+var_50]
0x18009dc9c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009dca1  nop
0x18009dca2  xorps   xmm0, xmm0
0x18009dca5  movups  xmmword ptr [rbp+90h+Block], xmm0
0x18009dca9  mov     [rbp+90h+var_60], r15
0x18009dcad  mov     [rbp+90h+var_58], r15
0x18009dcb1  lea     rcx, ?xml_block_list@protocol@storage@azure@@3QBGB; "BlockList"
0x18009dcb8  call    wcslen_0
0x18009dcbd  mov     r8, rax
0x18009dcc0  lea     rdx, ?xml_block_list@protocol@storage@azure@@3QBGB; "BlockList"
0x18009dcc7  lea     rcx, [rbp+90h+Block]
0x18009dccb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009dcd0  nop
0x18009dcd1  lea     r8, [rbp+90h+var_50]
0x18009dcd5  lea     rdx, [rbp+90h+Block]
0x18009dcd9  mov     rcx, rsi
0x18009dcdc  call    ?write_start_element@xml_writer@xml@core@storage@azure@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; azure::storage::core::xml::xml_writer::write_start_element(std::wstring const &,std::wstring const &)
0x18009dce1  nop
0x18009dce2  mov     rdx, [rbp+90h+var_58]
0x18009dce6  cmp     rdx, 7
0x18009dcea  jbe     short loc_18009DD27
0x18009dcec  mov     rax, [rbp+90h+Block]
0x18009dcf0  lea     rdx, ds:2[rdx*2]
0x18009dcf8  cmp     rdx, 1000h
0x18009dcff  jb      short loc_18009DD1F
0x18009dd01  mov     rcx, [rax-8]
0x18009dd05  sub     rax, rcx
0x18009dd08  sub     rax, 8
0x18009dd0c  cmp     rax, 1Fh
0x18009dd10  ja      short loc_18009DD18
0x18009dd12  add     rdx, 27h ; '''
0x18009dd16  jmp     short loc_18009DD22
0x18009dd18  mov     ecx, 5
0x18009dd1d  int     29h; Win8: RtlFailFast(ecx)
0x18009dd1f  mov     rcx, rax; Block
0x18009dd22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd27  mov     [rbp+90h+var_60], r15
0x18009dd2b  mov     [rbp+90h+var_58], 7
0x18009dd33  mov     word ptr [rbp+90h+Block], r15w
0x18009dd38  mov     rdx, [rbp+90h+var_38]
0x18009dd3c  cmp     rdx, 7
0x18009dd40  jbe     short loc_18009DD7A
0x18009dd42  mov     rax, [rbp+90h+var_50]
0x18009dd46  lea     rdx, ds:2[rdx*2]
0x18009dd4e  cmp     rdx, 1000h
0x18009dd55  jb      short loc_18009DD72
0x18009dd57  mov     rcx, [rax-8]
0x18009dd5b  sub     rax, rcx
0x18009dd5e  sub     rax, 8
0x18009dd62  cmp     rax, 1Fh
0x18009dd66  ja      loc_18009DEE3
0x18009dd6c  add     rdx, 27h ; '''
0x18009dd70  jmp     short loc_18009DD75
0x18009dd72  mov     rcx, rax; Block
0x18009dd75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd7a  mov     rbx, [rdi]
0x18009dd7d  cmp     rbx, [rdi+8]
0x18009dd81  jz      loc_18009DE60
0x18009dd87  nop     word ptr [rax+rax+00000000h]
0x18009dd90  xorps   xmm0, xmm0
0x18009dd93  movups  xmmword ptr [rbp+90h+Block], xmm0
0x18009dd97  mov     [rbp+90h+var_60], r15
0x18009dd9b  mov     [rbp+90h+var_58], 7
0x18009dda3  mov     word ptr [rbp+90h+Block], r15w
0x18009dda8  mov     ecx, [rbx+28h]
0x18009ddab  test    ecx, ecx
0x18009ddad  jz      short loc_18009DDE3
0x18009ddaf  sub     ecx, 1
0x18009ddb2  jz      short loc_18009DDCE
0x18009ddb4  cmp     ecx, 1
0x18009ddb7  jnz     short loc_18009DE02
0x18009ddb9  lea     rcx, ?xml_latest@protocol@storage@azure@@3QBGB; "Latest"
0x18009ddc0  call    wcslen_0
0x18009ddc5  lea     rdx, ?xml_latest@protocol@storage@azure@@3QBGB; "Latest"
0x18009ddcc  jmp     short loc_18009DDF6
0x18009ddce  lea     rcx, ?xml_uncommitted@protocol@storage@azure@@3QBGB; "Uncommitted"
0x18009ddd5  call    wcslen_0
0x18009ddda  lea     rdx, ?xml_uncommitted@protocol@storage@azure@@3QBGB; "Uncommitted"
0x18009dde1  jmp     short loc_18009DDF6
0x18009dde3  lea     rcx, ?xml_committed@protocol@storage@azure@@3QBGB; "Committed"
0x18009ddea  call    wcslen_0
0x18009ddef  lea     rdx, ?xml_committed@protocol@storage@azure@@3QBGB; "Committed"
0x18009ddf6  mov     r8, rax
0x18009ddf9  lea     rcx, [rbp+90h+Block]
0x18009ddfd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009de02  mov     r8, rbx
0x18009de05  lea     rdx, [rbp+90h+Block]
0x18009de09  mov     rcx, rsi
0x18009de0c  call    ?write_element@xml_writer@xml@core@storage@azure@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; azure::storage::core::xml::xml_writer::write_element(std::wstring const &,std::wstring const &)
0x18009de11  nop
0x18009de12  mov     rdx, [rbp+90h+var_58]
0x18009de16  cmp     rdx, 7
0x18009de1a  jbe     short loc_18009DE52
0x18009de1c  lea     rdx, ds:2[rdx*2]
0x18009de24  mov     rcx, [rbp+90h+Block]
0x18009de28  cmp     rdx, 1000h
0x18009de2f  jb      short loc_18009DE4D
0x18009de31  mov     rax, [rcx-8]
0x18009de35  sub     rcx, rax
0x18009de38  sub     rcx, 8
0x18009de3c  cmp     rcx, 1Fh
0x18009de40  ja      loc_18009DEE3
0x18009de46  add     rdx, 27h ; '''
0x18009de4a  mov     rcx, rax; Block
0x18009de4d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009de52  add     rbx, 30h ; '0'
0x18009de56  cmp     rbx, [rdi+8]
0x18009de5a  jnz     loc_18009DD90
0x18009de60  mov     rcx, rsi; this
0x18009de63  call    ?finalize@xml_writer@xml@core@storage@azure@@IEAAXXZ; azure::storage::core::xml::xml_writer::finalize(void)
0x18009de68  mov     rdx, r14
0x18009de6b  lea     rcx, [rsp+190h+var_160]
0x18009de70  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::ostringstream::str(void)
0x18009de75  nop
0x18009de76  mov     rcx, [rsp+190h+var_160]
0x18009de7b  movsxd  rdx, dword ptr [rcx+4]
0x18009de7f  mov     [rsp+rdx+190h+var_160], r12
0x18009de84  mov     rcx, [rsp+190h+var_160]
0x18009de89  movsxd  rdx, dword ptr [rcx+4]
0x18009de8d  lea     r8d, [rdx-88h]
0x18009de94  mov     dword ptr [rsp+rdx+190h+var_168+4], r8d
0x18009de99  lea     rcx, [rsp+190h+var_158]
0x18009de9e  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x18009dea3  lea     rcx, [rsp+190h+var_150]
0x18009dea8  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x18009deae  lea     rcx, [rbp+90h+var_D8]
0x18009deb2  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18009deb8  mov     rax, r14
0x18009debb  mov     rcx, [rbp+90h+var_30]
0x18009debf  xor     rcx, rsp; StackCookie
0x18009dec2  call    __security_check_cookie
0x18009dec7  lea     r11, [rsp+190h+var_20]
0x18009decf  mov     rbx, [r11+40h]
0x18009ded3  mov     rsi, [r11+48h]
0x18009ded7  mov     rsp, r11
0x18009deda  pop     r15
0x18009dedc  pop     r14
0x18009dede  pop     r12
0x18009dee0  pop     rdi
0x18009dee1  pop     rbp
0x18009dee2  retn
0x18009dee3  mov     ecx, 5
0x18009dee8  int     29h; Win8: RtlFailFast(ecx)
```
