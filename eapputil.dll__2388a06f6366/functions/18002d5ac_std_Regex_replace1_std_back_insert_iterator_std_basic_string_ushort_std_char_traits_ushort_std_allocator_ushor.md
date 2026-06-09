# std::_Regex_replace1<std::back_insert_iterator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,ushort const *,std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::back_insert_iterator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,ushort const *,ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::regex_constants::match_flag_type)

- ea: `0x18002d5ac`
- end: `0x18002d8ef`
- name: `??$_Regex_replace1@V?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEBGV?$regex_traits@G@2@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@V10@PEBG1AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@W4match_flag_type@regex_constants@0@@Z`
- size: `835`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int16 *, __int16 *, __int64 *, _QWORD *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002d8f8`

## callees

- `0x18000eb48`
- `0x180014b98`
- `0x180014efc`
- `0x180016970`
- `0x1800176e8`
- `0x180017758`
- `0x18002ce4c`
- `0x18002d2a0`
- `0x18002d5ac`
- `0x18002db34`
- `0x18002e654`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Regex_replace1<std::back_insert_iterator<std::wstring>,unsigned short const *,std::regex_traits<unsigned short>,unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        _QWORD *a1,
        __int64 a2,
        __int16 *a3,
        __int16 *a4,
        __int64 *a5,
        _QWORD *a6,
        int a7)
{
  _QWORD *v9; // rbx
  int v10; // r14d
  int v11; // esi
  _QWORD *v12; // r13
  int v13; // esi
  __int16 *v14; // r15
  char v15; // r14
  int i; // edx
  __int64 v17; // rax
  int v18; // esi
  __int16 *v19; // rsi
  __int16 *j; // rdi
  __int16 v21; // r9
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // r9
  _QWORD **v26; // rax
  _QWORD *v27; // r8
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int16 v31; // r9
  unsigned __int64 v32; // rcx
  char *v34; // [rsp+20h] [rbp-E0h]
  __int16 *v35; // [rsp+40h] [rbp-C0h] BYREF
  char v36; // [rsp+48h] [rbp-B8h]
  __int128 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+60h] [rbp-A0h]
  __int16 *v39; // [rsp+70h] [rbp-90h]
  bool v40; // [rsp+78h] [rbp-88h]
  __int128 v41; // [rsp+80h] [rbp-80h]
  char v42; // [rsp+90h] [rbp-70h]
  _QWORD v43[2]; // [rsp+98h] [rbp-68h] BYREF
  char v44; // [rsp+A8h] [rbp-58h]
  char v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v46[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v47[32]; // [rsp+C8h] [rbp-38h] BYREF
  char v48[32]; // [rsp+E8h] [rbp-18h] BYREF
  char v49[32]; // [rsp+108h] [rbp+8h] BYREF
  char v50[24]; // [rsp+128h] [rbp+28h] BYREF
  char v51[24]; // [rsp+140h] [rbp+40h] BYREF
  char v52[32]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v53; // [rsp+178h] [rbp+78h]
  unsigned int v54; // [rsp+194h] [rbp+94h]
  char v56; // [rsp+220h] [rbp+120h] BYREF

  v9 = (_QWORD *)a2;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43[0] = 0;
  v43[1] = 0;
  v44 = 0;
  v10 = 0;
  a7 = 0;
  v11 = 0;
  v12 = a6;
  while ( *a5 )
  {
    v13 = v10 | v11;
    v14 = a3;
    if ( (v13 & 0x4000) != 0 && a3 != a4 )
      v14 = a3 + 1;
    std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(
      (unsigned int)v46,
      (_DWORD)v14,
      (_DWORD)a4,
      (_DWORD)a5 + 8,
      *a5,
      *(_DWORD *)(*a5 + 40),
      *(_DWORD *)(*a5 + 32),
      v13);
    if ( (unsigned __int8)std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                            v46,
                            &v35,
                            0) )
      goto LABEL_14;
    v15 = 0;
    if ( v14 != a4 && (v13 & 0x40) == 0 )
    {
      v54 = v54 & 0xFFFFDEFF | 0x100;
      for ( i = (_DWORD)v14 + 2; ; i = v18 + 2 )
      {
        v17 = std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Skip(
                (unsigned int)v46,
                i,
                (_DWORD)a4,
                0,
                0);
        v18 = v17;
        if ( (__int16 *)v17 == a4 )
          break;
        v53 = v17;
        if ( (unsigned __int8)std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                                v46,
                                &v35,
                                0) )
          goto LABEL_14;
      }
      v53 = (__int64)a4;
      if ( (unsigned __int8)std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                              v46,
                              &v35,
                              0) )
      {
LABEL_14:
        v15 = 1;
        v35 = a3;
        *((_QWORD *)&v38 + 1) = a3;
        v40 = a3 != v39;
      }
    }
    std::vector<std::_Tgt_state_t<unsigned short const *>>::~vector<std::_Tgt_state_t<unsigned short const *>>(v52);
    std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v51);
    std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v50);
    std::vector<unsigned int>::~vector<unsigned int>(v49);
    std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v48);
    std::vector<unsigned int>::~vector<unsigned int>(v47);
    if ( !v15 )
      break;
    v19 = v39;
    for ( j = (__int16 *)*((_QWORD *)&v38 + 1); j != v19; ++j )
    {
      v21 = *j;
      v22 = v9[2];
      if ( v22 >= v9[3] )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v9);
      }
      else
      {
        v9[2] = v22 + 1;
        if ( v9[3] <= 7u )
          v23 = v9;
        else
          v23 = (_QWORD *)*v9;
        *((_WORD *)v23 + v22) = v21;
        *((_WORD *)v23 + v22 + 1) = 0;
      }
    }
    v24 = v12;
    if ( v12[3] <= 7u )
    {
      v25 = v12;
    }
    else
    {
      v24 = (_QWORD *)*v12;
      v25 = (_QWORD *)*v12;
    }
    v10 = a7;
    v34 = (char *)v24 + 2 * v12[2];
    if ( (a7 & 0x400) != 0 )
      v26 = (_QWORD **)std::_Format_sed<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short const *,std::back_insert_iterator<std::wstring>>(
                         &v56,
                         &v35,
                         v9,
                         v25,
                         v34);
    else
      v26 = (_QWORD **)std::_Format_default<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short const *,std::back_insert_iterator<std::wstring>>(
                         v45,
                         &v35,
                         v9,
                         v25,
                         v34);
    v9 = *v26;
    v27 = (_QWORD *)v37;
    a2 = (*((_QWORD *)&v37 + 1) - (_QWORD)v37) / 24LL;
    v28 = v43;
    if ( a2 )
      v28 = (_QWORD *)v37;
    a3 = (__int16 *)v28[1];
    if ( a3 == a4 )
      goto LABEL_50;
    if ( a2 )
    {
      v29 = (_QWORD *)v37;
    }
    else
    {
      v27 = v43;
      v29 = v43;
    }
    v30 = v29[1];
    if ( *v27 != v30 )
    {
      v10 |= 0x100u;
      a7 = v10;
    }
    v11 = 0x2000;
    if ( *v27 != v30 )
      v11 = 0;
  }
  while ( a3 != a4 )
  {
    v31 = *a3;
    v32 = v9[2];
    if ( v32 >= v9[3] )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v9);
    }
    else
    {
      v9[2] = v32 + 1;
      if ( v9[3] <= 7u )
        a2 = (__int64)v9;
      else
        a2 = *v9;
      *(_WORD *)(a2 + 2 * v32) = v31;
      *(_WORD *)(a2 + 2 * v32 + 2) = 0;
    }
    ++a3;
  }
LABEL_50:
  *a1 = v9;
  std::vector<std::sub_match<unsigned short const *>>::~vector<std::sub_match<unsigned short const *>>(&v37, a2);
  return a1;
}

```

