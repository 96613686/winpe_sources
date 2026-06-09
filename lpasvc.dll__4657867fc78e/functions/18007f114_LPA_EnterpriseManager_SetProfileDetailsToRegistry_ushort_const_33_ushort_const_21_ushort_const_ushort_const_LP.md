# LPA::EnterpriseManager::SetProfileDetailsToRegistry(ushort const (&)[33],ushort const (&)[21],ushort const *,ushort const *,LPAENTERPRISEPROFILESTATE,LPAERROR)

- ea: `0x18007f114`
- end: `0x18007f603`
- name: `?SetProfileDetailsToRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2W4LPAENTERPRISEPROFILESTATE@@W4LPAERROR@@@Z`
- size: `1263`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180077a40`
- `0x180079fc0`
- `0x18007d420`

## callees

- `0x180002e1c`
- `0x18000df90`
- `0x18000ebf4`
- `0x180063668`
- `0x1800653e8`
- `0x1800704b8`
- `0x180071344`
- `0x180071650`
- `0x1800741d0`
- `0x180074204`
- `0x180075554`
- `0x180075618`
- `0x1800759d4`
- `0x1800769bc`
- `0x1800769fc`
- `0x1800774b0`
- `0x180077628`
- `0x180077854`
- `0x1800778c8`
- `0x18007ed6c`
- `0x18007f114`
- `0x18007fdd8`
- `0x180080a28`
- `0x180081010`
- `0x180101010`

## string_xrefs

- `0x18007f4c8`: `LpaServiceEnterpriseManager`
- `0x18007f566`: `LpaServiceEnterpriseManager`
- `0x18007f4bd`: `LPA::EnterpriseManager::SetProfileDetailsToRegistry`
- `0x18007f55b`: `LPA::EnterpriseManager::SetProfileDetailsToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LPA::EnterpriseManager::SetProfileDetailsToRegistry(
        LPA::EnterpriseManager *a1,
        CommonUtil *a2,
        CommonUtil *a3,
        const BYTE *a4,
        struct _SECURITY_ATTRIBUTES *a5,
        unsigned int a6,
        unsigned int a7)
{
  const BYTE *v7; // r15
  const WCHAR *v11; // rax
  const unsigned __int16 *v12; // r8
  int v13; // edi
  const WCHAR *v14; // rax
  const unsigned __int16 *v15; // r8
  const WCHAR *v16; // rax
  unsigned int v17; // ebx
  const unsigned __int16 *v18; // r8
  const WCHAR *v19; // rax
  const unsigned __int16 *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  unsigned __int16 (*v29)[33]; // r8
  unsigned __int16 (*v30)[21]; // r8
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  const char **v34; // rax
  char *v35; // rdx
  const char **v37; // [rsp+28h] [rbp-D8h]
  void **v38; // [rsp+30h] [rbp-D0h]
  unsigned __int16 **v39; // [rsp+38h] [rbp-C8h]
  unsigned __int16 **v40; // [rsp+40h] [rbp-C0h]
  const char **v41; // [rsp+48h] [rbp-B8h]
  const char **v42; // [rsp+50h] [rbp-B0h]
  void **v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  void *v45; // [rsp+78h] [rbp-88h] BYREF
  const BYTE *v46; // [rsp+80h] [rbp-80h] BYREF
  const char *v47; // [rsp+88h] [rbp-78h] BYREF
  const char *v48; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v49; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v50; // [rsp+A0h] [rbp-60h] BYREF
  const char *v51; // [rsp+A8h] [rbp-58h] BYREF
  const char *v52; // [rsp+B0h] [rbp-50h] BYREF
  struct LPA_ENTERPRISE_ESIM_DETAILS *v53; // [rsp+B8h] [rbp-48h]
  _BYTE v54[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v55[8]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  _BYTE v57[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v58[21]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v59[33]; // [rsp+160h] [rbp+60h] BYREF

  v7 = a4;
  v46 = a4;
  *(_OWORD *)v55 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v55[0] = 0;
  LPA::EnterpriseManager::AssembleProfileRegKey((_DWORD)a1, (_DWORD)a2, (_DWORD)a3, 0, (__int64)v55);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
  v13 = CommonUtil::SetStringToRegistry(v11, L"ServerName", v12, v7);
  if ( v13 < 0 )
    goto LABEL_14;
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
  v13 = CommonUtil::SetStringToRegistry(v14, L"MatchingId", v15, (const BYTE *)a5);
  if ( v13 < 0 )
    goto LABEL_14;
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
  v17 = a6;
  v13 = CommonUtil::SetDwordToRegistry(v16, L"State", v18, (struct _SECURITY_ATTRIBUTES *)a6, 0);
  if ( v13 < 0 )
    goto LABEL_15;
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
  v13 = CommonUtil::SetDwordToRegistry(v19, L"ErrorDetail", v20, (struct _SECURITY_ATTRIBUTES *)a7, 0);
  if ( v13 < 0 )
  {
LABEL_14:
    v17 = a6;
  }
  else
  {
    v45 = 0;
    v17 = a6;
    v13 = LPA::EnterpriseManager::AssembleEnterpriseProfileDetails(v21, a2, a3, v7, a5, a6, a7, &v45);
    if ( v13 >= 0 )
    {
      std::wstring::wstring(&v52, a2);
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
        (char *)a1 + 88,
        &v44,
        &v52);
      std::wstring::_Tidy_deallocate(&v52);
      if ( *((_QWORD *)a1 + 11) == v44 )
      {
        std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(&v44);
        v22 = v44;
        std::wstring::wstring(v54, a3);
        v23 = std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(
                v22 + 16,
                &v52,
                v54);
        std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(
          (void **)(*(_QWORD *)v23 + 64LL),
          &v45);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::wstring(v54, a2);
        v24 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(
                (char *)a1 + 88,
                &v52,
                v54);
        std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(
          (__int64 *)(*(_QWORD *)v24 + 64LL),
          &v44);
        std::wstring::_Tidy_deallocate(v54);
        std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(&v44);
      }
      else
      {
        v25 = *(_QWORD *)(v44 + 64);
        std::wstring::wstring(v54, a3);
        v26 = std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(
                v25 + 16,
                &v52,
                v54);
        std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(
          (void **)(*(_QWORD *)v26 + 64LL),
          &v45);
        std::wstring::_Tidy_deallocate(v54);
      }
      std::wstring::wstring(v57, a2);
      v27 = *(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(
                                     (char *)a1 + 88,
                                     &v52,
                                     v57)
                      + 64LL);
      std::wstring::wstring(v54, a3);
      v28 = std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(
              v27 + 16,
              &v52,
              v54);
      LPA::EnterpriseManager::BroadcastProfileUpdates(
        a1,
        *(const struct LPA_ENTERPRISE_PROFILE_DETAILS **)(*(_QWORD *)v28 + 64LL));
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v57);
      v17 = a6;
      v7 = v46;
    }
    std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::~unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>(&v45);
    if ( v13 >= 0 )
    {
      v52 = (const char *)LPA::Util::CustomDeleter;
      v53 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD *, CommonUtil *, const char **))(*((_QWORD *)a1 + 1) + 64LL))(
              (_QWORD *)a1 + 1,
              a2,
              &v52);
      if ( v13 >= 0 )
        LPA::EnterpriseManager::BroadcastEsimUpdates(a1, v53);
      std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(&v52);
    }
  }
