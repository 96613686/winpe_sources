# std::vector<std::unique_ptr<ETW_PROVIDER_ENTRY,std::default_delete<ETW_PROVIDER_ENTRY>>,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY,std::default_delete<ETW_PROVIDER_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<ETW_PROVIDER_ENTRY,std::default_delete<ETW_PROVIDER_ENTRY>>>(std::unique_ptr<ETW_PROVIDER_ENTRY,std::default_delete<ETW_PROVIDER_ENTRY>> * const,std::unique_ptr<ETW_PROVIDER_ENTRY,std::default_delete<ETW_PROVIDER_ENTRY>> &&)

- ea: `0x18002e2a0`
- end: `0x18002e3de`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800360b4`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cc94`
- `0x18002e2a0`
- `0x18002f220`
- `0x180030aa4`
- `0x180033af8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e2db`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e2db`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<ETW_PROVIDER_ENTRY>>::_Emplace_reallocate<std::unique_ptr<ETW_PROVIDER_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<ETW_PROVIDER_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e2a0  push    rbx
0x18002e2a2  push    rbp
0x18002e2a3  push    rsi
0x18002e2a4  push    rdi
0x18002e2a5  push    r12
0x18002e2a7  push    r13
0x18002e2a9  push    r14
0x18002e2ab  push    r15
0x18002e2ad  sub     rsp, 58h
0x18002e2b1  mov     rax, [rcx+8]
0x18002e2b5  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e2bf  sub     rax, [rcx]
0x18002e2c2  mov     r13, r8
0x18002e2c5  sar     rax, 3
0x18002e2c9  mov     rbp, rdx
0x18002e2cc  mov     rbx, rcx
0x18002e2cf  cmp     rax, rdi
0x18002e2d2  jnz     short loc_18002E2E2
0x18002e2d4  lea     rcx, aVectorTooLong; "vector too long"
0x18002e2db  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e2e2  lea     r14, [rax+1]
0x18002e2e6  mov     r15, rbp
0x18002e2e9  sub     r15, [rcx]
0x18002e2ec  mov     rax, rdi
0x18002e2ef  mov     rcx, [rcx+10h]
0x18002e2f3  sub     rcx, [rbx]
0x18002e2f6  sar     rcx, 3
0x18002e2fa  mov     rdx, rcx
0x18002e2fd  sar     r15, 3
0x18002e301  shr     rdx, 1
0x18002e304  sub     rax, rdx
0x18002e307  cmp     rcx, rax
0x18002e30a  ja      short loc_18002E317
0x18002e30c  lea     rdi, [rdx+rcx]
0x18002e310  cmp     rdi, r14
0x18002e313  cmovb   rdi, r14
0x18002e317  mov     rcx, rdi
0x18002e31a  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e31f  mov     rcx, rax
0x18002e322  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e327  mov     rcx, [r13+0]
0x18002e32b  mov     rsi, rax
0x18002e32e  mov     qword ptr [r13+0], 0
0x18002e336  mov     r8, rax
0x18002e339  mov     [rsp+98h+var_78], rbx
0x18002e33e  lea     r15, [rax+r15*8]
0x18002e342  mov     [rsp+98h+var_68], rdi
0x18002e347  mov     [r15], rcx
0x18002e34a  lea     r12, [r15+8]
0x18002e34e  mov     rdx, [rbx+8]
0x18002e352  mov     rcx, [rbx]
0x18002e355  mov     [rsp+98h+var_58], r12
0x18002e35a  mov     [rsp+98h+var_60], r15
0x18002e35f  cmp     rbp, rdx
0x18002e362  jz      short loc_18002E37B
0x18002e364  mov     rdx, rbp
0x18002e367  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(std::unique_ptr<ETW_PROVIDER_ENTRY> * const,std::unique_ptr<ETW_PROVIDER_ENTRY> * const,std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>> &)
0x18002e36c  mov     rdx, [rbx+8]
0x18002e370  mov     r8, r12
0x18002e373  mov     rcx, rbp
0x18002e376  mov     [rsp+98h+var_60], rsi
0x18002e37b  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(std::unique_ptr<ETW_PROVIDER_ENTRY> * const,std::unique_ptr<ETW_PROVIDER_ENTRY> * const,std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>> &)
0x18002e380  mov     rcx, [rbx]
0x18002e383  mov     [rsp+98h+var_70], 0
0x18002e38c  test    rcx, rcx
0x18002e38f  jz      short loc_18002E3AD
0x18002e391  mov     rdx, [rbx+8]
0x18002e395  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>>>(std::unique_ptr<ETW_PROVIDER_ENTRY> *,std::unique_ptr<ETW_PROVIDER_ENTRY> * const,std::allocator<std::unique_ptr<ETW_PROVIDER_ENTRY>> &)
0x18002e39a  mov     rdx, [rbx+10h]
0x18002e39e  sub     rdx, [rbx]
0x18002e3a1  mov     rcx, [rbx]
0x18002e3a4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e3a8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e3ad  mov     [rbx], rsi
0x18002e3b0  lea     rcx, [rsi+r14*8]
0x18002e3b4  mov     [rbx+8], rcx
0x18002e3b8  lea     rcx, [rsi+rdi*8]
0x18002e3bc  mov     [rbx+10h], rcx
0x18002e3c0  lea     rcx, [rsp+98h+var_78]
0x18002e3c5  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VETW_PROVIDER_ENTRY@@U?$default_delete@VETW_PROVIDER_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ETW_PROVIDER_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e3ca  mov     rax, r15
0x18002e3cd  add     rsp, 58h
0x18002e3d1  pop     r15
0x18002e3d3  pop     r14
0x18002e3d5  pop     r13
0x18002e3d7  pop     r12
0x18002e3d9  pop     rdi
0x18002e3da  pop     rsi
0x18002e3db  pop     rbp
0x18002e3dc  pop     rbx
0x18002e3dd  retn
```
