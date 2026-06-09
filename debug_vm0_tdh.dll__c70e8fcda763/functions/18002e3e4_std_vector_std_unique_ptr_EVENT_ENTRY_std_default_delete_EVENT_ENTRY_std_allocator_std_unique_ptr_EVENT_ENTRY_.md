# std::vector<std::unique_ptr<EVENT_ENTRY,std::default_delete<EVENT_ENTRY>>,std::allocator<std::unique_ptr<EVENT_ENTRY,std::default_delete<EVENT_ENTRY>>>>::_Emplace_reallocate<std::unique_ptr<EVENT_ENTRY,std::default_delete<EVENT_ENTRY>>>(std::unique_ptr<EVENT_ENTRY,std::default_delete<EVENT_ENTRY>> * const,std::unique_ptr<EVENT_ENTRY,std::default_delete<EVENT_ENTRY>> &&)

- ea: `0x18002e3e4`
- end: `0x18002e522`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180035780`

## callees

- `0x180001084`
- `0x18000320c`
- `0x18002cccc`
- `0x18002e3e4`
- `0x18002f220`
- `0x180030ae4`
- `0x180033b34`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e41f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e41f`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<EVENT_ENTRY>>::_Emplace_reallocate<std::unique_ptr<EVENT_ENTRY>>(
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
    std::_Uninitialized_move<std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>>>(v20, a2, v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>>>(v20, v19, v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<EVENT_ENTRY>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<EVENT_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002e3e4  push    rbx
0x18002e3e6  push    rbp
0x18002e3e7  push    rsi
0x18002e3e8  push    rdi
0x18002e3e9  push    r12
0x18002e3eb  push    r13
0x18002e3ed  push    r14
0x18002e3ef  push    r15
0x18002e3f1  sub     rsp, 58h
0x18002e3f5  mov     rax, [rcx+8]
0x18002e3f9  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002e403  sub     rax, [rcx]
0x18002e406  mov     r13, r8
0x18002e409  sar     rax, 3
0x18002e40d  mov     rbp, rdx
0x18002e410  mov     rbx, rcx
0x18002e413  cmp     rax, rdi
0x18002e416  jnz     short loc_18002E426
0x18002e418  lea     rcx, aVectorTooLong; "vector too long"
0x18002e41f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002e426  lea     r14, [rax+1]
0x18002e42a  mov     r15, rbp
0x18002e42d  sub     r15, [rcx]
0x18002e430  mov     rax, rdi
0x18002e433  mov     rcx, [rcx+10h]
0x18002e437  sub     rcx, [rbx]
0x18002e43a  sar     rcx, 3
0x18002e43e  mov     rdx, rcx
0x18002e441  sar     r15, 3
0x18002e445  shr     rdx, 1
0x18002e448  sub     rax, rdx
0x18002e44b  cmp     rcx, rax
0x18002e44e  ja      short loc_18002E45B
0x18002e450  lea     rdi, [rdx+rcx]
0x18002e454  cmp     rdi, r14
0x18002e457  cmovb   rdi, r14
0x18002e45b  mov     rcx, rdi
0x18002e45e  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002e463  mov     rcx, rax
0x18002e466  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002e46b  mov     rcx, [r13+0]
0x18002e46f  mov     rsi, rax
0x18002e472  mov     qword ptr [r13+0], 0
0x18002e47a  mov     r8, rax
0x18002e47d  mov     [rsp+98h+var_78], rbx
0x18002e482  lea     r15, [rax+r15*8]
0x18002e486  mov     [rsp+98h+var_68], rdi
0x18002e48b  mov     [r15], rcx
0x18002e48e  lea     r12, [r15+8]
0x18002e492  mov     rdx, [rbx+8]
0x18002e496  mov     rcx, [rbx]
0x18002e499  mov     [rsp+98h+var_58], r12
0x18002e49e  mov     [rsp+98h+var_60], r15
0x18002e4a3  cmp     rbp, rdx
0x18002e4a6  jz      short loc_18002E4BF
0x18002e4a8  mov     rdx, rbp
0x18002e4ab  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>>>(std::unique_ptr<EVENT_ENTRY> * const,std::unique_ptr<EVENT_ENTRY> * const,std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>> &)
0x18002e4b0  mov     rdx, [rbx+8]
0x18002e4b4  mov     r8, r12
0x18002e4b7  mov     rcx, rbp
0x18002e4ba  mov     [rsp+98h+var_60], rsi
0x18002e4bf  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>>>(std::unique_ptr<EVENT_ENTRY> * const,std::unique_ptr<EVENT_ENTRY> * const,std::unique_ptr<EVENT_ENTRY> *,std::allocator<std::unique_ptr<EVENT_ENTRY>> &)
0x18002e4c4  mov     rcx, [rbx]
0x18002e4c7  mov     [rsp+98h+var_70], 0
0x18002e4d0  test    rcx, rcx
0x18002e4d3  jz      short loc_18002E4F1
0x18002e4d5  mov     rdx, [rbx+8]
0x18002e4d9  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<EVENT_ENTRY>>>(std::unique_ptr<EVENT_ENTRY> *,std::unique_ptr<EVENT_ENTRY> * const,std::allocator<std::unique_ptr<EVENT_ENTRY>> &)
0x18002e4de  mov     rdx, [rbx+10h]
0x18002e4e2  sub     rdx, [rbx]
0x18002e4e5  mov     rcx, [rbx]
0x18002e4e8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e4ec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e4f1  mov     [rbx], rsi
0x18002e4f4  lea     rcx, [rsi+r14*8]
0x18002e4f8  mov     [rbx+8], rcx
0x18002e4fc  lea     rcx, [rsi+rdi*8]
0x18002e500  mov     [rbx+10h], rcx
0x18002e504  lea     rcx, [rsp+98h+var_78]
0x18002e509  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VEVENT_ENTRY@@U?$default_delete@VEVENT_ENTRY@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<EVENT_ENTRY>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002e50e  mov     rax, r15
0x18002e511  add     rsp, 58h
0x18002e515  pop     r15
0x18002e517  pop     r14
0x18002e519  pop     r13
0x18002e51b  pop     r12
0x18002e51d  pop     rdi
0x18002e51e  pop     rsi
0x18002e51f  pop     rbp
0x18002e520  pop     rbx
0x18002e521  retn
```
