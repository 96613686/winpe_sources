# AclSettings::ApplySettings(std::shared_ptr<VfpPort>)

- ea: `0x180097370`
- end: `0x180097b9f`
- name: `?ApplySettings@AclSettings@@UEAAXV?$shared_ptr@VVfpPort@@@std@@@Z`
- size: `2095`
- prototype: `__int64 __fastcall(AclSettings *this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18005f0c0`
- `0x180067c00`
- `0x18006c530`
- `0x180097208`
- `0x180097370`
- `0x180098338`
- `0x1800985a0`
- `0x180098808`
- `0x1800a1448`
- `0x1800a3530`
- `0x1800a5df4`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800973ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800973ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180097b32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180097b32`

## string_xrefs

- `0x180097499`: `ACL_ENDPOINT_GROUP_IPV4_IN`
- `0x1800975bb`: `ACL_ENDPOINT_GROUP_IPV6_IN`
- `0x1800973df`: `ACL_ENDPOINT_LAYER`
- `0x18009740a`: `ACL_ENDPOINT_LAYER`
- `0x1800976d8`: `ACL_NETWORK_GROUP_IPV4_IN`
- `0x1800977fa`: `ACL_NETWORK_GROUP_IPV6_IN`
- `0x18009752a`: `ACL_ENDPOINT_GROUP_IPV4_OUT`
- `0x18009764c`: `ACL_ENDPOINT_GROUP_IPV6_OUT`
- `0x1800978c7`: `ACL_SUBNET_LAYER`
- `0x180097b1a`: `ACL_SUBNET_LAYER`
- `0x18009794c`: `ACL_SUBNET_GROUP_IPV4_IN`
- `0x180097769`: `ACL_NETWORK_GROUP_IPV4_OUT`
- `0x18009788b`: `ACL_NETWORK_GROUP_IPV6_OUT`
- `0x180097aff`: `ACL_SUBNET_GROUP_IPV6_OUT`
- `0x180097a6e`: `ACL_SUBNET_GROUP_IPV6_IN`
- `0x1800979dd`: `ACL_SUBNET_GROUP_IPV4_OUT`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AclSettings::ApplySettings(RTL_SRWLOCK *this, __int64 a2)
{
  RTL_SRWLOCK *v4; // rsi
  RTL_SRWLOCK *v5; // r15
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  bool HasSubnetRules; // al
  VfpPort *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rdi
  __int64 v33[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v34; // [rsp+50h] [rbp-19h]
  RTL_SRWLOCK *v35; // [rsp+58h] [rbp-11h]
  __int128 v36; // [rsp+60h] [rbp-9h] BYREF
  __int128 v37; // [rsp+70h] [rbp+7h]

  v34 = a2;
  v4 = this + 2;
  AcquireSRWLockShared(this + 2);
  v35 = v4;
  if ( LOBYTE(this[1].Ptr) )
  {
    if ( AclSettings::HasEndpointRules((AclSettings *)this) || AclSettings::HasNetworkRules((AclSettings *)this) )
    {
      VfpPort::AddLayer(*(VfpPort **)a2, L"ACL_ENDPOINT_LAYER", L"ACL_ENDPOINT_LAYER", 1, 0xFu, 0);
      v5 = this + 24;
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"EP_V4_IN", 8u);
      v6 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
             &this[24],
             &v36);
      *(_OWORD *)v33 = 0;
      v7 = *(_QWORD *)(a2 + 8);
      if ( v7 )
        _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_ENDPOINT_GROUP_IPV4_IN", (__int64)v33, v6, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"EP_V4_OUT", 9u);
      v8 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
             &this[24],
             &v36);
      *(_OWORD *)v33 = 0;
      v9 = *(_QWORD *)(a2 + 8);
      if ( v9 )
        _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_ENDPOINT_GROUP_IPV4_OUT", (__int64)v33, v8, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"EP_V6_IN", 8u);
      v10 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v11 = *(_QWORD *)(a2 + 8);
      if ( v11 )
        _InterlockedAdd((volatile signed __int32 *)(v11 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_ENDPOINT_GROUP_IPV6_IN", (__int64)v33, v10, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"EP_V6_OUT", 9u);
      v12 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v13 = *(_QWORD *)(a2 + 8);
      if ( v13 )
        _InterlockedAdd((volatile signed __int32 *)(v13 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_ENDPOINT_GROUP_IPV6_OUT", (__int64)v33, v12, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"NW_V4_IN", 8u);
      v14 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v15 = *(_QWORD *)(a2 + 8);
      if ( v15 )
        _InterlockedAdd((volatile signed __int32 *)(v15 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_NETWORK_GROUP_IPV4_IN", (__int64)v33, v14, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"NW_V4_OUT", 9u);
      v16 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v17 = *(_QWORD *)(a2 + 8);
      if ( v17 )
        _InterlockedAdd((volatile signed __int32 *)(v17 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_NETWORK_GROUP_IPV4_OUT", (__int64)v33, v16, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"NW_V6_IN", 8u);
      v18 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v19 = *(_QWORD *)(a2 + 8);
      if ( v19 )
        _InterlockedAdd((volatile signed __int32 *)(v19 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_NETWORK_GROUP_IPV6_IN", (__int64)v33, v18, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"NW_V6_OUT", 9u);
      v20 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              &this[24],
              &v36);
      *(_OWORD *)v33 = 0;
      v21 = *(_QWORD *)(a2 + 8);
      if ( v21 )
        _InterlockedAdd((volatile signed __int32 *)(v21 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_ENDPOINT_LAYER", L"ACL_NETWORK_GROUP_IPV6_OUT", (__int64)v33, v20, 0);
      std::wstring::~wstring(&v36);
    }
    else
    {
      VfpPort::RemoveLayer(*(VfpPort **)a2, (char *)L"ACL_ENDPOINT_LAYER");
      v5 = this + 24;
    }
    HasSubnetRules = AclSettings::HasSubnetRules((AclSettings *)this);
    v23 = *(VfpPort **)a2;
    if ( HasSubnetRules )
    {
      VfpPort::AddLayer(v23, L"ACL_SUBNET_LAYER", L"ACL_SUBNET_LAYER", 1, 0x11u, 0);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"SN_V4_IN", 8u);
      v24 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              v5,
              &v36);
      *(_OWORD *)v33 = 0;
      v25 = *(_QWORD *)(a2 + 8);
      if ( v25 )
        _InterlockedAdd((volatile signed __int32 *)(v25 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_SUBNET_LAYER", L"ACL_SUBNET_GROUP_IPV4_IN", (__int64)v33, v24, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"SN_V4_OUT", 9u);
      v26 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              v5,
              &v36);
      *(_OWORD *)v33 = 0;
      v27 = *(_QWORD *)(a2 + 8);
      if ( v27 )
        _InterlockedAdd((volatile signed __int32 *)(v27 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_SUBNET_LAYER", L"ACL_SUBNET_GROUP_IPV4_OUT", (__int64)v33, v26, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"SN_V6_IN", 8u);
      v28 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              v5,
              &v36);
      *(_OWORD *)v33 = 0;
      v29 = *(_QWORD *)(a2 + 8);
      if ( v29 )
        _InterlockedAdd((volatile signed __int32 *)(v29 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_SUBNET_LAYER", L"ACL_SUBNET_GROUP_IPV6_IN", (__int64)v33, v28, 0);
      std::wstring::~wstring(&v36);
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"SN_V6_OUT", 9u);
      v30 = std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](
              v5,
              &v36);
      *(_OWORD *)v33 = 0;
      v31 = *(_QWORD *)(a2 + 8);
      if ( v31 )
        _InterlockedAdd((volatile signed __int32 *)(v31 + 8), 1u);
      v33[0] = *(_QWORD *)a2;
      v33[1] = *(_QWORD *)(a2 + 8);
      VFPSettings::ApplyLayerRules(L"ACL_SUBNET_LAYER", L"ACL_SUBNET_GROUP_IPV6_OUT", (__int64)v33, v30, 0);
      std::wstring::~wstring(&v36);
    }
    else
    {
      VfpPort::RemoveLayer(v23, (char *)L"ACL_SUBNET_LAYER");
    }
    LOBYTE(this[1].Ptr) = 0;
  }
  if ( v4 )
    ReleaseSRWLockShared(v4);
  v32 = *(volatile signed __int32 **)(a2 + 8);
  if ( v32 && _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
    if ( !_InterlockedDecrement(v32 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
  }
}

```

