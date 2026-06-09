# ESIMPM::CoreFSM::UpdateCurrentIccid(void)

- ea: `0x14002a4b8`
- end: `0x14002a7bd`
- name: `?UpdateCurrentIccid@CoreFSM@ESIMPM@@AEAAHXZ`
- size: `773`
- prototype: `__int64 __fastcall(ESIMPM::CoreFSM *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140028160`
- `0x140028774`
- `0x140028e5c`
- `0x14002a188`
- `0x14002cb80`
- `0x14002cfb4`

## callees

- `0x1400011d8`
- `0x140002f60`
- `0x140003b1c`
- `0x14001a9b4`
- `0x140020620`
- `0x140022f0c`
- `0x14002a448`
- `0x14002a4b8`
- `0x140032434`

## import_xrefs

- `wwapi!WwanQueryInterface` at `0x14002a531`
- `wwapi!WwanQueryInterface` at `0x14002a531`
- `wwapi!WwanFreeMemory` at `0x14002a552`
- `wwapi!WwanFreeMemory` at `0x14002a671`
- `wwapi!WwanFreeMemory` at `0x14002a799`
- `wwapi!WwanFreeMemory` at `0x14002a552`
- `wwapi!WwanFreeMemory` at `0x14002a671`
- `wwapi!WwanFreeMemory` at `0x14002a799`

## string_xrefs

- `0x14002a6ab`: ` SIM ready for imsi %s, iccid %s`
- `0x14002a6b5`: `ESIMPM::CoreFSM::UpdateCurrentIccid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::CoreFSM::UpdateCurrentIccid(ESIMPM::CoreFSM *this)
{
  const struct _GUID *v2; // rdi
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  _WORD *v6; // r9
  const wchar_t **v7; // rdi
  unsigned __int64 v8; // rax
  wchar_t *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  const wchar_t **v12; // rbx
  const wchar_t *v13; // rdx
  size_t v14; // r8
  const wchar_t *v15; // rcx
  __int64 v16; // rcx
  __int64 *v18; // r8
  __int64 *v19; // r9
  __int64 v20; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  __int64 v25; // [rsp+48h] [rbp-51h] BYREF
  __int64 *v26; // [rsp+50h] [rbp-49h]
  __int64 v27; // [rsp+58h] [rbp-41h] BYREF
  char v28; // [rsp+60h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+70h] [rbp-29h] BYREF
  __int64 *v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h]
  __int64 *v32; // [rsp+A0h] [rbp+7h]
  int v33; // [rsp+A8h] [rbp+Fh]
  int v34; // [rsp+ACh] [rbp+13h]

  v24 = 0;
  v2 = (const struct _GUID *)((char *)this + 184);
  LODWORD(v25) = 0;
  v26 = &v24;
  v27 = 0;
  v28 = 1;
  v3 = WwanQueryInterface(
         *((_QWORD *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 1),
         (char *)this + 184,
         36,
         0,
         &v25,
         &v27,
         0,
         0);
  if ( v28 )
  {
    v4 = *v26;
    *v26 = v27;
    if ( v4 )
      WwanFreeMemory(v4);
  }
  ESIMPM::Log::Info("ESIMPM::WwanHelper::QuerySubscriberInfo", v2, L"query subscriberinfo, RetCode 0x%x", v3);
  if ( !v3 && *(_DWORD *)v24 == 1 && *(_WORD *)(v24 + 8) && (v6 = (_WORD *)(v24 + 40), *(_WORD *)(v24 + 40)) )
  {
    v7 = (const wchar_t **)((char *)this + 528);
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
    if ( v8 > *((_QWORD *)this + 69) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        (char *)this + 528,
        v8,
        v5,
        v6);
    }
    else
    {
      if ( *((_QWORD *)this + 69) <= 7u )
        v9 = (wchar_t *)((char *)this + 528);
      else
        v9 = (wchar_t *)*v7;
      *((_QWORD *)this + 68) = v8;
      v10 = v8;
      memmove_0(v9, v6, 2 * v8);
      v9[v10] = 0;
    }
    ESIMPM::CoreFSM::TruncateTailingF(v11, (char *)this + 528);
    v12 = (const wchar_t **)((char *)this + 560);
    if ( *((_QWORD *)this + 69) <= 7u )
      v13 = (const wchar_t *)((char *)this + 528);
    else
      v13 = *v7;
    v14 = *((_QWORD *)this + 72);
    if ( *((_QWORD *)this + 73) <= 7u )
      v15 = (const wchar_t *)((char *)this + 560);
    else
      v15 = *v12;
    if ( v14 == *((_QWORD *)this + 68) && (!v14 || !wmemcmp(v15, v13, v14)) )
    {
      *((_QWORD *)this + 72) = 0;
      if ( *((_QWORD *)this + 73) > 7u )
        v12 = (const wchar_t **)*v12;
      *(_WORD *)v12 = 0;
    }
    ESIMPM::LpaHelper::SetIMSI(
      (__int64)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128,
      (const wchar_t *)this + 264,
      (_WORD *)(v24 + 8));
    v16 = v24;
    v24 = 0;
    if ( v16 )
      WwanFreeMemory(v16);
    return 1;
  }
  else
  {
    v18 = &qword_14005F4F0;
    if ( *(_WORD *)(v24 + 40) )
      v18 = (__int64 *)(v24 + 40);
    v19 = &qword_14005F4F0;
    if ( *(_WORD *)(v24 + 8) )
      v19 = (__int64 *)(v24 + 8);
    ESIMPM::Log::Info("ESIMPM::CoreFSM::UpdateCurrentIccid", v2, L" SIM ready for imsi %s, iccid %s", v19, v18);
    v20 = v24;
    if ( *(_WORD *)(v24 + 8) && !*(_WORD *)(v24 + 40) )
    {
      if ( (unsigned int)dword_140075040 > 5
        && (qword_140075050 & 0x800000000000LL) != 0
        && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
      {
        v25 = 16779264;
        v21 = (__int64 *)(v24 + 8);
        if ( v24 == -8 )
        {
          v21 = &qword_14005F4F0;
          v23 = 2;
        }
        else
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_WORD *)v21 + v22) );
          v23 = 2 * v22 + 2;
        }
        v32 = v21;
        v33 = v23;
        v34 = 0;
        v30 = &v25;
        v31 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_140075040,
          (unsigned __int8 *)&word_14006AFCE,
          0,
          0,
          4u,
          &v29);
      }
      v20 = v24;
    }
    v24 = 0;
    if ( v20 )
      WwanFreeMemory(v20);
    return 0;
  }
}

```

