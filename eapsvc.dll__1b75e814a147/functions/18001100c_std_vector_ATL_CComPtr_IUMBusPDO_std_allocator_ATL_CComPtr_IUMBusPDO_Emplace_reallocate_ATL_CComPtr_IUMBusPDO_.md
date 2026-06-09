# std::vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>>::_Emplace_reallocate<ATL::CComPtr<IUMBusPDO> const &>(ATL::CComPtr<IUMBusPDO> * const,ATL::CComPtr<IUMBusPDO> const &)

- ea: `0x18001100c`
- end: `0x180011296`
- name: `??$_Emplace_reallocate@AEBV?$CComPtr@UIUMBusPDO@@@ATL@@@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@AEAAPEAV?$CComPtr@UIUMBusPDO@@@ATL@@QEAV23@AEBV23@@Z`
- size: `650`
- prototype: `char *__fastcall(char **, char *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012cf8`

## callees

- `0x180002330`
- `0x18000aafc`
- `0x18000d360`
- `0x18000d3a0`
- `0x18001100c`
- `0x1800115fc`
- `0x180017010`

## pseudocode

```c
char *__fastcall std::vector<ATL::CComPtr<IUMBusPDO>>::_Emplace_reallocate<ATL::CComPtr<IUMBusPDO> const &>(
        char **a1,
        char *a2,
        __int64 *a3)
{
  char *v5; // rbp
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r13
  _QWORD *v11; // rsi
  void *v12; // rax
  __int64 v13; // r12
  __int64 *v14; // r15
  __int64 v15; // rcx
  char *v16; // rbp
  char *v17; // rbx
  _QWORD *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // r15
  _QWORD *v21; // r15
  __int64 v22; // rcx
  char *v23; // rbp
  _QWORD *v24; // rbx
  __int64 v25; // rcx
  char *v26; // rbx
  char *v27; // rbp
  char *v28; // rcx
  unsigned __int64 v29; // rdx
  char *v30; // rax
  _QWORD v32[3]; // [rsp+20h] [rbp-68h] BYREF
  char *v33; // [rsp+38h] [rbp-50h]
  _QWORD *v34; // [rsp+40h] [rbp-48h]
  __int64 v35; // [rsp+90h] [rbp+8h]

  v5 = *a1;
  v6 = (a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<ATL::CComPtr<IUMBusPDO>>::_Xlength();
  v7 = (a1[2] - v5) >> 3;
  v8 = v7 >> 1;
  if ( v7 > 0x1FFFFFFFFFFFFFFFLL - (v7 >> 1) )
    goto LABEL_46;
  v35 = v6 + 1;
  v9 = v6 + 1;
  if ( v8 + v7 >= v6 + 1 )
    v9 = v8 + v7;
  if ( v9 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_46;
  v10 = 8 * v9;
  if ( !(8 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(8 * v9);
    goto LABEL_13;
  }
  if ( v10 + 39 < v10 )
LABEL_46:
    std::_Throw_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    goto LABEL_41;
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_13:
  v13 = (a2 - v5) >> 3;
  v14 = &v11[v13];
  v32[0] = a1;
  v32[2] = v9;
  v34 = v14 + 1;
  v15 = *a3;
  *v14 = *a3;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v33 = (char *)&v11[v13];
  v16 = a1[1];
  v17 = *a1;
  if ( a2 == v16 )
  {
    v18 = v11;
    while ( v17 != v16 )
    {
      v19 = *(_QWORD *)v17;
      *v18 = *(_QWORD *)v17;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      ++v18;
      v17 += 8;
    }
    v20 = v13;
  }
  else
  {
    v21 = v11;
    while ( v17 != a2 )
    {
      v22 = *(_QWORD *)v17;
      *v21 = *(_QWORD *)v17;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      ++v21;
      v17 += 8;
    }
    v33 = (char *)v11;
    v20 = v13;
    v23 = a1[1];
    v24 = &v11[v13 + 1];
    while ( a2 != v23 )
    {
      v25 = *(_QWORD *)a2;
      *v24 = *(_QWORD *)a2;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      ++v24;
      a2 += 8;
    }
  }
  v32[1] = 0;
  v26 = *a1;
  if ( *a1 )
  {
    v27 = a1[1];
    while ( v26 != v27 )
    {
      if ( *(_QWORD *)v26 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 16LL))(*(_QWORD *)v26);
      v26 += 8;
    }
    v28 = *a1;
    v29 = 8 * ((a1[2] - *a1) >> 3);
    if ( v29 < 0x1000 )
    {
      v30 = *a1;
      goto LABEL_43;
    }
    v30 = (char *)*((_QWORD *)v28 - 1);
    if ( (unsigned __int64)(v28 - v30 - 8) <= 0x1F )
    {
      v29 += 39LL;
LABEL_43:
      operator delete(v30, v29);
      goto LABEL_44;
    }
LABEL_41:
    __fastfail(5u);
  }
LABEL_44:
  *a1 = (char *)v11;
  a1[1] = (char *)&v11[v35];
  a1[2] = (char *)&v11[v10 / 8];
  std::vector<ATL::CComPtr<IUMBusPDO>>::_Reallocation_guard::~_Reallocation_guard(v32);
  return (char *)&v11[v20];
}

```

