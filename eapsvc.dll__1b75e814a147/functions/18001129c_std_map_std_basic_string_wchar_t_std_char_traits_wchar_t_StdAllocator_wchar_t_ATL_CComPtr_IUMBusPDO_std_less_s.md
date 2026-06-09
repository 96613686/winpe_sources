# std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>,0>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>> &&)

- ea: `0x18001129c`
- end: `0x180011404`
- name: `??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@1@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64 *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012cf8`

## callees

- `0x18000aafc`
- `0x18000d610`
- `0x18000e7d0`
- `0x18000eb88`
- `0x18001129c`
- `0x180011524`
- `0x1800137c8`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>,0>(
        __int64 *a1,
        __int64 a2,
        const wchar_t *a3)
{
  _QWORD *v6; // rax
  __int128 v7; // xmm6
  __int64 inserted; // rbx
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rbp
  const wchar_t *v12; // rcx
  size_t v13; // r8
  int v14; // eax
  __int64 v15; // rbp
  _OWORD *v16; // rbx
  __int64 v17; // rcx
  char v18; // al
  _OWORD v20[2]; // [rsp+20h] [rbp-68h] BYREF

  v6 = std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
         (__int64)a1,
         v20,
         (__int64)a3);
  v7 = *(_OWORD *)v6;
  inserted = v6[2];
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_11;
  v9 = (const wchar_t *)(inserted + 32);
  v10 = *(_QWORD *)(inserted + 48);
  if ( *(_QWORD *)(inserted + 56) > 7u )
    v9 = *(const wchar_t **)v9;
  v11 = *((_QWORD *)a3 + 2);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v12 = a3;
  else
    v12 = *(const wchar_t **)a3;
  v13 = *(_QWORD *)(inserted + 48);
  if ( v10 >= v11 )
    v13 = *((_QWORD *)a3 + 2);
  v14 = wmemcmp(v12, v9, v13);
  if ( v14 )
  {
    if ( v14 < 0 )
      goto LABEL_11;
LABEL_17:
    v18 = 0;
    goto LABEL_15;
  }
  if ( v11 >= v10 )
    goto LABEL_17;
LABEL_11:
  if ( a1[1] == 0x38E38E38E38E38ELL )
    std::_Throw_tree_length_error();
  v15 = *a1;
  v20[0] = (unsigned __int64)a1;
  v16 = operator new(0x48u);
  v16[2] = 0;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 0;
  v16[2] = *(_OWORD *)a3;
  v16[3] = *((_OWORD *)a3 + 1);
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 7;
  *a3 = 0;
  v17 = *((_QWORD *)a3 + 4);
  *((_QWORD *)v16 + 8) = v17;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  *(_QWORD *)v16 = v15;
  *((_QWORD *)v16 + 1) = v15;
  *((_QWORD *)v16 + 2) = v15;
  *((_WORD *)v16 + 12) = 0;
  *((_QWORD *)&v20[0] + 1) = 0;
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(v20);
  v20[0] = v7;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Insert_node(
               a1,
               v20,
               v16);
  v18 = 1;
LABEL_15:
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v18;
  return a2;
}

