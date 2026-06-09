# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Reallocate(unsigned __int64)

- ea: `0x14000bca4`
- end: `0x14000bd83`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000a99c`

## callees

- `0x140001674`
- `0x14000a958`
- `0x14000bca4`
- `0x140010010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000bcf6`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000bcf6`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000bd53`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000bd53`

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
0x14000bca4  mov     [rsp+arg_0], rbx
0x14000bca9  mov     [rsp+arg_10], rsi
0x14000bcae  push    rdi
0x14000bcaf  push    r12
0x14000bcb1  push    r13
0x14000bcb3  push    r14
0x14000bcb5  push    r15
0x14000bcb7  sub     rsp, 30h
0x14000bcbb  mov     r15, rdx
0x14000bcbe  mov     rdi, rcx
0x14000bcc1  xor     ebx, ebx
0x14000bcc3  mov     [rsp+58h+arg_8], rbx
0x14000bcc8  test    rdx, rdx
0x14000bccb  jz      short loc_14000BCFD
0x14000bccd  mov     rax, 1FFFFFFFFFFFFFFFh
0x14000bcd7  cmp     rdx, rax
0x14000bcda  ja      short loc_14000BCF6
0x14000bcdc  lea     rcx, ds:0[rdx*8]; Size
0x14000bce4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000bce9  mov     rbx, rax
0x14000bcec  mov     [rsp+58h+arg_8], rax
0x14000bcf1  test    rax, rax
0x14000bcf4  jnz     short loc_14000BCFD
0x14000bcf6  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000bcfc  nop
0x14000bcfd  lea     rsi, [rdi+8]
0x14000bd01  mov     r8, rbx
0x14000bd04  mov     rdx, [rsi]
0x14000bd07  mov     rcx, [rdi]
0x14000bd0a  call    ??$_Uninit_move@PEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>> &,std::unique_ptr<ProvPackage> *,std::_Nonscalar_ptr_iterator_tag)
0x14000bd0f  nop
0x14000bd10  mov     r14, [rdi]
0x14000bd13  mov     r13, [rsi]
0x14000bd16  mov     r12, r13
0x14000bd19  sub     r12, r14
0x14000bd1c  sar     r12, 3
0x14000bd20  test    r14, r14
0x14000bd23  jz      short loc_14000BD59
0x14000bd25  cmp     r14, r13
0x14000bd28  jz      short loc_14000BD50
0x14000bd2a  mov     rcx, [r14]
0x14000bd2d  test    rcx, rcx
0x14000bd30  jz      short loc_14000BD43
0x14000bd32  mov     rax, [rcx]
0x14000bd35  mov     edx, 1
0x14000bd3a  mov     rax, [rax+40h]
0x14000bd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd43  add     r14, 8
0x14000bd47  cmp     r14, r13
0x14000bd4a  jnz     short loc_14000BD2A
0x14000bd4c  lea     rsi, [rdi+8]
0x14000bd50  mov     rcx, [rdi]
0x14000bd53  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000bd59  lea     rax, [rbx+r15*8]
0x14000bd5d  mov     [rdi+10h], rax
0x14000bd61  lea     rax, [rbx+r12*8]
0x14000bd65  mov     [rsi], rax
0x14000bd68  mov     [rdi], rbx
0x14000bd6b  mov     rbx, [rsp+58h+arg_0]
0x14000bd70  mov     rsi, [rsp+58h+arg_10]
0x14000bd75  add     rsp, 30h
0x14000bd79  pop     r15
0x14000bd7b  pop     r14
0x14000bd7d  pop     r13
0x14000bd7f  pop     r12
0x14000bd81  pop     rdi
0x14000bd82  retn
```
