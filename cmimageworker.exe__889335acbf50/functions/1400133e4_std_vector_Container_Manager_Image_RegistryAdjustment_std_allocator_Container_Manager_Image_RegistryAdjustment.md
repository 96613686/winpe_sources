# std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>::_Emplace_reallocate<>(Container::Manager::Image::RegistryAdjustment * const)

- ea: `0x1400133e4`
- end: `0x1400135ba`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAURegistryAdjustment@Image@Manager@Container@@QEAU2345@@Z`
- size: `470`
- prototype: `char *__fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400111d0`

## callees

- `0x140002b2c`
- `0x140002bd4`
- `0x140012e48`
- `0x1400133e4`
- `0x1400153c4`
- `0x14001f5c0`
- `0x14001ffcc`
- `0x140020224`

## pseudocode

```c
char *__fastcall std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<>(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rbx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r12
  unsigned __int64 v9; // rbp
  size_t v10; // rcx
  _QWORD *v11; // rdi
  void *v12; // rax
  __int64 v13; // r15
  _QWORD *v14; // rbx
  _QWORD *v15; // rcx
  __int64 v16; // r11
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r11
  _QWORD *v24; // rcx
  __int64 v25; // rcx

  v2 = *a1;
  v5 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[1] - *a1) >> 3);
  if ( v5 == 0x222222222222222LL )
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
  v6 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[2] - v2) >> 3);
  v7 = v6 >> 1;
  if ( v6 > 0x222222222222222LL - (v6 >> 1) )
    goto LABEL_27;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x222222222222222LL )
    goto LABEL_27;
  v10 = 120 * v9;
  if ( !(120 * v9) )
  {
    v11 = 0;
    goto LABEL_14;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(v10);
    goto LABEL_14;
  }
  if ( v10 + 39 < v10 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    __fastfail(5u);
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_14:
  v13 = (a2 - v2) / 120;
  v14 = &v11[15 * v13];
  memset_0(v14, 0, 0x78u);
  v15 = v11;
  v14[1] = v14 + 3;
  v14[2] = v14 + 3;
  v14[5] = v14 + 7;
  v14[6] = v14 + 7;
  v14[9] = v14 + 11;
  v14[10] = v14 + 11;
  v16 = a1[1];
  v17 = *a1;
  if ( a2 == v16 )
  {
    while ( v17 != v16 )
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v15, v17);
      v15 = (_QWORD *)(v18 + 120);
      v17 = v19 + 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v15, v15);
    v20 = 15 * v13;
  }
  else
  {
    while ( v17 != a2 )
    {
      ((void (*)(void))Container::Manager::Image::RegistryAdjustment::RegistryAdjustment)();
      v15 = (_QWORD *)(v21 + 120);
      v17 = v22 + 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v15, v15);
    v23 = a1[1];
    v20 = 15 * v13;
    v24 = &v11[15 * v13 + 15];
    while ( a2 != v23 )
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v24, a2);
      v24 = (_QWORD *)(v25 + 120);
      a2 += 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v24, v24);
  }
  std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(a1, v11, v8, v9);
  return (char *)&v11[v20];
}

