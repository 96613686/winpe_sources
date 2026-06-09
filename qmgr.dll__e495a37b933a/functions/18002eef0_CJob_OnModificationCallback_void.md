# CJob::OnModificationCallback(void)

- ea: `0x18002eef0`
- end: `0x18002fa7d`
- name: `?OnModificationCallback@CJob@@UEAAXXZ`
- size: `2957`
- prototype: `void __fastcall(CJob *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180022ff8`
- `0x18002c6ac`
- `0x18002e6b8`
- `0x18002eef0`
- `0x180032204`
- `0x180033420`
- `0x180033480`
- `0x180039ef0`
- `0x180060058`
- `0x180063fa0`
- `0x180083a7c`
- `0x18009bd90`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800cba5c`
- `0x1800cc300`
- `0x1800d1940`
- `0x1800eea94`
- `0x1800f9954`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f04a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f04a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ef4f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3c1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ef4f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3c1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002f409`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002f409`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18002f4cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18002f4cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f044`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f3b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f044`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f3b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f463`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f463`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002f478`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002f478`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f39b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f39b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f9c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f9c9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002ef8f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002ef8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CJob::OnModificationCallback(struct _FILETIME *this)
{
  CJobManager *v2; // rbx
  _QWORD *Value; // rax
  void *v4; // rcx
  void *v5; // rax
  DWORD v6; // eax
  bool v7; // dl
  EVENT_LOG *v8; // r13
  __int64 v9; // rdx
  EVENT_LOG *v10; // rcx
  volatile signed __int32 *v11; // r15
  struct _FILETIME v12; // rax
  bool v13; // r12
  bool v14; // r14
  struct _GUID v15; // xmm6
  int v16; // ebx
  EVENT_LOG *v17; // rcx
  __int64 v18; // rbx
  struct CJob *v19; // rbx
  CJobManager *v20; // r13
  char *v21; // rbx
  CJobManager *v22; // rbx
  EVENT_LOG *v23; // rcx
  CJob *v24; // r13
  __int64 v26; // rbx
  unsigned int v27; // eax
  unsigned int v28; // r14d
  EVENT_LOG *v30; // rcx
  unsigned int v31; // eax
  __int64 FileExternal; // rax
  int v33; // eax
  int v34; // esi
  EVENT_LOG *v35; // rcx
  __int64 v36; // rdx
  EVENT_LOG *v37; // rcx
  void *v38; // rcx
  CJob *v39; // rcx
  void *v40[2]; // [rsp+30h] [rbp-C8h] BYREF
  struct _GUID Buf1; // [rsp+40h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A0h]
  CJob *v44; // [rsp+60h] [rbp-98h]
  __int64 v45; // [rsp+68h] [rbp-90h]
  HANDLE Handles; // [rsp+70h] [rbp-88h] BYREF
  void *v47; // [rsp+78h] [rbp-80h]
  struct CJob *v48[3]; // [rsp+80h] [rbp-78h] BYREF
  const ComError *v49; // [rsp+98h] [rbp-60h] BYREF
  const ComError *v50; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v51; // [rsp+108h] [rbp+10h] BYREF
  int RangesFromList; // [rsp+110h] [rbp+18h]
  __int64 v53; // [rsp+118h] [rbp+20h] BYREF

  LODWORD(v53) = 0;
  v2 = g_Manager;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  Value = TlsGetValue(*((_DWORD *)v2 + 143));
  v4 = (void *)*((_QWORD *)v2 + 70);
  if ( Value && (v5 = (void *)Value[6]) != 0 )
  {
    Handles = v5;
    v47 = v4;
    v6 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
    if ( !v6 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)v10 + 2), 150, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
      }
      TaskScheduler::CompleteWorkItem((CJobManager *)((char *)g_Manager + 520), v7);
      return;
    }
    if ( v6 != 1 )
      goto LABEL_22;
    *((_DWORD *)v2 + 144) = GetCurrentThreadId();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 33;
LABEL_21:
      WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
LABEL_22:
      v8 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    WaitForSingleObject(v4, 0xFFFFFFFF);
    *((_DWORD *)v2 + 144) = GetCurrentThreadId();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v9 = 31;
      goto LABEL_21;
    }
  }
  v44 = (CJob *)&this[-62];
  v48[2] = (struct CJob *)&this[-62];
  v11 = (volatile signed __int32 *)&this[-62];
  Handles = &this[-62];
  LOBYTE(v47) = 1;
  v40[0] = 0;
  LODWORD(v51) = 0;
  if ( (this[38].dwHighDateTime & 0x24) != 0x20 )
    goto LABEL_33;
  if ( !LOBYTE(this[106].dwLowDateTime) )
  {
    if ( this[34].dwLowDateTime
      || (memcmp_0(&this[36].dwHighDateTime, &GUID_NULL, 0x10u) || **(_QWORD **)&this[39])
      && memcmp_0(&this[36].dwHighDateTime, &GUID_NULL, 0x10u) )
    {
      v13 = 1;
LABEL_32:
      LODWORD(v51) = CJob::NeedFileRangesTransferredCallback((CJob *)&this[-62]);
      v8 = WPP_GLOBAL_Control;
      if ( (_DWORD)v51 != 0x80000000 )
        goto LABEL_34;
    }
LABEL_33:
    v13 = 0;
    goto LABEL_34;
  }
  v12 = this[109];
  v13 = v12 != 0;
  if ( v12 )
    goto LABEL_32;
LABEL_34:
  if ( (this[38].dwHighDateTime & 0xC) != 8 )
    goto LABEL_42;
  if ( !LOBYTE(this[106].dwLowDateTime) )
  {
    if ( this[34].dwLowDateTime
      || (memcmp_0(&this[36].dwHighDateTime, &GUID_NULL, 0x10u) || **(_QWORD **)&this[39])
      && memcmp_0(&this[36].dwHighDateTime, &GUID_NULL, 0x10u) )
    {
      v14 = 1;
      goto LABEL_43;
    }
LABEL_42:
    v14 = 0;
    goto LABEL_43;
  }
  v14 = *(_QWORD *)&this[109] != 0;
LABEL_43:
  RangesFromList = 0;
  v15 = *(struct _GUID *)&this[36].dwHighDateTime;
  pv = 0;
  v43 = 0;
  if ( v14 || v13 )
  {
    if ( this[34].dwLowDateTime )
    {
      v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, DWORD *, void **))(*(_QWORD *)g_GIT + 40LL))(
              g_GIT,
              this[34].dwLowDateTime,
              &this[34].dwHighDateTime,
              v40);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          151,
          &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          this[34].dwLowDateTime);
        v17 = WPP_GLOBAL_Control;
      }
      if ( v16 < 0 && v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)v17 + 2),
          152,
          &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          this[34].dwLowDateTime,
          v16);
    }
    if ( v13 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)&this[44] + 8LL * (unsigned int)v51);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&pv);
      *(_QWORD *)&Buf1.Data1 = &pv;
      *(_DWORD *)Buf1.Data4 = 0;
      Buf1.Data4[4] = 1;
      v19 = (struct CJob *)(v18 + 96);
      v48[1] = v19;
      CCritSec2::enter(v19);
      LOBYTE(v48[0]) = 1;
      RangesFromList = RangeTracker::GetRangesFromList(Buf1.Data4, &pv, (char *)v19 + 80);
      if ( RangesFromList >= 0 )
        std::list<_BG_FILE_RANGE>::clear((char *)v19 + 80);
      HoldCritSec::~HoldCritSec((HoldCritSec *)v48);
      if ( Buf1.Data4[4] )
        *(_QWORD *)(*(_QWORD *)&Buf1.Data1 + 8LL) = *(unsigned int *)Buf1.Data4;
    }
  }
  else if ( v8 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v8 + 2), 153, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
  }
  GetSystemTimeAsFileTime(this + 61);
  v20 = g_Manager;
  WaitForSingleObject(*((HANDLE *)g_Manager + 67), 0xFFFFFFFF);
  v21 = (char *)TlsGetValue(*((_DWORD *)v20 + 143));
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v21);
  if ( v21 )
  {
    TlsSetValue(*((_DWORD *)v20 + 143), 0);
    *((_QWORD *)v21 + 11) = 0;
    if ( *((_QWORD *)v21 + 3) == *((_QWORD *)v21 + 9) + 56LL && *((_QWORD *)v21 + 3) )
    {
      **((_QWORD **)v21 + 2) = *((_QWORD *)v21 + 1);
      *(_QWORD *)(*((_QWORD *)v21 + 1) + 8LL) = *((_QWORD *)v21 + 2);
      --*(_QWORD *)(*((_QWORD *)v21 + 3) + 24LL);
      *((_QWORD *)v21 + 1) = v21 + 8;
      *((_QWORD *)v21 + 2) = v21 + 8;
      *((_QWORD *)v21 + 3) = 0;
    }
    *((_QWORD *)v21 + 9) = 0;
    *((_DWORD *)v21 + 20) = 5;
    SetEvent(*((HANDLE *)v21 + 7));
    *((_QWORD *)v21 + 6) = 0;
    *((_QWORD *)v21 + 7) = 0;
  }
  ReleaseMutex(*((HANDLE *)v20 + 67));
  v22 = g_Manager;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  *((_DWORD *)v22 + 144) = 0;
  ReleaseSemaphore(*((HANDLE *)v22 + 70), 1, 0);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  if ( !v14 && !v13 )
  {
    v24 = v44;
LABEL_137:
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
      v43 = 0;
    }
    v38 = v40[0];
    if ( v40[0] )
    {
      v40[0] = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
    }
LABEL_141:
    _InterlockedDecrement(v11 + 148);
    CJob::ReevaluateIdleStopConditions((CJob *)v11);
    if ( !v24 )
      return;
LABEL_146:
    RefCountedObject::Release((CJob *)((char *)v24 + 600));
    return;
  }
  if ( v40[0] )
  {
    v24 = v44;
  }
  else
  {
    Buf1 = v15;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
    v24 = v44;
    if ( !CJob::CreateNotifyInterfaceIfNeeded(v44, &Buf1, v40) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&pv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
      goto LABEL_141;
    }
  }
  try
  {
    v45 = 0;
    v48[0] = v24;
    BitsComModule::ThrowingMakeInDisconnectableContext<CJobExternal,IBackgroundCopyJob5,CJob *>(
      (__int64)v23,
      (__int64 *)&Buf1,
      v48);
  }
  catch ( const ComError *v50 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        155,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)v50 + 6));
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&pv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
    v39 = (CJob *)Handles;
    _InterlockedDecrement((volatile signed __int32 *)Handles + 148);
    CJob::ReevaluateIdleStopConditions(v39);
    v24 = v44;
    if ( v44 )
      goto LABEL_146;
    return;
  }
  v26 = *(_QWORD *)&Buf1.Data1;
  v45 = *(_QWORD *)&Buf1.Data1;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
    v27 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v40[0] + 40LL))(v40[0], v26, 0);
    v28 = v27;
    if ( v27 == -2147023174 )
    {
      Buf1 = v15;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
      if ( CJob::CreateNotifyInterfaceIfNeeded(v24, &Buf1, v40) )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
            v30 = WPP_GLOBAL_Control;
          }
          if ( v30 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 )
            WPP_SF_q(*((_QWORD *)v30 + 2), 158, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
        }
        v31 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v40[0] + 40LL))(v40[0], v26, 0);
        v28 = v31;
      }
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v28);
  }
  v53 = 0;
  if ( !v13 )
  {
LABEL_132:
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_137;
  }
  try
  {
    FileExternal = CFile::GetFileExternal(*(_QWORD *)(*(_QWORD *)&this[44] + 8LL * (unsigned int)v51), &v51);
    Microsoft::WRL::ComPtr<IBackgroundCopyFile>::operator=(&v53, FileExternal);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v51 = 0;
    v33 = Microsoft::WRL::ComPtr<IBackgroundCopyCallback>::As<IBackgroundCopyCallback3>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v40,
            (__int64)&v51);
  }
  catch ( const ComError *v49 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)v49 + 6));
    v11 = (volatile signed __int32 *)Handles;
    v26 = v45;
    v24 = v44;
    goto LABEL_132;
  }
  v34 = v33;
  if ( v33 >= 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
      v35 = WPP_GLOBAL_Control;
    }
    if ( RangesFromList >= 0 )
    {
      v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, LPVOID))(*(_QWORD *)v51 + 56LL))(
              v51,
              v26,
              v53,
              (unsigned int)v43,
              pv);
      if ( v34 != -2147023174 )
        goto LABEL_127;
      Buf1 = v15;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40);
      if ( !CJob::CreateNotifyInterfaceIfNeeded(v24, &Buf1, v40) )
        goto LABEL_127;
      v34 = Microsoft::WRL::ComPtr<IBackgroundCopyCallback>::As<IBackgroundCopyCallback3>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v40,
              (__int64)&v51);
      if ( v34 >= 0 )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
            v37 = WPP_GLOBAL_Control;
          }
          if ( v37 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
            WPP_SF_q(*((_QWORD *)v37 + 2), 166, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v24);
        }
        v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, LPVOID))(*(_QWORD *)v51 + 56LL))(
                v51,
                v26,
                v53,
                (unsigned int)v43,
                pv);
        goto LABEL_127;
      }
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v36 = 164;
          goto LABEL_106;
        }
LABEL_128:
        if ( v35 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)v35 + 2), 167, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, (unsigned int)v34);
      }
    }
    else if ( v35 != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      v34 = RangesFromList;
      if ( (*((_BYTE *)v35 + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)v35 + 2),
          163,
          &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          (unsigned int)RangesFromList);
        goto LABEL_127;
      }
      goto LABEL_128;
    }
  }
  else
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v36 = 161;
LABEL_106:
        WPP_SF_(*((_QWORD *)v35 + 2), v36, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
LABEL_127:
        v35 = WPP_GLOBAL_Control;
        goto LABEL_128;
      }
      goto LABEL_128;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  goto LABEL_132;
}

```

