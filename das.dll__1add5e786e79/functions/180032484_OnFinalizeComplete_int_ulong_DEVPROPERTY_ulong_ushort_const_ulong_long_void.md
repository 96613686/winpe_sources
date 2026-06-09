# OnFinalizeComplete(int,ulong,_DEVPROPERTY *,ulong,ushort const * *,ulong,long,void *)

- ea: `0x180032484`
- end: `0x180033468`
- name: `?OnFinalizeComplete@@YAJHKPEAU_DEVPROPERTY@@KPEAPEBGKJPEAX@Z`
- size: `4068`
- prototype: `__int64 __fastcall(int, unsigned int, struct _DEVPROPERTY *, unsigned int, const unsigned __int16 **, unsigned int, int Reply, void *)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800493a0`

## callees

- `0x180005770`
- `0x180005c5c`
- `0x1800074c0`
- `0x180009220`
- `0x180009590`
- `0x1800122f4`
- `0x180019d00`
- `0x18001a268`
- `0x18001eae0`
- `0x180024d60`
- `0x180027750`
- `0x180027b2c`
- `0x180028ed8`
- `0x1800290c4`
- `0x18002be5c`
- `0x1800306d8`
- `0x180031f24`
- `0x180032484`
- `0x180033470`
- `0x1800335bc`
- `0x1800336d8`
- `0x1800345f0`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180057f14`
- `0x1800582b0`
- `0x1800587a8`
- `0x180058c18`
- `0x180059290`
- `0x18005e3f8`
- `0x18007e9cc`
- `0x18007e9d8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032f8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032f8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032610`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032f13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032610`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032f13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800325aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800325aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800326e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800326e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032fa0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180032f08`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180032f08`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180032ecb`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180032ecb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180032506`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180032506`

## string_xrefs

- `0x180032d0d`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x18003321e`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall OnFinalizeComplete(
        int a1,
        unsigned int a2,
        struct _DEVPROPERTY *a3,
        unsigned int a4,
        const unsigned __int16 **a5,
        unsigned int a6,
        int Reply,
        char *a8)
{
  __int64 v8; // r12
  __int64 v9; // r13
  char *v11; // rdi
  unsigned int v12; // r15d
  struct _DEVPROPERTY *v13; // r14
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // rax
  const wchar_t **v17; // rax
  const wchar_t *v18; // rax
  unsigned int v19; // ebx
  int v20; // edx
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // ebx
  int ProviderFromAepId; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  bool v28; // sf
  __int64 v29; // r15
  HANDLE ProcessHeap; // rax
  struct _DEVPROPERTY *v31; // rax
  __int64 v32; // rbx
  int v33; // edx
  int v34; // r8d
  int PerUserSubKey; // eax
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  PSRWLOCK v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  unsigned int i; // r13d
  char *v44; // rbx
  UCHAR *v45; // rdx
  unsigned __int64 v46; // r8
  int v47; // eax
  unsigned int j; // ebx
  struct _DEVPROPERTY *v49; // r13
  Windows::Devices::Pnp::Internal::PnpObjectStore *v50; // rcx
  int v51; // ecx
  const wchar_t *v52; // rax
  const unsigned __int16 *v53; // rdx
  int v54; // eax
  int v55; // edx
  int v56; // r8d
  int v57; // edx
  int v58; // r8d
  void *v59; // rax
  int v60; // edx
  int v61; // r8d
  int v62; // r9d
  void *v63; // rdx
  const unsigned __int16 **v64; // r13
  __int64 v65; // rcx
  int v66; // r8d
  void *v67; // rcx
  const unsigned __int16 *v68; // rdx
  __int64 v69; // r8
  int v70; // eax
  unsigned int v71; // ebx
  wil::details *v72; // rcx
  _DWORD *v73; // rcx
  _DWORD *v74; // rax
  int *p_Reply; // rdx
  int v76; // ebx
  int v77; // edx
  int v78; // r8d
  void *v79; // rcx
  char LastError; // al
  int v81; // edx
  int v82; // r8d
  void *v83; // r9
  int v84; // r15d
  const unsigned __int16 *v85; // r8
  int started; // eax
  int v87; // edx
  int v88; // r8d
  unsigned int v89; // r13d
  int v90; // eax
  int v91; // edx
  const wchar_t *v92; // rcx
  const wchar_t *v93; // rax
  int ProcessName; // eax
  __int64 v95; // rcx
  char v96; // r10
  char v97; // r11
  const char *v98; // r8
  const char *v99; // rax
  const char *v100; // rdx
  const char *v101; // rcx
  __int64 *v102; // rdx
  const char *v103; // r8
  const char *v104; // rax
  const char *v105; // rdx
  const char *v106; // rcx
  HANDLE v107; // rax
  unsigned int v108; // ebx
  LPCGUID MessageGuid; // [rsp+28h] [rbp-E0h]
  char v111; // [rsp+40h] [rbp-C8h]
  int v112; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v113[4]; // [rsp+8Ch] [rbp-7Ch] BYREF
  unsigned int v114; // [rsp+90h] [rbp-78h] BYREF
  int v115; // [rsp+94h] [rbp-74h] BYREF
  int v116; // [rsp+98h] [rbp-70h]
  Windows::Devices::Pnp::Internal::PnpObjectStore *v117; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v118; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int NotificationsQueued; // [rsp+B0h] [rbp-58h] BYREF
  void *Src; // [rsp+B8h] [rbp-50h]
  std::_Ref_count_base *v121[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v122; // [rsp+D0h] [rbp-38h]
  __int64 v123; // [rsp+D8h] [rbp-30h]
  const unsigned __int16 **v124; // [rsp+E0h] [rbp-28h]
  __int128 v125; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR Filename[264]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+360h] [rbp+258h]

  v8 = a4;
  Src = a3;
  v9 = a2;
  NotificationsQueued = a2;
  v116 = a1;
  v124 = a5;
  v11 = a8;
  v12 = 0;
  v112 = 0;
  v115 = 1;
  *(_OWORD *)v121 = 0;
  v13 = 0;
  v114 = 0;
  EventActivityIdControl(2u, (LPGUID)(a8 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v14, ASSOC_FINALIZE_PROVIDER_STOP, v11);
  if ( Reply >= 0 )
  {
    ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(
                          g_providerManager,
                          *((_QWORD *)v11 + 1),
                          v121);
    v112 = ProviderFromAepId;
    if ( ProviderFromAepId < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v27 = 147;
        v111 = ProviderFromAepId;
LABEL_18:
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v25,
          v26,
          v27,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)v11 + 1),
          (char)v11,
          v111);
      }
