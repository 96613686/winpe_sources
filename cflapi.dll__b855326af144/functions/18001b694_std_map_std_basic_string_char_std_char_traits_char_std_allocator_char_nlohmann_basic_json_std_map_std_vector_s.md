# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::less<void>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>>::operator[](std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001b694`
- end: `0x18001b796`
- name: `??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@QEAAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018df4`
- `0x1800250a0`

## callees

- `0x18000289c`
- `0x180015408`
- `0x180019eac`
- `0x18001a674`
- `0x18001b694`
- `0x180021d98`
- `0x1800222c4`
- `0x18002dff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::operator[](
        __int64 *a1,
        size_t *a2)
{
  __int64 inserted; // rbx
  _QWORD *v5; // rdx
  size_t v6; // rdi
  const void *v7; // rcx
  size_t v8; // r8
  int v9; // eax
  __int64 v10; // rsi
  _BYTE *v11; // rdi
  __int128 v13; // [rsp+20h] [rbp-58h] BYREF
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]

  std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>,0>>::_Find_lower_bound<std::string>(
    a1,
    &v14,
    a2);
  inserted = v15;
  if ( !*(_BYTE *)(v15 + 25) )
  {
    v5 = (_QWORD *)(v15 + 32);
    v6 = *(_QWORD *)(v15 + 48);
    if ( *(_QWORD *)(v15 + 56) > 0xFu )
      v5 = (_QWORD *)*v5;
    if ( a2[3] <= 0xF )
      v7 = a2;
    else
      v7 = (const void *)*a2;
    v8 = a2[2];
    if ( v6 < v8 )
      v8 = *(_QWORD *)(v15 + 48);
    v9 = memcmp_0(v7, v5, v8);
    if ( v9 )
    {
      if ( v9 >= 0 )
        return inserted + 64;
    }
    else if ( a2[2] >= v6 )
    {
      return inserted + 64;
    }
  }
  if ( a1[1] == 0x333333333333333LL )
    std::_Throw_tree_length_error();
  v10 = *a1;
  v11 = operator new(0x50u);
  std::string::string(v11 + 32, a2);
  v11[64] = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
    (_QWORD *)v11 + 9,
    0);
  *(_QWORD *)v11 = v10;
  *((_QWORD *)v11 + 1) = v10;
  *((_QWORD *)v11 + 2) = v10;
  *((_WORD *)v11 + 12) = 0;
  v13 = v14;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Insert_node(
               a1,
               &v13,
               v11);
  return inserted + 64;
}

```

## disassembly

```asm
0x18001b694  push    rbx
0x18001b696  push    rsi
0x18001b697  push    rdi
0x18001b698  push    r14
0x18001b69a  push    r15
0x18001b69c  sub     rsp, 50h
0x18001b6a0  mov     r14, rdx
0x18001b6a3  mov     r15, rcx
0x18001b6a6  mov     r8, rdx
0x18001b6a9  lea     rdx, [rsp+78h+var_48]
0x18001b6ae  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18001b6b3  mov     rbx, [rsp+78h+var_38]
0x18001b6b8  cmp     byte ptr [rbx+19h], 0
0x18001b6bc  jnz     short loc_18001B701
0x18001b6be  lea     rdx, [rbx+20h]
0x18001b6c2  mov     rdi, [rdx+10h]
0x18001b6c6  cmp     qword ptr [rdx+18h], 0Fh
0x18001b6cb  jbe     short loc_18001B6D0
0x18001b6cd  mov     rdx, [rdx]; Buf2
0x18001b6d0  cmp     qword ptr [r14+18h], 0Fh
0x18001b6d5  jbe     short loc_18001B6DC
0x18001b6d7  mov     rcx, [r14]
0x18001b6da  jmp     short loc_18001B6DF
0x18001b6dc  mov     rcx, r14; Buf1
0x18001b6df  mov     r8, [r14+10h]
0x18001b6e3  cmp     rdi, r8
0x18001b6e6  cmovb   r8, rdi; Size
0x18001b6ea  call    memcmp_0
0x18001b6ef  test    eax, eax
0x18001b6f1  jnz     short loc_18001B6FF
0x18001b6f3  cmp     [r14+10h], rdi
0x18001b6f7  jnb     loc_18001B780
0x18001b6fd  jmp     short loc_18001B701
0x18001b6ff  jns     short loc_18001B780
0x18001b701  mov     rax, 333333333333333h
0x18001b70b  cmp     [r15+8], rax
0x18001b70f  jz      short loc_18001B790
0x18001b711  mov     rsi, [r15]
0x18001b714  mov     qword ptr [rsp+78h+var_58], r15
0x18001b719  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001b722  mov     ecx, 50h ; 'P'; Size
0x18001b727  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b72c  mov     rdi, rax
0x18001b72f  mov     qword ptr [rsp+78h+var_58+8], rax
0x18001b734  mov     rdx, r14
0x18001b737  lea     rcx, [rax+20h]
0x18001b73b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001b740  nop
0x18001b741  mov     byte ptr [rdi+40h], 0
0x18001b745  lea     rcx, [rdi+48h]
0x18001b749  xor     edx, edx
0x18001b74b  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18001b750  nop
0x18001b751  mov     [rdi], rsi
0x18001b754  mov     [rdi+8], rsi
0x18001b758  mov     [rdi+10h], rsi
0x18001b75c  mov     word ptr [rdi+18h], 0
0x18001b762  movups  xmm0, [rsp+78h+var_48]
0x18001b767  movdqu  [rsp+78h+var_58], xmm0
0x18001b76d  mov     r8, rdi
0x18001b770  lea     rdx, [rsp+78h+var_58]
0x18001b775  mov     rcx, r15
0x18001b778  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> *>,std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> * const)
0x18001b77d  mov     rbx, rax
0x18001b780  lea     rax, [rbx+40h]
0x18001b784  add     rsp, 50h
0x18001b788  pop     r15
0x18001b78a  pop     r14
0x18001b78c  pop     rdi
0x18001b78d  pop     rsi
0x18001b78e  pop     rbx
0x18001b78f  retn
0x18001b790  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
