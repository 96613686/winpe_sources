# OnAepImportComplete(ulong,_DEVPROPERTY * const,long,void *)

- ea: `0x180059f94`
- end: `0x18005a3d0`
- name: `?OnAepImportComplete@@YAJKQEAU_DEVPROPERTY@@JPEAX@Z`
- size: `1084`
- prototype: `__int64 __fastcall(unsigned int, struct _DEVPROPERTY *const, int, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800491e0`

## callees

- `0x180005c5c`
- `0x1800074c0`
- `0x180007500`
- `0x180008a50`
- `0x180019d00`
- `0x18001a268`
- `0x18001eae0`
- `0x180027b2c`
- `0x180028ed8`
- `0x18002be5c`
- `0x180031f24`
- `0x1800582b0`
- `0x180059100`
- `0x180059f94`
- `0x18005b674`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059fd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059fd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059ff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a01d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a387`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059ff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a01d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a387`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005a1b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005a1b6`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005a128`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005a154`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005a128`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005a154`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059fc5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059fc5`

## pseudocode

```c
__int64 __fastcall OnAepImportComplete(unsigned int a1, struct _DEVPROPERTY *const a2, int a3, char *a4)
{
  int ProviderFromAepId; // esi
  const unsigned __int16 *v8; // rbx
  int v9; // r13d
  int v10; // r15d
  char *v11; // r14
  char IsEnabled; // al
  int v13; // edx
  int v14; // r8d
  struct _RPC_ASYNC_STATE *v15; // rcx
  RPC_STATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  const wchar_t *v21; // rcx
  const wchar_t *v22; // rax
  unsigned int NotificationsQueued; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+64h] [rbp-1Ch] BYREF
  const unsigned __int16 *v26; // [rsp+68h] [rbp-18h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+70h] [rbp-10h] BYREF
  int Reply; // [rsp+D0h] [rbp+50h] BYREF
  int v29; // [rsp+D8h] [rbp+58h] BYREF

  Reply = a3;
  EventActivityIdControl(2u, (LPGUID)(a4 + 8));
  EnterCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
  if ( *((_DWORD *)a4 + 56) )
  {
    ProviderFromAepId = -2147416294;
    *((_DWORD *)a4 + 56) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
    (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
  }
  else if ( *((_DWORD *)a4 + 57) )
  {
    ProviderFromAepId = -2147418113;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
  }
  else
  {
    NotificationsQueued = 0;
    *(_OWORD *)v27 = 0;
    v8 = 0;
    v26 = 0;
    v9 = 0;
    ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(
                          g_providerManager,
                          **((_QWORD **)a4 + 7),
                          v27);
    if ( ProviderFromAepId < 0
      || Reply < 0
      || Reply == 1
      || *((_DWORD *)v27[0] + 19)
      || (ProviderFromAepId = Windows::Devices::Pnp::Internal::PnpObjectStore::SetProperties(
                                g_AepStore,
                                **((const unsigned __int16 ***)a4 + 7),
                                1,
                                a1,
                                a2),
          ProviderFromAepId < 0) )
    {
      v10 = 0;
    }
    else
    {
      DAS::Dispatcher::Dispatch::ExternalAepStoreChange(**((const unsigned __int16 ***)a4 + 7), 0, 1u, a1, a2);
      v10 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v26,
          0);
        v9 = DafStringCopy(**((_QWORD **)a4 + 7), &v26);
        v8 = v26;
      }
    }
    v11 = a4 + 32;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)a4 + 72) )
      {
        RpcServerUnsubscribeForNotification(
          *(RPC_BINDING_HANDLE *)(*(_QWORD *)v11 + 32LL),
          RpcNotificationCallCancel,
          &NotificationsQueued);
        (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
      }
    }
    else
    {
      if ( *(_QWORD *)v11 )
      {
        RpcServerUnsubscribeForNotification(
          *(RPC_BINDING_HANDLE *)(*(_QWORD *)v11 + 32LL),
          RpcNotificationCallCancel,
          &NotificationsQueued);
        (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
      }
      if ( v10 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v26,
          0);
        v9 = DafStringCopy(**((_QWORD **)a4 + 7), &v26);
        v8 = v26;
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl);
    v15 = *(struct _RPC_ASYNC_STATE **)v11;
    if ( !IsEnabled || v15 )
    {
      *((_DWORD *)a4 + 57) = 1;
      v16 = RpcAsyncCompleteCall(v15, &Reply);
      if ( v16 )
      {
        if ( v16 < 0 )
          ProviderFromAepId = v16;
        else
          ProviderFromAepId = (unsigned __int16)v16 | 0x80010000;
      }
      *(_QWORD *)v11 = 0;
    }
    if ( v10 )
    {
      if ( v9 < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v13,
            v14,
            65,
            &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
            v9);
      }
      else
      {
        ProviderFromAepId = DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagement(g_devnodeManager, v8, 0, 0);
        if ( ProviderFromAepId >= 0 )
        {
          v25 = 0;
          v29 = 0;
          ProviderFromAepId = DasEvaluateServiceLifetime(&v25, &v29);
          if ( ProviderFromAepId >= 0 )
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v21 = L"armed";
              if ( !v29 )
                v21 = (const wchar_t *)L"disarmed";
              v22 = L"auto";
              if ( v25 != 2 )
                v22 = (const wchar_t *)L"trigger";
              WPP_RECORDER_SF_SSSSqD(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                (int)L"trigger",
                v20,
                64,
                &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
                (__int64)v8,
                (__int64)L"*currently not supported*",
                (__int64)v22,
                (__int64)v21,
                (char)a4,
                ProviderFromAepId);
            }
          }
          else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_SSqD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v19,
              v20,
              63,
              &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
              (__int64)v8,
              (__int64)L"*currently not supported*",
              (char)a4,
              ProviderFromAepId);
          }
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_SSq(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v17,
            v18,
            62,
            &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
            (__int64)v8,
            (__int64)L"*currently not supported*",
            (char)a4);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
    (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v26);
    if ( v27[1] )
      std::_Ref_count_base::_Decref(v27[1]);
  }
  return (unsigned int)ProviderFromAepId;
}

```