LABEL_10:
      v19 = a6;
      goto LABEL_11;
    }
    if ( Reply == 1 || *((_DWORD *)v121[0] + 19) )
    {
      v115 = 0;
    }
    else
    {
      v28 = ProviderFromAepId < 0;
      if ( ProviderFromAepId )
        goto LABEL_74;
      v29 = (unsigned int)v9 + (a1 != 0 ? 4 : 1);
      v113[0] = -1;
      LODWORD(v118) = 16;
      LODWORD(v117) = a1 != 0;
      ProcessHeap = GetProcessHeap();
      v31 = (struct _DEVPROPERTY *)HeapAlloc(ProcessHeap, 0, 48 * v29);
      v13 = v31;
      if ( !v31 )
      {
        v112 = -2147024882;
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_10;
        v27 = 148;
        v111 = 14;
        goto LABEL_18;
      }
      v32 = v9;
      memcpy_0(v31, Src, 48 * v9);
      v13[v32].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsAssociated;
      v13[v32].CompKey.Key.pid = (unsigned int)v118;
      v13[v32].CompKey.Store = (int)v117;
      v13[v32].CompKey.LocaleName = 0;
      v13[v32].Type = 17;
      v13[v32].BufferSize = 1;
      v13[v32].Buffer = v113;
      if ( v116 )
      {
        v117 = 0;
        if ( !*((_QWORD *)v11 + 2) )
        {
          v112 = -2140930011;
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_SqD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v33,
              v34,
              149,
              &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
              *((_QWORD *)v11 + 1),
              (char)v11,
              37);
          goto LABEL_29;
        }
        v118 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v118,
          0);
        PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(
                          *((const unsigned __int16 **)v11 + 2),
                          &v118);
        v112 = PerUserSubKey;
        if ( PerUserSubKey >= 0 )
        {
          v39 = g_StoreManager;
          Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v117);
          MessageGuid = (LPCGUID)&v117;
          PerUserSubKey = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v39, -2147483645, v118, 8);
          v112 = PerUserSubKey;
          v37 = 0;
          if ( PerUserSubKey >= 0 )
          {
            v40 = (unsigned int)(v9 + 1);
            v13[v40].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsAssociatedPerUser;
            v13[v40].CompKey.Key.pid = 20;
            v13[v40].CompKey.Store = DEVPROP_STORE_SYSTEM;
            v13[v40].CompKey.LocaleName = 0;
            v13[v40].Type = 17;
            v13[v40].BufferSize = 1;
            v13[v40].Buffer = v113;
            v125 = 0;
            v41 = (unsigned int)(v9 + 2);
            v122 = v41 * 48;
            v13[v41].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_ContainerId;
            v13[v41].CompKey.Key.pid = 2;
            v13[v41].CompKey.Store = DEVPROP_STORE_USER;
            v13[v41].CompKey.LocaleName = 0;
            v13[v41].Type = 13;
            v13[v41].BufferSize = 16;
            v13[v41].Buffer = 0;
            v42 = (unsigned int)(v9 + 3);
            v123 = v42 * 48;
            v13[v42].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_SystemContainerId;
            v13[v42].CompKey.Key.pid = 10;
            v13[v42].CompKey.Store = DEVPROP_STORE_USER;
            v13[v42].CompKey.LocaleName = 0;
            v13[v42].Type = 13;
            v13[v42].BufferSize = 16;
            v13[v42].Buffer = 0;
            for ( i = 0; ; ++i )
            {
              if ( i >= NotificationsQueued )
                goto LABEL_54;
              v44 = (char *)Src + 48 * i;
              if ( *((_DWORD *)v44 + 4) == 2
                && !memcmp_0((char *)Src + 48 * i, &DEVPKEY_Aep_ContainerId, 0x10u)
                && !*((_DWORD *)v44 + 5)
                && *((_DWORD *)v44 + 8) == 13 )
              {
                break;
              }
            }
            v45 = (UCHAR *)*((_QWORD *)v11 + 2);
            v46 = -1;
            do
              ++v46;
            while ( *(_WORD *)&v45[2 * v46] );
            if ( v46 >= 0x7FFFFFFF )
            {
              LOBYTE(v47) = 87;
              v112 = -2147024809;
            }
            else
            {
              v47 = DafClass5GuidFromBlob(*((__int128 **)v44 + 5), v45, 2 * (int)v46, &v125);
              v112 = v47;
              if ( v47 >= 0 )
              {
                *(PVOID *)((char *)&v13->Buffer + v122) = &v125;
                *(PVOID *)((char *)&v13->Buffer + v123) = (PVOID)*((_QWORD *)v44 + 5);
LABEL_54:
                for ( j = 0; ; ++j )
                {
                  if ( j >= (unsigned int)v29 )
                  {
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v118);
                    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v117);
                    v53 = (const unsigned __int16 *)*((_QWORD *)v11 + 2);
                    goto LABEL_69;
                  }
                  v49 = &v13[j];
                  v50 = v117;
                  if ( v49->CompKey.Store == DEVPROP_STORE_SYSTEM )
                    v50 = g_AepStore;
                  v51 = Windows::Devices::Pnp::Internal::PnpObjectStore::SetProperties(
                          v50,
                          *((const unsigned __int16 **)v11 + 1),
                          1,
                          1u,
                          &v13[j]);
                  v112 = v51;
                  if ( v51 < 0 )
                    break;
                }
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v52 = L"per-user";
                  if ( v49->CompKey.Store )
                    v52 = L"system";
                  WPP_RECORDER_SF_SSqD(
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    (int)L"system",
                    0,
                    153,
                    &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
                    *((_QWORD *)v11 + 1),
                    (__int64)v52,
                    (char)v11,
                    v51);
                }
                goto LABEL_34;
              }
            }
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_SSqD(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                (int)v45,
                v46,
                152,
                &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
                *((_QWORD *)v11 + 1),
                *((_QWORD *)v11 + 2),
                (char)v11,
                v47);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v118);
            Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v117);
            goto LABEL_10;
          }
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v38 = 151;
            goto LABEL_33;
          }
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v38 = 150;
LABEL_33:
          WPP_RECORDER_SF_SSqD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v36,
            v37,
            v38,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            *((_QWORD *)v11 + 1),
            *((_QWORD *)v11 + 2),
            (char)v11,
            PerUserSubKey);
        }
