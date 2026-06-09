# std::vector<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>::_Emplace_reallocate<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> * const,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> &&)

- ea: `0x1800072cc`
- end: `0x180007426`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000670c`

## callees

- `0x180005e14`
- `0x180006e2c`
- `0x1800070a8`
- `0x1800072cc`
- `0x180008f38`
- `0x18000a3c0`
- `0x18000fbfc`
- `0x1800105f8`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<D3DCoreModule>>::_Emplace_reallocate<std::unique_ptr<D3DCoreModule>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v7; // rax
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rdi
  _QWORD *v13; // r8
  _QWORD *v14; // rbp
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD v20[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-60h]
  _QWORD *v22; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v4 = 0x1FFFFFFFFFFFFFFFLL;
  v7 = (a1[1] - *a1) >> 3;
  if ( v7 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::unique_ptr<D3DCoreModule>>::_Xlength();
  v8 = v7 + 1;
  v9 = (a1[2] - v3) >> 3;
  if ( v9 <= 0x1FFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v10 = (v9 >> 1) + v9;
    v11 = v8;
    if ( v10 >= v8 )
      v11 = v10;
    if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v4 = v11;
  }
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v4);
  v20[0] = a1;
  v20[2] = v4;
  v13 = (_QWORD *)v12;
  v14 = (_QWORD *)(v12 + 8 * ((a2 - v3) >> 3));
  v21 = v14;
  v22 = v14 + 1;
  v15 = *a3;
  *a3 = 0;
  *v14 = v15;
  v16 = a1[1];
  v17 = *a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>>>(
      v17,
      a2,
      v12);
    v16 = a1[1];
    v13 = v14 + 1;
    v17 = a2;
    v21 = (_QWORD *)v12;
  }
  std::_Uninitialized_move<std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>>>(
    v17,
    v16,
    v13);
  v18 = *a1;
  v20[1] = 0;
  if ( v18 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(v18, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v12;
  a1[1] = v12 + 8 * v8;
  a1[2] = 8 * v4 + v12;
  std::vector<std::unique_ptr<D3DCoreModule>>::_Reallocation_guard::~_Reallocation_guard(v20);
  return v14;
}

```

## disassembly

```asm
0x1800072cc  mov     [rsp+arg_10], r8
0x1800072d1  push    rbx
0x1800072d2  push    rbp
0x1800072d3  push    rsi
0x1800072d4  push    rdi
0x1800072d5  push    r12
0x1800072d7  push    r13
0x1800072d9  push    r14
0x1800072db  push    r15
0x1800072dd  sub     rsp, 58h
0x1800072e1  mov     rbp, [rcx]
0x1800072e4  mov     rsi, 1FFFFFFFFFFFFFFFh
0x1800072ee  mov     rax, [rcx+8]
0x1800072f2  mov     r15, rdx
0x1800072f5  sub     rax, rbp
0x1800072f8  mov     rbx, rcx
0x1800072fb  sar     rax, 3
0x1800072ff  cmp     rax, rsi
0x180007302  jz      loc_180007420
0x180007308  mov     rcx, [rcx+10h]
0x18000730c  lea     r14, [rax+1]
0x180007310  sub     rcx, rbp
0x180007313  mov     rax, rsi
0x180007316  sar     rcx, 3
0x18000731a  mov     rdx, rcx
0x18000731d  shr     rdx, 1
0x180007320  sub     rax, rdx
0x180007323  cmp     rcx, rax
0x180007326  ja      short loc_180007342
0x180007328  lea     rax, [rdx+rcx]
0x18000732c  mov     rcx, r14
0x18000732f  cmp     rax, r14
0x180007332  cmovnb  rcx, rax
0x180007336  cmp     rcx, rsi
0x180007339  ja      loc_18000741A
0x18000733f  mov     rsi, rcx
0x180007342  lea     r12, ds:0[rsi*8]
0x18000734a  mov     rcx, r12
0x18000734d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180007352  mov     rdi, rax
0x180007355  mov     [rsp+98h+var_78], rbx
0x18000735a  mov     rcx, r15
0x18000735d  mov     [rsp+98h+var_68], rsi
0x180007362  sub     rcx, rbp
0x180007365  mov     r8, rdi
0x180007368  sar     rcx, 3
0x18000736c  lea     rbp, [rax+rcx*8]
0x180007370  mov     rax, [rsp+98h+arg_10]
0x180007378  lea     r13, [rbp+8]
0x18000737c  mov     [rsp+98h+var_60], rbp
0x180007381  mov     [rsp+98h+var_58], r13
0x180007386  mov     rcx, [rax]
0x180007389  mov     qword ptr [rax], 0
0x180007390  mov     [rbp+0], rcx
0x180007394  mov     rdx, [rbx+8]
0x180007398  mov     rcx, [rbx]
0x18000739b  cmp     r15, rdx
0x18000739e  jz      short loc_1800073B7
0x1800073a0  mov     rdx, r15
0x1800073a3  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule> * const,std::unique_ptr<D3DCoreModule> * const,std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>> &)
0x1800073a8  mov     rdx, [rbx+8]
0x1800073ac  mov     r8, r13
0x1800073af  mov     rcx, r15
0x1800073b2  mov     [rsp+98h+var_60], rdi
0x1800073b7  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule> * const,std::unique_ptr<D3DCoreModule> * const,std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>> &)
0x1800073bc  mov     rcx, [rbx]
0x1800073bf  mov     [rsp+98h+var_70], 0
0x1800073c8  test    rcx, rcx
0x1800073cb  jz      short loc_1800073E9
0x1800073cd  mov     rdx, [rbx+8]
0x1800073d1  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule> *,std::unique_ptr<D3DCoreModule> * const,std::allocator<std::unique_ptr<D3DCoreModule>> &)
0x1800073d6  mov     rdx, [rbx+10h]
0x1800073da  sub     rdx, [rbx]
0x1800073dd  mov     rcx, [rbx]
0x1800073e0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800073e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800073e9  mov     [rbx], rdi
0x1800073ec  lea     rcx, [rdi+r14*8]
0x1800073f0  mov     [rbx+8], rcx
0x1800073f4  lea     rcx, [r12+rdi]
0x1800073f8  mov     [rbx+10h], rcx
0x1800073fc  lea     rcx, [rsp+98h+var_78]
0x180007401  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<D3DCoreModule>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180007406  mov     rax, rbp
0x180007409  add     rsp, 58h
0x18000740d  pop     r15
0x18000740f  pop     r14
0x180007411  pop     r13
0x180007413  pop     r12
0x180007415  pop     rdi
0x180007416  pop     rsi
0x180007417  pop     rbp
0x180007418  pop     rbx
0x180007419  retn
0x18000741a  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180007420  call    ?_Xlength@?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::unique_ptr<D3DCoreModule>>::_Xlength(void)
```
