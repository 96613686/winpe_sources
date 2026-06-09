# std::vector<std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>,std::allocator<std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>>(std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>> * const,std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>> &&)

- ea: `0x18002e7b0`
- end: `0x18002e8ee`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180038a44`
- `0x180039780`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cd74`
- `0x18002e7b0`
- `0x18002f220`
- `0x180030ba4`
- `0x180033be8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e7eb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e7eb`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<MAPLIST_ENTRY>>::_Emplace_reallocate<std::unique_ptr<MAPLIST_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<MAPLIST_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e7b0  push    rbx
0x18002e7b2  push    rbp
0x18002e7b3  push    rsi
0x18002e7b4  push    rdi
0x18002e7b5  push    r12
0x18002e7b7  push    r13
0x18002e7b9  push    r14
0x18002e7bb  push    r15
0x18002e7bd  sub     rsp, 58h
0x18002e7c1  mov     rax, [rcx+8]
0x18002e7c5  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e7cf  sub     rax, [rcx]
0x18002e7d2  mov     r13, r8
0x18002e7d5  sar     rax, 3
0x18002e7d9  mov     rbp, rdx
0x18002e7dc  mov     rbx, rcx
0x18002e7df  cmp     rax, rdi
0x18002e7e2  jnz     short loc_18002E7F2
0x18002e7e4  lea     rcx, aVectorTooLong; "vector too long"
0x18002e7eb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e7f2  lea     r14, [rax+1]
0x18002e7f6  mov     r15, rbp
0x18002e7f9  sub     r15, [rcx]
0x18002e7fc  mov     rax, rdi
0x18002e7ff  mov     rcx, [rcx+10h]
0x18002e803  sub     rcx, [rbx]
0x18002e806  sar     rcx, 3
0x18002e80a  mov     rdx, rcx
0x18002e80d  sar     r15, 3
0x18002e811  shr     rdx, 1
0x18002e814  sub     rax, rdx
0x18002e817  cmp     rcx, rax
0x18002e81a  ja      short loc_18002E827
0x18002e81c  lea     rdi, [rdx+rcx]
0x18002e820  cmp     rdi, r14
0x18002e823  cmovb   rdi, r14
0x18002e827  mov     rcx, rdi
0x18002e82a  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e82f  mov     rcx, rax
0x18002e832  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e837  mov     rcx, [r13+0]
0x18002e83b  mov     rsi, rax
0x18002e83e  mov     qword ptr [r13+0], 0
0x18002e846  mov     r8, rax
0x18002e849  mov     [rsp+98h+var_78], rbx
0x18002e84e  lea     r15, [rax+r15*8]
0x18002e852  mov     [rsp+98h+var_68], rdi
0x18002e857  mov     [r15], rcx
0x18002e85a  lea     r12, [r15+8]
0x18002e85e  mov     rdx, [rbx+8]
0x18002e862  mov     rcx, [rbx]
0x18002e865  mov     [rsp+98h+var_58], r12
0x18002e86a  mov     [rsp+98h+var_60], r15
0x18002e86f  cmp     rbp, rdx
0x18002e872  jz      short loc_18002E88B
0x18002e874  mov     rdx, rbp
0x18002e877  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(std::unique_ptr<MAPLIST_ENTRY> * const,std::unique_ptr<MAPLIST_ENTRY> * const,std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>> &)
0x18002e87c  mov     rdx, [rbx+8]
0x18002e880  mov     r8, r12
0x18002e883  mov     rcx, rbp
0x18002e886  mov     [rsp+98h+var_60], rsi
0x18002e88b  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(std::unique_ptr<MAPLIST_ENTRY> * const,std::unique_ptr<MAPLIST_ENTRY> * const,std::unique_ptr<MAPLIST_ENTRY> *,std::allocator<std::unique_ptr<MAPLIST_ENTRY>> &)
0x18002e890  mov     rcx, [rbx]
0x18002e893  mov     [rsp+98h+var_70], 0
0x18002e89c  test    rcx, rcx
0x18002e89f  jz      short loc_18002E8BD
0x18002e8a1  mov     rdx, [rbx+8]
0x18002e8a5  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<MAPLIST_ENTRY>>>(std::unique_ptr<MAPLIST_ENTRY> *,std::unique_ptr<MAPLIST_ENTRY> * const,std::allocator<std::unique_ptr<MAPLIST_ENTRY>> &)
0x18002e8aa  mov     rdx, [rbx+10h]
0x18002e8ae  sub     rdx, [rbx]
0x18002e8b1  mov     rcx, [rbx]
0x18002e8b4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e8b8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e8bd  mov     [rbx], rsi
0x18002e8c0  lea     rcx, [rsi+r14*8]
0x18002e8c4  mov     [rbx+8], rcx
0x18002e8c8  lea     rcx, [rsi+rdi*8]
0x18002e8cc  mov     [rbx+10h], rcx
0x18002e8d0  lea     rcx, [rsp+98h+var_78]
0x18002e8d5  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<MAPLIST_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e8da  mov     rax, r15
0x18002e8dd  add     rsp, 58h
0x18002e8e1  pop     r15
0x18002e8e3  pop     r14
0x18002e8e5  pop     r13
0x18002e8e7  pop     r12
0x18002e8e9  pop     rdi
0x18002e8ea  pop     rsi
0x18002e8eb  pop     rbp
0x18002e8ec  pop     rbx
0x18002e8ed  retn
```
