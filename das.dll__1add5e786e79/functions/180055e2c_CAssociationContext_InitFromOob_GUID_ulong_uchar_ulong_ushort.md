# CAssociationContext::InitFromOob(_GUID,ulong,uchar *,ulong,ushort * *)

- ea: `0x180055e2c`
- end: `0x18005678d`
- name: `?InitFromOob@CAssociationContext@@QEAAJU_GUID@@KPEAEKPEAPEAG@Z`
- size: `2401`
- prototype: `__int64 __usercall@<rax>(CAssociationContext *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180030960`

## callees

- `0x180009220`
- `0x180009250`
- `0x180009590`
- `0x1800185d0`
- `0x18001a268`
- `0x18001fabc`
- `0x18002482c`
- `0x180026120`
- `0x18002cc94`
- `0x180033470`
- `0x1800335bc`
- `0x1800337e8`
- `0x1800345f0`
- `0x1800377ec`
- `0x180047448`
- `0x180054338`
- `0x180055e2c`
- `0x180057790`
- `0x180058084`
- `0x180059400`
- `0x180060764`
- `0x180063824`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005614e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005635a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005614e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005635a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056515`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005625e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005653b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005625e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005653b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005610e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005610e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800564c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800564c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180056105`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180056105`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056506`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005622c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005622c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800560c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800560f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800560c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800560f2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800561b0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180056254`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800561b0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180056254`

## pseudocode

