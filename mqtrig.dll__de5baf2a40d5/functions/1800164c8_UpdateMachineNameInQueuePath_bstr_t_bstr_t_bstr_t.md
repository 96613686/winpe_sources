# UpdateMachineNameInQueuePath(_bstr_t,_bstr_t,_bstr_t *)

- ea: `0x1800164c8`
- end: `0x180016635`
- name: `?UpdateMachineNameInQueuePath@@YA_NV_bstr_t@@0PEAV1@@Z`
- size: `365`
- prototype: `char __fastcall(_bstr_t *, _bstr_t *, _bstr_t *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180010590`
- `0x180012770`
- `0x180012f40`

## callees

- `0x180002ec8`
- `0x1800041ec`
- `0x180004478`
- `0x180005704`
- `0x180005740`
- `0x180009ab0`
- `0x180015bb0`
- `0x1800164c8`
- `0x18001663c`
- `0x18001e380`

## pseudocode

```c
char __fastcall UpdateMachineNameInQueuePath(_bstr_t *a1, _bstr_t *a2, _bstr_t *a3)
{
  __int64 v6; // rdx
  _WORD *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  char v10; // si
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  _BYTE v16[8]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-39h]
  _BYTE v19[8]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v20[4]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v21[40]; // [rsp+80h] [rbp-9h] BYREF

  if ( *(_QWORD *)a1 )
    v6 = **(_QWORD **)a1;
  else
    v6 = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    (__int64)v19,
    v6);
  v7 = v20;
  if ( v20[3] >= 8u )
    v7 = (_WORD *)v20[0];
  if ( *v7 == 46 )
  {
    v18 = 7;
    v17[2] = 0;
    LOWORD(v17[0]) = 0;
    if ( *(_QWORD *)a2 )
      v8 = **(_QWORD **)a2;
    else
      v8 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(v16);
    v10 = 1;
    v11 = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::substr(
            v19,
            v21,
            1,
            -1,
            a1,
            a2);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(v16, v11, 0, -1);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v21,
      1,
      0);
    v12 = (const wchar_t *)v17;
    if ( v18 >= 8 )
      v12 = (const wchar_t *)v17[0];
    _bstr_t::operator=(a3, v12);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v16,
      1,
      0);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v19,
      1,
      0);
  }
  else
  {
    _bstr_t::operator=(a3, a1);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v19,
      1,
      0);
    v10 = 0;
  }
  _bstr_t::_Free(a1);
  _bstr_t::_Free(a2);
  return v10;
}

```

## disassembly

```asm
0x1800164c8  push    rbp
0x1800164ca  push    rbx
0x1800164cb  push    rsi
0x1800164cc  push    rdi
0x1800164cd  push    r12
0x1800164cf  push    r14
0x1800164d1  push    r15
0x1800164d3  lea     rbp, [rsp-27h]
0x1800164d8  sub     rsp, 0B0h
0x1800164df  mov     rax, cs:__security_cookie
0x1800164e6  xor     rax, rsp
0x1800164e9  mov     [rbp+57h+var_38], rax
0x1800164ed  mov     r14, r8
0x1800164f0  mov     rdi, rdx
0x1800164f3  mov     rbx, rcx
0x1800164f6  mov     [rbp+57h+var_C0], rcx
0x1800164fa  mov     [rbp+57h+var_B8], rdx
0x1800164fe  mov     rdx, [rcx]
0x180016501  xor     r15d, r15d
0x180016504  test    rdx, rdx
0x180016507  jz      short loc_18001650E
0x180016509  mov     rdx, [rdx]
0x18001650c  jmp     short loc_180016511
0x18001650e  mov     rdx, r15
0x180016511  lea     rcx, [rbp+57h+var_88]
0x180016515  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x18001651a  nop
0x18001651b  lea     rax, [rbp+57h+var_80]
0x18001651f  cmp     [rbp+57h+var_68], 8
0x180016524  cmovnb  rax, [rbp+57h+var_80]
0x180016529  cmp     word ptr [rax], 2Eh ; '.'
0x18001652d  jnz     loc_1800165E3
0x180016533  mov     [rbp+57h+var_90], 7
0x18001653b  mov     [rbp+57h+var_98], r15
0x18001653f  mov     word ptr [rbp+57h+var_A8], r15w
0x180016544  mov     rax, [rdi]
0x180016547  test    rax, rax
0x18001654a  jz      short loc_180016551
0x18001654c  mov     rdx, [rax]
0x18001654f  jmp     short loc_180016554
0x180016551  mov     rdx, r15
0x180016554  or      r12, 0FFFFFFFFFFFFFFFFh
0x180016558  mov     r8, r12
0x18001655b  inc     r8
0x18001655e  cmp     [rdx+r8*2], r15w
0x180016563  jnz     short loc_18001655B
0x180016565  lea     rcx, [rbp+57h+var_B0]
0x180016569  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(wchar_t const *,unsigned __int64)
0x18001656e  mov     r9, r12
0x180016571  mov     esi, 1
0x180016576  mov     r8d, esi
0x180016579  lea     rdx, [rbp+57h+var_60]
0x18001657d  lea     rcx, [rbp+57h+var_88]
0x180016581  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEBA?AV12@_K0@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::substr(unsigned __int64,unsigned __int64)
0x180016586  nop
0x180016587  mov     r9, r12
0x18001658a  xor     r8d, r8d
0x18001658d  mov     rdx, rax
0x180016590  lea     rcx, [rbp+57h+var_B0]
0x180016594  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)
0x180016599  nop
0x18001659a  xor     r8d, r8d
0x18001659d  mov     dl, sil
0x1800165a0  lea     rcx, [rbp+57h+var_60]
0x1800165a4  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800165a9  nop
0x1800165aa  lea     rdx, [rbp+57h+var_A8]
0x1800165ae  cmp     [rbp+57h+var_90], 8
0x1800165b3  cmovnb  rdx, [rbp+57h+var_A8]
0x1800165b8  mov     rcx, r14
0x1800165bb  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x1800165c0  nop
0x1800165c1  xor     r8d, r8d
0x1800165c4  mov     dl, sil
0x1800165c7  lea     rcx, [rbp+57h+var_B0]
0x1800165cb  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800165d0  nop
0x1800165d1  xor     r8d, r8d
0x1800165d4  mov     dl, sil
0x1800165d7  lea     rcx, [rbp+57h+var_88]
0x1800165db  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800165e0  nop
0x1800165e1  jmp     short loc_180016603
0x1800165e3  mov     rdx, rbx
0x1800165e6  mov     rcx, r14
0x1800165e9  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800165ee  nop
0x1800165ef  xor     r8d, r8d
0x1800165f2  lea     edx, [r8+1]
0x1800165f6  lea     rcx, [rbp+57h+var_88]
0x1800165fa  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800165ff  nop
0x180016600  mov     sil, r15b
0x180016603  mov     rcx, rbx; this
0x180016606  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001660b  nop
0x18001660c  mov     rcx, rdi; this
0x18001660f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180016614  mov     al, sil
0x180016617  mov     rcx, [rbp+57h+var_38]
0x18001661b  xor     rcx, rsp; StackCookie
0x18001661e  call    __security_check_cookie
0x180016623  add     rsp, 0B0h
0x18001662a  pop     r15
0x18001662c  pop     r14
0x18001662e  pop     r12
0x180016630  pop     rdi
0x180016631  pop     rsi
0x180016632  pop     rbx
0x180016633  pop     rbp
0x180016634  retn
```
