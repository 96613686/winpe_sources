# std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>>::_Growmap(unsigned __int64)

- ea: `0x18001233c`
- end: `0x18001248c`
- name: `?_Growmap@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAX_K@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee70`

## callees

- `0x180004154`
- `0x180004958`
- `0x1800049b8`
- `0x180008be0`
- `0x180009d6c`
- `0x18001233c`
- `0x18002834c`

## pseudocode

```c
void *__fastcall std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Growmap(
        _QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 size_of; // rax
  char *v6; // r14
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  void *result; // rax
  __int64 v18; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::_Xlength_error("deque<T> too long");
    v2 *= 2LL;
  }
  v4 = a1[3] >> 1;
  size_of = std::_Get_size_of_n<8>(v2);
  v6 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = 8 * v4;
  v8 = &v6[8 * v4];
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v7;
  memmove_0(v8, (const void *)(a1[1] + v7), v12);
  v13 = (const void *)a1[1];
  v14 = &v8[v12];
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v7 - 8 * v11);
    v16 = &v6[v7 - 8 * v11];
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v7], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = v6;
  }
  result = memset_0(v16, 0, v15);
  v18 = a1[1];
  if ( v18 )
    result = (void *)std::_Deallocate<16>(v18, 8LL * a1[2]);
  a1[1] = v6;
  a1[2] += v11;
  return result;
}

```

## disassembly

```asm
0x18001233c  push    rbx
0x18001233e  push    rbp
0x18001233f  push    rsi
0x180012340  push    rdi
0x180012341  push    r12
0x180012343  push    r14
0x180012345  push    r15
0x180012347  sub     rsp, 20h
0x18001234b  mov     rbp, rcx
0x18001234e  mov     esi, 1
0x180012353  mov     rcx, [rcx+10h]
0x180012357  test    rcx, rcx
0x18001235a  cmovnz  rsi, rcx
0x18001235e  mov     rax, rsi
0x180012361  sub     rax, rcx
0x180012364  cmp     rax, 1
0x180012368  jb      short loc_180012370
0x18001236a  cmp     rsi, 8
0x18001236e  jnb     short loc_18001238B
0x180012370  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001237a  sub     rax, rsi
0x18001237d  cmp     rax, rsi
0x180012380  jb      loc_18001247F
0x180012386  add     rsi, rsi
0x180012389  jmp     short loc_18001235E
0x18001238b  mov     rdi, [rbp+18h]
0x18001238f  mov     rcx, rsi
0x180012392  shr     rdi, 1
0x180012395  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001239a  mov     rcx, rax
0x18001239d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800123a2  mov     r14, rax
0x1800123a5  lea     r15, ds:0[rdi*8]
0x1800123ad  lea     r12, [r15+rax]
0x1800123b1  mov     rax, rsi
0x1800123b4  shr     rax, 1
0x1800123b7  jmp     short loc_1800123BC
0x1800123b9  add     rsi, rsi
0x1800123bc  cmp     rsi, rax
0x1800123bf  jbe     short loc_1800123B9
0x1800123c1  mov     rcx, [rbp+8]
0x1800123c5  mov     rax, [rbp+10h]
0x1800123c9  sub     rsi, rax
0x1800123cc  shl     rax, 3
0x1800123d0  lea     rdx, [rcx+r15]; Src
0x1800123d4  sub     rax, rdx
0x1800123d7  lea     rbx, [rax+rcx]
0x1800123db  mov     rcx, r12; void *
0x1800123de  mov     r8, rbx; Size
0x1800123e1  call    memmove_0
0x1800123e6  mov     rdx, [rbp+8]; Src
0x1800123ea  add     rbx, r12
0x1800123ed  mov     rcx, rbx; void *
0x1800123f0  cmp     rdi, rsi
0x1800123f3  ja      short loc_18001241A
0x1800123f5  mov     r8, r15; Size
0x1800123f8  call    memmove_0
0x1800123fd  mov     r8, rsi
0x180012400  lea     rcx, [rbx+r15]; void *
0x180012404  sub     r8, rdi
0x180012407  xor     edx, edx; Val
0x180012409  shl     r8, 3; Size
0x18001240d  call    memset_0
0x180012412  mov     r8, r15
0x180012415  mov     rcx, r14
0x180012418  jmp     short loc_18001244B
0x18001241a  lea     rdi, ds:0[rsi*8]
0x180012422  mov     r8, rdi; Size
0x180012425  call    memmove_0
0x18001242a  mov     rax, [rbp+8]
0x18001242e  mov     rcx, r14; void *
0x180012431  lea     rdx, [rdi+rax]; Src
0x180012435  sub     rax, rdx
0x180012438  lea     rbx, [rax+r15]
0x18001243c  mov     r8, rbx; Size
0x18001243f  call    memmove_0
0x180012444  lea     rcx, [rbx+r14]; void *
0x180012448  mov     r8, rdi; Size
0x18001244b  xor     edx, edx; Val
0x18001244d  call    memset_0
0x180012452  mov     rcx, [rbp+8]
0x180012456  test    rcx, rcx
0x180012459  jz      short loc_180012468
0x18001245b  mov     rdx, [rbp+10h]
0x18001245f  shl     rdx, 3
0x180012463  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012468  mov     [rbp+8], r14
0x18001246c  add     [rbp+10h], rsi
0x180012470  add     rsp, 20h
0x180012474  pop     r15
0x180012476  pop     r14
0x180012478  pop     r12
0x18001247a  pop     rdi
0x18001247b  pop     rsi
0x18001247c  pop     rbp
0x18001247d  pop     rbx
0x18001247e  retn
0x18001247f  lea     rcx, aDequeTTooLong; "deque<T> too long"
0x180012486  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