## disassembly

```asm
0x18002eef0  mov     rax, rsp
0x18002eef3  push    rbx
0x18002eef4  push    rsi
0x18002eef5  push    rdi
0x18002eef6  push    r12
0x18002eef8  push    r13
0x18002eefa  push    r14
0x18002eefc  push    r15
0x18002eefe  sub     rsp, 0C0h
0x18002ef05  movaps  xmmword ptr [rax-48h], xmm6
0x18002ef09  mov     rsi, rcx
0x18002ef0c  xor     edi, edi
0x18002ef0e  mov     [rax+20h], edi
0x18002ef11  mov     rbx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002ef18  lea     r14, WPP_GLOBAL_Control
0x18002ef1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef26  cmp     rcx, r14
0x18002ef29  jz      short loc_18002EF49
0x18002ef2b  test    dword ptr [rcx+1Ch], 100h
0x18002ef32  jz      short loc_18002EF49
0x18002ef34  mov     edx, 1Eh
0x18002ef39  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18002ef40  mov     rcx, [rcx+10h]
0x18002ef44  call    WPP_SF_
0x18002ef49  mov     ecx, [rbx+23Ch]; dwTlsIndex
0x18002ef4f  call    cs:__imp_TlsGetValue
0x18002ef55  mov     rcx, [rbx+230h]; hHandle
0x18002ef5c  test    rax, rax
0x18002ef5f  jz      loc_18002F03F
0x18002ef65  mov     rax, [rax+30h]
0x18002ef69  test    rax, rax
0x18002ef6c  jz      loc_18002F03F
0x18002ef72  mov     [rsp+0F8h+Handles], rax
0x18002ef77  mov     [rsp+0F8h+var_80], rcx
0x18002ef7c  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18002ef82  xor     r8d, r8d; bWaitAll
0x18002ef85  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18002ef8a  mov     ecx, 2; nCount
0x18002ef8f  call    cs:__imp_WaitForMultipleObjects
0x18002ef95  test    eax, eax
0x18002ef97  jz      short loc_18002EFD6
0x18002ef99  cmp     eax, 1
0x18002ef9c  jnz     loc_18002F081
0x18002efa2  call    cs:__imp_GetCurrentThreadId
0x18002efa8  mov     [rbx+240h], eax
0x18002efae  mov     r13, cs:WPP_GLOBAL_Control
0x18002efb5  cmp     r13, r14
0x18002efb8  jz      loc_18002F088
0x18002efbe  test    dword ptr [r13+1Ch], 100h
0x18002efc6  jz      loc_18002F088
0x18002efcc  mov     edx, 21h ; '!'
0x18002efd1  jmp     loc_18002F071
0x18002efd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efdd  cmp     rcx, r14
0x18002efe0  jz      short loc_18002F027
0x18002efe2  test    dword ptr [rcx+1Ch], 100h
0x18002efe9  jz      short loc_18002F007
0x18002efeb  mov     edx, 20h ; ' '
0x18002eff0  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18002eff7  mov     rcx, [rcx+10h]
0x18002effb  call    WPP_SF_
0x18002f000  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f007  cmp     rcx, r14
0x18002f00a  jz      short loc_18002F027
0x18002f00c  test    byte ptr [rcx+1Ch], 1
0x18002f010  jz      short loc_18002F027
0x18002f012  mov     edx, 96h
0x18002f017  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002f01e  mov     rcx, [rcx+10h]
0x18002f022  call    WPP_SF_
0x18002f027  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002f02e  add     rcx, 208h; this
0x18002f035  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x18002f03a  jmp     loc_18002FA62
0x18002f03f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18002f044  call    cs:__imp_WaitForSingleObject
0x18002f04a  call    cs:__imp_GetCurrentThreadId
0x18002f050  mov     [rbx+240h], eax
0x18002f056  mov     r13, cs:WPP_GLOBAL_Control
0x18002f05d  cmp     r13, r14
0x18002f060  jz      short loc_18002F088
0x18002f062  test    dword ptr [r13+1Ch], 100h
0x18002f06a  jz      short loc_18002F088
0x18002f06c  mov     edx, 1Fh
0x18002f071  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18002f078  mov     rcx, [r13+10h]
0x18002f07c  call    WPP_SF_
0x18002f081  mov     r13, cs:WPP_GLOBAL_Control
0x18002f088  lea     r14, [rsi-1F0h]
0x18002f08f  mov     [rsp+0F8h+var_98], r14
0x18002f094  mov     [rsp+0F8h+var_68], r14
0x18002f09c  mov     r15, r14
0x18002f09f  mov     [rsp+0F8h+Handles], r14
0x18002f0a4  mov     byte ptr [rsp+0F8h+var_80], 1
0x18002f0a9  mov     [rsp+0F8h+var_C8], rdi
0x18002f0ae  mov     dword ptr [rsp+0F8h+arg_8], edi
0x18002f0b5  mov     eax, [rsi+134h]
0x18002f0bb  and     al, 24h
0x18002f0bd  cmp     al, 20h ; ' '
0x18002f0bf  jnz     loc_18002F153
0x18002f0c5  cmp     byte ptr [rsi+350h], 0
0x18002f0cc  jz      short loc_18002F0E3
0x18002f0ce  mov     rax, [rsi+368h]
0x18002f0d5  test    rax, rax
0x18002f0d8  setnz   r12b
0x18002f0dc  test    rax, rax
0x18002f0df  jnz     short loc_18002F136
0x18002f0e1  jmp     short loc_18002F156
0x18002f0e3  cmp     dword ptr [rsi+110h], 0
0x18002f0ea  jnz     short loc_18002F133
0x18002f0ec  lea     rcx, [rsi+124h]; Buf1
0x18002f0f3  mov     r8d, 10h; Size
0x18002f0f9  lea     rdx, GUID_NULL; Buf2
0x18002f100  call    memcmp_0
0x18002f105  test    eax, eax
0x18002f107  jnz     short loc_18002F116
0x18002f109  mov     rax, [rsi+138h]
0x18002f110  cmp     qword ptr [rax], 0
0x18002f114  jz      short loc_18002F153
0x18002f116  lea     rcx, [rsi+124h]; Buf1
0x18002f11d  mov     r8d, 10h; Size
0x18002f123  lea     rdx, GUID_NULL; Buf2
0x18002f12a  call    memcmp_0
0x18002f12f  test    eax, eax
0x18002f131  jz      short loc_18002F153
0x18002f133  mov     r12b, 1
0x18002f136  mov     rcx, r14; this
0x18002f139  call    ?NeedFileRangesTransferredCallback@CJob@@IEAAKXZ; CJob::NeedFileRangesTransferredCallback(void)
0x18002f13e  mov     dword ptr [rsp+0F8h+arg_8], eax
0x18002f145  mov     r13, cs:WPP_GLOBAL_Control
0x18002f14c  cmp     eax, 80000000h
0x18002f151  jnz     short loc_18002F156
0x18002f153  xor     r12b, r12b
0x18002f156  mov     eax, [rsi+134h]
0x18002f15c  and     al, 0Ch
0x18002f15e  cmp     al, 8
0x18002f160  jnz     short loc_18002F1CE
0x18002f162  cmp     byte ptr [rsi+350h], 0
0x18002f169  jz      short loc_18002F179
0x18002f16b  cmp     qword ptr [rsi+368h], 0
0x18002f173  setnz   r14b
0x18002f177  jmp     short loc_18002F1D1
0x18002f179  cmp     dword ptr [rsi+110h], 0
0x18002f180  jnz     short loc_18002F1C9
0x18002f182  lea     rcx, [rsi+124h]; Buf1
0x18002f189  mov     r8d, 10h; Size
0x18002f18f  lea     rdx, GUID_NULL; Buf2
0x18002f196  call    memcmp_0
0x18002f19b  test    eax, eax
0x18002f19d  jnz     short loc_18002F1AC
0x18002f19f  mov     rax, [rsi+138h]
0x18002f1a6  cmp     qword ptr [rax], 0
0x18002f1aa  jz      short loc_18002F1CE
0x18002f1ac  lea     rcx, [rsi+124h]; Buf1
0x18002f1b3  mov     r8d, 10h; Size
0x18002f1b9  lea     rdx, GUID_NULL; Buf2
0x18002f1c0  call    memcmp_0
0x18002f1c5  test    eax, eax
0x18002f1c7  jz      short loc_18002F1CE
0x18002f1c9  mov     r14b, 1
0x18002f1cc  jmp     short loc_18002F1D1
0x18002f1ce  xor     r14b, r14b
0x18002f1d1  mov     [rsp+0F8h+arg_10], edi
0x18002f1d8  movups  xmm6, xmmword ptr [rsi+124h]
0x18002f1df  mov     [rsp+0F8h+pv], rdi
0x18002f1e4  mov     [rsp+0F8h+var_A0], rdi
0x18002f1e9  test    r14b, r14b
0x18002f1ec  jnz     short loc_18002F228
0x18002f1ee  test    r12b, r12b
0x18002f1f1  jnz     short loc_18002F228
0x18002f1f3  lea     rax, WPP_GLOBAL_Control
0x18002f1fa  cmp     r13, rax
0x18002f1fd  jz      loc_18002F394
0x18002f203  test    byte ptr [r13+1Ch], 1
0x18002f208  jz      loc_18002F394
0x18002f20e  mov     edx, 99h
0x18002f213  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002f21a  mov     rcx, [r13+10h]
0x18002f21e  call    WPP_SF_
0x18002f223  jmp     loc_18002F394
0x18002f228  cmp     dword ptr [rsi+110h], 0
0x18002f22f  jz      loc_18002F2F6
0x18002f235  mov     r10, cs:?g_GIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_GIT
0x18002f23c  mov     rax, [r10]
0x18002f23f  mov     rbx, [rax+28h]
0x18002f243  mov     rcx, [rsp+0F8h+var_C8]
0x18002f248  test    rcx, rcx
0x18002f24b  jz      short loc_18002F265
0x18002f24d  mov     [rsp+0F8h+var_C8], rdi
0x18002f252  mov     rax, [rcx]
0x18002f255  mov     rax, [rax+10h]
0x18002f259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f25e  mov     r10, cs:?g_GIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_GIT
0x18002f265  lea     r8, [rsi+114h]
0x18002f26c  lea     r9, [rsp+0F8h+var_C8]
0x18002f271  mov     edx, [rsi+110h]
0x18002f277  mov     rcx, r10
0x18002f27a  mov     rax, rbx
0x18002f27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f282  mov     ebx, eax
0x18002f284  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f28b  lea     rax, WPP_GLOBAL_Control
0x18002f292  cmp     rcx, rax
0x18002f295  jz      short loc_18002F2C7
0x18002f297  test    byte ptr [rcx+1Ch], 1
0x18002f29b  jz      short loc_18002F2C7
0x18002f29d  mov     edx, 97h
0x18002f2a2  mov     r9d, [rsi+110h]
0x18002f2a9  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002f2b0  mov     rcx, [rcx+10h]
0x18002f2b4  call    WPP_SF_d
0x18002f2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2c0  lea     rax, WPP_GLOBAL_Control
0x18002f2c7  test    ebx, ebx
0x18002f2c9  jns     short loc_18002F2F6
0x18002f2cb  cmp     rcx, rax
0x18002f2ce  jz      short loc_18002F2F6
0x18002f2d0  test    byte ptr [rcx+1Ch], 4
0x18002f2d4  jz      short loc_18002F2F6
0x18002f2d6  mov     edx, 98h
0x18002f2db  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x18002f2df  mov     r9d, [rsi+110h]
0x18002f2e6  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002f2ed  mov     rcx, [rcx+10h]
0x18002f2f1  call    WPP_SF_Dd
0x18002f2f6  test    r12b, r12b
0x18002f2f9  jz      loc_18002F394
0x18002f2ff  mov     ecx, dword ptr [rsp+0F8h+arg_8]
0x18002f306  mov     rax, [rsi+160h]
0x18002f30d  mov     rbx, [rax+rcx*8]
0x18002f311  lea     rcx, [rsp+0F8h+pv]
0x18002f316  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18002f31b  lea     rax, [rsp+0F8h+pv]
0x18002f320  mov     qword ptr [rsp+0F8h+Buf1.Data1], rax
0x18002f325  mov     dword ptr [rsp+0F8h+Buf1.Data4], edi
0x18002f329  mov     [rsp+0F8h+Buf1.Data4+4], 1
0x18002f32e  add     rbx, 60h ; '`'
0x18002f332  mov     [rsp+0F8h+var_70], rbx
0x18002f33a  mov     rcx, rbx; this
0x18002f33d  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x18002f342  mov     byte ptr [rsp+0F8h+var_78], 1
0x18002f34a  lea     r8, [rbx+50h]
0x18002f34e  lea     rdx, [rsp+0F8h+pv]
0x18002f353  lea     rcx, [rsp+0F8h+Buf1.Data4]
0x18002f358  call    ?GetRangesFromList@RangeTracker@@KAJPEAKPEAPEAU_BG_FILE_RANGE@@AEBV?$list@U_BG_FILE_RANGE@@V?$allocator@U_BG_FILE_RANGE@@@std@@@std@@@Z; RangeTracker::GetRangesFromList(ulong *,_BG_FILE_RANGE * *,std::list<_BG_FILE_RANGE> const &)
0x18002f35d  mov     [rsp+0F8h+arg_10], eax
0x18002f364  test    eax, eax
0x18002f366  js      short loc_18002F372
0x18002f368  lea     rcx, [rbx+50h]
0x18002f36c  call    ?clear@?$list@U_BG_FILE_RANGE@@V?$allocator@U_BG_FILE_RANGE@@@std@@@std@@QEAAXXZ; std::list<_BG_FILE_RANGE>::clear(void)
0x18002f371  nop
0x18002f372  lea     rcx, [rsp+0F8h+var_78]; this
0x18002f37a  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18002f37f  nop
0x18002f380  cmp     [rsp+0F8h+Buf1.Data4+4], 0
0x18002f385  jz      short loc_18002F394
0x18002f387  mov     ecx, dword ptr [rsp+0F8h+Buf1.Data4]
0x18002f38b  mov     rax, qword ptr [rsp+0F8h+Buf1.Data1]
0x18002f390  mov     [rax+8], rcx
0x18002f394  lea     rcx, [rsi+1E8h]; lpSystemTimeAsFileTime
0x18002f39b  call    cs:__imp_GetSystemTimeAsFileTime
0x18002f3a1  mov     r13, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002f3a8  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18002f3ad  mov     rcx, [r13+218h]; hHandle
0x18002f3b4  call    cs:__imp_WaitForSingleObject
0x18002f3ba  mov     ecx, [r13+23Ch]; dwTlsIndex
0x18002f3c1  call    cs:__imp_TlsGetValue
0x18002f3c7  mov     rbx, rax
0x18002f3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3d1  lea     rax, WPP_GLOBAL_Control
0x18002f3d8  cmp     rcx, rax
0x18002f3db  jz      short loc_18002F3FB
0x18002f3dd  test    byte ptr [rcx+1Ch], 80h
0x18002f3e1  jz      short loc_18002F3FB
0x18002f3e3  mov     edx, 0Eh
0x18002f3e8  mov     r9, rbx
0x18002f3eb  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18002f3f2  mov     rcx, [rcx+10h]
0x18002f3f6  call    WPP_SF_q
0x18002f3fb  test    rbx, rbx
0x18002f3fe  jz      short loc_18002F471
0x18002f400  xor     edx, edx; lpTlsValue
0x18002f402  mov     ecx, [r13+23Ch]; dwTlsIndex
0x18002f409  call    cs:__imp_TlsSetValue
0x18002f40f  mov     [rbx+58h], rdi
0x18002f413  mov     rax, [rbx+48h]
0x18002f417  add     rax, 38h ; '8'
0x18002f41b  cmp     [rbx+18h], rax
0x18002f41f  jnz     short loc_18002F454
0x18002f421  lea     rdx, [rbx+8]
0x18002f425  cmp     qword ptr [rdx+10h], 0
0x18002f42a  jz      short loc_18002F454
0x18002f42c  mov     rcx, [rdx+8]
0x18002f430  mov     rax, [rdx]
0x18002f433  mov     [rcx], rax
0x18002f436  mov     rcx, [rdx]
0x18002f439  mov     rax, [rdx+8]
0x18002f43d  mov     [rcx+8], rax
0x18002f441  mov     rax, [rdx+10h]
0x18002f445  dec     qword ptr [rax+18h]
  ... truncated ...
```
