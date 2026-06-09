# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::less<void>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>>::operator[](std::basic_string<char,std::char_traits<char>,std::allocator<char>> &&)

- ea: `0x18001b560`
- end: `0x18001b68d`
- name: `??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@QEAAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180012cec`

## callees

- `0x18000289c`
- `0x180015408`
- `0x18001a674`
- `0x18001b560`
- `0x180021d98`
- `0x1800222c4`
- `0x18002dff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v10; // rdi
  _OWORD *v11; // rbx
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
  v13 = (unsigned __int64)a1;
  v11 = operator new(0x50u);
  v11[2] = 0;
  *((_QWORD *)v11 + 6) = 0;
  *((_QWORD *)v11 + 7) = 0;
  v11[2] = *(_OWORD *)a2;
  v11[3] = *((_OWORD *)a2 + 1);
  a2[2] = 0;
  a2[3] = 15;
  *(_BYTE *)a2 = 0;
  *((_BYTE *)v11 + 64) = 0;
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
0x18001b560  push    rbx
0x18001b562  push    rsi
0x18001b563  push    rdi
0x18001b564  push    r14
0x18001b566  sub     rsp, 58h
0x18001b56a  mov     rsi, rdx
0x18001b56d  mov     r14, rcx
0x18001b570  mov     r8, rdx
0x18001b573  lea     rdx, [rsp+78h+var_48]
0x18001b578  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18001b57d  mov     rbx, [rsp+78h+var_38]
0x18001b582  cmp     byte ptr [rbx+19h], 0
0x18001b586  jnz     short loc_18001B5CF
0x18001b588  lea     rdx, [rbx+20h]
0x18001b58c  mov     rdi, [rdx+10h]
0x18001b590  cmp     qword ptr [rdx+18h], 0Fh
0x18001b595  jbe     short loc_18001B59A
0x18001b597  mov     rdx, [rdx]; Buf2
0x18001b59a  cmp     qword ptr [rsi+18h], 0Fh
0x18001b59f  jbe     short loc_18001B5A6
0x18001b5a1  mov     rcx, [rsi]
0x18001b5a4  jmp     short loc_18001B5A9
0x18001b5a6  mov     rcx, rsi; Buf1
0x18001b5a9  mov     r8, [rsi+10h]
0x18001b5ad  cmp     rdi, r8
0x18001b5b0  cmovb   r8, rdi; Size
0x18001b5b4  call    memcmp_0
0x18001b5b9  test    eax, eax
0x18001b5bb  jnz     short loc_18001B5C9
0x18001b5bd  cmp     [rsi+10h], rdi
0x18001b5c1  jnb     loc_18001B679
0x18001b5c7  jmp     short loc_18001B5CF
0x18001b5c9  jns     loc_18001B679
0x18001b5cf  mov     rax, 333333333333333h
0x18001b5d9  cmp     [r14+8], rax
0x18001b5dd  jz      loc_18001B687
0x18001b5e3  mov     rdi, [r14]
0x18001b5e6  mov     qword ptr [rsp+78h+var_58], r14
0x18001b5eb  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001b5f4  mov     ecx, 50h ; 'P'; Size
0x18001b5f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b5fe  mov     rbx, rax
0x18001b601  xorps   xmm0, xmm0
0x18001b604  movups  xmmword ptr [rax+20h], xmm0
0x18001b608  mov     qword ptr [rax+30h], 0
0x18001b610  mov     qword ptr [rax+38h], 0
0x18001b618  movups  xmm0, xmmword ptr [rsi]
0x18001b61b  movups  xmmword ptr [rax+20h], xmm0
0x18001b61f  movups  xmm1, xmmword ptr [rsi+10h]
0x18001b623  movups  xmmword ptr [rax+30h], xmm1
0x18001b627  mov     qword ptr [rsi+10h], 0
0x18001b62f  mov     qword ptr [rsi+18h], 0Fh
0x18001b637  mov     byte ptr [rsi], 0
0x18001b63a  mov     byte ptr [rax+40h], 0
0x18001b63e  lea     rcx, [rax+48h]
0x18001b642  xor     edx, edx
0x18001b644  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18001b649  nop
0x18001b64a  mov     [rbx], rdi
0x18001b64d  mov     [rbx+8], rdi
0x18001b651  mov     [rbx+10h], rdi
0x18001b655  mov     word ptr [rbx+18h], 0
0x18001b65b  movups  xmm0, [rsp+78h+var_48]
0x18001b660  movdqu  [rsp+78h+var_58], xmm0
0x18001b666  mov     r8, rbx
0x18001b669  lea     rdx, [rsp+78h+var_58]
0x18001b66e  mov     rcx, r14
0x18001b671  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> *>,std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> * const)
0x18001b676  mov     rbx, rax
0x18001b679  lea     rax, [rbx+40h]
0x18001b67d  add     rsp, 58h
0x18001b681  pop     r14
0x18001b683  pop     rdi
0x18001b684  pop     rsi
0x18001b685  pop     rbx
0x18001b686  retn
0x18001b687  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