```c
__int64 __fastcall CAssociationContext::InitFromOob(
        CAssociationContext *this,
        struct _GUID *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  wil::details **v8; // rsi
  struct _TP_WORK *v9; // rbx
  int v10; // r8d
  std::_Ref_count_base *v11; // rsi
  int RpcClientToken; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  char *v16; // r13
  _QWORD *v17; // rax
  int HostContext; // eax
  int v19; // r8d
  void *v20; // rcx
  unsigned int v21; // ebx
  HANDLE v23; // r15
  signed int v24; // eax
  void *v25; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v27; // rcx
  signed int v28; // eax
  int v29; // r8d
  int v30; // r9d
  HANDLE v31; // r15
  void *v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rcx
  int v35; // r8d
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v38; // r8d
  _QWORD *v39; // r12
  const unsigned __int16 *v40; // rdx
  _QWORD *v41; // rbx
  int v42; // eax
  int v43; // r8d
  int v44; // r9d
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD v46; // eax
  int v47; // r9d
  signed int v48; // eax
  int v49; // r15d
  _QWORD *v50; // rax
  int IsAssociated; // eax
  int v52; // r8d
  int v53; // r9d
  unsigned __int64 v54; // rbx
  unsigned __int16 *v55; // rax
  int v56; // r8d
  unsigned __int16 **v57; // rcx
  int dwDesiredAccess; // [rsp+28h] [rbp-F0h]
  int bInheritHandle; // [rsp+30h] [rbp-E8h]
  char dwOptions; // [rsp+38h] [rbp-E0h]
  char v61[4]; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int16 **v62; // [rsp+A0h] [rbp-78h]
  struct _TP_WORK *v63; // [rsp+A8h] [rbp-70h]
  HANDLE hObject; // [rsp+B0h] [rbp-68h] BYREF
  HANDLE TargetHandle; // [rsp+B8h] [rbp-60h] BYREF
  std::_Ref_count_base *v66[2]; // [rsp+C0h] [rbp-58h] BYREF
  unsigned __int64 v67; // [rsp+D0h] [rbp-48h] BYREF
  HANDLE v68[2]; // [rsp+D8h] [rbp-40h] BYREF
  _QWORD v69[8]; // [rsp+E8h] [rbp-30h] BYREF
  _QWORD v70[8]; // [rsp+128h] [rbp+10h] BYREF
  int v71; // [rsp+188h] [rbp+70h] BYREF
  unsigned __int8 *v72; // [rsp+190h] [rbp+78h] BYREF

  v72 = a4;
  v71 = a3;
  v8 = (wil::details **)a6;
  v62 = a6;
  *(_DWORD *)v61 = 0;
  *(_OWORD *)v66 = 0;
  v9 = 0;
  v63 = 0;
  v67 = 0;
  hObject = 0;
  *a6 = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 6) = a5;
  if ( *((_DWORD *)this + 7) )
  {
    *(_DWORD *)v61 = -2140930033;
LABEL_24:
    if ( *v8 )
    {
      wil::details::FreeProcessHeap(*v8, a2);
      *v8 = 0;
    }
    *((_DWORD *)this + 7) = -1;
    goto LABEL_27;
  }
  *(_DWORD *)v61 = DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(g_providerManager, a2, v66);
  if ( *(_DWORD *)v61 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    WPP_RECORDER_SF_DDDDDDDDDDDqD(*((_QWORD *)WPP_GLOBAL_Control + 5), a2->Data4[5], a2->Data4[4], a2->Data4[3]);
    goto LABEL_6;
  }
  v11 = v66[0];
  if ( *((_DWORD *)v66[0] + 18) )
  {
    RpcClientToken = GetRpcClientToken(&hObject);
    *(_DWORD *)v61 = RpcClientToken;
    if ( RpcClientToken < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v14 = 34;
      goto LABEL_11;
    }
  }
  else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      v10,
      35,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *(_QWORD *)v66[0],
      (char)this);
  }
  std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v68, v66);
  *(_DWORD *)v61 = CAssociationContext::InitSetAssociation(this);
  if ( *(int *)v61 < 0 )
    goto LABEL_20;
  v15 = *((_DWORD *)v11 + 12);
  *((_DWORD *)this + 8) = v15 != 0;
  TargetHandle = 0;
  if ( !v15 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 13) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)v61 = LastError;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          v38,
          41,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (char)this,
          LastError);
      goto LABEL_20;
    }
    RpcClientToken = ProviderContext::GetClassFactory(v11, (struct IClassFactory **)&TargetHandle);
    *(_DWORD *)v61 = RpcClientToken;
    if ( RpcClientToken )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v14 = 42;
      goto LABEL_11;
    }
    v39 = (_QWORD *)((char *)this + 576);
    *(_DWORD *)v61 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, GUID *, char *))(*(_QWORD *)TargetHandle + 24LL))(
                       TargetHandle,
                       0,
                       &IID_IAepAssociation,
                       (char *)this + 576);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
    if ( *(_DWORD *)v61 )
    {
      if ( *(_DWORD *)v61 == -2147467262 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_20;
        v14 = 43;
        dwOptions = 2;
        goto LABEL_12;
      }
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v14 = 44;
      LOBYTE(RpcClientToken) = v61[0];
LABEL_11:
      dwOptions = RpcClientToken;
LABEL_12:
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        v13,
        v14,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        (char)this,
        dwOptions);
      goto LABEL_20;
    }
    if ( (*((_DWORD *)v11 + 14) & 0x800) != 0 )
      v40 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    else
      v40 = 0;
    v41 = (_QWORD *)((char *)this + 584);
    v42 = CAssociationCallback::Create(
            *(const unsigned __int16 **)v11,
            v40,
            *((_DWORD *)v11 + 19),
            this,
            hObject,
            (struct CAssociationCallback **)this + 73);
    *(_DWORD *)v61 = v42;
    if ( v42 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v44 = 45;
LABEL_107:
        WPP_RECORDER_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          v43,
          v44,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (char)this,
          v42);
      }
LABEL_108:
      if ( *v39 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 16LL))(*v39);
        *v39 = 0;
      }
      if ( *v41 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 16LL))(*v41);
        *v41 = 0;
      }
      goto LABEL_59;
    }
    hObject = 0;
    *((_DWORD *)this + 18) = v71;
    *((_QWORD *)this + 10) = v72;
    ThreadpoolWork = CreateThreadpoolWork(CAssociationContext::InitFromOobCallback, this, 0);
    v63 = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      v42 = GetLastError();
      if ( v42 > 0 )
        v42 = (unsigned __int16)v42 | 0x80070000;
      *(_DWORD *)v61 = v42;
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_108;
      v44 = 46;
      goto LABEL_107;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    v46 = WaitForSingleObject(*((HANDLE *)this + 13), 0xEA60u);
    if ( v46 )
    {
      switch ( v46 )
      {
        case 0x80u:
          *(_DWORD *)v61 = -2147024161;
          break;
        case 0x102u:
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dqD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              (_DWORD)a2,
              v43,
              v47,
              dwDesiredAccess,
              bInheritHandle,
              (char)this,
              v61[0]);
          *(_DWORD *)v61 = -2147023436;
          goto LABEL_98;
        case 0xFFFFFFFF:
          v48 = GetLastError();
          if ( v48 > 0 )
            v48 = (unsigned __int16)v48 | 0x80070000;
          *(_DWORD *)v61 = v48;
          break;
        default:
          *(_DWORD *)v61 = -2147467259;
          goto LABEL_98;
      }
    }
    if ( !*(_DWORD *)v61 )
    {
      v49 = *((_DWORD *)this + 28);
      *(_DWORD *)v61 = v49;
      if ( v49 < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)a2,
            v43,
            49,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            (char)this,
            v49);
        goto LABEL_108;
      }
      v50 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v70, v66);
      *(_DWORD *)v61 = CAssociationContext::SetupProviderCleanup(this, v50);
      if ( !*(_DWORD *)v61 )
        goto LABEL_112;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 96LL))(*v39);
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_108;
      v44 = 50;
LABEL_106:
      LOBYTE(v42) = v61[0];
      goto LABEL_107;
    }
LABEL_98:
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_108;
    v44 = 48;
    goto LABEL_106;
  }
  v68[0] = 0;
  v16 = (char *)this + 600;
  v17 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v70, v66);
  HostContext = CHostContext::GetHostContext(v17, (char *)this + 600);
  *(_DWORD *)v61 = HostContext;
  if ( HostContext )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        v19,
        36,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        (char)this,
        HostContext);
    goto LABEL_20;
  }
  v23 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 7) = v23;
  if ( !v23 )
  {
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    *(_DWORD *)v61 = v24;
    goto LABEL_20;
  }
  v25 = *(void **)(*(_QWORD *)v16 + 8LL);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v23, v25, &TargetHandle, 0, 0, 2u) )
  {
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    *(_DWORD *)v61 = v28;
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_6;
    v30 = 37;
LABEL_43:
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      v29,
      v30,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      (char)this,
      v28);
LABEL_6:
    v9 = 0;
LABEL_20:
    v8 = (wil::details **)v62;
    goto LABEL_21;
  }
  if ( *((_DWORD *)v11 + 18) )
  {
    if ( *((_DWORD *)v11 + 21) )
    {
      v31 = hObject;
      if ( hObject )
      {
        v32 = *(void **)(*(_QWORD *)v16 + 8LL);
        v33 = GetCurrentProcess();
        if ( !DuplicateHandle(v33, v31, v32, v68, 0, 0, 2u) )
        {
          v28 = GetLastError();
          if ( v28 > 0 )
            v28 = (unsigned __int16)v28 | 0x80070000;
          *(_DWORD *)v61 = v28;
          if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_6;
          v30 = 38;
          goto LABEL_43;
        }
      }
    }
  }
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v27, CREATE_ASSOC_CTX_PROVIDER_START, this);
  v69[0] = v61;
  v69[1] = this;
  v69[2] = a2;
  v69[3] = &v71;
  v69[4] = &v72;
  v69[5] = &TargetHandle;
  v69[6] = v68;
  v69[7] = &a5;
  *(_DWORD *)v61 = lambda_98b08e5795f36a480df9cbd41bed93cd_::operator()(v69);
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v34, CREATE_ASSOC_CTX_PROVIDER_STOP, this);
  if ( *(_DWORD *)v61 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        v35,
        40,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        (char)this,
        v61[0]);
    goto LABEL_59;
  }
LABEL_112:
  IsAssociated = StringCbLengthW(*((const unsigned __int16 **)this + 1), 0x600u, &v67);
  *(_DWORD *)v61 = IsAssociated;
  if ( IsAssociated < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v53 = 51;
LABEL_115:
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        v52,
        v53,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)this + 1),
        (char)this,
        IsAssociated);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  v54 = v67;
  v55 = (unsigned __int16 *)DAF_user_alloc(v67 + 2);
  v57 = v62;
  *v62 = v55;
  if ( v55 )
  {
    IsAssociated = StringCbCopyW(v55, v54 + 2, *((const unsigned __int16 **)this + 1));
    *(_DWORD *)v61 = IsAssociated;
    if ( IsAssociated < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_59;
      v53 = 53;
      goto LABEL_115;
    }
    if ( *((_DWORD *)v11 + 18) && !hObject )
      *(_DWORD *)v61 = GetRpcClientToken(&hObject);
    IsAssociated = CAssociationContext::IsAssociated(this, hObject);
    *(_DWORD *)v61 = IsAssociated;
    if ( !IsAssociated )
    {
      *((_DWORD *)this + 7) = 1;
      goto LABEL_59;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v53 = 54;
      goto LABEL_115;
    }
LABEL_59:
    v9 = v63;
    goto LABEL_20;
  }
  *(_DWORD *)v61 = -2147024882;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      v56,
      52,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)this + 1),
      (char)this,
      14);
    goto LABEL_59;
  }
  v9 = v63;
  v8 = (wil::details **)v57;
LABEL_21:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( *(int *)v61 < 0 )
    goto LABEL_24;
LABEL_27:
  v20 = (void *)*((_QWORD *)this + 13);
  if ( v20 )
    CloseHandle(v20);
  if ( v9 )
  {
    WaitForThreadpoolWorkCallbacks(v9, 1);
    CloseThreadpoolWork(v9);
  }
  v21 = *(_DWORD *)v61;
  if ( v66[1] )
    std::_Ref_count_base::_Decref(v66[1]);
  return v21;
}

```

