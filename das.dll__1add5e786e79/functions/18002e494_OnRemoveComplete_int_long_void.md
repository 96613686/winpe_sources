# OnRemoveComplete(int,long,void *)

- ea: `0x18002e494`
- end: `0x18002eced`
- name: `?OnRemoveComplete@@YAJHJPEAX@Z`
- size: `2137`
- prototype: `int(int, int, void *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800493f0`

## callees

- `0x180005770`
- `0x1800074c0`
- `0x180008a50`
- `0x180019d00`
- `0x18001a268`
- `0x18001eae0`
- `0x180024d60`
- `0x180028a2c`
- `0x180028ed8`
- `0x1800290c4`
- `0x18002a948`
- `0x18002be5c`
- `0x18002e494`
- `0x1800306d8`
- `0x180031f24`
- `0x180033470`
- `0x1800335bc`
- `0x1800345f0`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180046ef0`
- `0x180047448`
- `0x1800582b0`
- `0x180065280`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eada`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eb68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eada`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002eb68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ea21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ea21`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002eb5d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002eb5d`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002eb20`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002eb20`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e52c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e52c`

## string_xrefs

- `0x18002e56f`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x18002ec60`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall OnRemoveComplete(int a1, int a2, char *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  DWORD v9; // r15d
  int v10; // r14d
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  int ProviderFromAepId; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  const unsigned __int16 *v17; // r8
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // edx
  const wchar_t *v22; // rcx
  const wchar_t *v23; // rax
  int PerUserSubKey; // eax
  int v25; // edx
  int v26; // r8d
  PSRWLOCK v27; // rbx
  int Store; // eax
  int v29; // edx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // r9d
  const unsigned __int16 *v33; // rdx
  int v34; // eax
  int v35; // edx
  int v36; // r8d
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  int v39; // edx
  int v40; // r8d
  int v41; // edx
  int v42; // r8d
  __int64 v43; // rcx
  int v44; // ecx
  int v45; // eax
  __int64 v46; // rcx
  char *p_Reply; // rdx
  int v48; // ebx
  int v49; // edx
  int v50; // r8d
  int ProcessName; // eax
  int v52; // ecx
  int MessageGuid; // [rsp+20h] [rbp-E0h]
  char v55[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v56; // [rsp+64h] [rbp-9Ch] BYREF
  int Reply; // [rsp+68h] [rbp-98h] BYREF
  unsigned int NotificationsQueued[2]; // [rsp+70h] [rbp-90h] BYREF
  Windows::Devices::Pnp::Internal::PnpObjectStore *v59; // [rsp+78h] [rbp-88h] BYREF
  void *v60; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v61[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _DEVPROPERTY v62; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v62.CompKey.Key.pid = 16;
  Reply = a2;
  *(_DWORD *)v55 = 0;
  v62.CompKey.Store = a1 != 0;
  v56 = 0;
  v62.Buffer = &v56;
  v62.CompKey.LocaleName = 0;
  v62.Type = 17;
  v62.BufferSize = 1;
  *(_OWORD *)v61 = 0;
  v60 = 0;
  v62.CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsAssociated;
  EventActivityIdControl(2u, (LPGUID)(a3 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v5, ASSOC_REMOVE_PROVIDER_STOP, a3);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v60,
    0);
  v6 = DafStringCopy(*((_QWORD *)a3 + 1), &v60);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC94,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
      (const char *)(unsigned int)v6,
      MessageGuid);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return v8;
  }
  v9 = *((_DWORD *)a3 + 16);
  v10 = 8;
  if ( Reply < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v11 = *((_QWORD *)a3 + 46);
      if ( v11 )
        v12 = **(const wchar_t ***)(v11 + 24);
      else
        v12 = L"unknown";
      WPP_RECORDER_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        *(int *)v55,
        v7,
        174,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a3 + 1),
        (__int64)v12,
        (char)a3,
        v55[0]);
    }
    goto LABEL_64;
  }
  ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(
                        g_providerManager,
                        *((_QWORD *)a3 + 1),
                        v61);
  *(_DWORD *)v55 = ProviderFromAepId;
  if ( ProviderFromAepId < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v16 = 175;
    goto LABEL_14;
  }
  if ( *((_DWORD *)v61[0] + 19) )
    goto LABEL_64;
  if ( *((_DWORD *)a3 + 98) && a1 )
    v17 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
  else
    v17 = 0;
  ProviderFromAepId = DAS::DevnodeManagment::DevnodeManager::UninstallDevnodes(
                        g_devnodeManager,
                        *((const unsigned __int16 **)a3 + 1),
                        v17);
  *(_DWORD *)v55 = ProviderFromAepId;
  if ( ProviderFromAepId )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v16 = 176;
    goto LABEL_14;
  }
  NotificationsQueued[0] = 0;
  LODWORD(v59) = 0;
  v18 = DasEvaluateServiceLifetime(NotificationsQueued, (int *)&v59);
  *(_DWORD *)v55 = v18;
  v21 = v18;
  if ( v18 < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v18,
        v19,
        177,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a3 + 1),
        *((_QWORD *)a3 + 2),
        (char)a3,
        v18);
    goto LABEL_64;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v22 = L"armed";
    if ( !(_DWORD)v59 )
      v22 = (const wchar_t *)L"disarmed";
    v23 = L"auto";
    if ( NotificationsQueued[0] != 2 )
      v23 = (const wchar_t *)L"trigger";
    WPP_RECORDER_SF_SSSSqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v21,
      (int)L"trigger",
      178,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a3 + 1),
      *((_QWORD *)a3 + 2),
      (__int64)v23,
      (__int64)v22,
      (char)a3,
      v21);
  }
  if ( *((_DWORD *)a3 + 98) && a1 )
  {
    *(_QWORD *)NotificationsQueued = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      NotificationsQueued,
      0);
    PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(
                      *((const unsigned __int16 **)a3 + 2),
                      (unsigned __int16 **)NotificationsQueued);
    *(_DWORD *)v55 = PerUserSubKey;
    if ( PerUserSubKey < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v25,
          v26,
          179,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          *((_QWORD *)a3 + 2),
          (char)a3,
          PerUserSubKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)NotificationsQueued);
      goto LABEL_64;
    }
    v27 = g_StoreManager;
    v59 = 0;
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v59);
    Store = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(
              v27,
              -2147483645,
              *(_QWORD *)NotificationsQueued,
              8);
    *(_DWORD *)v55 = Store;
    if ( Store < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v32 = 180;
LABEL_44:
        WPP_RECORDER_SF_SSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v29,
          v30,
          v32,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          *((_QWORD *)a3 + 2),
          (char)a3,
          Store);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    Store = Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(
              v59,
              *((const unsigned __int16 **)a3 + 1),
              v30,
              v31,
              (int)&v59);
    *(_DWORD *)v55 = Store;
    if ( Store < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v32 = 181;
        goto LABEL_44;
      }
LABEL_45:
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v59);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)NotificationsQueued);
      goto LABEL_64;
    }
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v59);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)NotificationsQueued);
  }
  ProviderFromAepId = Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(
                        g_AepStore,
                        *((const unsigned __int16 **)a3 + 1),
                        v19,
                        v20,
                        MessageGuid);
  *(_DWORD *)v55 = ProviderFromAepId;
  if ( ProviderFromAepId < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v16 = 182;
LABEL_14:
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v14,
      v15,
      v16,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a3 + 1),
      (char)a3,
      ProviderFromAepId);
    goto LABEL_64;
  }
  if ( a1 )
    v33 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
  else
    v33 = 0;
  v34 = DAS::Dispatcher::Dispatch::ExternalAepStoreChange(*((const unsigned __int16 **)a3 + 1), v33, 3u, 1u, &v62);
  *(_DWORD *)v55 = v34;
  if ( v34 < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v35,
      v36,
      183,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      (char)a3,
      v34);
  if ( a1 )
    v37 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
  else
    v37 = 0;
  v38 = DAS::Dispatcher::Dispatch::ExternalAepStoreChange(*((const unsigned __int16 **)a3 + 1), v37, 2u, 1u, &v62);
  *(_DWORD *)v55 = v38;
  if ( v38 < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v39,
      v40,
      184,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      (char)a3,
      v38);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v39,
      v40,
      185,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a3 + 1),
      (char)a3);
LABEL_64:
  AcquireSRWLockExclusive((PSRWLOCK)a3 + 6);
  if ( *((_DWORD *)a3 + 10) )
  {
    *((_DWORD *)a3 + 7) = -1;
    *(_DWORD *)v55 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v41,
        v42,
        186,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a3 + 1),
        (char)a3,
        26);
    *((_DWORD *)a3 + 10) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
  }
  else
  {
    if ( *((_DWORD *)a3 + 9) )
    {
      *(_DWORD *)v55 = -2147418113;
      *((_DWORD *)a3 + 7) = -1;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v41,
          v42,
          187,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          (char)a3,
          255);
      ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
      goto LABEL_92;
    }
    v44 = *(_DWORD *)v55;
    v45 = Reply;
    if ( *(int *)v55 < 0 || Reply < 0 )
      v10 = -1;
    *((_DWORD *)a3 + 7) = v10;
    if ( *((_DWORD *)a3 + 94) )
    {
      v46 = *((_QWORD *)a3 + 25);
      NotificationsQueued[0] = 0;
      RpcServerUnsubscribeForNotification(
        *(RPC_BINDING_HANDLE *)(v46 + 32),
        RpcNotificationCallCancel,
        NotificationsQueued);
      (*(void (__fastcall **)(char *))(*(_QWORD *)a3 + 16LL))(a3);
      v44 = *(_DWORD *)v55;
      v45 = Reply;
    }
    *((_DWORD *)a3 + 9) = 1;
    if ( v45 < 0 || (p_Reply = v55, v44 >= 0) )
      p_Reply = (char *)&Reply;
    v48 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a3 + 25), p_Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
    if ( !v48 || v48 == 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v49,
          v50,
          189,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          (char)a3);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v49,
          v50,
          188,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          (char)a3,
          v48);
      if ( v48 >= 0 )
        v48 = (unsigned __int16)v48 | 0x80010000;
      *(_DWORD *)v55 = v48;
    }
  }
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v43, ASSOC_REMOVE_STOP, a3);
  (*(void (__fastcall **)(char *))(*(_QWORD *)a3 + 16LL))(a3);
LABEL_92:
  if ( *(int *)v55 < 0 || Reply < 0 )
  {
    memset_0(Filename, 0, 0x208u);
    ProcessName = GetProcessName(v9, Filename);
    if ( ProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD3F,
        (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
        (const char *)(unsigned int)ProcessName);
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
      McTemplateU0zzqqq_EventWriteTransfer(
        v52,
        (unsigned int)DISASSOCIATION_FAILURE,
        (_DWORD)v60,
        (unsigned int)Filename,
        v9,
        v55[0],
        Reply);
  }
  v8 = *(_DWORD *)v55;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
  if ( v61[1] )
    std::_Ref_count_base::_Decref(v61[1]);
  return v8;
}

```

