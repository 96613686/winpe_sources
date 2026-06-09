# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180011d60`
- end: `0x180011fbf`
- name: `??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `607`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001ca0`

## callees

- `0x180002b94`
- `0x180002c8c`
- `0x18000dcb0`
- `0x180011950`
- `0x180011aa8`
- `0x180011d60`
- `0x180013220`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011df6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011df6`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // r8
  _QWORD *v6; // rdx
  __int64 v7; // rsi
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  float v12; // xmm0_4
  unsigned __int64 v13; // rbx
  float v14; // xmm2_4
  float v15; // xmm0_4
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // r8
  _QWORD *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r10
  _BYTE v27[8]; // [rsp+20h] [rbp-28h] BYREF
  void *v28; // [rsp+28h] [rbp-20h]
  __int128 v29; // [rsp+30h] [rbp-18h] BYREF

  v5 = a3[2];
  if ( a3[3] <= 7u )
    v6 = a3;
  else
    v6 = (_QWORD *)*a3;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 0;
  v9 = 2 * v5;
  if ( v9 )
  {
    do
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)v6 + v8++) ^ (unsigned __int64)v7);
    while ( v8 < v9 );
  }
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
    v8,
    &v29,
    (__int64)a3,
    v7);
  if ( *((_QWORD *)&v29 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v29 + 1);
    *(_BYTE *)(a2 + 8) = 0;
    return a2;
  }
  if ( qword_180022ED0 == 0x555555555555555LL )
    std::_Xlength_error("unordered_map/set too long");
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(
    v27,
    &qword_180022EC8,
    a3);
  v10 = qword_180022ED0;
  v11 = qword_180022ED0 + 1;
  if ( qword_180022ED0 + 1 < 0 )
    v12 = (float)(int)(v11 & 1 | (v11 >> 1)) + (float)(int)(v11 & 1 | (v11 >> 1));
  else
    v12 = (float)(int)v11;
  v13 = qword_180022EF8;
  if ( qword_180022EF8 < 0 )
    v14 = (float)(qword_180022EF8 & 1 | (unsigned int)((unsigned __int64)qword_180022EF8 >> 1))
        + (float)(qword_180022EF8 & 1 | (unsigned int)((unsigned __int64)qword_180022EF8 >> 1));
  else
    v14 = (float)(int)qword_180022EF8;
  if ( (float)(v12 / v14) > *(float *)&EventHandler::infoEventsToEmit )
  {
    v15 = o_ceilf_0(v12 / *(float *)&EventHandler::infoEventsToEmit);
    v16 = 0;
    if ( v15 >= 9.223372e18 )
    {
      v15 = v15 - 9.223372e18;
      if ( v15 < 9.223372e18 )
        v16 = 0x8000000000000000uLL;
    }
    v17 = v16 + (unsigned int)(int)v15;
    v18 = 8;
    if ( v17 > 8 )
      v18 = v17;
    if ( v13 < v18 )
    {
      if ( v13 >= 0x200 || (v13 *= 8LL, v13 < v18) )
        v13 = v18;
    }
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
      v18,
      v13);
    v29 = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                       v19,
                       &v29,
                       (__int64)v28 + 16,
                       v7);
    v10 = qword_180022ED0;
  }
  v20 = v28;
  v28 = 0;
  v21 = v29;
  v22 = *(_QWORD **)(v29 + 8);
  qword_180022ED0 = v10 + 1;
  *v20 = v29;
  v20[1] = v22;
  *v22 = v20;
  *(_QWORD *)(v21 + 8) = v20;
  v23 = qword_180022ED8;
  v24 = 2 * (v7 & qword_180022EF0);
  v25 = *(_QWORD *)(qword_180022ED8 + 16 * (v7 & qword_180022EF0));
  if ( v25 == qword_180022EC8 )
  {
    *(_QWORD *)(qword_180022ED8 + 16 * (v7 & qword_180022EF0)) = v20;
LABEL_32:
    *(_QWORD *)(v23 + 8 * v24 + 8) = v20;
    goto LABEL_33;
  }
  if ( v25 == v21 )
  {
    *(_QWORD *)(qword_180022ED8 + 16 * (v7 & qword_180022EF0)) = v20;
  }
  else if ( *(_QWORD **)(qword_180022ED8 + 16 * (v7 & qword_180022EF0) + 8) == v22 )
  {
    goto LABEL_32;
  }
LABEL_33:
  *(_QWORD *)a2 = v20;
  *(_BYTE *)(a2 + 8) = 1;
  if ( v28 )
  {
    std::wstring::~wstring((char *)v28 + 16);
    if ( v28 )
      operator delete(v28, 0x30u);
  }
  return a2;
}

```