LABEL_15:
  v59[0] = 0;
  memset_0(&v59[1], 0, 0x40u);
  memset(v58, 0, sizeof(v58));
  CommonUtil::WritePiiFilteredEsimIdToBuffer(a2, (const unsigned __int16 (*)[33])v59, v29);
  CommonUtil::WritePiiFilteredProfileIdToBuffer(a3, (const unsigned __int16 (*)[21])v58, v30);
  if ( v13 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v45) = a7;
      v52 = (const char *)a5;
      v51 = (const char *)v7;
      v50 = v58;
      v49 = v59;
      LODWORD(v46) = v13;
      v48 = "LPA::EnterpriseManager::SetProfileDetailsToRegistry";
      v47 = "LpaServiceEnterpriseManager";
      v43 = &v45;
      v42 = &v52;
      v41 = &v51;
      v40 = &v50;
      v39 = &v49;
      v38 = (void **)&v46;
      v37 = &v48;
      v34 = &v47;
      v35 = byte_18012B589;
      goto LABEL_20;
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v46) = a7;
    v47 = (const char *)a5;
    v48 = (const char *)v7;
    v49 = v58;
    v50 = v59;
    LODWORD(v45) = v13;
    v51 = "LPA::EnterpriseManager::SetProfileDetailsToRegistry";
    v52 = "LpaServiceEnterpriseManager";
    v43 = (void **)&v46;
    v42 = &v47;
    v41 = &v48;
    v40 = &v49;
    v39 = &v50;
    v38 = &v45;
    v37 = &v51;
    v34 = &v52;
    v35 = byte_18012B603;
