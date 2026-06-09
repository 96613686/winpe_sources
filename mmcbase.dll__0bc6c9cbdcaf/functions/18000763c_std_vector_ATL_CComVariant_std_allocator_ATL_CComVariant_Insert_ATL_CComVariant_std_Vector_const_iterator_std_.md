# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Insert<ATL::CComVariant *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,ATL::CComVariant *,std::forward_iterator_tag)

- ea: `0x18000763c`
- end: `0x1800077fe`
- name: `??$_Insert@PEAVCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@1@PEAVCComVariant@ATL@@1Uforward_iterator_tag@1@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004bf0`

## callees

- `0x18000763c`
- `0x180009928`
- `0x180009950`
- `0x1800136d8`
- `0x1800137ec`
- `0x180013e30`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180007715`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180007715`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007798`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007798`

## pseudocode

```c
void __fastcall std::vector<ATL::CComVariant>::_Insert<ATL::CComVariant *>(
        __int64 a1,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int64 a4)
{
  unsigned __int64 v7; // rdi
  __int64 v8; // r8
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r15
  char *v13; // r14
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 v17; // [rsp+70h] [rbp+18h]
  void *v18; // [rsp+78h] [rbp+20h]

  v7 = 0xAAAAAAAAAAAAAAABuLL * ((a4 - (__int64)a3) >> 3);
  if ( v7 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( 0xAAAAAAAAAAAAAAABuLL * ((*(_QWORD *)(a1 + 16) - v8) >> 3) >= v7 )
    {
      std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(a3);
      v16 = 24 * v7;
      std::rotate<ATL::CComVariant *>(a2, *(_QWORD *)(a1 + 8), v16 + *(_QWORD *)(a1 + 8));
      *(_QWORD *)(a1 + 8) += v16;
    }
    else
    {
      v9 = 0xAAAAAAAAAAAAAAABuLL * ((v8 - *(_QWORD *)a1) >> 3);
      if ( 0xAAAAAAAAAAAAAAALL - v9 < v7 )
        std::_Xlength_error("vector<T> too long");
      v10 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
      v11 = 0xAAAAAAAAAAAAAAALL - (v10 >> 1);
      v12 = 0;
      if ( v11 >= v10 )
        v12 = v10 + (v10 >> 1);
      if ( v12 < v9 + v7 )
        v12 = v9 + v7;
      v13 = 0;
      v18 = 0;
      if ( v12 )
      {
        if ( v12 > 0xAAAAAAAAAAAAAAALL || (v13 = (char *)operator new(24 * v12), (v18 = v13) == 0) )
          std::_Xbad_alloc();
      }
      try
      {
        std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(*(struct tagVARIANT **)a1);
        v17 = std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(a3);
        std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(a2);
      }
      catch ( ... )
      {
        std::vector<ATL::CComVariant>::_Destroy(v14, v18, v17);
        operator delete(v18);
        throw;
      }
      v15 = v7 - 0x5555555555555555LL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
      if ( *(_QWORD *)a1 )
      {
        ((void (*)(void))std::vector<ATL::CComVariant>::_Destroy)();
        operator delete(*(void **)a1);
      }
      *(_QWORD *)(a1 + 16) = &v13[24 * v12];
      *(_QWORD *)(a1 + 8) = &v13[24 * v15];
      *(_QWORD *)a1 = v13;
    }
  }
}

```

## disassembly

