# std::vector<std::unique_ptr<NetSetup2::Mux,std::default_delete<NetSetup2::Mux>>,std::allocator<std::unique_ptr<NetSetup2::Mux,std::default_delete<NetSetup2::Mux>>>>::_Reallocate(unsigned __int64)

- ea: `0x180026f34`
- end: `0x180026fd8`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `164`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800256f0`
- `0x180027064`
- `0x18002af2c`

## callees

- `0x180001274`
- `0x180001418`
- `0x18002568c`
- `0x180025c98`
- `0x180026f34`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026fb5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026fb5`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<NetSetup2::Mux>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rsi
  _QWORD *result; // rax

  v3 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = a2, (v3 = operator new(8 * a2)) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  std::_Uninit_move<std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *,std::allocator<std::unique_ptr<NetSetup2::Mux>>,std::unique_ptr<NetSetup2::Mux>>(
    *(__int64 **)a1,
    *(__int64 **)(a1 + 8),
    v3);
  v6 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
  {
    std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(v5, *(void ***)a1, *(void ***)(a1 + 8));
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v3[v4];
  result = &v3[v6];
  *(_QWORD *)(a1 + 8) = result;
  *(_QWORD *)a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180026f34  push    rbx
0x180026f36  push    rsi
0x180026f37  push    rdi
0x180026f38  push    r14
0x180026f3a  sub     rsp, 38h
0x180026f3e  mov     rdi, rcx
0x180026f41  xor     ebx, ebx
0x180026f43  mov     [rsp+58h+arg_8], rbx
0x180026f48  test    rdx, rdx
0x180026f4b  jz      short loc_180026F7F
0x180026f4d  mov     rax, 1FFFFFFFFFFFFFFFh
0x180026f57  cmp     rdx, rax
0x180026f5a  ja      short loc_180026F79
0x180026f5c  lea     r14, ds:0[rdx*8]
0x180026f64  mov     rcx, r14; Size
0x180026f67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026f6c  mov     rbx, rax
0x180026f6f  mov     [rsp+58h+arg_8], rax
0x180026f74  test    rax, rax
0x180026f77  jnz     short loc_180026F87
0x180026f79  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180026f7f  lea     r14, ds:0[rdx*8]
0x180026f87  mov     r8, rbx
0x180026f8a  mov     rdx, [rdi+8]
0x180026f8e  mov     rcx, [rdi]
0x180026f91  call    ??$_Uninit_move@PEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *,std::allocator<std::unique_ptr<NetSetup2::Mux>>,std::unique_ptr<NetSetup2::Mux>>(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<NetSetup2::Mux>>> &,std::unique_ptr<NetSetup2::Mux> *,std::_Nonscalar_ptr_iterator_tag)
0x180026f96  nop
0x180026f97  mov     rdx, [rdi]
0x180026f9a  mov     r8, [rdi+8]
0x180026f9e  mov     rsi, r8
0x180026fa1  sub     rsi, rdx
0x180026fa4  sar     rsi, 3
0x180026fa8  test    rdx, rdx
0x180026fab  jz      short loc_180026FBB
0x180026fad  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x180026fb2  mov     rcx, [rdi]
0x180026fb5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026fbb  lea     rax, [r14+rbx]
0x180026fbf  mov     [rdi+10h], rax
0x180026fc3  lea     rax, [rbx+rsi*8]
0x180026fc7  mov     [rdi+8], rax
0x180026fcb  mov     [rdi], rbx
0x180026fce  add     rsp, 38h
0x180026fd2  pop     r14
0x180026fd4  pop     rdi
0x180026fd5  pop     rsi
0x180026fd6  pop     rbx
0x180026fd7  retn
```