## disassembly

```asm
0x180011d60  mov     [rsp+arg_0], rbx
0x180011d65  mov     [rsp+arg_8], rsi
0x180011d6a  push    rdi
0x180011d6b  sub     rsp, 40h
0x180011d6f  mov     rbx, r8
0x180011d72  mov     rdi, rdx
0x180011d75  mov     r8, [r8+10h]
0x180011d79  cmp     qword ptr [rbx+18h], 7
0x180011d7e  jbe     short loc_180011D85
0x180011d80  mov     rdx, [rbx]
0x180011d83  jmp     short loc_180011D88
0x180011d85  mov     rdx, rbx
0x180011d88  mov     rsi, 0CBF29CE484222325h
0x180011d92  xor     ecx, ecx
0x180011d94  add     r8, r8
0x180011d97  jz      short loc_180011DB6
0x180011d99  movzx   eax, byte ptr [rdx+rcx]
0x180011d9d  xor     rsi, rax
0x180011da0  mov     r9, 100000001B3h
0x180011daa  imul    rsi, r9
0x180011dae  inc     rcx
0x180011db1  cmp     rcx, r8
0x180011db4  jb      short loc_180011D99
0x180011db6  mov     r9, rsi
0x180011db9  mov     r8, rbx
0x180011dbc  lea     rdx, [rsp+48h+var_18]
0x180011dc1  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180011dc6  mov     rax, qword ptr [rsp+48h+var_18+8]
0x180011dcb  test    rax, rax
0x180011dce  jz      short loc_180011DDC
0x180011dd0  mov     [rdi], rax
0x180011dd3  mov     byte ptr [rdi+8], 0
0x180011dd7  jmp     loc_180011FAC
0x180011ddc  mov     rax, 555555555555555h
0x180011de6  cmp     cs:qword_180022ED0, rax
0x180011ded  jnz     short loc_180011DFD
0x180011def  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180011df6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011dfd  mov     r8, rbx
0x180011e00  lea     rdx, qword_180022EC8
0x180011e07  lea     rcx, [rsp+48h+var_28]
0x180011e0c  call    ??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::wstring const &)
0x180011e11  nop
0x180011e12  mov     rdx, cs:qword_180022ED0
0x180011e19  lea     rcx, [rdx+1]
0x180011e1d  xorps   xmm0, xmm0
0x180011e20  test    rcx, rcx
0x180011e23  js      short loc_180011E2C
0x180011e25  cvtsi2ss xmm0, rcx
0x180011e2a  jmp     short loc_180011E41
0x180011e2c  mov     rax, rcx
0x180011e2f  shr     rax, 1
0x180011e32  and     ecx, 1
0x180011e35  or      rax, rcx
0x180011e38  cvtsi2ss xmm0, rax
0x180011e3d  addss   xmm0, xmm0
0x180011e41  mov     rbx, cs:qword_180022EF8
0x180011e48  xorps   xmm2, xmm2
0x180011e4b  test    rbx, rbx
0x180011e4e  js      short loc_180011E57
0x180011e50  cvtsi2ss xmm2, rbx
0x180011e55  jmp     short loc_180011E6F
0x180011e57  mov     rcx, rbx
0x180011e5a  shr     rcx, 1
0x180011e5d  mov     rax, rbx
0x180011e60  and     eax, 1
0x180011e63  or      rcx, rax
0x180011e66  cvtsi2ss xmm2, rcx
0x180011e6b  addss   xmm2, xmm2
0x180011e6f  movaps  xmm1, xmm0
0x180011e72  divss   xmm1, xmm2
0x180011e76  movss   xmm3, cs:?infoEventsToEmit@EventHandler@@0V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::unordered_set<std::wstring> EventHandler::infoEventsToEmit
0x180011e7e  comiss  xmm1, xmm3
0x180011e81  jbe     loc_180011F11
0x180011e87  divss   xmm0, xmm3; X
0x180011e8b  call    _o_ceilf_0
0x180011e90  xor     ecx, ecx
0x180011e92  movss   xmm1, cs:__real@5f000000
0x180011e9a  comiss  xmm0, xmm1
0x180011e9d  jb      short loc_180011EB5
0x180011e9f  subss   xmm0, xmm1
0x180011ea3  comiss  xmm0, xmm1
0x180011ea6  jnb     short loc_180011EB5
0x180011ea8  mov     rax, 8000000000000000h
0x180011eb2  mov     rcx, rax
0x180011eb5  cvttss2si rax, xmm0
0x180011eba  add     rax, rcx
0x180011ebd  mov     ecx, 8
0x180011ec2  cmp     rax, rcx
0x180011ec5  cmova   rcx, rax
0x180011ec9  cmp     rbx, rcx
0x180011ecc  jnb     short loc_180011EE3
0x180011ece  cmp     rbx, 200h
0x180011ed5  jnb     short loc_180011EE0
0x180011ed7  shl     rbx, 3
0x180011edb  cmp     rbx, rcx
0x180011ede  jnb     short loc_180011EE3
0x180011ee0  mov     rbx, rcx
0x180011ee3  mov     rdx, rbx
0x180011ee6  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x180011eeb  mov     r8, [rsp+48h+var_20]
0x180011ef0  add     r8, 10h
0x180011ef4  mov     r9, rsi
0x180011ef7  lea     rdx, [rsp+48h+var_18]
0x180011efc  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180011f01  movups  xmm0, xmmword ptr [rax]
0x180011f04  movdqu  [rsp+48h+var_18], xmm0
0x180011f0a  mov     rdx, cs:qword_180022ED0
0x180011f11  mov     rcx, [rsp+48h+var_20]
0x180011f16  mov     [rsp+48h+var_20], 0
0x180011f1f  mov     r8, qword ptr [rsp+48h+var_18]
0x180011f24  mov     r9, [r8+8]
0x180011f28  inc     rdx
0x180011f2b  mov     cs:qword_180022ED0, rdx
0x180011f32  mov     [rcx], r8
0x180011f35  mov     [rcx+8], r9
0x180011f39  mov     [r9], rcx
0x180011f3c  mov     [r8+8], rcx
0x180011f40  mov     rdx, cs:qword_180022ED8
0x180011f47  mov     rax, cs:qword_180022EF0
0x180011f4e  and     rax, rsi
0x180011f51  add     rax, rax
0x180011f54  mov     r10, [rdx+rax*8]
0x180011f58  cmp     r10, cs:qword_180022EC8
0x180011f5f  jnz     short loc_180011F67
0x180011f61  mov     [rdx+rax*8], rcx
0x180011f65  jmp     short loc_180011F79
0x180011f67  cmp     r10, r8
0x180011f6a  jnz     short loc_180011F72
0x180011f6c  mov     [rdx+rax*8], rcx
0x180011f70  jmp     short loc_180011F7E
0x180011f72  cmp     [rdx+rax*8+8], r9
0x180011f77  jnz     short loc_180011F7E
0x180011f79  mov     [rdx+rax*8+8], rcx
0x180011f7e  mov     [rdi], rcx
0x180011f81  mov     byte ptr [rdi+8], 1
0x180011f85  mov     rcx, [rsp+48h+var_20]
0x180011f8a  test    rcx, rcx
0x180011f8d  jz      short loc_180011FAC
0x180011f8f  add     rcx, 10h; void *
0x180011f93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f98  mov     rcx, [rsp+48h+var_20]; void *
0x180011f9d  test    rcx, rcx
0x180011fa0  jz      short loc_180011FAC
0x180011fa2  mov     edx, 30h ; '0'; unsigned __int64
0x180011fa7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011fac  mov     rax, rdi
0x180011faf  mov     rbx, [rsp+48h+arg_0]
0x180011fb4  mov     rsi, [rsp+48h+arg_8]
0x180011fb9  add     rsp, 40h
0x180011fbd  pop     rdi
0x180011fbe  retn
```
