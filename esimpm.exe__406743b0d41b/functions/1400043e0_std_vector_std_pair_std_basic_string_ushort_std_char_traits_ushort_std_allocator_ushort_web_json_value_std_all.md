# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Emplace_reallocate<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> &&)

- ea: `0x1400043e0`
- end: `0x140004664`
- name: `??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z`
- size: `644`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140006810`

## callees

- `0x140002f84`
- `0x140003244`
- `0x1400043e0`
- `0x140005c90`
- `0x140007030`
- `0x140013dd0`
- `0x140013df8`
- `0x14003e010`

## pseudocode

```c
char *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  void *v3; // rbp
  __int64 v7; // r9
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // r15
  bool v12; // cf
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r14
  _QWORD *v15; // rsi
  void *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // r12
  __int64 v19; // rax
  char *v20; // rbp
  __int64 v21; // rax
  _QWORD *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 i; // rbp
  __int64 v27; // rcx
  __int64 v28; // r8
  void *v29; // rcx

  v3 = (void *)*a1;
  v7 = (a1[1] - *a1) / 40LL;
  if ( v7 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v8 = (a1[2] - (_QWORD)v3) / 40LL;
  v9 = v8 >> 1;
  if ( v8 > 0x666666666666666LL - (v8 >> 1) )
    goto LABEL_27;
  v10 = v8 + v9;
  v11 = v7 + 1;
  v12 = v8 + v9 < v7 + 1;
  v13 = v7 + 1;
  if ( !v12 )
    v13 = v10;
  if ( v13 > 0x666666666666666LL )
    goto LABEL_27;
  v14 = 40 * v13;
  if ( !(40 * v13) )
  {
    v15 = 0;
    goto LABEL_13;
  }
  if ( v14 < 0x1000 )
  {
    v15 = operator new(40 * v13);
    goto LABEL_13;
  }
  if ( v14 + 39 < v14 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v16 = operator new(v14 + 39);
  if ( !v16 )
    goto LABEL_22;
  v15 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v15 - 1) = v16;
LABEL_13:
  v17 = a1;
  v18 = (a2 - (__int64)v3) / 40;
  v19 = 5 * v18;
  *(_OWORD *)&v15[v19] = 0;
  v15[v19 + 2] = 0;
  v20 = (char *)&v15[5 * v18];
  *((_QWORD *)v20 + 3) = 0;
  *(_OWORD *)v20 = *(_OWORD *)a3;
  *((_OWORD *)v20 + 1) = *(_OWORD *)(a3 + 16);
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)a3 = 0;
  *(_QWORD *)(a3 + 24) = 7;
  v21 = *(_QWORD *)(a3 + 32);
  *(_QWORD *)(a3 + 32) = 0;
  v22 = v15;
  *((_QWORD *)v20 + 4) = v21;
  v23 = a1[1];
  v24 = *a1;
  if ( a2 != v23 )
  {
    std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
      v24,
      a2,
      v15,
      a1);
    v23 = a1[1];
    v22 = v20 + 40;
    v24 = a2;
    v17 = a1;
  }
  std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
    v24,
    v23,
    v22,
    v17);
  v25 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v25 != i; v25 += 40 )
    {
      v27 = *(_QWORD *)(v25 + 32);
      if ( v27 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 192LL))(v27, 1);
      std::wstring::_Tidy_deallocate(v25);
    }
    v28 = *a1;
    if ( (unsigned __int64)(40 * ((a1[2] - *a1) / 40LL)) < 0x1000 )
    {
      v29 = (void *)*a1;
    }
    else
    {
      v29 = *(void **)(v28 - 8);
      if ( (unsigned __int64)(v28 - (_QWORD)v29 - 8) > 0x1F )
LABEL_22:
        __fastfail(5u);
    }
    operator delete(v29);
  }
  *a1 = v15;
  a1[1] = &v15[5 * v11];
  a1[2] = &v15[v14 / 8];
  return (char *)&v15[5 * v18];
}