```asm
0x18000763c  mov     [rsp+arg_0], rbx
0x180007641  mov     [rsp+arg_8], rsi
0x180007646  push    rdi
0x180007647  push    r12
0x180007649  push    r13
0x18000764b  push    r14
0x18000764d  push    r15
0x18000764f  sub     rsp, 30h
0x180007653  mov     r12, r9
0x180007656  mov     r13, r8
0x180007659  mov     rbx, rdx
0x18000765c  mov     rsi, rcx
0x18000765f  mov     rdi, r9
0x180007662  sub     rdi, r8
0x180007665  sar     rdi, 3
0x180007669  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180007673  imul    rdi, rcx
0x180007677  test    rdi, rdi
0x18000767a  jz      loc_1800077E6
0x180007680  mov     r8, [rsi+8]
0x180007684  mov     r9, [rsi+10h]
0x180007688  mov     rax, r9
0x18000768b  sub     rax, r8
0x18000768e  sar     rax, 3
0x180007692  imul    rax, rcx
0x180007696  cmp     rax, rdi
0x180007699  jnb     loc_1800077BB
0x18000769f  sub     r8, [rsi]
0x1800076a2  sar     r8, 3
0x1800076a6  imul    r8, rcx
0x1800076aa  mov     r10, 0AAAAAAAAAAAAAAAh
0x1800076b4  mov     rax, r10
0x1800076b7  sub     rax, r8
0x1800076ba  cmp     rax, rdi
0x1800076bd  jnb     short loc_1800076CC
0x1800076bf  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x1800076c6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800076cc  lea     rdx, [r8+rdi]
0x1800076d0  sub     r9, [rsi]
0x1800076d3  sar     r9, 3
0x1800076d7  imul    r9, rcx
0x1800076db  mov     rax, r9
0x1800076de  shr     rax, 1
0x1800076e1  mov     rcx, r10
0x1800076e4  sub     rcx, rax
0x1800076e7  add     rax, r9
0x1800076ea  xor     r15d, r15d
0x1800076ed  cmp     rcx, r9
0x1800076f0  cmovnb  r15, rax
0x1800076f4  cmp     r15, rdx
0x1800076f7  cmovb   r15, rdx
0x1800076fb  xor     r14d, r14d
0x1800076fe  mov     [rsp+58h+arg_18], r14
0x180007703  test    r15, r15
0x180007706  jz      short loc_18000772E
0x180007708  cmp     r15, r10
0x18000770b  ja      short loc_180007728
0x18000770d  lea     rcx, [r15+r15*2]
0x180007711  shl     rcx, 3
0x180007715  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000771b  mov     r14, rax
0x18000771e  mov     [rsp+58h+arg_18], rax
0x180007723  test    rax, rax
0x180007726  jnz     short loc_18000772E
0x180007728  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000772e  mov     [rsp+58h+arg_10], r14
0x180007733  mov     r8, r14
0x180007736  mov     rdx, rbx
0x180007739  mov     rcx, [rsi]; struct tagVARIANT *
0x18000773c  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180007741  mov     [rsp+58h+arg_10], rax
0x180007746  mov     r8, rax
0x180007749  mov     rdx, r12
0x18000774c  mov     rcx, r13; struct tagVARIANT *
0x18000774f  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180007754  mov     [rsp+58h+arg_10], rax
0x180007759  mov     r8, rax
0x18000775c  mov     rdx, [rsi+8]
0x180007760  mov     rcx, rbx; struct tagVARIANT *
0x180007763  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180007768  nop
0x180007769  mov     rdx, [rsi]
0x18000776c  mov     r8, [rsi+8]
0x180007770  mov     rbx, r8
0x180007773  sub     rbx, rdx
0x180007776  sar     rbx, 3
0x18000777a  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180007784  imul    rbx, rcx
0x180007788  add     rbx, rdi
0x18000778b  test    rdx, rdx
0x18000778e  jz      short loc_18000779E
0x180007790  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x180007795  mov     rcx, [rsi]
0x180007798  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000779e  lea     rax, [r15+r15*2]
0x1800077a2  lea     rcx, [r14+rax*8]
0x1800077a6  mov     [rsi+10h], rcx
0x1800077aa  lea     rax, [rbx+rbx*2]
0x1800077ae  lea     rcx, [r14+rax*8]
0x1800077b2  mov     [rsi+8], rcx
0x1800077b6  mov     [rsi], r14
0x1800077b9  jmp     short loc_1800077E6
0x1800077bb  mov     rdx, r12
0x1800077be  mov     rcx, r13; struct tagVARIANT *
0x1800077c1  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x1800077c6  mov     rdx, [rsi+8]
0x1800077ca  lea     rax, [rdi+rdi*2]
0x1800077ce  lea     rdi, ds:0[rax*8]
0x1800077d6  lea     r8, [rdi+rdx]
0x1800077da  mov     rcx, rbx
0x1800077dd  call    ??$rotate@PEAVCComVariant@ATL@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00@Z; std::rotate<ATL::CComVariant *>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *)
0x1800077e2  add     [rsi+8], rdi
0x1800077e6  mov     rbx, [rsp+58h+arg_0]
0x1800077eb  mov     rsi, [rsp+58h+arg_8]
0x1800077f0  add     rsp, 30h
0x1800077f4  pop     r15
0x1800077f6  pop     r14
0x1800077f8  pop     r13
0x1800077fa  pop     r12
0x1800077fc  pop     rdi
0x1800077fd  retn
```
