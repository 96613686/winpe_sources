# std::vector<Microsoft::WRL::ComPtr<IMVHandler>,std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>>::_Reallocate(unsigned __int64)

- ea: `0x180021904`
- end: `0x1800219e6`
- name: `?_Reallocate@?$vector@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z`
- size: `226`
- prototype: `__int64 *__fastcall(void **, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001d25c`
- `0x18001d924`

## callees

- `0x1800021b4`
- `0x18000f110`
- `0x180021904`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180021956`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180021956`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800219b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800219b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall std::vector<Microsoft::WRL::ComPtr<IMVHandler>>::_Reallocate(void **a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // rdi
  __int64 *v7; // r13
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 **v10; // r14
  __int64 *result; // rax
  void *v12; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v12 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2), (v12 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v10 = (__int64 **)(a1 + 1);
    std::_Uninit_move<Microsoft::WRL::ComPtr<IMVHandler> *,Microsoft::WRL::ComPtr<IMVHandler> *,std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>,Microsoft::WRL::ComPtr<IMVHandler>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v5, v12);
    throw;
  }
  v6 = (__int64 *)*a1;
  v7 = *v10;
  v8 = ((char *)*v10 - (_BYTE *)*a1) >> 3;
  if ( *a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        v9 = *v6;
        if ( *v6 )
        {
          *v6 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        ++v6;
      }
      while ( v6 != v7 );
      v10 = (__int64 **)(a1 + 1);
    }
    operator delete(*a1);
  }
  a1[2] = &v4[a2];
  result = &v4[v8];
  *v10 = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180021904  mov     [rsp+arg_0], rbx
0x180021909  mov     [rsp+arg_10], rsi
0x18002190e  push    rdi
0x18002190f  push    r12
0x180021911  push    r13
0x180021913  push    r14
0x180021915  push    r15
0x180021917  sub     rsp, 30h
0x18002191b  mov     r15, rdx
0x18002191e  mov     rsi, rcx
0x180021921  xor     ebx, ebx
0x180021923  mov     [rsp+58h+arg_8], rbx
0x180021928  test    rdx, rdx
0x18002192b  jz      short loc_18002195D
0x18002192d  mov     rax, 1FFFFFFFFFFFFFFFh
0x180021937  cmp     rdx, rax
0x18002193a  ja      short loc_180021956
0x18002193c  lea     rcx, ds:0[rdx*8]; Size
0x180021944  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021949  mov     rbx, rax
0x18002194c  mov     [rsp+58h+arg_8], rax
0x180021951  test    rax, rax
0x180021954  jnz     short loc_18002195D
0x180021956  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002195c  nop
0x18002195d  lea     r14, [rsi+8]
0x180021961  mov     r8, rbx
0x180021964  mov     rdx, [r14]
0x180021967  mov     rcx, [rsi]
0x18002196a  call    ??$_Uninit_move@PEAV?$ComPtr@UIMVHandler@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@@std@@V123@@std@@YAPEAV?$ComPtr@UIMVHandler@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Microsoft::WRL::ComPtr<IMVHandler> *,Microsoft::WRL::ComPtr<IMVHandler> *,std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>,Microsoft::WRL::ComPtr<IMVHandler>>(Microsoft::WRL::ComPtr<IMVHandler> *,Microsoft::WRL::ComPtr<IMVHandler> *,Microsoft::WRL::ComPtr<IMVHandler> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>> &,Microsoft::WRL::ComPtr<IMVHandler> *,std::_Nonscalar_ptr_iterator_tag)
0x18002196f  nop
0x180021970  mov     rdi, [rsi]
0x180021973  mov     r13, [r14]
0x180021976  mov     r12, r13
0x180021979  sub     r12, rdi
0x18002197c  sar     r12, 3
0x180021980  test    rdi, rdi
0x180021983  jz      short loc_1800219BC
0x180021985  cmp     rdi, r13
0x180021988  jz      short loc_1800219B3
0x18002198a  mov     rcx, [rdi]
0x18002198d  test    rcx, rcx
0x180021990  jz      short loc_1800219A6
0x180021992  mov     qword ptr [rdi], 0
0x180021999  mov     rax, [rcx]
0x18002199c  mov     rax, [rax+10h]
0x1800219a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219a5  nop
0x1800219a6  add     rdi, 8
0x1800219aa  cmp     rdi, r13
0x1800219ad  jnz     short loc_18002198A
0x1800219af  lea     r14, [rsi+8]
0x1800219b3  mov     rcx, [rsi]
0x1800219b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800219bc  lea     rax, [rbx+r15*8]
0x1800219c0  mov     [rsi+10h], rax
0x1800219c4  lea     rax, [rbx+r12*8]
0x1800219c8  mov     [r14], rax
0x1800219cb  mov     [rsi], rbx
0x1800219ce  mov     rbx, [rsp+58h+arg_0]
0x1800219d3  mov     rsi, [rsp+58h+arg_10]
0x1800219d8  add     rsp, 30h
0x1800219dc  pop     r15
0x1800219de  pop     r14
0x1800219e0  pop     r13
0x1800219e2  pop     r12
0x1800219e4  pop     rdi
0x1800219e5  retn
```
