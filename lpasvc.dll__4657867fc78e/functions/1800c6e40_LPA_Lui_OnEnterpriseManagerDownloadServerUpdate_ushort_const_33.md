# LPA::Lui::OnEnterpriseManagerDownloadServerUpdate(ushort const (&)[33])

- ea: `0x1800c6e40`
- end: `0x1800c7127`
- name: `?OnEnterpriseManagerDownloadServerUpdate@Lui@LPA@@EEAAXAEAY0CB@$$CBG@Z`
- size: `743`
- prototype: `void(LPA::Lui *__hidden this, const unsigned __int16 (*)[33])`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006b2c`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005fd34`
- `0x1800602e0`
- `0x1800612d0`
- `0x180063668`
- `0x180064d50`
- `0x180065bd4`
- `0x180071650`
- `0x1800769d8`
- `0x180080a28`
- `0x180081010`
- `0x180084bbc`
- `0x1800c5bc8`
- `0x1800c6e40`
- `0x180101010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800c6f54`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800c6f54`

## string_xrefs

- `0x1800c7019`: `LpaServiceLui`
- `0x1800c700e`: `LPA::Lui::OnEnterpriseManagerDownloadServerUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LPA::Lui::OnEnterpriseManagerDownloadServerUpdate(LPA::Lui *this, unsigned __int16 (*a2)[33])
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 *v6; // rbx
  __int64 v7; // rbx
  _QWORD **v8; // rdi
  size_t size_of; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  unsigned __int16 (*v12)[33]; // r8
  _QWORD *v13; // rdi
  _QWORD *i; // rbx
  int v15; // r8d
  int v16; // r9d
  _DWORD *v17; // rcx
  _QWORD **v18; // rcx
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  _QWORD **v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD **v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  const char *v30; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  void *v32[2]; // [rsp+98h] [rbp-68h] BYREF
  char *v33; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v34; // [rsp+B0h] [rbp-50h] BYREF
  const char *v35; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v36[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37[33]; // [rsp+E0h] [rbp-20h] BYREF

  std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(&v25);
  v4 = **((_QWORD **)this + 15);
  v24 = v4;
  while ( *((_QWORD *)this + 15) != v4 )
  {
    v5 = *(_QWORD *)(v4 + 40);
    std::wstring::wstring(v36, (unsigned __int16 *)a2);
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
      v5 + 24,
      &v29,
      v36);
    std::wstring::_Tidy_deallocate(v36);
    v6 = *(__int64 **)(v4 + 40);
    if ( v6[3] != v29 && *(_BYTE *)(*(_QWORD *)(v29 + 64) + 3LL) )
    {
      if ( v26 == 0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("list too long");
      v7 = *v6;
      v8 = v25;
      v30 = (const char *)&v25;
      v31 = 0;
      size_of = std::_Get_size_of_n<24>(1);
      v10 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      v10[2] = v7;
      ++v26;
      v11 = v8[1];
      *v10 = v8;
      v10[1] = v11;
      v31 = 0;
      v8[1] = v10;
      *v11 = v10;
      std::_Alloc_construct_ptr<std::allocator<std::_List_node<LPA_ENTERPRISE_PROFILE_DETAILS const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<LPA_ENTERPRISE_PROFILE_DETAILS const *,void *>>>(&v30);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v24);
    v4 = v24;
  }
  std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(v32);
  if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 80LL))(
         *((_QWORD *)this + 13),
         (unsigned __int16 *)a2,
         v32) >= 0 )
  {
    v37[0] = 0;
    memset_0(&v37[1], 0, 0x40u);
    CommonUtil::WritePiiFilteredEsimIdToBuffer((CommonUtil *)a2, (const unsigned __int16 (*)[33])v37, v12);
    v13 = v32[0];
    for ( i = *(_QWORD **)v32[0]; i != v13; i = (_QWORD *)*i )
    {
      LPA::Lui::BroadcastHelper(&v25, 10, 652, i[2]);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v17 = (_DWORD *)i[2];
        v33 = (char *)v17 + 78;
        v27 = v17[150];
        v28 = v17[2];
        LODWORD(v29) = v17[1];
        LODWORD(v24) = *v17;
        v34 = v37;
        v35 = "LPA::Lui::OnEnterpriseManagerDownloadServerUpdate";
        v30 = "LpaServiceLui";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v17,
          (unsigned int)&word_180132656,
          v15,
          v16,
          (__int64)&v30,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v24,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v33);
      }
    }
  }
  v18 = (_QWORD **)v32[0];
  **((_QWORD **)v32[0] + 1) = 0;
  v19 = *v18;
  if ( *v18 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(v19 + 2);
      std::_Deallocate<16>(v19, (struct std::nothrow_t *)0x18);
      v19 = v20;
    }
    while ( v20 );
  }
  std::_Deallocate<16>(v32[0], (struct std::nothrow_t *)0x18);
  v21 = v25;
  *v25[1] = 0;
  v22 = *v21;
  if ( v22 )
  {
    do
    {
      v23 = (_QWORD *)*v22;
      std::_Deallocate<16>(v22, (struct std::nothrow_t *)0x18);
      v22 = v23;
    }
    while ( v23 );
  }
  std::_Deallocate<16>(v25, (struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x1800c6e40  mov     [rsp-8+arg_10], rbx
0x1800c6e45  mov     [rsp-8+arg_18], rsi
0x1800c6e4a  push    rbp
0x1800c6e4b  push    rdi
0x1800c6e4c  push    r14
0x1800c6e4e  lea     rbp, [rsp-40h]
0x1800c6e53  sub     rsp, 140h
0x1800c6e5a  mov     rax, cs:__security_cookie
0x1800c6e61  xor     rax, rsp
0x1800c6e64  mov     [rbp+50h+var_20], rax
0x1800c6e68  mov     r14, rdx
0x1800c6e6b  mov     rsi, rcx
0x1800c6e6e  lea     rcx, [rsp+150h+var_E8]
0x1800c6e73  call    ??0?$list@PEBULPA_PROFILE_DETAILS@@V?$allocator@PEBULPA_PROFILE_DETAILS@@@std@@@std@@QEAA@XZ; std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(void)
0x1800c6e78  nop
0x1800c6e79  mov     rbx, [rsi+78h]
0x1800c6e7d  mov     rbx, [rbx]
0x1800c6e80  mov     [rsp+150h+var_F0], rbx
0x1800c6e85  cmp     [rsi+78h], rbx
0x1800c6e89  jz      loc_1800C6F5B
0x1800c6e8f  mov     rdi, [rbx+28h]
0x1800c6e93  mov     rdx, r14
0x1800c6e96  lea     rcx, [rbp+50h+var_90]
0x1800c6e9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c6e9f  lea     r8, [rbp+50h+var_90]
0x1800c6ea3  lea     rdx, [rbp+50h+var_D0]
0x1800c6ea7  lea     rcx, [rdi+18h]
0x1800c6eab  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x1800c6eb0  lea     rcx, [rbp+50h+var_90]
0x1800c6eb4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c6eb9  mov     rbx, [rbx+28h]
0x1800c6ebd  mov     rax, [rbp+50h+var_D0]
0x1800c6ec1  cmp     [rbx+18h], rax
0x1800c6ec5  jz      short loc_1800C6F39
0x1800c6ec7  mov     rcx, [rax+40h]
0x1800c6ecb  cmp     byte ptr [rcx+3], 0
0x1800c6ecf  jz      short loc_1800C6F39
0x1800c6ed1  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800c6edb  cmp     [rsp+150h+var_E0], rax
0x1800c6ee0  jz      short loc_1800C6F4D
0x1800c6ee2  mov     rbx, [rbx]
0x1800c6ee5  mov     rdi, [rsp+150h+var_E8]
0x1800c6eea  lea     rax, [rsp+150h+var_E8]
0x1800c6eef  mov     [rbp+50h+var_C8], rax
0x1800c6ef3  mov     [rbp+50h+var_C0], 0
0x1800c6efb  mov     ecx, 1
0x1800c6f00  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800c6f05  mov     rcx, rax
0x1800c6f08  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800c6f0d  mov     [rax+10h], rbx
0x1800c6f11  inc     [rsp+150h+var_E0]
0x1800c6f16  mov     rcx, [rdi+8]
0x1800c6f1a  mov     [rax], rdi
0x1800c6f1d  mov     [rax+8], rcx
0x1800c6f21  mov     [rbp+50h+var_C0], 0
0x1800c6f29  mov     [rdi+8], rax
0x1800c6f2d  mov     [rcx], rax
0x1800c6f30  lea     rcx, [rbp+50h+var_C8]
0x1800c6f34  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEBULPA_ENTERPRISE_PROFILE_DETAILS@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<LPA_ENTERPRISE_PROFILE_DETAILS const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<LPA_ENTERPRISE_PROFILE_DETAILS const *,void *>>>(void)
0x1800c6f39  lea     rcx, [rsp+150h+var_F0]
0x1800c6f3e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x1800c6f43  mov     rbx, [rsp+150h+var_F0]
0x1800c6f48  jmp     loc_1800C6E85
0x1800c6f4d  lea     rcx, aListTooLong; "list too long"
0x1800c6f54  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800c6f5b  lea     rcx, [rbp+50h+var_B8]
0x1800c6f5f  call    ??0?$list@PEBULPA_PROFILE_DETAILS@@V?$allocator@PEBULPA_PROFILE_DETAILS@@@std@@@std@@QEAA@XZ; std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(void)
0x1800c6f64  nop
0x1800c6f65  mov     rcx, [rsi+68h]
0x1800c6f69  mov     rax, [rcx]
0x1800c6f6c  lea     r8, [rbp+50h+var_B8]
0x1800c6f70  mov     rdx, r14
0x1800c6f73  mov     rax, [rax+50h]
0x1800c6f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6f7c  test    eax, eax
0x1800c6f7e  js      loc_1800C7083
0x1800c6f84  xor     eax, eax
0x1800c6f86  mov     [rbp+50h+var_70], ax
0x1800c6f8a  xor     edx, edx; Val
0x1800c6f8c  lea     r8d, [rax+40h]; Size
0x1800c6f90  lea     rcx, [rbp+50h+var_70+2]; void *
0x1800c6f94  call    memset_0
0x1800c6f99  lea     rdx, [rbp+50h+var_70]; unsigned __int16 (*)[33]
0x1800c6f9d  mov     rcx, r14; this
0x1800c6fa0  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x1800c6fa5  mov     rdi, [rbp+50h+var_B8]
0x1800c6fa9  mov     rbx, [rdi]
0x1800c6fac  cmp     rbx, rdi
0x1800c6faf  jz      loc_1800C7083
0x1800c6fb5  mov     r9, [rbx+10h]
0x1800c6fb9  mov     edx, 0Ah
0x1800c6fbe  mov     r8d, 28Ch
0x1800c6fc4  lea     rcx, [rsp+150h+var_E8]
0x1800c6fc9  call    ?BroadcastHelper@Lui@LPA@@CAXAEBV?$list@PEAXV?$allocator@PEAX@std@@@std@@W4LPALUIMSGTYPE@@KPEBX@Z; LPA::Lui::BroadcastHelper(std::list<void *> const &,LPALUIMSGTYPE,ulong,void const *)
0x1800c6fce  mov     eax, cs:CallbackContext
0x1800c6fd4  cmp     eax, 4
0x1800c6fd7  jbe     loc_1800C707B
0x1800c6fdd  mov     rcx, [rbx+10h]
0x1800c6fe1  lea     rax, [rcx+4Eh]
0x1800c6fe5  mov     [rbp+50h+var_A8], rax
0x1800c6fe9  mov     eax, [rcx+258h]
0x1800c6fef  mov     [rsp+150h+var_D8], eax
0x1800c6ff3  mov     eax, [rcx+8]
0x1800c6ff6  mov     [rsp+150h+var_D4], eax
0x1800c6ffa  mov     eax, [rcx+4]
0x1800c6ffd  mov     dword ptr [rbp+50h+var_D0], eax
0x1800c7000  mov     eax, [rcx]
0x1800c7002  mov     dword ptr [rsp+150h+var_F0], eax
0x1800c7006  lea     rax, [rbp+50h+var_70]
0x1800c700a  mov     [rbp+50h+var_A0], rax
0x1800c700e  lea     rax, aLpaLuiOnenterp; "LPA::Lui::OnEnterpriseManagerDownloadSe"...
0x1800c7015  mov     [rbp+50h+var_98], rax
0x1800c7019  lea     rax, aLpaservicelui; "LpaServiceLui"
0x1800c7020  mov     [rbp+50h+var_C8], rax
0x1800c7024  lea     rax, [rbp+50h+var_A8]
0x1800c7028  mov     [rsp+150h+var_F8], rax
0x1800c702d  lea     rax, [rsp+150h+var_D8]
0x1800c7032  mov     [rsp+150h+var_100], rax
0x1800c7037  lea     rax, [rsp+150h+var_D4]
0x1800c703c  mov     [rsp+150h+var_108], rax
0x1800c7041  lea     rax, [rbp+50h+var_D0]
0x1800c7045  mov     [rsp+150h+var_110], rax
0x1800c704a  lea     rax, [rsp+150h+var_F0]
0x1800c704f  mov     [rsp+150h+var_118], rax
0x1800c7054  lea     rax, [rbp+50h+var_A0]
0x1800c7058  mov     [rsp+150h+var_120], rax
0x1800c705d  lea     rax, [rbp+50h+var_98]
0x1800c7061  mov     [rsp+150h+var_128], rax
0x1800c7066  lea     rax, [rbp+50h+var_C8]
0x1800c706a  mov     [rsp+150h+var_130], rax
0x1800c706f  lea     rdx, word_180132656
0x1800c7076  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800c707b  mov     rbx, [rbx]
0x1800c707e  jmp     loc_1800C6FAC
0x1800c7083  mov     rcx, [rbp+50h+var_B8]
0x1800c7087  mov     rax, [rcx+8]
0x1800c708b  mov     qword ptr [rax], 0
0x1800c7092  mov     rdi, [rcx]
0x1800c7095  mov     esi, 18h
0x1800c709a  test    rdi, rdi
0x1800c709d  jz      short loc_1800C70BE
0x1800c709f  mov     rbx, [rdi]
0x1800c70a2  lea     rcx, [rdi+10h]
0x1800c70a6  call    ??1?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(void)
0x1800c70ab  mov     rdx, rsi
0x1800c70ae  mov     rcx, rdi
0x1800c70b1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c70b6  mov     rdi, rbx
0x1800c70b9  test    rbx, rbx
0x1800c70bc  jnz     short loc_1800C709F
0x1800c70be  mov     rdx, rsi
0x1800c70c1  mov     rcx, [rbp+50h+var_B8]
0x1800c70c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c70ca  nop
0x1800c70cb  mov     rcx, [rsp+150h+var_E8]
0x1800c70d0  mov     rax, [rcx+8]
0x1800c70d4  mov     qword ptr [rax], 0
0x1800c70db  mov     rcx, [rcx]
0x1800c70de  test    rcx, rcx
0x1800c70e1  jz      short loc_1800C70F6
0x1800c70e3  mov     rbx, [rcx]
0x1800c70e6  mov     rdx, rsi
0x1800c70e9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c70ee  mov     rcx, rbx
0x1800c70f1  test    rbx, rbx
0x1800c70f4  jnz     short loc_1800C70E3
0x1800c70f6  mov     rdx, rsi
0x1800c70f9  mov     rcx, [rsp+150h+var_E8]
0x1800c70fe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c7103  mov     rcx, [rbp+50h+var_20]
0x1800c7107  xor     rcx, rsp; StackCookie
0x1800c710a  call    __security_check_cookie
0x1800c710f  lea     r11, [rsp+150h+var_10]
0x1800c7117  mov     rbx, [r11+30h]
0x1800c711b  mov     rsi, [r11+38h]
0x1800c711f  mov     rsp, r11
0x1800c7122  pop     r14
0x1800c7124  pop     rdi
0x1800c7125  pop     rbp
0x1800c7126  retn
```
