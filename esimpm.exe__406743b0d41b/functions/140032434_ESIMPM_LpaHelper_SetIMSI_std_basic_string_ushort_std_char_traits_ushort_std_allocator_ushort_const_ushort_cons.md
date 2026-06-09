# ESIMPM::LpaHelper::SetIMSI(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const * const)

- ea: `0x140032434`
- end: `0x14003267d`
- name: `?SetIMSI@LpaHelper@ESIMPM@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z`
- size: `585`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140029040`
- `0x14002a4b8`

## callees

- `0x140002f60`
- `0x140003b1c`
- `0x14000dd20`
- `0x140013df8`
- `0x140014f64`
- `0x1400167fc`
- `0x14001a9b4`
- `0x140020620`
- `0x140032434`
- `0x140032684`
- `0x1400336c8`

## string_xrefs

- `0x14003247a`: `profileid %s, imsi %s`
- `0x140032483`: `ESIMPM::LpaHelper::SetIMSI`
- `0x14003264a`: `ESIMPM::LpaHelper::SetIMSI`
- `0x14003261d`: `ESIMPM::EsimProfile::SetImsi`
- `0x140032573`: `cache\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ESIMPM::LpaHelper::SetIMSI(__int64 a1, const wchar_t *a2, _WORD *a3)
{
  const wchar_t *v4; // rdi
  const wchar_t *v6; // r9
  __int64 *v7; // rbx
  __int64 *v8; // rcx
  __int64 v9; // r8
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned __int64 *v13; // r13
  void **v14; // rdi
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rdx
  char *v17; // r14
  __int64 v18; // rbx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r9
  const unsigned __int16 *v23; // rdx
  unsigned int v24; // eax
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v26[2]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v27; // [rsp+48h] [rbp-38h]
  _OWORD Src[2]; // [rsp+58h] [rbp-28h] BYREF

  v4 = a2;
  v6 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v6 = *(const wchar_t **)a2;
  ESIMPM::Log::Info("ESIMPM::LpaHelper::SetIMSI", 0, L"profileid %s, imsi %s", v6, a3);
  v7 = **(__int64 ***)(a1 + 24);
  while ( !*((_BYTE *)v7 + 25) )
  {
    v8 = (__int64 *)v7[8];
    if ( *(_DWORD *)(*v8 + 112) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(
        v8 + 1,
        &v25,
        v4);
      if ( *(_QWORD *)(v7[8] + 8) != v25 )
      {
        v13 = *(unsigned __int64 **)(v25 + 64);
        v14 = (void **)(v13 + 8);
        v15 = -1;
        v16 = -1;
        do
          ++v16;
        while ( a3[v16] );
        if ( v16 > v13[11] )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
            v14,
            v16,
            v9,
            a3);
        }
        else
        {
          v17 = (char *)(v13 + 8);
          if ( v13[11] > 7 )
            v17 = (char *)*v14;
          v13[10] = v16;
          v18 = 2 * v16;
          memmove_0(v17, a3, 2 * v16);
          *(_WORD *)&v17[v18] = 0;
        }
        memset(Src, 0, sizeof(Src));
        do
          ++v15;
        while ( ESIMPM::strCache[v15] );
        std::wstring::_Construct<1,unsigned short const *>(Src, L"cache\\", v15);
        v19 = v13 + 4;
        if ( v13[7] > 7 )
          v19 = (_QWORD *)*v19;
        v20 = std::wstring::_Append<unsigned short>(Src, v19, v13[6]);
        *(_OWORD *)v26 = *(_OWORD *)v20;
        v27 = *((_OWORD *)v20 + 1);
        *(_WORD *)v20 = 0;
        v20[2] = 0;
        v20[3] = 7;
        std::wstring::_Tidy_deallocate((char **)Src);
        v22 = (const unsigned __int16 *)(v13 + 8);
        if ( v13[11] > 7 )
          v22 = (const unsigned __int16 *)*v14;
        v23 = (const unsigned __int16 *)v26;
        if ( *((_QWORD *)&v27 + 1) > 7u )
          v23 = v26[0];
        v24 = StateSeparation::SetString(*((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120), v23, v21, v22);
        if ( v13[11] > 7 )
          v14 = (void **)*v14;
        ESIMPM::Log::Info("ESIMPM::EsimProfile::SetImsi", 0, L"ret 0x%x: %s", v24, v14);
        std::wstring::_Tidy_deallocate((char **)v26);
        return;
      }
    }
    v10 = (__int64 **)v7[2];
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v7 = i;
      v7 = i;
    }
    else
    {
      v7 = (__int64 *)v7[2];
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v7 = j;
    }
  }
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  ESIMPM::Log::Error("ESIMPM::LpaHelper::SetIMSI", 0, L"failed to find esim profile %s", v4);
}