## disassembly

```asm
0x14002a4b8  push    rbp
0x14002a4ba  push    rbx
0x14002a4bb  push    rsi
0x14002a4bc  push    rdi
0x14002a4bd  push    r14
0x14002a4bf  push    r15
0x14002a4c1  lea     rbp, [rsp-2Fh]
0x14002a4c6  sub     rsp, 0C8h
0x14002a4cd  mov     rax, cs:__security_cookie
0x14002a4d4  xor     rax, rsp
0x14002a4d7  mov     [rbp+57h+var_40], rax
0x14002a4db  mov     r14, rcx
0x14002a4de  xor     r15d, r15d
0x14002a4e1  mov     [rbp+57h+var_B0], r15
0x14002a4e5  lea     rdi, [rcx+0B8h]
0x14002a4ec  mov     dword ptr [rbp+57h+var_A8], r15d
0x14002a4f0  lea     rax, [rbp+57h+var_B0]
0x14002a4f4  mov     [rbp+57h+var_A0], rax
0x14002a4f8  mov     [rbp+57h+var_98], r15
0x14002a4fc  mov     [rbp+57h+var_90], 1
0x14002a500  mov     [rsp+0F0h+var_B8], r15
0x14002a505  mov     [rsp+0F0h+var_C0], r15
0x14002a50a  lea     rax, [rbp+57h+var_98]
0x14002a50e  mov     [rsp+0F0h+var_C8], rax
0x14002a513  lea     rax, [rbp+57h+var_A8]
0x14002a517  mov     [rsp+0F0h+var_D0], rax
0x14002a51c  xor     r9d, r9d
0x14002a51f  lea     r8d, [r15+24h]
0x14002a523  mov     rdx, rdi
0x14002a526  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x14002a52d  mov     rcx, [rcx+8]
0x14002a531  call    cs:__imp_WwanQueryInterface
0x14002a537  mov     ebx, eax
0x14002a539  cmp     [rbp+57h+var_90], r15b
0x14002a53d  jz      short loc_14002A558
0x14002a53f  mov     rdx, [rbp+57h+var_A0]
0x14002a543  mov     rcx, [rdx]
0x14002a546  mov     rax, [rbp+57h+var_98]
0x14002a54a  mov     [rdx], rax
0x14002a54d  test    rcx, rcx
0x14002a550  jz      short loc_14002A558
0x14002a552  call    cs:__imp_WwanFreeMemory
0x14002a558  mov     r9d, ebx
0x14002a55b  lea     r8, aQuerySubscribe; "query subscriberinfo, RetCode 0x%x"
0x14002a562  mov     rdx, rdi; struct _GUID *
0x14002a565  lea     rcx, aEsimpmWwanhelp_1; "ESIMPM::WwanHelper::QuerySubscriberInfo"
0x14002a56c  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002a571  mov     rax, [rbp+57h+var_B0]
0x14002a575  test    ebx, ebx
0x14002a577  jnz     loc_14002A681
0x14002a57d  cmp     dword ptr [rax], 1
0x14002a580  jnz     loc_14002A681
0x14002a586  cmp     [rax+8], r15w
0x14002a58b  jz      loc_14002A681
0x14002a591  lea     r9, [rax+28h]
0x14002a595  cmp     [r9], r15w
0x14002a599  jz      loc_14002A681
0x14002a59f  lea     rdi, [r14+210h]
0x14002a5a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002a5aa  inc     rax
0x14002a5ad  cmp     [r9+rax*2], r15w
0x14002a5b2  jnz     short loc_14002A5AA
0x14002a5b4  cmp     rax, [rdi+18h]
0x14002a5b8  ja      short loc_14002A5E6
0x14002a5ba  cmp     qword ptr [rdi+18h], 7
0x14002a5bf  jbe     short loc_14002A5C6
0x14002a5c1  mov     rsi, [rdi]
0x14002a5c4  jmp     short loc_14002A5C9
0x14002a5c6  mov     rsi, rdi
0x14002a5c9  mov     [rdi+10h], rax
0x14002a5cd  lea     rbx, [rax+rax]
0x14002a5d1  mov     r8, rbx; Size
0x14002a5d4  mov     rdx, r9; Src
0x14002a5d7  mov     rcx, rsi; void *
0x14002a5da  call    memmove_0
0x14002a5df  mov     [rbx+rsi], r15w
0x14002a5e4  jmp     short loc_14002A5F1
0x14002a5e6  mov     rdx, rax
0x14002a5e9  mov     rcx, rdi
0x14002a5ec  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14002a5f1  mov     rdx, rdi
0x14002a5f4  call    ?TruncateTailingF@CoreFSM@ESIMPM@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ESIMPM::CoreFSM::TruncateTailingF(std::wstring &)
0x14002a5f9  lea     rbx, [r14+230h]
0x14002a600  cmp     qword ptr [rdi+18h], 7
0x14002a605  jbe     short loc_14002A60C
0x14002a607  mov     rdx, [rdi]
0x14002a60a  jmp     short loc_14002A60F
0x14002a60c  mov     rdx, rdi; S2
0x14002a60f  mov     r8, [rbx+10h]; N
0x14002a613  cmp     qword ptr [rbx+18h], 7
0x14002a618  jbe     short loc_14002A61F
0x14002a61a  mov     rcx, [rbx]
0x14002a61d  jmp     short loc_14002A622
0x14002a61f  mov     rcx, rbx; S1
0x14002a622  cmp     r8, [rdi+10h]
0x14002a626  jnz     short loc_14002A648
0x14002a628  test    r8, r8
0x14002a62b  jz      short loc_14002A636
0x14002a62d  call    wmemcmp
0x14002a632  test    eax, eax
0x14002a634  jnz     short loc_14002A648
0x14002a636  mov     [rbx+10h], r15
0x14002a63a  cmp     qword ptr [rbx+18h], 7
0x14002a63f  jbe     short loc_14002A644
0x14002a641  mov     rbx, [rbx]
0x14002a644  mov     [rbx], r15w
0x14002a648  mov     r8, [rbp+57h+var_B0]
0x14002a64c  add     r8, 8
0x14002a650  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x14002a657  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14002a65b  mov     rdx, rdi
0x14002a65e  call    ?SetIMSI@LpaHelper@ESIMPM@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; ESIMPM::LpaHelper::SetIMSI(std::wstring const &,ushort const * const)
0x14002a663  nop
0x14002a664  mov     rcx, [rbp+57h+var_B0]
0x14002a668  mov     [rbp+57h+var_B0], r15
0x14002a66c  test    rcx, rcx
0x14002a66f  jz      short loc_14002A677
0x14002a671  call    cs:__imp_WwanFreeMemory
0x14002a677  mov     eax, 1
0x14002a67c  jmp     loc_14002A7A1
0x14002a681  lea     rcx, [rax+28h]
0x14002a685  lea     rbx, qword_14005F4F0
0x14002a68c  mov     r8, rbx
0x14002a68f  cmp     [rcx], r15w
0x14002a693  cmovnz  r8, rcx
0x14002a697  add     rax, 8
0x14002a69b  mov     r9, rbx
0x14002a69e  cmp     [rax], r15w
0x14002a6a2  cmovnz  r9, rax
0x14002a6a6  mov     [rsp+0F0h+var_D0], r8
0x14002a6ab  lea     r8, aSimReadyForIms; " SIM ready for imsi %s, iccid %s"
0x14002a6b2  mov     rdx, rdi; struct _GUID *
0x14002a6b5  lea     rcx, aEsimpmCorefsmU; "ESIMPM::CoreFSM::UpdateCurrentIccid"
0x14002a6bc  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002a6c1  mov     rcx, [rbp+57h+var_B0]
0x14002a6c5  cmp     [rcx+8], r15w
0x14002a6ca  jz      loc_14002A790
0x14002a6d0  cmp     [rcx+28h], r15w
0x14002a6d5  jnz     loc_14002A790
0x14002a6db  mov     eax, cs:dword_140075040
0x14002a6e1  cmp     eax, 5
0x14002a6e4  jbe     loc_14002A78C
0x14002a6ea  mov     rcx, cs:qword_140075058
0x14002a6f1  mov     rax, cs:qword_140075050
0x14002a6f8  mov     rdx, 800000000000h
0x14002a702  test    rdx, rax
0x14002a705  jz      loc_14002A78C
0x14002a70b  mov     rax, rcx
0x14002a70e  and     rax, rdx
0x14002a711  cmp     rax, rcx
0x14002a714  jnz     short loc_14002A78C
0x14002a716  mov     rcx, [rbp+57h+var_B0]
0x14002a71a  mov     [rbp+57h+var_A8], 1000800h
0x14002a722  add     rcx, 8
0x14002a726  jz      short loc_14002A73F
0x14002a728  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002a72c  inc     rax
0x14002a72f  cmp     [rcx+rax*2], r15w
0x14002a734  jnz     short loc_14002A72C
0x14002a736  lea     eax, ds:2[rax*2]
0x14002a73d  jmp     short loc_14002A747
0x14002a73f  mov     rcx, rbx
0x14002a742  mov     eax, 2
0x14002a747  mov     [rbp+57h+var_50], rcx
0x14002a74b  mov     [rbp+57h+var_48], eax
0x14002a74e  mov     [rbp+57h+var_44], r15d
0x14002a752  lea     rax, [rbp+57h+var_A8]
0x14002a756  mov     [rbp+57h+var_60], rax
0x14002a75a  mov     [rbp+57h+var_58], 8
0x14002a762  lea     rax, [rbp+57h+var_80]
0x14002a766  mov     [rsp+0F0h+var_C8], rax
0x14002a76b  mov     dword ptr [rsp+0F0h+var_D0], 4
0x14002a773  xor     r9d, r9d
0x14002a776  xor     r8d, r8d
0x14002a779  lea     rdx, word_14006AFCE
0x14002a780  lea     rcx, dword_140075040
0x14002a787  call    _tlgWriteTransfer_EventWriteTransfer
0x14002a78c  mov     rcx, [rbp+57h+var_B0]
0x14002a790  mov     [rbp+57h+var_B0], r15
0x14002a794  test    rcx, rcx
0x14002a797  jz      short loc_14002A79F
0x14002a799  call    cs:__imp_WwanFreeMemory
0x14002a79f  xor     eax, eax
0x14002a7a1  mov     rcx, [rbp+57h+var_40]
0x14002a7a5  xor     rcx, rsp; StackCookie
0x14002a7a8  call    __security_check_cookie
0x14002a7ad  add     rsp, 0C8h
0x14002a7b4  pop     r15
0x14002a7b6  pop     r14
0x14002a7b8  pop     rdi
0x14002a7b9  pop     rsi
0x14002a7ba  pop     rbx
0x14002a7bb  pop     rbp
0x14002a7bc  retn
```
