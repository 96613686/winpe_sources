# LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry(ushort const (&)[33],ushort const (&)[21],std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<LPA::EnterpriseManager::EsimDetails,std::default_delete<LPA::EnterpriseManager::EsimDetails>>>>>> &,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS,std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>>>>>> &)

- ea: `0x180077b9c`
- end: `0x180077f1a`
- name: `?DeleteProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEAY0BF@$$CBGAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@std@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@@std@@@std@@@4@@Z`
- size: `894`
- prototype: `__int64 __usercall@<rax>(LPA::EnterpriseManager *this@<rcx>, CommonUtil *@<rdx>, CommonUtil *@<r8>, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180077a40`
- `0x18007f610`

## callees

- `0x1800028e0`
- `0x18000df90`
- `0x18000ebf4`
- `0x1800602e0`
- `0x1800653e8`
- `0x180065bd4`
- `0x1800704b8`
- `0x180070d40`
- `0x180071344`
- `0x180071650`
- `0x1800768e8`
- `0x180076910`
- `0x1800775b4`
- `0x180077628`
- `0x180077854`
- `0x180077b9c`
- `0x180080a28`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180077d7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180077d7c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180077c6b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180077c6b`

## string_xrefs

- `0x180077e1c`: `LpaServiceEnterpriseManager`
- `0x180077e9a`: `LpaServiceEnterpriseManager`
- `0x180077e10`: `LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry`
- `0x180077e8e`: `LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry(
        LPA::EnterpriseManager *this,
        CommonUtil *a2,
        CommonUtil *a3,
        __int64 *a4,
        __int64 *a5)
{
  unsigned __int16 (*v9)[33]; // r8
  unsigned __int16 (*v10)[21]; // r8
  signed int v11; // r15d
  const WCHAR *v12; // rax
  LSTATUS v13; // eax
  __int64 v14; // rcx
  int v15; // r8d
  int v16; // r9d
  signed int v17; // edi
  __int64 v18; // r10
  char *v19; // rbx
  const WCHAR *v20; // rax
  LSTATUS v21; // eax
  __int64 v22; // r9
  char *v23; // rbx
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  signed int v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-90h] BYREF
  struct LPA_ENTERPRISE_ESIM_DETAILS *v30[2]; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h]
  _OWORD v32[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v33[21]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v34[33]; // [rsp+F0h] [rbp-10h] BYREF

  v34[0] = 0;
  memset_0(&v34[1], 0, 0x40u);
  memset(v33, 0, sizeof(v33));
  CommonUtil::WritePiiFilteredEsimIdToBuffer(a2, (const unsigned __int16 (*)[33])v34, v9);
  CommonUtil::WritePiiFilteredProfileIdToBuffer(a3, (const unsigned __int16 (*)[21])v33, v10);
  v32[0] = 0;
  v32[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32[0]) = 0;
  v11 = *(_DWORD *)(*(_QWORD *)(*a5 + 64) + 116LL);
  LPA::EnterpriseManager::AssembleProfileRegKey((_DWORD)this, (_DWORD)a2, (_DWORD)a3, 0, (__int64)v32);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  v13 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v12);
  v17 = v13;
  if ( v13 > 0 )
    v17 = (unsigned __int16)v13 | 0x80070000;
  if ( v17 < 0 )
    goto LABEL_16;
  v25 = *a5;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v25);
  v19 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(
                  *(_QWORD *)(*a4 + 64) + 16LL,
                  v18);
  std::pair<std::wstring const,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::~pair<std::wstring const,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>(v19 + 32);
  std::_Deallocate<16>(v19, (struct std::nothrow_t *)0x48);
  *a5 = v25;
  v30[0] = (struct LPA_ENTERPRISE_ESIM_DETAILS *)LPA::Util::CustomDeleter;
  v30[1] = 0;
  v17 = (*(__int64 (__fastcall **)(char *, CommonUtil *, struct LPA_ENTERPRISE_ESIM_DETAILS **))(*((_QWORD *)this + 1)
                                                                                               + 64LL))(
          (char *)this + 8,
          a2,
          v30);
  if ( v17 >= 0 )
    LPA::EnterpriseManager::BroadcastEsimUpdates(this, v30[1]);
  std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(v30);
  if ( v17 < 0 )
    goto LABEL_16;
  v14 = *(_QWORD *)(*a4 + 64);
  if ( *(_QWORD *)(v14 + 24) || *(_DWORD *)v14 )
    goto LABEL_14;
  *(_OWORD *)v30 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v30[0]) = 0;
  LPA::EnterpriseManager::AssembleEuiccRegKey(this, a2, 0, v30);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
  v21 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v20);
  v17 = v21;
  if ( v21 > 0 )
    v17 = (unsigned __int16)v21 | 0x80070000;
  if ( v17 >= 0 )
  {
    v25 = *a4;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v25);
    v23 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(
                    (char *)this + 88,
                    v22);
    std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::~pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>(v23 + 32);
    std::_Deallocate<16>(v23, (struct std::nothrow_t *)0x48);
    *a4 = v25;
  }
  std::wstring::_Tidy_deallocate(v30);
  if ( v17 >= 0 )
  {
LABEL_14:
    if ( (unsigned int)CallbackContext > 4 )
    {
      v26 = v11;
      v27 = v33;
      v28 = v34;
      LODWORD(v25) = v17;
      v29 = (unsigned __int16 *)"LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry";
      v30[0] = (struct LPA_ENTERPRISE_ESIM_DETAILS *)"LpaServiceEnterpriseManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_18012BCB3,
        v15,
        v16,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  else
  {
LABEL_16:
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v25) = v11;
      v30[0] = (struct LPA_ENTERPRISE_ESIM_DETAILS *)v33;
      v29 = v34;
      v26 = v17;
      v28 = (unsigned __int16 *)"LPA::EnterpriseManager::DeleteProfileDetailsFromRegistry";
      v27 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_18012BC5B,
        v15,
        v16,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)v30,
        (__int64)&v25);
    }
  }
  std::wstring::_Tidy_deallocate(v32);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180077b9c  push    rbp