LABEL_34:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v118);
LABEL_29:
        Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v117);
        goto LABEL_10;
      }
      v54 = Windows::Devices::Pnp::Internal::PnpObjectStore::SetProperties(
              g_AepStore,
              *((const unsigned __int16 **)v11 + 1),
              1,
              v29,
              v13);
      v112 = v54;
      if ( v54 < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_SqD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v55,
            v56,
            154,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            *((_QWORD *)v11 + 1),
            (char)v11,
            v54);
        goto LABEL_10;
      }
      v53 = 0;
LABEL_69:
      DAS::Dispatcher::Dispatch::ExternalAepStoreChange(*((const unsigned __int16 **)v11 + 1), v53, 1u, v29, v13);
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v57,
          v58,
          155,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)v11 + 1),
          (char)v11);
      ProviderFromAepId = v112;
      v12 = 0;
    }
    v28 = ProviderFromAepId < 0;
LABEL_74:
    if ( !v28 )
    {
      if ( (_DWORD)v8 )
      {
        v59 = (void *)DAF_user_alloc(8 * v8);
        *((_QWORD *)v11 + 51) = v59;
        if ( v59 )
        {
          memset_0(v59, 0, 8 * v8);
          v64 = v124;
          while ( v12 < (unsigned int)v8 )
          {
            if ( (unsigned int)DafGetTypeFromId_1(v64[v12]) == 5 )
            {
              v65 = -1;
              do
                ++v65;
              while ( v64[v12][v65] );
              *(_QWORD *)(*((_QWORD *)v11 + 51) + 8LL * v12) = DAF_user_alloc(2 * v65 + 2);
              v67 = *(void **)(*((_QWORD *)v11 + 51) + 8LL * v12);
              if ( !v67 )
              {
                v112 = -2147024882;
                if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                  goto LABEL_94;
                WPP_RECORDER_SF_SSqD(
                  *((_QWORD *)WPP_GLOBAL_Control + 5),
                  (int)v63,
                  v66,
                  157,
                  &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
                  *((_QWORD *)v11 + 1),
                  (__int64)v64[v12],
                  (char)v11,
                  14);
                break;
              }
              v68 = v64[v12];
              v69 = -1;
              do
                ++v69;
              while ( v68[v69] );
              memcpy_0(v67, v68, 2 * v69 + 2);
            }
            else
            {
              v70 = DafConcatenateWithDelimiter_2(*(unsigned __int16 **)v121[0], (unsigned __int16 *)v64[v12]);
              if ( v70 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xB83,
                  (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
                  (const char *)(unsigned int)v70);
            }
            ++v12;
          }
          if ( v112 != -2147024882 )
          {
            *((_DWORD *)v11 + 100) = v8;
            goto LABEL_100;
          }
LABEL_94:
          v71 = 0;
          do
          {
            v72 = *(wil::details **)(*((_QWORD *)v11 + 51) + 8LL * v71);
            if ( v72 )
              wil::details::FreeProcessHeap(v72, v63);
            ++v71;
          }
          while ( v71 < (unsigned int)v8 );
          wil::details::FreeProcessHeap(*((wil::details **)v11 + 51), v63);
          *((_QWORD *)v11 + 51) = 0;
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_SdqD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v60,
            v61,
            v62,
            (_DWORD)MessageGuid,
            *((_QWORD *)v11 + 1),
            v8,
            (char)v11,
            v112);
        }
        goto LABEL_10;
      }
LABEL_100:
      v19 = a6;
      *((_DWORD *)v11 + 101) = a6;
      goto LABEL_11;
    }
    goto LABEL_10;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v16 = *((_QWORD *)v11 + 46);
    if ( !v16 || (v17 = *(const wchar_t ***)(v16 + 24)) == 0 || (v18 = *v17) == 0 )
      v18 = L"unknown";
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)&WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      v15,
      146,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      (__int64)v18,
      (char)v11,
      Reply);
    goto LABEL_10;
  }
  v19 = a6;
