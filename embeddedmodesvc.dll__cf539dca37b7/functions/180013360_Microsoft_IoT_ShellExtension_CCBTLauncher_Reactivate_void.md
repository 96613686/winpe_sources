# Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(void)

- ea: `0x180013360`
- end: `0x18001362d`
- name: `?Reactivate@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010bfc`

## callees

- `0x180008358`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a730`
- `0x18000d410`
- `0x18000fd84`
- `0x180010040`
- `0x1800114f0`
- `0x180011c34`
- `0x1800120c4`
- `0x180013360`
- `0x180014fd0`
- `0x180015000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133ec`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  __int64 v2; // rcx
  int AutoStartCBTs; // eax
  unsigned int v4; // r8d
  Microsoft::IoT::ShellExtension::CCBT *v5; // rcx
  __int64 i; // rbx
  Microsoft::IoT::ShellExtension::CCBT *v7; // rdi
  unsigned __int16 **v8; // r9
  __int64 *v9; // rax
  __int64 v10; // r8
  unsigned __int16 *v11; // rax
  __int64 v12; // r8
  int v13; // ecx
  int v14; // edx
  unsigned __int16 *v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  int v18; // edx
  Microsoft::IoT::ShellExtension::CCBT *v19; // rdx
  unsigned __int16 **v20; // r10
  __int64 *v21; // rax
  __int64 v22; // r9
  unsigned __int16 *v23; // rax
  __int64 v24; // r9
  int v25; // ecx
  int v26; // r8d
  unsigned __int16 *v27; // rax
  __int64 v28; // r9
  int v29; // ecx
  int v30; // r8d
  Microsoft::IoT::ShellExtension::CCBT *v31; // rbx
  Microsoft::IoT::ShellExtension::CCBT *v32; // rdi
  int v33; // eax
  Microsoft::IoT::ShellExtension::CCBT *v35; // [rsp+20h] [rbp-30h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v36; // [rsp+28h] [rbp-28h]
  __int64 v37; // [rsp+30h] [rbp-20h]
  Microsoft::IoT::ShellExtension::CCBT *v38; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v39; // [rsp+40h] [rbp-10h]
  __int64 v40; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  char *v42; // [rsp+78h] [rbp+28h] BYREF
  char v43; // [rsp+80h] [rbp+30h] BYREF

  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v35);
  AutoStartCBTs = Microsoft::IoT::ShellExtension::CCBTLauncher::GetAutoStartCBTs(v2, &v35);
  if ( AutoStartCBTs >= 0 )
  {
    if ( v35 == v36 )
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x2A7, v4, (const char *)0x800710D2LL, (int)v35);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v42 = (char *)this + 96;
    std::vector<Microsoft::IoT::ShellExtension::CCBT>::vector<Microsoft::IoT::ShellExtension::CCBT>(
      &v38,
      (char *)this + 136);
    std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear((char *)this + 136);
    for ( i = *((_QWORD *)this + 20); i != *((_QWORD *)this + 21); i += 88 )
    {
      v7 = v35;
      if ( v35 != v36 )
      {
        v8 = *(unsigned __int16 ***)(i + 16);
        do
        {
          v9 = (__int64 *)*((_QWORD *)v7 + 2);
          if ( v9 )
            v10 = *v9;
          else
            v10 = 0;
          if ( v8 )
            v11 = *v8;
          else
            v11 = 0;
          v12 = v10 - (_QWORD)v11;
          do
          {
            v13 = *(unsigned __int16 *)((char *)v11 + v12);
            v14 = *v11 - v13;
            if ( v14 )
              break;
            ++v11;
          }
          while ( v13 );
          if ( !v14 )
          {
            v15 = *(unsigned __int16 **)(i + 40);
            v16 = *((_QWORD *)v7 + 5) - (_QWORD)v15;
            do
            {
              v17 = *(unsigned __int16 *)((char *)v15 + v16);
              v18 = *v15 - v17;
              if ( v18 )
                break;
              ++v15;
            }
            while ( v17 );
            if ( !v18 )
              break;
          }
          v7 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v7 + 88);
        }
        while ( v7 != v36 );
      }
      *(_BYTE *)(i + 80) = 1;
      if ( v7 == v36 )
      {
        *(_BYTE *)(i + 79) = 1;
      }
      else
      {
        *(_BYTE *)(i + 79) = 0;
        if ( *(_DWORD *)(i + 56) )
        {
          v19 = v38;
          if ( v38 == v39 )
            goto LABEL_45;
          v20 = (unsigned __int16 **)*((_QWORD *)v7 + 2);
          do
          {
            v21 = (__int64 *)*((_QWORD *)v19 + 2);
            if ( v21 )
              v22 = *v21;
            else
              v22 = 0;
            if ( v20 )
              v23 = *v20;
            else
              v23 = 0;
            v24 = v22 - (_QWORD)v23;
            do
            {
              v25 = *(unsigned __int16 *)((char *)v23 + v24);
              v26 = *v23 - v25;
              if ( v26 )
                break;
              ++v23;
            }
            while ( v25 );
            if ( !v26 )
            {
              v27 = (unsigned __int16 *)*((_QWORD *)v7 + 5);
              v28 = *((_QWORD *)v19 + 5) - (_QWORD)v27;
              do
              {
                v29 = *(unsigned __int16 *)((char *)v27 + v28);
                v30 = *v27 - v29;
                if ( v30 )
                  break;
                ++v27;
              }
              while ( v29 );
              if ( !v30 )
                break;
            }
            v19 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v19 + 88);
          }
          while ( v19 != v39 );
          if ( v19 == v39 )
LABEL_45:
            v19 = v7;
          std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(
            (char *)this + 136,
            v19);
        }
        std::vector<Microsoft::IoT::ShellExtension::CCBT>::erase(&v35, &v43, v7);
      }
    }
    v31 = v35;
    v32 = v36;
    while ( v31 != v32 )
    {
      std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(
        (char *)this + 136,
        v31);
      v31 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v31 + 88);
    }
    v33 = Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(this);
    if ( v33 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v33,
        (int)v35);
    if ( v38 )
    {
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v38);
      std::_Deallocate<16>(v38, 8 * ((v40 - (__int64)v38) >> 3));
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v42);
    v5 = v35;
    if ( v35 )
      goto LABEL_58;
  }
  else
  {
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x29E, v4, (const char *)(unsigned int)AutoStartCBTs, (int)v35);
    v5 = v35;
    if ( v35 )
    {
LABEL_58:
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v5);
      std::_Deallocate<16>(v35, 8 * ((v37 - (__int64)v35) >> 3));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013360  mov     [rsp-18h+arg_0], rbx
0x180013365  mov     [rsp-18h+arg_18], rdi
0x18001336a  push    rbp
0x18001336b  push    r14
0x18001336d  push    r15
0x18001336f  mov     rbp, rsp
0x180013372  sub     rsp, 50h
0x180013376  mov     r14, rcx
0x180013379  lea     rcx, [rbp+var_30]
0x18001337d  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180013382  nop
0x180013383  lea     rdx, [rbp+var_30]
0x180013387  call    ?GetAutoStartCBTs@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::GetAutoStartCBTs(std::vector<Microsoft::IoT::ShellExtension::CCBT> &)
0x18001338c  test    eax, eax
0x18001338e  jns     short loc_1800133C7
0x180013390  mov     rcx, [rbp+18h]; this
0x180013394  mov     r9d, eax; char *
0x180013397  mov     edx, 29Eh; void *
0x18001339c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800133a1  nop
0x1800133a2  mov     rcx, [rbp+var_30]; this
0x1800133a6  test    rcx, rcx
0x1800133a9  jz      loc_180013615
0x1800133af  mov     rdx, [rbp+var_28]
0x1800133b3  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x1800133b8  mov     rbx, 2E8BA2E8BA2E8BA3h
0x1800133c2  jmp     loc_1800135F9
0x1800133c7  mov     rax, [rbp+var_28]
0x1800133cb  cmp     [rbp+var_30], rax
0x1800133cf  jnz     short loc_1800133E5
0x1800133d1  mov     rcx, [rbp+18h]; this
0x1800133d5  mov     edx, 2A7h; void *
0x1800133da  mov     r9d, 800710D2h; char *
0x1800133e0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800133e5  lea     rbx, [r14+60h]
0x1800133e9  mov     rcx, rbx; lpCriticalSection
0x1800133ec  call    cs:__imp_EnterCriticalSection
0x1800133f2  mov     [rbp+arg_8], rbx
0x1800133f6  lea     r15, [r14+88h]
0x1800133fd  mov     rdx, r15
0x180013400  lea     rcx, [rbp+var_18]
0x180013404  call    ??0?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::vector<Microsoft::IoT::ShellExtension::CCBT>(std::vector<Microsoft::IoT::ShellExtension::CCBT> &&)
0x180013409  nop
0x18001340a  mov     rcx, r15
0x18001340d  call    ?clear@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear(void)
0x180013412  mov     rbx, [r14+0A0h]
0x180013419  cmp     rbx, [r14+0A8h]
0x180013420  jz      loc_18001355E
0x180013426  mov     rdi, [rbp+var_30]
0x18001342a  cmp     rdi, [rbp+var_28]
0x18001342e  jz      short loc_180013499
0x180013430  mov     r9, [rbx+10h]
0x180013434  mov     rax, [rdi+10h]
0x180013438  test    rax, rax
0x18001343b  jz      short loc_180013442
0x18001343d  mov     r8, [rax]
0x180013440  jmp     short loc_180013445
0x180013442  xor     r8d, r8d
0x180013445  test    r9, r9
0x180013448  jz      short loc_18001344F
0x18001344a  mov     rax, [r9]
0x18001344d  jmp     short loc_180013451
0x18001344f  xor     eax, eax
0x180013451  sub     r8, rax
0x180013454  movzx   edx, word ptr [rax]
0x180013457  movzx   ecx, word ptr [rax+r8]
0x18001345c  sub     edx, ecx
0x18001345e  jnz     short loc_180013468
0x180013460  add     rax, 2
0x180013464  test    ecx, ecx
0x180013466  jnz     short loc_180013454
0x180013468  test    edx, edx
0x18001346a  jnz     short loc_18001348F
0x18001346c  mov     rax, [rbx+28h]
0x180013470  mov     r8, [rdi+28h]
0x180013474  sub     r8, rax
0x180013477  movzx   edx, word ptr [rax]
0x18001347a  movzx   ecx, word ptr [rax+r8]
0x18001347f  sub     edx, ecx
0x180013481  jnz     short loc_18001348B
0x180013483  add     rax, 2
0x180013487  test    ecx, ecx
0x180013489  jnz     short loc_180013477
0x18001348b  test    edx, edx
0x18001348d  jz      short loc_180013499
0x18001348f  add     rdi, 58h ; 'X'
0x180013493  cmp     rdi, [rbp+var_28]
0x180013497  jnz     short loc_180013434
0x180013499  mov     byte ptr [rbx+50h], 1
0x18001349d  cmp     rdi, [rbp+var_28]
0x1800134a1  jz      loc_180013551
0x1800134a7  mov     byte ptr [rbx+4Fh], 0
0x1800134ab  cmp     dword ptr [rbx+38h], 0
0x1800134af  jz      loc_18001353F
0x1800134b5  mov     rdx, [rbp+var_18]
0x1800134b9  cmp     rdx, [rbp+var_10]
0x1800134bd  jz      short loc_180013534
0x1800134bf  mov     r10, [rdi+10h]
0x1800134c3  mov     rax, [rdx+10h]
0x1800134c7  test    rax, rax
0x1800134ca  jz      short loc_1800134D1
0x1800134cc  mov     r9, [rax]
0x1800134cf  jmp     short loc_1800134D4
0x1800134d1  xor     r9d, r9d
0x1800134d4  test    r10, r10
0x1800134d7  jz      short loc_1800134DE
0x1800134d9  mov     rax, [r10]
0x1800134dc  jmp     short loc_1800134E0
0x1800134de  xor     eax, eax
0x1800134e0  sub     r9, rax
0x1800134e3  movzx   r8d, word ptr [rax]
0x1800134e7  movzx   ecx, word ptr [rax+r9]
0x1800134ec  sub     r8d, ecx
0x1800134ef  jnz     short loc_1800134F9
0x1800134f1  add     rax, 2
0x1800134f5  test    ecx, ecx
0x1800134f7  jnz     short loc_1800134E3
0x1800134f9  test    r8d, r8d
0x1800134fc  jnz     short loc_180013524
0x1800134fe  mov     rax, [rdi+28h]
0x180013502  mov     r9, [rdx+28h]
0x180013506  sub     r9, rax
0x180013509  movzx   r8d, word ptr [rax]
0x18001350d  movzx   ecx, word ptr [rax+r9]
0x180013512  sub     r8d, ecx
0x180013515  jnz     short loc_18001351F
0x180013517  add     rax, 2
0x18001351b  test    ecx, ecx
0x18001351d  jnz     short loc_180013509
0x18001351f  test    r8d, r8d
0x180013522  jz      short loc_18001352E
0x180013524  add     rdx, 58h ; 'X'
0x180013528  cmp     rdx, [rbp+var_10]
0x18001352c  jnz     short loc_1800134C3
0x18001352e  cmp     rdx, [rbp+var_10]
0x180013532  jnz     short loc_180013537
0x180013534  mov     rdx, rdi
0x180013537  mov     rcx, r15
0x18001353a  call    ??$emplace_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x18001353f  mov     r8, rdi
0x180013542  lea     rdx, [rbp+arg_10]
0x180013546  lea     rcx, [rbp+var_30]
0x18001354a  call    ?erase@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>)
0x18001354f  jmp     short loc_180013555
0x180013551  mov     byte ptr [rbx+4Fh], 1
0x180013555  add     rbx, 58h ; 'X'
0x180013559  jmp     loc_180013419
0x18001355e  mov     rbx, [rbp+var_30]
0x180013562  mov     rdi, [rbp+var_28]
0x180013566  jmp     short loc_180013577
0x180013568  mov     rdx, rbx
0x18001356b  mov     rcx, r15
0x18001356e  call    ??$emplace_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180013573  add     rbx, 58h ; 'X'
0x180013577  cmp     rbx, rdi
0x18001357a  jnz     short loc_180013568
0x18001357c  mov     rcx, r14; this
0x18001357f  call    ?DoLaunchCBT@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(void)
0x180013584  mov     rcx, [rbp+18h]; this
0x180013588  test    eax, eax
0x18001358a  jns     short loc_1800135A1
0x18001358c  mov     r9d, eax; char *
0x18001358f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180013596  mov     edx, 2E9h; void *
0x18001359b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800135a1  mov     rbx, 2E8BA2E8BA2E8BA3h
0x1800135ab  cmp     [rbp+var_18], 0
0x1800135b0  jz      short loc_1800135DD
0x1800135b2  mov     rdx, [rbp+var_10]
0x1800135b6  mov     rcx, [rbp+var_18]; this
0x1800135ba  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x1800135bf  mov     rax, [rbp+var_8]
0x1800135c3  sub     rax, [rbp+var_18]
0x1800135c7  sar     rax, 3
0x1800135cb  imul    rax, rbx
0x1800135cf  imul    rdx, rax, 58h ; 'X'
0x1800135d3  mov     rcx, [rbp+var_18]
0x1800135d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800135dc  nop
0x1800135dd  lea     rcx, [rbp+arg_8]
0x1800135e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800135e6  nop
0x1800135e7  mov     rcx, [rbp+var_30]; this
0x1800135eb  test    rcx, rcx
0x1800135ee  jz      short loc_180013615
0x1800135f0  mov     rdx, [rbp+var_28]
0x1800135f4  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x1800135f9  mov     rcx, [rbp+var_30]
0x1800135fd  mov     rax, [rbp+var_20]
0x180013601  sub     rax, rcx
0x180013604  sar     rax, 3
0x180013608  imul    rax, rbx
0x18001360c  imul    rdx, rax, 58h ; 'X'
0x180013610  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013615  xor     eax, eax
0x180013617  lea     r11, [rsp+50h+var_s0]
0x18001361c  mov     rbx, [r11+20h]
0x180013620  mov     rdi, [r11+38h]
0x180013624  mov     rsp, r11
0x180013627  pop     r15
0x180013629  pop     r14
0x18001362b  pop     rbp
0x18001362c  retn
```
