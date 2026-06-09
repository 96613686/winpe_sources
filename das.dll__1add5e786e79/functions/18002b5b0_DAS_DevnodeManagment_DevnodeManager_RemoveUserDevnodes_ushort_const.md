# DAS::DevnodeManagment::DevnodeManager::RemoveUserDevnodes(ushort const *)

- ea: `0x18002b5b0`
- end: `0x18002b900`
- name: `?RemoveUserDevnodes@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG@Z`
- size: `848`
- prototype: `__int64 __fastcall(DAS::DevnodeManagment::DevnodeManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027a38`

## callees

- `0x1800074c0`
- `0x180018ef8`
- `0x180019548`
- `0x180019adc`
- `0x180019b54`
- `0x18001a350`
- `0x18001dfe0`
- `0x18001eae0`
- `0x18002a948`
- `0x18002b5b0`
- `0x18002d764`
- `0x180033f14`
- `0x18003bc80`
- `0x18004dc64`
- `0x18004dea4`
- `0x18004ecc0`
- `0x18005e7c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b73e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b73e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b619`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b6dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b729`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b7af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b86a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b8cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b619`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b6dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b729`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b7af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b86a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b8cd`

## string_xrefs

- `0x18002b5fd`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18002b6aa`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18002b808`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::RemoveUserDevnodes(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2)
{
  __int64 v5; // rdx
  unsigned __int16 **v6; // rcx
  int ServiceIdFromAepServiceId; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  void *v13; // rcx
  char *v14; // rbx
  __int64 v15; // rdx
  char *v16; // r14
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  unsigned int v19; // esi
  char *v20; // [rsp+20h] [rbp-88h] BYREF
  __int128 v21; // [rsp+28h] [rbp-80h]
  void *v22; // [rsp+38h] [rbp-70h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-68h] BYREF
  __int64 v24; // [rsp+48h] [rbp-60h] BYREF
  PSRWLOCK v25; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int16 *v26[3]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  wil::AcquireSRWLockShared(&SRWLock, this + 1);
  if ( LOBYTE(this[2].Ptr) )
  {
    std::vector<std::wstring>::vector<std::wstring>(&v20);
    wil::AcquireSRWLockShared(&v25, this + 4);
    v5 = *(_QWORD *)this[5].Ptr;
    v24 = v5;
    while ( !*(_BYTE *)(v5 + 25) )
    {
      std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
        (__int64)v26,
        v5 + 32);
      v22 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v22,
        0);
      v6 = v26;
      if ( v27 > 7 )
        v6 = (unsigned __int16 **)v26[0];
      ServiceIdFromAepServiceId = DafGetServiceIdFromAepServiceId(v6, &v22);
      v8 = ServiceIdFromAepServiceId;
      if ( ServiceIdFromAepServiceId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B3,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)(unsigned int)ServiceIdFromAepServiceId,
          (int)v20);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
        std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
          (__int64)v26,
          v9,
          v10);
        if ( v25 )
          ReleaseSRWLockShared(v25);
        if ( v20 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v20, v21);
          std::_Deallocate<16>(v20, (*((_QWORD *)&v21 + 1) - (_QWORD)v20) & 0xFFFFFFFFFFFFFFE0uLL);
          v20 = 0;
          v21 = 0;
        }
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        return v8;
      }
      if ( !(unsigned int)_o__wcsicmp(v22, a2) )
      {
        if ( (_QWORD)v21 == *((_QWORD *)&v21 + 1) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v20, v21, v26);
        }
        else
        {
          std::wstring::wstring(v21, v26);
          *(_QWORD *)&v21 = v21 + 32;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
      std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
        (__int64)v26,
        v11,
        v12);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(&v24);
      v5 = v24;
    }
    if ( v25 )
      ReleaseSRWLockShared(v25);
    v13 = v20;
    v14 = v20;
    v15 = v21;
    v16 = (char *)v21;
    while ( v14 != v16 )
    {
      std::wstring::wstring(v26, v14);
      v17 = (const unsigned __int16 *)v26;
      if ( v27 > 7 )
        v17 = v26[0];
      v18 = DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(
              (DAS::DevnodeManagment::DevnodeManager *)this,
              v17,
              0);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)(unsigned int)v18,
          (int)v20);
        std::wstring::_Tidy_deallocate((__int64)v26);
        if ( v20 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v20, v21);
          std::_Deallocate<16>(v20, (*((_QWORD *)&v21 + 1) - (_QWORD)v20) & 0xFFFFFFFFFFFFFFE0uLL);
          v20 = 0;
          v21 = 0;
        }
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        return v19;
      }
      std::wstring::_Tidy_deallocate((__int64)v26);
      v14 += 32;
      v15 = v21;
      v13 = v20;
    }
    if ( v13 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v13, v15);
      std::_Deallocate<16>(v20, (*((_QWORD *)&v21 + 1) - (_QWORD)v20) & 0xFFFFFFFFFFFFFFE0uLL);
      v20 = 0;
      v21 = 0;
    }
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)0x80640013LL,
      (int)v20);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return 2154037267LL;
  }
}