LABEL_11:
  AcquireSRWLockExclusive((PSRWLOCK)v11 + 6);
  if ( *((_DWORD *)v11 + 10) )
  {
    *((_DWORD *)v11 + 7) = -1;
    v112 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v20,
        v22,
        158,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)v11 + 1),
        (char)v11,
        26);
    *((_DWORD *)v11 + 10) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v11 + 6);
    v23 = v115;
    goto LABEL_157;
  }
  if ( !*((_DWORD *)v11 + 9) )
  {
    if ( !*((_QWORD *)v11 + 21) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v21);
    if ( v112 || Reply < 0 )
    {
      *((_DWORD *)v11 + 7) = -1;
      v74 = (_DWORD *)*((_QWORD *)v11 + 21);
      if ( v74 )
        *v74 = -1;
    }
    else
    {
      *((_DWORD *)v11 + 7) = 6;
      v73 = (_DWORD *)*((_QWORD *)v11 + 21);
      if ( v73 )
      {
        if ( v115 )
          *v73 = v19 != 0 ? 2 : 0;
        else
          *v73 = 1;
      }
    }
    if ( *((_DWORD *)v11 + 94) )
    {
      NotificationsQueued = 0;
      RpcServerUnsubscribeForNotification(
        *(RPC_BINDING_HANDLE *)(*((_QWORD *)v11 + 25) + 32LL),
        RpcNotificationCallCancel,
        &NotificationsQueued);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    *((_DWORD *)v11 + 9) = 1;
    if ( Reply < 0 || (p_Reply = &v112, v112 >= 0) )
      p_Reply = &Reply;
    v76 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)v11 + 25), p_Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)v11 + 6);
    if ( !v76 || v76 == 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v77,
          v78,
          161,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)v11 + 1),
          (char)v11);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v77,
          v78,
          160,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)v11 + 1),
          (char)v11,
          v76);
      if ( v76 >= 0 )
        v76 = (unsigned __int16)v76 | 0x80010000;
      v112 = v76;
    }
    v79 = (void *)*((_QWORD *)v11 + 54);
    if ( v79 && !SetEvent(v79) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LastError = GetLastError();
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v81,
        v82,
        162,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)v11 + 1),
        (char)v11,
        LastError);
    }
    v23 = v115;
    if ( !v112 && !Reply )
    {
      if ( v115 )
      {
        if ( *((_DWORD *)v11 + 104) == 1 )
          v83 = (void *)*((_QWORD *)v11 + 56);
        else
          v83 = 0;
        v84 = v116;
        if ( v116 )
          v85 = (const unsigned __int16 *)*((_QWORD *)v11 + 2);
        else
          v85 = 0;
        started = DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagement(
                    g_devnodeManager,
                    *((const unsigned __int16 **)v11 + 1),
                    v85,
                    v83);
        v112 = started;
        if ( started >= 0 )
        {
          v89 = 1;
          v114 = 0;
          v115 = 0;
          v90 = DasEvaluateServiceLifetime(&v114, &v115);
          v91 = v90;
          if ( v90 >= 0 )
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v92 = L"armed";
              if ( !v115 )
                v92 = (const wchar_t *)L"disarmed";
              v93 = L"auto";
              if ( v114 != 2 )
                v93 = (const wchar_t *)L"trigger";
              WPP_RECORDER_SF_SSSSqD(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                v91,
                (int)L"trigger",
                165,
                &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
                *((_QWORD *)v11 + 1),
                *((_QWORD *)v11 + 2),
                (__int64)v93,
                (__int64)v92,
                (char)v11,
                v91);
            }
          }
          else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_SSqD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v90,
              0,
              164,
              &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
              *((_QWORD *)v11 + 1),
              *((_QWORD *)v11 + 2),
              (char)v11,
              v90);
          }
