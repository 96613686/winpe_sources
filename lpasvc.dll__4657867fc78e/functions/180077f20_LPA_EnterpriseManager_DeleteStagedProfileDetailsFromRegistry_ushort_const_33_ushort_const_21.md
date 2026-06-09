# LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry(ushort const (*)[33],ushort const (&)[21])

- ea: `0x180077f20`
- end: `0x180078300`
- name: `?DeleteStagedProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0BF@$$CBG@Z`
- size: `992`
- prototype: `int(LPA::EnterpriseManager *__hidden this, const unsigned __int16 (*)[33], const unsigned __int16 (*)[21])`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007d420`

## callees

- `0x180002794`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005cd20`
- `0x1800602e0`
- `0x180063668`
- `0x18006d990`
- `0x1800704b8`
- `0x180070d40`
- `0x180071344`
- `0x180071650`
- `0x180076938`
- `0x1800775b4`
- `0x180077628`
- `0x180077f20`
- `0x18007a404`
- `0x18007d37c`
- `0x180080d34`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800780fe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800780fe`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180078085`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180078085`

## string_xrefs

- `0x180078221`: `LpaServiceEnterpriseManager`
- `0x180078286`: `LpaServiceEnterpriseManager`
- `0x180078215`: `LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry`
- `0x18007827a`: `LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry(
        LPA::EnterpriseManager *this,
        const unsigned __int16 (*a2)[33],
        unsigned __int16 (*a3)[21])
{
  LPA::EnterpriseManager *v6; // rcx
  signed int StagedEsimDetails; // edi
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // r15
  const unsigned __int16 *v11; // rax
  int v12; // r9d
  const WCHAR *v13; // rax
  LSTATUS v14; // eax
  __int64 v15; // r8
  const WCHAR *v16; // rax
  LSTATUS v17; // eax
  char *v18; // rbx
  unsigned __int16 *v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned __int16 **v23; // rax
  char *v24; // rdx
  unsigned __int16 **v26; // [rsp+28h] [rbp-D8h]
  unsigned __int16 **v27; // [rsp+38h] [rbp-C8h]
  unsigned __int16 **v28; // [rsp+40h] [rbp-C0h]
  _BYTE v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v32; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v34; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v36[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v37; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[14]; // [rsp+C2h] [rbp-3Eh] BYREF
  __m128 v39; // [rsp+D0h] [rbp-30h]
  _BYTE v40[28]; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v41; // [rsp+FCh] [rbp-4h]
  unsigned __int16 v42; // [rsp+FEh] [rbp-2h]
  __int16 v43; // [rsp+100h] [rbp+0h]
  unsigned __int16 v44[21]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v45[40]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v46[40]; // [rsp+190h] [rbp+90h] BYREF

  memset_0(v45, 0, 0x42u);
  v30 = *((_QWORD *)this + 9);
  StagedEsimDetails = LPA::EnterpriseManager::ResolveEsimId(v6, a2, (unsigned __int16 (*)[33])v45);
  if ( StagedEsimDetails >= 0 )
  {
    v29[0] = 0;
    StagedEsimDetails = LPA::EnterpriseManager::GetStagedEsimDetails(
                          (_DWORD)this,
                          (unsigned int)v45,
                          0,
                          (unsigned int)&v30,
                          (__int64)v29);
    if ( StagedEsimDetails >= 0 )
    {
      v8 = v30;
      v9 = *(_QWORD *)(v30 + 64);
      std::wstring::wstring(v35, (unsigned __int16 *)a3);
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
        v9,
        &v30,
        v35);
      std::wstring::_Tidy_deallocate(v35);
      v10 = v30;
      if ( **(_QWORD **)(v8 + 64) == v30 )
      {
        StagedEsimDetails = -2147023728;
      }
      else
      {
        memset_0(v46, 0, 0x42u);
        v35[0] = 0;
        v35[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v35[0]) = 0;
        v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8 + 32);
        StagedEsimDetails = StringCchCopyW(v46, 0x21u, v11);
        if ( StagedEsimDetails >= 0 )
        {
          LOBYTE(v12) = 1;
          LPA::EnterpriseManager::AssembleProfileRegKey((_DWORD)this, (unsigned int)v46, (_DWORD)a3, v12, (__int64)v35);
          v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
          v14 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v13);
          StagedEsimDetails = v14;
          if ( v14 > 0 )
            StagedEsimDetails = (unsigned __int16)v14 | 0x80070000;
          if ( StagedEsimDetails >= 0 )
          {
            std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>,0>>::_Erase_unchecked(
              *(_QWORD *)(v8 + 64),
              v10);
            if ( !*(_QWORD *)(*(_QWORD *)(v8 + 64) + 8LL) )
            {
              v36[0] = 0;
              v36[1] = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v36[0]) = 0;
              LOBYTE(v15) = 1;
              LPA::EnterpriseManager::AssembleEuiccRegKey(this, v46, v15, v36);
              v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
              v17 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v16);
              StagedEsimDetails = v17;
              if ( v17 > 0 )
                StagedEsimDetails = (unsigned __int16)v17 | 0x80070000;
              if ( StagedEsimDetails >= 0 )
              {
                v18 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(
                                (char *)this + 72,
                                v8);
                std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::~pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>(v18 + 32);
                std::_Deallocate<16>(v18, (struct std::nothrow_t *)0x48);
              }
              std::wstring::_Tidy_deallocate(v36);
            }
          }
        }
        std::wstring::_Tidy_deallocate(v35);
      }
    }
  }
  v37 = 0;
  memset_0(v38, 0, 0x40u);
  memset(v44, 0, sizeof(v44));
  if ( v45[0] && (int)StringCchCopyNW(&v37, 0x21u, v45, 8u) >= 0 )
  {
    v39 = _mm_movelh_ps((__m128)0x2A002A002A002AuLL, (__m128)0x2A002A002A002AuLL);
    *(__m128 *)v40 = v39;
    *(__m128 *)&v40[12] = v39;
    v41 = v45[30];
    v42 = v45[31];
    v43 = 0;
  }
  else
  {
    v37 = 0;
  }
  CommonUtil::WritePiiFilteredProfileIdToBuffer(
    (CommonUtil *)a3,
    (const unsigned __int16 (*)[21])v44,
    (unsigned __int16 (*)[21])v19);
  if ( StagedEsimDetails < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = v44;
      v33 = &v37;
      v32 = (unsigned __int16 *)"LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry";
      v31 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
      v28 = &v34;
      v27 = &v33;
      v26 = &v32;
      v23 = &v31;
      v24 = byte_18012BBBB;
      goto LABEL_25;
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v31 = v44;
    v32 = &v37;
    v33 = (unsigned __int16 *)"LPA::EnterpriseManager::DeleteStagedProfileDetailsFromRegistry";
    v34 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
    v28 = &v31;
    v27 = &v32;
    v26 = &v33;
    v23 = &v34;
    v24 = byte_18012BC0B;
LABEL_25:
    LODWORD(v30) = StagedEsimDetails;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v20,
      (_DWORD)v24,
      v21,
      v22,
      (__int64)v23,
      (__int64)v26,
      (__int64)&v30,
      (__int64)v27,
      (__int64)v28);
  }
  return (unsigned int)StagedEsimDetails;
}