```

## disassembly

```asm
0x140032434  mov     [rsp-38h+arg_0], rbx
0x140032439  push    rbp
0x14003243a  push    rsi
0x14003243b  push    rdi
0x14003243c  push    r12
0x14003243e  push    r13
0x140032440  push    r14
0x140032442  push    r15
0x140032444  mov     rbp, rsp
0x140032447  sub     rsp, 80h
0x14003244e  mov     rax, cs:__security_cookie
0x140032455  xor     rax, rsp
0x140032458  mov     [rbp+var_8], rax
0x14003245c  mov     r15, r8
0x14003245f  mov     rdi, rdx
0x140032462  mov     rbx, rcx
0x140032465  xor     r12d, r12d
0x140032468  mov     r9, rdx
0x14003246b  cmp     qword ptr [rdx+18h], 7
0x140032470  jbe     short loc_140032475
0x140032472  mov     r9, [rdx]
0x140032475  mov     [rsp+80h+var_60], r15
0x14003247a  lea     r8, aProfileidSImsi; "profileid %s, imsi %s"
0x140032481  xor     edx, edx; struct _GUID *
0x140032483  lea     rcx, aEsimpmLpahelpe_13; "ESIMPM::LpaHelper::SetIMSI"
0x14003248a  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14003248f  mov     rbx, [rbx+18h]
0x140032493  mov     rbx, [rbx]
0x140032496  cmp     [rbx+19h], r12b
0x14003249a  jnz     loc_140032634
0x1400324a0  mov     rcx, [rbx+40h]
0x1400324a4  mov     rax, [rcx]
0x1400324a7  cmp     [rax+70h], r12d
0x1400324ab  jz      short loc_1400324CB
0x1400324ad  add     rcx, 8
0x1400324b1  mov     r8, rdi
0x1400324b4  lea     rdx, [rbp+var_50]
0x1400324b8  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(std::wstring const &)
0x1400324bd  mov     rcx, [rbx+40h]
0x1400324c1  mov     rax, [rbp+var_50]
0x1400324c5  cmp     [rcx+8], rax
0x1400324c9  jnz     short loc_140032510
0x1400324cb  mov     rcx, [rbx+10h]
0x1400324cf  cmp     [rcx+19h], r12b
0x1400324d3  jz      short loc_1400324F3
0x1400324d5  mov     rax, [rbx+8]
0x1400324d9  jmp     short loc_1400324E8
0x1400324db  cmp     rbx, [rax+10h]
0x1400324df  jnz     short loc_1400324EE
0x1400324e1  mov     rbx, rax
0x1400324e4  mov     rax, [rax+8]
0x1400324e8  cmp     [rax+19h], r12b
0x1400324ec  jz      short loc_1400324DB
0x1400324ee  mov     rbx, rax
0x1400324f1  jmp     short loc_140032496
0x1400324f3  mov     rbx, rcx
0x1400324f6  mov     rcx, [rcx]
0x1400324f9  cmp     [rcx+19h], r12b
0x1400324fd  jnz     short loc_140032496
0x1400324ff  mov     rbx, rcx
0x140032502  mov     rax, [rcx]
0x140032505  mov     rcx, rax
0x140032508  cmp     [rax+19h], r12b
0x14003250c  jz      short loc_1400324FF
0x14003250e  jmp     short loc_140032496
0x140032510  mov     r13, [rax+40h]
0x140032514  lea     rdi, [r13+40h]
0x140032518  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14003251c  mov     rdx, rsi
0x14003251f  inc     rdx
0x140032522  cmp     [r15+rdx*2], r12w
0x140032527  jnz     short loc_14003251F
0x140032529  cmp     rdx, [rdi+18h]
0x14003252d  ja      short loc_140032559
0x14003252f  mov     r14, rdi
0x140032532  cmp     qword ptr [rdi+18h], 7
0x140032537  jbe     short loc_14003253C
0x140032539  mov     r14, [rdi]
0x14003253c  mov     [rdi+10h], rdx
0x140032540  lea     rbx, [rdx+rdx]
0x140032544  mov     r8, rbx; Size
0x140032547  mov     rdx, r15; Src
0x14003254a  mov     rcx, r14; void *
0x14003254d  call    memmove_0
0x140032552  mov     [rbx+r14], r12w
0x140032557  jmp     short loc_140032564
0x140032559  mov     r9, r15
0x14003255c  mov     rcx, rdi
0x14003255f  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x140032564  xorps   xmm0, xmm0
0x140032567  movups  [rbp+Src], xmm0
0x14003256b  xorps   xmm1, xmm1
0x14003256e  movdqu  [rbp+var_18], xmm1
0x140032573  lea     rdx, ?strCache@ESIMPM@@3QBGB; "cache\\"
0x14003257a  inc     rsi
0x14003257d  cmp     [rdx+rsi*2], r12w
0x140032582  jnz     short loc_14003257A
0x140032584  mov     r8, rsi
0x140032587  lea     rcx, [rbp+Src]
0x14003258b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140032590  nop
0x140032591  lea     rdx, [r13+20h]
0x140032595  mov     r8, [rdx+10h]
0x140032599  cmp     qword ptr [rdx+18h], 7
0x14003259e  jbe     short loc_1400325A3
0x1400325a0  mov     rdx, [rdx]
0x1400325a3  lea     rcx, [rbp+Src]; Src
0x1400325a7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1400325ac  movups  xmm0, xmmword ptr [rax]
0x1400325af  movups  xmmword ptr [rbp+var_48], xmm0
0x1400325b3  movups  xmm1, xmmword ptr [rax+10h]
0x1400325b7  movups  [rbp+var_38], xmm1
0x1400325bb  mov     [rax], r12w
0x1400325bf  mov     [rax+10h], r12
0x1400325c3  mov     qword ptr [rax+18h], 7
0x1400325cb  lea     rcx, [rbp+Src]
0x1400325cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400325d4  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400325db  mov     r9, rdi
0x1400325de  cmp     qword ptr [rdi+18h], 7
0x1400325e3  jbe     short loc_1400325E8
0x1400325e5  mov     r9, [rdi]; unsigned __int16 *
0x1400325e8  lea     rdx, [rbp+var_48]
0x1400325ec  cmp     qword ptr [rbp+var_38+8], 7
0x1400325f1  cmova   rdx, [rbp+var_48]; unsigned __int16 *
0x1400325f6  mov     rcx, [rax+3C0h]; this
0x1400325fd  call    ?SetString@StateSeparation@@QEAAKPEBG00@Z; StateSeparation::SetString(ushort const *,ushort const *,ushort const *)
0x140032602  cmp     qword ptr [rdi+18h], 7
0x140032607  jbe     short loc_14003260C
0x140032609  mov     rdi, [rdi]
0x14003260c  mov     [rsp+80h+var_60], rdi
0x140032611  mov     r9d, eax
0x140032614  lea     r8, aRet0xXS; "ret 0x%x: %s"
0x14003261b  xor     edx, edx; struct _GUID *
0x14003261d  lea     rcx, aEsimpmEsimprof_0; "ESIMPM::EsimProfile::SetImsi"
0x140032624  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140032629  lea     rcx, [rbp+var_48]
0x14003262d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032632  jmp     short loc_140032656
0x140032634  cmp     qword ptr [rdi+18h], 7
0x140032639  jbe     short loc_14003263E
0x14003263b  mov     rdi, [rdi]
0x14003263e  mov     r9, rdi
0x140032641  lea     r8, aFailedToFindEs_0; "failed to find esim profile %s"
0x140032648  xor     edx, edx; struct _GUID *
0x14003264a  lea     rcx, aEsimpmLpahelpe_13; "ESIMPM::LpaHelper::SetIMSI"
0x140032651  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140032656  mov     rcx, [rbp+var_8]
0x14003265a  xor     rcx, rsp; StackCookie
0x14003265d  call    __security_check_cookie
0x140032662  mov     rbx, [rsp+80h+arg_0]
0x14003266a  add     rsp, 80h
0x140032671  pop     r15
0x140032673  pop     r14
0x140032675  pop     r13
0x140032677  pop     r12
0x140032679  pop     rdi
0x14003267a  pop     rsi
0x14003267b  pop     rbp
0x14003267c  retn
```