0x180077b9e  push    rbx
0x180077b9f  push    rsi
0x180077ba0  push    rdi
0x180077ba1  push    r12
0x180077ba3  push    r13
0x180077ba5  push    r14
0x180077ba7  push    r15
0x180077ba9  lea     rbp, [rsp-58h]
0x180077bae  sub     rsp, 158h
0x180077bb5  mov     rax, cs:__security_cookie
0x180077bbc  xor     rax, rsp
0x180077bbf  mov     [rbp+90h+var_50], rax
0x180077bc3  mov     rsi, r9
0x180077bc6  mov     rbx, r8
0x180077bc9  mov     r12, rdx
0x180077bcc  mov     r14, rcx
0x180077bcf  mov     r13, [rbp+90h+arg_20]
0x180077bd6  xor     eax, eax
0x180077bd8  mov     [rbp+90h+var_A0], ax
0x180077bdc  xor     edx, edx; Val
0x180077bde  lea     r8d, [rax+40h]; Size
0x180077be2  lea     rcx, [rbp+90h+var_A0+2]; void *
0x180077be6  call    memset_0
0x180077beb  xor     eax, eax
0x180077bed  mov     [rbp+90h+var_D8], ax
0x180077bf1  xorps   xmm0, xmm0
0x180077bf4  movups  xmmword ptr [rbp+90h+var_D8+2], xmm0
0x180077bf8  movups  xmmword ptr [rbp+90h+var_D8+12h], xmm0
0x180077bfc  mov     qword ptr [rbp+90h+var_D8+22h], rax
0x180077c00  lea     rdx, [rbp+90h+var_A0]; unsigned __int16 (*)[33]
0x180077c04  mov     rcx, r12; this
0x180077c07  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x180077c0c  lea     rdx, [rbp+90h+var_D8]; unsigned __int16 (*)[21]
0x180077c10  mov     rcx, rbx; this
0x180077c13  call    ?WritePiiFilteredProfileIdToBuffer@CommonUtil@@YAXPEAY0BF@$$CBGAEAY0BF@G@Z; CommonUtil::WritePiiFilteredProfileIdToBuffer(ushort const (*)[21],ushort (&)[21])
0x180077c18  xorps   xmm0, xmm0
0x180077c1b  movups  [rbp+90h+var_F8], xmm0
0x180077c1f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180077c27  movdqu  [rbp+90h+var_E8], xmm1
0x180077c2c  xor     eax, eax
0x180077c2e  mov     word ptr [rbp+90h+var_F8], ax
0x180077c32  mov     rax, [r13+0]
0x180077c36  mov     rcx, [rax+40h]
0x180077c3a  mov     r15d, [rcx+74h]
0x180077c3e  lea     rax, [rbp+90h+var_F8]
0x180077c42  mov     [rsp+190h+var_170], rax
0x180077c47  xor     r9d, r9d
0x180077c4a  mov     r8, rbx
0x180077c4d  mov     rdx, r12
0x180077c50  mov     rcx, r14
0x180077c53  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x180077c58  lea     rcx, [rbp+90h+var_F8]
0x180077c5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077c61  mov     rdx, rax; lpSubKey
0x180077c64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077c6b  call    cs:__imp_RegDeleteKeyW
0x180077c71  mov     edi, eax
0x180077c73  test    eax, eax
0x180077c75  jle     short loc_180077C80
0x180077c77  movzx   edi, ax
0x180077c7a  or      edi, 80070000h
0x180077c80  test    edi, edi
0x180077c82  js      loc_180077E68
0x180077c88  mov     r10, [r13+0]
0x180077c8c  mov     [rsp+190h+var_140], r10
0x180077c91  lea     rcx, [rsp+190h+var_140]
0x180077c96  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180077c9b  mov     r9, [rsi]
0x180077c9e  mov     rcx, [r9+40h]
0x180077ca2  add     rcx, 10h
0x180077ca6  mov     rdx, r10
0x180077ca9  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>,std::_Iterator_base0>)
0x180077cae  mov     rbx, rax
0x180077cb1  lea     rcx, [rax+20h]
0x180077cb5  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::~pair<std::wstring const,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>(void)
0x180077cba  mov     edx, 48h ; 'H'
0x180077cbf  mov     rcx, rbx
0x180077cc2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180077cc7  mov     rax, [rsp+190h+var_140]
0x180077ccc  mov     [r13+0], rax
0x180077cd0  lea     rax, ?CustomDeleter@Util@LPA@@YAXPEAX@Z; LPA::Util::CustomDeleter(void *)
0x180077cd7  mov     [rsp+190h+var_118], rax
0x180077cdc  xor     r13d, r13d
0x180077cdf  mov     [rbp+90h+var_118+8], r13
0x180077ce3  lea     rcx, [r14+8]
0x180077ce7  mov     rax, [rcx]
0x180077cea  lea     r8, [rsp+190h+var_118]
0x180077cef  mov     rdx, r12
0x180077cf2  mov     rax, [rax+40h]
0x180077cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077cfb  mov     edi, eax
0x180077cfd  test    eax, eax
0x180077cff  js      short loc_180077D0E
0x180077d01  mov     rdx, [rbp+90h+var_118+8]; struct LPA_ENTERPRISE_ESIM_DETAILS *
0x180077d05  mov     rcx, r14; this
0x180077d08  call    ?BroadcastEsimUpdates@EnterpriseManager@LPA@@AEAAXPEBULPA_ENTERPRISE_ESIM_DETAILS@@@Z; LPA::EnterpriseManager::BroadcastEsimUpdates(LPA_ENTERPRISE_ESIM_DETAILS const *)
0x180077d0d  nop
0x180077d0e  lea     rcx, [rsp+190h+var_118]
0x180077d13  call    ??1?$unique_ptr@ULPA_SERVICE_INFO@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(void)
0x180077d18  test    edi, edi
0x180077d1a  js      loc_180077E68
0x180077d20  mov     rax, [rsi]
0x180077d23  mov     rcx, [rax+40h]
0x180077d27  cmp     [rcx+18h], r13
0x180077d2b  jnz     loc_180077DE6
0x180077d31  cmp     [rcx], r13d
0x180077d34  jnz     loc_180077DE6
0x180077d3a  xorps   xmm0, xmm0
0x180077d3d  movups  xmmword ptr [rsp+190h+var_118], xmm0
0x180077d42  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180077d4a  movdqu  [rbp+90h+var_108], xmm1
0x180077d4f  mov     word ptr [rsp+190h+var_118], r13w
0x180077d55  lea     r9, [rsp+190h+var_118]
0x180077d5a  xor     r8d, r8d
0x180077d5d  mov     rdx, r12
0x180077d60  mov     rcx, r14
0x180077d63  call    ?AssembleEuiccRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleEuiccRegKey(ushort const (&)[33],bool,std::wstring &)
0x180077d68  lea     rcx, [rsp+190h+var_118]
0x180077d6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077d72  mov     rdx, rax; lpSubKey
0x180077d75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077d7c  call    cs:__imp_RegDeleteTreeW
0x180077d82  mov     edi, eax
0x180077d84  test    eax, eax
0x180077d86  jle     short loc_180077D91
0x180077d88  movzx   edi, ax
0x180077d8b  or      edi, 80070000h
0x180077d91  test    edi, edi
0x180077d93  js      short loc_180077DD4
0x180077d95  mov     r9, [rsi]
0x180077d98  mov     [rsp+190h+var_140], r9
0x180077d9d  lea     rcx, [rsp+190h+var_140]
0x180077da2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180077da7  lea     rcx, [r14+58h]
0x180077dab  mov     rdx, r9
0x180077dae  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VOperationEntry@EnterpriseManager@LPA@@U?$default_delete@VOperationEntry@EnterpriseManager@LPA@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>,std::_Iterator_base0>)
0x180077db3  mov     rbx, rax
0x180077db6  lea     rcx, [rax+20h]
0x180077dba  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::~pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>(void)
0x180077dbf  mov     edx, 48h ; 'H'
0x180077dc4  mov     rcx, rbx
0x180077dc7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180077dcc  mov     rax, [rsp+190h+var_140]
0x180077dd1  mov     [rsi], rax
0x180077dd4  lea     rcx, [rsp+190h+var_118]
0x180077dd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077dde  test    edi, edi
0x180077de0  js      loc_180077E68
0x180077de6  mov     eax, cs:CallbackContext
0x180077dec  cmp     eax, 4
0x180077def  jbe     loc_180077EEF
0x180077df5  mov     [rsp+190h+var_138], r15d
0x180077dfa  lea     rax, [rbp+90h+var_D8]
0x180077dfe  mov     [rsp+190h+var_130], rax
0x180077e03  lea     rax, [rbp+90h+var_A0]
0x180077e07  mov     [rsp+190h+var_128], rax
0x180077e0c  mov     dword ptr [rsp+190h+var_140], edi
0x180077e10  lea     rax, aLpaEnterprisem_10; "LPA::EnterpriseManager::DeleteProfileDe"...
0x180077e17  mov     [rsp+190h+var_120], rax
0x180077e1c  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x180077e23  mov     [rsp+190h+var_118], rax
0x180077e28  lea     rax, [rsp+190h+var_138]
0x180077e2d  mov     [rsp+190h+var_148], rax
0x180077e32  lea     rax, [rsp+190h+var_130]
0x180077e37  mov     [rsp+190h+var_150], rax
0x180077e3c  lea     rax, [rsp+190h+var_128]
0x180077e41  mov     [rsp+190h+var_158], rax
0x180077e46  lea     rax, [rsp+190h+var_140]
0x180077e4b  mov     [rsp+190h+var_160], rax
0x180077e50  lea     rax, [rsp+190h+var_120]
0x180077e55  mov     [rsp+190h+var_168], rax
0x180077e5a  lea     rax, [rsp+190h+var_118]
0x180077e5f  lea     rdx, byte_18012BCB3
0x180077e66  jmp     short loc_180077EE4
0x180077e68  mov     eax, cs:CallbackContext
0x180077e6e  cmp     eax, 2
0x180077e71  jbe     short loc_180077EEF
0x180077e73  mov     dword ptr [rsp+190h+var_140], r15d
0x180077e78  lea     rax, [rbp+90h+var_D8]
0x180077e7c  mov     [rsp+190h+var_118], rax
0x180077e81  lea     rax, [rbp+90h+var_A0]
0x180077e85  mov     [rsp+190h+var_120], rax
0x180077e8a  mov     [rsp+190h+var_138], edi
0x180077e8e  lea     rax, aLpaEnterprisem_10; "LPA::EnterpriseManager::DeleteProfileDe"...
0x180077e95  mov     [rsp+190h+var_128], rax
0x180077e9a  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x180077ea1  mov     [rsp+190h+var_130], rax
0x180077ea6  lea     rax, [rsp+190h+var_140]
0x180077eab  mov     [rsp+190h+var_148], rax
0x180077eb0  lea     rax, [rsp+190h+var_118]
0x180077eb5  mov     [rsp+190h+var_150], rax
0x180077eba  lea     rax, [rsp+190h+var_120]
0x180077ebf  mov     [rsp+190h+var_158], rax
0x180077ec4  lea     rax, [rsp+190h+var_138]
0x180077ec9  mov     [rsp+190h+var_160], rax
0x180077ece  lea     rax, [rsp+190h+var_128]
0x180077ed3  mov     [rsp+190h+var_168], rax
0x180077ed8  lea     rax, [rsp+190h+var_130]
0x180077edd  lea     rdx, byte_18012BC5B
0x180077ee4  mov     [rsp+190h+var_170], rax
0x180077ee9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180077eee  nop
0x180077eef  lea     rcx, [rbp+90h+var_F8]
0x180077ef3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077ef8  mov     eax, edi
0x180077efa  mov     rcx, [rbp+90h+var_50]
0x180077efe  xor     rcx, rsp; StackCookie
0x180077f01  call    __security_check_cookie
0x180077f06  add     rsp, 158h
0x180077f0d  pop     r15
0x180077f0f  pop     r14
0x180077f11  pop     r13
0x180077f13  pop     r12
0x180077f15  pop     rdi
0x180077f16  pop     rsi
0x180077f17  pop     rbx
0x180077f18  pop     rbp
0x180077f19  retn
```