```

## disassembly

```asm
0x18002b5b0  mov     [rsp+arg_10], rbx
0x18002b5b5  push    rsi
0x18002b5b6  push    rdi
0x18002b5b7  push    r14
0x18002b5b9  sub     rsp, 90h
0x18002b5c0  mov     rax, cs:__security_cookie
0x18002b5c7  xor     rax, rsp
0x18002b5ca  mov     [rsp+0A8h+var_28], rax
0x18002b5d2  mov     rsi, rdx
0x18002b5d5  mov     rdi, rcx
0x18002b5d8  lea     rdx, [rcx+8]
0x18002b5dc  lea     rcx, [rsp+0A8h+SRWLock]
0x18002b5e1  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b5e6  nop
0x18002b5e7  cmp     byte ptr [rdi+10h], 0
0x18002b5eb  jnz     short loc_18002B626
0x18002b5ed  mov     rcx, [rsp+0A8h]; this
0x18002b5f5  mov     ebx, 80640013h
0x18002b5fa  mov     r9d, ebx; char *
0x18002b5fd  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b604  mov     edx, 1A9h; void *
0x18002b609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b60e  nop
0x18002b60f  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18002b614  test    rcx, rcx
0x18002b617  jz      short loc_18002B61F
0x18002b619  call    cs:__imp_ReleaseSRWLockShared
0x18002b61f  mov     eax, ebx
0x18002b621  jmp     loc_18002B8DB
0x18002b626  lea     rcx, [rsp+0A8h+var_88]
0x18002b62b  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18002b630  nop
0x18002b631  lea     rdx, [rdi+20h]
0x18002b635  lea     rcx, [rsp+0A8h+var_58]
0x18002b63a  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b63f  nop
0x18002b640  mov     rdx, [rdi+28h]
0x18002b644  mov     rdx, [rdx]
0x18002b647  mov     [rsp+0A8h+var_60], rdx
0x18002b64c  cmp     byte ptr [rdx+19h], 0
0x18002b650  jnz     loc_18002B7A5
0x18002b656  add     rdx, 20h ; ' '
0x18002b65a  lea     rcx, [rsp+0A8h+var_50]
0x18002b65f  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>> const &)
0x18002b664  nop
0x18002b665  mov     [rsp+0A8h+var_70], 0
0x18002b66e  xor     edx, edx
0x18002b670  lea     rcx, [rsp+0A8h+var_70]
0x18002b675  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b67a  lea     rcx, [rsp+0A8h+var_50]
0x18002b67f  cmp     [rsp+0A8h+var_38], 7
0x18002b685  cmova   rcx, [rsp+0A8h+var_50]
0x18002b68b  lea     rdx, [rsp+0A8h+var_70]
0x18002b690  call    DafGetServiceIdFromAepServiceId
0x18002b695  mov     ebx, eax
0x18002b697  test    eax, eax
0x18002b699  jns     loc_18002B736
0x18002b69f  mov     rcx, [rsp+0A8h]; this
0x18002b6a7  mov     r9d, eax; char *
0x18002b6aa  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b6b1  mov     edx, 1B3h; void *
0x18002b6b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6bb  nop
0x18002b6bc  lea     rcx, [rsp+0A8h+var_70]
0x18002b6c1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b6c6  nop
0x18002b6c7  lea     rcx, [rsp+0A8h+var_50]
0x18002b6cc  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(void)
0x18002b6d1  nop
0x18002b6d2  mov     rcx, [rsp+0A8h+var_58]; SRWLock
0x18002b6d7  test    rcx, rcx
0x18002b6da  jz      short loc_18002B6E3
0x18002b6dc  call    cs:__imp_ReleaseSRWLockShared
0x18002b6e2  nop
0x18002b6e3  mov     rcx, [rsp+0A8h+var_88]
0x18002b6e8  test    rcx, rcx
0x18002b6eb  jz      short loc_18002B71F
0x18002b6ed  mov     rdx, qword ptr [rsp+0A8h+var_80]
0x18002b6f2  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b6f7  mov     rcx, [rsp+0A8h+var_88]
0x18002b6fc  mov     rdx, qword ptr [rsp+0A8h+var_80+8]
0x18002b701  sub     rdx, rcx
0x18002b704  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b708  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b70d  mov     [rsp+0A8h+var_88], 0
0x18002b716  xorps   xmm0, xmm0
0x18002b719  movdqu  [rsp+0A8h+var_80], xmm0
0x18002b71f  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18002b724  test    rcx, rcx
0x18002b727  jz      short loc_18002B72F
0x18002b729  call    cs:__imp_ReleaseSRWLockShared
0x18002b72f  mov     eax, ebx
0x18002b731  jmp     loc_18002B8DB
0x18002b736  mov     rdx, rsi
0x18002b739  mov     rcx, [rsp+0A8h+var_70]
0x18002b73e  call    cs:__imp__o__wcsicmp
0x18002b744  test    eax, eax
0x18002b746  jnz     short loc_18002B77C
0x18002b748  mov     rax, qword ptr [rsp+0A8h+var_80]
0x18002b74d  cmp     rax, qword ptr [rsp+0A8h+var_80+8]
0x18002b752  jz      short loc_18002B769
0x18002b754  lea     rdx, [rsp+0A8h+var_50]
0x18002b759  mov     rcx, rax
0x18002b75c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b761  add     qword ptr [rsp+0A8h+var_80], 20h ; ' '
0x18002b767  jmp     short loc_18002B77C
0x18002b769  lea     r8, [rsp+0A8h+var_50]
0x18002b76e  mov     rdx, rax
0x18002b771  lea     rcx, [rsp+0A8h+var_88]
0x18002b776  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002b77b  nop
0x18002b77c  lea     rcx, [rsp+0A8h+var_70]
0x18002b781  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b786  nop
0x18002b787  lea     rcx, [rsp+0A8h+var_50]
0x18002b78c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(void)
0x18002b791  lea     rcx, [rsp+0A8h+var_60]
0x18002b796  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(void)
0x18002b79b  mov     rdx, [rsp+0A8h+var_60]
0x18002b7a0  jmp     loc_18002B64C
0x18002b7a5  mov     rcx, [rsp+0A8h+var_58]; SRWLock
0x18002b7aa  test    rcx, rcx
0x18002b7ad  jz      short loc_18002B7B5
0x18002b7af  call    cs:__imp_ReleaseSRWLockShared
0x18002b7b5  mov     rcx, [rsp+0A8h+var_88]
0x18002b7ba  mov     rbx, rcx
0x18002b7bd  mov     rdx, qword ptr [rsp+0A8h+var_80]
0x18002b7c2  mov     r14, rdx
0x18002b7c5  cmp     rbx, r14
0x18002b7c8  jz      loc_18002B891
0x18002b7ce  mov     rdx, rbx
0x18002b7d1  lea     rcx, [rsp+0A8h+var_50]
0x18002b7d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b7db  lea     rdx, [rsp+0A8h+var_50]
0x18002b7e0  cmp     [rsp+0A8h+var_38], 7
0x18002b7e6  cmova   rdx, [rsp+0A8h+var_50]; unsigned __int16 *
0x18002b7ec  xor     r8d, r8d; unsigned __int16 *
0x18002b7ef  mov     rcx, rdi; this
0x18002b7f2  call    ?StopDevnodeManagement@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(ushort const *,ushort const *)
0x18002b7f7  mov     esi, eax
0x18002b7f9  test    eax, eax
0x18002b7fb  jns     short loc_18002B874
0x18002b7fd  mov     rcx, [rsp+0A8h]; this
0x18002b805  mov     r9d, eax; char *
0x18002b808  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b80f  mov     edx, 1BEh; void *
0x18002b814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b819  lea     rcx, [rsp+0A8h+var_50]
0x18002b81e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b823  nop
0x18002b824  mov     rcx, [rsp+0A8h+var_88]
0x18002b829  test    rcx, rcx
0x18002b82c  jz      short loc_18002B860
0x18002b82e  mov     rdx, qword ptr [rsp+0A8h+var_80]
0x18002b833  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b838  mov     rcx, [rsp+0A8h+var_88]
0x18002b83d  mov     rdx, qword ptr [rsp+0A8h+var_80+8]
0x18002b842  sub     rdx, rcx
0x18002b845  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b849  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b84e  mov     [rsp+0A8h+var_88], 0
0x18002b857  xorps   xmm0, xmm0
0x18002b85a  movdqu  [rsp+0A8h+var_80], xmm0
0x18002b860  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18002b865  test    rcx, rcx
0x18002b868  jz      short loc_18002B870
0x18002b86a  call    cs:__imp_ReleaseSRWLockShared
0x18002b870  mov     eax, esi
0x18002b872  jmp     short loc_18002B8DB
0x18002b874  lea     rcx, [rsp+0A8h+var_50]
0x18002b879  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b87e  add     rbx, 20h ; ' '
0x18002b882  mov     rdx, qword ptr [rsp+0A8h+var_80]
0x18002b887  mov     rcx, [rsp+0A8h+var_88]
0x18002b88c  jmp     loc_18002B7C5
0x18002b891  test    rcx, rcx
0x18002b894  jz      short loc_18002B8C3
0x18002b896  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b89b  mov     rcx, [rsp+0A8h+var_88]
0x18002b8a0  mov     rdx, qword ptr [rsp+0A8h+var_80+8]
0x18002b8a5  sub     rdx, rcx
0x18002b8a8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b8ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b8b1  mov     [rsp+0A8h+var_88], 0
0x18002b8ba  xorps   xmm0, xmm0
0x18002b8bd  movdqu  [rsp+0A8h+var_80], xmm0
0x18002b8c3  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18002b8c8  test    rcx, rcx
0x18002b8cb  jz      short loc_18002B8D3
0x18002b8cd  call    cs:__imp_ReleaseSRWLockShared
0x18002b8d3  xor     eax, eax
0x18002b8d5  jmp     short loc_18002B8DB
0x18002b8d7  mov     eax, dword ptr [rsp+0A8h+var_70]
0x18002b8db  mov     rcx, [rsp+0A8h+var_28]
0x18002b8e3  xor     rcx, rsp; StackCookie
0x18002b8e6  call    __security_check_cookie
0x18002b8eb  mov     rbx, [rsp+0A8h+arg_10]
0x18002b8f3  add     rsp, 90h
0x18002b8fa  pop     r14
0x18002b8fc  pop     rdi
0x18002b8fd  pop     rsi
0x18002b8fe  retn
```
