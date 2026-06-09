# PolicyFileParser::validatePolicies(web::json::value)

- ea: `0x14003adc4`
- end: `0x14003b254`
- name: `?validatePolicies@PolicyFileParser@@YAXVvalue@json@web@@@Z`
- size: `1168`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config`

## callers

- `0x14002595c`

## callees

- `0x140002f60`
- `0x140002f84`
- `0x140003244`
- `0x140003b64`
- `0x1400064d0`
- `0x140006a30`
- `0x140007630`
- `0x140008500`
- `0x14000dd20`
- `0x140013df8`
- `0x140022f0c`
- `0x14002ef10`
- `0x140036830`
- `0x1400374d0`
- `0x1400375d8`
- `0x1400377fc`
- `0x14003796c`
- `0x1400384a0`
- `0x1400385b0`
- `0x14003adc4`
- `0x14003b424`
- `0x14003b63c`
- `0x14003e010`

## pseudocode

```c
void __fastcall PolicyFileParser::validatePolicies(_QWORD *a1)
{
  char v2; // bl
  const struct web::json::value *v3; // rax
  unsigned int v4; // esi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  const struct web::json::value *v7; // rax
  __int64 v8; // rax
  __int64 v9; // r14
  const wchar_t *v10; // rdx
  size_t v11; // rbx
  size_t v12; // rdi
  const wchar_t *v13; // rcx
  size_t v14; // r8
  int v15; // eax
  char v16; // al
  __int64 v17; // rax
  _QWORD *v18; // rcx
  _BYTE *v19; // rdx
  void *v20; // rcx
  _QWORD *v21; // rbx
  void *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  const wchar_t *v27; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+28h] [rbp-D8h]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  char v35[8]; // [rsp+78h] [rbp-88h] BYREF
  char v36[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v37; // [rsp+88h] [rbp-78h]
  char v38[16]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *S1[2]; // [rsp+A0h] [rbp-60h] BYREF
  size_t v40; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v41; // [rsp+B8h] [rbp-48h]
  _BYTE Src[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+F8h] [rbp-8h] BYREF

  v37 = a1;
  *(_OWORD *)S1 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S1, L"policies");
  v2 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(*(_QWORD *)*a1 + 8LL))(*a1, S1);
  std::wstring::_Tidy_deallocate(S1);
  if ( !v2 )
  {
    v27 = L"Missing required field \"{}\"";
    v28 = 27;
    v25 = std::format<unsigned short const (&)[9]>(S1);
    PolicyFileParser::ParsingException::ParsingException(Src, v25);
    throw (PolicyFileParser::ParsingException *)Src;
  }
  *(_OWORD *)S1 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S1, L"policies");
  v3 = (const struct web::json::value *)web::json::value::at(a1, S1);
  web::json::value::value((web::json::value *)&v31, v3);
  std::wstring::_Tidy_deallocate(S1);
  if ( (unsigned int)web::json::value::type(&v31) != 4 )
  {
    v27 = L"Field \"{}\" does not have type Array";
    v28 = 35;
    v24 = std::format<unsigned short const (&)[9]>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v24);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  v4 = 0;
  Block[0] = 0;
  Block[1] = 0;
  v5 = operator new(0x20u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  Block[0] = v5;
  v34[0] = 0;
  v34[1] = 0;
  v6 = operator new(0x40u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  v34[0] = v6;
  while ( v4 < (unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 184LL))(v31) )
  {
    v7 = (const struct web::json::value *)web::json::value::operator[](&v31, v4);
    web::json::value::value((web::json::value *)&v33, v7);
    *(_OWORD *)S1 = 0;
    v40 = 0;
    v41 = 7;
    LOWORD(S1[0]) = 0;
    v8 = web::json::value::value((web::json::value *)v35, (const struct web::json::value *)&v33);
    PolicyFileParser::validateProfileId(v8, S1);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      v34,
      &v27,
      S1);
    v9 = v29;
    if ( *(_BYTE *)(v29 + 25) )
      goto LABEL_21;
    v10 = (const wchar_t *)(v29 + 32);
    v11 = *(_QWORD *)(v29 + 48);
    if ( *(_QWORD *)(v29 + 56) > 7u )
      v10 = *(const wchar_t **)v10;
    v12 = v40;
    v13 = (const wchar_t *)S1;
    if ( v41 > 7 )
      v13 = S1[0];
    v14 = v40;
    if ( v11 < v40 )
      v14 = *(_QWORD *)(v29 + 48);
    v15 = wmemcmp(v13, v10, v14);
    if ( v15 )
    {
      if ( v15 >= 0 )
LABEL_18:
        v16 = 1;
      else
LABEL_16:
        v16 = -1;
      if ( v16 < 0 )
        goto LABEL_21;
      goto LABEL_20;
    }
    if ( v12 < v11 )
      goto LABEL_16;
    if ( v12 > v11 )
      goto LABEL_18;
LABEL_20:
    if ( v9 != v34[0] )
    {
      v27 = L"Multiple policies have the same \"{}\". This is not allowed";
      v28 = 57;
      v26 = std::format<unsigned short const (&)[10]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v26);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
LABEL_21:
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
      v34,
      v38,
      S1);
    v30 = 0;
    v17 = web::json::value::value((web::json::value *)v36, (const struct web::json::value *)&v33);
    PolicyFileParser::validatePriority(v17, &v30);
    v18 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    HIDWORD(v28) = 0;
    v19 = Block[0];
    while ( !*((_BYTE *)v18 + 25) )
    {
      if ( *((_DWORD *)v18 + 7) >= v30 )
      {
        v19 = v18;
        v18 = (_QWORD *)*v18;
      }
      else
      {
        v18 = (_QWORD *)v18[2];
      }
    }
    if ( !v19[25] && v30 >= *((_DWORD *)v19 + 7) && v19 != Block[0] )
    {
      v27 = L"Multiple policies have the same \"{}\". This is not allowed";
      v28 = 57;
      v23 = std::format<unsigned short const (&)[9]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v23);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    std::_Tree<std::_Tset_traits<int,std::less<int>,std::allocator<int>,0>>::emplace<int &>(Block, Src, &v30);
    std::wstring::_Tidy_deallocate(S1);
    if ( v33 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 192LL))(v33, 1);
    ++v4;
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v34);
  v20 = Block[0];
  v21 = (_QWORD *)*((_QWORD *)Block[0] + 1);
  if ( !*((_BYTE *)v21 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<int>>::_Erase_tree<std::allocator<std::_Tree_node<int,void *>>>(
        Block,
        Block,
        v21[2]);
      v22 = v21;
      v21 = (_QWORD *)*v21;
      operator delete(v22);
    }
    while ( !*((_BYTE *)v21 + 25) );
    v20 = Block[0];
  }
  operator delete(v20);
  if ( v31 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 192LL))(v31, 1);
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
}