## disassembly

```asm
0x18001100c  mov     [rsp+arg_8], rbx
0x180011011  mov     [rsp+arg_10], r8
0x180011016  push    rbp
0x180011017  push    rsi
0x180011018  push    rdi
0x180011019  push    r12
0x18001101b  push    r13
0x18001101d  push    r14
0x18001101f  push    r15
0x180011021  sub     rsp, 50h
0x180011025  mov     r14, rdx
0x180011028  mov     rdi, rcx
0x18001102b  mov     rbp, [rcx]
0x18001102e  mov     r9, [rcx+8]
0x180011032  sub     r9, rbp
0x180011035  sar     r9, 3
0x180011039  mov     r10, 1FFFFFFFFFFFFFFFh
0x180011043  cmp     r9, r10
0x180011046  jz      loc_18001128A
0x18001104c  mov     rcx, [rcx+10h]
0x180011050  sub     rcx, rbp
0x180011053  sar     rcx, 3
0x180011057  mov     rdx, rcx
0x18001105a  shr     rdx, 1
0x18001105d  mov     rax, r10
0x180011060  sub     rax, rdx
0x180011063  cmp     rcx, rax
0x180011066  ja      loc_180011290
0x18001106c  lea     r8, [r9+1]
0x180011070  mov     [rsp+88h+arg_0], r8
0x180011078  lea     rax, [rdx+rcx]
0x18001107c  mov     rbx, r8
0x18001107f  cmp     rax, r8
0x180011082  cmovnb  rbx, rax
0x180011086  cmp     rbx, r10
0x180011089  ja      loc_180011290
0x18001108f  lea     r13, ds:0[rbx*8]
0x180011097  test    r13, r13
0x18001109a  jnz     short loc_1800110A0
0x18001109c  xor     esi, esi
0x18001109e  jmp     short loc_1800110DD
0x1800110a0  cmp     r13, 1000h
0x1800110a7  jb      short loc_1800110D2
0x1800110a9  lea     rcx, [r13+27h]; dwBytes
0x1800110ad  cmp     rcx, r13
0x1800110b0  jbe     loc_180011290
0x1800110b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110bb  test    rax, rax
0x1800110be  jz      loc_180011237
0x1800110c4  lea     rsi, [rax+27h]
0x1800110c8  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800110cc  mov     [rsi-8], rax
0x1800110d0  jmp     short loc_1800110DD
0x1800110d2  mov     rcx, r13; dwBytes
0x1800110d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110da  mov     rsi, rax
0x1800110dd  mov     r12, r14
0x1800110e0  sub     r12, rbp
0x1800110e3  sar     r12, 3
0x1800110e7  lea     r15, [rsi+r12*8]
0x1800110eb  mov     [rsp+88h+var_68], rdi
0x1800110f0  mov     [rsp+88h+var_58], rbx
0x1800110f5  lea     rcx, [r15+8]
0x1800110f9  mov     [rsp+88h+var_48], rcx
0x1800110fe  mov     rcx, [rsp+88h+arg_10]
0x180011106  mov     rcx, [rcx]
0x180011109  mov     [r15], rcx
0x18001110c  test    rcx, rcx
0x18001110f  jz      short loc_18001111E
0x180011111  mov     rax, [rcx]
0x180011114  mov     rax, [rax+8]
0x180011118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111d  nop
0x18001111e  mov     [rsp+88h+var_50], r15
0x180011123  mov     rbp, [rdi+8]
0x180011127  mov     rbx, [rdi]
0x18001112a  cmp     r14, rbp
0x18001112d  jnz     short loc_180011163
0x18001112f  mov     r14, rsi
0x180011132  jmp     short loc_180011154
0x180011134  mov     rcx, [rbx]
0x180011137  mov     [r14], rcx
0x18001113a  test    rcx, rcx
0x18001113d  jz      short loc_18001114C
0x18001113f  mov     rax, [rcx]
0x180011142  mov     rax, [rax+8]
0x180011146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114b  nop
0x18001114c  add     r14, 8
0x180011150  add     rbx, 8
0x180011154  cmp     rbx, rbp
0x180011157  jnz     short loc_180011134
0x180011159  lea     r15, ds:0[r12*8]
0x180011161  jmp     short loc_1800111CC
0x180011163  mov     r15, rsi
0x180011166  jmp     short loc_180011188
0x180011168  mov     rcx, [rbx]
0x18001116b  mov     [r15], rcx
0x18001116e  test    rcx, rcx
0x180011171  jz      short loc_180011180
0x180011173  mov     rax, [rcx]
0x180011176  mov     rax, [rax+8]
0x18001117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001117f  nop
0x180011180  add     r15, 8
0x180011184  add     rbx, 8
0x180011188  cmp     rbx, r14
0x18001118b  jnz     short loc_180011168
0x18001118d  mov     [rsp+88h+var_50], rsi
0x180011192  lea     r15, ds:0[r12*8]
0x18001119a  mov     rbp, [rdi+8]
0x18001119e  lea     rbx, [r15+8]
0x1800111a2  add     rbx, rsi
0x1800111a5  jmp     short loc_1800111C7
0x1800111a7  mov     rcx, [r14]
0x1800111aa  mov     [rbx], rcx
0x1800111ad  test    rcx, rcx
0x1800111b0  jz      short loc_1800111BF
0x1800111b2  mov     rax, [rcx]
0x1800111b5  mov     rax, [rax+8]
0x1800111b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111be  nop
0x1800111bf  add     rbx, 8
0x1800111c3  add     r14, 8
0x1800111c7  cmp     r14, rbp
0x1800111ca  jnz     short loc_1800111A7
0x1800111cc  mov     [rsp+88h+var_60], 0
0x1800111d5  mov     rbx, [rdi]
0x1800111d8  test    rbx, rbx
0x1800111db  jz      short loc_180011249
0x1800111dd  mov     rbp, [rdi+8]
0x1800111e1  jmp     short loc_1800111FC
0x1800111e3  mov     rcx, [rbx]
0x1800111e6  test    rcx, rcx
0x1800111e9  jz      short loc_1800111F8
0x1800111eb  mov     rax, [rcx]
0x1800111ee  mov     rax, [rax+10h]
0x1800111f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f7  nop
0x1800111f8  add     rbx, 8
0x1800111fc  cmp     rbx, rbp
0x1800111ff  jnz     short loc_1800111E3
0x180011201  mov     rcx, [rdi]
0x180011204  mov     rax, [rdi+10h]
0x180011208  sub     rax, rcx
0x18001120b  sar     rax, 3
0x18001120f  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180011217  cmp     rdx, 1000h
0x18001121e  jb      short loc_18001123E
0x180011220  mov     rax, [rcx-8]
0x180011224  sub     rcx, rax
0x180011227  sub     rcx, 8
0x18001122b  cmp     rcx, 1Fh
0x18001122f  ja      short loc_180011237
0x180011231  add     rdx, 27h ; '''
0x180011235  jmp     short loc_180011241
0x180011237  mov     ecx, 5
0x18001123c  int     29h; Win8: RtlFailFast(ecx)
0x18001123e  mov     rax, rcx
0x180011241  mov     rcx, rax; void *
0x180011244  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011249  mov     [rdi], rsi
0x18001124c  mov     rax, [rsp+88h+arg_0]
0x180011254  lea     rax, [rsi+rax*8]
0x180011258  mov     [rdi+8], rax
0x18001125c  lea     rax, [rsi+r13]
0x180011260  mov     [rdi+10h], rax
0x180011264  lea     rcx, [rsp+88h+var_68]
0x180011269  call    ??1_Reallocation_guard@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComPtr<IUMBusPDO>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001126e  lea     rax, [r15+rsi]
0x180011272  mov     rbx, [rsp+88h+arg_8]
0x18001127a  add     rsp, 50h
0x18001127e  pop     r15
0x180011280  pop     r14
0x180011282  pop     r13
0x180011284  pop     r12
0x180011286  pop     rdi
0x180011287  pop     rsi
0x180011288  pop     rbp
0x180011289  retn
0x18001128a  call    ?_Xlength@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComPtr<IUMBusPDO>>::_Xlength(void)
0x180011290  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
