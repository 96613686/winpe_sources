# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Emplace_reallocate<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&,web::json::value &&)

- ea: `0x140008630`
- end: `0x1400088bb`
- name: `??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAVvalue@json@web@@@Z`
- size: `651`
- prototype: `char *__fastcall(_QWORD *, _BYTE *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x140009f80`

## callees

- `0x140002f84`
- `0x140003244`
- `0x140005c90`
- `0x1400064b0`
- `0x140007030`
- `0x140008630`
- `0x140013dd0`
- `0x140013df8`
- `0x14003e010`

## pseudocode

```c
char *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3,
        __int64 a4)
{
  _BYTE *v4; // rbx
  __int64 v8; // r10
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // r15
  bool v13; // cf
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r14
  _QWORD *v16; // rsi
  void *v17; // rax
  __int64 v18; // r12
  char *v19; // rbx
  _BYTE *v20; // rdx
  _QWORD *v21; // r8
  _BYTE *v22; // rcx
  _QWORD *v23; // r9
  __int64 v24; // rbx
  __int64 i; // rbp
  __int64 v26; // rcx
  __int64 v27; // r8
  void *v28; // rcx

  v4 = (_BYTE *)*a1;
  v8 = (a1[1] - *a1) / 40LL;
  if ( v8 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v9 = (a1[2] - (_QWORD)v4) / 40LL;
  v10 = v9 >> 1;
  if ( v9 > 0x666666666666666LL - (v9 >> 1) )
    goto LABEL_27;
  v11 = v9 + v10;
  v12 = v8 + 1;
  v13 = v9 + v10 < v8 + 1;
  v14 = v8 + 1;
  if ( !v13 )
    v14 = v11;
  if ( v14 > 0x666666666666666LL )
    goto LABEL_27;
  v15 = 40 * v14;
  if ( !(40 * v14) )
  {
    v16 = 0;
    goto LABEL_13;
  }
  if ( v15 < 0x1000 )
  {
    v16 = operator new(40 * v14);
    goto LABEL_13;
  }
  if ( v15 + 39 < v15 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v17 = operator new(v15 + 39);
  if ( !v17 )
    goto LABEL_22;
  v16 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v16 - 1) = v17;
LABEL_13:
  v18 = (a2 - v4) / 40;
  *(_OWORD *)&v16[5 * v18] = 0;
  v19 = (char *)&v16[5 * v18];
  *((_QWORD *)v19 + 2) = 0;
  *((_QWORD *)v19 + 3) = 0;
  *(_OWORD *)v19 = *(_OWORD *)a3;
  *((_OWORD *)v19 + 1) = *(_OWORD *)(a3 + 16);
  *(_QWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 24) = 7;
  *(_WORD *)a3 = 0;
  web::json::value::value(v19 + 32, a4);
  v20 = (_BYTE *)a1[1];
  v21 = v16;
  v22 = (_BYTE *)*a1;
  v23 = a1;
  if ( a2 != v20 )
  {
    std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
      v22,
      a2,
      v16,
      a1);
    v20 = (_BYTE *)a1[1];
    v21 = v19 + 40;
    v22 = a2;
    v23 = a1;
  }
  std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
    v22,
    v20,
    v21,
    v23);
  v24 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v24 != i; v24 += 40 )
    {
      v26 = *(_QWORD *)(v24 + 32);
      if ( v26 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 192LL))(v26, 1);
      std::wstring::_Tidy_deallocate(v24);
    }
    v27 = *a1;
    if ( (unsigned __int64)(40 * ((a1[2] - *a1) / 40LL)) < 0x1000 )
    {
      v28 = (void *)*a1;
    }
    else
    {
      v28 = *(void **)(v27 - 8);
      if ( (unsigned __int64)(v27 - (_QWORD)v28 - 8) > 0x1F )
LABEL_22:
        __fastfail(5u);
    }
    operator delete(v28);
  }
  *a1 = v16;
  a1[1] = &v16[5 * v12];
  a1[2] = &v16[v15 / 8];
  return (char *)&v16[5 * v18];
}

```

