# PublicNetworkListManager::SetDestinationAddresses(uint,NLM_SOCKADDR *,short)

- ea: `0x1800299c0`
- end: `0x180029e35`
- name: `?SetDestinationAddresses@PublicNetworkListManager@@UEAAJIPEAUNLM_SOCKADDR@@F@Z`
- size: `1141`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, unsigned int, struct NLM_SOCKADDR *, __int16)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800068d0`
- `0x180009184`
- `0x180009d08`
- `0x1800120d0`
- `0x180012f40`
- `0x18001e698`
- `0x18001fb2c`
- `0x18001ff00`
- `0x180023150`
- `0x1800293f0`
- `0x1800299c0`
- `0x18002a978`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029bc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029dd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029bc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029dd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b9d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180029d31`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180029d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c4e`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::SetDestinationAddresses(
        PublicNetworkListManager *this,
        unsigned int a2,
        struct NLM_SOCKADDR *a3,
        __int16 a4)
{
  unsigned int v8; // r15d
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // esi
  PublicNetworkListManager *v16; // rcx
  const struct NLM_SOCKADDR *v17; // r8
  unsigned int v18; // edx
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // rbx
  struct NLM_SOCKADDR *v21; // [rsp+20h] [rbp-50h]
  _QWORD v22[2]; // [rsp+28h] [rbp-48h] BYREF
  struct _GUID v23; // [rsp+38h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+48h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-20h] BYREF
  SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  SystemTime = 0;
  v8 = 0;
  FileTime = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 131, 1, 1) )
  {
    v9 = -2147023649;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v11 = 68;
LABEL_8:
    WPP_SF_d(v10[2], v11, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v9);
    return v9;
  }
  if ( a2 > 0xA )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2147483659LL;
    v14 = 69;
LABEL_35:
    WPP_SF_d(v13[2], v14, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, 2147483659LL);
    return 2147483659LL;
  }
  if ( a2 && !a3 )
  {
    v9 = -2147467261;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v9;
    v11 = 70;
    goto LABEL_8;
  }
  v15 = 0;
  if ( a2 )
  {
    *(_DWORD *)&SystemTime.wYear = 67436;
    SystemTime.wDay = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
    {
      if ( !a4 )
      {
        v17 = a3;
        v18 = a2;
        v16 = (PublicNetworkListManager *)((char *)this - 136);
        goto LABEL_23;
      }
      v24 = 0;
      wil::EnterCriticalSection(&v24, (struct _RTL_CRITICAL_SECTION *)((char *)this + 424));
      PublicNetworkListManager::AppendAddressInterfaceList((__int64)this - 136, a2, (__int64)a3);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v24);
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      if ( !a4 )
        PublicNetworkListManager::ClearAddressInterfaceListNoLock((PublicNetworkListManager *)((char *)this - 136));
      if ( a2 + *((_DWORD *)this + 118) > 0xA )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return 2147483659LL;
        v14 = 71;
        goto LABEL_35;
      }
      while ( v8 < a2 )
      {
        v24 = 0;
        v21 = &a3[(unsigned __int64)v8];
        PublicNetworkListManager::FindAddressInListNoLock((char *)this - 136, &v24, v21);
        if ( v24 == *((struct _RTL_CRITICAL_SECTION **)this + 58) )
        {
          v19 = (unsigned __int8 *)CoTaskMemAlloc(0x150u);
          v20 = v19;
          if ( !v19 )
          {
            v15 = -2147024882;
            break;
          }
          *((_OWORD *)v19 + 1) = *(_OWORD *)v21->data;
          *((_OWORD *)v19 + 2) = *(_OWORD *)&v21->data[16];
          *((_OWORD *)v19 + 3) = *(_OWORD *)&v21->data[32];
          *((_OWORD *)v19 + 4) = *(_OWORD *)&v21->data[48];
          *((_OWORD *)v19 + 5) = *(_OWORD *)&v21->data[64];
          *((_OWORD *)v19 + 6) = *(_OWORD *)&v21->data[80];
          *((_OWORD *)v19 + 7) = *(_OWORD *)&v21->data[96];
          *((_OWORD *)v19 + 8) = *(_OWORD *)&v21->data[112];
          *(struct _GUID *)v19 = *GetConnectionIdFromInterfaceByteBlob(&v23, 0x80u, v19 + 16);
          *((_OWORD *)v20 + 9) = 0;
          *((_OWORD *)v20 + 10) = 0;
          *((_QWORD *)v20 + 22) = 0;
          *((_DWORD *)v20 + 46) = -1;
          *(GUID *)(v20 + 188) = GUID_NULL;
          *((_DWORD *)v20 + 51) = -1;
          *((_QWORD *)v20 + 26) = 0;
          *((_DWORD *)v20 + 54) = -1;
          *((_DWORD *)v20 + 55) = -1;
          *((_DWORD *)v20 + 56) = -1;
          *(_QWORD *)(v20 + 228) = 0;
          *((_DWORD *)v20 + 59) = -1;
          *((_DWORD *)v20 + 60) = 0;
          if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
            *(struct _FILETIME *)(v20 + 228) = FileTime;
          *((_QWORD *)v20 + 41) = 0;
          memset_0(v20 + 248, 0, 0x50u);
          v22[0] = v20;
          v22[1] = (char *)this - 136;
          v15 = wil::ResultFromException__PublicNetworkListManager::SetDestinationAddresses_::_48_::_lambda_1___(v22);
          if ( v15 < 0 )
          {
            CoTaskMemFree(v20);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                72,
                &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
                (unsigned int)v15);
              break;
            }
          }
        }
        ++v8;
        if ( v15 < 0 )
          break;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    }
  }
  else
  {
    if ( a4 )
      goto LABEL_50;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
    {
      v16 = (PublicNetworkListManager *)((char *)this - 136);
      v17 = 0;
      v18 = 0;
LABEL_23:
      PublicNetworkListManager::ResetAddressInterfaceList(v16, v18, v17);
      goto LABEL_50;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    PublicNetworkListManager::ClearAddressInterfaceListNoLock((PublicNetworkListManager *)((char *)this - 136));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
  }
LABEL_50:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
      (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800299c0  mov     [rsp-38h+arg_18], rbx
0x1800299c5  push    rbp
0x1800299c6  push    rsi
0x1800299c7  push    rdi
0x1800299c8  push    r12
0x1800299ca  push    r13
0x1800299cc  push    r14
0x1800299ce  push    r15
0x1800299d0  mov     rbp, rsp
0x1800299d3  sub     rsp, 70h
0x1800299d7  mov     rax, cs:__security_cookie
0x1800299de  xor     rax, rsp
0x1800299e1  mov     [rbp+var_8], rax
0x1800299e5  movzx   ebx, r9w
0x1800299e9  mov     r12, r8
0x1800299ec  mov     r14d, edx
0x1800299ef  mov     rdi, rcx
0x1800299f2  xorps   xmm0, xmm0
0x1800299f5  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800299f9  xor     r15d, r15d
0x1800299fc  mov     qword ptr [rbp+FileTime.dwLowDateTime], r15
0x180029a00  lea     r8, WPP_GLOBAL_Control
0x180029a07  lea     r13, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180029a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a15  cmp     rcx, r8
0x180029a18  jz      short loc_180029A37
0x180029a1a  test    byte ptr [rcx+1Ch], 8
0x180029a1e  jz      short loc_180029A37
0x180029a20  lea     edx, [r15+43h]
0x180029a24  mov     r8, r13
0x180029a27  mov     rcx, [rcx+10h]
0x180029a2b  call    WPP_SF_
0x180029a30  lea     r8, WPP_GLOBAL_Control
0x180029a37  mov     edx, 1
0x180029a3c  mov     eax, edx
0x180029a3e  lock cmpxchg [rdi+20Ch], edx
0x180029a46  test    eax, eax
0x180029a48  jz      short loc_180029A7B
0x180029a4a  mov     ebx, 800704DFh
0x180029a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a56  cmp     rcx, r8
0x180029a59  jz      short loc_180029A74
0x180029a5b  test    [rcx+1Ch], dl
0x180029a5e  jz      short loc_180029A74
0x180029a60  mov     edx, 44h ; 'D'
0x180029a65  mov     r9d, ebx
0x180029a68  mov     r8, r13
0x180029a6b  mov     rcx, [rcx+10h]
0x180029a6f  call    WPP_SF_d
0x180029a74  mov     eax, ebx
0x180029a76  jmp     loc_180029E11
0x180029a7b  cmp     r14d, 0Ah
0x180029a7f  jbe     short loc_180029AA7
0x180029a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a88  cmp     rcx, r8
0x180029a8b  jz      loc_180029BFF
0x180029a91  test    [rcx+1Ch], dl
0x180029a94  jz      loc_180029BFF
0x180029a9a  mov     edx, 45h ; 'E'
0x180029a9f  mov     r8, r13
0x180029aa2  jmp     loc_180029BF0
0x180029aa7  test    r14d, r14d
0x180029aaa  jz      short loc_180029ACE
0x180029aac  test    r12, r12
0x180029aaf  jnz     short loc_180029ACE
0x180029ab1  mov     ebx, 80004003h
0x180029ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180029abd  cmp     rcx, r8
0x180029ac0  jz      short loc_180029A74
0x180029ac2  test    [rcx+1Ch], dl
0x180029ac5  jz      short loc_180029A74
0x180029ac7  lea     edx, [r12+46h]
0x180029acc  jmp     short loc_180029A65
0x180029ace  mov     esi, r15d
0x180029ad1  test    r14d, r14d
0x180029ad4  jnz     short loc_180029B2F
0x180029ad6  test    bx, bx
0x180029ad9  jnz     loc_180029DE2
0x180029adf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180029ae6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180029aeb  test    al, al
0x180029aed  jz      short loc_180029B05
0x180029aef  lea     rcx, [rdi-88h]; this
0x180029af6  xor     r8d, r8d; struct NLM_SOCKADDR *
0x180029af9  xor     edx, edx; unsigned int
0x180029afb  call    ?ResetAddressInterfaceList@PublicNetworkListManager@@AEAAJIPEBUNLM_SOCKADDR@@@Z; PublicNetworkListManager::ResetAddressInterfaceList(uint,NLM_SOCKADDR const *)
0x180029b00  jmp     loc_180029DE2
0x180029b05  lea     rbx, [rdi+1A8h]
0x180029b0c  mov     rcx, rbx; lpCriticalSection
0x180029b0f  call    cs:__imp_EnterCriticalSection
0x180029b15  lea     rcx, [rdi-88h]; this
0x180029b1c  call    ?ClearAddressInterfaceListNoLock@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::ClearAddressInterfaceListNoLock(void)
0x180029b21  mov     rcx, rbx; lpCriticalSection
0x180029b24  call    cs:__imp_LeaveCriticalSection
0x180029b2a  jmp     loc_180029DE2
0x180029b2f  mov     dword ptr [rbp+SystemTime.wYear], 1076Ch
0x180029b36  mov     [rbp+SystemTime.wDay], dx
0x180029b3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180029b41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180029b46  test    al, al
0x180029b48  jz      short loc_180029B93
0x180029b4a  lea     r15, [rdi-88h]
0x180029b51  xor     eax, eax
0x180029b53  test    bx, bx
0x180029b56  jnz     short loc_180029B63
0x180029b58  mov     r8, r12
0x180029b5b  mov     edx, r14d
0x180029b5e  mov     rcx, r15
0x180029b61  jmp     short loc_180029AFB
0x180029b63  mov     [rbp+var_28], rax
0x180029b67  lea     rdx, [rdi+1A8h]
0x180029b6e  lea     rcx, [rbp+var_28]
0x180029b72  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180029b77  mov     r8, r12
0x180029b7a  mov     edx, r14d
0x180029b7d  mov     rcx, r15
0x180029b80  call    ?AppendAddressInterfaceList@PublicNetworkListManager@@AEAAJIPEBUNLM_SOCKADDR@@Uwrite_lock_required@wil@@@Z; PublicNetworkListManager::AppendAddressInterfaceList(uint,NLM_SOCKADDR const *,wil::write_lock_required)
0x180029b85  lea     rcx, [rbp+var_28]
0x180029b89  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180029b8e  jmp     loc_180029DE2
0x180029b93  lea     r13, [rdi+1A8h]
0x180029b9a  mov     rcx, r13; lpCriticalSection
0x180029b9d  call    cs:__imp_EnterCriticalSection
0x180029ba3  test    bx, bx
0x180029ba6  jnz     short loc_180029BB4
0x180029ba8  lea     rcx, [rdi-88h]; this
0x180029baf  call    ?ClearAddressInterfaceListNoLock@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::ClearAddressInterfaceListNoLock(void)
0x180029bb4  mov     ecx, [rdi+1D8h]
0x180029bba  add     ecx, r14d
0x180029bbd  cmp     ecx, 0Ah
0x180029bc0  jbe     short loc_180029C09
0x180029bc2  mov     rcx, r13; lpCriticalSection
0x180029bc5  call    cs:__imp_LeaveCriticalSection
0x180029bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bd2  lea     rdx, WPP_GLOBAL_Control
0x180029bd9  cmp     rcx, rdx
0x180029bdc  jz      short loc_180029BFF
0x180029bde  test    byte ptr [rcx+1Ch], 1
0x180029be2  jz      short loc_180029BFF
0x180029be4  mov     edx, 47h ; 'G'
0x180029be9  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180029bf0  mov     r9d, 8000000Bh
0x180029bf6  mov     rcx, [rcx+10h]
0x180029bfa  call    WPP_SF_d
0x180029bff  mov     eax, 8000000Bh
0x180029c04  jmp     loc_180029E11
0x180029c09  cmp     r15d, r14d
0x180029c0c  jnb     loc_180029DD2
0x180029c12  mov     [rbp+var_28], 0
0x180029c1a  mov     r8d, r15d
0x180029c1d  shl     r8, 7
0x180029c21  add     r8, r12
0x180029c24  mov     [rbp+var_50], r8
0x180029c28  lea     rcx, [rdi-88h]
0x180029c2f  lea     rdx, [rbp+var_28]
0x180029c33  call    ?FindAddressInListNoLock@PublicNetworkListManager@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAUADDRESS_INTERFACE_DATA@@@std@@@std@@@std@@PEAUsockaddr_storage@@@Z; PublicNetworkListManager::FindAddressInListNoLock(sockaddr_storage *)
0x180029c38  mov     rax, [rdi+1D0h]
0x180029c3f  cmp     [rbp+var_28], rax
0x180029c43  jnz     loc_180029DA6
0x180029c49  mov     ecx, 150h; cb
0x180029c4e  call    cs:__imp_CoTaskMemAlloc
0x180029c54  mov     rbx, rax
0x180029c57  xor     esi, esi
0x180029c59  test    rax, rax
0x180029c5c  jz      loc_180029DCD
0x180029c62  lea     r8, [rax+10h]; unsigned __int8 *
0x180029c66  mov     rax, [rbp+var_50]
0x180029c6a  movups  xmm0, xmmword ptr [rax]
0x180029c6d  movups  xmmword ptr [r8], xmm0
0x180029c71  movups  xmm1, xmmword ptr [rax+10h]
0x180029c75  movups  xmmword ptr [r8+10h], xmm1
0x180029c7a  movups  xmm0, xmmword ptr [rax+20h]
0x180029c7e  movups  xmmword ptr [r8+20h], xmm0
0x180029c83  movups  xmm1, xmmword ptr [rax+30h]
0x180029c87  movups  xmmword ptr [r8+30h], xmm1
0x180029c8c  movups  xmm0, xmmword ptr [rax+40h]
0x180029c90  movups  xmmword ptr [r8+40h], xmm0
0x180029c95  movups  xmm1, xmmword ptr [rax+50h]
0x180029c99  movups  xmmword ptr [r8+50h], xmm1
0x180029c9e  movups  xmm0, xmmword ptr [rax+60h]
0x180029ca2  movups  xmmword ptr [r8+60h], xmm0
0x180029ca7  movups  xmm1, xmmword ptr [rax+70h]
0x180029cab  movups  xmmword ptr [r8+70h], xmm1
0x180029cb0  mov     edx, 80h; unsigned int
0x180029cb5  lea     rcx, [rbp+var_38]; retstr
0x180029cb9  call    ?GetConnectionIdFromInterfaceByteBlob@@YA?AU_GUID@@KPEBE@Z; GetConnectionIdFromInterfaceByteBlob(ulong,uchar const *)
0x180029cbe  movups  xmm1, xmmword ptr [rax]
0x180029cc1  movdqu  xmmword ptr [rbx], xmm1
0x180029cc5  xorps   xmm0, xmm0
0x180029cc8  xor     eax, eax
0x180029cca  movups  xmmword ptr [rbx+90h], xmm0
0x180029cd1  movups  xmmword ptr [rbx+0A0h], xmm0
0x180029cd8  mov     [rbx+0B0h], rax
0x180029cdf  or      eax, 0FFFFFFFFh
0x180029ce2  mov     [rbx+0B8h], eax
0x180029ce8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180029cef  movdqu  xmmword ptr [rbx+0BCh], xmm0
0x180029cf7  mov     [rbx+0CCh], eax
0x180029cfd  mov     [rbx+0D0h], rsi
0x180029d04  mov     [rbx+0D8h], eax
0x180029d0a  mov     [rbx+0DCh], eax
0x180029d10  mov     [rbx+0E0h], eax
0x180029d16  mov     [rbx+0E4h], rsi
0x180029d1d  mov     [rbx+0ECh], eax
0x180029d23  mov     [rbx+0F0h], esi
0x180029d29  lea     rdx, [rbp+FileTime]; lpFileTime
0x180029d2d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180029d31  call    cs:__imp_SystemTimeToFileTime
0x180029d37  test    eax, eax
0x180029d39  jz      short loc_180029D4D
0x180029d3b  mov     eax, [rbp+FileTime.dwHighDateTime]
0x180029d3e  mov     [rbx+0E8h], eax
0x180029d44  mov     eax, [rbp+FileTime.dwLowDateTime]
0x180029d47  mov     [rbx+0E4h], eax
0x180029d4d  mov     [rbx+148h], rsi
0x180029d54  lea     rcx, [rbx+0F8h]; void *
0x180029d5b  xor     edx, edx; Val
0x180029d5d  lea     r8d, [rdx+50h]; Size
0x180029d61  call    memset_0
0x180029d66  mov     [rbp+var_48], rbx
0x180029d6a  lea     rax, [rdi-88h]
0x180029d71  mov     [rbp+var_40], rax
0x180029d75  lea     rcx, [rbp+var_48]
0x180029d79  call    wil__ResultFromException__PublicNetworkListManager__SetDestinationAddresses____48____lambda_1___
0x180029d7e  mov     esi, eax
0x180029d80  test    eax, eax
0x180029d82  jns     short loc_180029DA6
0x180029d84  mov     rcx, rbx; pv
0x180029d87  call    cs:__imp_CoTaskMemFree
0x180029d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d94  lea     rax, WPP_GLOBAL_Control
0x180029d9b  cmp     rcx, rax
0x180029d9e  jz      short loc_180029DA6
0x180029da0  test    byte ptr [rcx+1Ch], 1
0x180029da4  jnz     short loc_180029DB3
0x180029da6  inc     r15d
0x180029da9  test    esi, esi
0x180029dab  jns     loc_180029C09
0x180029db1  jmp     short loc_180029DD2
0x180029db3  mov     edx, 48h ; 'H'
0x180029db8  mov     r9d, esi
0x180029dbb  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180029dc2  mov     rcx, [rcx+10h]
0x180029dc6  call    WPP_SF_d
0x180029dcb  jmp     short loc_180029DD2
0x180029dcd  mov     esi, 8007000Eh
0x180029dd2  mov     rcx, r13; lpCriticalSection
0x180029dd5  call    cs:__imp_LeaveCriticalSection
0x180029ddb  lea     r13, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180029de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180029de9  lea     rax, WPP_GLOBAL_Control
0x180029df0  cmp     rcx, rax
0x180029df3  jz      short loc_180029E0F
0x180029df5  test    byte ptr [rcx+1Ch], 8
0x180029df9  jz      short loc_180029E0F
0x180029dfb  mov     edx, 49h ; 'I'
0x180029e00  mov     r9d, esi
0x180029e03  mov     r8, r13
0x180029e06  mov     rcx, [rcx+10h]
0x180029e0a  call    WPP_SF_d
0x180029e0f  mov     eax, esi
0x180029e11  mov     rcx, [rbp+var_8]
0x180029e15  xor     rcx, rsp; StackCookie
0x180029e18  call    __security_check_cookie
0x180029e1d  mov     rbx, [rsp+70h+arg_18]
0x180029e25  add     rsp, 70h
0x180029e29  pop     r15
0x180029e2b  pop     r14
0x180029e2d  pop     r13
0x180029e2f  pop     r12
0x180029e31  pop     rdi
0x180029e32  pop     rsi
0x180029e33  pop     rbp
0x180029e34  retn
```
