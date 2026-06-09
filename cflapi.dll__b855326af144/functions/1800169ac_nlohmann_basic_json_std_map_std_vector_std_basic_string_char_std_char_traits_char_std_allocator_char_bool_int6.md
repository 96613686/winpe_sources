# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::erase<nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>,0>(nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>)

- ea: `0x1800169ac`
- end: `0x180016c69`
- name: `??$erase@V?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA?AV?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@1@V231@@Z`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x180024220`

## callees

- `0x180002490`
- `0x180002860`
- `0x180002f04`
- `0x180008a68`
- `0x180013130`
- `0x1800169ac`
- `0x180019fb8`
- `0x18001b0bc`
- `0x180021820`
- `0x1800226a8`
- `0x180022be8`
- `0x180022cf4`
- `0x180027b28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int8 **__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::erase<nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>,0>(
        unsigned __int8 *a1,
        unsigned __int8 **a2,
        unsigned __int8 **a3)
{
  unsigned __int8 *v5; // rdx
  unsigned __int8 v6; // cl
  unsigned __int8 *v7; // rsi
  __int64 v8; // rbx
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // r12
  unsigned __int8 *k; // rdi
  unsigned __int8 v12; // al
  __int64 v13; // rcx
  unsigned __int8 v14; // dl
  void *v15; // rax
  __int64 v16; // r9
  unsigned __int8 *v17; // rdx
  unsigned __int8 *i; // rbx
  unsigned __int8 *v19; // rax
  unsigned __int8 *j; // rcx
  __int64 v21; // rsi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-79h] BYREF
  unsigned __int8 v27[8]; // [rsp+58h] [rbp-41h] BYREF
  void *v28; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v29[56]; // [rsp+78h] [rbp-21h] BYREF

  if ( a1 != *a3 )
  {
    std::string::string(v27, "iterator does not fit current value");
    nlohmann::detail::invalid_iterator::create(v29, 202, v27);
    throw (nlohmann::detail::invalid_iterator *)v29;
  }
  *a2 = a1;
  a2[1] = 0;
  a2[2] = 0;
  a2[3] = (unsigned __int8 *)0x8000000000000000LL;
  v5 = *a2;
  if ( *v5 == 1 )
  {
    a2[1] = (unsigned __int8 *)**((_QWORD **)v5 + 1);
  }
  else if ( *v5 == 2 )
  {
    a2[2] = *(unsigned __int8 **)(*((_QWORD *)v5 + 1) + 8LL);
  }
  else
  {
    a2[3] = (unsigned __int8 *)1;
  }
  v6 = *a1;
  if ( *a1 == 1 )
  {
    v16 = *((_QWORD *)a1 + 1);
    v17 = a3[1];
    i = (unsigned __int8 *)*((_QWORD *)v17 + 2);
    if ( i[25] )
    {
      v19 = a3[1];
      for ( i = (unsigned __int8 *)*((_QWORD *)v17 + 1);
            !i[25] && v19 == *((unsigned __int8 **)i + 2);
            i = (unsigned __int8 *)*((_QWORD *)i + 1) )
      {
        v19 = i;
      }
    }
    else
    {
      for ( j = *(unsigned __int8 **)i; !j[25]; j = *(unsigned __int8 **)j )
        i = j;
    }
    v21 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Extract(v16);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)(v21 + 72),
      *(_BYTE *)(v21 + 64));
    std::string::~string(v21 + 32);
    operator delete((void *)v21);
    a2[1] = i;
  }
  else
  {
    if ( *a1 != 2 )
    {
      if ( *a1 != 3 && *a1 != 4 && *a1 != 5 && *a1 != 6 && (unsigned int)*a1 - 7 > 1 )
      {
        v23 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::type_name(a1);
        v24 = std::string::string(v27, v23);
        v25 = std::operator+<char>(v29, "cannot use erase() with ", v24);
        nlohmann::detail::type_error::create(pExceptionObject, 307, v25);
        throw (nlohmann::detail::type_error *)pExceptionObject;
      }
      if ( a3[3] )
      {
        std::string::string(v27, "iterator out of range");
        nlohmann::detail::invalid_iterator::create(pExceptionObject, 205, v27);
        throw (nlohmann::detail::invalid_iterator *)pExceptionObject;
      }
      if ( v6 == 3 )
      {
        std::string::~string(*((_QWORD *)a1 + 1));
      }
      else
      {
        if ( v6 != 8 )
        {
LABEL_20:
          *a1 = 0;
          return a2;
        }
        std::vector<char>::~vector<char>(*((_QWORD *)a1 + 1));
      }
      operator delete(*((void **)a1 + 1));
      *((_QWORD *)a1 + 1) = 0;
      goto LABEL_20;
    }
    v7 = a3[2];
    v8 = *((_QWORD *)a1 + 1);
    v9 = v7;
    v10 = *(unsigned __int8 **)(v8 + 8);
    for ( k = v7 + 16; k != v10; k += 16 )
    {
      v12 = *k;
      v13 = *((_QWORD *)k + 1);
      *k = 0;
      *((_QWORD *)k + 1) = 0;
      v14 = *v9;
      *v9 = v12;
      v27[0] = v14;
      v15 = (void *)*((_QWORD *)v9 + 1);
      *((_QWORD *)v9 + 1) = v13;
      v28 = v15;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v28,
        v14);
      v9 += 16;
    }
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)(*(_QWORD *)(v8 + 8) - 8LL),
      *(_BYTE *)(*(_QWORD *)(v8 + 8) - 16LL));
    *(_QWORD *)(v8 + 8) -= 16LL;
    a2[2] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x1800169ac  mov     [rsp-8+arg_18], rbx