```

## disassembly

```asm
0x1400133e4  push    rbx
0x1400133e6  push    rbp
0x1400133e7  push    rsi
0x1400133e8  push    rdi
0x1400133e9  push    r12
0x1400133eb  push    r14
0x1400133ed  push    r15
0x1400133ef  sub     rsp, 20h
0x1400133f3  mov     rbx, [rcx]
0x1400133f6  mov     rsi, rdx
0x1400133f9  mov     rdx, [rcx+8]
0x1400133fd  mov     rax, 0EEEEEEEEEEEEEEEFh
0x140013407  sub     rdx, rbx
0x14001340a  mov     r9, 222222222222222h
0x140013414  sar     rdx, 3
0x140013418  mov     r14, rcx
0x14001341b  imul    rdx, rax
0x14001341f  cmp     rdx, r9
0x140013422  jz      loc_1400135AE
0x140013428  mov     rcx, [rcx+10h]
0x14001342c  sub     rcx, rbx
0x14001342f  sar     rcx, 3
0x140013433  imul    rcx, rax
0x140013437  mov     rax, r9
0x14001343a  mov     r8, rcx
0x14001343d  shr     r8, 1
0x140013440  sub     rax, r8
0x140013443  cmp     rcx, rax
0x140013446  ja      loc_1400135B4
0x14001344c  lea     r12, [rdx+1]
0x140013450  lea     rax, [rcx+r8]
0x140013454  mov     rbp, r12
0x140013457  cmp     rax, r12
0x14001345a  cmovnb  rbp, rax
0x14001345e  cmp     rbp, r9
0x140013461  ja      loc_1400135B4
0x140013467  imul    rcx, rbp, 78h ; 'x'; Size
0x14001346b  test    rcx, rcx
0x14001346e  jnz     short loc_140013474
0x140013470  xor     edi, edi
0x140013472  jmp     short loc_1400134B2
0x140013474  cmp     rcx, 1000h
0x14001347b  jb      short loc_1400134AA
0x14001347d  lea     rax, [rcx+27h]
0x140013481  cmp     rax, rcx
0x140013484  jbe     loc_1400135B4
0x14001348a  mov     rcx, rax; Size
0x14001348d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013492  test    rax, rax
0x140013495  jnz     short loc_14001349C
0x140013497  lea     ecx, [rax+5]
0x14001349a  int     29h; Win8: RtlFailFast(ecx)
0x14001349c  lea     rdi, [rax+27h]
0x1400134a0  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1400134a4  mov     [rdi-8], rax
0x1400134a8  jmp     short loc_1400134B2
0x1400134aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400134af  mov     rdi, rax
0x1400134b2  mov     rcx, rsi
0x1400134b5  mov     rax, 8888888888888889h
0x1400134bf  sub     rcx, rbx
0x1400134c2  imul    rcx
0x1400134c5  lea     r15, [rcx+rdx]
0x1400134c9  xor     edx, edx; Val
0x1400134cb  sar     r15, 6
0x1400134cf  mov     rcx, r15
0x1400134d2  shr     rcx, 3Fh
0x1400134d6  add     r15, rcx
0x1400134d9  lea     r8d, [rdx+78h]; Size
0x1400134dd  imul    rbx, r15, 78h ; 'x'
0x1400134e1  add     rbx, rdi
0x1400134e4  mov     rcx, rbx; void *
0x1400134e7  call    memset_0
0x1400134ec  lea     rax, [rbx+18h]
0x1400134f0  mov     rcx, rdi
0x1400134f3  mov     [rbx+8], rax
0x1400134f7  mov     [rbx+10h], rax
0x1400134fb  lea     rax, [rbx+38h]
0x1400134ff  mov     [rbx+28h], rax
0x140013503  mov     [rbx+30h], rax
0x140013507  lea     rax, [rbx+58h]
0x14001350b  mov     [rbx+48h], rax
0x14001350f  mov     [rbx+50h], rax
0x140013513  mov     r11, [r14+8]
0x140013517  mov     rdx, [r14]
0x14001351a  cmp     rsi, r11
0x14001351d  jnz     short loc_14001354E
0x14001351f  jmp     short loc_14001352E
0x140013521  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140013526  add     rcx, 78h ; 'x'
0x14001352a  add     rdx, 78h ; 'x'
0x14001352e  cmp     rdx, r11
0x140013531  jnz     short loc_140013521
0x140013533  mov     rdx, rcx
0x140013536  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x14001353b  imul    rbx, r15, 78h ; 'x'
0x14001353f  jmp     short loc_140013589
0x140013541  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140013546  add     rcx, 78h ; 'x'
0x14001354a  add     rdx, 78h ; 'x'
0x14001354e  cmp     rdx, rsi
0x140013551  jnz     short loc_140013541
0x140013553  mov     rdx, rcx
0x140013556  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x14001355b  mov     r11, [r14+8]
0x14001355f  imul    rbx, r15, 78h ; 'x'
0x140013563  lea     rcx, [rbx+78h]
0x140013567  add     rcx, rdi
0x14001356a  jmp     short loc_14001357C
0x14001356c  mov     rdx, rsi
0x14001356f  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140013574  add     rcx, 78h ; 'x'
0x140013578  add     rsi, 78h ; 'x'
0x14001357c  cmp     rsi, r11
0x14001357f  jnz     short loc_14001356C
0x140013581  mov     rdx, rcx
0x140013584  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140013589  mov     r9, rbp
0x14001358c  mov     r8, r12
0x14001358f  mov     rdx, rdi
0x140013592  mov     rcx, r14
0x140013595  call    ?_Change_array@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAURegistryAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(Container::Manager::Image::RegistryAdjustment * const,unsigned __int64,unsigned __int64)
0x14001359a  lea     rax, [rbx+rdi]
0x14001359e  add     rsp, 20h
0x1400135a2  pop     r15
0x1400135a4  pop     r14
0x1400135a6  pop     r12
0x1400135a8  pop     rdi
0x1400135a9  pop     rsi
0x1400135aa  pop     rbp
0x1400135ab  pop     rbx
0x1400135ac  retn
0x1400135ae  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Xlength(void)
0x1400135b4  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
