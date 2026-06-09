# azure::storage::protocol::block_list_writer::write(std::vector<azure::storage::block_list_item,std::allocator<azure::storage::block_list_item>> const &)

- ea: `0x18009dd50`
- end: `0x18009e08a`
- name: `?write@block_list_writer@protocol@storage@azure@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@Vblock_list_item@storage@azure@@V?$allocator@Vblock_list_item@storage@azure@@@std@@@6@@Z`
- size: `826`
- prototype: `__int64 __fastcall(azure::storage::core::xml::xml_writer *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006ff80`

## callees

- `0x180019080`
- `0x180019588`
- `0x18009c600`
- `0x18009cc90`
- `0x18009d3f0`
- `0x18009d4c0`
- `0x18009dd50`
- `0x1800aa020`
- `0x1800e53ec`
- `0x1800e54e0`
- `0x1800e7bac`
- `0x1800f4a30`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009e048`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009e048`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009ddf5`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009ddf5`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009e052`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18009e052`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18009ddc1`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18009ddc1`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dda2`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18009dda2`

## string_xrefs

- `0x18009df83`: `Committed`
- `0x18009df8f`: `Committed`
- `0x18009df6e`: `Uncommitted`
- `0x18009df7a`: `Uncommitted`

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
0x18009dd50  mov     [rsp-8+arg_10], rbx
0x18009dd55  mov     [rsp-8+arg_18], rsi
0x18009dd5a  push    rbp
0x18009dd5b  push    rdi
0x18009dd5c  push    r12
0x18009dd5e  push    r14
0x18009dd60  push    r15
0x18009dd62  lea     rbp, [rsp-70h]
0x18009dd67  sub     rsp, 170h
0x18009dd6e  mov     rax, cs:__security_cookie
0x18009dd75  xor     rax, rsp
0x18009dd78  mov     [rbp+90h+var_30], rax
0x18009dd7c  mov     rdi, r8
0x18009dd7f  mov     r14, rdx
0x18009dd82  mov     rsi, rcx
0x18009dd85  mov     [rsp+190h+var_168], rdx
0x18009dd8a  xor     r15d, r15d
0x18009dd8d  mov     [rsp+190h+var_170], r15d
0x18009dd92  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x18009dd99  mov     [rsp+190h+var_160], rax
0x18009dd9e  lea     rcx, [rbp+90h+var_D8]
0x18009dda2  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x18009dda8  nop
0x18009dda9  mov     [rsp+190h+var_170], 2
0x18009ddb1  xor     r9d, r9d
0x18009ddb4  xor     r8d, r8d
0x18009ddb7  lea     rdx, [rsp+190h+var_158]
0x18009ddbc  lea     rcx, [rsp+190h+var_160]
0x18009ddc1  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x18009ddc7  nop
0x18009ddc8  mov     rax, [rsp+190h+var_160]
0x18009ddcd  movsxd  rcx, dword ptr [rax+4]
0x18009ddd1  lea     r12, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x18009ddd8  mov     [rsp+rcx+190h+var_160], r12
0x18009dddd  mov     rax, [rsp+190h+var_160]
0x18009dde2  movsxd  rcx, dword ptr [rax+4]
0x18009dde6  lea     edx, [rcx-88h]
0x18009ddec  mov     dword ptr [rsp+rcx+190h+var_168+4], edx
0x18009ddf0  lea     rcx, [rsp+190h+var_158]
0x18009ddf5  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x18009ddfb  lea     rax, ??_7?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::stringbuf::`vftable'
0x18009de02  mov     [rsp+190h+var_158], rax
0x18009de07  mov     [rbp+90h+var_F0], r15
0x18009de0b  mov     [rbp+90h+var_E8], 4
0x18009de12  lea     rdx, [rsp+190h+var_160]
0x18009de17  mov     rcx, rsi
0x18009de1a  call    ?initialize@xml_writer@xml@core@storage@azure@@IEAAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z; azure::storage::core::xml::xml_writer::initialize(std::ostream &)
0x18009de1f  xorps   xmm0, xmm0
0x18009de22  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x18009de26  mov     [rbp+90h+var_40], r15
0x18009de2a  mov     [rbp+90h+var_38], r15
0x18009de2e  xor     r8d, r8d
0x18009de31  lea     rdx, Name
0x18009de38  lea     rcx, [rbp+90h+var_50]
0x18009de3c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009de41  nop
0x18009de42  xorps   xmm0, xmm0
0x18009de45  movups  xmmword ptr [rbp+90h+Block], xmm0
0x18009de49  mov     [rbp+90h+var_60], r15
0x18009de4d  mov     [rbp+90h+var_58], r15
0x18009de51  lea     rcx, ?xml_block_list@protocol@storage@azure@@3QBGB; "BlockList"
0x18009de58  call    wcslen_0
0x18009de5d  mov     r8, rax
0x18009de60  lea     rdx, ?xml_block_list@protocol@storage@azure@@3QBGB; "BlockList"
0x18009de67  lea     rcx, [rbp+90h+Block]
0x18009de6b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009de70  nop
0x18009de71  lea     r8, [rbp+90h+var_50]
0x18009de75  lea     rdx, [rbp+90h+Block]
0x18009de79  mov     rcx, rsi
0x18009de7c  call    ?write_start_element@xml_writer@xml@core@storage@azure@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; azure::storage::core::xml::xml_writer::write_start_element(std::wstring const &,std::wstring const &)
0x18009de81  nop
0x18009de82  mov     rdx, [rbp+90h+var_58]
0x18009de86  cmp     rdx, 7
0x18009de8a  jbe     short loc_18009DEC7
0x18009de8c  mov     rax, [rbp+90h+Block]
0x18009de90  lea     rdx, ds:2[rdx*2]
0x18009de98  cmp     rdx, 1000h
0x18009de9f  jb      short loc_18009DEBF
0x18009dea1  mov     rcx, [rax-8]
0x18009dea5  sub     rax, rcx
0x18009dea8  sub     rax, 8
0x18009deac  cmp     rax, 1Fh
0x18009deb0  ja      short loc_18009DEB8
0x18009deb2  add     rdx, 27h ; '''
0x18009deb6  jmp     short loc_18009DEC2
0x18009deb8  mov     ecx, 5
0x18009debd  int     29h; Win8: RtlFailFast(ecx)
0x18009debf  mov     rcx, rax; Block
0x18009dec2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dec7  mov     [rbp+90h+var_60], r15
0x18009decb  mov     [rbp+90h+var_58], 7
0x18009ded3  mov     word ptr [rbp+90h+Block], r15w
0x18009ded8  mov     rdx, [rbp+90h+var_38]
0x18009dedc  cmp     rdx, 7
0x18009dee0  jbe     short loc_18009DF1A
0x18009dee2  mov     rax, [rbp+90h+var_50]
0x18009dee6  lea     rdx, ds:2[rdx*2]
0x18009deee  cmp     rdx, 1000h
0x18009def5  jb      short loc_18009DF12
0x18009def7  mov     rcx, [rax-8]
0x18009defb  sub     rax, rcx
0x18009defe  sub     rax, 8
0x18009df02  cmp     rax, 1Fh
0x18009df06  ja      loc_18009E083
0x18009df0c  add     rdx, 27h ; '''
0x18009df10  jmp     short loc_18009DF15
0x18009df12  mov     rcx, rax; Block
0x18009df15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009df1a  mov     rbx, [rdi]
0x18009df1d  cmp     rbx, [rdi+8]
0x18009df21  jz      loc_18009E000
0x18009df27  nop     word ptr [rax+rax+00000000h]
0x18009df30  xorps   xmm0, xmm0
0x18009df33  movups  xmmword ptr [rbp+90h+Block], xmm0
0x18009df37  mov     [rbp+90h+var_60], r15
0x18009df3b  mov     [rbp+90h+var_58], 7
0x18009df43  mov     word ptr [rbp+90h+Block], r15w
0x18009df48  mov     ecx, [rbx+28h]
0x18009df4b  test    ecx, ecx
0x18009df4d  jz      short loc_18009DF83
0x18009df4f  sub     ecx, 1
0x18009df52  jz      short loc_18009DF6E
0x18009df54  cmp     ecx, 1
0x18009df57  jnz     short loc_18009DFA2
0x18009df59  lea     rcx, ?xml_latest@protocol@storage@azure@@3QBGB; "Latest"
0x18009df60  call    wcslen_0
0x18009df65  lea     rdx, ?xml_latest@protocol@storage@azure@@3QBGB; "Latest"
0x18009df6c  jmp     short loc_18009DF96
0x18009df6e  lea     rcx, ?xml_uncommitted@protocol@storage@azure@@3QBGB; "Uncommitted"
0x18009df75  call    wcslen_0
0x18009df7a  lea     rdx, ?xml_uncommitted@protocol@storage@azure@@3QBGB; "Uncommitted"
0x18009df81  jmp     short loc_18009DF96
0x18009df83  lea     rcx, ?xml_committed@protocol@storage@azure@@3QBGB; "Committed"
0x18009df8a  call    wcslen_0
0x18009df8f  lea     rdx, ?xml_committed@protocol@storage@azure@@3QBGB; "Committed"
0x18009df96  mov     r8, rax
0x18009df99  lea     rcx, [rbp+90h+Block]
0x18009df9d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009dfa2  mov     r8, rbx
0x18009dfa5  lea     rdx, [rbp+90h+Block]
0x18009dfa9  mov     rcx, rsi
0x18009dfac  call    ?write_element@xml_writer@xml@core@storage@azure@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; azure::storage::core::xml::xml_writer::write_element(std::wstring const &,std::wstring const &)
0x18009dfb1  nop
0x18009dfb2  mov     rdx, [rbp+90h+var_58]
0x18009dfb6  cmp     rdx, 7
0x18009dfba  jbe     short loc_18009DFF2
0x18009dfbc  lea     rdx, ds:2[rdx*2]
0x18009dfc4  mov     rcx, [rbp+90h+Block]
0x18009dfc8  cmp     rdx, 1000h
0x18009dfcf  jb      short loc_18009DFED
0x18009dfd1  mov     rax, [rcx-8]
0x18009dfd5  sub     rcx, rax
0x18009dfd8  sub     rcx, 8
0x18009dfdc  cmp     rcx, 1Fh
0x18009dfe0  ja      loc_18009E083
0x18009dfe6  add     rdx, 27h ; '''
0x18009dfea  mov     rcx, rax; Block
0x18009dfed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dff2  add     rbx, 30h ; '0'
0x18009dff6  cmp     rbx, [rdi+8]
0x18009dffa  jnz     loc_18009DF30
0x18009e000  mov     rcx, rsi; this
0x18009e003  call    ?finalize@xml_writer@xml@core@storage@azure@@IEAAXXZ; azure::storage::core::xml::xml_writer::finalize(void)
0x18009e008  mov     rdx, r14
0x18009e00b  lea     rcx, [rsp+190h+var_160]
0x18009e010  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::ostringstream::str(void)
0x18009e015  nop
0x18009e016  mov     rcx, [rsp+190h+var_160]
0x18009e01b  movsxd  rdx, dword ptr [rcx+4]
0x18009e01f  mov     [rsp+rdx+190h+var_160], r12
0x18009e024  mov     rcx, [rsp+190h+var_160]
0x18009e029  movsxd  rdx, dword ptr [rcx+4]
0x18009e02d  lea     r8d, [rdx-88h]
0x18009e034  mov     dword ptr [rsp+rdx+190h+var_168+4], r8d
0x18009e039  lea     rcx, [rsp+190h+var_158]
0x18009e03e  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x18009e043  lea     rcx, [rsp+190h+var_150]
0x18009e048  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x18009e04e  lea     rcx, [rbp+90h+var_D8]
0x18009e052  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18009e058  mov     rax, r14
0x18009e05b  mov     rcx, [rbp+90h+var_30]
0x18009e05f  xor     rcx, rsp; StackCookie
0x18009e062  call    __security_check_cookie
0x18009e067  lea     r11, [rsp+190h+var_20]
0x18009e06f  mov     rbx, [r11+40h]
0x18009e073  mov     rsi, [r11+48h]
0x18009e077  mov     rsp, r11
0x18009e07a  pop     r15
0x18009e07c  pop     r14
0x18009e07e  pop     r12
0x18009e080  pop     rdi
0x18009e081  pop     rbp
0x18009e082  retn
0x18009e083  mov     ecx, 5
0x18009e088  int     29h; Win8: RtlFailFast(ecx)
```