```

## disassembly

```asm
0x180077f20  mov     [rsp-8+arg_18], rbx
0x180077f25  push    rbp
0x180077f26  push    rsi
0x180077f27  push    rdi
0x180077f28  push    r12
0x180077f2a  push    r13
0x180077f2c  push    r14
0x180077f2e  push    r15
0x180077f30  lea     rbp, [rsp-0F0h]
0x180077f38  sub     rsp, 1F0h
0x180077f3f  mov     rax, cs:__security_cookie
0x180077f46  xor     rax, rsp
0x180077f49  mov     [rbp+120h+var_40], rax
0x180077f50  mov     r12, r8
0x180077f53  mov     rbx, rdx
0x180077f56  mov     rsi, rcx
0x180077f59  xor     edx, edx; Val
0x180077f5b  lea     r8d, [rdx+42h]; Size
0x180077f5f  lea     rcx, [rbp+120h+var_E0]; void *
0x180077f63  call    memset_0
0x180077f68  mov     rax, [rsi+48h]
0x180077f6c  mov     [rsp+220h+var_1C8], rax
0x180077f71  lea     r8, [rbp+120h+var_E0]; unsigned __int16 (*)[33]
0x180077f75  mov     rdx, rbx; unsigned __int16 (*)[33]
0x180077f78  call    ?ResolveEsimId@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAY0CB@G@Z; LPA::EnterpriseManager::ResolveEsimId(ushort const (*)[33],ushort (&)[33])
0x180077f7d  mov     edi, eax
0x180077f7f  xor     r14d, r14d
0x180077f82  test    eax, eax
0x180077f84  js      loc_180078150
0x180077f8a  mov     [rsp+220h+var_1D0], r14b
0x180077f8f  lea     rax, [rsp+220h+var_1D0]
0x180077f94  mov     [rsp+220h+var_200], rax
0x180077f99  lea     r9, [rsp+220h+var_1C8]
0x180077f9e  xor     r8d, r8d
0x180077fa1  lea     rdx, [rbp+120h+var_E0]
0x180077fa5  mov     rcx, rsi
0x180077fa8  call    ?GetStagedEsimDetails@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBG_NAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@std@@AEA_N@Z; LPA::EnterpriseManager::GetStagedEsimDetails(ushort const (*)[33],bool,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>>> &,bool &)
0x180077fad  mov     edi, eax
0x180077faf  test    eax, eax
0x180077fb1  js      loc_180078150
0x180077fb7  mov     rbx, [rsp+220h+var_1C8]
0x180077fbc  mov     rdi, [rbx+40h]
0x180077fc0  mov     rdx, r12
0x180077fc3  lea     rcx, [rbp+120h+var_1A0]
0x180077fc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180077fcc  lea     r8, [rbp+120h+var_1A0]
0x180077fd0  lea     rdx, [rsp+220h+var_1C8]
0x180077fd5  mov     rcx, rdi
0x180077fd8  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x180077fdd  lea     rcx, [rbp+120h+var_1A0]
0x180077fe1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077fe6  mov     r15, [rsp+220h+var_1C8]
0x180077feb  mov     rax, [rbx+40h]
0x180077fef  cmp     [rax], r15
0x180077ff2  jnz     short loc_180077FFE
0x180077ff4  mov     edi, 80070490h
0x180077ff9  jmp     loc_180078150
0x180077ffe  xor     edx, edx; Val
0x180078000  lea     r8d, [rdx+42h]; Size
0x180078004  lea     rcx, [rbp+120h+var_90]; void *
0x18007800b  call    memset_0
0x180078010  xorps   xmm0, xmm0
0x180078013  movups  [rbp+120h+var_1A0], xmm0
0x180078017  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007801f  movdqu  [rbp+120h+var_190], xmm1
0x180078024  xor     eax, eax
0x180078026  mov     word ptr [rbp+120h+var_1A0], ax
0x18007802a  lea     rcx, [rbx+20h]
0x18007802e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078033  mov     r8, rax; unsigned __int16 *
0x180078036  mov     edx, 21h ; '!'; unsigned __int64
0x18007803b  lea     rcx, [rbp+120h+var_90]; unsigned __int16 *
0x180078042  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180078047  mov     edi, eax
0x180078049  xor     r14d, r14d
0x18007804c  test    eax, eax
0x18007804e  js      loc_180078147
0x180078054  lea     rax, [rbp+120h+var_1A0]
0x180078058  mov     [rsp+220h+var_200], rax
0x18007805d  mov     r9b, 1
0x180078060  mov     r8, r12
0x180078063  lea     rdx, [rbp+120h+var_90]
0x18007806a  mov     rcx, rsi
0x18007806d  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x180078072  lea     rcx, [rbp+120h+var_1A0]
0x180078076  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007807b  mov     rdx, rax; lpSubKey
0x18007807e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078085  call    cs:__imp_RegDeleteKeyW
0x18007808b  mov     edi, eax
0x18007808d  test    eax, eax
0x18007808f  jle     short loc_18007809A
0x180078091  movzx   edi, ax
0x180078094  or      edi, 80070000h
0x18007809a  test    edi, edi
0x18007809c  js      loc_180078147
0x1800780a2  mov     rdx, r15
0x1800780a5  mov     rcx, [rbx+40h]
0x1800780a9  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>>,std::_Iterator_base0>)
0x1800780ae  mov     rax, [rbx+40h]
0x1800780b2  cmp     [rax+8], r14
0x1800780b6  jnz     loc_180078147
0x1800780bc  xorps   xmm0, xmm0
0x1800780bf  movups  [rbp+120h+var_180], xmm0
0x1800780c3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800780cb  movdqu  [rbp+120h+var_170], xmm1
0x1800780d0  mov     word ptr [rbp+120h+var_180], r14w
0x1800780d5  lea     r9, [rbp+120h+var_180]
0x1800780d9  mov     r8b, 1
0x1800780dc  lea     rdx, [rbp+120h+var_90]
0x1800780e3  mov     rcx, rsi
0x1800780e6  call    ?AssembleEuiccRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleEuiccRegKey(ushort const (&)[33],bool,std::wstring &)
0x1800780eb  lea     rcx, [rbp+120h+var_180]
0x1800780ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800780f4  mov     rdx, rax; lpSubKey
0x1800780f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800780fe  call    cs:__imp_RegDeleteTreeW
0x180078104  mov     edi, eax
0x180078106  test    eax, eax
0x180078108  jle     short loc_180078113
0x18007810a  movzx   edi, ax
0x18007810d  or      edi, 80070000h
0x180078113  test    edi, edi
0x180078115  js      short loc_18007813D
0x180078117  mov     rdx, rbx
0x18007811a  lea     rcx, [rsi+48h]
0x18007811e  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>,std::_Iterator_base0>)
0x180078123  mov     rbx, rax
0x180078126  lea     rcx, [rax+20h]
0x18007812a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::~pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>(void)
0x18007812f  mov     edx, 48h ; 'H'
0x180078134  mov     rcx, rbx
0x180078137  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007813c  nop
0x18007813d  lea     rcx, [rbp+120h+var_180]
0x180078141  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078146  nop
0x180078147  lea     rcx, [rbp+120h+var_1A0]
0x18007814b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078150  mov     [rbp+120h+var_160], r14w
0x180078155  xor     edx, edx; Val
0x180078157  lea     r8d, [rdx+40h]; Size
0x18007815b  lea     rcx, [rbp+120h+var_15E]; void *
0x18007815f  call    memset_0
0x180078164  mov     [rbp+120h+var_110], r14w
0x180078169  xorps   xmm0, xmm0
0x18007816c  xor     eax, eax
0x18007816e  movups  xmmword ptr [rbp+120h+var_110+2], xmm0
0x180078172  movups  xmmword ptr [rbp+120h+var_110+12h], xmm0
0x180078176  mov     qword ptr [rbp+120h+var_110+22h], rax
0x18007817a  cmp     [rbp+120h+var_E0], r14w
0x18007817f  jz      short loc_1800781DF
0x180078181  lea     r9d, [rax+8]; unsigned __int64
0x180078185  lea     r8, [rbp+120h+var_E0]; unsigned __int16 *
0x180078189  lea     edx, [rax+21h]; unsigned __int64
0x18007818c  lea     rcx, [rbp+120h+var_160]; unsigned __int16 *
0x180078190  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180078195  test    eax, eax
0x180078197  js      short loc_1800781DF
0x180078199  mov     eax, 2Ah ; '*'
0x18007819e  movzx   ecx, ax
0x1800781a1  mov     eax, ecx
0x1800781a3  shl     rcx, 10h
0x1800781a7  or      rcx, rax
0x1800781aa  mov     rax, rcx
0x1800781ad  shl     rcx, 20h
0x1800781b1  or      rcx, rax
0x1800781b4  movq    xmm0, rcx
0x1800781b9  movlhps xmm0, xmm0
0x1800781bc  movups  [rbp+120h+var_150], xmm0
0x1800781c0  movups  xmmword ptr [rbp+120h+var_140], xmm0
0x1800781c4  movups  xmmword ptr [rbp+120h+var_140+0Ch], xmm0
0x1800781c8  movzx   eax, [rbp+120h+var_A4]
0x1800781cc  mov     [rbp+120h+var_124], ax
0x1800781d0  movzx   eax, [rbp+120h+var_A2]
0x1800781d4  mov     [rbp+120h+var_122], ax
0x1800781d8  mov     [rbp+120h+var_120], r14w
0x1800781dd  jmp     short loc_1800781E4
0x1800781df  mov     [rbp+120h+var_160], r14w
0x1800781e4  lea     rdx, [rbp+120h+var_110]; unsigned __int16 (*)[21]
0x1800781e8  mov     rcx, r12; this
0x1800781eb  call    ?WritePiiFilteredProfileIdToBuffer@CommonUtil@@YAXPEAY0BF@$$CBGAEAY0BF@G@Z; CommonUtil::WritePiiFilteredProfileIdToBuffer(ushort const (*)[21],ushort (&)[21])
0x1800781f0  mov     eax, cs:CallbackContext
0x1800781f6  test    edi, edi
0x1800781f8  js      short loc_180078263
0x1800781fa  cmp     eax, 4
0x1800781fd  jbe     loc_1800782D4
0x180078203  lea     rax, [rbp+120h+var_110]
0x180078207  mov     [rsp+220h+var_1C0], rax
0x18007820c  lea     rax, [rbp+120h+var_160]
0x180078210  mov     [rsp+220h+var_1B8], rax
0x180078215  lea     rax, aLpaEnterprisem_1; "LPA::EnterpriseManager::DeleteStagedPro"...
0x18007821c  mov     [rsp+220h+var_1B0], rax
0x180078221  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x180078228  mov     [rsp+220h+var_1A8], rax
0x18007822d  lea     rax, [rsp+220h+var_1C0]
0x180078232  mov     [rsp+220h+var_1E0], rax
0x180078237  lea     rax, [rsp+220h+var_1B8]
0x18007823c  mov     [rsp+220h+var_1E8], rax
0x180078241  lea     rax, [rsp+220h+var_1C8]
0x180078246  mov     [rsp+220h+var_1F0], rax
0x18007824b  lea     rax, [rsp+220h+var_1B0]
0x180078250  mov     [rsp+220h+var_1F8], rax
0x180078255  lea     rax, [rsp+220h+var_1A8]
0x18007825a  lea     rdx, byte_18012BC0B
0x180078261  jmp     short loc_1800782C6
0x180078263  cmp     eax, 2
0x180078266  jbe     short loc_1800782D4
0x180078268  lea     rax, [rbp+120h+var_110]
0x18007826c  mov     [rsp+220h+var_1A8], rax
0x180078271  lea     rax, [rbp+120h+var_160]
0x180078275  mov     [rsp+220h+var_1B0], rax
0x18007827a  lea     rax, aLpaEnterprisem_1; "LPA::EnterpriseManager::DeleteStagedPro"...
0x180078281  mov     [rsp+220h+var_1B8], rax
0x180078286  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007828d  mov     [rsp+220h+var_1C0], rax
0x180078292  lea     rax, [rsp+220h+var_1A8]
0x180078297  mov     [rsp+220h+var_1E0], rax
0x18007829c  lea     rax, [rsp+220h+var_1B0]
0x1800782a1  mov     [rsp+220h+var_1E8], rax
0x1800782a6  lea     rax, [rsp+220h+var_1C8]
0x1800782ab  mov     [rsp+220h+var_1F0], rax
0x1800782b0  lea     rax, [rsp+220h+var_1B8]
0x1800782b5  mov     [rsp+220h+var_1F8], rax
0x1800782ba  lea     rax, [rsp+220h+var_1C0]
0x1800782bf  lea     rdx, byte_18012BBBB
0x1800782c6  mov     [rsp+220h+var_200], rax
0x1800782cb  mov     dword ptr [rsp+220h+var_1C8], edi
0x1800782cf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800782d4  mov     eax, edi
0x1800782d6  mov     rcx, [rbp+120h+var_40]
0x1800782dd  xor     rcx, rsp; StackCookie
0x1800782e0  call    __security_check_cookie
0x1800782e5  mov     rbx, [rsp+220h+arg_18]
0x1800782ed  add     rsp, 1F0h
0x1800782f4  pop     r15
0x1800782f6  pop     r14
0x1800782f8  pop     r13
0x1800782fa  pop     r12
0x1800782fc  pop     rdi
0x1800782fd  pop     rsi
0x1800782fe  pop     rbp
0x1800782ff  retn
```
