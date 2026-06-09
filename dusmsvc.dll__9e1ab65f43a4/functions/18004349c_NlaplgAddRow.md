# NlaplgAddRow

- ea: `0x18004349c`
- end: `0x180043780`
- name: `NlaplgAddRow`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180042034`

## callees

- `0x180007c90`
- `0x180008704`
- `0x1800096b0`
- `0x180009755`
- `0x18000d6ec`
- `0x18000dc74`
- `0x1800172c8`
- `0x180020820`
- `0x180026f84`
- `0x1800423d4`
- `0x180042b44`
- `0x180042bc4`
- `0x180042db4`
- `0x180042dec`
- `0x180042e28`
- `0x180042e6c`
- `0x180042ec8`
- `0x18004349c`
- `0x180043f48`

## string_xrefs

- `0x1800434ed`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`
- `0x18004351e`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`
- `0x180043636`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 NlaplgAddRow(_QWORD *a1, unsigned __int16 a2, ...)
{
  int v3; // r15d
  va_list v4; // rax
  unsigned __int16 i; // r14
  unsigned int v6; // edx
  unsigned int v7; // r12d
  void *v8; // r13
  _DWORD *v9; // rcx
  const void **v10; // rdx
  int v12[2]; // [rsp+20h] [rbp-98h] BYREF
  const void **v13; // [rsp+28h] [rbp-90h]
  va_list *v14; // [rsp+30h] [rbp-88h]
  char v15; // [rsp+38h] [rbp-80h]
  va_list v16; // [rsp+40h] [rbp-78h] BYREF
  __int128 v17; // [rsp+48h] [rbp-70h] BYREF
  __int64 v18; // [rsp+58h] [rbp-60h]
  __int128 v19; // [rsp+60h] [rbp-58h] BYREF
  __int64 v20; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  va_list va; // [rsp+D0h] [rbp+18h] BYREF

  va_start(va, a2);
  v3 = 0;
  LODWORD(v16) = 0;
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
      (const char *)0x57,
      v12[0]);
  }
  if ( (unsigned __int64)((__int64)(a1[7] - a1[6]) >> 4) >= 0xFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
      (const char *)0xD000009ALL,
      v12[0]);
  v17 = 0;
  v18 = 0;
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(&v17);
  *(_QWORD *)v12 = a2;
  if ( a2 > (unsigned __int64)((v18 - (__int64)v17) >> 3) )
    std::vector<std::unique_ptr<unsigned char [0]>>::_Reallocate<0>(&v17, v12);
  v19 = 0;
  v20 = 0;
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(&v19);
  *(_QWORD *)v12 = a2;
  if ( a2 > (unsigned __int64)((v20 - (__int64)v19) >> 3) )
    std::vector<_NLA_DATA *>::_Reallocate<0>(&v19, v12);
  va_copy(v4, va);
  va_copy(v16, va);
  v14 = &v16;
  v15 = 1;
  for ( i = 0; i < a2; ++i )
  {
    v16 = v4 + 8;
    v13 = *(const void ***)v4;
    v6 = -1;
    if ( *((_DWORD *)v13 + 1) < 0xFFFFFFF4 )
      v6 = *((_DWORD *)v13 + 1) + 12;
    if ( (unsigned int)(*((_DWORD *)v13 + 1) + 12) < 0xC )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
        *((_DWORD *)v13 + 1) >= 0xFFFFFFF4 ? (const char *)0x80070216LL : 0,
        v12[0]);
    v7 = v6;
    v8 = operator new[](v6);
    memset_0(v8, 0, v7);
    *(_QWORD *)v12 = v8;
    v3 |= 1u;
    std::vector<std::unique_ptr<unsigned char [0]>>::emplace_back<std::unique_ptr<unsigned char [0]>>(
      (__int64 *)&v17,
      (__int64 *)v12);
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v12);
    v9 = *(_DWORD **)(*((_QWORD *)&v17 + 1) - 8LL);
    *(_QWORD *)v12 = v9;
    v10 = v13;
    *v9 = *(_DWORD *)v13;
    v9[2] = *((_DWORD *)v10 + 1);
    memcpy_0(v9 + 3, v10[1], *((unsigned int *)v10 + 1));
    std::vector<_NLA_DATA *>::emplace_back<_NLA_DATA * &>(&v19, v12);
    v4 = v16;
  }
  std::vector<std::vector<std::unique_ptr<unsigned char [0]>>>::emplace_back<std::vector<std::unique_ptr<unsigned char [0]>>>(
    a1,
    (__int64 *)&v17);
  std::vector<std::vector<_NLA_DATA *>>::emplace_back<std::vector<_NLA_DATA *>>(a1 + 3, &v19);
  std::vector<_NLAPLG_DATA_ROW>::emplace_back<>(a1 + 6);
  v16 = 0;
  if ( (_QWORD)v19 )
  {
    std::_Deallocate<16>((void *)v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF8uLL);
    v19 = 0;
    v20 = 0;
  }
  if ( (_QWORD)v17 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<unsigned char [0]>>>(v17, *((__int64 *)&v17 + 1));
    std::_Deallocate<16>((void *)v17, (v18 - v17) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x18004349c  mov     [rsp+arg_8], dx
0x1800434a1  mov     [rsp+arg_10], r8
0x1800434a6  mov     [rsp+arg_18], r9
0x1800434ab  push    rbx
0x1800434ac  push    rsi
0x1800434ad  push    rdi
0x1800434ae  push    r12
0x1800434b0  push    r13
0x1800434b2  push    r14
0x1800434b4  push    r15
0x1800434b6  sub     rsp, 80h
0x1800434bd  mov     rax, cs:__security_cookie
0x1800434c4  xor     rax, rsp
0x1800434c7  mov     [rsp+0B8h+var_40], rax
0x1800434cc  mov     rdi, rcx
0x1800434cf  xor     r15d, r15d
0x1800434d2  mov     dword ptr [rsp+0B8h+var_78], r15d
0x1800434d7  test    rcx, rcx
0x1800434da  jnz     short loc_1800434FC
0x1800434dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800434e1  mov     rcx, [rsp+0B8h]; this
0x1800434e9  lea     r9d, [rdi+57h]; char *
0x1800434ed  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x1800434f4  lea     edx, [rdi+6Dh]; void *
0x1800434f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800434fc  mov     rcx, [rsp+0B8h]; this
0x180043504  mov     rax, [rdi+38h]
0x180043508  sub     rax, [rdi+30h]
0x18004350c  sar     rax, 4
0x180043510  cmp     rax, 0FFFFh
0x180043516  jb      short loc_18004352F
0x180043518  mov     r9d, 0D000009Ah; char *
0x18004351e  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x180043525  mov     edx, 71h ; 'q'; void *
0x18004352a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004352f  xorps   xmm0, xmm0
0x180043532  xor     eax, eax
0x180043534  movups  [rsp+0B8h+var_70], xmm0
0x180043539  mov     [rsp+0B8h+var_60], rax
0x18004353e  lea     rcx, [rsp+0B8h+var_70]
0x180043543  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x180043548  nop
0x180043549  movzx   ecx, [rsp+0B8h+arg_8]
0x180043551  mov     qword ptr [rsp+0B8h+var_98], rcx
0x180043556  mov     rax, [rsp+0B8h+var_60]
0x18004355b  sub     rax, qword ptr [rsp+0B8h+var_70]
0x180043560  sar     rax, 3
0x180043564  cmp     rcx, rax
0x180043567  jbe     short loc_180043578
0x180043569  lea     rdx, [rsp+0B8h+var_98]
0x18004356e  lea     rcx, [rsp+0B8h+var_70]
0x180043573  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<uchar [0]>>::_Reallocate<0>(unsigned __int64 &)
0x180043578  xorps   xmm0, xmm0
0x18004357b  xor     eax, eax
0x18004357d  movups  [rsp+0B8h+var_58], xmm0
0x180043582  mov     [rsp+0B8h+var_48], rax
0x180043587  lea     rcx, [rsp+0B8h+var_58]
0x18004358c  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x180043591  nop
0x180043592  movzx   ecx, [rsp+0B8h+arg_8]
0x18004359a  mov     qword ptr [rsp+0B8h+var_98], rcx; int
0x18004359f  mov     rax, [rsp+0B8h+var_48]
0x1800435a4  sub     rax, qword ptr [rsp+0B8h+var_58]
0x1800435a9  sar     rax, 3
0x1800435ad  cmp     rcx, rax
0x1800435b0  jbe     short loc_1800435C1
0x1800435b2  lea     rdx, [rsp+0B8h+var_98]
0x1800435b7  lea     rcx, [rsp+0B8h+var_58]
0x1800435bc  call    ??$_Reallocate@$0A@@?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@AEAAXAEA_K@Z; std::vector<_NLA_DATA *>::_Reallocate<0>(unsigned __int64 &)
0x1800435c1  mov     [rsp+0B8h+var_78], 0
0x1800435ca  lea     rax, [rsp+0B8h+arg_10]
0x1800435d2  mov     [rsp+0B8h+var_78], rax
0x1800435d7  lea     rbx, [rsp+0B8h+var_78]
0x1800435dc  mov     [rsp+0B8h+var_88], rbx
0x1800435e1  mov     r12d, 1
0x1800435e7  mov     [rsp+0B8h+var_80], r12b
0x1800435ec  xor     r14d, r14d
0x1800435ef  cmp     r14w, [rsp+0B8h+arg_8]
0x1800435f8  jnb     loc_1800436D4
0x1800435fe  add     rax, 8
0x180043602  mov     [rsp+0B8h+var_78], rax
0x180043607  mov     rax, [rax-8]
0x18004360b  mov     [rsp+0B8h+var_90], rax
0x180043610  mov     eax, [rax+4]
0x180043613  add     eax, 0Ch
0x180043616  or      edx, 0FFFFFFFFh
0x180043619  cmp     eax, 0Ch
0x18004361c  cmovnb  edx, eax
0x18004361f  sbb     r9d, r9d
0x180043622  and     r9d, 80070216h; char *
0x180043629  mov     rcx, [rsp+0B8h]; this
0x180043631  cmp     eax, 0Ch
0x180043634  jnb     short loc_180043647
0x180043636  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18004363d  mov     edx, 85h; void *
0x180043642  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180043647  mov     r12d, edx
0x18004364a  mov     ecx, edx; unsigned __int64
0x18004364c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180043651  mov     r13, rax
0x180043654  mov     r8d, r12d; Size
0x180043657  xor     edx, edx; Val
0x180043659  mov     rcx, rax; void *
0x18004365c  call    memset_0
0x180043661  mov     qword ptr [rsp+0B8h+var_98], r13
0x180043666  mov     r12d, 1
0x18004366c  or      r15d, r12d
0x18004366f  lea     rdx, [rsp+0B8h+var_98]
0x180043674  lea     rcx, [rsp+0B8h+var_70]
0x180043679  call    ??$emplace_back@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<uchar [0]>>::emplace_back<std::unique_ptr<uchar [0]>>(std::unique_ptr<uchar [0]> &&)
0x18004367e  nop
0x18004367f  lea     rcx, [rsp+0B8h+var_98]
0x180043684  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180043689  mov     rax, qword ptr [rsp+0B8h+var_70+8]
0x18004368e  mov     rcx, [rax-8]
0x180043692  mov     qword ptr [rsp+0B8h+var_98], rcx
0x180043697  mov     rdx, [rsp+0B8h+var_90]
0x18004369c  mov     eax, [rdx]
0x18004369e  mov     [rcx], eax
0x1800436a0  mov     eax, [rdx+4]
0x1800436a3  mov     [rcx+8], eax
0x1800436a6  mov     r8d, [rdx+4]; Size
0x1800436aa  add     rcx, 0Ch; void *
0x1800436ae  mov     rdx, [rdx+8]; Src
0x1800436b2  call    memcpy_0
0x1800436b7  lea     rdx, [rsp+0B8h+var_98]
0x1800436bc  lea     rcx, [rsp+0B8h+var_58]
0x1800436c1  call    ??$emplace_back@AEAPEAU_NLA_DATA@@@?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@QEAAAEAPEAU_NLA_DATA@@AEAPEAU2@@Z; std::vector<_NLA_DATA *>::emplace_back<_NLA_DATA * &>(_NLA_DATA * &)
0x1800436c6  add     r14w, r12w
0x1800436ca  mov     rax, [rsp+0B8h+var_78]
0x1800436cf  jmp     loc_1800435EF
0x1800436d4  lea     rdx, [rsp+0B8h+var_70]
0x1800436d9  mov     rcx, rdi
0x1800436dc  call    ??$emplace_back@V?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@@?$vector@V?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@V?$allocator@V?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@1@$$QEAV21@@Z; std::vector<std::vector<std::unique_ptr<uchar [0]>>>::emplace_back<std::vector<std::unique_ptr<uchar [0]>>>(std::vector<std::unique_ptr<uchar [0]>> &&)
0x1800436e1  lea     rcx, [rdi+18h]
0x1800436e5  lea     rdx, [rsp+0B8h+var_58]
0x1800436ea  call    ??$emplace_back@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAAAEAV?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@1@$$QEAV21@@Z; std::vector<std::vector<_NLA_DATA *>>::emplace_back<std::vector<_NLA_DATA *>>(std::vector<_NLA_DATA *> &&)
0x1800436ef  lea     rcx, [rdi+30h]
0x1800436f3  call    ??$emplace_back@$$V@?$vector@U_NLAPLG_DATA_ROW@@V?$allocator@U_NLAPLG_DATA_ROW@@@std@@@std@@QEAAAEAU_NLAPLG_DATA_ROW@@XZ; std::vector<_NLAPLG_DATA_ROW>::emplace_back<>(void)
0x1800436f8  nop
0x1800436f9  mov     qword ptr [rbx], 0
0x180043700  mov     rcx, qword ptr [rsp+0B8h+var_58]
0x180043705  test    rcx, rcx
0x180043708  jz      short loc_18004372D
0x18004370a  mov     rdx, [rsp+0B8h+var_48]
0x18004370f  sub     rdx, rcx
0x180043712  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180043716  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004371b  xorps   xmm0, xmm0
0x18004371e  movdqu  [rsp+0B8h+var_58], xmm0
0x180043724  mov     [rsp+0B8h+var_48], 0
0x18004372d  mov     rcx, qword ptr [rsp+0B8h+var_70]
0x180043732  test    rcx, rcx
0x180043735  jz      short loc_180043757
0x180043737  mov     rdx, qword ptr [rsp+0B8h+var_70+8]
0x18004373c  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<uchar [0]>>>(std::unique_ptr<uchar [0]> *,std::unique_ptr<uchar [0]> * const,std::allocator<std::unique_ptr<uchar [0]>> &)
0x180043741  mov     rcx, qword ptr [rsp+0B8h+var_70]
0x180043746  mov     rdx, [rsp+0B8h+var_60]
0x18004374b  sub     rdx, rcx
0x18004374e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180043752  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180043757  xor     eax, eax
0x180043759  jmp     short loc_18004375F
0x18004375b  mov     eax, dword ptr [rsp+0B8h+var_78]
0x18004375f  mov     rcx, [rsp+0B8h+var_40]
0x180043764  xor     rcx, rsp; StackCookie
0x180043767  call    __security_check_cookie
0x18004376c  add     rsp, 80h
0x180043773  pop     r15
0x180043775  pop     r14
0x180043777  pop     r13
0x180043779  pop     r12
0x18004377b  pop     rdi
0x18004377c  pop     rsi
0x18004377d  pop     rbx
0x18004377e  retn
```
