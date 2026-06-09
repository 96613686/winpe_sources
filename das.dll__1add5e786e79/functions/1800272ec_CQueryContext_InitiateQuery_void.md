# CQueryContext::InitiateQuery(void)

- ea: `0x1800272ec`
- end: `0x180027737`
- name: `?InitiateQuery@CQueryContext@@QEAAXXZ`
- size: `1099`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a4b0`
- `0x180052b30`

## callees

- `0x1800074c0`
- `0x1800095bc`
- `0x180018db4`
- `0x180019f78`
- `0x18001e3d0`
- `0x18001eae0`
- `0x180021ef4`
- `0x180023f34`
- `0x180024024`
- `0x180024d60`
- `0x1800272ec`
- `0x1800290c4`
- `0x1800345f0`
- `0x18003602c`
- `0x18003c79c`
- `0x18003c9f8`
- `0x180044c70`
- `0x180050438`
- `0x1800529dc`
- `0x1800536d4`
- `0x18005eee4`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18002737c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002737c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800276d2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800276d2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027354`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180027354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800275b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027681`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800275b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027681`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800275c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027690`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800275c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027690`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800275ff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800275ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002766c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002766c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x1800275f2`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x1800275f2`

## pseudocode

```c
void __fastcall CQueryContext::InitiateQuery(unsigned __int16 *SRWLock, int a2, int a3)
{
  unsigned __int16 *v3; // rbx
  char *v4; // rsi
  int ProviderQueryEntry; // eax
  int PerUserSubKey; // esi
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ecx
  __int64 v10; // rcx
  int StateUpdateStub; // eax
  HANDLE ProcessHeap; // rax
  struct _SLIST_ENTRY *v13; // rax
  HANDLE v14; // rax
  _OWORD *v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // [rsp+28h] [rbp-80h]
  __int128 v20; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-58h] BYREF
  int *v22; // [rsp+60h] [rbp-48h]
  _QWORD *v23; // [rsp+88h] [rbp-20h]
  unsigned __int16 *v24; // [rsp+B0h] [rbp+8h] BYREF
  int v25; // [rsp+B8h] [rbp+10h] BYREF
  int v26; // [rsp+C0h] [rbp+18h]

  v24 = SRWLock;
  v3 = SRWLock;
  v25 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      a3,
      11,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v19,
      (char)SRWLock);
  try
  {
    v4 = (char *)operator new(0x70u);
    InitializeSRWLock((PSRWLOCK)v4);
    RtlInitializeGenericTableAvl((PRTL_AVL_TABLE)(v4 + 8), ObjectCompare, AllocateTableEntry, FreeTableEntry, 0);
    *((_QWORD *)v3 + 16) = v4;
    v20 = 0;
    ProviderQueryEntry = CreateProviderQueryEntry((__int64)v3, (__int64)&v20, 0, (__int64)(v3 + 72));
  }
  catch ( std::bad_alloc )
  {
    v26 = -2147024882;
    v3 = v24;
    PerUserSubKey = -2147024882;
    goto LABEL_35;
  }
  PerUserSubKey = ProviderQueryEntry;
  if ( !ProviderQueryEntry )
  {
    *((_QWORD *)v3 + 49) = *((_QWORD *)v3 + 23);
    PerUserSubKey = CQueryContext::AddNeedKeys((CQueryContext *)v3);
    if ( !PerUserSubKey )
    {
      v9 = *(_DWORD *)(*((_QWORD *)v3 + 17) + 16LL);
      if ( ((v9 - 5) & 0xFFFFFFFA) != 0
        || v9 == 9
        || (v21[0] = off_1800839E8,
            v21[1] = v3,
            v22 = &v25,
            v23 = v21,
            (PerUserSubKey = DAS::ProviderManagement::ProviderManager::ForEach(g_providerManager, v21)) == 0) )
      {
        v10 = *(unsigned int *)(*((_QWORD *)v3 + 17) + 16LL);
        if ( (unsigned int)(v10 - 5) <= 1 )
        {
          if ( *((_QWORD *)v3 + 2) )
          {
            v24 = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v24,
              0);
            PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(
                              *((const unsigned __int16 **)v3 + 2),
                              &v24);
            if ( PerUserSubKey < 0
              || (PerUserSubKey = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(
                                    g_StoreManager,
                                    -2147483645,
                                    v24,
                                    8),
                  PerUserSubKey < 0) )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v24);
              goto LABEL_35;
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v24);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
          {
            ProcessHeap = GetProcessHeap();
            v13 = (struct _SLIST_ENTRY *)HeapAlloc(ProcessHeap, 0, 0x40u);
            if ( !v13 )
            {
              PerUserSubKey = -2147024882;
              goto LABEL_35;
            }
            _InterlockedIncrement((volatile signed __int32 *)v3 + 113);
            *((_QWORD *)&v13[1].Next + 1) = v3;
            LODWORD(v13[1].Next) = 2;
            InterlockedPushEntrySList(g_QueryWorkItemList, v13);
            SubmitThreadpoolWork(g_QueryThreadpoolWork);
LABEL_17:
            if ( !v25 )
            {
LABEL_19:
              if ( PerUserSubKey >= 0
                && (unsigned int)UseRm()
                && *((_DWORD *)v3 + 126)
                && *((_DWORD *)v3 + 3)
                && (*(_BYTE *)(*((_QWORD *)v3 + 17) + 40LL) & 1) != 0 )
              {
                PerUserSubKey = CQueryContext::AcquireResource(v3);
              }
              goto LABEL_35;
            }
LABEL_18:
            PerUserSubKey = DAS::Dispatcher::Dispatch::StartProviderQueries((struct CQueryContext *)v3);
            goto LABEL_19;
          }
          memset_0(v21, 0, 0x40u);
          LODWORD(v22) = 2;
          StateUpdateStub = CQueryContext::SubmitWorkItem((PSRWLOCK)v3, (const struct _QUERY_WORK_ITEM *)v21);
        }
        else
        {
          if ( (_DWORD)v10 == 10 )
          {
            *(_DWORD *)(*((_QWORD *)v3 + 49) + 48LL) = 1;
            if ( v25 )
              goto LABEL_18;
          }
          else
          {
            if ( (_DWORD)v10 != 12 )
              goto LABEL_17;
            PerUserSubKey = DafGetProvidersInfo(
                              v10,
                              v7,
                              v8,
                              (__int64)v3,
                              (void (__fastcall *)(_QWORD, __int64, __int128 *))lambda_8c707c2317bbe6a0926c391432dd6ec0_::_lambda_invoker_cdecl_);
            if ( PerUserSubKey < 0 )
              goto LABEL_35;
            PerUserSubKey = *((_DWORD *)v3 + 112);
            if ( PerUserSubKey < 0 )
              goto LABEL_35;
          }
          StateUpdateStub = OnQueryStateUpdateStub(1, 4, *((_QWORD *)v3 + 49));
        }
        PerUserSubKey = StateUpdateStub;
        if ( StateUpdateStub < 0 )
          goto LABEL_35;
        goto LABEL_17;
      }
    }
  }
LABEL_35:
  if ( _InterlockedIncrement((volatile signed __int32 *)v3 + 120) == 2 )
  {
    CloseHandle(*((HANDLE *)v3 + 51));
    *((_QWORD *)v3 + 51) = 0;
  }
  if ( PerUserSubKey < 0 )
  {
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 0, 0x38u);
    if ( v15 )
    {
      *((_DWORD *)v3 + 50) = 2;
      *v15 = 0;
      v15[1] = 0;
      v15[2] = 0;
      *((_QWORD *)v15 + 6) = 0;
      *((_DWORD *)v15 + 6) = 2;
      CQueryContext::AddToResultSet((PSRWLOCK)v3, (struct _QUERY_RESULT *)v15);
    }
  }
  SetEvent(*((HANDLE *)v3 + 54));
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v18,
      12,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v19,
      (char)v3,
      PerUserSubKey);
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
    McTemplateU0p_EventWriteTransfer(v17, CREATE_QUERY_INCL_PROVIDERS_STOP, *((_QWORD *)v3 + 17));
}

```