```

## disassembly

```asm
0x18001129c  push    rbx
0x18001129e  push    rbp
0x18001129f  push    rsi
0x1800112a0  push    rdi
0x1800112a1  push    r14
0x1800112a3  push    r15
0x1800112a5  sub     rsp, 58h
0x1800112a9  movaps  [rsp+88h+var_48], xmm6
0x1800112ae  mov     rdi, r8
0x1800112b1  mov     rsi, rdx
0x1800112b4  mov     r15, rcx
0x1800112b7  lea     rdx, [rsp+88h+var_68]
0x1800112bc  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800112c1  movups  xmm6, xmmword ptr [rax]
0x1800112c4  mov     rbx, [rax+10h]
0x1800112c8  cmp     byte ptr [rbx+19h], 0
0x1800112cc  jnz     short loc_180011313
0x1800112ce  lea     rdx, [rbx+20h]
0x1800112d2  mov     r14, [rdx+10h]
0x1800112d6  cmp     qword ptr [rdx+18h], 7
0x1800112db  jbe     short loc_1800112E0
0x1800112dd  mov     rdx, [rdx]; S2
0x1800112e0  mov     rbp, [rdi+10h]
0x1800112e4  cmp     qword ptr [rdi+18h], 7
0x1800112e9  jbe     short loc_1800112F0
0x1800112eb  mov     rcx, [rdi]
0x1800112ee  jmp     short loc_1800112F3
0x1800112f0  mov     rcx, rdi; S1
0x1800112f3  mov     r8, r14
0x1800112f6  cmp     r14, rbp
0x1800112f9  cmovnb  r8, rbp; N
0x1800112fd  call    wmemcmp
0x180011302  test    eax, eax
0x180011304  jnz     loc_1800113F4
0x18001130a  cmp     rbp, r14
0x18001130d  jnb     loc_1800113FA
0x180011313  mov     rax, 38E38E38E38E38Eh
0x18001131d  cmp     [r15+8], rax
0x180011321  jz      loc_1800113FE
0x180011327  mov     rbp, [r15]
0x18001132a  mov     qword ptr [rsp+88h+var_68], r15
0x18001132f  mov     qword ptr [rsp+88h+var_68+8], 0
0x180011338  mov     ecx, 48h ; 'H'; dwBytes
0x18001133d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011342  mov     rbx, rax
0x180011345  xorps   xmm0, xmm0
0x180011348  movups  xmmword ptr [rax+20h], xmm0
0x18001134c  mov     qword ptr [rax+30h], 0
0x180011354  mov     qword ptr [rax+38h], 0
0x18001135c  movups  xmm0, xmmword ptr [rdi]
0x18001135f  movups  xmmword ptr [rax+20h], xmm0
0x180011363  movups  xmm1, xmmword ptr [rdi+10h]
0x180011367  movups  xmmword ptr [rax+30h], xmm1
0x18001136b  mov     qword ptr [rdi+10h], 0
0x180011373  mov     qword ptr [rdi+18h], 7
0x18001137b  xor     eax, eax
0x18001137d  mov     [rdi], ax
0x180011380  mov     rcx, [rdi+20h]
0x180011384  mov     [rbx+40h], rcx
0x180011388  test    rcx, rcx
0x18001138b  jz      short loc_18001139A
0x18001138d  mov     rax, [rcx]
0x180011390  mov     rax, [rax+8]
0x180011394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011399  nop
0x18001139a  mov     [rbx], rbp
0x18001139d  mov     [rbx+8], rbp
0x1800113a1  mov     [rbx+10h], rbp
0x1800113a5  mov     word ptr [rbx+18h], 0
0x1800113ab  mov     qword ptr [rsp+88h+var_68+8], 0
0x1800113b4  lea     rcx, [rsp+88h+var_68]
0x1800113b9  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(void)
0x1800113be  movdqu  [rsp+88h+var_68], xmm6
0x1800113c4  mov     r8, rbx
0x1800113c7  lea     rdx, [rsp+88h+var_68]
0x1800113cc  mov     rcx, r15
0x1800113cf  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> *>,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> * const)
0x1800113d4  mov     rbx, rax
0x1800113d7  mov     al, 1
0x1800113d9  mov     [rsi], rbx
0x1800113dc  mov     [rsi+8], al
0x1800113df  mov     rax, rsi
0x1800113e2  movaps  xmm6, [rsp+88h+var_48]
0x1800113e7  add     rsp, 58h
0x1800113eb  pop     r15
0x1800113ed  pop     r14
0x1800113ef  pop     rdi
0x1800113f0  pop     rsi
0x1800113f1  pop     rbp
0x1800113f2  pop     rbx
0x1800113f3  retn
0x1800113f4  js      loc_180011313
0x1800113fa  xor     al, al
0x1800113fc  jmp     short loc_1800113D9
0x1800113fe  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
