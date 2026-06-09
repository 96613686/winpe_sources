# Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(_PNP_OBJECT_TYPE,SERVICE_STATUS_HANDLE__ *,Windows::Devices::Pnp::Internal::PnpObjectStore * *)

- ea: `0x180036b18`
- end: `0x180036dfb`
- name: `?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJW4_PNP_OBJECT_TYPE@@PEAUSERVICE_STATUS_HANDLE__@@PEAPEAVPnpObjectStore@2345@@Z`
- size: `739`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x180004ac0`
- `0x180042f44`

## callees

- `0x18001dfe0`
- `0x180021058`
- `0x1800290c4`
- `0x18002a948`
- `0x18003573c`
- `0x180036b18`
- `0x180036e04`
- `0x18003bc80`
- `0x180042bc8`
- `0x180049834`
- `0x1800618b4`
- `0x180064e38`
- `0x180064ff0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036bcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036bea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036bcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036bea`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180036dab`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180036dab`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180036cf6`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180036cf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=2
__int64 __fastcall Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rbx
  _QWORD *v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebx
  unsigned int ServiceRegistryStateKey; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // r8
  int Store; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // [rsp+20h] [rbp-D8h]
  unsigned int v28; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C0h] BYREF
  __int64 i; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-98h]
  _BYTE v34[32]; // [rsp+70h] [rbp-88h] BYREF
  __int64 v35; // [rsp+90h] [rbp-68h]
  _QWORD v36[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v37; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v28 = a2;
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\pnpobjectstore\\pnpobjectstoremanager.cpp",
      (const char *)0x80004003LL,
      v27);
    return 2147500035LL;
  }
  if ( a2 == 8 )
    return 2147943568LL;
  wil::AcquireSRWLockShared(&SRWLock, (RTL_SRWLOCK *)a1);
  v9 = **(_QWORD **)(a1 + 8);
  for ( i = v9; ; v9 = i )
  {
    if ( !*(_BYTE *)(v9 + 25) )
    {
      v10 = *(_QWORD *)(v9 + 40);
      if ( *(_DWORD *)(v10 + 40) != a2 )
        goto LABEL_31;
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v9 + 40)) > 1 )
      {
        *a4 = v10;
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        return 0;
      }
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 8));
    }
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    std::wstring::wstring(v34);
    std::wstring::wstring(v36);
    std::_Tree<std::_Tmap_traits<enum _PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::_STORE_CONFIG,std::less<enum _PNP_OBJECT_TYPE>,std::allocator<std::pair<enum _PNP_OBJECT_TYPE const,Windows::Devices::Pnp::Internal::_STORE_CONFIG>>,0>>::_Find_lower_bound<enum _PNP_OBJECT_TYPE>(
      v11,
      &v32,
      &v28);
    if ( !*(_BYTE *)(v33 + 25) && (signed int)a2 >= *(_DWORD *)(v33 + 32) )
      break;
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_31:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,Windows::Devices::Pnp::Internal::PnpObjectStore *>>>,std::_Iterator_base0>::operator++(&i);
  }
  v12 = v33 + 40;
  std::wstring::operator=(v34, v33 + 40);
  v35 = *(_QWORD *)(v12 + 32);
  std::wstring::operator=(v36, v12 + 40);
  if ( v35 == 3221225473LL )
  {
    v29 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v29,
      0);
    ServiceRegistryStateKey = GetServiceRegistryStateKey(a3, 1, 0x2000000, &v29);
    if ( ServiceRegistryStateKey )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\pnpobjectstore\\pnpobjectstoremanager.cpp",
              (const char *)ServiceRegistryStateKey,
              v27);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
      Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(
        (Windows::Devices::Pnp::Internal::_STORE_CONFIG *)v34,
        v20,
        v21);
      return v19;
    }
    else
    {
      v22 = v36;
      if ( v37 > 7 )
        v22 = (_QWORD *)v36[0];
      Store = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(a1, v29, v22, a2);
      v24 = Store;
      if ( Store < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA3,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\pnpobjectstore\\pnpobjectstoremanager.cpp",
          (const char *)(unsigned int)Store,
          (int)a4);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
      Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(
        (Windows::Devices::Pnp::Internal::_STORE_CONFIG *)v34,
        v25,
        v26);
      return v24;
    }
  }
  else
  {
    v13 = v36;
    if ( v37 > 7 )
      v13 = (_QWORD *)v36[0];
    v14 = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(a1, v35, v13, a2);
    v17 = v14;
    if ( v14 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\pnpobjectstore\\pnpobjectstoremanager.cpp",
        (const char *)(unsigned int)v14,
        (int)a4);
    Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(
      (Windows::Devices::Pnp::Internal::_STORE_CONFIG *)v34,
      v15,
      v16);
    return v17;
  }
}

