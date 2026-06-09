# std::vector<web::json::value,std::allocator<web::json::value>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x1400055e0`
- end: `0x1400057a4`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `452`
- prototype: `char *__fastcall(char **, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140007e60`

## callees

- `0x140002f84`
- `0x140003244`
- `0x1400055e0`
- `0x140005d00`
- `0x140007030`
- `0x140013dd0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall std::vector<web::json::value>::_Resize_reallocate<std::_Value_init_tag>(
        char **a1,
        unsigned __int64 a2)
{
  char *v4; // r12
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rbx
  char *v8; // rbp
  unsigned __int64 v9; // r14
  _QWORD *v10; // rsi
  void *v11; // rax
  char *v12; // r8
  _QWORD *v13; // rdx
  char *i; // rcx
  __int64 v15; // rax
  char *v16; // rbx
  char *j; // rbp
  char *v18; // rcx
  char *v19; // rax
  char *result; // rax

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v4 = *a1;
  v5 = (a1[2] - *a1) >> 3;
  v6 = v5 >> 1;
  if ( v5 > 0x1FFFFFFFFFFFFFFFLL - (v5 >> 1) )
    goto LABEL_28;
  v7 = v5 + v6;
  if ( v5 + v6 >= a2 )
  {
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      goto LABEL_28;
  }
  else
  {
    v7 = a2;
  }
  v8 = a1[1];
  v9 = 8 * v7;
  if ( !(8 * v7) )
  {
    v10 = 0;
    goto LABEL_14;
  }
  if ( v9 < 0x1000 )
  {
    v10 = operator new(8 * v7);
    goto LABEL_14;
  }
  if ( v9 + 39 < v9 )
LABEL_28:
    __scrt_throw_std_bad_array_new_length();
  v11 = operator new(v9 + 39);
  if ( !v11 )
    __fastfail(5u);
  v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v10 - 1) = v11;
LABEL_14:
  std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(
    &v10[(v8 - v4) >> 3],
    a2 - ((v8 - v4) >> 3),
    a1);
  v12 = a1[1];
  v13 = v10;
  for ( i = *a1; i != v12; i += 8 )
  {
    v15 = *(_QWORD *)i;
    *(_QWORD *)i = 0;
    *v13++ = v15;
  }
  v16 = *a1;
  if ( *a1 )
  {
    for ( j = a1[1]; v16 != j; v16 += 8 )
    {
      if ( *(_QWORD *)v16 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v16 + 192LL))(*(_QWORD *)v16, 1);
    }
    v18 = *a1;
    if ( (unsigned __int64)(8 * ((a1[2] - *a1) >> 3)) < 0x1000 )
    {
      v19 = *a1;
    }
    else
    {
      v19 = (char *)*((_QWORD *)v18 - 1);
      if ( (unsigned __int64)(v18 - v19 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v19);
  }
  *a1 = (char *)v10;
  a1[1] = (char *)&v10[a2];
  result = (char *)&v10[v9 / 8];
  a1[2] = (char *)&v10[v9 / 8];
  return result;
}

```

## disassembly

