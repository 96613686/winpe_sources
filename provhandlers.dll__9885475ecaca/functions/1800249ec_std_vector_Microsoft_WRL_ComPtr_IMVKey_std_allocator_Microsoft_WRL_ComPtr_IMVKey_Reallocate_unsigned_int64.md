# std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>>::_Reallocate(unsigned __int64)

- ea: `0x1800249ec`
- end: `0x180024ace`
- name: `?_Reallocate@?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z`
- size: `226`
- prototype: `__int64 *__fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024ad4`

## callees

- `0x180002034`
- `0x180015ce0`
- `0x1800249ec`
- `0x18003f010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180024a3e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180024a3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024a9e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024a9e`

## pseudocode

```c
__int64 *__fastcall std::vector<Microsoft::WRL::ComPtr<IMVKey>>::_Reallocate(void **a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // rdi
  __int64 *v7; // r13
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 **v10; // r14
  __int64 *result; // rax
  _QWORD *v12; // [rsp+68h] [rbp+10h]

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
    std::_Uninit_move<Microsoft::WRL::ComPtr<IMVKey> *,Microsoft::WRL::ComPtr<IMVKey> *,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>,Microsoft::WRL::ComPtr<IMVKey>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v5, v12);
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
0x1800249ec  mov     [rsp+arg_0], rbx
0x1800249f1  mov     [rsp+arg_10], rsi
0x1800249f6  push    rdi
0x1800249f7  push    r12
0x1800249f9  push    r13
0x1800249fb  push    r14
0x1800249fd  push    r15
0x1800249ff  sub     rsp, 30h
0x180024a03  mov     r15, rdx
0x180024a06  mov     rsi, rcx
0x180024a09  xor     ebx, ebx
0x180024a0b  mov     [rsp+58h+arg_8], rbx
0x180024a10  test    rdx, rdx
0x180024a13  jz      short loc_180024A45
0x180024a15  mov     rax, 1FFFFFFFFFFFFFFFh
0x180024a1f  cmp     rdx, rax
0x180024a22  ja      short loc_180024A3E
0x180024a24  lea     rcx, ds:0[rdx*8]; Size
0x180024a2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024a31  mov     rbx, rax
0x180024a34  mov     [rsp+58h+arg_8], rax
0x180024a39  test    rax, rax
0x180024a3c  jnz     short loc_180024A45
0x180024a3e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180024a44  nop
0x180024a45  lea     r14, [rsi+8]
0x180024a49  mov     r8, rbx
0x180024a4c  mov     rdx, [r14]
0x180024a4f  mov     rcx, [rsi]
0x180024a52  call    ??$_Uninit_move@PEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V123@@std@@YAPEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Microsoft::WRL::ComPtr<IMVKey> *,Microsoft::WRL::ComPtr<IMVKey> *,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>,Microsoft::WRL::ComPtr<IMVKey>>(Microsoft::WRL::ComPtr<IMVKey> *,Microsoft::WRL::ComPtr<IMVKey> *,Microsoft::WRL::ComPtr<IMVKey> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> &,Microsoft::WRL::ComPtr<IMVKey> *,std::_Nonscalar_ptr_iterator_tag)
0x180024a57  nop
0x180024a58  mov     rdi, [rsi]
0x180024a5b  mov     r13, [r14]
0x180024a5e  mov     r12, r13
0x180024a61  sub     r12, rdi
0x180024a64  sar     r12, 3
0x180024a68  test    rdi, rdi
0x180024a6b  jz      short loc_180024AA4
0x180024a6d  cmp     rdi, r13
0x180024a70  jz      short loc_180024A9B
0x180024a72  mov     rcx, [rdi]
0x180024a75  test    rcx, rcx
0x180024a78  jz      short loc_180024A8E
0x180024a7a  mov     qword ptr [rdi], 0
0x180024a81  mov     rax, [rcx]
0x180024a84  mov     rax, [rax+10h]
0x180024a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a8d  nop
0x180024a8e  add     rdi, 8
0x180024a92  cmp     rdi, r13
0x180024a95  jnz     short loc_180024A72
0x180024a97  lea     r14, [rsi+8]
0x180024a9b  mov     rcx, [rsi]
0x180024a9e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024aa4  lea     rax, [rbx+r15*8]
0x180024aa8  mov     [rsi+10h], rax
0x180024aac  lea     rax, [rbx+r12*8]
0x180024ab0  mov     [r14], rax
0x180024ab3  mov     [rsi], rbx
0x180024ab6  mov     rbx, [rsp+58h+arg_0]
0x180024abb  mov     rsi, [rsp+58h+arg_10]
0x180024ac0  add     rsp, 30h
0x180024ac4  pop     r15
0x180024ac6  pop     r14
0x180024ac8  pop     r13
0x180024aca  pop     r12
0x180024acc  pop     rdi
0x180024acd  retn
```