LABEL_20:
    LODWORD(v44) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v31,
      (_DWORD)v35,
      v32,
      v33,
      (__int64)v34,
      (__int64)v37,
      (__int64)v38,
      (__int64)v39,
      (__int64)v40,
      (__int64)v41,
      (__int64)v42,
      (__int64)&v44,
      (__int64)v43);
  }
  std::wstring::_Tidy_deallocate(v55);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007f114  push    rbp
0x18007f116  push    rbx
0x18007f117  push    rsi
0x18007f118  push    rdi
0x18007f119  push    r12
0x18007f11b  push    r13
0x18007f11d  push    r14
0x18007f11f  push    r15
0x18007f121  lea     rbp, [rsp-0C8h]
0x18007f129  sub     rsp, 1C8h
0x18007f130  mov     rax, cs:__security_cookie
0x18007f137  xor     rax, rsp
0x18007f13a  mov     [rbp+100h+var_50], rax
0x18007f141  mov     r15, r9
0x18007f144  mov     [rbp+100h+var_180], r9
0x18007f148  mov     r12, r8
0x18007f14b  mov     rsi, rdx
0x18007f14e  mov     r14, rcx
0x18007f151  mov     r13, [rbp+100h+arg_20]
0x18007f158  xorps   xmm0, xmm0
0x18007f15b  movups  xmmword ptr [rbp+100h+var_110], xmm0
0x18007f15f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007f167  movdqu  [rbp+100h+var_100], xmm1
0x18007f16c  xor     eax, eax
0x18007f16e  mov     [rbp+100h+var_110], ax
0x18007f172  lea     rax, [rbp+100h+var_110]
0x18007f176  mov     [rsp+200h+var_1E0], rax; unsigned __int16 *
0x18007f17b  xor     r9d, r9d
0x18007f17e  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x18007f183  lea     rcx, [rbp+100h+var_110]
0x18007f187  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f18c  mov     rcx, rax; lpSubKey
0x18007f18f  mov     r9, r15; struct _SECURITY_ATTRIBUTES *
0x18007f192  lea     rdx, aServername; "ServerName"
0x18007f199  call    ?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z; CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)
0x18007f19e  mov     edi, eax
0x18007f1a0  test    eax, eax
0x18007f1a2  js      loc_18007F439
0x18007f1a8  lea     rcx, [rbp+100h+var_110]
0x18007f1ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f1b1  mov     rcx, rax; lpSubKey
0x18007f1b4  mov     r9, r13; struct _SECURITY_ATTRIBUTES *
0x18007f1b7  lea     rdx, aMatchingid_0; "MatchingId"
0x18007f1be  call    ?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z; CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)
0x18007f1c3  mov     edi, eax
0x18007f1c5  test    eax, eax
0x18007f1c7  js      loc_18007F439
0x18007f1cd  lea     rcx, [rbp+100h+var_110]
0x18007f1d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f1d6  mov     rcx, rax; lpSubKey
0x18007f1d9  mov     dword ptr [rsp+200h+var_1E0], 0; unsigned int
0x18007f1e1  mov     ebx, dword ptr [rbp+100h+arg_28]
0x18007f1e7  mov     r9d, ebx; struct _SECURITY_ATTRIBUTES *
0x18007f1ea  lea     rdx, aState; "State"
0x18007f1f1  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007f1f6  mov     edi, eax
0x18007f1f8  test    eax, eax
0x18007f1fa  js      loc_18007F43F
0x18007f200  lea     rcx, [rbp+100h+var_110]
0x18007f204  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f209  mov     rcx, rax; lpSubKey
0x18007f20c  mov     dword ptr [rsp+200h+var_1E0], 0; unsigned int
0x18007f214  mov     ebx, dword ptr [rbp+100h+arg_30]
0x18007f21a  mov     r9d, ebx; struct _SECURITY_ATTRIBUTES *
0x18007f21d  lea     rdx, aErrordetail; "ErrorDetail"
0x18007f224  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007f229  mov     edi, eax
0x18007f22b  test    eax, eax
0x18007f22d  js      loc_18007F439
0x18007f233  mov     [rsp+200h+var_188], 0
0x18007f23c  lea     rax, [rsp+200h+var_188]
0x18007f241  mov     [rsp+200h+var_1C8], rax
0x18007f246  mov     dword ptr [rsp+200h+var_1D0], ebx
0x18007f24a  mov     ebx, dword ptr [rbp+100h+arg_28]
0x18007f250  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18007f254  mov     [rsp+200h+var_1E0], r13
0x18007f259  mov     r9, r15
0x18007f25c  mov     r8, r12
0x18007f25f  mov     rdx, rsi
0x18007f262  call    ?AssembleEnterpriseProfileDetails@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2W4LPAENTERPRISEPROFILESTATE@@W4LPAERROR@@AEAV?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@@Z; LPA::EnterpriseManager::AssembleEnterpriseProfileDetails(ushort const (&)[33],ushort const (&)[21],ushort const *,ushort const *,LPAENTERPRISEPROFILESTATE,LPAERROR,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS> &)
0x18007f267  mov     edi, eax
0x18007f269  test    eax, eax
0x18007f26b  js      loc_18007F3E3
0x18007f271  mov     rdx, rsi
0x18007f274  lea     rcx, [rbp+100h+var_150]
0x18007f278  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f27d  lea     r15, [r14+58h]
0x18007f281  lea     r8, [rbp+100h+var_150]
0x18007f285  lea     rdx, [rsp+200h+var_190]
0x18007f28a  mov     rcx, r15
0x18007f28d  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x18007f292  lea     rcx, [rbp+100h+var_150]
0x18007f296  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f29b  mov     rax, [rsp+200h+var_190]
0x18007f2a0  cmp     [r15], rax
0x18007f2a3  jnz     loc_18007F337
0x18007f2a9  lea     rcx, [rsp+200h+var_190]
0x18007f2ae  call    ??$make_unique@UEsimDetails@EnterpriseManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(void)
0x18007f2b3  nop
0x18007f2b4  mov     rbx, [rsp+200h+var_190]
0x18007f2b9  mov     rdx, r12
0x18007f2bc  lea     rcx, [rbp+100h+var_130]
0x18007f2c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f2c5  nop
0x18007f2c6  lea     r8, [rbp+100h+var_130]
0x18007f2ca  lea     rdx, [rbp+100h+var_150]
0x18007f2ce  lea     rcx, [rbx+10h]
0x18007f2d2  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007f2d7  mov     rcx, [rax]
0x18007f2da  add     rcx, 40h ; '@'
0x18007f2de  lea     rdx, [rsp+200h+var_188]
0x18007f2e3  call    ??$?4U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@$0A@@?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS> &&)
0x18007f2e8  nop
0x18007f2e9  lea     rcx, [rbp+100h+var_130]
0x18007f2ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f2f2  mov     rdx, rsi
0x18007f2f5  lea     rcx, [rbp+100h+var_130]
0x18007f2f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f2fe  nop
0x18007f2ff  lea     r8, [rbp+100h+var_130]
0x18007f303  lea     rdx, [rbp+100h+var_150]
0x18007f307  mov     rcx, r15
0x18007f30a  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007f30f  mov     rcx, [rax]
0x18007f312  add     rcx, 40h ; '@'
0x18007f316  lea     rdx, [rsp+200h+var_190]
0x18007f31b  call    ??$?4U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::EsimDetails> &&)
0x18007f320  nop
0x18007f321  lea     rcx, [rbp+100h+var_130]
0x18007f325  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f32a  nop
0x18007f32b  lea     rcx, [rsp+200h+var_190]
0x18007f330  call    ??1?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(void)
0x18007f335  jmp     short loc_18007F374
0x18007f337  mov     rbx, [rax+40h]
0x18007f33b  mov     rdx, r12
0x18007f33e  lea     rcx, [rbp+100h+var_130]
0x18007f342  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f347  nop
0x18007f348  lea     r8, [rbp+100h+var_130]
0x18007f34c  lea     rdx, [rbp+100h+var_150]
0x18007f350  lea     rcx, [rbx+10h]
0x18007f354  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007f359  mov     rcx, [rax]
0x18007f35c  add     rcx, 40h ; '@'
0x18007f360  lea     rdx, [rsp+200h+var_188]
0x18007f365  call    ??$?4U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@$0A@@?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS> &&)
0x18007f36a  nop
0x18007f36b  lea     rcx, [rbp+100h+var_130]
0x18007f36f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f374  mov     rdx, rsi
0x18007f377  lea     rcx, [rbp+100h+var_F0]
0x18007f37b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f380  nop
0x18007f381  lea     r8, [rbp+100h+var_F0]
0x18007f385  lea     rdx, [rbp+100h+var_150]
0x18007f389  mov     rcx, r15
0x18007f38c  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007f391  mov     rcx, [rax]
0x18007f394  mov     rbx, [rcx+40h]
0x18007f398  mov     rdx, r12
0x18007f39b  lea     rcx, [rbp+100h+var_130]
0x18007f39f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f3a4  nop
0x18007f3a5  lea     r8, [rbp+100h+var_130]
0x18007f3a9  lea     rdx, [rbp+100h+var_150]
0x18007f3ad  lea     rcx, [rbx+10h]
0x18007f3b1  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007f3b6  mov     rdx, [rax]
0x18007f3b9  mov     rdx, [rdx+40h]; struct LPA_ENTERPRISE_PROFILE_DETAILS *
0x18007f3bd  mov     rcx, r14; this
0x18007f3c0  call    ?BroadcastProfileUpdates@EnterpriseManager@LPA@@AEAAXPEBULPA_ENTERPRISE_PROFILE_DETAILS@@@Z; LPA::EnterpriseManager::BroadcastProfileUpdates(LPA_ENTERPRISE_PROFILE_DETAILS const *)
0x18007f3c5  nop
0x18007f3c6  lea     rcx, [rbp+100h+var_130]
0x18007f3ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f3cf  nop
0x18007f3d0  lea     rcx, [rbp+100h+var_F0]
0x18007f3d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f3d9  mov     ebx, dword ptr [rbp+100h+arg_28]
0x18007f3df  mov     r15, [rbp+100h+var_180]
0x18007f3e3  lea     rcx, [rsp+200h+var_188]
0x18007f3e8  call    ??1?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::~unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>(void)
0x18007f3ed  test    edi, edi
0x18007f3ef  js      short loc_18007F43F
0x18007f3f1  lea     rax, ?CustomDeleter@Util@LPA@@YAXPEAX@Z; LPA::Util::CustomDeleter(void *)
0x18007f3f8  mov     [rbp+100h+var_150], rax
0x18007f3fc  mov     [rbp+100h+var_148], 0
0x18007f404  lea     rcx, [r14+8]
0x18007f408  mov     rax, [rcx]
0x18007f40b  lea     r8, [rbp+100h+var_150]
0x18007f40f  mov     rdx, rsi
0x18007f412  mov     rax, [rax+40h]
0x18007f416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f41b  mov     edi, eax
0x18007f41d  test    eax, eax
0x18007f41f  js      short loc_18007F42E
0x18007f421  mov     rdx, [rbp+100h+var_148]; struct LPA_ENTERPRISE_ESIM_DETAILS *
0x18007f425  mov     rcx, r14; this
0x18007f428  call    ?BroadcastEsimUpdates@EnterpriseManager@LPA@@AEAAXPEBULPA_ENTERPRISE_ESIM_DETAILS@@@Z; LPA::EnterpriseManager::BroadcastEsimUpdates(LPA_ENTERPRISE_ESIM_DETAILS const *)
0x18007f42d  nop
0x18007f42e  lea     rcx, [rbp+100h+var_150]
0x18007f432  call    ??1?$unique_ptr@ULPA_SERVICE_INFO@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(void)
0x18007f437  jmp     short loc_18007F43F
0x18007f439  mov     ebx, dword ptr [rbp+100h+arg_28]
0x18007f43f  xor     eax, eax
0x18007f441  mov     [rbp+100h+var_A0], ax
0x18007f445  xor     edx, edx; Val
0x18007f447  lea     r8d, [rax+40h]; Size
0x18007f44b  lea     rcx, [rbp+100h+var_A0+2]; void *
0x18007f44f  call    memset_0
0x18007f454  xor     eax, eax
0x18007f456  mov     [rbp+100h+var_D0], ax
0x18007f45a  xorps   xmm0, xmm0
0x18007f45d  movups  xmmword ptr [rbp+100h+var_D0+2], xmm0
0x18007f461  movups  xmmword ptr [rbp+100h+var_D0+12h], xmm0
0x18007f465  mov     qword ptr [rbp+100h+var_D0+22h], rax
0x18007f469  lea     rdx, [rbp+100h+var_A0]; unsigned __int16 (*)[33]
0x18007f46d  mov     rcx, rsi; this
0x18007f470  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x18007f475  lea     rdx, [rbp+100h+var_D0]; unsigned __int16 (*)[21]
0x18007f479  mov     rcx, r12; this
0x18007f47c  call    ?WritePiiFilteredProfileIdToBuffer@CommonUtil@@YAXPEAY0BF@$$CBGAEAY0BF@G@Z; CommonUtil::WritePiiFilteredProfileIdToBuffer(ushort const (*)[21],ushort (&)[21])
0x18007f481  mov     eax, cs:CallbackContext
0x18007f487  test    edi, edi
0x18007f489  js      loc_18007F52D
0x18007f48f  cmp     eax, 4
0x18007f492  jbe     loc_18007F5D5
0x18007f498  mov     eax, dword ptr [rbp+100h+arg_30]
0x18007f49e  mov     dword ptr [rbp+100h+var_180], eax
0x18007f4a1  mov     [rbp+100h+var_178], r13
0x18007f4a5  mov     [rbp+100h+var_170], r15
0x18007f4a9  lea     rax, [rbp+100h+var_D0]
0x18007f4ad  mov     [rbp+100h+var_168], rax
0x18007f4b1  lea     rax, [rbp+100h+var_A0]
0x18007f4b5  mov     [rbp+100h+var_160], rax
0x18007f4b9  mov     dword ptr [rsp+200h+var_188], edi
0x18007f4bd  lea     rax, aLpaEnterprisem_13; "LPA::EnterpriseManager::SetProfileDetai"...
0x18007f4c4  mov     [rbp+100h+var_158], rax
0x18007f4c8  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007f4cf  mov     [rbp+100h+var_150], rax
0x18007f4d3  lea     rax, [rbp+100h+var_180]
0x18007f4d7  mov     [rsp+200h+var_1A0], rax
0x18007f4dc  lea     rax, [rsp+200h+var_190]
0x18007f4e1  mov     [rsp+200h+var_1A8], rax
0x18007f4e6  lea     rax, [rbp+100h+var_178]
0x18007f4ea  mov     [rsp+200h+var_1B0], rax
0x18007f4ef  lea     rax, [rbp+100h+var_170]
0x18007f4f3  mov     [rsp+200h+var_1B8], rax
0x18007f4f8  lea     rax, [rbp+100h+var_168]
0x18007f4fc  mov     [rsp+200h+var_1C0], rax
0x18007f501  lea     rax, [rbp+100h+var_160]
0x18007f505  mov     [rsp+200h+var_1C8], rax
0x18007f50a  lea     rax, [rsp+200h+var_188]
0x18007f50f  mov     [rsp+200h+var_1D0], rax
0x18007f514  lea     rax, [rbp+100h+var_158]
0x18007f518  mov     [rsp+200h+var_1D8], rax
0x18007f51d  lea     rax, [rbp+100h+var_150]
0x18007f521  lea     rdx, byte_18012B603
0x18007f528  jmp     loc_18007F5C6
0x18007f52d  cmp     eax, 2
0x18007f530  jbe     loc_18007F5D5
0x18007f536  mov     eax, dword ptr [rbp+100h+arg_30]
0x18007f53c  mov     dword ptr [rsp+200h+var_188], eax
0x18007f540  mov     [rbp+100h+var_150], r13
0x18007f544  mov     [rbp+100h+var_158], r15
0x18007f548  lea     rax, [rbp+100h+var_D0]
0x18007f54c  mov     [rbp+100h+var_160], rax
0x18007f550  lea     rax, [rbp+100h+var_A0]
0x18007f554  mov     [rbp+100h+var_168], rax
0x18007f558  mov     dword ptr [rbp+100h+var_180], edi
0x18007f55b  lea     rax, aLpaEnterprisem_13; "LPA::EnterpriseManager::SetProfileDetai"...
0x18007f562  mov     [rbp+100h+var_170], rax
0x18007f566  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007f56d  mov     [rbp+100h+var_178], rax
0x18007f571  lea     rax, [rsp+200h+var_188]
0x18007f576  mov     [rsp+200h+var_1A0], rax
0x18007f57b  lea     rax, [rsp+200h+var_190]
0x18007f580  mov     [rsp+200h+var_1A8], rax
0x18007f585  lea     rax, [rbp+100h+var_150]
0x18007f589  mov     [rsp+200h+var_1B0], rax
0x18007f58e  lea     rax, [rbp+100h+var_158]
0x18007f592  mov     [rsp+200h+var_1B8], rax
0x18007f597  lea     rax, [rbp+100h+var_160]
0x18007f59b  mov     [rsp+200h+var_1C0], rax
0x18007f5a0  lea     rax, [rbp+100h+var_168]
0x18007f5a4  mov     [rsp+200h+var_1C8], rax
0x18007f5a9  lea     rax, [rbp+100h+var_180]
0x18007f5ad  mov     [rsp+200h+var_1D0], rax
0x18007f5b2  lea     rax, [rbp+100h+var_170]
0x18007f5b6  mov     [rsp+200h+var_1D8], rax
0x18007f5bb  lea     rax, [rbp+100h+var_178]
0x18007f5bf  lea     rdx, byte_18012B589
0x18007f5c6  mov     dword ptr [rsp+200h+var_190], ebx
0x18007f5ca  mov     [rsp+200h+var_1E0], rax
0x18007f5cf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007f5d4  nop
0x18007f5d5  lea     rcx, [rbp+100h+var_110]
0x18007f5d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f5de  mov     eax, edi
0x18007f5e0  mov     rcx, [rbp+100h+var_50]
  ... truncated ...
```
