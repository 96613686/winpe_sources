# std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(Container::Manager::Image::RegistryAdjustment * const,Container::Manager::Image::RegistryAdjustment &&)

- ea: `0x140013ee8`
- end: `0x140014097`
- name: `??$_Emplace_reallocate@URegistryAdjustment@Image@Manager@Container@@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAURegistryAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400113ec`

## callees

- `0x140002bd4`
- `0x140012e48`
- `0x140013ee8`
- `0x1400153c4`
- `0x14001f5c0`
- `0x14001ffcc`
- `0x140020224`

## pseudocode

```c
char *__fastcall std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbp
  unsigned __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rsi
  size_t v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  __int64 v15; // rbp
  __int64 v16; // r11
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rbp
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r11
  char *v25; // rcx
  __int64 v26; // rcx

  v3 = *a1;
  v6 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[1] - *a1) >> 3);
  if ( v6 == 0x222222222222222LL )
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
  v8 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[2] - v3) >> 3);
  v9 = v8 >> 1;
  if ( v8 > 0x222222222222222LL - (v8 >> 1) )
    goto LABEL_27;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x222222222222222LL )
    goto LABEL_27;
  v12 = 120 * v11;
  if ( !(120 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v15 = (a2 - v3) / 120;
  Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(&v13[15 * v15], a3);
  v16 = a1[1];
  v17 = v13;
  v18 = *a1;
  if ( a2 == v16 )
  {
    while ( v18 != v16 )
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v17, v18);
      v17 = (_QWORD *)(v19 + 120);
      v18 = v20 + 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v17, v17);
    v21 = 15 * v15;
  }
  else
  {
    while ( v18 != a2 )
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v17, v18);
      v17 = (_QWORD *)(v22 + 120);
      v18 = v23 + 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v17, v17);
    v24 = a1[1];
    v21 = 15 * v15;
    v25 = (char *)&v13[v21 + 15];
    while ( a2 != v24 )
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v25, a2);
      v25 = (char *)(v26 + 120);
      a2 += 120;
    }
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v25, v25);
  }
  std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(a1, v13, v10, v11);
  return (char *)&v13[v21];
}

```

## disassembly