```

## disassembly

```asm
0x14003adc4  mov     [rsp-8+arg_8], rbx
0x14003adc9  mov     [rsp-8+arg_10], rsi
0x14003adce  push    rbp
0x14003adcf  push    rdi
0x14003add0  push    r12
0x14003add2  push    r14
0x14003add4  push    r15
0x14003add6  lea     rbp, [rsp-40h]
0x14003addb  sub     rsp, 140h
0x14003ade2  mov     rax, cs:__security_cookie
0x14003ade9  xor     rax, rsp
0x14003adec  mov     [rbp+60h+var_30], rax
0x14003adf0  mov     r15, rcx
0x14003adf3  mov     [rbp+60h+var_D8], rcx
0x14003adf7  xorps   xmm0, xmm0
0x14003adfa  movups  xmmword ptr [rbp+60h+S1], xmm0
0x14003adfe  xor     r12d, r12d
0x14003ae01  mov     [rbp+60h+var_B0], r12
0x14003ae05  mov     [rbp+60h+var_A8], r12
0x14003ae09  lea     esi, [r12+8]
0x14003ae0e  mov     r8d, esi
0x14003ae11  lea     rdi, aPolicies; "policies"
0x14003ae18  mov     rdx, rdi
0x14003ae1b  lea     rcx, [rbp+60h+S1]
0x14003ae1f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003ae24  nop
0x14003ae25  mov     rcx, [r15]
0x14003ae28  mov     rax, [rcx]
0x14003ae2b  lea     rdx, [rbp+60h+S1]
0x14003ae2f  mov     rax, [rax+8]
0x14003ae33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae38  mov     bl, al
0x14003ae3a  lea     rcx, [rbp+60h+S1]
0x14003ae3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003ae43  lea     rcx, [rbp+60h+S1]; Src
0x14003ae47  test    bl, bl
0x14003ae49  jz      loc_14003B1D3
0x14003ae4f  xorps   xmm0, xmm0
0x14003ae52  movups  xmmword ptr [rbp+60h+S1], xmm0
0x14003ae56  mov     [rbp+60h+var_B0], r12
0x14003ae5a  mov     [rbp+60h+var_A8], r12
0x14003ae5e  mov     r8d, esi
0x14003ae61  mov     rdx, rdi
0x14003ae64  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003ae69  nop
0x14003ae6a  lea     rdx, [rbp+60h+S1]
0x14003ae6e  mov     rcx, r15
0x14003ae71  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003ae76  mov     rdx, rax; struct web::json::value *
0x14003ae79  lea     rcx, [rsp+160h+var_118]; this
0x14003ae7e  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003ae83  nop
0x14003ae84  lea     rcx, [rbp+60h+S1]
0x14003ae88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003ae8d  lea     rcx, [rsp+160h+var_118]
0x14003ae92  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x14003ae97  cmp     eax, 4
0x14003ae9a  jnz     loc_14003B18F
0x14003aea0  mov     esi, r12d
0x14003aea3  mov     [rsp+160h+Block], r12
0x14003aea8  mov     [rsp+160h+var_108], r12
0x14003aead  lea     ecx, [rax+1Ch]; Size
0x14003aeb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003aeb5  mov     [rax], rax
0x14003aeb8  mov     [rax+8], rax
0x14003aebc  mov     [rax+10h], rax
0x14003aec0  mov     word ptr [rax+18h], 101h
0x14003aec6  mov     [rsp+160h+Block], rax
0x14003aecb  mov     [rsp+160h+var_F8], r12
0x14003aed0  mov     [rsp+160h+var_F0], r12
0x14003aed5  lea     ecx, [r12+40h]; Size
0x14003aeda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003aedf  mov     [rax], rax
0x14003aee2  mov     [rax+8], rax
0x14003aee6  mov     [rax+10h], rax
0x14003aeea  mov     word ptr [rax+18h], 101h
0x14003aef0  mov     [rsp+160h+var_F8], rax
0x14003aef5  mov     rcx, [rsp+160h+var_118]
0x14003aefa  mov     ebx, esi
0x14003aefc  mov     rax, [rcx]
0x14003aeff  mov     rax, [rax+0B8h]
0x14003af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003af0b  cmp     rbx, rax
0x14003af0e  jnb     loc_14003B091
0x14003af14  mov     edx, ebx
0x14003af16  lea     rcx, [rsp+160h+var_118]
0x14003af1b  call    ??Avalue@json@web@@QEAAAEAV012@_K@Z; web::json::value::operator[](unsigned __int64)
0x14003af20  mov     rdx, rax; struct web::json::value *
0x14003af23  lea     rcx, [rsp+160h+var_100]; this
0x14003af28  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003af2d  nop
0x14003af2e  xorps   xmm0, xmm0
0x14003af31  movups  xmmword ptr [rbp+60h+S1], xmm0
0x14003af35  mov     [rbp+60h+var_B0], r12
0x14003af39  mov     [rbp+60h+var_A8], 7
0x14003af41  mov     word ptr [rbp+60h+S1], r12w
0x14003af46  lea     rdx, [rsp+160h+var_100]; struct web::json::value *
0x14003af4b  lea     rcx, [rsp+160h+var_E8]; this
0x14003af50  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003af55  lea     rdx, [rbp+60h+S1]
0x14003af59  mov     rcx, rax
0x14003af5c  call    ?validateProfileId@PolicyFileParser@@YAXVvalue@json@web@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::validateProfileId(web::json::value,std::wstring &)
0x14003af61  lea     r8, [rbp+60h+S1]
0x14003af65  lea     rdx, [rsp+160h+var_140]
0x14003af6a  lea     rcx, [rsp+160h+var_F8]
0x14003af6f  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14003af74  mov     r14, [rsp+160h+var_130]
0x14003af79  cmp     [r14+19h], r12b
0x14003af7d  jnz     short loc_14003AFD6
0x14003af7f  lea     rdx, [r14+20h]
0x14003af83  mov     rbx, [rdx+10h]
0x14003af87  cmp     qword ptr [rdx+18h], 7
0x14003af8c  jbe     short loc_14003AF91
0x14003af8e  mov     rdx, [rdx]; S2
0x14003af91  mov     rdi, [rbp+60h+var_B0]
0x14003af95  lea     rcx, [rbp+60h+S1]
0x14003af99  cmp     [rbp+60h+var_A8], 7
0x14003af9e  cmova   rcx, [rbp+60h+S1]; S1
0x14003afa3  mov     r8, rdi
0x14003afa6  cmp     rbx, rdi
0x14003afa9  cmovb   r8, rbx; N
0x14003afad  call    wmemcmp
0x14003afb2  test    eax, eax
0x14003afb4  jz      short loc_14003AFBA
0x14003afb6  jns     short loc_14003AFC5
0x14003afb8  jmp     short loc_14003AFBF
0x14003afba  cmp     rdi, rbx
0x14003afbd  jnb     short loc_14003AFC3
0x14003afbf  mov     al, 0FFh
0x14003afc1  jmp     short loc_14003AFC7
0x14003afc3  jbe     short loc_14003AFCB
0x14003afc5  mov     al, 1
0x14003afc7  test    al, al
0x14003afc9  js      short loc_14003AFD6
0x14003afcb  cmp     r14, [rsp+160h+var_F8]
0x14003afd0  jnz     loc_14003B213
0x14003afd6  lea     r8, [rbp+60h+S1]
0x14003afda  lea     rdx, [rbp+60h+var_D0]
0x14003afde  lea     rcx, [rsp+160h+var_F8]
0x14003afe3  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x14003afe8  mov     [rsp+160h+var_120], r12d
0x14003afed  lea     rdx, [rsp+160h+var_100]; struct web::json::value *
0x14003aff2  lea     rcx, [rbp+60h+var_E0]; this
0x14003aff6  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003affb  lea     rdx, [rsp+160h+var_120]
0x14003b000  mov     rcx, rax
0x14003b003  call    ?validatePriority@PolicyFileParser@@YAXVvalue@json@web@@AEAH@Z; PolicyFileParser::validatePriority(web::json::value,int &)
0x14003b008  mov     rax, [rsp+160h+Block]
0x14003b00d  mov     rcx, [rax+8]
0x14003b011  xor     edx, edx
0x14003b013  mov     [rsp+160h+var_134], edx
0x14003b017  mov     rdx, rax
0x14003b01a  mov     r8d, [rsp+160h+var_120]
0x14003b01f  jmp     short loc_14003B033
0x14003b021  cmp     [rcx+1Ch], r8d
0x14003b025  jge     short loc_14003B02D
0x14003b027  mov     rcx, [rcx+10h]
0x14003b02b  jmp     short loc_14003B033
0x14003b02d  mov     rdx, rcx
0x14003b030  mov     rcx, [rcx]
0x14003b033  cmp     [rcx+19h], r12b
0x14003b037  jz      short loc_14003B021
0x14003b039  cmp     [rdx+19h], r12b
0x14003b03d  jnz     short loc_14003B04E
0x14003b03f  cmp     r8d, [rdx+1Ch]
0x14003b043  jl      short loc_14003B04E
0x14003b045  cmp     rdx, rax
0x14003b048  jnz     loc_14003B147
0x14003b04e  lea     r8, [rsp+160h+var_120]
0x14003b053  lea     rdx, [rbp+60h+Src]
0x14003b057  lea     rcx, [rsp+160h+Block]
0x14003b05c  call    ??$emplace@AEAH@?$_Tree@V?$_Tset_traits@HU?$less@H@std@@V?$allocator@H@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@H@std@@@std@@@std@@_N@1@AEAH@Z; std::_Tree<std::_Tset_traits<int,std::less<int>,std::allocator<int>,0>>::emplace<int &>(int &)
0x14003b061  nop
0x14003b062  lea     rcx, [rbp+60h+S1]
0x14003b066  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b06b  nop
0x14003b06c  mov     rcx, [rsp+160h+var_100]
0x14003b071  test    rcx, rcx
0x14003b074  jz      short loc_14003B08A
0x14003b076  mov     rax, [rcx]
0x14003b079  mov     edx, 1
0x14003b07e  mov     rax, [rax+0C0h]
0x14003b085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b08a  inc     esi
0x14003b08c  jmp     loc_14003AEF5
0x14003b091  lea     rcx, [rsp+160h+var_F8]
0x14003b096  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x14003b09b  nop
0x14003b09c  mov     rcx, [rsp+160h+Block]
0x14003b0a1  mov     rbx, [rcx+8]
0x14003b0a5  cmp     [rbx+19h], r12b
0x14003b0a9  jnz     short loc_14003B0D9
0x14003b0ab  mov     r8, [rbx+10h]
0x14003b0af  lea     rdx, [rsp+160h+Block]
0x14003b0b4  lea     rcx, [rsp+160h+Block]
0x14003b0b9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@HPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@H@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@HPEAX@std@@@1@PEAU?$_Tree_node@HPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<int>>::_Erase_tree<std::allocator<std::_Tree_node<int,void *>>>(std::allocator<std::_Tree_node<int,void *>> &,std::_Tree_node<int,void *> *)
0x14003b0be  mov     rcx, rbx; Block
0x14003b0c1  mov     rbx, [rbx]
0x14003b0c4  mov     edx, 20h ; ' '
0x14003b0c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003b0ce  cmp     [rbx+19h], r12b
0x14003b0d2  jz      short loc_14003B0AB
0x14003b0d4  mov     rcx, [rsp+160h+Block]; Block
0x14003b0d9  mov     edx, 20h ; ' '
0x14003b0de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003b0e3  nop
0x14003b0e4  mov     rcx, [rsp+160h+var_118]
0x14003b0e9  test    rcx, rcx
0x14003b0ec  jz      short loc_14003B103
0x14003b0ee  mov     rax, [rcx]
0x14003b0f1  mov     edx, 1
0x14003b0f6  mov     rax, [rax+0C0h]
0x14003b0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b102  nop
0x14003b103  mov     rcx, [r15]
0x14003b106  test    rcx, rcx
0x14003b109  jz      short loc_14003B11F
0x14003b10b  mov     rax, [rcx]
0x14003b10e  mov     edx, 1
0x14003b113  mov     rax, [rax+0C0h]
0x14003b11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b11f  mov     rcx, [rbp+60h+var_30]
0x14003b123  xor     rcx, rsp; StackCookie
0x14003b126  call    __security_check_cookie
0x14003b12b  lea     r11, [rsp+160h+var_20]
0x14003b133  mov     rbx, [r11+38h]
0x14003b137  mov     rsi, [r11+40h]
0x14003b13b  mov     rsp, r11
0x14003b13e  pop     r15
0x14003b140  pop     r14
0x14003b142  pop     r12
0x14003b144  pop     rdi
0x14003b145  pop     rbp
0x14003b146  retn
0x14003b147  lea     rax, aMultiplePolici; "Multiple policies have the same \"{}\"."...
0x14003b14e  mov     [rsp+160h+var_140], rax
0x14003b153  mov     qword ptr [rsp+28h], 39h ; '9'
0x14003b15c  lea     r8, aPriority; "priority"
0x14003b163  lea     rdx, [rsp+160h+var_140]
0x14003b168  lea     rcx, [rbp+60h+Src]; Src
0x14003b16c  call    ??$format@AEAY08$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBG@0@AEAY08$$CBG@Z; std::format<ushort const (&)[9]>(std::basic_format_string<ushort,ushort const (&)[9]>,ushort const (&)[9])
0x14003b171  nop
0x14003b172  mov     rdx, rax
0x14003b175  lea     rcx, [rbp+60h+pExceptionObject]
0x14003b179  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b17e  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b185  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x14003b189  call    _CxxThrowException_0
0x14003b18f  lea     rax, aFieldDoesNotHa_1; "Field \"{}\" does not have type Array"
0x14003b196  mov     [rsp+160h+var_140], rax
0x14003b19b  mov     qword ptr [rsp+28h], 23h ; '#'
0x14003b1a4  mov     r8, rdi
0x14003b1a7  lea     rdx, [rsp+160h+var_140]
0x14003b1ac  lea     rcx, [rbp+60h+Src]; Src
0x14003b1b0  call    ??$format@AEAY08$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBG@0@AEAY08$$CBG@Z; std::format<ushort const (&)[9]>(std::basic_format_string<ushort,ushort const (&)[9]>,ushort const (&)[9])
0x14003b1b5  nop
0x14003b1b6  mov     rdx, rax
0x14003b1b9  lea     rcx, [rbp+60h+pExceptionObject]
0x14003b1bd  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b1c2  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b1c9  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x14003b1cd  call    _CxxThrowException_0
0x14003b1d3  lea     rax, aMissingRequire; "Missing required field \"{}\""
0x14003b1da  mov     [rsp+160h+var_140], rax
0x14003b1df  mov     qword ptr [rsp+28h], 1Bh
0x14003b1e8  mov     r8, rdi
0x14003b1eb  lea     rdx, [rsp+160h+var_140]
0x14003b1f0  call    ??$format@AEAY08$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBG@0@AEAY08$$CBG@Z; std::format<ushort const (&)[9]>(std::basic_format_string<ushort,ushort const (&)[9]>,ushort const (&)[9])
0x14003b1f5  nop
0x14003b1f6  mov     rdx, rax
0x14003b1f9  lea     rcx, [rbp+60h+Src]
0x14003b1fd  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b202  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b209  lea     rcx, [rbp+60h+Src]; pExceptionObject
0x14003b20d  call    _CxxThrowException_0
0x14003b213  lea     rax, aMultiplePolici; "Multiple policies have the same \"{}\"."...
0x14003b21a  mov     [rsp+160h+var_140], rax
0x14003b21f  mov     qword ptr [rsp+28h], 39h ; '9'
0x14003b228  lea     rdx, [rsp+160h+var_140]
0x14003b22d  lea     rcx, [rbp+60h+Src]; Src
0x14003b231  call    ??$format@AEAY09$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY09$$CBG@0@AEAY09$$CBG@Z; std::format<ushort const (&)[10]>(std::basic_format_string<ushort,ushort const (&)[10]>,ushort const (&)[10])
0x14003b236  nop
0x14003b237  mov     rdx, rax
0x14003b23a  lea     rcx, [rbp+60h+pExceptionObject]
0x14003b23e  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b243  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b24a  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x14003b24e  call    _CxxThrowException_0
```
