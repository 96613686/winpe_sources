# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::parse<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &&,std::function<bool (int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> &)>,bool,bool)

- ea: `0x1800178d0`
- end: `0x180017b8d`
- name: `??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@SA?AV01@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z@3@_N2@Z`
- size: `701`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001cb44`
- `0x180028cc4`

## callees

- `0x180002490`
- `0x180008a68`
- `0x1800178d0`
- `0x18001a674`
- `0x18001b0bc`
- `0x180025448`
- `0x180025d30`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_localeconv` at `0x180017a83`
- `api-ms-win-crt-private-l1-1-0!_o_localeconv` at `0x180017a83`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::parse<std::string>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  _BYTE *v6; // r8
  __int64 (__fastcall ***v7)(_QWORD, _BYTE *, _QWORD); // rcx
  _QWORD *v8; // rcx
  char *v9; // r14
  _BYTE *v10; // rcx
  __int64 v11; // rdx
  char *decimal_point; // rax
  char v13; // al
  __int64 v14; // rdx
  _BYTE *v15; // rdx
  _BYTE *v16; // rdx
  _BYTE *v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rdx
  _BYTE v21[56]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v22; // [rsp+70h] [rbp-90h]
  _BYTE v23[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  __int64 *v26; // [rsp+C0h] [rbp-40h]
  _BYTE *v27; // [rsp+C8h] [rbp-38h]
  _BYTE v28[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v29; // [rsp+108h] [rbp+8h]
  int v30; // [rsp+110h] [rbp+10h]
  _QWORD v31[2]; // [rsp+118h] [rbp+18h] BYREF
  char v32; // [rsp+128h] [rbp+28h]
  int v33; // [rsp+12Ch] [rbp+2Ch]
  char v34; // [rsp+130h] [rbp+30h]
  __int64 v35; // [rsp+138h] [rbp+38h]
  __int128 v36; // [rsp+140h] [rbp+40h]
  __int128 v37; // [rsp+150h] [rbp+50h] BYREF
  __int64 v38; // [rsp+160h] [rbp+60h]
  __int128 v39; // [rsp+168h] [rbp+68h] BYREF
  __int64 v40; // [rsp+178h] [rbp+78h]
  __int64 v41; // [rsp+180h] [rbp+80h]
  const unsigned __int16 *v42; // [rsp+188h] [rbp+88h]
  __int128 v43; // [rsp+190h] [rbp+90h]
  __int64 v44; // [rsp+1A0h] [rbp+A0h]
  int v45; // [rsp+1A8h] [rbp+A8h]
  char v46; // [rsp+1B0h] [rbp+B0h]

  v25 = a1;
  v26 = a3;
  *(_BYTE *)a1 = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
    (_QWORD *)(a1 + 8),
    0);
  v6 = 0;
  v22 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, _QWORD))a3[7];
  if ( v7 )
  {
    v6 = (_BYTE *)(**v7)(v7, v21, 0);
    v22 = v6;
  }
  if ( a2[3] <= 0xFu )
    v8 = a2;
  else
    v8 = (_QWORD *)*a2;
  v9 = (char *)v8 + a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  v10 = 0;
  v24 = 0;
  if ( v6 )
  {
    v10 = v6;
    if ( v6 == v21 )
    {
      v10 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v23);
      v24 = v10;
      if ( !v22 )
        goto LABEL_14;
      LOBYTE(v11) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v22 + 32LL))(v22, v11);
      v10 = v24;
    }
    else
    {
      v24 = v6;
    }
    v22 = 0;
  }
LABEL_14:
  v27 = v28;
  v29 = 0;
  if ( v10 )
    v29 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v10)(v10, v28);
  v30 = 0;
  v31[0] = a2;
  v31[1] = v9;
  v32 = 0;
  v33 = -1;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 15;
  LOBYTE(v39) = 0;
  v42 = &word_1800321F2;
  v43 = 0;
  v44 = 0;
  decimal_point = localeconv()->decimal_point;
  if ( decimal_point )
    v13 = *decimal_point;
  else
    v13 = 46;
  v45 = v13;
  v46 = 1;
  v30 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan((__int64)v31);
  if ( v24 )
  {
    v15 = v23;
    LOBYTE(v15) = v24 != v23;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v24 + 32LL))(v24, v15);
    v24 = 0;
  }
  if ( v22 )
  {
    v16 = v21;
    LOBYTE(v16) = v22 != v21;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v16);
    v22 = 0;
  }
  nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(
    (__int64)v28,
    v14,
    a1);
  std::string::~string(&v39);
  std::vector<char>::~vector<char>(&v37);
  if ( v29 )
  {
    v17 = v28;
    LOBYTE(v17) = v29 != v28;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v29 + 32LL))(v29, v17);
  }
  v18 = (__int64 *)a3[7];
  if ( v18 )
  {
    v19 = *v18;
    LOBYTE(v19) = v18 != a3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v18 + 32))(v18, v19);
    a3[7] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800178d0  mov     [rsp-8+arg_8], rbx