```asm
0x140013ee8  push    rbx
0x140013eea  push    rbp
0x140013eeb  push    rsi
0x140013eec  push    rdi
0x140013eed  push    r12
0x140013eef  push    r14
0x140013ef1  push    r15
0x140013ef3  sub     rsp, 20h
0x140013ef7  mov     rbp, [rcx]
0x140013efa  mov     rdi, rdx
0x140013efd  mov     rdx, [rcx+8]
0x140013f01  mov     rax, 0EEEEEEEEEEEEEEEFh
0x140013f0b  sub     rdx, rbp
0x140013f0e  mov     r9, 222222222222222h
0x140013f18  sar     rdx, 3
0x140013f1c  mov     r12, r8
0x140013f1f  imul    rdx, rax
0x140013f23  mov     r14, rcx
0x140013f26  cmp     rdx, r9
0x140013f29  jz      loc_14001408B
0x140013f2f  mov     rcx, [rcx+10h]
0x140013f33  sub     rcx, rbp
0x140013f36  sar     rcx, 3
0x140013f3a  imul    rcx, rax
0x140013f3e  mov     rax, r9
0x140013f41  mov     r8, rcx
0x140013f44  shr     r8, 1
0x140013f47  sub     rax, r8
0x140013f4a  cmp     rcx, rax
0x140013f4d  ja      loc_140014091
0x140013f53  lea     r15, [rdx+1]
0x140013f57  lea     rax, [rcx+r8]
0x140013f5b  mov     rsi, r15
0x140013f5e  cmp     rax, r15
0x140013f61  cmovnb  rsi, rax
0x140013f65  cmp     rsi, r9
0x140013f68  ja      loc_140014091
0x140013f6e  imul    rcx, rsi, 78h ; 'x'; Size
0x140013f72  test    rcx, rcx
0x140013f75  jnz     short loc_140013F7B
0x140013f77  xor     ebx, ebx
0x140013f79  jmp     short loc_140013FB9
0x140013f7b  cmp     rcx, 1000h
0x140013f82  jb      short loc_140013FB1
0x140013f84  lea     rax, [rcx+27h]
0x140013f88  cmp     rax, rcx
0x140013f8b  jbe     loc_140014091
0x140013f91  mov     rcx, rax; Size
0x140013f94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013f99  test    rax, rax
0x140013f9c  jnz     short loc_140013FA3
0x140013f9e  lea     ecx, [rax+5]
0x140013fa1  int     29h; Win8: RtlFailFast(ecx)
0x140013fa3  lea     rbx, [rax+27h]
0x140013fa7  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140013fab  mov     [rbx-8], rax
0x140013faf  jmp     short loc_140013FB9
0x140013fb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013fb6  mov     rbx, rax
0x140013fb9  mov     rcx, rdi
0x140013fbc  mov     rax, 8888888888888889h
0x140013fc6  sub     rcx, rbp
0x140013fc9  imul    rcx
0x140013fcc  lea     rbp, [rcx+rdx]
0x140013fd0  mov     rdx, r12
0x140013fd3  sar     rbp, 6
0x140013fd7  mov     rcx, rbp
0x140013fda  shr     rcx, 3Fh
0x140013fde  add     rbp, rcx
0x140013fe1  imul    rcx, rbp, 78h ; 'x'
0x140013fe5  add     rcx, rbx
0x140013fe8  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140013fed  mov     r11, [r14+8]
0x140013ff1  mov     rcx, rbx
0x140013ff4  mov     rdx, [r14]
0x140013ff7  cmp     rdi, r11
0x140013ffa  jnz     short loc_14001402B
0x140013ffc  jmp     short loc_14001400B
0x140013ffe  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140014003  add     rcx, 78h ; 'x'
0x140014007  add     rdx, 78h ; 'x'
0x14001400b  cmp     rdx, r11
0x14001400e  jnz     short loc_140013FFE
0x140014010  mov     rdx, rcx
0x140014013  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140014018  imul    rbp, 78h ; 'x'
0x14001401c  jmp     short loc_140014066
0x14001401e  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140014023  add     rcx, 78h ; 'x'
0x140014027  add     rdx, 78h ; 'x'
0x14001402b  cmp     rdx, rdi
0x14001402e  jnz     short loc_14001401E
0x140014030  mov     rdx, rcx
0x140014033  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140014038  mov     r11, [r14+8]
0x14001403c  imul    rbp, 78h ; 'x'
0x140014040  lea     rcx, [rbp+78h]
0x140014044  add     rcx, rbx
0x140014047  jmp     short loc_140014059
0x140014049  mov     rdx, rdi
0x14001404c  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140014051  add     rcx, 78h ; 'x'
0x140014055  add     rdi, 78h ; 'x'
0x140014059  cmp     rdi, r11
0x14001405c  jnz     short loc_140014049
0x14001405e  mov     rdx, rcx
0x140014061  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140014066  mov     r9, rsi
0x140014069  mov     r8, r15
0x14001406c  mov     rdx, rbx
0x14001406f  mov     rcx, r14
0x140014072  call    ?_Change_array@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAURegistryAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(Container::Manager::Image::RegistryAdjustment * const,unsigned __int64,unsigned __int64)
0x140014077  lea     rax, [rbx+rbp]
0x14001407b  add     rsp, 20h
0x14001407f  pop     r15
0x140014081  pop     r14
0x140014083  pop     r12
0x140014085  pop     rdi
0x140014086  pop     rsi
0x140014087  pop     rbp
0x140014088  pop     rbx
0x140014089  retn
0x14001408b  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Xlength(void)
0x140014091  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
