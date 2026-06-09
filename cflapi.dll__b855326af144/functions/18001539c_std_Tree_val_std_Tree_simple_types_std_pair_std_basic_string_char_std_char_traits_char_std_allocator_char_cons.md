# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>,void *> *)

- ea: `0x18001539c`
- end: `0x1800153ff`
- name: `??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@1@@Z`
- size: `99`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18001539c`
- `0x18001a978`
- `0x18001ab24`
- `0x18001ab94`
- `0x180022cf4`

## callees

- `0x180002860`
- `0x180008a68`
- `0x18001539c`
- `0x180022cf4`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rsi
  __int64 *v6; // rdi

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)v6 + 9,
      *((_BYTE *)v6 + 64));
    std::string::~string(v6 + 4);
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x18001539c  push    rbx
0x18001539e  push    rbp
0x18001539f  push    rsi
0x1800153a0  push    rdi
0x1800153a1  push    r14
0x1800153a3  sub     rsp, 20h
0x1800153a7  cmp     byte ptr [r8+19h], 0
0x1800153ac  mov     rsi, r8
0x1800153af  mov     rbp, rdx
0x1800153b2  mov     r14, rcx
0x1800153b5  jnz     short loc_1800153F4
0x1800153b7  mov     r8, [rsi+10h]
0x1800153bb  mov     rdx, rbp
0x1800153be  mov     rcx, r14
0x1800153c1  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *>> &,std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> *)
0x1800153c6  mov     rdi, rsi
0x1800153c9  mov     rsi, [rsi]
0x1800153cc  mov     dl, [rdi+40h]
0x1800153cf  lea     rcx, [rdi+48h]
0x1800153d3  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800153d8  lea     rcx, [rdi+20h]
0x1800153dc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800153e1  mov     edx, 50h ; 'P'; unsigned __int64
0x1800153e6  mov     rcx, rdi; void *
0x1800153e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800153ee  cmp     byte ptr [rsi+19h], 0
0x1800153f2  jz      short loc_1800153B7
0x1800153f4  add     rsp, 20h
0x1800153f8  pop     r14
0x1800153fa  pop     rdi
0x1800153fb  pop     rsi
0x1800153fc  pop     rbp
0x1800153fd  pop     rbx
0x1800153fe  retn
```