```

## disassembly

```asm
0x1400043e0  push    rbx
0x1400043e2  push    rbp
0x1400043e3  push    rdi
0x1400043e4  push    r12
0x1400043e6  push    r13
0x1400043e8  sub     rsp, 20h
0x1400043ec  mov     rbp, [rcx]
0x1400043ef  mov     r12, 6666666666666667h
0x1400043f9  mov     r9, [rcx+8]
0x1400043fd  mov     rax, r12
0x140004400  sub     r9, rbp
0x140004403  mov     rbx, rdx
0x140004406  imul    r9
0x140004409  mov     r13, r8
0x14000440c  mov     rdi, rcx
0x14000440f  mov     r9, rdx
0x140004412  mov     r8, 666666666666666h
0x14000441c  sar     r9, 4
0x140004420  mov     rax, r9
0x140004423  shr     rax, 3Fh
0x140004427  add     r9, rax
0x14000442a  cmp     r9, r8
0x14000442d  jz      loc_140004658
0x140004433  mov     rcx, [rcx+10h]
0x140004437  mov     rax, r12
0x14000443a  sub     rcx, rbp
0x14000443d  mov     [rsp+48h+arg_0], rsi
0x140004442  imul    rcx
0x140004445  mov     [rsp+48h+arg_8], r14
0x14000444a  sar     rdx, 4
0x14000444e  mov     rax, rdx
0x140004451  mov     [rsp+48h+arg_10], r15
0x140004456  shr     rax, 3Fh
0x14000445a  add     rdx, rax
0x14000445d  mov     rax, r8
0x140004460  mov     rcx, rdx
0x140004463  shr     rcx, 1
0x140004466  sub     rax, rcx
0x140004469  cmp     rdx, rax
0x14000446c  ja      loc_14000465E
0x140004472  lea     rax, [rdx+rcx]
0x140004476  lea     r15, [r9+1]
0x14000447a  cmp     rax, r15
0x14000447d  mov     rcx, r15
0x140004480  cmovnb  rcx, rax
0x140004484  cmp     rcx, r8
0x140004487  ja      loc_14000465E
0x14000448d  lea     rax, [rcx+rcx*4]
0x140004491  xor     r8d, r8d
0x140004494  lea     r14, ds:0[rax*8]
0x14000449c  test    r14, r14
0x14000449f  jnz     short loc_1400044A6
0x1400044a1  mov     esi, r8d
0x1400044a4  jmp     short loc_1400044E6
0x1400044a6  cmp     r14, 1000h
0x1400044ad  jb      short loc_1400044D8
0x1400044af  lea     rcx, [r14+27h]; Size
0x1400044b3  cmp     rcx, r14
0x1400044b6  jbe     loc_14000465E
0x1400044bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400044c1  test    rax, rax
0x1400044c4  jz      loc_14000460F
0x1400044ca  lea     rsi, [rax+27h]
0x1400044ce  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1400044d2  mov     [rsi-8], rax
0x1400044d6  jmp     short loc_1400044E3
0x1400044d8  mov     rcx, r14; Size
0x1400044db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400044e0  mov     rsi, rax
0x1400044e3  xor     r8d, r8d
0x1400044e6  mov     rax, r12
0x1400044e9  xorps   xmm0, xmm0
0x1400044ec  mov     rcx, rbx
0x1400044ef  mov     r9, rdi
0x1400044f2  sub     rcx, rbp
0x1400044f5  imul    rcx
0x1400044f8  mov     r12, rdx
0x1400044fb  sar     r12, 4
0x1400044ff  mov     rax, r12
0x140004502  shr     rax, 3Fh
0x140004506  add     r12, rax
0x140004509  lea     rax, [r12+r12*4]
0x14000450d  movups  xmmword ptr [rsi+rax*8], xmm0
0x140004511  mov     [rsi+rax*8+10h], r8
0x140004516  lea     rbp, [rsi+rax*8]
0x14000451a  mov     [rbp+18h], r8
0x14000451e  movups  xmm0, xmmword ptr [r13+0]
0x140004523  movups  xmmword ptr [rbp+0], xmm0
0x140004527  movups  xmm1, xmmword ptr [r13+10h]
0x14000452c  movups  xmmword ptr [rbp+10h], xmm1
0x140004530  mov     [r13+10h], r8
0x140004534  mov     [r13+0], r8w
0x140004539  mov     qword ptr [r13+18h], 7
0x140004541  mov     rax, [r13+20h]
0x140004545  mov     [r13+20h], r8
0x140004549  mov     r8, rsi
0x14000454c  mov     [rbp+20h], rax
0x140004550  mov     rdx, [rdi+8]
0x140004554  mov     rcx, [rdi]
0x140004557  cmp     rbx, rdx
0x14000455a  jz      short loc_140004572
0x14000455c  mov     rdx, rbx
0x14000455f  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x140004564  mov     rdx, [rdi+8]
0x140004568  lea     r8, [rbp+28h]
0x14000456c  mov     rcx, rbx
0x14000456f  mov     r9, rdi
0x140004572  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x140004577  mov     rbx, [rdi]
0x14000457a  test    rbx, rbx
0x14000457d  jz      loc_14000461E
0x140004583  mov     rbp, [rdi+8]
0x140004587  cmp     rbx, rbp
0x14000458a  jz      short loc_1400045BE
0x14000458c  nop     dword ptr [rax+00h]
0x140004590  mov     rcx, [rbx+20h]
0x140004594  test    rcx, rcx
0x140004597  jz      short loc_1400045AD
0x140004599  mov     rax, [rcx]
0x14000459c  mov     edx, 1
0x1400045a1  mov     rax, [rax+0C0h]
0x1400045a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045ad  mov     rcx, rbx
0x1400045b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400045b5  add     rbx, 28h ; '('
0x1400045b9  cmp     rbx, rbp
0x1400045bc  jnz     short loc_140004590
0x1400045be  mov     r8, [rdi]
0x1400045c1  mov     rax, 6666666666666667h
0x1400045cb  mov     rcx, [rdi+10h]
0x1400045cf  sub     rcx, r8
0x1400045d2  imul    rcx
0x1400045d5  sar     rdx, 4
0x1400045d9  mov     rax, rdx
0x1400045dc  shr     rax, 3Fh
0x1400045e0  add     rdx, rax
0x1400045e3  lea     rax, [rdx+rdx*4]
0x1400045e7  lea     rdx, ds:0[rax*8]
0x1400045ef  cmp     rdx, 1000h
0x1400045f6  jb      short loc_140004616
0x1400045f8  mov     rcx, [r8-8]
0x1400045fc  sub     r8, rcx
0x1400045ff  sub     r8, 8
0x140004603  cmp     r8, 1Fh
0x140004607  ja      short loc_14000460F
0x140004609  add     rdx, 27h ; '''
0x14000460d  jmp     short loc_140004619
0x14000460f  mov     ecx, 5
0x140004614  int     29h; Win8: RtlFailFast(ecx)
0x140004616  mov     rcx, r8; Block
0x140004619  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000461e  lea     rax, [r15+r15*4]
0x140004622  mov     [rdi], rsi
0x140004625  mov     r15, [rsp+48h+arg_10]
0x14000462a  lea     rcx, [rsi+rax*8]
0x14000462e  lea     rax, [r14+rsi]
0x140004632  mov     [rdi+8], rcx
0x140004636  mov     r14, [rsp+48h+arg_8]
0x14000463b  mov     [rdi+10h], rax
0x14000463f  lea     rax, [r12+r12*4]
0x140004643  lea     rax, [rsi+rax*8]
0x140004647  mov     rsi, [rsp+48h+arg_0]
0x14000464c  add     rsp, 20h
0x140004650  pop     r13
0x140004652  pop     r12
0x140004654  pop     rdi
0x140004655  pop     rbp
0x140004656  pop     rbx
0x140004657  retn
0x140004658  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x14000465e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
