# ESIMPM::CoreFSM::FindNextProfileToEnable(ESIMPM::CoreFSM::_CoreFSMEvent,bool,bool)

- ea: `0x140027e3c`
- end: `0x140028157`
- name: `?FindNextProfileToEnable@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N1@Z`
- size: `795`
- prototype: `__int64 __fastcall(__int64, unsigned int, char, char)`
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x140028620`
- `0x14002b32c`
- `0x14002b8c0`
- `0x14002bf60`
- `0x14002c0a0`
- `0x14002cb80`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140020620`
- `0x140022f0c`
- `0x1400240fc`
- `0x140027e3c`
- `0x14002d7c8`
- `0x14002fda4`
- `0x14003039c`
- `0x1400309bc`
- `0x140030ee0`

## string_xrefs

- `0x140028082`: `esim profile we want to enable is already enabled and in use (%s)`

## pseudocode

```c
__int64 __fastcall ESIMPM::CoreFSM::FindNextProfileToEnable(__int64 a1, unsigned int a2, char a3, char a4)
{
  _DWORD *v6; // rdi
  unsigned __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r15d
  __int64 v10; // rsi
  char *v11; // rcx
  char ProfileIccIdForPlmnId; // al
  const wchar_t *v13; // rax
  wchar_t *v14; // rcx
  unsigned __int64 v15; // rdx
  const wchar_t *v16; // r9
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  _QWORD *v20; // r9
  __int64 v21; // rdx
  wchar_t **v22; // r9
  __int64 v23; // rdx
  wchar_t **v25; // r9
  wchar_t *S2[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v27; // [rsp+30h] [rbp-40h]
  unsigned __int64 v28; // [rsp+38h] [rbp-38h]
  wchar_t *S1[2]; // [rsp+40h] [rbp-30h] BYREF
  size_t N; // [rsp+50h] [rbp-20h]
  unsigned __int64 v31; // [rsp+58h] [rbp-18h]

  v6 = (_DWORD *)(a1 + 328);
  if ( a3 )
  {
    LODWORD(v7) = 0;
  }
  else
  {
    LODWORD(v7) = *v6;
    if ( !a4 )
      LODWORD(v7) = v7 + 1;
  }
  *v6 = v7;
  v8 = *(_QWORD *)(a1 + 320);
  if ( (unsigned int)v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v8 + 32) - *(_QWORD *)(v8 + 24)) >> 3) )
    goto LABEL_24;
  v9 = *(_DWORD *)(v8 + 16);
  while ( 1 )
  {
    *(_OWORD *)S2 = 0;
    v27 = 0;
    v28 = 7;
    LOWORD(S2[0]) = 0;
    v10 = *(_QWORD *)(v8 + 24) + 40LL * (unsigned int)v7;
    v11 = (char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128;
    if ( v9 == 2 )
      ProfileIccIdForPlmnId = ESIMPM::LpaHelper::GetProfileIccIdForPlmnId(v11, v10, S2);
    else
      ProfileIccIdForPlmnId = ESIMPM::LpaHelper::IsProfilePresentAndPermissible(v11, v10, a1 + 312, S2);
    if ( !ProfileIccIdForPlmnId )
      goto LABEL_23;
    *(_OWORD *)S1 = 0;
    N = 0;
    v31 = 7;
    LOWORD(S1[0]) = 0;
    if ( !(unsigned __int8)ESIMPM::LpaHelper::HasActiveProfile((char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128, S1) )
      goto LABEL_19;
    v13 = (const wchar_t *)S2;
    v14 = S2[0];
    v15 = v28;
    if ( v28 > 7 )
      v13 = S2[0];
    v16 = (const wchar_t *)S1;
    if ( v31 > 7 )
      v16 = S1[0];
    if ( N == v27 )
    {
      if ( !N )
        goto LABEL_29;
      if ( !wmemcmp(v16, v13, N) )
      {
        v15 = v28;
        v14 = S2[0];
LABEL_29:
        v22 = S2;
        if ( v15 > 7 )
          v22 = (wchar_t **)v14;
        ESIMPM::Log::Info(
          "ESIMPM::CoreFSM::FindNextProfileToEnable",
          (const struct _GUID *)(a1 + 184),
          L"esim profile we want to enable is already enabled and in use (%s)",
          v22,
          S2[0],
          S2[1]);
        v23 = 5;
LABEL_32:
        ESIMPM::CoreFSM::fsmStateTransition(a1, v23, a2);
        std::wstring::_Tidy_deallocate(S1);
        return std::wstring::_Tidy_deallocate(S2);
      }
LABEL_19:
      v15 = v28;
      v14 = S2[0];
    }
    if ( *((_QWORD *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 31) )
    {
      v25 = S2;
      if ( v15 > 7 )
        v25 = (wchar_t **)v14;
      ESIMPM::Log::Info(
        "ESIMPM::CoreFSM::FindNextProfileToEnable",
        (const struct _GUID *)(a1 + 184),
        L"waiting for pending activating profile activated before enable the new profile (%s)",
        v25,
        S2[0],
        S2[1]);
      v23 = 2;
      goto LABEL_32;
    }
    if ( !(unsigned int)ESIMPM::LpaHelper::EnableProfile((__int64)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128, (__int64 *)S2) )
      break;
    std::wstring::_Tidy_deallocate(S1);
LABEL_23:
    ++*v6;
    std::wstring::_Tidy_deallocate(S2);
    v8 = *(_QWORD *)(a1 + 320);
    v7 = (unsigned int)*v6;
    if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v8 + 32) - *(_QWORD *)(v8 + 24)) >> 3) )
      goto LABEL_24;
  }
  std::wstring::operator=(a1 + 376, v10);
  std::wstring::operator=(a1 + 560, S2);
  std::wstring::_Tidy_deallocate(S1);
  std::wstring::_Tidy_deallocate(S2);
LABEL_24:
  v17 = *(_QWORD *)(a1 + 320);
  v18 = *(_QWORD *)(v17 + 24);
  v19 = (unsigned int)*v6;
  if ( v19 >= 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(v17 + 32) - v18) >> 3) )
  {
    v21 = 8;
  }
  else
  {
    v20 = (_QWORD *)(v18 + 40 * v19);
    if ( v20[3] > 7u )
      v20 = (_QWORD *)*v20;
    ESIMPM::Log::Info(
      "ESIMPM::CoreFSM::FindNextProfileToEnable",
      (const struct _GUID *)(a1 + 184),
      L"Enabling eSIM profile (%s)",
      v20,
      S2[0],
      S2[1]);
    v21 = 3;
  }
  return ESIMPM::CoreFSM::fsmStateTransition(a1, v21, a2);
}

```

