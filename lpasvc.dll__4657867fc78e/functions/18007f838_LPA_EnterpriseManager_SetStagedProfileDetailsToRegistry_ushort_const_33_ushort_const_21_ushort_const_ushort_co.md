# LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry(ushort const (*)[33],ushort const (&)[21],ushort const *,ushort const *,bool,ushort const *,ulong,bool)

- ea: `0x18007f838`
- end: `0x18007fdd2`
- name: `?SetStagedProfileDetailsToRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2_N2K3@Z`
- size: `1434`
- prototype: `__int64 __usercall@<rax>(LPA::EnterpriseManager *__hidden this@<rcx>, const unsigned __int16 (*)[33]@<rdx>, const unsigned __int16 (*)[21]@<r8>, const unsigned __int16 *@<r9>, struct _SECURITY_ATTRIBUTES *, bool, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *, bool)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800770b0`
- `0x18007d420`

## callees

- `0x180002ff0`
- `0x18000df90`
- `0x18000ebf4`
- `0x180063668`
- `0x1800704b8`
- `0x1800709e4`
- `0x180071344`
- `0x180071650`
- `0x180071a8c`
- `0x18007423c`
- `0x1800742d8`
- `0x1800756dc`
- `0x1800757a0`
- `0x180075a7c`
- `0x180075d30`
- `0x180076a20`
- `0x180076a74`
- `0x180077628`
- `0x18007793c`
- `0x18007d37c`
- `0x18007ed6c`
- `0x18007f838`
- `0x18007fdd8`
- `0x180080484`
- `0x180080a28`
- `0x180081010`

## string_xrefs