## disassembly

```asm
0x180059f94  mov     [rsp-38h+arg_0], rbx
0x180059f99  mov     [rsp-38h+Reply], r8d
0x180059f9e  push    rbp
0x180059f9f  push    rsi
0x180059fa0  push    rdi
0x180059fa1  push    r12
0x180059fa3  push    r13
0x180059fa5  push    r14
0x180059fa7  push    r15
0x180059fa9  mov     rbp, rsp
0x180059fac  sub     rsp, 80h
0x180059fb3  mov     rdi, r9
0x180059fb6  mov     r14, rdx
0x180059fb9  mov     r15d, ecx
0x180059fbc  lea     rdx, [r9+8]; ActivityId
0x180059fc0  mov     ecx, 2; ControlCode
0x180059fc5  call    cs:__imp_EventActivityIdControl
0x180059fcb  lea     r12, [rdi+0E8h]
0x180059fd2  mov     rcx, r12; lpCriticalSection
0x180059fd5  call    cs:__imp_EnterCriticalSection
0x180059fdb  xor     eax, eax
0x180059fdd  cmp     [rdi+0E0h], eax
0x180059fe3  jz      short loc_18005A00D
0x180059fe5  mov     esi, 8001071Ah
0x180059fea  mov     [rdi+0E0h], eax
0x180059ff0  mov     rcx, r12; lpCriticalSection
0x180059ff3  call    cs:__imp_LeaveCriticalSection
0x180059ff9  mov     rax, [rdi]
0x180059ffc  mov     rcx, rdi
0x180059fff  mov     rax, [rax+10h]
0x18005a003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a008  jmp     loc_18005A3B3
0x18005a00d  cmp     [rdi+0E4h], eax
0x18005a013  jz      short loc_18005A028
0x18005a015  mov     esi, 8000FFFFh
0x18005a01a  mov     rcx, r12; lpCriticalSection
0x18005a01d  call    cs:__imp_LeaveCriticalSection
0x18005a023  jmp     loc_18005A3B3
0x18005a028  mov     [rbp+NotificationsQueued], eax
0x18005a02b  xorps   xmm0, xmm0
0x18005a02e  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18005a033  mov     rbx, rax
0x18005a036  mov     [rbp+var_18], rax
0x18005a03a  mov     r13d, eax
0x18005a03d  mov     rdx, [rdi+38h]
0x18005a041  lea     r8, [rbp+var_10]
0x18005a045  mov     rdx, [rdx]
0x18005a048  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18005a04f  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x18005a054  mov     esi, eax
0x18005a056  test    eax, eax
0x18005a058  js      loc_18005A0F8
0x18005a05e  test    [rbp+Reply], 80000000h
0x18005a065  jnz     loc_18005A0F8
0x18005a06b  cmp     [rbp+Reply], 1
0x18005a06f  jz      loc_18005A0F8
0x18005a075  mov     rcx, [rbp+var_10]
0x18005a079  cmp     [rcx+4Ch], ebx
0x18005a07c  jnz     short loc_18005A0F8
0x18005a07e  mov     rdx, [rdi+38h]
0x18005a082  mov     [rsp+80h+MessageGuid], r14; struct _DEVPROPERTY *
0x18005a087  mov     r9d, r15d; unsigned int
0x18005a08a  mov     r8b, 1; bool
0x18005a08d  mov     rdx, [rdx]; unsigned __int16 *
0x18005a090  mov     rcx, cs:?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; this
0x18005a097  call    ?SetProperties@PnpObjectStore@Internal@Pnp@Devices@Windows@@AEAAJPEBG_NKPEBU_DEVPROPERTY@@@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::SetProperties(ushort const *,bool,ulong,_DEVPROPERTY const *)
0x18005a09c  mov     esi, eax
0x18005a09e  test    eax, eax
0x18005a0a0  js      short loc_18005A0F8
0x18005a0a2  mov     rcx, [rdi+38h]
0x18005a0a6  mov     [rsp+80h+MessageGuid], r14; struct _DEVPROPERTY *
0x18005a0ab  mov     r9d, r15d; unsigned int
0x18005a0ae  mov     r14d, 1
0x18005a0b4  mov     r8d, r14d; unsigned int
0x18005a0b7  xor     edx, edx; unsigned __int16 *
0x18005a0b9  mov     rcx, [rcx]; unsigned __int16 *
0x18005a0bc  call    ?ExternalAepStoreChange@Dispatch@Dispatcher@DAS@@SAJPEBG0KKQEAU_DEVPROPERTY@@@Z; DAS::Dispatcher::Dispatch::ExternalAepStoreChange(ushort const *,ushort const *,ulong,ulong,_DEVPROPERTY * const)
0x18005a0c1  mov     r15d, r14d
0x18005a0c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005a0cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005a0d0  test    al, al
0x18005a0d2  jz      short loc_18005A0FB
0x18005a0d4  xor     edx, edx
0x18005a0d6  lea     rcx, [rbp+var_18]
0x18005a0da  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005a0df  mov     rcx, [rdi+38h]
0x18005a0e3  lea     rdx, [rbp+var_18]
0x18005a0e7  mov     rcx, [rcx]
0x18005a0ea  call    DafStringCopy
0x18005a0ef  mov     r13d, eax
0x18005a0f2  mov     rbx, [rbp+var_18]
0x18005a0f6  jmp     short loc_18005A0FB
0x18005a0f8  mov     r15d, ebx
0x18005a0fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005a102  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005a107  lea     r14, [rdi+20h]
0x18005a10b  test    al, al
0x18005a10d  jz      short loc_18005A13F
0x18005a10f  cmp     dword ptr [rdi+120h], 0
0x18005a116  jz      short loc_18005A190
0x18005a118  mov     rcx, [r14]
0x18005a11b  lea     r8, [rbp+NotificationsQueued]; NotificationsQueued
0x18005a11f  mov     edx, 2; Notification
0x18005a124  mov     rcx, [rcx+20h]; Binding
0x18005a128  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18005a12e  mov     rax, [rdi]
0x18005a131  mov     rcx, rdi
0x18005a134  mov     rax, [rax+10h]
0x18005a138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a13d  jmp     short loc_18005A190
0x18005a13f  mov     rcx, [r14]
0x18005a142  test    rcx, rcx
0x18005a145  jz      short loc_18005A169
0x18005a147  lea     r8, [rbp+NotificationsQueued]; NotificationsQueued
0x18005a14b  mov     edx, 2; Notification
0x18005a150  mov     rcx, [rcx+20h]; Binding
0x18005a154  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18005a15a  mov     rax, [rdi]
0x18005a15d  mov     rcx, rdi
0x18005a160  mov     rax, [rax+10h]
0x18005a164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a169  test    r15d, r15d
0x18005a16c  jz      short loc_18005A190
0x18005a16e  xor     edx, edx
0x18005a170  lea     rcx, [rbp+var_18]
0x18005a174  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005a179  mov     rcx, [rdi+38h]
0x18005a17d  lea     rdx, [rbp+var_18]
0x18005a181  mov     rcx, [rcx]
0x18005a184  call    DafStringCopy
0x18005a189  mov     r13d, eax
0x18005a18c  mov     rbx, [rbp+var_18]
0x18005a190  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005a197  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005a19c  mov     rcx, [r14]; pAsync
0x18005a19f  test    al, al
0x18005a1a1  jz      short loc_18005A1A8
0x18005a1a3  test    rcx, rcx
0x18005a1a6  jz      short loc_18005A1D6
0x18005a1a8  mov     dword ptr [rdi+0E4h], 1
0x18005a1b2  lea     rdx, [rbp+Reply]; Reply
0x18005a1b6  call    cs:__imp_RpcAsyncCompleteCall
0x18005a1bc  test    eax, eax
0x18005a1be  jz      short loc_18005A1CF
0x18005a1c0  js      short loc_18005A1CD
0x18005a1c2  movzx   esi, ax
0x18005a1c5  or      esi, 80010000h
0x18005a1cb  jmp     short loc_18005A1CF
0x18005a1cd  mov     esi, eax
0x18005a1cf  mov     qword ptr [r14], 0
0x18005a1d6  xor     r14d, r14d
0x18005a1d9  test    r15d, r15d
0x18005a1dc  jz      loc_18005A384
0x18005a1e2  test    r13d, r13d
0x18005a1e5  js      loc_18005A34D
0x18005a1eb  xor     r9d, r9d; void *
0x18005a1ee  xor     r8d, r8d; unsigned __int16 *
0x18005a1f1  mov     rdx, rbx; unsigned __int16 *
0x18005a1f4  mov     rcx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; this
0x18005a1fb  call    ?StartDevnodeManagement@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0PEAX@Z; DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagement(ushort const *,ushort const *,void *)
0x18005a200  mov     esi, eax
0x18005a202  test    eax, eax
0x18005a204  jns     short loc_18005A255
0x18005a206  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a20d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a214  jz      loc_18005A384
0x18005a21a  lea     r9d, [r14+3Eh]; int
0x18005a21e  mov     qword ptr [rsp+80h+var_48], rdi; char
0x18005a223  lea     rax, aCurrentlyNotSu; "*currently not supported*"
0x18005a22a  mov     [rsp+80h+var_50], rax; __int64
0x18005a22f  mov     qword ptr [rsp+80h+var_58], rbx; __int64
0x18005a234  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005a23b  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x18005a240  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a247  mov     rcx, [rcx+28h]; int
0x18005a24b  call    WPP_RECORDER_SF_SSq
0x18005a250  jmp     loc_18005A384
0x18005a255  mov     [rbp+var_1C], r14d
0x18005a259  mov     [rbp+arg_18], r14d
0x18005a25d  lea     rdx, [rbp+arg_18]; int *
0x18005a261  lea     rcx, [rbp+var_1C]; unsigned int *
0x18005a265  call    ?DasEvaluateServiceLifetime@@YAJPEAKPEAH@Z; DasEvaluateServiceLifetime(ulong *,int *)
0x18005a26a  mov     esi, eax
0x18005a26c  test    eax, eax
0x18005a26e  jns     short loc_18005A2C5
0x18005a270  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a277  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a27e  jz      loc_18005A384
0x18005a284  mov     r9d, 3Fh ; '?'; int
0x18005a28a  mov     dword ptr [rsp+80h+var_40], esi; char
0x18005a28e  mov     qword ptr [rsp+80h+var_48], rdi; char
0x18005a293  lea     rax, aCurrentlyNotSu; "*currently not supported*"
0x18005a29a  mov     [rsp+80h+var_50], rax; __int64
0x18005a29f  mov     qword ptr [rsp+80h+var_58], rbx; __int64
0x18005a2a4  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005a2ab  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x18005a2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2b7  mov     rcx, [rcx+28h]; int
0x18005a2bb  call    WPP_RECORDER_SF_SSqD
0x18005a2c0  jmp     loc_18005A384
0x18005a2c5  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a2cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a2d3  jz      loc_18005A384
0x18005a2d9  lea     rcx, aArmed; "armed"
0x18005a2e0  lea     rax, aDisarmed; "disarmed"
0x18005a2e7  cmp     [rbp+arg_18], r14d
0x18005a2eb  cmovz   rcx, rax
0x18005a2ef  lea     rax, aAuto; "auto"
0x18005a2f6  lea     rdx, aTrigger; "trigger"
0x18005a2fd  cmp     [rbp+var_1C], 2
0x18005a301  cmovnz  rax, rdx
0x18005a305  mov     r9d, 40h ; '@'; int
0x18005a30b  mov     dword ptr [rsp+80h+var_30], esi; char
0x18005a30f  mov     qword ptr [rsp+80h+var_38], rdi; char
0x18005a314  mov     qword ptr [rsp+80h+var_40], rcx; __int64
0x18005a319  mov     qword ptr [rsp+80h+var_48], rax; __int64
0x18005a31e  lea     rax, aCurrentlyNotSu; "*currently not supported*"
0x18005a325  mov     [rsp+80h+var_50], rax; __int64
0x18005a32a  mov     qword ptr [rsp+80h+var_58], rbx; __int64
0x18005a32f  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005a336  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x18005a33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a342  mov     rcx, [rcx+28h]; int
0x18005a346  call    WPP_RECORDER_SF_SSSSqD
0x18005a34b  jmp     short loc_18005A384
0x18005a34d  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a354  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a35b  jz      short loc_18005A384
0x18005a35d  mov     r9d, 41h ; 'A'; int
0x18005a363  mov     dword ptr [rsp+80h+var_58], r13d; char
0x18005a368  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005a36f  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x18005a374  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a37b  mov     rcx, [rcx+28h]; int
0x18005a37f  call    WPP_RECORDER_SF_D
0x18005a384  mov     rcx, r12; lpCriticalSection
0x18005a387  call    cs:__imp_LeaveCriticalSection
0x18005a38d  mov     rax, [rdi]
0x18005a390  mov     rcx, rdi
0x18005a393  mov     rax, [rax+10h]
0x18005a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a39c  lea     rcx, [rbp+var_18]
0x18005a3a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005a3a5  mov     rcx, [rbp+var_10+8]; this
0x18005a3a9  test    rcx, rcx
0x18005a3ac  jz      short loc_18005A3B3
0x18005a3ae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a3b3  mov     eax, esi
0x18005a3b5  mov     rbx, [rsp+80h+arg_0]
0x18005a3bd  add     rsp, 80h
0x18005a3c4  pop     r15
0x18005a3c6  pop     r14
0x18005a3c8  pop     r13
0x18005a3ca  pop     r12
0x18005a3cc  pop     rdi
0x18005a3cd  pop     rsi
0x18005a3ce  pop     rbp
0x18005a3cf  retn
```