## disassembly

```asm
0x180097370  mov     [rsp-8+arg_10], rbx
0x180097375  push    rbp
0x180097376  push    rsi
0x180097377  push    rdi
0x180097378  push    r12
0x18009737a  push    r13
0x18009737c  push    r14
0x18009737e  push    r15
0x180097380  lea     rbp, [rsp-27h]
0x180097385  sub     rsp, 90h
0x18009738c  mov     rax, cs:__security_cookie
0x180097393  xor     rax, rsp
0x180097396  mov     [rbp+57h+var_40], rax
0x18009739a  mov     rbx, rdx
0x18009739d  mov     rdi, rcx
0x1800973a0  mov     [rbp+57h+var_70], rdx
0x1800973a4  lea     rsi, [rcx+10h]
0x1800973a8  mov     rcx, rsi; SRWLock
0x1800973ab  call    cs:__imp_AcquireSRWLockShared
0x1800973b1  mov     [rbp+57h+var_68], rsi
0x1800973b5  xor     r12d, r12d
0x1800973b8  cmp     [rdi+8], r12b
0x1800973bc  jz      loc_180097B2A
0x1800973c2  mov     rcx, rdi; this
0x1800973c5  call    ?HasEndpointRules@AclSettings@@AEBA_NXZ; AclSettings::HasEndpointRules(void)
0x1800973ca  lea     r13d, [r12+1]
0x1800973cf  test    al, al
0x1800973d1  jnz     short loc_1800973FA
0x1800973d3  mov     rcx, rdi; this
0x1800973d6  call    ?HasNetworkRules@AclSettings@@AEBA_NXZ; AclSettings::HasNetworkRules(void)
0x1800973db  test    al, al
0x1800973dd  jnz     short loc_1800973FA
0x1800973df  lea     rdx, aAclEndpointLay; "ACL_ENDPOINT_LAYER"
0x1800973e6  mov     rcx, [rbx]; this
0x1800973e9  call    ?RemoveLayer@VfpPort@@QEBA_NPEBG@Z; VfpPort::RemoveLayer(ushort const *)
0x1800973ee  lea     r15, [rdi+0C0h]
0x1800973f5  jmp     loc_1800978A4
0x1800973fa  mov     [rsp+0C0h+var_98], r12w; unsigned __int16
0x180097400  mov     [rsp+0C0h+var_A0], 0Fh; unsigned __int16
0x180097407  mov     r9b, r13b; bool
0x18009740a  lea     r14, aAclEndpointLay; "ACL_ENDPOINT_LAYER"
0x180097411  mov     r8, r14; unsigned __int16 *
0x180097414  mov     rdx, r14; unsigned __int16 *
0x180097417  mov     rcx, [rbx]; this
0x18009741a  call    ?AddLayer@VfpPort@@QEBA_NPEBG0_NGG@Z; VfpPort::AddLayer(ushort const *,ushort const *,bool,ushort,ushort)
0x18009741f  lea     r15, [rdi+0C0h]
0x180097426  xorps   xmm0, xmm0
0x180097429  movups  [rbp+57h+var_60], xmm0
0x18009742d  xorps   xmm1, xmm1
0x180097430  movdqu  [rbp+57h+var_50], xmm1
0x180097435  mov     r8d, 8
0x18009743b  lea     rdx, aEpV4In; "EP_V4_IN"
0x180097442  lea     rcx, [rbp+57h+var_60]
0x180097446  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009744b  nop
0x18009744c  lea     rdx, [rbp+57h+var_60]
0x180097450  mov     rcx, r15
0x180097453  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x180097458  mov     rdx, rax
0x18009745b  xorps   xmm0, xmm0
0x18009745e  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180097463  mov     rcx, [rbx+8]
0x180097467  test    rcx, rcx
0x18009746a  jz      short loc_180097471
0x18009746c  lock add [rcx+8], r13d
0x180097471  mov     rax, [rbx]
0x180097474  mov     [rbp+57h+var_80], rax
0x180097478  mov     rax, [rbx+8]
0x18009747c  mov     [rbp+57h+var_80+8], rax
0x180097480  mov     r9d, r13d
0x180097483  mov     [rsp+0C0h+var_90], r12b; char
0x180097488  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x18009748d  lea     rax, [rbp+57h+var_80]
0x180097491  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x180097496  mov     r8d, r13d
0x180097499  lea     rdx, aAclEndpointGro_0; "ACL_ENDPOINT_GROUP_IPV4_IN"
0x1800974a0  mov     rcx, r14; unsigned __int16 *
0x1800974a3  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x1800974a8  nop
0x1800974a9  lea     rcx, [rbp+57h+var_60]; void *
0x1800974ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800974b2  xorps   xmm0, xmm0
0x1800974b5  movups  [rbp+57h+var_60], xmm0
0x1800974b9  xorps   xmm1, xmm1
0x1800974bc  movdqu  [rbp+57h+var_50], xmm1
0x1800974c1  mov     r8d, 9
0x1800974c7  lea     rdx, aEpV4Out; "EP_V4_OUT"
0x1800974ce  lea     rcx, [rbp+57h+var_60]
0x1800974d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800974d7  nop
0x1800974d8  lea     rdx, [rbp+57h+var_60]
0x1800974dc  mov     rcx, r15
0x1800974df  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x1800974e4  mov     rdx, rax
0x1800974e7  xorps   xmm0, xmm0
0x1800974ea  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800974ef  mov     rcx, [rbx+8]
0x1800974f3  test    rcx, rcx
0x1800974f6  jz      short loc_1800974FD
0x1800974f8  lock add [rcx+8], r13d
0x1800974fd  mov     rcx, [rbx]
0x180097500  mov     [rbp+57h+var_80], rcx
0x180097504  mov     rax, [rbx+8]
0x180097508  mov     [rbp+57h+var_80+8], rax
0x18009750c  mov     ecx, 2
0x180097511  mov     r9d, ecx
0x180097514  mov     [rsp+0C0h+var_90], r12b; char
0x180097519  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x18009751e  lea     rax, [rbp+57h+var_80]
0x180097522  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x180097527  mov     r8d, ecx
0x18009752a  lea     rdx, aAclEndpointGro; "ACL_ENDPOINT_GROUP_IPV4_OUT"
0x180097531  mov     rcx, r14; unsigned __int16 *
0x180097534  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x180097539  nop
0x18009753a  lea     rcx, [rbp+57h+var_60]; void *
0x18009753e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180097543  xorps   xmm0, xmm0
0x180097546  movups  [rbp+57h+var_60], xmm0
0x18009754a  xorps   xmm1, xmm1
0x18009754d  movdqu  [rbp+57h+var_50], xmm1
0x180097552  mov     r8d, 8
0x180097558  lea     rdx, aEpV6In; "EP_V6_IN"
0x18009755f  lea     rcx, [rbp+57h+var_60]
0x180097563  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180097568  nop
0x180097569  lea     rdx, [rbp+57h+var_60]
0x18009756d  mov     rcx, r15
0x180097570  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x180097575  mov     rdx, rax
0x180097578  xorps   xmm0, xmm0
0x18009757b  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180097580  mov     rcx, [rbx+8]
0x180097584  test    rcx, rcx
0x180097587  jz      short loc_18009758E
0x180097589  lock add [rcx+8], r13d
0x18009758e  mov     rcx, [rbx]
0x180097591  mov     [rbp+57h+var_80], rcx
0x180097595  mov     rax, [rbx+8]
0x180097599  mov     [rbp+57h+var_80+8], rax
0x18009759d  mov     ecx, 3
0x1800975a2  mov     r9d, ecx
0x1800975a5  mov     [rsp+0C0h+var_90], r12b; char
0x1800975aa  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x1800975af  lea     rax, [rbp+57h+var_80]
0x1800975b3  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x1800975b8  mov     r8d, ecx
0x1800975bb  lea     rdx, aAclEndpointGro_1; "ACL_ENDPOINT_GROUP_IPV6_IN"
0x1800975c2  mov     rcx, r14; unsigned __int16 *
0x1800975c5  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x1800975ca  nop
0x1800975cb  lea     rcx, [rbp+57h+var_60]; void *
0x1800975cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800975d4  xorps   xmm0, xmm0
0x1800975d7  movups  [rbp+57h+var_60], xmm0
0x1800975db  xorps   xmm1, xmm1
0x1800975de  movdqu  [rbp+57h+var_50], xmm1
0x1800975e3  mov     r8d, 9
0x1800975e9  lea     rdx, aEpV6Out; "EP_V6_OUT"
0x1800975f0  lea     rcx, [rbp+57h+var_60]
0x1800975f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800975f9  nop
0x1800975fa  lea     rdx, [rbp+57h+var_60]
0x1800975fe  mov     rcx, r15
0x180097601  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x180097606  mov     rdx, rax
0x180097609  xorps   xmm0, xmm0
0x18009760c  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180097611  mov     rcx, [rbx+8]
0x180097615  test    rcx, rcx
0x180097618  jz      short loc_18009761F
0x18009761a  lock add [rcx+8], r13d
0x18009761f  mov     rcx, [rbx]
0x180097622  mov     [rbp+57h+var_80], rcx
0x180097626  mov     rax, [rbx+8]
0x18009762a  mov     [rbp+57h+var_80+8], rax
0x18009762e  mov     ecx, 4
0x180097633  mov     r9d, ecx
0x180097636  mov     [rsp+0C0h+var_90], r12b; char
0x18009763b  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x180097640  lea     rax, [rbp+57h+var_80]
0x180097644  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x180097649  mov     r8d, ecx
0x18009764c  lea     rdx, aAclEndpointGro_2; "ACL_ENDPOINT_GROUP_IPV6_OUT"
0x180097653  mov     rcx, r14; unsigned __int16 *
0x180097656  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x18009765b  nop
0x18009765c  lea     rcx, [rbp+57h+var_60]; void *
0x180097660  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180097665  xorps   xmm0, xmm0
0x180097668  movups  [rbp+57h+var_60], xmm0
0x18009766c  xorps   xmm1, xmm1
0x18009766f  movdqu  [rbp+57h+var_50], xmm1
0x180097674  mov     r8d, 8
0x18009767a  lea     rdx, aNwV4In; "NW_V4_IN"
0x180097681  lea     rcx, [rbp+57h+var_60]
0x180097685  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009768a  nop
0x18009768b  lea     rdx, [rbp+57h+var_60]
0x18009768f  mov     rcx, r15
0x180097692  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x180097697  mov     rdx, rax
0x18009769a  xorps   xmm0, xmm0
0x18009769d  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800976a2  mov     rcx, [rbx+8]
0x1800976a6  test    rcx, rcx
0x1800976a9  jz      short loc_1800976B0
0x1800976ab  lock add [rcx+8], r13d
0x1800976b0  mov     rcx, [rbx]
0x1800976b3  mov     [rbp+57h+var_80], rcx
0x1800976b7  mov     rax, [rbx+8]
0x1800976bb  mov     [rbp+57h+var_80+8], rax
0x1800976bf  mov     r9d, r13d
0x1800976c2  mov     [rsp+0C0h+var_90], r12b; char
0x1800976c7  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x1800976cc  lea     rax, [rbp+57h+var_80]
0x1800976d0  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x1800976d5  mov     r8d, r13d
0x1800976d8  lea     rdx, aAclNetworkGrou_1; "ACL_NETWORK_GROUP_IPV4_IN"
0x1800976df  mov     rcx, r14; unsigned __int16 *
0x1800976e2  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x1800976e7  nop
0x1800976e8  lea     rcx, [rbp+57h+var_60]; void *
0x1800976ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800976f1  xorps   xmm0, xmm0
0x1800976f4  movups  [rbp+57h+var_60], xmm0
0x1800976f8  xorps   xmm1, xmm1
0x1800976fb  movdqu  [rbp+57h+var_50], xmm1
0x180097700  mov     r8d, 9
0x180097706  lea     rdx, aNwV4Out; "NW_V4_OUT"
0x18009770d  lea     rcx, [rbp+57h+var_60]
0x180097711  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180097716  nop
0x180097717  lea     rdx, [rbp+57h+var_60]
0x18009771b  mov     rcx, r15
0x18009771e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x180097723  mov     rdx, rax
0x180097726  xorps   xmm0, xmm0
0x180097729  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18009772e  mov     rcx, [rbx+8]
0x180097732  test    rcx, rcx
0x180097735  jz      short loc_18009773C
0x180097737  lock add [rcx+8], r13d
0x18009773c  mov     rcx, [rbx]
0x18009773f  mov     [rbp+57h+var_80], rcx
0x180097743  mov     rax, [rbx+8]
0x180097747  mov     [rbp+57h+var_80+8], rax
0x18009774b  mov     ecx, 2
0x180097750  mov     r9d, ecx
0x180097753  mov     [rsp+0C0h+var_90], r12b; char
0x180097758  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x18009775d  lea     rax, [rbp+57h+var_80]
0x180097761  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x180097766  mov     r8d, ecx
0x180097769  lea     rdx, aAclNetworkGrou_0; "ACL_NETWORK_GROUP_IPV4_OUT"
0x180097770  mov     rcx, r14; unsigned __int16 *
0x180097773  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x180097778  nop
0x180097779  lea     rcx, [rbp+57h+var_60]; void *
0x18009777d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180097782  xorps   xmm0, xmm0
0x180097785  movups  [rbp+57h+var_60], xmm0
0x180097789  xorps   xmm1, xmm1
0x18009778c  movdqu  [rbp+57h+var_50], xmm1
0x180097791  mov     r8d, 8
0x180097797  lea     rdx, aNwV6In; "NW_V6_IN"
0x18009779e  lea     rcx, [rbp+57h+var_60]
0x1800977a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800977a7  nop
0x1800977a8  lea     rdx, [rbp+57h+var_60]
0x1800977ac  mov     rcx, r15
0x1800977af  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>,WString_iless,std::allocator<std::pair<std::wstring const,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>>>>>::operator[](std::wstring &&)
0x1800977b4  mov     rdx, rax
0x1800977b7  xorps   xmm0, xmm0
0x1800977ba  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800977bf  mov     rcx, [rbx+8]
0x1800977c3  test    rcx, rcx
0x1800977c6  jz      short loc_1800977CD
0x1800977c8  lock add [rcx+8], r13d
0x1800977cd  mov     rcx, [rbx]
0x1800977d0  mov     [rbp+57h+var_80], rcx
0x1800977d4  mov     rax, [rbx+8]
0x1800977d8  mov     [rbp+57h+var_80+8], rax
0x1800977dc  mov     ecx, 3
0x1800977e1  mov     r9d, ecx
0x1800977e4  mov     [rsp+0C0h+var_90], r12b; char
0x1800977e9  mov     qword ptr [rsp+0C0h+var_98], rdx; __int64
0x1800977ee  lea     rax, [rbp+57h+var_80]
0x1800977f2  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x1800977f7  mov     r8d, ecx
0x1800977fa  lea     rdx, aAclNetworkGrou; "ACL_NETWORK_GROUP_IPV6_IN"
0x180097801  mov     rcx, r14; unsigned __int16 *
0x180097804  call    ?ApplyLayerRules@VFPSettings@@KAXPEBG0W4_VFX_GROUP_TYPE@@GV?$shared_ptr@VVfpPort@@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@UWString_iless@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VVfpRule@@@std@@@2@@4@E@Z; VFPSettings::ApplyLayerRules(ushort const *,ushort const *,_VFX_GROUP_TYPE,ushort,std::shared_ptr<VfpPort>,std::map<std::wstring,VfpRule,WString_iless,std::allocator<std::pair<std::wstring const,VfpRule>>> const &,uchar)
0x180097809  nop
0x18009780a  lea     rcx, [rbp+57h+var_60]; void *
0x18009780e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180097813  xorps   xmm0, xmm0
0x180097816  movups  [rbp+57h+var_60], xmm0
0x18009781a  xorps   xmm1, xmm1
0x18009781d  movdqu  [rbp+57h+var_50], xmm1
  ... truncated ...
```
