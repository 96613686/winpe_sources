# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Reallocate(unsigned __int64)

- ea: `0x180025f80`
- end: `0x18002605f`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `223`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180026068`

## callees

- `0x180002f44`
- `0x1800230a0`
- `0x180025f80`
- `0x180037010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180025fd2`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180025fd2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002602f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002602f`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<ProvPackage>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  __int64 *v6; // r14
  __int64 *v7; // r13
  __int64 v8; // r12
  _QWORD *result; // rax

  v4 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2)) == 0 )
      std::_Xbad_alloc();
  }
  v5 = (_QWORD *)(a1 + 8);
  std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(
    *(__int64 **)a1,
    *(__int64 **)(a1 + 8),
    v4);
  v6 = *(__int64 **)a1;
  v7 = *(__int64 **)(a1 + 8);
  v8 = ((__int64)v7 - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        if ( *v6 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v6 + 64LL))(*v6, 1);
        ++v6;
      }
      while ( v6 != v7 );
      v5 = (_QWORD *)(a1 + 8);
    }
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v4[a2];
  result = &v4[v8];
  *v5 = result;
  *(_QWORD *)a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180025f80  mov     [rsp+arg_0], rbx
0x180025f85  mov     [rsp+arg_10], rsi
0x180025f8a  push    rdi
0x180025f8b  push    r12
0x180025f8d  push    r13
0x180025f8f  push    r14
0x180025f91  push    r15
0x180025f93  sub     rsp, 30h
0x180025f97  mov     r15, rdx
0x180025f9a  mov     rdi, rcx
0x180025f9d  xor     ebx, ebx
0x180025f9f  mov     [rsp+58h+arg_8], rbx
0x180025fa4  test    rdx, rdx
0x180025fa7  jz      short loc_180025FD9
0x180025fa9  mov     rax, 1FFFFFFFFFFFFFFFh
0x180025fb3  cmp     rdx, rax
0x180025fb6  ja      short loc_180025FD2
0x180025fb8  lea     rcx, ds:0[rdx*8]; Size
0x180025fc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025fc5  mov     rbx, rax
0x180025fc8  mov     [rsp+58h+arg_8], rax
0x180025fcd  test    rax, rax
0x180025fd0  jnz     short loc_180025FD9
0x180025fd2  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180025fd8  nop
0x180025fd9  lea     rsi, [rdi+8]
0x180025fdd  mov     r8, rbx
0x180025fe0  mov     rdx, [rsi]
0x180025fe3  mov     rcx, [rdi]
0x180025fe6  call    ??$_Uninit_move@PEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>> &,std::unique_ptr<ProvPackage> *,std::_Nonscalar_ptr_iterator_tag)
0x180025feb  nop
0x180025fec  mov     r14, [rdi]
0x180025fef  mov     r13, [rsi]
0x180025ff2  mov     r12, r13
0x180025ff5  sub     r12, r14
0x180025ff8  sar     r12, 3
0x180025ffc  test    r14, r14
0x180025fff  jz      short loc_180026035
0x180026001  cmp     r14, r13
0x180026004  jz      short loc_18002602C
0x180026006  mov     rcx, [r14]
0x180026009  test    rcx, rcx
0x18002600c  jz      short loc_18002601F
0x18002600e  mov     rax, [rcx]
0x180026011  mov     edx, 1
0x180026016  mov     rax, [rax+40h]
0x18002601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002601f  add     r14, 8
0x180026023  cmp     r14, r13
0x180026026  jnz     short loc_180026006
0x180026028  lea     rsi, [rdi+8]
0x18002602c  mov     rcx, [rdi]
0x18002602f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026035  lea     rax, [rbx+r15*8]
0x180026039  mov     [rdi+10h], rax
0x18002603d  lea     rax, [rbx+r12*8]
0x180026041  mov     [rsi], rax
0x180026044  mov     [rdi], rbx
0x180026047  mov     rbx, [rsp+58h+arg_0]
0x18002604c  mov     rsi, [rsp+58h+arg_10]
0x180026051  add     rsp, 30h
0x180026055  pop     r15
0x180026057  pop     r14
0x180026059  pop     r13
0x18002605b  pop     r12
0x18002605d  pop     rdi
0x18002605e  retn
```
