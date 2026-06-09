# std::vector<std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>>,std::allocator<std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>>>(std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>> * const,std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>> &&)

- ea: `0x18002e528`
- end: `0x18002e666`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180011b30`
- `0x18003479c`
- `0x180036d30`
- `0x180039878`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cd04`
- `0x18002e528`
- `0x18002f220`
- `0x180030b24`
- `0x180033b70`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e563`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e563`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<FILTER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<FILTER_ENTRY>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  __int64 size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  _QWORD *v17; // r8
  _QWORD *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  *a3 = 0;
  v17 = (_QWORD *)v14;
  v23[0] = a1;
  v18 = (_QWORD *)(v14 + 8 * v11);
  v23[2] = v3;
  *v18 = v15;
  v19 = a1[1];
  v20 = *a1;
  v25 = v18 + 1;
  v24 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>>>(v20, v19, v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<FILTER_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<MAP_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e528  push    rbx
0x18002e52a  push    rbp
0x18002e52b  push    rsi
0x18002e52c  push    rdi
0x18002e52d  push    r12
0x18002e52f  push    r13
0x18002e531  push    r14
0x18002e533  push    r15
0x18002e535  sub     rsp, 58h
0x18002e539  mov     rax, [rcx+8]
0x18002e53d  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e547  sub     rax, [rcx]
0x18002e54a  mov     r13, r8
0x18002e54d  sar     rax, 3
0x18002e551  mov     rbp, rdx
0x18002e554  mov     rbx, rcx
0x18002e557  cmp     rax, rdi
0x18002e55a  jnz     short loc_18002E56A
0x18002e55c  lea     rcx, aVectorTooLong; "vector too long"
0x18002e563  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e56a  lea     r14, [rax+1]
0x18002e56e  mov     r15, rbp
0x18002e571  sub     r15, [rcx]
0x18002e574  mov     rax, rdi
0x18002e577  mov     rcx, [rcx+10h]
0x18002e57b  sub     rcx, [rbx]
0x18002e57e  sar     rcx, 3
0x18002e582  mov     rdx, rcx
0x18002e585  sar     r15, 3
0x18002e589  shr     rdx, 1
0x18002e58c  sub     rax, rdx
0x18002e58f  cmp     rcx, rax
0x18002e592  ja      short loc_18002E59F
0x18002e594  lea     rdi, [rdx+rcx]
0x18002e598  cmp     rdi, r14
0x18002e59b  cmovb   rdi, r14
0x18002e59f  mov     rcx, rdi
0x18002e5a2  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e5a7  mov     rcx, rax
0x18002e5aa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e5af  mov     rcx, [r13+0]
0x18002e5b3  mov     rsi, rax
0x18002e5b6  mov     qword ptr [r13+0], 0
0x18002e5be  mov     r8, rax
0x18002e5c1  mov     [rsp+98h+var_78], rbx
0x18002e5c6  lea     r15, [rax+r15*8]
0x18002e5ca  mov     [rsp+98h+var_68], rdi
0x18002e5cf  mov     [r15], rcx
0x18002e5d2  lea     r12, [r15+8]
0x18002e5d6  mov     rdx, [rbx+8]
0x18002e5da  mov     rcx, [rbx]
0x18002e5dd  mov     [rsp+98h+var_58], r12
0x18002e5e2  mov     [rsp+98h+var_60], r15
0x18002e5e7  cmp     rbp, rdx
0x18002e5ea  jz      short loc_18002E603
0x18002e5ec  mov     rdx, rbp
0x18002e5ef  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>>>(std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>> &)
0x18002e5f4  mov     rdx, [rbx+8]
0x18002e5f8  mov     r8, r12
0x18002e5fb  mov     rcx, rbp
0x18002e5fe  mov     [rsp+98h+var_60], rsi
0x18002e603  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>>>(std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> * const,std::unique_ptr<FILTER_ENTRY> *,std::allocator<std::unique_ptr<FILTER_ENTRY>> &)
0x18002e608  mov     rcx, [rbx]
0x18002e60b  mov     [rsp+98h+var_70], 0
0x18002e614  test    rcx, rcx
0x18002e617  jz      short loc_18002E635
0x18002e619  mov     rdx, [rbx+8]
0x18002e61d  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<FILTER_ENTRY>>>(std::unique_ptr<FILTER_ENTRY> *,std::unique_ptr<FILTER_ENTRY> * const,std::allocator<std::unique_ptr<FILTER_ENTRY>> &)
0x18002e622  mov     rdx, [rbx+10h]
0x18002e626  sub     rdx, [rbx]
0x18002e629  mov     rcx, [rbx]
0x18002e62c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e630  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e635  mov     [rbx], rsi
0x18002e638  lea     rcx, [rsi+r14*8]
0x18002e63c  mov     [rbx+8], rcx
0x18002e640  lea     rcx, [rsi+rdi*8]
0x18002e644  mov     [rbx+10h], rcx
0x18002e648  lea     rcx, [rsp+98h+var_78]
0x18002e64d  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<MAP_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e652  mov     rax, r15
0x18002e655  add     rsp, 58h
0x18002e659  pop     r15
0x18002e65b  pop     r14
0x18002e65d  pop     r13
0x18002e65f  pop     r12
0x18002e661  pop     rdi
0x18002e662  pop     rsi
0x18002e663  pop     rbp
0x18002e664  pop     rbx
0x18002e665  retn
```