## disassembly

```asm
0x18002d5ac  mov     [rsp-8+arg_8], rbx
0x18002d5b1  mov     [rsp-8+arg_0], rcx
0x18002d5b6  push    rbp
0x18002d5b7  push    rsi
0x18002d5b8  push    rdi
0x18002d5b9  push    r12
0x18002d5bb  push    r13
0x18002d5bd  push    r14
0x18002d5bf  push    r15
0x18002d5c1  lea     rbp, [rsp-0D0h]
0x18002d5c9  sub     rsp, 1D0h
0x18002d5d0  mov     r12, r9
0x18002d5d3  mov     rdi, r8
0x18002d5d6  mov     rbx, rdx
0x18002d5d9  xor     r15d, r15d
0x18002d5dc  mov     [rsp+200h+var_1C0], r15
0x18002d5e1  mov     [rsp+200h+var_1B8], r15b
0x18002d5e6  xorps   xmm0, xmm0
0x18002d5e9  movdqa  [rsp+200h+var_1B0], xmm0
0x18002d5ef  xorps   xmm1, xmm1
0x18002d5f2  movdqa  [rsp+200h+var_1A0], xmm1
0x18002d5f8  mov     [rsp+200h+var_190], r15
0x18002d5fd  mov     [rsp+200h+var_188], r15b
0x18002d602  movdqa  [rbp+100h+var_180], xmm0
0x18002d607  mov     [rbp+100h+var_170], r15b
0x18002d60b  mov     [rbp+100h+var_168], r15
0x18002d60f  mov     [rbp+100h+var_160], r15
0x18002d613  mov     [rbp+100h+var_158], r15b
0x18002d617  mov     r14d, r15d
0x18002d61a  mov     [rbp+100h+arg_30], r15d
0x18002d621  mov     esi, r15d
0x18002d624  mov     r13, [rbp+100h+arg_28]
0x18002d62b  mov     rax, [rbp+100h+arg_20]
0x18002d632  mov     rcx, [rax]
0x18002d635  test    rcx, rcx
0x18002d638  jz      loc_18002D8B8
0x18002d63e  or      esi, r14d
0x18002d641  mov     r15, rdi
0x18002d644  bt      esi, 0Eh
0x18002d648  jnb     short loc_18002D653
0x18002d64a  cmp     rdi, r12
0x18002d64d  jz      short loc_18002D653
0x18002d64f  lea     r15, [rdi+2]
0x18002d653  lea     r9, [rax+8]
0x18002d657  mov     [rsp+200h+var_1C8], esi
0x18002d65b  mov     eax, [rcx+20h]
0x18002d65e  mov     [rsp+200h+var_1D0], eax
0x18002d662  mov     eax, [rcx+28h]
0x18002d665  mov     [rsp+200h+var_1D8], eax
0x18002d669  mov     [rsp+200h+var_1E0], rcx
0x18002d66e  mov     r8, r12
0x18002d671  mov     rdx, r15
0x18002d674  lea     rcx, [rbp+100h+var_140]
0x18002d678  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x18002d67d  nop
0x18002d67e  xor     r8d, r8d
0x18002d681  lea     rdx, [rsp+200h+var_1C0]
0x18002d686  lea     rcx, [rbp+100h+var_140]
0x18002d68a  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x18002d68f  test    al, al
0x18002d691  jnz     short loc_18002D70B
0x18002d693  xor     r14b, r14b
0x18002d696  cmp     r15, r12
0x18002d699  jz      loc_18002D722
0x18002d69f  test    sil, 40h
0x18002d6a3  jnz     short loc_18002D722
0x18002d6a5  mov     eax, [rbp+100h+var_6C]
0x18002d6ab  btr     eax, 0Dh
0x18002d6af  bts     eax, 8
0x18002d6b3  mov     [rbp+100h+var_6C], eax
0x18002d6b9  lea     rdx, [r15+2]
0x18002d6bd  jmp     short loc_18002D6D3
0x18002d6bf  mov     [rbp+100h+var_88], rsi
0x18002d6c3  xor     r8d, r8d
0x18002d6c6  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x18002d6cb  test    al, al
0x18002d6cd  jnz     short loc_18002D70B
0x18002d6cf  lea     rdx, [rsi+2]
0x18002d6d3  mov     dword ptr [rsp+200h+var_1E0], 0
0x18002d6db  xor     r9d, r9d
0x18002d6de  mov     r8, r12
0x18002d6e1  lea     rcx, [rbp+100h+var_140]
0x18002d6e5  call    ?_Skip@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAAPEBGPEBG0PEAV_Node_base@2@I@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Skip(ushort const *,ushort const *,std::_Node_base *,uint)
0x18002d6ea  cmp     rax, r12
0x18002d6ed  mov     rsi, rax
0x18002d6f0  lea     rdx, [rsp+200h+var_1C0]
0x18002d6f5  lea     rcx, [rbp+100h+var_140]
0x18002d6f9  jnz     short loc_18002D6BF
0x18002d6fb  mov     [rbp+100h+var_88], r12
0x18002d6ff  xor     r8d, r8d
0x18002d702  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x18002d707  test    al, al
0x18002d709  jz      short loc_18002D722
0x18002d70b  mov     r14b, 1
0x18002d70e  mov     [rsp+200h+var_1C0], rdi
0x18002d713  mov     qword ptr [rsp+200h+var_1A0+8], rdi
0x18002d718  cmp     rdi, [rsp+200h+var_190]
0x18002d71d  setnz   [rsp+200h+var_188]
0x18002d722  lea     rcx, [rbp+100h+var_A8]
0x18002d726  call    ??1?$vector@V?$_Tgt_state_t@PEBG@std@@V?$allocator@V?$_Tgt_state_t@PEBG@std@@@2@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<ushort const *>>::~vector<std::_Tgt_state_t<ushort const *>>(void)
0x18002d72b  lea     rcx, [rbp+100h+var_C0]
0x18002d72f  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18002d734  lea     rcx, [rbp+100h+var_D8]
0x18002d738  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18002d73d  lea     rcx, [rbp+100h+var_F8]
0x18002d741  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18002d746  lea     rcx, [rbp+100h+var_118]
0x18002d74a  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18002d74f  lea     rcx, [rbp+100h+var_138]
0x18002d753  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18002d758  xor     r15d, r15d
0x18002d75b  test    r14b, r14b
0x18002d75e  jz      loc_18002D8B8
0x18002d764  mov     rsi, [rsp+200h+var_190]
0x18002d769  mov     rdi, qword ptr [rsp+200h+var_1A0+8]
0x18002d76e  jmp     short loc_18002D7AE
0x18002d770  movzx   r9d, word ptr [rdi]
0x18002d774  mov     rcx, [rbx+10h]
0x18002d778  cmp     rcx, [rbx+18h]
0x18002d77c  jnb     short loc_18002D7A2
0x18002d77e  lea     rax, [rcx+1]
0x18002d782  mov     [rbx+10h], rax
0x18002d786  cmp     qword ptr [rbx+18h], 7
0x18002d78b  jbe     short loc_18002D792
0x18002d78d  mov     rdx, [rbx]
0x18002d790  jmp     short loc_18002D795
0x18002d792  mov     rdx, rbx
0x18002d795  mov     [rdx+rcx*2], r9w
0x18002d79a  mov     [rdx+rcx*2+2], r15w
0x18002d7a0  jmp     short loc_18002D7AA
0x18002d7a2  mov     rcx, rbx; Src
0x18002d7a5  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18002d7aa  add     rdi, 2
0x18002d7ae  cmp     rdi, rsi
0x18002d7b1  jnz     short loc_18002D770
0x18002d7b3  mov     rcx, r13
0x18002d7b6  cmp     qword ptr [r13+18h], 7
0x18002d7bb  jbe     short loc_18002D7C1
0x18002d7bd  mov     rcx, [r13+0]
0x18002d7c1  mov     rax, [r13+10h]
0x18002d7c5  lea     rdx, [rcx+rax*2]
0x18002d7c9  jbe     short loc_18002D7D1
0x18002d7cb  mov     r9, [r13+0]
0x18002d7cf  jmp     short loc_18002D7D4
0x18002d7d1  mov     r9, r13
0x18002d7d4  mov     r14d, [rbp+100h+arg_30]
0x18002d7db  mov     [rsp+200h+var_1E0], rdx
0x18002d7e0  mov     r8, rbx
0x18002d7e3  lea     rdx, [rsp+200h+var_1C0]
0x18002d7e8  bt      r14d, 0Ah
0x18002d7ed  jnb     short loc_18002D7FD
0x18002d7ef  lea     rcx, [rbp+100h+arg_10]
0x18002d7f6  call    ??$_Format_sed@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@PEBGV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YA?AV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEBV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@V10@PEBG2W4match_flag_type@regex_constants@0@@Z; std::_Format_sed<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort const *,std::back_insert_iterator<std::wstring>>(std::match_results<ushort const *> const &,std::back_insert_iterator<std::wstring>,ushort const *,ushort const *,std::regex_constants::match_flag_type)
0x18002d7fb  jmp     short loc_18002D806
0x18002d7fd  lea     rcx, [rbp+100h+var_150]
0x18002d801  call    ??$_Format_default@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@PEBGV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YA?AV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEBV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@V10@PEBG2W4match_flag_type@regex_constants@0@@Z; std::_Format_default<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort const *,std::back_insert_iterator<std::wstring>>(std::match_results<ushort const *> const &,std::back_insert_iterator<std::wstring>,ushort const *,ushort const *,std::regex_constants::match_flag_type)
0x18002d806  mov     rbx, [rax]
0x18002d809  mov     r8, qword ptr [rsp+200h+var_1B0]
0x18002d80e  mov     rcx, qword ptr [rsp+200h+var_1B0+8]
0x18002d813  sub     rcx, r8
0x18002d816  mov     rax, 2AAAAAAAAAAAAAABh
0x18002d820  imul    rcx
0x18002d823  sar     rdx, 2
0x18002d827  mov     rax, rdx
0x18002d82a  shr     rax, 3Fh
0x18002d82e  add     rdx, rax
0x18002d831  lea     rax, [rbp+100h+var_168]
0x18002d835  cmovnz  rax, r8
0x18002d839  mov     rdi, [rax+8]
0x18002d83d  cmp     rdi, r12
0x18002d840  jz      short loc_18002D8BD
0x18002d842  test    rdx, rdx
0x18002d845  jnz     short loc_18002D851
0x18002d847  lea     r8, [rbp+100h+var_168]
0x18002d84b  lea     rax, [rbp+100h+var_168]
0x18002d84f  jmp     short loc_18002D854
0x18002d851  mov     rax, r8
0x18002d854  mov     rcx, [rax+8]
0x18002d858  cmp     [r8], rcx
0x18002d85b  jz      short loc_18002D869
0x18002d85d  bts     r14d, 8
0x18002d862  mov     [rbp+100h+arg_30], r14d
0x18002d869  mov     esi, 2000h
0x18002d86e  cmp     [r8], rcx
0x18002d871  cmovnz  esi, r15d
0x18002d875  jmp     loc_18002D62B
0x18002d87a  movzx   r9d, word ptr [rdi]
0x18002d87e  mov     rcx, [rbx+10h]
0x18002d882  cmp     rcx, [rbx+18h]
0x18002d886  jnb     short loc_18002D8AC
0x18002d888  lea     rax, [rcx+1]
0x18002d88c  mov     [rbx+10h], rax
0x18002d890  cmp     qword ptr [rbx+18h], 7
0x18002d895  jbe     short loc_18002D89C
0x18002d897  mov     rdx, [rbx]
0x18002d89a  jmp     short loc_18002D89F
0x18002d89c  mov     rdx, rbx
0x18002d89f  mov     [rdx+rcx*2], r9w
0x18002d8a4  mov     [rdx+rcx*2+2], r15w
0x18002d8aa  jmp     short loc_18002D8B4
0x18002d8ac  mov     rcx, rbx; Src
0x18002d8af  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18002d8b4  add     rdi, 2
0x18002d8b8  cmp     rdi, r12
0x18002d8bb  jnz     short loc_18002D87A
0x18002d8bd  mov     r15, [rbp+100h+arg_0]
0x18002d8c4  mov     [r15], rbx
0x18002d8c7  lea     rcx, [rsp+200h+var_1B0]
0x18002d8cc  call    ??1?$vector@V?$sub_match@PEBG@std@@V?$allocator@V?$sub_match@PEBG@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<ushort const *>>::~vector<std::sub_match<ushort const *>>(void)
0x18002d8d1  mov     rax, r15
0x18002d8d4  mov     rbx, [rsp+200h+arg_8]
0x18002d8dc  add     rsp, 1D0h
0x18002d8e3  pop     r15
0x18002d8e5  pop     r14
0x18002d8e7  pop     r13
0x18002d8e9  pop     r12
0x18002d8eb  pop     rdi
0x18002d8ec  pop     rsi
0x18002d8ed  pop     rbp
0x18002d8ee  retn
```