LABEL_159:
          memset_0(Filename, 0, 0x208u);
          ProcessName = GetProcessName(*((_DWORD *)v11 + 16), Filename);
          v95 = 0;
          if ( ProcessName < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xC04,
              (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
              (const char *)(unsigned int)ProcessName);
            v95 = 0;
          }
          v96 = Reply;
          v97 = v112;
          if ( v112 < 0 || Reply < 0 )
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v103 = (const char *)&byte_18008E598;
              v104 = (const char *)&byte_18008E598;
              if ( !(_DWORD)v8 )
                v104 = "not ";
              v105 = (const char *)&byte_18008E598;
              if ( !v84 )
                v105 = "not ";
              v106 = (const char *)&byte_18008E598;
              if ( !v89 )
                v106 = "not ";
              if ( !v23 )
                v103 = "not ";
              WPP_RECORDER_SF_SSdsssSsDD(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                (_DWORD)v105,
                (_DWORD)v103,
                (unsigned int)"not ",
                (__int64)MessageGuid,
                *((_QWORD *)v11 + 1),
                (__int64)Filename,
                *((_DWORD *)v11 + 16),
                (__int64)v103,
                (__int64)v106,
                (__int64)v105,
                *((_QWORD *)v11 + 2),
                (__int64)v104,
                v112,
                Reply);
              v96 = Reply;
              v97 = v112;
              v95 = 0;
            }
            if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) == 0 )
              goto LABEL_188;
            v102 = ASSOCIATION_FAILURE;
          }
          else
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v98 = (const char *)&byte_18008E598;
              v99 = (const char *)&byte_18008E598;
              if ( !(_DWORD)v8 )
                v99 = "not ";
              v100 = (const char *)&byte_18008E598;
              if ( !v84 )
                v100 = "not ";
              v101 = (const char *)&byte_18008E598;
              if ( !v89 )
                v101 = "not ";
              if ( !v23 )
                v98 = "not ";
              WPP_RECORDER_SF_SSdsssSs(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                (_DWORD)v100,
                (_DWORD)v98,
                (unsigned int)"not ",
                (__int64)MessageGuid,
                *((_QWORD *)v11 + 1),
                (__int64)Filename,
                *((_DWORD *)v11 + 16),
                (__int64)v98,
                (__int64)v101,
                (__int64)v100,
                *((_QWORD *)v11 + 2),
                (__int64)v99);
              v96 = Reply;
              v97 = v112;
              v95 = 0;
            }
            if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 1) == 0 )
              goto LABEL_188;
            v102 = ASSOCIATION_SUCCESS;
          }
          McTemplateU0zzqtttztqq_EventWriteTransfer(
            0,
            (_DWORD)v102,
            *((_QWORD *)v11 + 1),
            (unsigned int)Filename,
            *((_DWORD *)v11 + 16),
            v23,
            v89,
            v84,
            *((_QWORD *)v11 + 2),
            (_DWORD)v8 != 0,
            v97,
            v96);
LABEL_188:
          if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
            McTemplateU0p_EventWriteTransfer(v95, ASSOC_FINALIZE_STOP, v11);
          (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
          goto LABEL_191;
        }
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_SSqD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v87,
            v88,
            163,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            *((_QWORD *)v11 + 1),
            *((_QWORD *)v11 + 2),
            (char)v11,
            started);
LABEL_158:
        v89 = v114;
        goto LABEL_159;
      }
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v77,
          v78,
          166,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)v11 + 1),
          (char)v11);
    }
LABEL_157:
    v84 = v116;
    goto LABEL_158;
  }
  v112 = -2147418113;
  *((_DWORD *)v11 + 7) = -1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v22,
      159,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)v11 + 1),
      (char)v11,
      255);
  ReleaseSRWLockExclusive((PSRWLOCK)v11 + 6);
LABEL_191:
  if ( v13 )
  {
    v107 = GetProcessHeap();
    HeapFree(v107, 0, v13);
  }
  v108 = v112;
  if ( v121[1] )
    std::_Ref_count_base::_Decref(v121[1]);
  return v108;
}