0x1800178d5  push    rbp
0x1800178d6  push    rsi
0x1800178d7  push    rdi
0x1800178d8  push    r14
0x1800178da  push    r15
0x1800178dc  lea     rbp, [rsp-0D0h]
0x1800178e4  sub     rsp, 1D0h
0x1800178eb  mov     rax, cs:__security_cookie
0x1800178f2  xor     rax, rsp
0x1800178f5  mov     [rbp+0F0h+var_30], rax
0x1800178fc  mov     rsi, r8
0x1800178ff  mov     rbx, rdx
0x180017902  mov     rdi, rcx
0x180017905  mov     [rbp+0F0h+var_138], rcx
0x180017909  mov     [rbp+0F0h+var_130], r8
0x18001790d  xor     r15d, r15d
0x180017910  mov     [rsp+1F0h+var_1D0], r15d
0x180017915  mov     [rcx], r15b
0x180017918  add     rcx, 8
0x18001791c  xor     edx, edx
0x18001791e  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180017923  nop
0x180017924  mov     [rsp+1F0h+var_1D0], 1
0x18001792c  lea     rax, [rsp+1F0h+var_1B8]
0x180017931  mov     [rsp+1F0h+var_1C8], rax
0x180017936  mov     r8d, r15d
0x180017939  mov     [rsp+1F0h+var_180], r15
0x18001793e  mov     rcx, [rsi+38h]
0x180017942  test    rcx, rcx
0x180017945  jz      short loc_18001795F
0x180017947  mov     rax, [rcx]
0x18001794a  lea     rdx, [rsp+1F0h+var_1B8]
0x18001794f  mov     rax, [rax]
0x180017952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017957  mov     r8, rax
0x18001795a  mov     [rsp+1F0h+var_180], rax
0x18001795f  lea     rax, [rsp+1F0h+var_1B8]
0x180017964  mov     [rsp+1F0h+var_1C8], rax
0x180017969  cmp     qword ptr [rbx+18h], 0Fh
0x18001796e  jbe     short loc_180017975
0x180017970  mov     rcx, [rbx]
0x180017973  jmp     short loc_180017978
0x180017975  mov     rcx, rbx
0x180017978  mov     r14, [rbx+10h]
0x18001797c  add     r14, rcx
0x18001797f  cmp     qword ptr [rbx+18h], 0Fh
0x180017984  jbe     short loc_180017989
0x180017986  mov     rbx, [rbx]
0x180017989  mov     rcx, r15
0x18001798c  mov     [rbp+0F0h+var_140], rcx
0x180017990  test    r8, r8
0x180017993  jz      short loc_1800179ED
0x180017995  lea     rax, [rsp+1F0h+var_1B8]
0x18001799a  mov     rcx, r8
0x18001799d  cmp     r8, rax
0x1800179a0  jnz     short loc_1800179E4
0x1800179a2  mov     rax, [r8]
0x1800179a5  lea     rdx, [rsp+1F0h+var_178]
0x1800179aa  mov     rax, [rax+8]
0x1800179ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179b3  mov     rcx, rax
0x1800179b6  mov     [rbp+0F0h+var_140], rax
0x1800179ba  mov     r8, [rsp+1F0h+var_180]
0x1800179bf  test    r8, r8
0x1800179c2  jz      short loc_1800179ED
0x1800179c4  mov     rax, [r8]
0x1800179c7  lea     rcx, [rsp+1F0h+var_1B8]
0x1800179cc  cmp     r8, rcx
0x1800179cf  setnz   dl
0x1800179d2  mov     rcx, r8
0x1800179d5  mov     rax, [rax+20h]
0x1800179d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179de  mov     rcx, [rbp+0F0h+var_140]
0x1800179e2  jmp     short loc_1800179E8
0x1800179e4  mov     [rbp+0F0h+var_140], rcx
0x1800179e8  mov     [rsp+1F0h+var_180], r15
0x1800179ed  lea     rax, [rsp+1F0h+var_178]
0x1800179f2  mov     [rsp+1F0h+var_1C0], rax
0x1800179f7  lea     rax, [rbp+0F0h+var_120]
0x1800179fb  mov     [rbp+0F0h+var_128], rax
0x1800179ff  mov     [rbp+0F0h+var_E8], r15
0x180017a03  test    rcx, rcx
0x180017a06  jz      short loc_180017A1B
0x180017a08  mov     rax, [rcx]
0x180017a0b  lea     rdx, [rbp+0F0h+var_120]
0x180017a0f  mov     rax, [rax]
0x180017a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a17  mov     [rbp+0F0h+var_E8], rax
0x180017a1b  mov     [rbp+0F0h+var_E0], r15d
0x180017a1f  mov     [rbp+0F0h+var_D8], rbx
0x180017a23  mov     [rbp+0F0h+var_D0], r14
0x180017a27  mov     [rbp+0F0h+var_C8], r15b
0x180017a2b  mov     [rbp+0F0h+var_C4], 0FFFFFFFFh
0x180017a32  mov     [rbp+0F0h+var_C0], r15b
0x180017a36  mov     [rbp+0F0h+var_B8], r15
0x180017a3a  xorps   xmm0, xmm0
0x180017a3d  movdqa  [rbp+0F0h+var_B0], xmm0
0x180017a42  xorps   xmm1, xmm1
0x180017a45  movdqa  [rbp+0F0h+var_A0], xmm1
0x180017a4a  mov     [rbp+0F0h+var_90], r15
0x180017a4e  movups  [rbp+0F0h+var_88], xmm0
0x180017a52  mov     [rbp+0F0h+var_78], r15
0x180017a56  mov     [rbp+0F0h+var_70], 0Fh
0x180017a61  mov     byte ptr [rbp+0F0h+var_88], r15b
0x180017a65  lea     rax, word_1800321F2
0x180017a6c  mov     [rbp+0F0h+var_68], rax
0x180017a73  movdqa  [rbp+0F0h+var_60], xmm0
0x180017a7b  movsd   [rbp+0F0h+var_50], xmm1
0x180017a83  call    cs:__imp_localeconv
0x180017a89  mov     rax, [rax]
0x180017a8c  test    rax, rax
0x180017a8f  jnz     short loc_180017A95
0x180017a91  mov     al, 2Eh ; '.'
0x180017a93  jmp     short loc_180017A97
0x180017a95  mov     al, [rax]
0x180017a97  movsx   eax, al
0x180017a9a  mov     [rbp+0F0h+var_48], eax
0x180017aa0  mov     [rbp+0F0h+var_40], 1
0x180017aa7  lea     rcx, [rbp+0F0h+var_D8]
0x180017aab  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x180017ab0  mov     [rbp+0F0h+var_E0], eax
0x180017ab3  mov     rcx, [rbp+0F0h+var_140]
0x180017ab7  test    rcx, rcx
0x180017aba  jz      short loc_180017AD7
0x180017abc  mov     rax, [rcx]
0x180017abf  lea     rdx, [rsp+1F0h+var_178]
0x180017ac4  cmp     rcx, rdx
0x180017ac7  setnz   dl
0x180017aca  mov     rax, [rax+20h]
0x180017ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad3  mov     [rbp+0F0h+var_140], r15
0x180017ad7  mov     [rsp+1F0h+var_1D0], 3
0x180017adf  mov     rcx, [rsp+1F0h+var_180]
0x180017ae4  test    rcx, rcx
0x180017ae7  jz      short loc_180017B05
0x180017ae9  mov     rax, [rcx]
0x180017aec  lea     rdx, [rsp+1F0h+var_1B8]
0x180017af1  cmp     rcx, rdx
0x180017af4  setnz   dl
0x180017af7  mov     rax, [rax+20h]
0x180017afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b00  mov     [rsp+1F0h+var_180], r15
0x180017b05  mov     r8, rdi
0x180017b08  lea     rcx, [rbp+0F0h+var_120]
0x180017b0c  call    ?parse@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAAX_NAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z; nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(bool,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &)
0x180017b11  nop
0x180017b12  lea     rcx, [rbp+0F0h+var_88]
0x180017b16  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180017b1b  lea     rcx, [rbp+0F0h+var_A0]
0x180017b1f  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180017b24  mov     rcx, [rbp+0F0h+var_E8]
0x180017b28  test    rcx, rcx
0x180017b2b  jz      short loc_180017B44
0x180017b2d  mov     rax, [rcx]
0x180017b30  lea     rdx, [rbp+0F0h+var_120]
0x180017b34  cmp     rcx, rdx
0x180017b37  setnz   dl
0x180017b3a  mov     rax, [rax+20h]
0x180017b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b43  nop
0x180017b44  mov     rcx, [rsi+38h]
0x180017b48  test    rcx, rcx
0x180017b4b  jz      short loc_180017B63
0x180017b4d  mov     rdx, [rcx]
0x180017b50  mov     rax, [rdx+20h]
0x180017b54  cmp     rcx, rsi
0x180017b57  setnz   dl
0x180017b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5f  mov     [rsi+38h], r15
0x180017b63  mov     rax, rdi
0x180017b66  mov     rcx, [rbp+0F0h+var_30]
0x180017b6d  xor     rcx, rsp; StackCookie
0x180017b70  call    __security_check_cookie
0x180017b75  mov     rbx, [rsp+1F0h+arg_8]
0x180017b7d  add     rsp, 1D0h
0x180017b84  pop     r15
0x180017b86  pop     r14
0x180017b88  pop     rdi
0x180017b89  pop     rsi
0x180017b8a  pop     rbp
0x180017b8b  retn
```