0x1800169b1  push    rbp
0x1800169b2  push    rsi
0x1800169b3  push    rdi
0x1800169b4  push    r12
0x1800169b6  push    r13
0x1800169b8  push    r14
0x1800169ba  push    r15
0x1800169bc  lea     rbp, [rsp-27h]
0x1800169c1  sub     rsp, 0C0h
0x1800169c8  mov     rax, cs:__security_cookie
0x1800169cf  xor     rax, rsp
0x1800169d2  mov     [rbp+57h+var_40], rax
0x1800169d6  mov     r14, rdx
0x1800169d9  mov     rbx, rcx
0x1800169dc  cmp     rcx, [r8]
0x1800169df  jnz     loc_180016BEA
0x1800169e5  mov     [rdx], rcx
0x1800169e8  xor     r13d, r13d
0x1800169eb  mov     [rdx+8], r13
0x1800169ef  mov     [rdx+10h], r13
0x1800169f3  mov     rax, 8000000000000000h
0x1800169fd  mov     [rdx+18h], rax
0x180016a01  mov     rdx, [rdx]
0x180016a04  movzx   ecx, byte ptr [rdx]
0x180016a07  sub     ecx, 1
0x180016a0a  jz      short loc_180016A29
0x180016a0c  cmp     ecx, 1
0x180016a0f  jz      short loc_180016A1B
0x180016a11  mov     qword ptr [r14+18h], 1
0x180016a19  jmp     short loc_180016A34
0x180016a1b  mov     rax, [rdx+8]
0x180016a1f  mov     rcx, [rax+8]
0x180016a23  mov     [r14+10h], rcx
0x180016a27  jmp     short loc_180016A34
0x180016a29  mov     rax, [rdx+8]
0x180016a2d  mov     rcx, [rax]
0x180016a30  mov     [r14+8], rcx
0x180016a34  movzx   ecx, byte ptr [rbx]
0x180016a37  mov     edx, ecx
0x180016a39  sub     edx, 1
0x180016a3c  jz      loc_180016B13
0x180016a42  sub     edx, 1
0x180016a45  jz      short loc_180016AAB
0x180016a47  sub     edx, 1
0x180016a4a  jz      short loc_180016A69
0x180016a4c  sub     edx, 1
0x180016a4f  jz      short loc_180016A69
0x180016a51  sub     edx, 1
0x180016a54  jz      short loc_180016A69
0x180016a56  sub     edx, 1
0x180016a59  jz      short loc_180016A69
0x180016a5b  sub     edx, 1
0x180016a5e  jz      short loc_180016A69
0x180016a60  cmp     edx, 1
0x180016a63  jnz     loc_180016C1E
0x180016a69  cmp     [r8+18h], r13
0x180016a6d  jnz     loc_180016BB6
0x180016a73  cmp     cl, 3
0x180016a76  jnz     short loc_180016A83
0x180016a78  mov     rcx, [rbx+8]
0x180016a7c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016a81  jmp     short loc_180016A91
0x180016a83  cmp     cl, 8
0x180016a86  jnz     short loc_180016AA3
0x180016a88  mov     rcx, [rbx+8]
0x180016a8c  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180016a91  mov     edx, 20h ; ' '; unsigned __int64
0x180016a96  mov     rcx, [rbx+8]; void *
0x180016a9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016a9f  mov     [rbx+8], r13
0x180016aa3  mov     [rbx], r13b
0x180016aa6  jmp     loc_180016B8C
0x180016aab  mov     rsi, [r8+10h]
0x180016aaf  mov     rbx, [rbx+8]
0x180016ab3  mov     r15, rsi
0x180016ab6  mov     r12, [rbx+8]
0x180016aba  lea     rdi, [rsi+10h]
0x180016abe  jmp     short loc_180016AF3
0x180016ac0  mov     al, [rdi]
0x180016ac2  mov     rcx, [rdi+8]
0x180016ac6  mov     [rdi], r13b
0x180016ac9  mov     [rdi+8], r13
0x180016acd  mov     dl, [r15]
0x180016ad0  mov     [r15], al
0x180016ad3  mov     [rbp+57h+var_98], dl
0x180016ad6  mov     rax, [r15+8]
0x180016ada  mov     [r15+8], rcx
0x180016ade  mov     [rbp+57h+var_90], rax
0x180016ae2  lea     rcx, [rbp+57h+var_90]
0x180016ae6  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180016aeb  lea     r15, [r15+10h]
0x180016aef  add     rdi, 10h
0x180016af3  cmp     rdi, r12
0x180016af6  jnz     short loc_180016AC0
0x180016af8  mov     rdx, [rbx+8]
0x180016afc  lea     rcx, [rdx-8]
0x180016b00  mov     dl, [rdx-10h]
0x180016b03  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180016b08  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFF0h
0x180016b0d  mov     [r14+10h], rsi
0x180016b11  jmp     short loc_180016B8C
0x180016b13  mov     r9, [rbx+8]
0x180016b17  mov     rdx, [r8+8]
0x180016b1b  mov     rbx, [rdx+10h]
0x180016b1f  cmp     [rbx+19h], r13b
0x180016b23  jz      short loc_180016B43
0x180016b25  mov     rax, rdx
0x180016b28  mov     rbx, [rdx+8]
0x180016b2c  jmp     short loc_180016B3B
0x180016b2e  cmp     rax, [rbx+10h]
0x180016b32  jnz     short loc_180016B5B
0x180016b34  mov     rax, rbx
0x180016b37  mov     rbx, [rbx+8]
0x180016b3b  cmp     [rbx+19h], r13b
0x180016b3f  jz      short loc_180016B2E
0x180016b41  jmp     short loc_180016B5B
0x180016b43  mov     rcx, [rbx]
0x180016b46  cmp     [rcx+19h], r13b
0x180016b4a  jnz     short loc_180016B5B
0x180016b4c  mov     rbx, rcx
0x180016b4f  mov     rax, [rcx]
0x180016b52  mov     rcx, rax
0x180016b55  cmp     [rax+19h], r13b
0x180016b59  jz      short loc_180016B4C
0x180016b5b  mov     rcx, r9
0x180016b5e  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>,std::_Iterator_base0>)
0x180016b63  mov     rsi, rax
0x180016b66  lea     rcx, [rax+48h]
0x180016b6a  mov     dl, [rax+40h]
0x180016b6d  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180016b72  lea     rcx, [rsi+20h]
0x180016b76  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016b7b  mov     edx, 50h ; 'P'; unsigned __int64
0x180016b80  mov     rcx, rsi; void *
0x180016b83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b88  mov     [r14+8], rbx
0x180016b8c  mov     rax, r14
0x180016b8f  mov     rcx, [rbp+57h+var_40]
0x180016b93  xor     rcx, rsp; StackCookie
0x180016b96  call    __security_check_cookie
0x180016b9b  mov     rbx, [rsp+0F0h+arg_18]
0x180016ba3  add     rsp, 0C0h
0x180016baa  pop     r15
0x180016bac  pop     r14
0x180016bae  pop     r13
0x180016bb0  pop     r12
0x180016bb2  pop     rdi
0x180016bb3  pop     rsi
0x180016bb4  pop     rbp
0x180016bb5  retn
0x180016bb6  lea     rdx, aIteratorOutOfR; "iterator out of range"
0x180016bbd  lea     rcx, [rbp+57h+var_98]
0x180016bc1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016bc6  nop
0x180016bc7  lea     r8, [rbp+57h+var_98]
0x180016bcb  mov     edx, 0CDh
0x180016bd0  lea     rcx, [rbp+57h+pExceptionObject]
0x180016bd4  call    ?create@invalid_iterator@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::invalid_iterator::create(int,std::string const &)
0x180016bd9  lea     rdx, _TI3?AVinvalid_iterator@detail@nlohmann@@; pThrowInfo
0x180016be0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180016be4  call    _CxxThrowException_0
0x180016bea  lea     rdx, aIteratorDoesNo; "iterator does not fit current value"
0x180016bf1  lea     rcx, [rbp+57h+var_98]
0x180016bf5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016bfa  nop
0x180016bfb  lea     r8, [rbp+57h+var_98]
0x180016bff  mov     edx, 0CAh
0x180016c04  lea     rcx, [rbp+57h+var_78]
0x180016c08  call    ?create@invalid_iterator@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::invalid_iterator::create(int,std::string const &)
0x180016c0d  lea     rdx, _TI3?AVinvalid_iterator@detail@nlohmann@@; pThrowInfo
0x180016c14  lea     rcx, [rbp+57h+var_78]; pExceptionObject
0x180016c18  call    _CxxThrowException_0
0x180016c1e  mov     rcx, rbx
0x180016c21  call    ?type_name@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBAPEBDXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::type_name(void)
0x180016c26  mov     rdx, rax
0x180016c29  lea     rcx, [rbp+57h+var_98]
0x180016c2d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016c32  nop
0x180016c33  mov     r8, rax
0x180016c36  lea     rdx, aCannotUseErase; "cannot use erase() with "
0x180016c3d  lea     rcx, [rbp+57h+var_78]
0x180016c41  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180016c46  nop
0x180016c47  mov     r8, rax
0x180016c4a  mov     edx, 133h
0x180016c4f  lea     rcx, [rbp+57h+pExceptionObject]
0x180016c53  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180016c58  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180016c5f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180016c63  call    _CxxThrowException_0
```