```

## disassembly

```asm
0x180032484  mov     rax, rsp
0x180032487  mov     [rax+8], rbx
0x18003248b  push    rbp
0x18003248c  push    rsi
0x18003248d  push    rdi
0x18003248e  push    r12
0x180032490  push    r13
0x180032492  push    r14
0x180032494  push    r15
0x180032496  lea     rbp, [rax-258h]
0x18003249d  sub     rsp, 320h
0x1800324a4  movaps  xmmword ptr [rax-48h], xmm6
0x1800324a8  mov     rax, cs:__security_cookie
0x1800324af  xor     rax, rsp
0x1800324b2  mov     [rbp+250h+var_50], rax
0x1800324b9  mov     r12d, r9d
0x1800324bc  mov     [rbp+250h+Src], r8
0x1800324c0  mov     r13d, edx
0x1800324c3  mov     [rbp+250h+NotificationsQueued], r13d
0x1800324c7  mov     ebx, ecx
0x1800324c9  mov     [rbp+250h+var_2C0], ecx
0x1800324cc  mov     rax, [rbp+250h+arg_20]
0x1800324d3  mov     [rbp+250h+var_278], rax
0x1800324d7  mov     rdi, [rbp+250h+arg_38]
0x1800324de  xor     r15d, r15d
0x1800324e1  mov     [rbp+250h+var_2D0], r15d
0x1800324e5  mov     [rbp+250h+var_2C4], 1
0x1800324ec  xorps   xmm0, xmm0
0x1800324ef  movdqu  xmmword ptr [rbp+250h+var_298], xmm0
0x1800324f4  mov     r14d, r15d
0x1800324f7  mov     [rbp+250h+var_2C8], r15d
0x1800324fb  lea     rdx, [rdi+15Ch]; ActivityId
0x180032502  lea     ecx, [r15+2]; ControlCode
0x180032506  call    cs:__imp_EventActivityIdControl
0x18003250c  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180032513  jz      short loc_180032524
0x180032515  mov     r8, rdi
0x180032518  lea     rdx, ASSOC_FINALIZE_PROVIDER_STOP
0x18003251f  call    McTemplateU0p_EventWriteTransfer
0x180032524  lea     rdx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids; int
0x18003252b  mov     ecx, [rbp+250h+Reply]
0x180032531  test    ecx, ecx
0x180032533  jns     loc_18003261E
0x180032539  lea     rsi, WPP_RECORDER_INITIALIZED
0x180032540  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032547  jz      loc_180032DD7
0x18003254d  mov     rax, [rdi+170h]
0x180032554  test    rax, rax
0x180032557  jz      short loc_18003256A
0x180032559  mov     rax, [rax+18h]
0x18003255d  test    rax, rax
0x180032560  jz      short loc_18003256A
0x180032562  mov     rax, [rax]
0x180032565  test    rax, rax
0x180032568  jnz     short loc_180032571
0x18003256a  lea     rax, aUnknown_0; "unknown"
0x180032571  mov     r9d, 92h; int
0x180032577  mov     dword ptr [rsp+350h+var_318], ecx; char
0x18003257b  mov     qword ptr [rsp+350h+var_320], rdi; char
0x180032580  mov     [rsp+350h+var_328], rax; __int64
0x180032585  mov     [rsp+350h+MessageGuid], rdx; MessageGuid
0x18003258a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032591  mov     rcx, [rcx+28h]; int
0x180032595  call    WPP_RECORDER_SF_SqD
0x18003259a  xor     r13d, r13d
0x18003259d  mov     ebx, [rbp+250h+arg_28]
0x1800325a3  lea     r15, [rdi+30h]
0x1800325a7  mov     rcx, r15; SRWLock
0x1800325aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800325b0  cmp     [rdi+28h], r13d
0x1800325b4  jz      loc_180032DE5
0x1800325ba  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1800325c1  mov     [rbp+250h+var_2D0], 8001071Ah
0x1800325c8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800325cf  jz      short loc_180032609
0x1800325d1  mov     r9d, 9Eh; int
0x1800325d7  mov     dword ptr [rsp+350h+var_318], 8001071Ah; char
0x1800325df  mov     qword ptr [rsp+350h+var_320], rdi; char
0x1800325e4  mov     rax, [rdi+8]
0x1800325e8  mov     [rsp+350h+var_328], rax; __int64
0x1800325ed  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x1800325f4  mov     [rsp+350h+MessageGuid], rax; MessageGuid
0x1800325f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180032600  mov     rcx, [rcx+28h]; int
0x180032604  call    WPP_RECORDER_SF_SqD
0x180032609  mov     [rdi+28h], r13d
0x18003260d  mov     rcx, r15; SRWLock
0x180032610  call    cs:__imp_ReleaseSRWLockExclusive
0x180032616  mov     ebx, [rbp+250h+var_2C4]
0x180032619  jmp     loc_1800331E9
0x18003261e  lea     r8, [rbp+250h+var_298]
0x180032622  mov     rdx, [rdi+8]
0x180032626  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18003262d  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x180032632  mov     [rbp+250h+var_2D0], eax
0x180032635  test    eax, eax
0x180032637  jns     short loc_180032676
0x180032639  lea     rsi, WPP_RECORDER_INITIALIZED
0x180032640  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032647  jz      loc_18003259A
0x18003264d  mov     r9d, 93h
0x180032653  mov     dword ptr [rsp+350h+var_318], eax
0x180032657  mov     qword ptr [rsp+350h+var_320], rdi
0x18003265c  mov     rax, [rdi+8]
0x180032660  mov     [rsp+350h+var_328], rax
0x180032665  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18003266c  mov     [rsp+350h+MessageGuid], rax
0x180032671  jmp     loc_18003258A
0x180032676  lea     rsi, WPP_RECORDER_INITIALIZED
0x18003267d  cmp     [rbp+250h+Reply], 1
0x180032684  jz      loc_180032BEB
0x18003268a  mov     rcx, [rbp+250h+var_298]
0x18003268e  cmp     [rcx+4Ch], r15d
0x180032692  jnz     loc_180032BEB
0x180032698  test    eax, eax
0x18003269a  jnz     loc_180032BF1
0x1800326a0  mov     eax, ebx
0x1800326a2  neg     eax
0x1800326a4  sbb     r15d, r15d
0x1800326a7  and     r15d, 3
0x1800326ab  inc     r15d
0x1800326ae  add     r15d, r13d
0x1800326b1  mov     [rbp+250h+var_2CC], 0FFh
0x1800326b5  movups  xmm6, cs:DEVPKEY_Aep_IsAssociated
0x1800326bc  mov     eax, cs:dword_18008C9A8
0x1800326c2  mov     dword ptr [rbp+250h+var_2B0], eax
0x1800326c5  xor     ecx, ecx
0x1800326c7  mov     eax, ecx
0x1800326c9  test    ebx, ebx
0x1800326cb  setnz   al
0x1800326ce  mov     dword ptr [rbp+250h+var_2B8], eax
0x1800326d1  lea     rbx, [r15+r15*2]
0x1800326d5  shl     rbx, 4
0x1800326d9  call    cs:__imp_GetProcessHeap
0x1800326df  mov     rcx, rax; hHeap
0x1800326e2  mov     r8, rbx; dwBytes
0x1800326e5  xor     edx, edx; dwFlags
0x1800326e7  call    cs:__imp_HeapAlloc
0x1800326ed  mov     r14, rax
0x1800326f0  test    rax, rax
0x1800326f3  jnz     short loc_18003271C
0x1800326f5  mov     [rbp+250h+var_2D0], 8007000Eh
0x1800326fc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032703  jz      loc_18003259A
0x180032709  mov     r9d, 94h
0x18003270f  mov     dword ptr [rsp+350h+var_318], 8007000Eh
0x180032717  jmp     loc_180032657
0x18003271c  lea     rbx, ds:0[r13*2]
0x180032724  add     rbx, r13
0x180032727  shl     rbx, 4
0x18003272b  mov     r8, rbx; Size
0x18003272e  mov     rdx, [rbp+250h+Src]; Src
0x180032732  mov     rcx, r14; void *
0x180032735  call    memcpy_0
0x18003273a  movups  xmmword ptr [rbx+r14], xmm6
0x18003273f  mov     eax, dword ptr [rbp+250h+var_2B0]
0x180032742  mov     [rbx+r14+10h], eax
0x180032747  mov     eax, dword ptr [rbp+250h+var_2B8]
0x18003274a  mov     [rbx+r14+14h], eax
0x18003274f  xor     ecx, ecx
0x180032751  mov     [rbx+r14+18h], rcx
0x180032756  mov     dword ptr [rbx+r14+20h], 11h
0x18003275f  mov     dword ptr [rbx+r14+24h], 1
0x180032768  lea     rax, [rbp+250h+var_2CC]
0x18003276c  mov     [rbx+r14+28h], rax
0x180032771  cmp     [rbp+250h+var_2C0], ecx
0x180032774  jz      loc_180032B25
0x18003277a  mov     [rbp+250h+var_2B8], rcx
0x18003277e  cmp     [rdi+10h], rcx
0x180032782  jnz     short loc_1800327DA
0x180032784  mov     [rbp+250h+var_2D0], 80640025h
0x18003278b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032792  jz      short loc_1800327CC
0x180032794  mov     r9d, 95h; int
0x18003279a  mov     dword ptr [rsp+350h+var_318], 80640025h; char
0x1800327a2  mov     qword ptr [rsp+350h+var_320], rdi; char
0x1800327a7  mov     rax, [rdi+8]
0x1800327ab  mov     [rsp+350h+var_328], rax; __int64
0x1800327b0  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x1800327b7  mov     [rsp+350h+MessageGuid], rax; MessageGuid
0x1800327bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327c3  mov     rcx, [rcx+28h]; int
0x1800327c7  call    WPP_RECORDER_SF_SqD
0x1800327cc  lea     rcx, [rbp+250h+var_2B8]
0x1800327d0  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x1800327d5  jmp     loc_18003259A
0x1800327da  mov     [rbp+250h+var_2B0], rcx
0x1800327de  xor     edx, edx
0x1800327e0  lea     rcx, [rbp+250h+var_2B0]
0x1800327e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800327e9  lea     rdx, [rbp+250h+var_2B0]; unsigned __int16 **
0x1800327ed  mov     rcx, [rdi+10h]; Src
0x1800327f1  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x1800327f6  mov     [rbp+250h+var_2D0], eax
0x1800327f9  test    eax, eax
0x1800327fb  jns     short loc_180032851
0x1800327fd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032804  jz      short loc_180032843
0x180032806  mov     r9d, 96h; int
0x18003280c  mov     dword ptr [rsp+350h+var_310], eax; char
0x180032810  mov     rax, [rdi+10h]
0x180032814  mov     qword ptr [rsp+350h+var_318], rdi; char
0x180032819  mov     qword ptr [rsp+350h+var_320], rax; __int64
0x18003281e  mov     rax, [rdi+8]
0x180032822  mov     [rsp+350h+var_328], rax; __int64
0x180032827  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18003282e  mov     [rsp+350h+MessageGuid], rax; MessageGuid
0x180032833  mov     rcx, cs:WPP_GLOBAL_Control
0x18003283a  mov     rcx, [rcx+28h]; int
0x18003283e  call    WPP_RECORDER_SF_SSqD
0x180032843  lea     rcx, [rbp+250h+var_2B0]
0x180032847  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003284c  jmp     loc_1800327CC
0x180032851  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x180032858  lea     rcx, [rbp+250h+var_2B8]
0x18003285c  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180032861  lea     rax, [rbp+250h+var_2B8]
0x180032865  mov     [rsp+350h+MessageGuid], rax
0x18003286a  mov     r9d, 8
0x180032870  mov     r8, [rbp+250h+var_2B0]
0x180032874  mov     rdx, 0FFFFFFFF80000003h
0x18003287b  mov     rcx, rbx
0x18003287e  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180032883  mov     [rbp+250h+var_2D0], eax
0x180032886  xor     r8d, r8d
0x180032889  test    eax, eax
0x18003288b  jns     short loc_1800328A1
0x18003288d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180032894  jz      short loc_180032843
0x180032896  mov     r9d, 97h
0x18003289c  jmp     loc_18003280C
0x1800328a1  movups  xmm0, cs:DEVPKEY_Aep_IsAssociatedPerUser
0x1800328a8  mov     edx, cs:dword_18008DBE8
0x1800328ae  lea     eax, [r13+1]
0x1800328b2  lea     rax, [rax+rax*2]
0x1800328b6  add     rax, rax
0x1800328b9  movups  xmmword ptr [r14+rax*8], xmm0
0x1800328be  mov     [r14+rax*8+10h], edx
0x1800328c3  mov     [r14+rax*8+14h], r8d
0x1800328c8  mov     [r14+rax*8+18h], r8
0x1800328cd  mov     dword ptr [r14+rax*8+20h], 11h
0x1800328d6  mov     dword ptr [r14+rax*8+24h], 1
0x1800328df  lea     rcx, [rbp+250h+var_2CC]
0x1800328e3  mov     [r14+rax*8+28h], rcx
0x1800328e8  xorps   xmm0, xmm0
0x1800328eb  movups  [rbp+250h+var_270], xmm0
0x1800328ef  movups  xmm1, cs:DEVPKEY_Aep_ContainerId
0x1800328f6  mov     edx, cs:dword_18008C9C0
0x1800328fc  lea     eax, [r13+2]
0x180032900  lea     rax, [rax+rax*2]
0x180032904  shl     rax, 4
0x180032908  mov     [rbp+250h+var_288], rax
0x18003290c  movups  xmmword ptr [rax+r14], xmm1
0x180032911  mov     [rax+r14+10h], edx
0x180032916  mov     dword ptr [rax+r14+14h], 1
0x18003291f  mov     [rax+r14+18h], r8
0x180032924  mov     edx, 0Dh
0x180032929  mov     [rax+r14+20h], edx
0x18003292e  mov     dword ptr [rax+r14+24h], 10h
0x180032937  mov     [rax+r14+28h], r8
0x18003293c  lea     eax, [r13+3]
0x180032940  lea     rcx, [rax+rax*2]
0x180032944  shl     rcx, 4
0x180032948  mov     [rbp+250h+var_280], rcx
0x18003294c  movups  xmm0, cs:DEVPKEY_Aep_SystemContainerId
0x180032953  movups  xmmword ptr [rcx+r14], xmm0
0x180032958  mov     eax, cs:dword_18008CA38
0x18003295e  mov     [rcx+r14+10h], eax
0x180032963  mov     dword ptr [rcx+r14+14h], 1
0x18003296c  mov     [rcx+r14+18h], r8
0x180032971  mov     [rcx+r14+20h], edx
0x180032976  mov     dword ptr [rcx+r14+24h], 10h
0x18003297f  mov     [rcx+r14+28h], r8
0x180032984  mov     r13d, r8d
0x180032987  cmp     r13d, [rbp+250h+NotificationsQueued]
0x18003298b  jnb     loc_180032A89
0x180032991  mov     eax, r13d
0x180032994  lea     rbx, [rax+rax*2]
0x180032998  shl     rbx, 4
0x18003299c  add     rbx, [rbp+250h+Src]
0x1800329a0  cmp     dword ptr [rbx+10h], 2
0x1800329a4  jnz     short loc_1800329CE
0x1800329a6  mov     r8d, 10h; Size
0x1800329ac  lea     rdx, DEVPKEY_Aep_ContainerId; Buf2
0x1800329b3  mov     rcx, rbx; Buf1
0x1800329b6  call    memcmp_0
0x1800329bb  xor     r8d, r8d
0x1800329be  test    eax, eax
0x1800329c0  jnz     short loc_1800329CE
0x1800329c2  cmp     [rbx+14h], r8d
0x1800329c6  jnz     short loc_1800329CE
0x1800329c8  cmp     dword ptr [rbx+20h], 0Dh
0x1800329cc  jz      short loc_1800329D3
0x1800329ce  inc     r13d
0x1800329d1  jmp     short loc_180032987
0x1800329d3  mov     rdx, [rdi+10h]; int
0x1800329d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800329db  xor     r13d, r13d
0x1800329de  inc     r8; int
0x1800329e1  cmp     [rdx+r8*2], r13w
  ... truncated ...
```