## disassembly

```asm
0x1800272ec  mov     rax, rsp
0x1800272ef  mov     [rax+20h], rbx
0x1800272f3  mov     [rax+8], rcx
0x1800272f7  push    rsi
0x1800272f8  push    r12
0x1800272fa  push    r15
0x1800272fc  sub     rsp, 90h
0x180027303  mov     rbx, rcx
0x180027306  mov     dword ptr [rax+10h], 0
0x18002730d  lea     r12, WPP_RECORDER_INITIALIZED
0x180027314  lea     r15, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002731b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180027322  jz      short loc_180027344
0x180027324  mov     r9d, 0Bh; int
0x18002732a  mov     [rax-78h], rcx
0x18002732e  mov     [rsp+0A8h+TableContext], r15; MessageGuid
0x180027333  mov     rcx, cs:WPP_GLOBAL_Control
0x18002733a  mov     rcx, [rcx+28h]; int
0x18002733e  call    WPP_RECORDER_SF_sq
0x180027343  nop
0x180027344  mov     ecx, 70h ; 'p'; Size
0x180027349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002734e  mov     rsi, rax
0x180027351  mov     rcx, rax; SRWLock
0x180027354  call    cs:__imp_InitializeSRWLock
0x18002735a  lea     rcx, [rsi+8]; Table
0x18002735e  mov     [rsp+0A8h+TableContext], 0; TableContext
0x180027367  lea     r9, FreeTableEntry; FreeRoutine
0x18002736e  lea     r8, AllocateTableEntry; AllocateRoutine
0x180027375  lea     rdx, ObjectCompare; CompareRoutine
0x18002737c  call    cs:__imp_RtlInitializeGenericTableAvl
0x180027382  mov     [rbx+80h], rsi
0x180027389  xorps   xmm0, xmm0
0x18002738c  movdqu  [rsp+0A8h+var_68], xmm0
0x180027392  lea     r9, [rbx+90h]
0x180027399  xor     r8d, r8d
0x18002739c  lea     rdx, [rsp+0A8h+var_68]
0x1800273a1  mov     rcx, rbx
0x1800273a4  call    ?CreateProviderQueryEntry@@YAJPEAXV?$shared_ptr@VProviderContext@@@std@@KPEAU_DAS_LOCKED_LIST@@0PEAPEAU_PROVIDER_QUERY_ENTRY@@@Z; CreateProviderQueryEntry(void *,std::shared_ptr<ProviderContext>,ulong,_DAS_LOCKED_LIST *,void *,_PROVIDER_QUERY_ENTRY * *)
0x1800273a9  mov     esi, eax
0x1800273ab  test    eax, eax
0x1800273ad  jnz     loc_180027651
0x1800273b3  mov     rax, [rbx+0B8h]
0x1800273ba  mov     [rbx+188h], rax
0x1800273c1  mov     rcx, rbx; this
0x1800273c4  call    ?AddNeedKeys@CQueryContext@@IEAAJXZ; CQueryContext::AddNeedKeys(void)
0x1800273c9  mov     esi, eax
0x1800273cb  test    eax, eax
0x1800273cd  jnz     loc_180027651
0x1800273d3  mov     rax, [rbx+88h]
0x1800273da  mov     ecx, [rax+10h]
0x1800273dd  lea     eax, [rcx-5]
0x1800273e0  test    eax, 0FFFFFFFAh
0x1800273e5  jnz     short loc_180027432
0x1800273e7  cmp     ecx, 9
0x1800273ea  jz      short loc_180027432
0x1800273ec  lea     rax, off_1800839E8
0x1800273f3  mov     [rsp+0A8h+var_58], rax
0x1800273f8  mov     [rsp+0A8h+var_50], rbx
0x1800273fd  lea     rax, [rsp+0A8h+arg_8]
0x180027405  mov     [rsp+0A8h+var_48], rax
0x18002740a  lea     rax, [rsp+0A8h+var_58]
0x18002740f  mov     [rsp+0A8h+var_20], rax
0x180027417  lea     rdx, [rsp+0A8h+var_58]
0x18002741c  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x180027423  call    ?ForEach@ProviderManager@ProviderManagement@DAS@@QEAAJV?$function@$$A6AJV?$shared_ptr@VProviderContext@@@std@@AEA_N@Z@std@@@Z; DAS::ProviderManagement::ProviderManager::ForEach(std::function<long (std::shared_ptr<ProviderContext>,bool &)>)
0x180027428  mov     esi, eax
0x18002742a  test    eax, eax
0x18002742c  jnz     loc_180027651
0x180027432  mov     rax, [rbx+88h]
0x180027439  mov     ecx, [rax+10h]
0x18002743c  lea     eax, [rcx-5]
0x18002743f  cmp     eax, 1
0x180027442  jbe     loc_180027516
0x180027448  cmp     ecx, 0Ah
0x18002744b  jnz     short loc_180027467
0x18002744d  mov     rax, [rbx+188h]
0x180027454  mov     dword ptr [rax+30h], 1
0x18002745b  cmp     [rsp+0A8h+arg_8], 0
0x180027463  jnz     short loc_1800274C0
0x180027465  jmp     short loc_180027498
0x180027467  cmp     ecx, 0Ch
0x18002746a  jnz     short loc_1800274B6
0x18002746c  lea     rax, _lambda_8c707c2317bbe6a0926c391432dd6ec0____lambda_invoker_cdecl_
0x180027473  mov     [rsp+0A8h+TableContext], rax
0x180027478  mov     r9, rbx
0x18002747b  call    DafGetProvidersInfo
0x180027480  mov     esi, eax
0x180027482  test    eax, eax
0x180027484  js      loc_180027651
0x18002748a  mov     esi, [rbx+1C0h]
0x180027490  test    esi, esi
0x180027492  js      loc_180027651
0x180027498  mov     r8, [rbx+188h]
0x18002749f  mov     edx, 4
0x1800274a4  lea     ecx, [rdx-3]
0x1800274a7  call    ?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z; OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)
0x1800274ac  mov     esi, eax
0x1800274ae  test    eax, eax
0x1800274b0  js      loc_180027651
0x1800274b6  cmp     [rsp+0A8h+arg_8], 0
0x1800274be  jz      short loc_1800274CA
0x1800274c0  mov     rcx, rbx; struct CQueryContext *
0x1800274c3  call    ?StartProviderQueries@Dispatch@Dispatcher@DAS@@SAJPEAVCQueryContext@@@Z; DAS::Dispatcher::Dispatch::StartProviderQueries(CQueryContext *)
0x1800274c8  mov     esi, eax
0x1800274ca  test    esi, esi
0x1800274cc  js      loc_180027651
0x1800274d2  call    ?UseRm@@YAHXZ; UseRm(void)
0x1800274d7  test    eax, eax
0x1800274d9  jz      loc_180027651
0x1800274df  cmp     dword ptr [rbx+1F8h], 0
0x1800274e6  jz      loc_180027651
0x1800274ec  cmp     dword ptr [rbx+0Ch], 0
0x1800274f0  jz      loc_180027651
0x1800274f6  mov     rax, [rbx+88h]
0x1800274fd  test    byte ptr [rax+28h], 1
0x180027501  jz      loc_180027651
0x180027507  mov     rcx, rbx; pv
0x18002750a  call    ?AcquireResource@CQueryContext@@IEAAJXZ; CQueryContext::AcquireResource(void)
0x18002750f  mov     esi, eax
0x180027511  jmp     loc_180027651
0x180027516  cmp     qword ptr [rbx+10h], 0
0x18002751b  jz      loc_1800275A5
0x180027521  mov     [rsp+0A8h+arg_0], 0
0x18002752d  xor     edx, edx
0x18002752f  lea     rcx, [rsp+0A8h+arg_0]
0x180027537  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002753c  lea     rdx, [rsp+0A8h+arg_0]; unsigned __int16 **
0x180027544  mov     rcx, [rbx+10h]; Src
0x180027548  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x18002754d  mov     esi, eax
0x18002754f  test    eax, eax
0x180027551  jns     short loc_180027565
0x180027553  lea     rcx, [rsp+0A8h+arg_0]
0x18002755b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027560  jmp     loc_180027651
0x180027565  lea     rax, [rbx+230h]
0x18002756c  mov     [rsp+0A8h+TableContext], rax
0x180027571  mov     r9d, 8
0x180027577  mov     r8, [rsp+0A8h+arg_0]
0x18002757f  mov     rdx, 0FFFFFFFF80000003h
0x180027586  mov     rcx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x18002758d  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180027592  mov     esi, eax
0x180027594  lea     rcx, [rsp+0A8h+arg_0]
0x18002759c  test    eax, eax
0x18002759e  js      short loc_18002755B
0x1800275a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800275a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x1800275ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x1800275b1  test    al, al
0x1800275b3  jnz     short loc_18002760A
0x1800275b5  call    cs:__imp_GetProcessHeap
0x1800275bb  mov     rcx, rax; hHeap
0x1800275be  xor     edx, edx; dwFlags
0x1800275c0  lea     r8d, [rdx+40h]; dwBytes
0x1800275c4  call    cs:__imp_HeapAlloc
0x1800275ca  test    rax, rax
0x1800275cd  jnz     short loc_1800275D6
0x1800275cf  mov     esi, 8007000Eh
0x1800275d4  jmp     short loc_180027651
0x1800275d6  lock inc dword ptr [rbx+1C4h]
0x1800275dd  mov     [rax+18h], rbx
0x1800275e1  mov     dword ptr [rax+10h], 2
0x1800275e8  mov     rdx, rax; ListEntry
0x1800275eb  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800275f2  call    cs:__imp_InterlockedPushEntrySList
0x1800275f8  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x1800275ff  call    cs:__imp_SubmitThreadpoolWork
0x180027605  jmp     loc_1800274B6
0x18002760a  xor     edx, edx; Val
0x18002760c  lea     r8d, [rdx+40h]; Size
0x180027610  lea     rcx, [rsp+0A8h+var_58]; void *
0x180027615  call    memset_0
0x18002761a  mov     dword ptr [rsp+0A8h+var_48], 2
0x180027622  lea     rdx, [rsp+0A8h+var_58]; struct _QUERY_WORK_ITEM *
0x180027627  mov     rcx, rbx; SRWLock
0x18002762a  call    ?SubmitWorkItem@CQueryContext@@IEAAJAEBU_QUERY_WORK_ITEM@@@Z; CQueryContext::SubmitWorkItem(_QUERY_WORK_ITEM const &)
0x18002762f  jmp     loc_1800274AC
0x180027634  lea     r12, WPP_RECORDER_INITIALIZED
0x18002763b  lea     r15, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180027642  mov     rbx, [rsp+0A8h+arg_0]
0x18002764a  mov     esi, [rsp+0A8h+arg_10]
0x180027651  mov     eax, 1
0x180027656  lock xadd [rbx+1E0h], eax
0x18002765e  inc     eax
0x180027660  cmp     eax, 2
0x180027663  jnz     short loc_18002767D
0x180027665  mov     rcx, [rbx+198h]; hObject
0x18002766c  call    cs:__imp_CloseHandle
0x180027672  mov     qword ptr [rbx+198h], 0
0x18002767d  test    esi, esi
0x18002767f  jns     short loc_1800276CB
0x180027681  call    cs:__imp_GetProcessHeap
0x180027687  mov     rcx, rax; hHeap
0x18002768a  xor     edx, edx; dwFlags
0x18002768c  lea     r8d, [rdx+38h]; dwBytes
0x180027690  call    cs:__imp_HeapAlloc
0x180027696  test    rax, rax
0x180027699  jz      short loc_1800276CB
0x18002769b  mov     dword ptr [rbx+0C8h], 2
0x1800276a5  xorps   xmm0, xmm0
0x1800276a8  xor     ecx, ecx
0x1800276aa  movups  xmmword ptr [rax], xmm0
0x1800276ad  movups  xmmword ptr [rax+10h], xmm0
0x1800276b1  movups  xmmword ptr [rax+20h], xmm0
0x1800276b5  mov     [rax+30h], rcx
0x1800276b9  mov     dword ptr [rax+18h], 2
0x1800276c0  mov     rdx, rax; struct _QUERY_RESULT *
0x1800276c3  mov     rcx, rbx; SRWLock
0x1800276c6  call    ?AddToResultSet@CQueryContext@@QEAAJPEAU_QUERY_RESULT@@@Z; CQueryContext::AddToResultSet(_QUERY_RESULT *)
0x1800276cb  mov     rcx, [rbx+1B0h]; hEvent
0x1800276d2  call    cs:__imp_SetEvent
0x1800276d8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800276df  jz      short loc_180027705
0x1800276e1  mov     r9d, 0Ch; int
0x1800276e7  mov     dword ptr [rsp+0A8h+var_70], esi; char
0x1800276eb  mov     qword ptr [rsp+0A8h+var_78], rbx; char
0x1800276f0  mov     [rsp+0A8h+TableContext], r15; MessageGuid
0x1800276f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276fc  mov     rcx, [rcx+28h]; int
0x180027700  call    WPP_RECORDER_SF_sqd
0x180027705  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x18002770c  jz      short loc_180027722
0x18002770e  mov     r8, [rbx+88h]
0x180027715  lea     rdx, CREATE_QUERY_INCL_PROVIDERS_STOP
0x18002771c  call    McTemplateU0p_EventWriteTransfer
0x180027721  nop
0x180027722  mov     rbx, [rsp+0A8h+arg_18]
0x18002772a  add     rsp, 90h
0x180027731  pop     r15
0x180027733  pop     r12
0x180027735  pop     rsi
0x180027736  retn
```
