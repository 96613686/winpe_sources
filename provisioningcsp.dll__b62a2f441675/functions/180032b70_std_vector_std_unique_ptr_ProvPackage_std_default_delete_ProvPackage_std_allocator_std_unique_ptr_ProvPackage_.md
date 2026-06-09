# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Reallocate(unsigned __int64)

- ea: `0x180032b70`
- end: `0x180032c5c`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180031818`

## callees

- `0x180002fd4`
- `0x1800317d4`
- `0x180032b70`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180032c25`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032c25`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180032bc2`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180032bc2`

## pseudocode

```c
char *__fastcall std::vector<std::unique_ptr<ProvPackage>>::_Reallocate(_QWORD *a1, unsigned __int64 a2)
{
  char *v4; // rbx
  __int64 v5; // rcx
  char *v6; // r14
  char *v7; // r13
  __int64 v8; // r12
  char **v9; // rsi
  char *result; // rax
  char *v11; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = (char *)operator new(8 * a2), (v11 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v9 = (char **)(a1 + 1);
    std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v5, v11);
    throw;
  }
  v6 = (char *)*a1;
  v7 = *v9;
  v8 = (__int64)&(*v9)[-*a1] >> 3;
  if ( *a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        if ( *(_QWORD *)v6 )
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v6 + 64LL))(*(_QWORD *)v6, 1);
        v6 += 8;
      }
      while ( v6 != v7 );
      v9 = (char **)(a1 + 1);
    }
    operator delete((void *)*a1);
  }
  a1[2] = &v4[8 * a2];
  result = &v4[8 * v8];
  *v9 = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180032b70  mov     [rsp+arg_0], rbx
0x180032b75  mov     [rsp+arg_10], rsi
0x180032b7a  push    rdi
0x180032b7b  push    r12
0x180032b7d  push    r13
0x180032b7f  push    r14
0x180032b81  push    r15
0x180032b83  sub     rsp, 30h
0x180032b87  mov     r15, rdx
0x180032b8a  mov     rdi, rcx
0x180032b8d  xor     ebx, ebx
0x180032b8f  mov     [rsp+58h+arg_8], rbx
0x180032b94  test    rdx, rdx
0x180032b97  jz      short loc_180032BCF
0x180032b99  mov     rax, 1FFFFFFFFFFFFFFFh
0x180032ba3  cmp     rdx, rax
0x180032ba6  ja      short loc_180032BC2
0x180032ba8  lea     rcx, ds:0[rdx*8]; Size
0x180032bb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032bb5  mov     rbx, rax
0x180032bb8  mov     [rsp+58h+arg_8], rax
0x180032bbd  test    rax, rax
0x180032bc0  jnz     short loc_180032BCF
0x180032bc2  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180032bc9  nop     dword ptr [rax+rax+00h]
0x180032bce  nop
0x180032bcf  lea     rsi, [rdi+8]
0x180032bd3  mov     r8, rbx
0x180032bd6  mov     rdx, [rsi]
0x180032bd9  mov     rcx, [rdi]
0x180032bdc  call    ??$_Uninit_move@PEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>> &,std::unique_ptr<ProvPackage> *,std::_Nonscalar_ptr_iterator_tag)
0x180032be1  nop
0x180032be2  mov     r14, [rdi]
0x180032be5  mov     r13, [rsi]
0x180032be8  mov     r12, r13
0x180032beb  sub     r12, r14
0x180032bee  sar     r12, 3
0x180032bf2  test    r14, r14
0x180032bf5  jz      short loc_180032C31
0x180032bf7  cmp     r14, r13
0x180032bfa  jz      short loc_180032C22
0x180032bfc  mov     rcx, [r14]
0x180032bff  test    rcx, rcx
0x180032c02  jz      short loc_180032C15
0x180032c04  mov     rax, [rcx]
0x180032c07  mov     edx, 1
0x180032c0c  mov     rax, [rax+40h]
0x180032c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c15  add     r14, 8
0x180032c19  cmp     r14, r13
0x180032c1c  jnz     short loc_180032BFC
0x180032c1e  lea     rsi, [rdi+8]
0x180032c22  mov     rcx, [rdi]
0x180032c25  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032c2c  nop     dword ptr [rax+rax+00h]
0x180032c31  lea     rax, [rbx+r15*8]
0x180032c35  mov     [rdi+10h], rax
0x180032c39  lea     rax, [rbx+r12*8]
0x180032c3d  mov     [rsi], rax
0x180032c40  mov     [rdi], rbx
0x180032c43  mov     rbx, [rsp+58h+arg_0]
0x180032c48  mov     rsi, [rsp+58h+arg_10]
0x180032c4d  add     rsp, 30h
0x180032c51  pop     r15
0x180032c53  pop     r14
0x180032c55  pop     r13
0x180032c57  pop     r12
0x180032c59  pop     rdi
0x180032c5a  retn
```
