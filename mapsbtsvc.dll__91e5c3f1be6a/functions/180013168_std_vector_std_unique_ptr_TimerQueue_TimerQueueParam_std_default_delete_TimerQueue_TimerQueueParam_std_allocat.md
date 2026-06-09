# std::vector<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> * const,std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>> &&)

- ea: `0x180013168`
- end: `0x1800132af`
- name: `??$_Emplace_reallocate@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `327`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180013384`

## callees

- `0x180003a00`
- `0x180003c34`
- `0x180003c74`
- `0x180003e4c`
- `0x180010d54`
- `0x180013168`
- `0x1800132b8`
- `0x180013348`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // rbp
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // r12
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
    std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Xlength();
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
  v23[0] = a1;
  v17 = &v14[v11];
  v23[2] = v3;
  *v17 = v15;
  v18 = v17 + 1;
  v19 = a1[1];
  v20 = *a1;
  v25 = v17 + 1;
  v24 = v17;
  if ( a2 == v19 )
  {
    v18 = v14;
  }
  else
  {
    std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(
      v20,
      a2,
      v14,
      a1,
      v23[0]);
    v19 = a1[1];
    v20 = a2;
    v24 = v16;
  }
  std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(
    v20,
    v19,
    v18,
    a1,
    v23[0]);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(v21, a1[1]);
    std::_Deallocate<16>((void *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = (__int64)v16;
  a1[1] = (__int64)&v16[v8];
  a1[2] = (__int64)&v16[v3];
  std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v17;
}

```

## disassembly

```asm
0x180013168  push    rbx
0x18001316a  push    rbp
0x18001316b  push    rsi
0x18001316c  push    rdi
0x18001316d  push    r12
0x18001316f  push    r13
0x180013171  push    r14
0x180013173  push    r15
0x180013175  sub     rsp, 58h
0x180013179  mov     rax, [rcx+8]
0x18001317d  mov     rdi, 1FFFFFFFFFFFFFFFh
0x180013187  sub     rax, [rcx]
0x18001318a  mov     r13, r8
0x18001318d  sar     rax, 3
0x180013191  mov     r14, rdx
0x180013194  mov     rbx, rcx
0x180013197  cmp     rax, rdi
0x18001319a  jz      loc_1800132A9
0x1800131a0  mov     r15, rdx
0x1800131a3  lea     rbp, [rax+1]
0x1800131a7  sub     r15, [rcx]
0x1800131aa  mov     rax, rdi
0x1800131ad  mov     rcx, [rcx+10h]
0x1800131b1  sub     rcx, [rbx]
0x1800131b4  sar     rcx, 3
0x1800131b8  mov     rdx, rcx
0x1800131bb  sar     r15, 3
0x1800131bf  shr     rdx, 1
0x1800131c2  sub     rax, rdx
0x1800131c5  cmp     rcx, rax
0x1800131c8  ja      short loc_1800131D5
0x1800131ca  lea     rdi, [rdx+rcx]
0x1800131ce  cmp     rdi, rbp
0x1800131d1  cmovb   rdi, rbp
0x1800131d5  mov     rcx, rdi
0x1800131d8  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800131dd  mov     rcx, rax
0x1800131e0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800131e5  mov     rcx, [r13+0]
0x1800131e9  mov     rsi, rax
0x1800131ec  mov     qword ptr [r13+0], 0
0x1800131f4  mov     [rsp+98h+var_78], rbx
0x1800131f9  lea     r12, [rax+r15*8]
0x1800131fd  mov     [rsp+98h+var_68], rdi
0x180013202  mov     [r12], rcx
0x180013206  lea     r15, [r12+8]
0x18001320b  mov     rdx, [rbx+8]
0x18001320f  mov     rcx, [rbx]
0x180013212  mov     [rsp+98h+var_58], r15
0x180013217  mov     [rsp+98h+var_60], r12
0x18001321c  cmp     r14, rdx
0x18001321f  jnz     short loc_180013226
0x180013221  mov     r15, rax
0x180013224  jmp     short loc_180013240
0x180013226  mov     r9, rbx
0x180013229  mov     r8, rsi
0x18001322c  mov     rdx, r14
0x18001322f  call    ??$_Uninitialized_move@PEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180013234  mov     rdx, [rbx+8]
0x180013238  mov     rcx, r14
0x18001323b  mov     [rsp+98h+var_60], rsi
0x180013240  mov     r9, rbx
0x180013243  mov     r8, r15
0x180013246  call    ??$_Uninitialized_move@PEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> *,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x18001324b  mov     rcx, [rbx]
0x18001324e  mov     [rsp+98h+var_70], 0
0x180013257  test    rcx, rcx
0x18001325a  jz      short loc_180013278
0x18001325c  mov     rdx, [rbx+8]
0x180013260  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>>>(std::unique_ptr<TimerQueue::TimerQueueParam> *,std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam>> &)
0x180013265  mov     rdx, [rbx+10h]
0x180013269  sub     rdx, [rbx]
0x18001326c  mov     rcx, [rbx]
0x18001326f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180013273  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013278  mov     [rbx], rsi
0x18001327b  lea     rcx, [rsi+rbp*8]
0x18001327f  mov     [rbx+8], rcx
0x180013283  lea     rcx, [rsi+rdi*8]
0x180013287  mov     [rbx+10h], rcx
0x18001328b  lea     rcx, [rsp+98h+var_78]
0x180013290  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180013295  mov     rax, r12
0x180013298  add     rsp, 58h
0x18001329c  pop     r15
0x18001329e  pop     r14
0x1800132a0  pop     r13
0x1800132a2  pop     r12
0x1800132a4  pop     rdi
0x1800132a5  pop     rsi
0x1800132a6  pop     rbp
0x1800132a7  pop     rbx
0x1800132a8  retn
0x1800132a9  call    ?_Xlength@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Xlength(void)
```