## disassembly

```asm
0x140008630  mov     [rsp+arg_18], r9
0x140008635  push    rbx
0x140008636  push    rbp
0x140008637  push    rdi
0x140008638  push    r12
0x14000863a  push    r13
0x14000863c  sub     rsp, 20h
0x140008640  mov     rbx, [rcx]
0x140008643  mov     r12, 6666666666666667h
0x14000864d  mov     r10, [rcx+8]
0x140008651  mov     rax, r12
0x140008654  sub     r10, rbx
0x140008657  mov     rbp, rdx
0x14000865a  imul    r10
0x14000865d  mov     r13, r8
0x140008660  mov     rdi, rcx
0x140008663  mov     r10, rdx
0x140008666  mov     r8, 666666666666666h
0x140008670  sar     r10, 4
0x140008674  mov     rax, r10
0x140008677  shr     rax, 3Fh
0x14000867b  add     r10, rax
0x14000867e  cmp     r10, r8
0x140008681  jz      loc_1400088AF
0x140008687  mov     rcx, [rcx+10h]
0x14000868b  mov     rax, r12
0x14000868e  sub     rcx, rbx
0x140008691  mov     [rsp+48h+arg_0], rsi
0x140008696  imul    rcx
0x140008699  mov     [rsp+48h+arg_8], r14
0x14000869e  sar     rdx, 4
0x1400086a2  mov     rax, rdx
0x1400086a5  mov     [rsp+48h+arg_10], r15
0x1400086aa  shr     rax, 3Fh
0x1400086ae  add     rdx, rax
0x1400086b1  mov     rax, r8
0x1400086b4  mov     rcx, rdx
0x1400086b7  shr     rcx, 1
0x1400086ba  sub     rax, rcx
0x1400086bd  cmp     rdx, rax
0x1400086c0  ja      loc_1400088B5
0x1400086c6  lea     rax, [rdx+rcx]
0x1400086ca  lea     r15, [r10+1]
0x1400086ce  cmp     rax, r15
0x1400086d1  mov     rcx, r15
0x1400086d4  cmovnb  rcx, rax
0x1400086d8  cmp     rcx, r8
0x1400086db  ja      loc_1400088B5
0x1400086e1  lea     rax, [rcx+rcx*4]
0x1400086e5  lea     r14, ds:0[rax*8]
0x1400086ed  test    r14, r14
0x1400086f0  jnz     short loc_1400086F6
0x1400086f2  xor     esi, esi
0x1400086f4  jmp     short loc_140008733
0x1400086f6  cmp     r14, 1000h
0x1400086fd  jb      short loc_140008728
0x1400086ff  lea     rcx, [r14+27h]; Size
0x140008703  cmp     rcx, r14
0x140008706  jbe     loc_1400088B5
0x14000870c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008711  test    rax, rax
0x140008714  jz      loc_140008866
0x14000871a  lea     rsi, [rax+27h]
0x14000871e  and     rsi, 0FFFFFFFFFFFFFFE0h
0x140008722  mov     [rsi-8], rax
0x140008726  jmp     short loc_140008733
0x140008728  mov     rcx, r14; Size
0x14000872b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008730  mov     rsi, rax
0x140008733  mov     rax, r12
0x140008736  xorps   xmm0, xmm0
0x140008739  mov     rcx, rbp
0x14000873c  sub     rcx, rbx
0x14000873f  imul    rcx
0x140008742  mov     r12, rdx
0x140008745  mov     rdx, [rsp+48h+arg_18]
0x14000874a  sar     r12, 4
0x14000874e  mov     rax, r12
0x140008751  shr     rax, 3Fh
0x140008755  add     r12, rax
0x140008758  lea     rax, [r12+r12*4]
0x14000875c  movups  xmmword ptr [rsi+rax*8], xmm0
0x140008760  lea     rbx, [rsi+rax*8]
0x140008764  xor     eax, eax
0x140008766  mov     qword ptr [rbx+10h], 0
0x14000876e  lea     rcx, [rbx+20h]
0x140008772  mov     qword ptr [rbx+18h], 0
0x14000877a  movups  xmm0, xmmword ptr [r13+0]
0x14000877f  movups  xmmword ptr [rbx], xmm0
0x140008782  movups  xmm1, xmmword ptr [r13+10h]
0x140008787  movups  xmmword ptr [rbx+10h], xmm1
0x14000878b  mov     qword ptr [r13+10h], 0
0x140008793  mov     qword ptr [r13+18h], 7
0x14000879b  mov     [r13+0], ax
0x1400087a0  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x1400087a5  mov     rdx, [rdi+8]
0x1400087a9  mov     r8, rsi
0x1400087ac  mov     rcx, [rdi]
0x1400087af  mov     r9, rdi
0x1400087b2  cmp     rbp, rdx
0x1400087b5  jz      short loc_1400087CD
0x1400087b7  mov     rdx, rbp
0x1400087ba  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x1400087bf  mov     rdx, [rdi+8]
0x1400087c3  lea     r8, [rbx+28h]
0x1400087c7  mov     rcx, rbp
0x1400087ca  mov     r9, rdi
0x1400087cd  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x1400087d2  mov     rbx, [rdi]
0x1400087d5  test    rbx, rbx
0x1400087d8  jz      loc_140008875
0x1400087de  mov     rbp, [rdi+8]
0x1400087e2  cmp     rbx, rbp
0x1400087e5  jz      short loc_140008815
0x1400087e7  mov     rcx, [rbx+20h]
0x1400087eb  test    rcx, rcx
0x1400087ee  jz      short loc_140008804
0x1400087f0  mov     rax, [rcx]
0x1400087f3  mov     edx, 1
0x1400087f8  mov     rax, [rax+0C0h]
0x1400087ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008804  mov     rcx, rbx
0x140008807  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000880c  add     rbx, 28h ; '('
0x140008810  cmp     rbx, rbp
0x140008813  jnz     short loc_1400087E7
0x140008815  mov     r8, [rdi]
0x140008818  mov     rax, 6666666666666667h
0x140008822  mov     rcx, [rdi+10h]
0x140008826  sub     rcx, r8
0x140008829  imul    rcx
0x14000882c  sar     rdx, 4
0x140008830  mov     rax, rdx
0x140008833  shr     rax, 3Fh
0x140008837  add     rdx, rax
0x14000883a  lea     rax, [rdx+rdx*4]
0x14000883e  lea     rdx, ds:0[rax*8]
0x140008846  cmp     rdx, 1000h
0x14000884d  jb      short loc_14000886D
0x14000884f  mov     rcx, [r8-8]
0x140008853  sub     r8, rcx
0x140008856  sub     r8, 8
0x14000885a  cmp     r8, 1Fh
0x14000885e  ja      short loc_140008866
0x140008860  add     rdx, 27h ; '''
0x140008864  jmp     short loc_140008870
0x140008866  mov     ecx, 5
0x14000886b  int     29h; Win8: RtlFailFast(ecx)
0x14000886d  mov     rcx, r8; Block
0x140008870  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008875  lea     rax, [r15+r15*4]
0x140008879  mov     [rdi], rsi
0x14000887c  mov     r15, [rsp+48h+arg_10]
0x140008881  lea     rcx, [rsi+rax*8]
0x140008885  lea     rax, [r14+rsi]
0x140008889  mov     [rdi+8], rcx
0x14000888d  mov     r14, [rsp+48h+arg_8]
0x140008892  mov     [rdi+10h], rax
0x140008896  lea     rax, [r12+r12*4]
0x14000889a  lea     rax, [rsi+rax*8]
0x14000889e  mov     rsi, [rsp+48h+arg_0]
0x1400088a3  add     rsp, 20h
0x1400088a7  pop     r13
0x1400088a9  pop     r12
0x1400088ab  pop     rdi
0x1400088ac  pop     rbp
0x1400088ad  pop     rbx
0x1400088ae  retn
0x1400088af  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x1400088b5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