## disassembly

```asm
0x140027e3c  mov     [rsp-28h+arg_10], rbx
0x140027e41  mov     [rsp-28h+arg_18], rsi
0x140027e46  push    rbp
0x140027e47  push    rdi
0x140027e48  push    r13
0x140027e4a  push    r14
0x140027e4c  push    r15
0x140027e4e  mov     rbp, rsp
0x140027e51  sub     rsp, 70h
0x140027e55  mov     rax, cs:__security_cookie
0x140027e5c  xor     rax, rsp
0x140027e5f  mov     [rbp+var_10], rax
0x140027e63  mov     r14d, edx
0x140027e66  mov     rbx, rcx
0x140027e69  lea     rdi, [rcx+148h]
0x140027e70  test    r8b, r8b
0x140027e73  jz      short loc_140027E79
0x140027e75  xor     edx, edx
0x140027e77  jmp     short loc_140027E82
0x140027e79  mov     edx, [rdi]
0x140027e7b  test    r9b, r9b
0x140027e7e  jnz     short loc_140027E82
0x140027e80  inc     edx
0x140027e82  mov     [rdi], edx
0x140027e84  mov     r8, [rcx+140h]
0x140027e8b  mov     rcx, [r8+20h]
0x140027e8f  sub     rcx, [r8+18h]
0x140027e93  sar     rcx, 3
0x140027e97  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140027ea1  imul    rcx, rax
0x140027ea5  mov     eax, edx
0x140027ea7  mov     r13d, 7
0x140027ead  cmp     rax, rcx
0x140027eb0  jnb     loc_140028004
0x140027eb6  mov     r15d, [r8+10h]
0x140027eba  xorps   xmm0, xmm0
0x140027ebd  movups  xmmword ptr [rbp+S2], xmm0
0x140027ec1  mov     [rbp+var_40], 0
0x140027ec9  mov     [rbp+var_38], r13
0x140027ecd  xor     eax, eax
0x140027ecf  mov     word ptr [rbp+S2], ax
0x140027ed3  mov     eax, edx
0x140027ed5  lea     rcx, [rax+rax*4]
0x140027ed9  mov     rax, [r8+18h]
0x140027edd  lea     rsi, [rax+rcx*8]
0x140027ee1  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140027ee8  mov     rdx, rsi
0x140027eeb  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140027eef  cmp     r15d, 2
0x140027ef3  jnz     short loc_140027F00
0x140027ef5  lea     r8, [rbp+S2]
0x140027ef9  call    ?GetProfileIccIdForPlmnId@LpaHelper@ESIMPM@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; ESIMPM::LpaHelper::GetProfileIccIdForPlmnId(std::wstring const &,std::wstring &)
0x140027efe  jmp     short loc_140027F10
0x140027f00  lea     r8, [rbx+138h]
0x140027f07  lea     r9, [rbp+S2]
0x140027f0b  call    ?IsProfilePresentAndPermissible@LpaHelper@ESIMPM@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_ptr@V?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$default_delete@V?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@4@AEAV34@@Z; ESIMPM::LpaHelper::IsProfilePresentAndPermissible(std::wstring const &,std::unique_ptr<std::list<std::wstring>> const &,std::wstring &)
0x140027f10  test    al, al
0x140027f12  jz      loc_140027FCD
0x140027f18  xorps   xmm0, xmm0
0x140027f1b  movups  xmmword ptr [rbp+S1], xmm0
0x140027f1f  mov     [rbp+N], 0
0x140027f27  mov     [rbp+var_18], r13
0x140027f2b  xor     eax, eax
0x140027f2d  mov     word ptr [rbp+S1], ax
0x140027f31  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140027f38  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140027f3c  lea     rdx, [rbp+S1]
0x140027f40  call    ?HasActiveProfile@LpaHelper@ESIMPM@@QEAA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ESIMPM::LpaHelper::HasActiveProfile(std::wstring &)
0x140027f45  test    al, al
0x140027f47  jz      short loc_140027F8F
0x140027f49  lea     rax, [rbp+S2]
0x140027f4d  mov     rcx, [rbp+S2]
0x140027f51  mov     rdx, [rbp+var_38]
0x140027f55  cmp     rdx, r13
0x140027f58  cmova   rax, rcx
0x140027f5c  mov     r8, [rbp+N]; N
0x140027f60  lea     r9, [rbp+S1]
0x140027f64  cmp     [rbp+var_18], r13
0x140027f68  cmova   r9, [rbp+S1]
0x140027f6d  cmp     r8, [rbp+var_40]
0x140027f71  jnz     short loc_140027F97
0x140027f73  test    r8, r8
0x140027f76  jz      loc_140028070
0x140027f7c  mov     rdx, rax; S2
0x140027f7f  mov     rcx, r9; S1
0x140027f82  call    wmemcmp
0x140027f87  test    eax, eax
0x140027f89  jz      loc_140028068
0x140027f8f  mov     rdx, [rbp+var_38]
0x140027f93  mov     rcx, [rbp+S2]
0x140027f97  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140027f9e  cmp     qword ptr [rax+0F8h], 0
0x140027fa6  jnz     loc_1400280F3
0x140027fac  lea     rdx, [rbp+S2]
0x140027fb0  lea     rcx, [rax+80h]
0x140027fb7  call    ?EnableProfile@LpaHelper@ESIMPM@@QEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ESIMPM::LpaHelper::EnableProfile(std::wstring const &)
0x140027fbc  test    eax, eax
0x140027fbe  jz      loc_1400280BB
0x140027fc4  lea     rcx, [rbp+S1]
0x140027fc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140027fcd  inc     dword ptr [rdi]
0x140027fcf  lea     rcx, [rbp+S2]
0x140027fd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140027fd8  mov     r8, [rbx+140h]
0x140027fdf  mov     edx, [rdi]
0x140027fe1  mov     rax, [r8+20h]
0x140027fe5  sub     rax, [r8+18h]
0x140027fe9  sar     rax, 3
0x140027fed  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x140027ff7  imul    rax, rcx
0x140027ffb  cmp     rdx, rax
0x140027ffe  jb      loc_140027EBA
0x140028004  mov     rax, [rbx+140h]
0x14002800b  mov     r8, [rax+18h]
0x14002800f  mov     edx, [rdi]
0x140028011  mov     rcx, [rax+20h]
0x140028015  sub     rcx, r8
0x140028018  sar     rcx, 3
0x14002801c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140028026  imul    rcx, rax
0x14002802a  cmp     rdx, rcx
0x14002802d  jnb     loc_140028122
0x140028033  lea     rax, [rdx+rdx*4]
0x140028037  lea     r9, [r8+rax*8]
0x14002803b  cmp     [r9+18h], r13
0x14002803f  jbe     short loc_140028044
0x140028041  mov     r9, [r9]
0x140028044  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002804b  lea     r8, aEnablingEsimPr; "Enabling eSIM profile (%s)"
0x140028052  lea     rcx, aEsimpmCorefsmF_7; "ESIMPM::CoreFSM::FindNextProfileToEnabl"...
0x140028059  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002805e  mov     edx, 3
0x140028063  jmp     loc_140028127
0x140028068  mov     rdx, [rbp+var_38]
0x14002806c  mov     rcx, [rbp+S2]
0x140028070  lea     r9, [rbp+S2]
0x140028074  cmp     rdx, r13
0x140028077  cmova   r9, rcx
0x14002807b  lea     rdx, [rbx+0B8h]; struct _GUID *
0x140028082  lea     r8, aEsimProfileWeW_0; "esim profile we want to enable is alrea"...
0x140028089  lea     rcx, aEsimpmCorefsmF_7; "ESIMPM::CoreFSM::FindNextProfileToEnabl"...
0x140028090  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140028095  mov     edx, 5
0x14002809a  mov     r8d, r14d
0x14002809d  mov     rcx, rbx
0x1400280a0  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x1400280a5  nop
0x1400280a6  lea     rcx, [rbp+S1]
0x1400280aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400280af  nop
0x1400280b0  lea     rcx, [rbp+S2]
0x1400280b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400280b9  jmp     short loc_140028132
0x1400280bb  lea     rcx, [rbx+178h]
0x1400280c2  mov     rdx, rsi
0x1400280c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400280ca  lea     rcx, [rbx+230h]
0x1400280d1  lea     rdx, [rbp+S2]
0x1400280d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400280da  nop
0x1400280db  lea     rcx, [rbp+S1]
0x1400280df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400280e4  nop
0x1400280e5  lea     rcx, [rbp+S2]
0x1400280e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400280ee  jmp     loc_140028004
0x1400280f3  lea     r9, [rbp+S2]
0x1400280f7  cmp     rdx, r13
0x1400280fa  cmova   r9, rcx
0x1400280fe  lea     rdx, [rbx+0B8h]; struct _GUID *
0x140028105  lea     r8, aWaitingForPend; "waiting for pending activating profile "...
0x14002810c  lea     rcx, aEsimpmCorefsmF_7; "ESIMPM::CoreFSM::FindNextProfileToEnabl"...
0x140028113  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140028118  mov     edx, 2
0x14002811d  jmp     loc_14002809A
0x140028122  mov     edx, 8
0x140028127  mov     r8d, r14d
0x14002812a  mov     rcx, rbx
0x14002812d  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x140028132  mov     rcx, [rbp+var_10]
0x140028136  xor     rcx, rsp; StackCookie
0x140028139  call    __security_check_cookie
0x14002813e  lea     r11, [rsp+70h+var_s0]
0x140028143  mov     rbx, [r11+40h]
0x140028147  mov     rsi, [r11+48h]
0x14002814b  mov     rsp, r11
0x14002814e  pop     r15
0x140028150  pop     r14
0x140028152  pop     r13
0x140028154  pop     rdi
0x140028155  pop     rbp
0x140028156  retn
```