## disassembly

```asm
0x18002e494  mov     [rsp-8+arg_0], rbx
0x18002e499  push    rbp
0x18002e49a  push    rsi
0x18002e49b  push    rdi
0x18002e49c  push    r12
0x18002e49e  push    r13
0x18002e4a0  push    r14
0x18002e4a2  push    r15
0x18002e4a4  lea     rbp, [rsp-1F0h]
0x18002e4ac  sub     rsp, 2F0h
0x18002e4b3  mov     rax, cs:__security_cookie
0x18002e4ba  xor     rax, rsp
0x18002e4bd  mov     [rbp+220h+var_40], rax
0x18002e4c4  mov     eax, cs:dword_18008C9A8
0x18002e4ca  xor     r12d, r12d
0x18002e4cd  movups  xmm1, cs:DEVPKEY_Aep_IsAssociated
0x18002e4d4  mov     [rbp+220h+var_288.CompKey.Key.pid], eax
0x18002e4d7  test    ecx, ecx
0x18002e4d9  mov     eax, r12d
0x18002e4dc  mov     [rsp+320h+Reply], edx
0x18002e4e0  setnz   al
0x18002e4e3  mov     dword ptr [rsp+320h+var_2C0], r12d
0x18002e4e8  mov     [rbp+220h+var_288.CompKey.Store], eax
0x18002e4eb  lea     rdx, [r8+15Ch]; ActivityId
0x18002e4f2  lea     rax, [rsp+320h+var_2BC]
0x18002e4f7  mov     [rsp+320h+var_2BC], r12b
0x18002e4fc  mov     esi, ecx
0x18002e4fe  mov     [rbp+220h+var_288.Buffer], rax
0x18002e502  xorps   xmm0, xmm0
0x18002e505  mov     [rbp+220h+var_288.CompKey.LocaleName], r12
0x18002e509  lea     ecx, [r12+2]; ControlCode
0x18002e50e  mov     [rbp+220h+var_288.Type], 11h
0x18002e515  mov     rdi, r8
0x18002e518  mov     [rbp+220h+var_288.BufferSize], 1
0x18002e51f  movdqu  xmmword ptr [rbp+220h+var_298], xmm0
0x18002e524  mov     [rbp+220h+var_2A0], r12
0x18002e528  movups  xmmword ptr [rbp+220h+var_288.CompKey.Key.fmtid.Data1], xmm1
0x18002e52c  call    cs:__imp_EventActivityIdControl
0x18002e532  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x18002e539  jz      short loc_18002E54A
0x18002e53b  mov     r8, rdi
0x18002e53e  lea     rdx, ASSOC_REMOVE_PROVIDER_STOP
0x18002e545  call    McTemplateU0p_EventWriteTransfer
0x18002e54a  xor     edx, edx
0x18002e54c  lea     rcx, [rbp+220h+var_2A0]
0x18002e550  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e555  mov     rcx, [rdi+8]
0x18002e559  lea     rdx, [rbp+220h+var_2A0]
0x18002e55d  call    DafStringCopy
0x18002e562  mov     ebx, eax
0x18002e564  test    eax, eax
0x18002e566  jns     short loc_18002E591
0x18002e568  mov     rcx, [rbp+228h]; this
0x18002e56f  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x18002e576  mov     r9d, eax; char *
0x18002e579  mov     edx, 0C94h; void *
0x18002e57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e583  lea     rcx, [rbp+220h+var_2A0]
0x18002e587  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e58c  jmp     loc_18002ECC1
0x18002e591  lea     r13, WPP_RECORDER_INITIALIZED
0x18002e598  mov     r15d, [rdi+40h]
0x18002e59c  lea     rbx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18002e5a3  mov     r14d, 8
0x18002e5a9  cmp     [rsp+320h+Reply], r12d
0x18002e5ae  jge     short loc_18002E614
0x18002e5b0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e5b7  jz      loc_18002EA13
0x18002e5bd  mov     rax, [rdi+170h]
0x18002e5c4  mov     edx, dword ptr [rsp+320h+var_2C0]; int
0x18002e5c8  test    rax, rax
0x18002e5cb  jz      short loc_18002E5D6
0x18002e5cd  mov     rax, [rax+18h]
0x18002e5d1  mov     rcx, [rax]
0x18002e5d4  jmp     short loc_18002E5DD
0x18002e5d6  lea     rcx, aUnknown_0; "unknown"
0x18002e5dd  mov     dword ptr [rsp+320h+var_2E0], edx; char
0x18002e5e1  mov     r9d, 0AEh; int
0x18002e5e7  mov     qword ptr [rsp+320h+var_2E8], rdi; char
0x18002e5ec  mov     qword ptr [rsp+320h+var_2F0], rcx; __int64
0x18002e5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5f8  mov     rax, [rdi+8]
0x18002e5fc  mov     qword ptr [rsp+320h+var_2F8], rax; __int64
0x18002e601  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e606  mov     rcx, [rcx+28h]; int
0x18002e60a  call    WPP_RECORDER_SF_SSqD
0x18002e60f  jmp     loc_18002EA13
0x18002e614  mov     rdx, [rdi+8]
0x18002e618  lea     r8, [rbp+220h+var_298]
0x18002e61c  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18002e623  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x18002e628  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e62c  test    eax, eax
0x18002e62e  jns     short loc_18002E66F
0x18002e630  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e637  jz      loc_18002EA13
0x18002e63d  mov     r9d, 0AFh; int
0x18002e643  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e64a  mov     dword ptr [rsp+320h+var_2E8], eax; char
0x18002e64e  mov     rax, [rdi+8]
0x18002e652  mov     qword ptr [rsp+320h+var_2F0], rdi; char
0x18002e657  mov     rcx, [rcx+28h]; int
0x18002e65b  mov     qword ptr [rsp+320h+var_2F8], rax; __int64
0x18002e660  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e665  call    WPP_RECORDER_SF_SqD
0x18002e66a  jmp     loc_18002EA13
0x18002e66f  mov     rax, [rbp+220h+var_298]
0x18002e673  cmp     [rax+4Ch], r12d
0x18002e677  jnz     loc_18002EA13
0x18002e67d  cmp     [rdi+188h], r12d
0x18002e684  jz      short loc_18002E690
0x18002e686  test    esi, esi
0x18002e688  jz      short loc_18002E690
0x18002e68a  mov     r8, [rdi+10h]
0x18002e68e  jmp     short loc_18002E693
0x18002e690  mov     r8, r12; unsigned __int16 *
0x18002e693  mov     rcx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; this
0x18002e69a  mov     rdx, [rdi+8]; unsigned __int16 *
0x18002e69e  call    ?UninstallDevnodes@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::UninstallDevnodes(ushort const *,ushort const *)
0x18002e6a3  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e6a7  test    eax, eax
0x18002e6a9  jz      short loc_18002E6C0
0x18002e6ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e6b2  jz      loc_18002EA13
0x18002e6b8  mov     r9d, 0B0h
0x18002e6be  jmp     short loc_18002E643
0x18002e6c0  lea     rdx, [rsp+320h+var_2A8]; int *
0x18002e6c5  mov     [rsp+320h+NotificationsQueued], r12d
0x18002e6ca  lea     rcx, [rsp+320h+NotificationsQueued]; unsigned int *
0x18002e6cf  mov     dword ptr [rsp+320h+var_2A8], r12d
0x18002e6d4  call    ?DasEvaluateServiceLifetime@@YAJPEAKPEAH@Z; DasEvaluateServiceLifetime(ulong *,int *)
0x18002e6d9  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e6dd  mov     edx, eax; int
0x18002e6df  test    eax, eax
0x18002e6e1  jns     short loc_18002E70D
0x18002e6e3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e6ea  jz      loc_18002EA13
0x18002e6f0  mov     dword ptr [rsp+320h+var_2E0], eax
0x18002e6f4  mov     r9d, 0B1h
0x18002e6fa  mov     rax, [rdi+10h]
0x18002e6fe  mov     qword ptr [rsp+320h+var_2E8], rdi
0x18002e703  mov     qword ptr [rsp+320h+var_2F0], rax
0x18002e708  jmp     loc_18002E5F1
0x18002e70d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e714  jz      short loc_18002E784
0x18002e716  cmp     dword ptr [rsp+320h+var_2A8], r12d
0x18002e71b  lea     rax, aDisarmed; "disarmed"
0x18002e722  mov     dword ptr [rsp+320h+var_2D0], edx; char
0x18002e726  lea     r8, aTrigger; "trigger"
0x18002e72d  mov     qword ptr [rsp+320h+var_2D8], rdi; char
0x18002e732  lea     rcx, aArmed; "armed"
0x18002e739  cmovz   rcx, rax
0x18002e73d  mov     r9d, 0B2h; int
0x18002e743  cmp     [rsp+320h+NotificationsQueued], 2
0x18002e748  lea     rax, aAuto; "auto"
0x18002e74f  mov     qword ptr [rsp+320h+var_2E0], rcx; __int64
0x18002e754  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e75b  cmovnz  rax, r8
0x18002e75f  mov     qword ptr [rsp+320h+var_2E8], rax; __int64
0x18002e764  mov     rax, [rdi+10h]
0x18002e768  mov     qword ptr [rsp+320h+var_2F0], rax; __int64
0x18002e76d  mov     rax, [rdi+8]
0x18002e771  mov     rcx, [rcx+28h]; int
0x18002e775  mov     qword ptr [rsp+320h+var_2F8], rax; __int64
0x18002e77a  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e77f  call    WPP_RECORDER_SF_SSSSqD
0x18002e784  cmp     [rdi+188h], r12d
0x18002e78b  jz      loc_18002E8F5
0x18002e791  test    esi, esi
0x18002e793  jz      loc_18002E8F5
0x18002e799  xor     edx, edx
0x18002e79b  mov     qword ptr [rsp+320h+NotificationsQueued], r12
0x18002e7a0  lea     rcx, [rsp+320h+NotificationsQueued]
0x18002e7a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e7aa  mov     rcx, [rdi+10h]; Src
0x18002e7ae  lea     rdx, [rsp+320h+NotificationsQueued]; unsigned __int16 **
0x18002e7b3  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x18002e7b8  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e7bc  test    eax, eax
0x18002e7be  jns     short loc_18002E80E
0x18002e7c0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e7c7  jz      short loc_18002E7FF
0x18002e7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7d0  mov     r9d, 0B3h; int
0x18002e7d6  mov     dword ptr [rsp+320h+var_2E0], eax; char
0x18002e7da  mov     rax, [rdi+10h]
0x18002e7de  mov     qword ptr [rsp+320h+var_2E8], rdi; char
0x18002e7e3  mov     rcx, [rcx+28h]; int
0x18002e7e7  mov     qword ptr [rsp+320h+var_2F0], rax; __int64
0x18002e7ec  mov     rax, [rdi+8]
0x18002e7f0  mov     qword ptr [rsp+320h+var_2F8], rax; __int64
0x18002e7f5  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e7fa  call    WPP_RECORDER_SF_SSqD
0x18002e7ff  lea     rcx, [rsp+320h+NotificationsQueued]
0x18002e804  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e809  jmp     loc_18002EA13
0x18002e80e  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x18002e815  lea     rcx, [rsp+320h+var_2A8]
0x18002e81a  mov     [rsp+320h+var_2A8], r12
0x18002e81f  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18002e824  mov     r8, qword ptr [rsp+320h+NotificationsQueued]
0x18002e829  lea     rax, [rsp+320h+var_2A8]
0x18002e82e  mov     r9d, r14d
0x18002e831  mov     [rsp+320h+MessageGuid], rax
0x18002e836  mov     rdx, 0FFFFFFFF80000003h
0x18002e83d  mov     rcx, rbx
0x18002e840  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x18002e845  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e849  test    eax, eax
0x18002e84b  jns     short loc_18002E865
0x18002e84d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e854  lea     rbx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18002e85b  jz      short loc_18002E8C1
0x18002e85d  mov     r9d, 0B4h
0x18002e863  jmp     short loc_18002E891
0x18002e865  mov     rdx, [rdi+8]; unsigned __int16 *
0x18002e869  mov     rcx, [rsp+320h+var_2A8]; this
0x18002e86e  call    ?DeleteObject@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBG@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(ushort const *)
0x18002e873  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e877  test    eax, eax
0x18002e879  jns     short loc_18002E8DA
0x18002e87b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e882  lea     rbx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18002e889  jz      short loc_18002E8C1
0x18002e88b  mov     r9d, 0B5h; int
0x18002e891  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e898  mov     dword ptr [rsp+320h+var_2E0], eax; char
0x18002e89c  mov     rax, [rdi+10h]
0x18002e8a0  mov     qword ptr [rsp+320h+var_2E8], rdi; char
0x18002e8a5  mov     rcx, [rcx+28h]; int
0x18002e8a9  mov     qword ptr [rsp+320h+var_2F0], rax; __int64
0x18002e8ae  mov     rax, [rdi+8]
0x18002e8b2  mov     qword ptr [rsp+320h+var_2F8], rax; __int64
0x18002e8b7  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e8bc  call    WPP_RECORDER_SF_SSqD
0x18002e8c1  lea     rcx, [rsp+320h+var_2A8]
0x18002e8c6  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18002e8cb  lea     rcx, [rsp+320h+NotificationsQueued]
0x18002e8d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e8d5  jmp     loc_18002EA1A
0x18002e8da  lea     rcx, [rsp+320h+var_2A8]
0x18002e8df  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18002e8e4  lea     rcx, [rsp+320h+NotificationsQueued]
0x18002e8e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e8ee  lea     rbx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18002e8f5  mov     rdx, [rdi+8]; unsigned __int16 *
0x18002e8f9  mov     rcx, cs:?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; this
0x18002e900  call    ?DeleteObject@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBG@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::DeleteObject(ushort const *)
0x18002e905  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e909  test    eax, eax
0x18002e90b  jns     short loc_18002E925
0x18002e90d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e914  jz      loc_18002EA13
0x18002e91a  mov     r9d, 0B6h
0x18002e920  jmp     loc_18002E643
0x18002e925  test    esi, esi
0x18002e927  jz      short loc_18002E92F
0x18002e929  mov     rdx, [rdi+10h]
0x18002e92d  jmp     short loc_18002E932
0x18002e92f  mov     rdx, r12; unsigned __int16 *
0x18002e932  mov     rcx, [rdi+8]; unsigned __int16 *
0x18002e936  lea     rax, [rbp+220h+var_288]
0x18002e93a  mov     r9d, 1; unsigned int
0x18002e940  mov     [rsp+320h+MessageGuid], rax; struct _DEVPROPERTY *
0x18002e945  lea     r8d, [r9+2]; unsigned int
0x18002e949  call    ?ExternalAepStoreChange@Dispatch@Dispatcher@DAS@@SAJPEBG0KKQEAU_DEVPROPERTY@@@Z; DAS::Dispatcher::Dispatch::ExternalAepStoreChange(ushort const *,ushort const *,ulong,ulong,_DEVPROPERTY * const)
0x18002e94e  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e952  test    eax, eax
0x18002e954  jns     short loc_18002E983
0x18002e956  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e95d  jz      short loc_18002E983
0x18002e95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e966  mov     r9d, 0B7h; int
0x18002e96c  mov     dword ptr [rsp+320h+var_2F0], eax; char
0x18002e970  mov     qword ptr [rsp+320h+var_2F8], rdi; char
0x18002e975  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e97a  mov     rcx, [rcx+28h]; int
0x18002e97e  call    WPP_RECORDER_SF_qD
0x18002e983  test    esi, esi
0x18002e985  jz      short loc_18002E98D
0x18002e987  mov     rdx, [rdi+10h]
0x18002e98b  jmp     short loc_18002E990
0x18002e98d  mov     rdx, r12; unsigned __int16 *
0x18002e990  mov     rcx, [rdi+8]; unsigned __int16 *
0x18002e994  lea     rax, [rbp+220h+var_288]
0x18002e998  mov     r9d, 1; unsigned int
0x18002e99e  mov     [rsp+320h+MessageGuid], rax; struct _DEVPROPERTY *
0x18002e9a3  lea     r8d, [r9+1]; unsigned int
0x18002e9a7  call    ?ExternalAepStoreChange@Dispatch@Dispatcher@DAS@@SAJPEBG0KKQEAU_DEVPROPERTY@@@Z; DAS::Dispatcher::Dispatch::ExternalAepStoreChange(ushort const *,ushort const *,ulong,ulong,_DEVPROPERTY * const)
0x18002e9ac  mov     dword ptr [rsp+320h+var_2C0], eax
0x18002e9b0  test    eax, eax
0x18002e9b2  jns     short loc_18002E9E1
0x18002e9b4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e9bb  jz      short loc_18002EA13
0x18002e9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9c4  mov     r9d, 0B8h; int
0x18002e9ca  mov     dword ptr [rsp+320h+var_2F0], eax; char
0x18002e9ce  mov     qword ptr [rsp+320h+var_2F8], rdi; char
0x18002e9d3  mov     [rsp+320h+MessageGuid], rbx; MessageGuid
0x18002e9d8  mov     rcx, [rcx+28h]; int
  ... truncated ...
```