```asm
0x1400055e0  push    rbx
0x1400055e2  push    rbp
0x1400055e3  push    rsi
0x1400055e4  push    rdi
0x1400055e5  push    r12
0x1400055e7  push    r13
0x1400055e9  push    r14
0x1400055eb  push    r15
0x1400055ed  sub     rsp, 58h
0x1400055f1  mov     r15, rdx
0x1400055f4  mov     rdi, rcx
0x1400055f7  mov     r8, 1FFFFFFFFFFFFFFFh
0x140005601  cmp     rdx, r8
0x140005604  ja      loc_140005798
0x14000560a  mov     r12, [rcx]
0x14000560d  mov     rcx, [rcx+10h]
0x140005611  sub     rcx, r12
0x140005614  sar     rcx, 3
0x140005618  mov     rdx, rcx
0x14000561b  shr     rdx, 1
0x14000561e  mov     rax, r8
0x140005621  sub     rax, rdx
0x140005624  cmp     rcx, rax
0x140005627  ja      loc_14000579E
0x14000562d  lea     rbx, [rcx+rdx]
0x140005631  cmp     rbx, r15
0x140005634  jnb     short loc_14000563B
0x140005636  mov     rbx, r15
0x140005639  jmp     short loc_140005644
0x14000563b  cmp     rbx, r8
0x14000563e  ja      loc_14000579E
0x140005644  mov     rbp, [rdi+8]
0x140005648  lea     r14, ds:0[rbx*8]
0x140005650  xor     r13d, r13d
0x140005653  test    r14, r14
0x140005656  jnz     short loc_14000565D
0x140005658  mov     esi, r13d
0x14000565b  jmp     short loc_14000569D
0x14000565d  cmp     r14, 1000h
0x140005664  jb      short loc_140005692
0x140005666  lea     rcx, [r14+27h]; Size
0x14000566a  cmp     rcx, r14
0x14000566d  jbe     loc_14000579E
0x140005673  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005678  test    rax, rax
0x14000567b  jnz     short loc_140005684
0x14000567d  mov     ecx, 5
0x140005682  int     29h; Win8: RtlFailFast(ecx)
0x140005684  lea     rsi, [rax+27h]
0x140005688  and     rsi, 0FFFFFFFFFFFFFFE0h
0x14000568c  mov     [rsi-8], rax
0x140005690  jmp     short loc_14000569D
0x140005692  mov     rcx, r14; Size
0x140005695  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000569a  mov     rsi, rax
0x14000569d  sub     rbp, r12
0x1400056a0  sar     rbp, 3
0x1400056a4  lea     rcx, [rsi+rbp*8]
0x1400056a8  mov     [rsp+98h+var_78], rdi
0x1400056ad  mov     [rsp+98h+var_70], rsi
0x1400056b2  mov     [rsp+98h+var_68], rbx
0x1400056b7  mov     [rsp+98h+var_60], rcx
0x1400056bc  mov     [rsp+98h+var_58], rcx
0x1400056c1  mov     rdx, r15
0x1400056c4  sub     rdx, rbp
0x1400056c7  mov     r8, rdi
0x1400056ca  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vvalue@json@web@@@std@@@std@@YAPEAVvalue@json@web@@PEAV123@_KAEAV?$allocator@Vvalue@json@web@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(web::json::value *,unsigned __int64,std::allocator<web::json::value> &)
0x1400056cf  mov     r8, [rdi+8]
0x1400056d3  mov     rdx, rsi
0x1400056d6  mov     rcx, [rdi]
0x1400056d9  cmp     rcx, r8
0x1400056dc  jz      short loc_1400056F6
0x1400056de  xchg    ax, ax
0x1400056e0  mov     rax, [rcx]
0x1400056e3  mov     [rcx], r13
0x1400056e6  mov     [rdx], rax
0x1400056e9  lea     rdx, [rdx+8]
0x1400056ed  add     rcx, 8
0x1400056f1  cmp     rcx, r8
0x1400056f4  jnz     short loc_1400056E0
0x1400056f6  mov     rbx, [rdi]
0x1400056f9  test    rbx, rbx
0x1400056fc  jz      short loc_140005774
0x1400056fe  mov     rbp, [rdi+8]
0x140005702  cmp     rbx, rbp
0x140005705  jz      short loc_14000572C
0x140005707  mov     rcx, [rbx]
0x14000570a  test    rcx, rcx
0x14000570d  jz      short loc_140005723
0x14000570f  mov     rax, [rcx]
0x140005712  mov     edx, 1
0x140005717  mov     rax, [rax+0C0h]
0x14000571e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005723  add     rbx, 8
0x140005727  cmp     rbx, rbp
0x14000572a  jnz     short loc_140005707
0x14000572c  mov     rcx, [rdi]
0x14000572f  mov     rax, [rdi+10h]
0x140005733  sub     rax, rcx
0x140005736  sar     rax, 3
0x14000573a  lea     rdx, ds:0[rax*8]
0x140005742  cmp     rdx, 1000h
0x140005749  jb      short loc_140005769
0x14000574b  mov     rax, [rcx-8]
0x14000574f  sub     rcx, rax
0x140005752  sub     rcx, 8
0x140005756  cmp     rcx, 1Fh
0x14000575a  ja      short loc_140005762
0x14000575c  add     rdx, 27h ; '''
0x140005760  jmp     short loc_14000576C
0x140005762  mov     ecx, 5
0x140005767  int     29h; Win8: RtlFailFast(ecx)
0x140005769  mov     rax, rcx
0x14000576c  mov     rcx, rax; Block
0x14000576f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005774  mov     [rdi], rsi
0x140005777  lea     rax, [rsi+r15*8]
0x14000577b  mov     [rdi+8], rax
0x14000577f  lea     rax, [r14+rsi]
0x140005783  mov     [rdi+10h], rax
0x140005787  add     rsp, 58h
0x14000578b  pop     r15
0x14000578d  pop     r14
0x14000578f  pop     r13
0x140005791  pop     r12
0x140005793  pop     rdi
0x140005794  pop     rsi
0x140005795  pop     rbp
0x140005796  pop     rbx
0x140005797  retn
0x140005798  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x14000579e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