```

## disassembly

```asm
0x180036b18  push    rbx
0x180036b1a  push    rsi
0x180036b1b  push    rdi
0x180036b1c  push    r14
0x180036b1e  push    r15
0x180036b20  sub     rsp, 0D0h
0x180036b27  mov     rax, cs:__security_cookie
0x180036b2e  xor     rax, rsp
0x180036b31  mov     [rsp+0F8h+var_38], rax
0x180036b39  mov     rsi, r9
0x180036b3c  mov     r15, r8
0x180036b3f  mov     edi, edx
0x180036b41  mov     r14, rcx
0x180036b44  mov     [rsp+0F8h+var_C8], edx
0x180036b48  test    r9, r9
0x180036b4b  jnz     short loc_180036B73
0x180036b4d  mov     rcx, [rsp+0F8h]; this
0x180036b55  mov     ebx, 80004003h
0x180036b5a  mov     r9d, ebx; char *
0x180036b5d  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x180036b64  lea     edx, [rsi+6Eh]; void *
0x180036b67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b6c  mov     eax, ebx
0x180036b6e  jmp     loc_180036DDB
0x180036b73  cmp     edi, 8
0x180036b76  jnz     short loc_180036B82
0x180036b78  mov     eax, 80070490h
0x180036b7d  jmp     loc_180036DDB
0x180036b82  mov     rdx, r14
0x180036b85  lea     rcx, [rsp+0F8h+SRWLock]
0x180036b8a  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180036b8f  mov     rax, [r14+8]
0x180036b93  mov     rax, [rax]
0x180036b96  mov     [rsp+0F8h+var_B8], rax
0x180036b9b  cmp     byte ptr [rax+19h], 0
0x180036b9f  jnz     short loc_180036BE0
0x180036ba1  mov     rbx, [rax+28h]
0x180036ba5  cmp     [rbx+28h], edi
0x180036ba8  jnz     loc_180036DB2
0x180036bae  mov     rax, [rbx]
0x180036bb1  mov     rcx, rbx
0x180036bb4  mov     rax, [rax+8]
0x180036bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bbd  cmp     eax, 1
0x180036bc0  jbe     short loc_180036BDC
0x180036bc2  mov     [rsi], rbx
0x180036bc5  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180036bca  test    rcx, rcx
0x180036bcd  jz      short loc_180036BD5
0x180036bcf  call    cs:__imp_ReleaseSRWLockShared
0x180036bd5  xor     eax, eax
0x180036bd7  jmp     loc_180036DDB
0x180036bdc  lock dec dword ptr [rbx+8]
0x180036be0  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180036be5  test    rcx, rcx
0x180036be8  jz      short loc_180036BF0
0x180036bea  call    cs:__imp_ReleaseSRWLockShared
0x180036bf0  lea     rcx, [rsp+0F8h+var_88]
0x180036bf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036bfa  lea     rcx, [rsp+0F8h+var_60]
0x180036c02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036c07  nop
0x180036c08  lea     r8, [rsp+0F8h+var_C8]
0x180036c0d  lea     rdx, [rsp+0F8h+var_A8]
0x180036c12  call    ??$_Find_lower_bound@W4_PNP_OBJECT_TYPE@@@?$_Tree@V?$_Tmap_traits@W4_PNP_OBJECT_TYPE@@U_STORE_CONFIG@Internal@Pnp@Devices@Windows@@U?$less@W4_PNP_OBJECT_TYPE@@@std@@V?$allocator@U?$pair@$$CBW4_PNP_OBJECT_TYPE@@U_STORE_CONFIG@Internal@Pnp@Devices@Windows@@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4_PNP_OBJECT_TYPE@@U_STORE_CONFIG@Internal@Pnp@Devices@Windows@@@std@@PEAX@std@@@1@AEBW4_PNP_OBJECT_TYPE@@@Z; std::_Tree<std::_Tmap_traits<_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::_STORE_CONFIG,std::less<_PNP_OBJECT_TYPE>,std::allocator<std::pair<_PNP_OBJECT_TYPE const,Windows::Devices::Pnp::Internal::_STORE_CONFIG>>,0>>::_Find_lower_bound<_PNP_OBJECT_TYPE>(_PNP_OBJECT_TYPE const &)
0x180036c17  mov     rdx, [rsp+0F8h+var_98]
0x180036c1c  cmp     byte ptr [rdx+19h], 0
0x180036c20  jnz     loc_180036DA4
0x180036c26  cmp     edi, [rdx+20h]
0x180036c29  jl      loc_180036DA4
0x180036c2f  lea     rbx, [rdx+28h]
0x180036c33  mov     rdx, rbx
0x180036c36  lea     rcx, [rsp+0F8h+var_88]
0x180036c3b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036c40  mov     rax, [rbx+20h]
0x180036c44  mov     [rsp+0F8h+var_68], rax
0x180036c4c  lea     rdx, [rbx+28h]
0x180036c50  lea     rcx, [rsp+0F8h+var_60]
0x180036c58  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036c5d  nop
0x180036c5e  mov     eax, 0C0000001h
0x180036c63  mov     rdx, [rsp+0F8h+var_68]
0x180036c6b  cmp     rdx, rax
0x180036c6e  jz      short loc_180036CCE
0x180036c70  lea     r8, [rsp+0F8h+var_60]
0x180036c78  cmp     [rsp+0F8h+var_48], 7
0x180036c81  cmova   r8, [rsp+0F8h+var_60]
0x180036c8a  mov     qword ptr [rsp+0F8h+var_D8], rsi; int
0x180036c8f  mov     r9d, edi
0x180036c92  mov     rcx, r14
0x180036c95  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180036c9a  mov     ebx, eax
0x180036c9c  test    eax, eax
0x180036c9e  jns     short loc_180036CBD
0x180036ca0  mov     rcx, [rsp+0F8h]; this
0x180036ca8  mov     r9d, eax; char *
0x180036cab  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x180036cb2  mov     edx, 99h; void *
0x180036cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036cbc  nop
0x180036cbd  lea     rcx, [rsp+0F8h+var_88]; this
0x180036cc2  call    ??1_STORE_CONFIG@Internal@Pnp@Devices@Windows@@QEAA@XZ; Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(void)
0x180036cc7  mov     eax, ebx
0x180036cc9  jmp     loc_180036DDB
0x180036cce  mov     [rsp+0F8h+var_C0], 0
0x180036cd7  xor     edx, edx
0x180036cd9  lea     rcx, [rsp+0F8h+var_C0]
0x180036cde  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180036ce3  lea     r9, [rsp+0F8h+var_C0]
0x180036ce8  mov     edx, 1
0x180036ced  mov     r8d, 2000000h
0x180036cf3  mov     rcx, r15
0x180036cf6  call    cs:__imp_GetServiceRegistryStateKey
0x180036cfc  test    eax, eax
0x180036cfe  jz      short loc_180036D3A
0x180036d00  mov     rcx, [rsp+0F8h]; this
0x180036d08  mov     r9d, eax; char *
0x180036d0b  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x180036d12  mov     edx, 0A1h; void *
0x180036d17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036d1c  mov     ebx, eax
0x180036d1e  lea     rcx, [rsp+0F8h+var_C0]
0x180036d23  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036d28  nop
0x180036d29  lea     rcx, [rsp+0F8h+var_88]; this
0x180036d2e  call    ??1_STORE_CONFIG@Internal@Pnp@Devices@Windows@@QEAA@XZ; Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(void)
0x180036d33  mov     eax, ebx
0x180036d35  jmp     loc_180036DDB
0x180036d3a  lea     r8, [rsp+0F8h+var_60]
0x180036d42  cmp     [rsp+0F8h+var_48], 7
0x180036d4b  cmova   r8, [rsp+0F8h+var_60]
0x180036d54  mov     qword ptr [rsp+0F8h+var_D8], rsi; int
0x180036d59  mov     r9d, edi
0x180036d5c  mov     rdx, [rsp+0F8h+var_C0]
0x180036d61  mov     rcx, r14
0x180036d64  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180036d69  mov     ebx, eax
0x180036d6b  test    eax, eax
0x180036d6d  jns     short loc_180036D8B
0x180036d6f  mov     rcx, [rsp+0F8h]; this
0x180036d77  mov     r9d, eax; char *
0x180036d7a  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x180036d81  mov     edx, 0A3h; void *
0x180036d86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d8b  lea     rcx, [rsp+0F8h+var_C0]
0x180036d90  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036d95  nop
0x180036d96  lea     rcx, [rsp+0F8h+var_88]; this
0x180036d9b  call    ??1_STORE_CONFIG@Internal@Pnp@Devices@Windows@@QEAA@XZ; Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(void)
0x180036da0  mov     eax, ebx
0x180036da2  jmp     short loc_180036DDB
0x180036da4  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180036dab  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180036db1  nop
0x180036db2  lea     rcx, [rsp+0F8h+var_B8]
0x180036db7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXPEAVPnpObjectStore@Internal@Pnp@Devices@Windows@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,Windows::Devices::Pnp::Internal::PnpObjectStore *>>>,std::_Iterator_base0>::operator++(void)
0x180036dbc  mov     rax, [rsp+0F8h+var_B8]
0x180036dc1  jmp     loc_180036B9B
0x180036dc6  lea     rcx, [rsp+0F8h+var_88]; this
0x180036dcb  call    ??1_STORE_CONFIG@Internal@Pnp@Devices@Windows@@QEAA@XZ; Windows::Devices::Pnp::Internal::_STORE_CONFIG::~_STORE_CONFIG(void)
0x180036dd0  mov     eax, 80070490h
0x180036dd5  jmp     short loc_180036DDB
0x180036dd7  mov     eax, [rsp+0F8h+var_C8]
0x180036ddb  mov     rcx, [rsp+0F8h+var_38]
0x180036de3  xor     rcx, rsp; StackCookie
0x180036de6  call    __security_check_cookie
0x180036deb  add     rsp, 0D0h
0x180036df2  pop     r15
0x180036df4  pop     r14
0x180036df6  pop     rdi
0x180036df7  pop     rsi
0x180036df8  pop     rbx
0x180036df9  retn
```