- `0x18007fc8a`: `LpaServiceEnterpriseManager`
- `0x18007fd28`: `LpaServiceEnterpriseManager`
- `0x18007fc7f`: `LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry`
- `0x18007fd1d`: `LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry(
        LPA::EnterpriseManager *this,
        unsigned __int16 (*a2)[33],
        unsigned __int16 (*a3)[21],
        struct _SECURITY_ATTRIBUTES *a4,
        struct _SECURITY_ATTRIBUTES *a5,
        bool a6,
        struct _SECURITY_ATTRIBUTES *a7,
        struct _SECURITY_ATTRIBUTES *a8,
        bool a9)
{
  struct _SECURITY_ATTRIBUTES *v12; // rbx
  const BYTE *v13; // r14
  LPA::EnterpriseManager *v14; // rcx
  int v15; // edi
  int v16; // r9d
  unsigned int v17; // r13d
  const WCHAR *v18; // rax
  const unsigned __int16 *v19; // r8
  const WCHAR *v20; // rax
  const unsigned __int16 *v21; // r8
  BOOL v22; // ebx
  const WCHAR *v23; // rax
  const unsigned __int16 *v24; // r8
  const WCHAR *v25; // rax
  const unsigned __int16 *v26; // r8
  const WCHAR *v27; // rax
  const unsigned __int16 *v28; // r8
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rbx
  unsigned __int16 *v36; // r8
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  struct _SECURITY_ATTRIBUTES **v40; // rax
  __int64 *v41; // rdx
  __int64 *v43; // [rsp+58h] [rbp-A8h]
  __int64 *v44; // [rsp+68h] [rbp-98h]
  BOOL v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  struct _SECURITY_ATTRIBUTES *v47; // [rsp+80h] [rbp-80h] BYREF
  const char *v48; // [rsp+88h] [rbp-78h] BYREF
  struct _SECURITY_ATTRIBUTES *v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v50; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v51; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES *v52; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES *v53; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v54[8]; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v55; // [rsp+C0h] [rbp-40h]
  _BYTE v56[32]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v57[4]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 v58[8]; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  unsigned __int16 v60[21]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v61[33]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v62[33]; // [rsp+1B0h] [rbp+B0h] BYREF

  v49 = a4;
  v57[0] = a2;
  v52 = a4;
  v12 = a5;
  v47 = a5;
  v51 = (unsigned __int16 *)a5;
  v13 = (const BYTE *)a7;
  v53 = a7;
  v50 = (unsigned __int16 *)a7;
  memset_0(v61, 0, sizeof(v61));
  *(_OWORD *)v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v58[0] = 0;
  v15 = LPA::EnterpriseManager::ResolveEsimId(v14, a2, (unsigned __int16 (*)[33])v61);
  v17 = (unsigned int)a8;
  if ( v15 >= 0 )
  {
    LOBYTE(v16) = 1;
    LPA::EnterpriseManager::AssembleProfileRegKey((_DWORD)this, (unsigned int)v61, (_DWORD)a3, v16, (__int64)v58);
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
    v15 = CommonUtil::SetStringToRegistry(v18, L"ServerName", v19, (const BYTE *)v49);
    if ( v15 >= 0 )
    {
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
      v15 = CommonUtil::SetStringToRegistry(v20, L"MatchingId", v21, (const BYTE *)a5);
      if ( v15 >= 0 )
      {
        v22 = a6;
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
        v15 = CommonUtil::SetDwordToRegistry(v23, L"Enable", v24, (struct _SECURITY_ATTRIBUTES *)v22, 0);
        if ( v15 >= 0 )
        {
          v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
          v15 = CommonUtil::SetStringToRegistry(v25, L"AccountId", v26, v13);
          if ( v15 >= 0 )
          {
            v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
            v15 = CommonUtil::SetDwordToRegistry(v27, L"RetriesLeft", v28, (struct _SECURITY_ATTRIBUTES *)v17, 0);
            if ( v15 >= 0 )
            {
              v45 = 0;
              LODWORD(v46) = 0;
              v29 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 24, v54);
              std::make_unique<LPA::EnterpriseManager::StagedProfileDetails,std::shared_ptr<LPA::EnterpriseManager>,unsigned short const (* &)[33],unsigned short const * &,unsigned short const * &,bool &,unsigned short const * &,unsigned long &,int,int,bool &,0>(
                (unsigned int)&v48,
                v29,
                (unsigned int)v57,
                (unsigned int)&v52,
                (__int64)&v51,
                (__int64)&a6,
                (__int64)&v50,
                (__int64)&a8,
                (__int64)&v46,
                (__int64)&v45,
                (__int64)&a9);
              if ( v55 )
                std::_Ref_count_base::_Decref(v55);
              std::wstring::wstring(v56, v61);
              std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
                (char *)this + 72,
                v57,
                v56);
              std::wstring::_Tidy_deallocate(v56);
              if ( *((_QWORD *)this + 9) == v57[0] )
              {
                std::make_unique<LPA::EnterpriseManager::StagedEsimDetails,,0>(&v46);
                std::wstring::wstring(v56, (unsigned __int16 *)a3);
                v30 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(
                        v46,
                        v57,
                        v56);
                std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(
                  (__int64 *)(*(_QWORD *)v30 + 64LL),
                  (__int64 *)&v48);
                std::wstring::_Tidy_deallocate(v56);
                std::wstring::wstring(v56, v61);
                v31 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(
                        (char *)this + 72,
                        v57,
                        v56);
                std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedEsimDetails>,0>(
                  (__int64 *)(*(_QWORD *)v31 + 64LL),
                  &v46);
                std::wstring::_Tidy_deallocate(v56);
                std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::~unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>(&v46);
              }
              else
              {
                v32 = *(_QWORD *)(v57[0] + 64LL);
                std::wstring::wstring(v56, (unsigned __int16 *)a3);
                v33 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(
                        v32,
                        v57,
                        v56);
                std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(
                  (__int64 *)(*(_QWORD *)v33 + 64LL),
                  (__int64 *)&v48);
                std::wstring::_Tidy_deallocate(v56);
              }
              std::wstring::wstring(v57, v61);
              v34 = *(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(
                                             (char *)this + 72,
                                             v54,
                                             v57)
                              + 64LL);
              std::wstring::wstring(v56, (unsigned __int16 *)a3);
              v35 = *(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(
                                 v34,
                                 v54,
                                 v56);
              std::wstring::_Tidy_deallocate(v56);
              std::wstring::_Tidy_deallocate(v57);
              if ( a9
                && v17 == 2
                && (int)LPA::EnterpriseManager::StagedProfileDetails::StartTimer(*(struct _TP_TIMER ***)(v35 + 64)) >= 0 )
              {
                *(_BYTE *)(*(_QWORD *)(v35 + 64) + 197LL) = 1;
                LPA::EnterpriseManager::CalculateNumberOfEnterpriseTasks(this, a2);
              }
              std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::~unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>(&v48);
              v13 = (const BYTE *)v53;
            }
          }
        }
        v12 = v47;
      }
    }
  }
  v62[0] = 0;
  memset_0(&v62[1], 0, 0x40u);
  memset(v60, 0, sizeof(v60));
  if ( a2 )
    CommonUtil::WritePiiFilteredEsimIdToBuffer(
      (CommonUtil *)a2,
      (const unsigned __int16 (*)[33])v62,
      (unsigned __int16 (*)[33])v36);
  CommonUtil::WritePiiFilteredProfileIdToBuffer(
    (CommonUtil *)a3,
    (const unsigned __int16 (*)[21])v60,
    (unsigned __int16 (*)[21])v36);
  if ( v15 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v47) = v17;
      LODWORD(v46) = a6;
      v52 = v49;
      v51 = v60;
      v50 = v62;
      v45 = v15;
      v49 = (struct _SECURITY_ATTRIBUTES *)"LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry";
      v48 = "LpaServiceEnterpriseManager";
      v44 = (__int64 *)&v47;
      v43 = &v46;
      v40 = (struct _SECURITY_ATTRIBUTES **)&v45;
      v41 = (__int64 *)&byte_18012B1FF;
      goto LABEL_25;
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v46) = v17;
    v45 = a6;
    v52 = v49;
    v51 = v60;
    v50 = v62;
    LODWORD(v47) = v15;
    v49 = (struct _SECURITY_ATTRIBUTES *)"LPA::EnterpriseManager::SetStagedProfileDetailsToRegistry";
    v48 = "LpaServiceEnterpriseManager";
    v44 = &v46;
    v43 = (__int64 *)&v45;
    v40 = &v47;
    v41 = qword_18012B290;
LABEL_25:
    v53 = (struct _SECURITY_ATTRIBUTES *)v13;
    v57[0] = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v37,
      (_DWORD)v41,
      v38,
      v39,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)v40,
      (__int64)&v50,
      (__int64)&v51,
      (__int64)&v52,
      (__int64)v57,
      (__int64)v43,
      (__int64)&v53,
      (__int64)v44);
  }
  std::wstring::_Tidy_deallocate(v58);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18007f838  push    rbp
0x18007f83a  push    rbx
0x18007f83b  push    rsi
0x18007f83c  push    rdi
0x18007f83d  push    r12
0x18007f83f  push    r13
0x18007f841  push    r14
0x18007f843  push    r15
0x18007f845  lea     rbp, [rsp-118h]
0x18007f84d  sub     rsp, 218h
0x18007f854  mov     rax, cs:__security_cookie
0x18007f85b  xor     rax, rsp
0x18007f85e  mov     [rbp+150h+var_50], rax
0x18007f865  mov     rax, r9
0x18007f868  mov     [rbp+150h+var_1C0], rax
0x18007f86c  mov     r12, r8
0x18007f86f  mov     rsi, rdx
0x18007f872  mov     r15, rcx
0x18007f875  mov     [rbp+150h+var_168], rdx
0x18007f879  mov     [rbp+150h+var_1A8], rax
0x18007f87d  mov     rbx, [rbp+150h+arg_20]
0x18007f884  mov     [rbp+150h+var_1D0], rbx
0x18007f888  mov     [rbp+150h+var_1B0], rbx
0x18007f88c  mov     r14, [rbp+150h+arg_30]
0x18007f893  mov     [rbp+150h+var_1A0], r14
0x18007f897  mov     [rbp+150h+var_1B8], r14
0x18007f89b  xor     edx, edx; Val
0x18007f89d  lea     r8d, [rdx+42h]; Size
0x18007f8a1  lea     rcx, [rbp+150h+var_F0]; void *
0x18007f8a5  call    memset_0
0x18007f8aa  xorps   xmm0, xmm0
0x18007f8ad  movups  xmmword ptr [rbp+150h+var_148], xmm0
0x18007f8b1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007f8b9  movdqu  [rbp+150h+var_138], xmm1
0x18007f8be  xor     eax, eax
0x18007f8c0  mov     [rbp+150h+var_148], ax
0x18007f8c4  lea     r8, [rbp+150h+var_F0]; unsigned __int16 (*)[33]
0x18007f8c8  mov     rdx, rsi; unsigned __int16 (*)[33]
0x18007f8cb  call    ?ResolveEsimId@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0CB@G@Z; LPA::EnterpriseManager::ResolveEsimId(ushort const (*)[33],ushort (&)[33])
0x18007f8d0  mov     edi, eax
0x18007f8d2  mov     r13d, dword ptr [rbp+150h+arg_38]
0x18007f8d9  test    eax, eax
0x18007f8db  js      loc_18007FBEA
0x18007f8e1  lea     rax, [rbp+150h+var_148]
0x18007f8e5  mov     [rsp+250h+var_230], rax; unsigned __int16 *
0x18007f8ea  mov     r9b, 1
0x18007f8ed  mov     r8, r12
0x18007f8f0  lea     rdx, [rbp+150h+var_F0]
0x18007f8f4  mov     rcx, r15
0x18007f8f7  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x18007f8fc  lea     rcx, [rbp+150h+var_148]
0x18007f900  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f905  mov     rcx, rax; lpSubKey
0x18007f908  mov     r9, [rbp+150h+var_1C0]; struct _SECURITY_ATTRIBUTES *
0x18007f90c  lea     rdx, aServername; "ServerName"
0x18007f913  call    ?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z; CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)
0x18007f918  mov     edi, eax
0x18007f91a  test    eax, eax
0x18007f91c  js      loc_18007FBEA
0x18007f922  lea     rcx, [rbp+150h+var_148]
0x18007f926  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f92b  mov     rcx, rax; lpSubKey
0x18007f92e  mov     r9, rbx; struct _SECURITY_ATTRIBUTES *
0x18007f931  lea     rdx, aMatchingid_0; "MatchingId"
0x18007f938  call    ?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z; CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)
0x18007f93d  mov     edi, eax
0x18007f93f  test    eax, eax
0x18007f941  js      loc_18007FBEA
0x18007f947  xor     ebx, ebx
0x18007f949  cmp     [rbp+150h+arg_28], bl
0x18007f94f  setnz   bl
0x18007f952  lea     rcx, [rbp+150h+var_148]
0x18007f956  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f95b  mov     rcx, rax; lpSubKey
0x18007f95e  mov     dword ptr [rsp+250h+var_230], 0; unsigned __int16 *
0x18007f966  mov     r9d, ebx; struct _SECURITY_ATTRIBUTES *
0x18007f969  lea     rdx, aEnable; "Enable"
0x18007f970  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007f975  mov     edi, eax
0x18007f977  xor     ebx, ebx
0x18007f979  test    eax, eax
0x18007f97b  js      loc_18007FBE6
0x18007f981  lea     rcx, [rbp+150h+var_148]
0x18007f985  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f98a  mov     rcx, rax; lpSubKey
0x18007f98d  mov     r9, r14; struct _SECURITY_ATTRIBUTES *
0x18007f990  lea     rdx, aAccountid; "AccountId"
0x18007f997  call    ?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z; CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)
0x18007f99c  mov     edi, eax
0x18007f99e  test    eax, eax
0x18007f9a0  js      loc_18007FBE6
0x18007f9a6  lea     rcx, [rbp+150h+var_148]
0x18007f9aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f9af  mov     rcx, rax; lpSubKey
0x18007f9b2  mov     dword ptr [rsp+250h+var_230], ebx; unsigned int
0x18007f9b6  mov     r9d, r13d; struct _SECURITY_ATTRIBUTES *
0x18007f9b9  lea     rdx, aRetriesleft; "RetriesLeft"
0x18007f9c0  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007f9c5  mov     edi, eax
0x18007f9c7  test    eax, eax
0x18007f9c9  js      loc_18007FBE6
0x18007f9cf  mov     [rsp+250h+var_1E0], ebx
0x18007f9d3  mov     dword ptr [rsp+250h+var_1D8], ebx
0x18007f9d7  lea     rcx, [r15+18h]
0x18007f9db  lea     rdx, [rbp+150h+var_198]
0x18007f9df  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18007f9e4  nop
0x18007f9e5  lea     rcx, [rbp+150h+arg_40]
0x18007f9ec  mov     [rsp+250h+var_200], rcx
0x18007f9f1  lea     rcx, [rsp+250h+var_1E0]
0x18007f9f6  mov     [rsp+250h+var_208], rcx
0x18007f9fb  lea     rcx, [rsp+250h+var_1D8]
0x18007fa00  mov     [rsp+250h+var_210], rcx
0x18007fa05  lea     rcx, [rbp+150h+arg_38]
0x18007fa0c  mov     [rsp+250h+var_218], rcx
0x18007fa11  lea     rcx, [rbp+150h+var_1B8]
0x18007fa15  mov     [rsp+250h+var_220], rcx
0x18007fa1a  lea     rcx, [rbp+150h+arg_28]
0x18007fa21  mov     [rsp+250h+var_228], rcx
0x18007fa26  lea     rcx, [rbp+150h+var_1B0]
0x18007fa2a  mov     [rsp+250h+var_230], rcx
0x18007fa2f  lea     r9, [rbp+150h+var_1A8]
0x18007fa33  lea     r8, [rbp+150h+var_168]
0x18007fa37  mov     rdx, rax
0x18007fa3a  lea     rcx, [rbp+150h+var_1C8]
0x18007fa3e  call    ??$make_unique@VStagedProfileDetails@EnterpriseManager@LPA@@V?$shared_ptr@VEnterpriseManager@LPA@@@std@@AEAPEAY0CB@$$CBGAEAPEBGAEAPEBGAEA_NAEAPEBGAEAKHHAEA_N$0A@@std@@YA?AV?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@0@$$QEAV?$shared_ptr@VEnterpriseManager@LPA@@@0@AEAPEAY0CB@$$CBGAEAPEBG2AEA_N2AEAK$$QEAH53@Z; std::make_unique<LPA::EnterpriseManager::StagedProfileDetails,std::shared_ptr<LPA::EnterpriseManager>,ushort const (* &)[33],ushort const * &,ushort const * &,bool &,ushort const * &,ulong &,int,int,bool &,0>(std::shared_ptr<LPA::EnterpriseManager> &&,ushort const (* &)[33],ushort const * &,ushort const * &,bool &,ushort const * &,ulong &,int &&,int &&,bool &)
0x18007fa43  nop
0x18007fa44  mov     rcx, [rbp+150h+var_190]; this
0x18007fa48  test    rcx, rcx
0x18007fa4b  jz      short loc_18007FA52
0x18007fa4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007fa52  lea     rdx, [rbp+150h+var_F0]
0x18007fa56  lea     rcx, [rbp+150h+var_188]
0x18007fa5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007fa5f  lea     r14, [r15+48h]
0x18007fa63  lea     r8, [rbp+150h+var_188]
0x18007fa67  lea     rdx, [rbp+150h+var_168]
0x18007fa6b  mov     rcx, r14
0x18007fa6e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x18007fa73  lea     rcx, [rbp+150h+var_188]
0x18007fa77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007fa7c  mov     rbx, [rbp+150h+var_168]
0x18007fa80  cmp     [r14], rbx
0x18007fa83  jnz     loc_18007FB13
0x18007fa89  lea     rcx, [rsp+250h+var_1D8]
0x18007fa8e  call    ??$make_unique@UStagedEsimDetails@EnterpriseManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EnterpriseManager::StagedEsimDetails,,0>(void)
0x18007fa93  nop
0x18007fa94  mov     rdx, r12
0x18007fa97  lea     rcx, [rbp+150h+var_188]
0x18007fa9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007faa0  nop
0x18007faa1  lea     r8, [rbp+150h+var_188]
0x18007faa5  lea     rdx, [rbp+150h+var_168]
0x18007faa9  mov     rcx, [rsp+250h+var_1D8]
0x18007faae  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007fab3  mov     rcx, [rax]
0x18007fab6  add     rcx, 40h ; '@'
0x18007faba  lea     rdx, [rbp+150h+var_1C8]
0x18007fabe  call    ??$?4U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails> &&)
0x18007fac3  nop
0x18007fac4  lea     rcx, [rbp+150h+var_188]
0x18007fac8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007facd  lea     rdx, [rbp+150h+var_F0]
0x18007fad1  lea     rcx, [rbp+150h+var_188]
0x18007fad5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007fada  nop
0x18007fadb  lea     r8, [rbp+150h+var_188]
0x18007fadf  lea     rdx, [rbp+150h+var_168]
0x18007fae3  mov     rcx, r14
0x18007fae6  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007faeb  mov     rcx, [rax]
0x18007faee  add     rcx, 40h ; '@'
0x18007faf2  lea     rdx, [rsp+250h+var_1D8]
0x18007faf7  call    ??$?4U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedEsimDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails> &&)
0x18007fafc  nop
0x18007fafd  lea     rcx, [rbp+150h+var_188]
0x18007fb01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007fb06  nop
0x18007fb07  lea     rcx, [rsp+250h+var_1D8]
0x18007fb0c  call    ??1?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::~unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>(void)
0x18007fb11  jmp     short loc_18007FB4E
0x18007fb13  mov     rbx, [rbx+40h]
0x18007fb17  mov     rdx, r12
0x18007fb1a  lea     rcx, [rbp+150h+var_188]
0x18007fb1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007fb23  nop
0x18007fb24  lea     r8, [rbp+150h+var_188]
0x18007fb28  lea     rdx, [rbp+150h+var_168]
0x18007fb2c  mov     rcx, rbx
0x18007fb2f  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007fb34  mov     rcx, [rax]
0x18007fb37  add     rcx, 40h ; '@'
0x18007fb3b  lea     rdx, [rbp+150h+var_1C8]
0x18007fb3f  call    ??$?4U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails> &&)
0x18007fb44  nop
0x18007fb45  lea     rcx, [rbp+150h+var_188]
0x18007fb49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007fb4e  lea     rdx, [rbp+150h+var_F0]
0x18007fb52  lea     rcx, [rbp+150h+var_168]
0x18007fb56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007fb5b  nop
0x18007fb5c  lea     r8, [rbp+150h+var_168]
0x18007fb60  lea     rdx, [rbp+150h+var_198]
0x18007fb64  mov     rcx, r14
0x18007fb67  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007fb6c  mov     rcx, [rax]
0x18007fb6f  mov     rbx, [rcx+40h]
0x18007fb73  mov     rdx, r12
0x18007fb76  lea     rcx, [rbp+150h+var_188]
0x18007fb7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007fb7f  nop
0x18007fb80  lea     r8, [rbp+150h+var_188]
0x18007fb84  lea     rdx, [rbp+150h+var_198]
0x18007fb88  mov     rcx, rbx
0x18007fb8b  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007fb90  mov     rbx, [rax]
0x18007fb93  lea     rcx, [rbp+150h+var_188]
0x18007fb97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007fb9c  nop
0x18007fb9d  lea     rcx, [rbp+150h+var_168]
0x18007fba1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007fba6  cmp     [rbp+150h+arg_40], 0
0x18007fbad  jz      short loc_18007FBD9
0x18007fbaf  cmp     r13d, 2
0x18007fbb3  jnz     short loc_18007FBD9
0x18007fbb5  mov     rcx, [rbx+40h]; this
0x18007fbb9  call    ?StartTimer@StagedProfileDetails@EnterpriseManager@LPA@@QEAAJXZ; LPA::EnterpriseManager::StagedProfileDetails::StartTimer(void)
0x18007fbbe  test    eax, eax
0x18007fbc0  js      short loc_18007FBD9
0x18007fbc2  mov     rax, [rbx+40h]
0x18007fbc6  mov     byte ptr [rax+0C5h], 1
0x18007fbcd  mov     rdx, rsi; unsigned __int16 (*)[33]
0x18007fbd0  mov     rcx, r15; this
0x18007fbd3  call    ?CalculateNumberOfEnterpriseTasks@EnterpriseManager@LPA@@AEAAXPEAY0CB@$$CBG@Z; LPA::EnterpriseManager::CalculateNumberOfEnterpriseTasks(ushort const (*)[33])
0x18007fbd8  nop
0x18007fbd9  lea     rcx, [rbp+150h+var_1C8]
0x18007fbdd  call    ??1?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::~unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>(void)
0x18007fbe2  mov     r14, [rbp+150h+var_1A0]
0x18007fbe6  mov     rbx, [rbp+150h+var_1D0]
0x18007fbea  xor     eax, eax
0x18007fbec  mov     [rbp+150h+var_A0], ax
0x18007fbf3  xor     edx, edx; Val
0x18007fbf5  lea     r8d, [rax+40h]; Size
0x18007fbf9  lea     rcx, [rbp+150h+var_A0+2]; void *
0x18007fc00  call    memset_0
0x18007fc05  xor     eax, eax
0x18007fc07  mov     [rbp+150h+var_128], ax
0x18007fc0b  xorps   xmm0, xmm0
0x18007fc0e  movups  xmmword ptr [rbp+150h+var_128+2], xmm0
0x18007fc12  movups  xmmword ptr [rbp+150h+var_128+12h], xmm0
0x18007fc16  mov     qword ptr [rbp+150h+var_128+22h], rax
0x18007fc1a  test    rsi, rsi
0x18007fc1d  jz      short loc_18007FC2E
0x18007fc1f  lea     rdx, [rbp+150h+var_A0]; unsigned __int16 (*)[33]
0x18007fc26  mov     rcx, rsi; this
0x18007fc29  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x18007fc2e  lea     rdx, [rbp+150h+var_128]; unsigned __int16 (*)[21]
0x18007fc32  mov     rcx, r12; this
0x18007fc35  call    ?WritePiiFilteredProfileIdToBuffer@CommonUtil@@YAXPEAY0BF@$$CBGAEAY0BF@G@Z; CommonUtil::WritePiiFilteredProfileIdToBuffer(ushort const (*)[21],ushort (&)[21])
0x18007fc3a  mov     eax, cs:CallbackContext
0x18007fc40  test    edi, edi
0x18007fc42  js      loc_18007FCE6
0x18007fc48  cmp     eax, 4
0x18007fc4b  jbe     loc_18007FDA4
0x18007fc51  mov     dword ptr [rsp+250h+var_1D8], r13d
0x18007fc56  movzx   eax, [rbp+150h+arg_28]
0x18007fc5d  mov     [rsp+250h+var_1E0], eax
0x18007fc61  mov     rax, [rbp+150h+var_1C0]
0x18007fc65  mov     [rbp+150h+var_1A8], rax
0x18007fc69  lea     rax, [rbp+150h+var_128]
0x18007fc6d  mov     [rbp+150h+var_1B0], rax
0x18007fc71  lea     rax, [rbp+150h+var_A0]
0x18007fc78  mov     [rbp+150h+var_1B8], rax
0x18007fc7c  mov     dword ptr [rbp+150h+var_1D0], edi
0x18007fc7f  lea     rax, aLpaEnterprisem_19; "LPA::EnterpriseManager::SetStagedProfil"...
0x18007fc86  mov     [rbp+150h+var_1C0], rax
0x18007fc8a  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007fc91  mov     [rbp+150h+var_1C8], rax
0x18007fc95  lea     rax, [rsp+250h+var_1D8]
0x18007fc9a  mov     [rsp+250h+var_1E8], rax
0x18007fc9f  lea     rax, [rbp+150h+var_1A0]
0x18007fca3  mov     [rsp+250h+var_1F0], rax
0x18007fca8  lea     rax, [rsp+250h+var_1E0]
0x18007fcad  mov     [rsp+250h+var_1F8], rax
0x18007fcb2  lea     rax, [rbp+150h+var_168]
0x18007fcb6  mov     [rsp+250h+var_200], rax
0x18007fcbb  lea     rax, [rbp+150h+var_1A8]
0x18007fcbf  mov     [rsp+250h+var_208], rax
0x18007fcc4  lea     rax, [rbp+150h+var_1B0]
0x18007fcc8  mov     [rsp+250h+var_210], rax
0x18007fccd  lea     rax, [rbp+150h+var_1B8]
0x18007fcd1  mov     [rsp+250h+var_218], rax
0x18007fcd6  lea     rax, [rbp+150h+var_1D0]
0x18007fcda  lea     rdx, qword_18012B290
0x18007fce1  jmp     loc_18007FD7F
0x18007fce6  cmp     eax, 2
0x18007fce9  jbe     loc_18007FDA4
0x18007fcef  mov     dword ptr [rbp+150h+var_1D0], r13d
0x18007fcf3  movzx   eax, [rbp+150h+arg_28]
0x18007fcfa  mov     dword ptr [rsp+250h+var_1D8], eax
  ... truncated ...
```