## disassembly

```asm
0x180055e2c  mov     rax, rsp
0x180055e2f  mov     [rax+10h], rbx
0x180055e33  mov     [rax+20h], r9
0x180055e37  mov     [rax+18h], r8d
0x180055e3b  push    rbp
0x180055e3c  push    rsi
0x180055e3d  push    rdi
0x180055e3e  push    r12
0x180055e40  push    r13
0x180055e42  push    r14
0x180055e44  push    r15
0x180055e46  lea     rbp, [rax-58h]
0x180055e4a  sub     rsp, 130h
0x180055e51  mov     r12, rdx
0x180055e54  mov     r14, rcx
0x180055e57  mov     rsi, [rbp+50h+arg_28]
0x180055e5e  mov     [rbp+50h+var_C8], rsi
0x180055e62  xor     r13d, r13d
0x180055e65  mov     dword ptr [rbp+50h+var_D0], r13d
0x180055e69  xorps   xmm0, xmm0
0x180055e6c  movdqu  xmmword ptr [rbp+50h+var_A8], xmm0
0x180055e71  mov     ebx, r13d
0x180055e74  mov     [rbp+50h+var_C0], rbx
0x180055e78  mov     [rbp+50h+var_98], r13
0x180055e7c  mov     [rbp+50h+hObject], r13
0x180055e80  mov     [rsi], r13
0x180055e83  mov     [rcx+68h], r13
0x180055e87  mov     eax, [rbp+50h+arg_20]
0x180055e8d  mov     [rcx+18h], eax
0x180055e90  cmp     [rcx+1Ch], r13d
0x180055e94  jz      short loc_180055EA2
0x180055e96  mov     dword ptr [rbp+50h+var_D0], 8064000Fh
0x180055e9d  jmp     loc_1800560D1
0x180055ea2  lea     r8, [rbp+50h+var_A8]
0x180055ea6  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x180055ead  call    ?GetProviderFromProtocolId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBU_GUID@@AEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(_GUID const *,std::shared_ptr<ProviderContext> &)
0x180055eb2  mov     r15d, eax
0x180055eb5  mov     dword ptr [rbp+50h+var_D0], eax
0x180055eb8  test    eax, eax
0x180055eba  jz      loc_180055F6C
0x180055ec0  lea     rdi, WPP_RECORDER_INITIALIZED
0x180055ec7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180055ece  jz      loc_1800560B8
0x180055ed4  movzx   eax, byte ptr [r12+0Fh]
0x180055eda  movzx   ecx, byte ptr [r12+0Eh]
0x180055ee0  movzx   edx, byte ptr [r12+0Dh]
0x180055ee6  movzx   r8d, byte ptr [r12+0Ch]
0x180055eec  movzx   r9d, byte ptr [r12+0Bh]
0x180055ef2  movzx   r10d, byte ptr [r12+0Ah]
0x180055ef8  movzx   r11d, byte ptr [r12+9]
0x180055efe  movzx   ebx, byte ptr [r12+8]
0x180055f04  movzx   edi, word ptr [r12+6]
0x180055f0a  movzx   esi, word ptr [r12+4]
0x180055f10  mov     [rsp+88h], r15d
0x180055f18  mov     qword ptr [rsp+160h+var_E0], r14
0x180055f20  mov     dword ptr [rsp+160h+var_E8], eax
0x180055f24  mov     [rsp+160h+var_F0], ecx
0x180055f28  mov     [rsp+160h+var_F8], edx
0x180055f2c  mov     [rsp+160h+var_100], r8d
0x180055f31  mov     [rsp+160h+var_108], r9d
0x180055f36  mov     [rsp+160h+var_110], r10d
0x180055f3b  mov     [rsp+160h+var_118], r11d
0x180055f40  mov     [rsp+160h+var_120], ebx
0x180055f44  mov     dword ptr [rsp+160h+var_128], edi
0x180055f48  mov     dword ptr [rsp+160h+dwOptions], esi
0x180055f4c  mov     eax, [r12]
0x180055f50  mov     [rsp+160h+bInheritHandle], eax
0x180055f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f5b  mov     rcx, [rcx+28h]
0x180055f5f  call    WPP_RECORDER_SF_DDDDDDDDDDDqD
0x180055f64  mov     rbx, r13
0x180055f67  jmp     loc_1800560B4
0x180055f6c  mov     rsi, [rbp+50h+var_A8]
0x180055f70  lea     r15, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180055f77  lea     rdi, WPP_RECORDER_INITIALIZED
0x180055f7e  cmp     [rsi+48h], r13d
0x180055f82  jz      short loc_180055FD1
0x180055f84  lea     rcx, [rbp+50h+hObject]; TokenHandle
0x180055f88  call    ?GetRpcClientToken@@YAJPEAPEAX@Z; GetRpcClientToken(void * *)
0x180055f8d  mov     dword ptr [rbp+50h+var_D0], eax
0x180055f90  test    eax, eax
0x180055f92  jns     short loc_180056004
0x180055f94  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180055f9b  jz      loc_1800560B4
0x180055fa1  mov     r9d, 22h ; '"'; int
0x180055fa7  mov     dword ptr [rsp+160h+dwOptions], eax; char
0x180055fab  mov     qword ptr [rsp+160h+bInheritHandle], r14; char
0x180055fb0  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180055fb7  mov     qword ptr [rsp+160h+dwDesiredAccess], rax; MessageGuid
0x180055fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180055fc3  mov     rcx, [rcx+28h]; int
0x180055fc7  call    WPP_RECORDER_SF_qD
0x180055fcc  jmp     loc_1800560B4
0x180055fd1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180055fd8  jz      short loc_18005600B
0x180055fda  mov     r9d, 23h ; '#'; int
0x180055fe0  mov     qword ptr [rsp+160h+dwOptions], r14; char
0x180055fe5  mov     rax, [rsi]
0x180055fe8  mov     qword ptr [rsp+160h+bInheritHandle], rax; __int64
0x180055fed  mov     qword ptr [rsp+160h+dwDesiredAccess], r15; MessageGuid
0x180055ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ff9  mov     rcx, [rcx+28h]; int
0x180055ffd  call    WPP_RECORDER_SF_Sq
0x180056002  jmp     short loc_18005600B
0x180056004  lea     r15, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18005600b  lea     rdx, [rbp+50h+var_A8]
0x18005600f  lea     rcx, [rbp+50h+var_90]
0x180056013  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x180056018  mov     rdx, rax
0x18005601b  xor     r9d, r9d
0x18005601e  xor     r8d, r8d
0x180056021  mov     rcx, r14; pv
0x180056024  call    ?InitSetAssociation@CAssociationContext@@IEAAJV?$shared_ptr@VProviderContext@@@std@@KPEBU_DAF_ASSOCIATION_PARAMETER@@@Z; CAssociationContext::InitSetAssociation(std::shared_ptr<ProviderContext>,ulong,_DAF_ASSOCIATION_PARAMETER const *)
0x180056029  mov     dword ptr [rbp+50h+var_D0], eax
0x18005602c  test    eax, eax
0x18005602e  js      loc_1800560B4
0x180056034  mov     ecx, [rsi+30h]
0x180056037  mov     eax, r13d
0x18005603a  test    ecx, ecx
0x18005603c  setnz   al
0x18005603f  mov     [r14+20h], eax
0x180056043  mov     [rbp+50h+TargetHandle], r13
0x180056047  test    ecx, ecx
0x180056049  jz      loc_180056350
0x18005604f  mov     [rbp+50h+var_90], r13
0x180056053  lea     r13, [r14+258h]
0x18005605a  lea     rdx, [rbp+50h+var_A8]
0x18005605e  lea     rcx, [rbp+50h+var_40]
0x180056062  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x180056067  mov     rcx, rax
0x18005606a  mov     rdx, r13
0x18005606d  call    ?GetHostContext@CHostContext@@SAJV?$shared_ptr@VProviderContext@@@std@@PEAPEAV1@@Z; CHostContext::GetHostContext(std::shared_ptr<ProviderContext>,CHostContext * *)
0x180056072  mov     dword ptr [rbp+50h+var_D0], eax
0x180056075  test    eax, eax
0x180056077  jz      loc_180056142
0x18005607d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180056084  jz      short loc_1800560B1
0x180056086  mov     r9d, 24h ; '$'; int
0x18005608c  mov     dword ptr [rsp+160h+dwOptions], eax; char
0x180056090  mov     qword ptr [rsp+160h+bInheritHandle], r14; char
0x180056095  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18005609c  mov     qword ptr [rsp+160h+dwDesiredAccess], rax; MessageGuid
0x1800560a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560a8  mov     rcx, [rcx+28h]; int
0x1800560ac  call    WPP_RECORDER_SF_qD
0x1800560b1  xor     r13d, r13d
0x1800560b4  mov     rsi, [rbp+50h+var_C8]
0x1800560b8  mov     rcx, [rbp+50h+hObject]; hObject
0x1800560bc  test    rcx, rcx
0x1800560bf  jz      short loc_1800560CB
0x1800560c1  call    cs:__imp_CloseHandle
0x1800560c7  mov     [rbp+50h+hObject], r13
0x1800560cb  cmp     dword ptr [rbp+50h+var_D0], r13d
0x1800560cf  jge     short loc_1800560E9
0x1800560d1  mov     rcx, [rsi]; this
0x1800560d4  test    rcx, rcx
0x1800560d7  jz      short loc_1800560E1
0x1800560d9  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800560de  mov     [rsi], r13
0x1800560e1  mov     dword ptr [r14+1Ch], 0FFFFFFFFh
0x1800560e9  mov     rcx, [r14+68h]; hObject
0x1800560ed  test    rcx, rcx
0x1800560f0  jz      short loc_1800560F8
0x1800560f2  call    cs:__imp_CloseHandle
0x1800560f8  test    rbx, rbx
0x1800560fb  jz      short loc_180056114
0x1800560fd  mov     edx, 1; fCancelPendingCallbacks
0x180056102  mov     rcx, rbx; pwk
0x180056105  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005610b  mov     rcx, rbx; pwk
0x18005610e  call    cs:__imp_CloseThreadpoolWork
0x180056114  mov     ebx, dword ptr [rbp+50h+var_D0]
0x180056117  mov     rcx, [rbp+50h+var_A8+8]; this
0x18005611b  test    rcx, rcx
0x18005611e  jz      short loc_180056125
0x180056120  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056125  mov     eax, ebx
0x180056127  mov     rbx, [rsp+160h+arg_8]
0x18005612f  add     rsp, 130h
0x180056136  pop     r15
0x180056138  pop     r14
0x18005613a  pop     r13
0x18005613c  pop     r12
0x18005613e  pop     rdi
0x18005613f  pop     rsi
0x180056140  pop     rbp
0x180056141  retn
0x180056142  xor     r9d, r9d; lpName
0x180056145  xor     r8d, r8d; bInitialState
0x180056148  lea     edx, [r9+1]; bManualReset
0x18005614c  xor     ecx, ecx; lpEventAttributes
0x18005614e  call    cs:__imp_CreateEventW
0x180056154  mov     r15, rax
0x180056157  mov     [r14+38h], rax
0x18005615b  test    rax, rax
0x18005615e  jnz     short loc_18005617D
0x180056160  call    cs:__imp_GetLastError
0x180056166  xor     r13d, r13d
0x180056169  test    eax, eax
0x18005616b  jle     short loc_180056175
0x18005616d  movzx   eax, ax
0x180056170  or      eax, 80070000h
0x180056175  mov     dword ptr [rbp+50h+var_D0], eax
0x180056178  jmp     loc_1800560B4
0x18005617d  mov     rax, [r13+0]
0x180056181  mov     rbx, [rax+8]
0x180056185  call    cs:__imp_GetCurrentProcess
0x18005618b  mov     dword ptr [rsp+160h+dwOptions], 2; dwOptions
0x180056193  mov     [rsp+160h+bInheritHandle], 0; bInheritHandle
0x18005619b  mov     [rsp+160h+dwDesiredAccess], 0; dwDesiredAccess
0x1800561a3  lea     r9, [rbp+50h+TargetHandle]; lpTargetHandle
0x1800561a7  mov     r8, rbx; hTargetProcessHandle
0x1800561aa  mov     rdx, r15; hSourceHandle
0x1800561ad  mov     rcx, rax; hSourceProcessHandle
0x1800561b0  call    cs:__imp_DuplicateHandle
0x1800561b6  test    eax, eax
0x1800561b8  jnz     short loc_18005620F
0x1800561ba  call    cs:__imp_GetLastError
0x1800561c0  xor     r13d, r13d
0x1800561c3  test    eax, eax
0x1800561c5  jle     short loc_1800561CF
0x1800561c7  movzx   eax, ax
0x1800561ca  or      eax, 80070000h
0x1800561cf  mov     dword ptr [rbp+50h+var_D0], eax
0x1800561d2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800561d9  jz      loc_180055F64
0x1800561df  mov     r9d, 25h ; '%'; int
0x1800561e5  mov     dword ptr [rsp+160h+dwOptions], eax; char
0x1800561e9  mov     qword ptr [rsp+160h+bInheritHandle], r14; char
0x1800561ee  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x1800561f5  mov     qword ptr [rsp+160h+dwDesiredAccess], rax; MessageGuid
0x1800561fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180056201  mov     rcx, [rcx+28h]; int
0x180056205  call    WPP_RECORDER_SF_qD
0x18005620a  jmp     loc_180055F64
0x18005620f  cmp     dword ptr [rsi+48h], 0
0x180056213  jz      short loc_18005628B
0x180056215  cmp     dword ptr [rsi+54h], 0
0x180056219  jz      short loc_18005628B
0x18005621b  mov     r15, [rbp+50h+hObject]
0x18005621f  test    r15, r15
0x180056222  jz      short loc_18005628B
0x180056224  mov     rax, [r13+0]
0x180056228  mov     rbx, [rax+8]
0x18005622c  call    cs:__imp_GetCurrentProcess
0x180056232  mov     dword ptr [rsp+160h+dwOptions], 2; dwOptions
0x18005623a  xor     r13d, r13d
0x18005623d  mov     [rsp+160h+bInheritHandle], r13d; bInheritHandle
0x180056242  mov     [rsp+160h+dwDesiredAccess], r13d; dwDesiredAccess
0x180056247  lea     r9, [rbp+50h+var_90]; lpTargetHandle
0x18005624b  mov     r8, rbx; hTargetProcessHandle
0x18005624e  mov     rdx, r15; hSourceHandle
0x180056251  mov     rcx, rax; hSourceProcessHandle
0x180056254  call    cs:__imp_DuplicateHandle
0x18005625a  test    eax, eax
0x18005625c  jnz     short loc_18005628E
0x18005625e  call    cs:__imp_GetLastError
0x180056264  test    eax, eax
0x180056266  jle     short loc_180056270
0x180056268  movzx   eax, ax
0x18005626b  or      eax, 80070000h
0x180056270  mov     dword ptr [rbp+50h+var_D0], eax
0x180056273  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005627a  jz      loc_180055F64
0x180056280  mov     r9d, 26h ; '&'
0x180056286  jmp     loc_1800561E5
0x18005628b  xor     r13d, r13d
0x18005628e  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180056295  jz      short loc_1800562A6
0x180056297  mov     r8, r14
0x18005629a  lea     rdx, CREATE_ASSOC_CTX_PROVIDER_START
0x1800562a1  call    McTemplateU0p_EventWriteTransfer
0x1800562a6  lea     rax, [rbp+50h+var_D0]
0x1800562aa  mov     [rbp+50h+var_80], rax
0x1800562ae  mov     [rbp+50h+var_78], r14
0x1800562b2  mov     [rbp+50h+var_70], r12
0x1800562b6  lea     rax, [rbp+50h+arg_10]
0x1800562ba  mov     [rbp+50h+var_68], rax
0x1800562be  lea     rax, [rbp+50h+arg_18]
0x1800562c2  mov     [rbp+50h+var_60], rax
0x1800562c6  lea     rax, [rbp+50h+TargetHandle]
0x1800562ca  mov     [rbp+50h+var_58], rax
0x1800562ce  lea     rax, [rbp+50h+var_90]
0x1800562d2  mov     [rbp+50h+var_50], rax
0x1800562d6  lea     rax, [rbp+50h+arg_20]
0x1800562dd  mov     [rbp+50h+var_48], rax
0x1800562e1  lea     rcx, [rbp+50h+var_80]
0x1800562e5  call    _lambda_98b08e5795f36a480df9cbd41bed93cd___operator__
0x1800562ea  mov     dword ptr [rbp+50h+var_D0], eax
0x1800562ed  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x1800562f4  jz      short loc_180056305
0x1800562f6  mov     r8, r14
0x1800562f9  lea     rdx, CREATE_ASSOC_CTX_PROVIDER_STOP
0x180056300  call    McTemplateU0p_EventWriteTransfer
0x180056305  mov     r15d, dword ptr [rbp+50h+var_D0]
0x180056309  test    r15d, r15d
0x18005630c  jz      loc_180056668
0x180056312  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180056319  jz      short loc_180056347
0x18005631b  mov     r9d, 28h ; '('; int
  ... truncated ...
```
