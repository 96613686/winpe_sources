# RealtimeProtection::CFilterCommunicatorBase::CommunicatorMainFunction(RealtimeProtection::CCommunicatorThreadObject *)

- ea: `0x18005ab80`
- end: `0x18005bc06`
- name: `?CommunicatorMainFunction@CFilterCommunicatorBase@RealtimeProtection@@AEAAJPEAVCCommunicatorThreadObject@2@@Z`
- size: `4230`
- prototype: `__int64 __fastcall(RealtimeProtection::CFilterCommunicatorBase *__hidden this, struct RealtimeProtection::CCommunicatorThreadObject *)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801cf010`

## callees

- `0x180053080`
- `0x18005ab80`
- `0x18005bc10`
- `0x18005c2a0`
- `0x180068cd0`
- `0x180080030`
- `0x180080800`
- `0x1800809d0`
- `0x180089510`
- `0x18008b100`
- `0x18009351c`
- `0x1800947c0`
- `0x1800951b0`
- `0x1800a2020`
- `0x1800b51d0`
- `0x180101af8`
- `0x1801054f0`
- `0x180105e54`
- `0x180105f50`
- `0x18010cb40`
- `0x18015b214`
- `0x18015bc5c`
- `0x1801d0ffc`
- `0x18023a290`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18005af2e`
- `KERNEL32!GetCurrentThread` at `0x18005b4ce`
- `KERNEL32!GetCurrentThread` at `0x18005ba12`
- `KERNEL32!GetCurrentThread` at `0x18005af2e`
- `KERNEL32!GetCurrentThread` at `0x18005b4ce`
- `KERNEL32!GetCurrentThread` at `0x18005ba12`
- `FLTLIB!FilterReplyMessage` at `0x18005b053`
- `FLTLIB!FilterReplyMessage` at `0x18005b053`
- `FLTLIB!FilterGetMessage` at `0x18005ace8`
- `FLTLIB!FilterGetMessage` at `0x18005ace8`

## string_xrefs

- `0x18005b806`: `GetThreadInformation`
- `0x18005b829`: `SetThreadInformation`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CFilterCommunicatorBase::CommunicatorMainFunction(
        RealtimeProtection::CFilterCommunicatorBase *this,
        struct RealtimeProtection::CCommunicatorThreadObject *a2)
{
  HRESULT NextFilterRequest; // r15d
  unsigned int v5; // r13d
  void *v6; // r12
  int ThreadPriority; // edi
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  void (__fastcall ***v13)(_QWORD); // rcx
  __int64 v14; // rsi
  DWORD v15; // edi
  struct _FILTER_MESSAGE_HEADER *v16; // rax
  unsigned int Message; // eax
  int v18; // edi
  int v19; // ecx
  unsigned int v20; // r8d
  PVOID *v21; // rax
  int v22; // eax
  int v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rcx
  RealtimeProtection::DlpPlugin *v26; // rcx
  __int64 v27; // rsi
  void (__fastcall *v28)(__int64, _QWORD); // rdi
  __int64 v29; // rax
  int v30; // edi
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  const char *v34; // r8
  bool v35; // r9
  unsigned int (__fastcall *v36)(HANDLE, __int64, int *, __int64); // rbx
  HANDLE v37; // rax
  int LoadedKernel32ProcAddress; // eax
  char v39; // bl
  char v40; // al
  int v41; // edx
  int v42; // ecx
  int v43; // ebx
  int v44; // eax
  int v45; // edx
  int v46; // ecx
  DWORD v47; // ebx
  struct _FILTER_REPLY_HEADER *v48; // rax
  int v49; // ebx
  int v50; // eax
  int v51; // ecx
  int v52; // ecx
  int v53; // ebx
  int v54; // eax
  struct RealtimeProtection::CDlpFilterManager *v55; // rax
  unsigned int v56; // ebx
  int ThreadInformationApi; // eax
  int v59; // ebx
  int v60; // eax
  unsigned int LastFailure; // ebx
  char v62; // al
  int v63; // edx
  int v64; // ecx
  char v65; // al
  int v66; // edx
  int v67; // ecx
  RealtimeProtection::DlpPlugin *v68; // rcx
  RealtimeProtection::CDlpFilterManager *FilterManager; // rbx
  PVOID *v70; // rax
  HANDLE CurrentThread; // rax
  int v72; // ebx
  int v73; // eax
  int v74; // edx
  int v75; // ecx
  int v76; // ebx
  int v77; // eax
  int v78; // edx
  int v79; // ecx
  int v80; // ebx
  int v81; // eax
  __int64 v82; // rcx
  int v83; // ebx
  int v84; // eax
  int v85; // edx
  int v86; // r8d
  int v87; // ebx
  int v88; // eax
  __int64 v89; // rax
  int v90; // ebx
  int v91; // eax
  int v92; // ebx
  int v93; // eax
  RealtimeProtection::DlpPlugin *v94; // rcx
  RealtimeProtection::CDlpFilterManager *v95; // rbx
  PVOID *v96; // rax
  char v97; // di
  HANDLE v98; // rax
  int v99; // eax
  int v100; // ebx
  int v101; // eax
  int v102; // ebx
  int v103; // eax
  int v104; // ebx
  int v105; // eax
  int v106; // edx
  __int64 v107; // rcx
  int v108; // ebx
  int v109; // eax
  RealtimeProtection::CDlpFilterManager *v110; // rcx
  char v111; // [rsp+28h] [rbp-60h]
  char v112; // [rsp+28h] [rbp-60h]
  char v113; // [rsp+28h] [rbp-60h]
  __int64 v114; // [rsp+30h] [rbp-58h] BYREF
  void *v115; // [rsp+38h] [rbp-50h]
  unsigned int v116; // [rsp+40h] [rbp-48h] BYREF
  int v117; // [rsp+44h] [rbp-44h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids);
  NextFilterRequest = 0;
  v5 = 0;
  if ( (unsigned int)MpIsWindows8OrGreater() )
  {
    ThreadInformationApi = UtilLoadThreadInformationApi();
    NextFilterRequest = ThreadInformationApi;
    if ( ThreadInformationApi < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
          (unsigned int)ThreadInformationApi);
      NextFilterRequest = 0;
    }
  }
  v115 = (void *)*((_QWORD *)this + 20);
  v6 = (void *)*((_QWORD *)this + 17);
  if ( *((_DWORD *)a2 + 9) == 2 )
  {
    v115 = (void *)*((_QWORD *)this + 21);
    v6 = (void *)*((_QWORD *)this + 18);
  }
  else if ( *((_DWORD *)a2 + 9) == 3 )
  {
    v115 = (void *)*((_QWORD *)this + 22);
    v6 = (void *)*((_QWORD *)this + 19);
  }
  ThreadPriority = UtilGetThreadPriority();
  if ( *((_DWORD *)a2 + 8) == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v59 = *((_DWORD *)a2 + 7);
      v60 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
        v60,
        v59);
    }
    v114 = 0;
    NextFilterRequest = UtilSetThreadPriority(&v114, 7);
    if ( NextFilterRequest >= 0 )
    {
      if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
      {
        v65 = UtilGetThreadPriority();
        McTemplateU0zqqq_EventWriteTransfer(v67, v66, (unsigned int)L"LowPriStartOK", ThreadPriority, 0, v65);
      }
      *((_DWORD *)a2 + 10) = 1;
      if ( (unsigned int)MpIsWindows8OrGreater() )
      {
        FilterManager = RealtimeProtection::DlpPlugin::GetFilterManager(v68);
        if ( FilterManager )
        {
          CurrentThread = GetCurrentThread();
          NextFilterRequest = RealtimeProtection::CDlpFilterManager::RegisterThreadForBoosting(
                                FilterManager,
                                CurrentThread,
                                1u);
          if ( NextFilterRequest >= 0 )
            goto LABEL_11;
          v70 = (PVOID *)WPP_GLOBAL_Control;
        }
        else
        {
          v70 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids);
            v70 = (PVOID *)WPP_GLOBAL_Control;
          }
          LOBYTE(NextFilterRequest) = 14;
        }
        if ( v70 != &WPP_GLOBAL_Control && (*((_BYTE *)v70 + 28) & 1) != 0 )
        {
          v72 = *((_DWORD *)a2 + 7);
          v73 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
            v73,
            v72,
            NextFilterRequest);
        }
        NextFilterRequest = 0;
      }
    }
    else
    {
      LastFailure = HrGetLastFailure();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids, LastFailure);
      if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
      {
        v62 = UtilGetThreadPriority();
        McTemplateU0zqqq_EventWriteTransfer(
          v64,
          v63,
          (unsigned int)L"LowPriStartError",
          ThreadPriority,
          LastFailure,
          v62);
      }
      NextFilterRequest = 0;
    }
  }
  else if ( *((_DWORD *)this + 51) == 1 )
  {
    v114 = 0;
    NextFilterRequest = UtilSetThreadPriority(&v114, 14);
    if ( NextFilterRequest >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v76 = *((_DWORD *)a2 + 7);
        v77 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
          v77,
          v76,
          14);
      }
      if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
      {
        v113 = UtilGetThreadPriority();
        McTemplateU0zqqq_EventWriteTransfer(v79, v78, (unsigned int)L"SyncStartOK", ThreadPriority, 14, v113);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
          (unsigned int)NextFilterRequest);
      if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
      {
        v112 = UtilGetThreadPriority();
        McTemplateU0zqqq_EventWriteTransfer(
          v75,
          v74,
          (unsigned int)L"SyncStartError",
          ThreadPriority,
          NextFilterRequest,
          v112);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v80 = *((_DWORD *)a2 + 7);
      v81 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
        v81,
        v80);
    }
    if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
    {
      v111 = UtilGetThreadPriority();
      McTemplateU0zqqq_EventWriteTransfer(v9, v8, (unsigned int)L"AsyncStartOK", ThreadPriority, 0, v111);
    }
  }
LABEL_11:
  *((_DWORD *)a2 + 11) = UtilGetThreadPriority();
  while ( 2 )
  {
    while ( 2 )
    {
      if ( *((_DWORD *)this + 48) )
        goto LABEL_92;
      v11 = (_QWORD *)((char *)a2 + 48);
      v12 = *((_QWORD *)a2 + 6);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v13 = (void (__fastcall ***)(_QWORD))*((_QWORD *)a2 + 7);
      if ( v13 )
        (**v13)(v13);
      v14 = *v11;
      if ( !*v11 )
      {
        NextFilterRequest = -2147467261;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v43 = *((_DWORD *)a2 + 7);
          v44 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          v45 = 66;
LABEL_172:
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v45,
            (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
            v44,
            v43,
            NextFilterRequest);
        }
        goto LABEL_92;
      }
      while ( 1 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
        v16 = (struct _FILTER_MESSAGE_HEADER *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        Message = FilterGetMessage(v6, v16, v15, (LPOVERLAPPED)(v14 + 16));
        v18 = Message;
        if ( Message == -2147023899 )
          goto LABEL_29;
        if ( *((_DWORD *)this + 48) )
        {
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v89 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids, v89);
LABEL_166:
            v21 = (PVOID *)WPP_GLOBAL_Control;
          }
          LOBYTE(v18) = 4;
          NextFilterRequest = -2147467260;
          goto LABEL_168;
        }
        if ( (unsigned int)RealtimeProtection::IsFilterUnloadError((RealtimeProtection *)Message, v10) )
          break;
        if ( v19 != -2147024882 && v19 != -2147024888 && v19 != -2147023446 && v19 != -2147023443 )
        {
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v22 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
            v23 = 43;
            goto LABEL_147;
          }
          goto LABEL_28;
        }
        if ( !CommonUtil::UtilWaitForSingleObject(*((CommonUtil **)this + 23), (void *)0xFA, v20) )
          goto LABEL_166;
      }
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v22 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
        v23 = 42;
LABEL_147:
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
          v22,
          v18);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_28:
      NextFilterRequest = v18;
      if ( v18 < 0 )
      {
LABEL_168:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
        {
          v90 = *((_DWORD *)a2 + 7);
          v91 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
            v91,
            v90,
            v18);
        }
        goto LABEL_92;
      }
LABEL_29:
      v24 = *v11;
      *v11 = 0;
      if ( v24 )
      {
        v25 = v24 + 8 + *(int *)(*(_QWORD *)(v24 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      }
      v116 = 0;
      if ( *v11 )
      {
        v82 = *v11 + 8LL + *(int *)(*(_QWORD *)(*v11 + 8LL) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
        *v11 = 0;
      }
      NextFilterRequest = RealtimeProtection::CFilterCommunicatorBase::GetNextFilterRequestEx(
                            this,
                            v6,
                            v115,
                            &v116,
                            (struct RealtimeProtection::IFilterRequest **)a2 + 6);
      if ( NextFilterRequest >= 0 )
      {
        v5 = 0;
        if ( *((_DWORD *)this + 51) == 1 && v116 >= 0x10 )
        {
          v27 = *((_QWORD *)a2 + 7);
          v28 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 24LL);
          v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
          v28(v27, *(_QWORD *)(v29 + 8));
        }
        v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v11 + 48LL))(*v11, v116);
        if ( *((_DWORD *)this + 51) == 1 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a2 + 7) + 8LL))(*((_QWORD *)a2 + 7), (unsigned int)v30);
        if ( v30 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            _mm_lfence();
            v83 = *((_DWORD *)a2 + 7);
            v84 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
            WPP_SF_SdL(*((_QWORD *)WPP_GLOBAL_Control + 2), v85, v86, v84, v83, v30);
          }
        }
        else
        {
          v31 = *((_DWORD *)a2 + 9);
          if ( v31 == 1 )
          {
            v32 = *((_DWORD *)this + 30);
            if ( *((_QWORD *)this + 42) < 0xFFFFFFFFFFFFEFFFuLL )
            {
              _InterlockedIncrement64((volatile signed __int64 *)this + 42);
              if ( _InterlockedExchangeAdd64((volatile signed __int64 *)this + 44, 1u) >= (unsigned __int64)(unsigned int)(v32 - 1) )
              {
                _mm_lfence();
                _InterlockedIncrement64((volatile signed __int64 *)this + 43);
              }
            }
          }
          else
          {
            v51 = v31 - 2;
            if ( v51 )
            {
              if ( v51 == 1 )
                RealtimeProtection::FilterCommunicatorStatistics::PreHandleRequest(
                  (RealtimeProtection::CFilterCommunicatorBase *)((char *)this + 384),
                  *((_DWORD *)this + 32));
            }
            else
            {
              v52 = *((_DWORD *)this + 31);
              if ( *((_QWORD *)this + 45) < 0xFFFFFFFFFFFFEFFFuLL )
              {
                _InterlockedIncrement64((volatile signed __int64 *)this + 45);
                if ( _InterlockedExchangeAdd64((volatile signed __int64 *)this + 47, 1u) >= (unsigned __int64)(unsigned int)(v52 - 1) )
                {
                  _mm_lfence();
                  _InterlockedIncrement64((volatile signed __int64 *)this + 46);
                }
              }
            }
          }
          NextFilterRequest = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *, _QWORD, _QWORD))(*(_QWORD *)this + 16LL))(
                                this,
                                *v11,
                                *((_QWORD *)a2 + 7));
          if ( NextFilterRequest < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v87 = *((_DWORD *)a2 + 7);
            v88 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
            WPP_SF_SLd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
              v88,
              v87,
              NextFilterRequest);
          }
          v33 = *((_DWORD *)a2 + 9);
          if ( v33 == 1 )
          {
            if ( *((_QWORD *)this + 42) < 0xFFFFFFFFFFFFEFFFuLL )
              _InterlockedDecrement64((volatile signed __int64 *)this + 44);
          }
          else
          {
            v46 = v33 - 2;
            if ( v46 )
            {
              if ( v46 == 1 )
                RealtimeProtection::FilterCommunicatorStatistics::PostHandleRequest((RealtimeProtection::CFilterCommunicatorBase *)((char *)this + 384));
            }
            else if ( *((_QWORD *)this + 45) < 0xFFFFFFFFFFFFEFFFuLL )
            {
              _InterlockedDecrement64((volatile signed __int64 *)this + 47);
            }
          }
        }
        if ( *((_DWORD *)this + 51) == 1 )
        {
          v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 7) + 40LL))(*((_QWORD *)a2 + 7));
          v48 = (struct _FILTER_REPLY_HEADER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 7) + 32LL))(*((_QWORD *)a2 + 7));
          NextFilterRequest = FilterReplyMessage(v6, v48, v47);
          if ( NextFilterRequest < 0
            && (*(int (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 7) + 16LL))(*((_QWORD *)a2 + 7)) >= 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v49 = *((_DWORD *)a2 + 7);
            v50 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
            WPP_SF_SLd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              74,
              (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
              v50,
              v49,
              NextFilterRequest);
          }
        }
        if ( (unsigned int)MpIsWindows8OrGreater() )
        {
          if ( qword_1803135B0
            || (LOBYTE(v34) = 1,
                LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                              (CommonUtil *)&qword_1803135B0,
                                              (__int64 (**)(void))"GetThreadInformation",
                                              v34,
                                              v35),
                LoadedKernel32ProcAddress >= 0) )
          {
            if ( qword_1803135A8
              || (LOBYTE(v34) = 1,
                  LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                                (CommonUtil *)&qword_1803135A8,
                                                (__int64 (**)(void))"SetThreadInformation",
                                                v34,
                                                v35),
                  LoadedKernel32ProcAddress >= 0) )
            {
              v117 = 0;
              v36 = (unsigned int (__fastcall *)(HANDLE, __int64, int *, __int64))qword_1803135B0;
              v37 = GetCurrentThread();
              if ( v36(v37, 1, &v117, 4) )
                LoadedKernel32ProcAddress = v117;
              else
                LoadedKernel32ProcAddress = 0;
            }
          }
        }
        else
        {
          LoadedKernel32ProcAddress = 0;
        }
        v10 = *((unsigned int *)a2 + 11);
        if ( (_DWORD)v10 != LoadedKernel32ProcAddress )
        {
          v114 = 0;
          v39 = UtilSetThreadPriority(&v114, v10);
          if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
          {
            v40 = UtilGetThreadPriority();
            McTemplateU0zqqq_EventWriteTransfer(v42, v41, (unsigned int)L"PriorityNotRestoredProperly", v114, v39, v40);
          }
          NextFilterRequest = 0;
        }
        continue;
      }
      break;
    }
    switch ( NextFilterRequest )
    {
      case -2147024161:
        goto LABEL_60;
      case -2147467260:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v92 = *((_DWORD *)a2 + 7);
          v93 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
            v93,
            v92);
        }
        break;
      case -2147024890:
      case -2147023901:
LABEL_60:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v43 = *((_DWORD *)a2 + 7);
          v44 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          v45 = 69;
          goto LABEL_172;
        }
        break;
      case -2147024882:
      case -2147024888:
      case -2147023446:
      case -2147023443:
        continue;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v53 = *((_DWORD *)a2 + 7);
          v54 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
            v54,
            v53,
            NextFilterRequest);
        }
        ++v5;
        v55 = RealtimeProtection::DlpPlugin::GetFilterManager(v26);
        if ( v55 )
        {
          v56 = *((_DWORD *)v55 + 26);
        }
        else
        {
          v56 = 1000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids, 1000);
        }
        if ( v5 <= v56 )
          continue;
        break;
    }
    break;
  }
LABEL_92:
  if ( *((_DWORD *)a2 + 10) == 1 && (unsigned int)MpIsWindows8OrGreater() )
  {
    v95 = RealtimeProtection::DlpPlugin::GetFilterManager(v94);
    if ( v95 )
    {
      v98 = GetCurrentThread();
      v99 = RealtimeProtection::CDlpFilterManager::RegisterThreadForBoosting(v95, v98, 0);
      v97 = v99;
      if ( v99 < 0 )
      {
        v96 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_187;
      }
    }
    else
    {
      v96 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids);
        v96 = (PVOID *)WPP_GLOBAL_Control;
      }
      v97 = 14;
LABEL_187:
      if ( v96 != &WPP_GLOBAL_Control && (*((_BYTE *)v96 + 28) & 1) != 0 )
      {
        v100 = *((_DWORD *)a2 + 7);
        v101 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
          v101,
          v100,
          v97);
      }
    }
  }
  if ( *((_DWORD *)this + 48) )
  {
    NextFilterRequest = -2147467260;
LABEL_95:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v102 = *((_DWORD *)a2 + 7);
      v103 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
        v103,
        v102);
    }
    return (unsigned int)NextFilterRequest;
  }
  if ( NextFilterRequest == -2147467260 )
    goto LABEL_95;
  if ( (unsigned int)RealtimeProtection::IsFilterUnloadError((RealtimeProtection *)(unsigned int)NextFilterRequest, v10) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v104 = *((_DWORD *)a2 + 7);
      v105 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
      v106 = 78;
      goto LABEL_201;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v104 = *((_DWORD *)a2 + 7);
    v105 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
    v106 = 79;
LABEL_201:
    WPP_SF_SLd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v106,
      (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
      v105,
      v104,
      NextFilterRequest);
  }
  v107 = 1;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 50, 1, 0) )
    return (unsigned int)NextFilterRequest;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v108 = *((_DWORD *)a2 + 7);
    v109 = (*(__int64 (__fastcall **)(RealtimeProtection::CFilterCommunicatorBase *))(*(_QWORD *)this + 24LL))(this);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_e87f1f92f3293c2947b4334773a72108_Traceguids,
      v109,
      v108);
  }
  if ( RealtimeProtection::DlpPlugin::GetFilterManager((RealtimeProtection::DlpPlugin *)v107) )
  {
    RealtimeProtection::CDlpFilterManager::HandleFilterUnload(v110, NextFilterRequest);
    return (unsigned int)NextFilterRequest;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_e87f1f92f3293c2947b4334773a72108_Traceguids);
  return 2147483662LL;
}

```

## disassembly

```asm
0x18005ab80  mov     [rsp+arg_10], rbx
0x18005ab85  push    rbp
0x18005ab86  push    rsi
0x18005ab87  push    rdi
0x18005ab88  push    r12
0x18005ab8a  push    r13
0x18005ab8c  push    r14
0x18005ab8e  push    r15
0x18005ab90  sub     rsp, 50h
0x18005ab94  mov     rax, cs:__security_cookie
0x18005ab9b  xor     rax, rsp
0x18005ab9e  mov     [rsp+88h+var_40], rax
0x18005aba3  mov     rbp, rdx
0x18005aba6  mov     r14, rcx
0x18005aba9  lea     rbx, WPP_GLOBAL_Control
0x18005abb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005abb7  cmp     rcx, rbx
0x18005abba  jnz     loc_18005B2E5
0x18005abc0  xor     esi, esi
0x18005abc2  mov     r15d, esi
0x18005abc5  mov     r13d, esi
0x18005abc8  call    MpIsWindows8OrGreater
0x18005abcd  test    eax, eax
0x18005abcf  jnz     loc_18005B309
0x18005abd5  mov     rbx, [r14+0A0h]
0x18005abdc  mov     [rsp+88h+var_50], rbx
0x18005abe1  mov     r12, [r14+88h]
0x18005abe8  mov     ecx, [rbp+24h]
0x18005abeb  sub     ecx, 2
0x18005abee  jz      loc_18005B363
0x18005abf4  cmp     ecx, 1
0x18005abf7  jz      loc_18005B34B
0x18005abfd  call    UtilGetThreadPriority
0x18005ac02  mov     edi, eax
0x18005ac04  mov     ebx, 1
0x18005ac09  cmp     [rbp+20h], ebx
0x18005ac0c  jz      loc_18005B37B
0x18005ac12  cmp     [r14+0CCh], ebx
0x18005ac19  jz      loc_18005B549
0x18005ac1f  mov     rax, cs:WPP_GLOBAL_Control
0x18005ac26  lea     rcx, WPP_GLOBAL_Control
0x18005ac2d  cmp     rax, rcx
0x18005ac30  jnz     loc_18005B63C
0x18005ac36  test    cs:Microsoft_Antimalware_RTPEnableBits, 1
0x18005ac3d  jz      short loc_18005AC5B
0x18005ac3f  call    UtilGetThreadPriority
0x18005ac44  mov     dword ptr [rsp+88h+var_60], eax
0x18005ac48  mov     dword ptr [rsp+88h+var_68], esi
0x18005ac4c  lea     r8, aAsyncstartok; "AsyncStartOK"
0x18005ac53  mov     r9d, edi
0x18005ac56  call    McTemplateU0zqqq_EventWriteTransfer
0x18005ac5b  lea     rdi, WPP_GLOBAL_Control
0x18005ac62  call    UtilGetThreadPriority
0x18005ac67  mov     [rbp+2Ch], eax
0x18005ac6a  nop     word ptr [rax+rax+00h]
0x18005ac70  mov     eax, [r14+0C0h]
0x18005ac77  test    eax, eax
0x18005ac79  jnz     loc_18005B287
0x18005ac7f  lea     rbx, [rbp+30h]
0x18005ac83  mov     rcx, [rbx]
0x18005ac86  test    rcx, rcx
0x18005ac89  jz      short loc_18005AC98
0x18005ac8b  mov     rax, [rcx]
0x18005ac8e  mov     rax, [rax+8]
0x18005ac92  call    cs:__guard_dispatch_icall_fptr
0x18005ac98  mov     rcx, [rbp+38h]
0x18005ac9c  test    rcx, rcx
0x18005ac9f  jz      short loc_18005ACAD
0x18005aca1  mov     rax, [rcx]
0x18005aca4  mov     rax, [rax]
0x18005aca7  call    cs:__guard_dispatch_icall_fptr
0x18005acad  mov     rsi, [rbx]
0x18005acb0  test    rsi, rsi
0x18005acb3  jz      loc_18005B99E
0x18005acb9  mov     rax, [rsi]
0x18005acbc  mov     rcx, rsi
0x18005acbf  mov     rax, [rax+18h]
0x18005acc3  call    cs:__guard_dispatch_icall_fptr
0x18005acc9  mov     edi, eax
0x18005accb  mov     rcx, [rsi]
0x18005acce  mov     rax, [rcx+10h]
0x18005acd2  mov     rcx, rsi
0x18005acd5  call    cs:__guard_dispatch_icall_fptr
0x18005acdb  lea     r9, [rsi+10h]; lpOverlapped
0x18005acdf  mov     r8d, edi; dwMessageBufferSize
0x18005ace2  mov     rdx, rax; lpMessageBuffer
0x18005ace5  mov     rcx, r12; hPort
0x18005ace8  call    cs:__imp_FilterGetMessage
0x18005acee  mov     edi, eax
0x18005acf0  cmp     eax, 800703E5h
0x18005acf5  jz      loc_18005AD87
0x18005acfb  mov     ecx, [r14+0C0h]
0x18005ad02  test    ecx, ecx
0x18005ad04  jnz     loc_18005B85A
0x18005ad0a  mov     ecx, eax; this
0x18005ad0c  call    ?IsFilterUnloadError@RealtimeProtection@@YAHJ@Z; RealtimeProtection::IsFilterUnloadError(long)
0x18005ad11  test    eax, eax
0x18005ad13  jnz     loc_18005B6A6
0x18005ad19  cmp     ecx, 8007000Eh
0x18005ad1f  jz      loc_18005B681
0x18005ad25  cmp     ecx, 80070008h
0x18005ad2b  jz      loc_18005B681
0x18005ad31  cmp     ecx, 800705AAh
0x18005ad37  jz      loc_18005B681
0x18005ad3d  cmp     ecx, 800705ADh
0x18005ad43  jz      loc_18005B681
0x18005ad49  mov     rax, cs:WPP_GLOBAL_Control
0x18005ad50  lea     rsi, WPP_GLOBAL_Control
0x18005ad57  cmp     rax, rsi
0x18005ad5a  jz      short loc_18005AD7C
0x18005ad5c  test    byte ptr [rax+1Ch], 1
0x18005ad60  jz      short loc_18005AD7C
0x18005ad62  mov     rax, [r14]
0x18005ad65  mov     rcx, r14
0x18005ad68  mov     rax, [rax+18h]
0x18005ad6c  call    cs:__guard_dispatch_icall_fptr
0x18005ad72  mov     edx, 2Bh ; '+'
0x18005ad77  jmp     loc_18005B6DC
0x18005ad7c  mov     r15d, edi
0x18005ad7f  test    edi, edi
0x18005ad81  js      loc_18005B8B1
0x18005ad87  mov     rdx, [rbx]
0x18005ad8a  xor     esi, esi
0x18005ad8c  mov     [rbx], rsi
0x18005ad8f  test    rdx, rdx
0x18005ad92  jz      short loc_18005ADB0
0x18005ad94  mov     rax, [rdx+8]
0x18005ad98  movsxd  rcx, dword ptr [rax+4]
0x18005ad9c  add     rdx, 8
0x18005ada0  add     rcx, rdx
0x18005ada3  mov     rax, [rcx]
0x18005ada6  mov     rax, [rax+8]
0x18005adaa  call    cs:__guard_dispatch_icall_fptr
0x18005adb0  mov     [rsp+88h+var_48], esi
0x18005adb4  mov     rdx, [rbx]
0x18005adb7  test    rdx, rdx
0x18005adba  jnz     loc_18005B706
0x18005adc0  mov     [rsp+88h+var_68], rbx; struct RealtimeProtection::IFilterRequest **
0x18005adc5  lea     r9, [rsp+88h+var_48]; unsigned int *
0x18005adca  mov     r8, [rsp+88h+var_50]; void *
0x18005adcf  mov     rdx, r12; hPort
0x18005add2  mov     rcx, r14; this
0x18005add5  call    ?GetNextFilterRequestEx@CFilterCommunicatorBase@RealtimeProtection@@AEAAJPEAX0PEAKPEAPEAUIFilterRequest@2@@Z; RealtimeProtection::CFilterCommunicatorBase::GetNextFilterRequestEx(void *,void *,ulong *,RealtimeProtection::IFilterRequest * *)
0x18005adda  mov     r15d, eax
0x18005addd  test    eax, eax
0x18005addf  js      loc_18005AFB5
0x18005ade5  mov     r13d, esi
0x18005ade8  cmp     dword ptr [r14+0CCh], 1
0x18005adf0  jnz     short loc_18005AE29
0x18005adf2  cmp     [rsp+88h+var_48], 10h
0x18005adf7  jb      short loc_18005AE29
0x18005adf9  mov     rsi, [rbp+38h]
0x18005adfd  mov     rax, [rsi]
0x18005ae00  mov     rdi, [rax+18h]
0x18005ae04  mov     rdx, [rbx]
0x18005ae07  mov     rcx, [rdx]
0x18005ae0a  mov     rax, [rcx+10h]
0x18005ae0e  mov     rcx, rdx
0x18005ae11  call    cs:__guard_dispatch_icall_fptr
0x18005ae17  mov     rdx, [rax+8]
0x18005ae1b  mov     rcx, rsi
0x18005ae1e  mov     rax, rdi
0x18005ae21  call    cs:__guard_dispatch_icall_fptr
0x18005ae27  xor     esi, esi
0x18005ae29  mov     rcx, [rbx]
0x18005ae2c  mov     rax, [rcx]
0x18005ae2f  mov     edx, [rsp+88h+var_48]
0x18005ae33  mov     rax, [rax+30h]
0x18005ae37  call    cs:__guard_dispatch_icall_fptr
0x18005ae3d  mov     edi, eax
0x18005ae3f  cmp     dword ptr [r14+0CCh], 1
0x18005ae47  jnz     short loc_18005AE5F
0x18005ae49  mov     r8, [rbp+38h]
0x18005ae4d  mov     rcx, [r8]
0x18005ae50  mov     rax, [rcx+8]
0x18005ae54  mov     edx, edi
0x18005ae56  mov     rcx, r8
0x18005ae59  call    cs:__guard_dispatch_icall_fptr
0x18005ae5f  test    edi, edi
0x18005ae61  js      loc_18005B72A
0x18005ae67  mov     ecx, [rbp+24h]
0x18005ae6a  cmp     ecx, 1
0x18005ae6d  jnz     loc_18005B116
0x18005ae73  mov     ecx, [r14+78h]
0x18005ae77  mov     rax, [r14+150h]
0x18005ae7e  nop
0x18005ae7f  cmp     rax, 0FFFFFFFFFFFFEFFFh
0x18005ae85  jnb     short loc_18005AEA8
0x18005ae87  lock inc qword ptr [r14+150h]
0x18005ae8f  mov     edx, 1
0x18005ae94  lock xadd [r14+160h], rdx
0x18005ae9d  dec     ecx
0x18005ae9f  cmp     rdx, rcx
0x18005aea2  jnb     loc_18005B106
0x18005aea8  mov     rax, [r14]
0x18005aeab  mov     r8, [rbp+38h]
0x18005aeaf  mov     rdx, [rbx]
0x18005aeb2  mov     rcx, r14
0x18005aeb5  mov     rax, [rax+10h]
0x18005aeb9  call    cs:__guard_dispatch_icall_fptr
0x18005aebf  mov     r15d, eax
0x18005aec2  test    eax, eax
0x18005aec4  js      loc_18005B7A2
0x18005aeca  mov     ecx, [rbp+24h]
0x18005aecd  cmp     ecx, 1
0x18005aed0  jnz     loc_18005B000
0x18005aed6  mov     rax, [r14+150h]
0x18005aedd  nop
0x18005aede  cmp     rax, 0FFFFFFFFFFFFEFFFh
0x18005aee4  jnb     short loc_18005AEEE
0x18005aee6  lock dec qword ptr [r14+160h]
0x18005aeee  cmp     dword ptr [r14+0CCh], 1
0x18005aef6  jz      loc_18005B023
0x18005aefc  call    MpIsWindows8OrGreater
0x18005af01  test    eax, eax
0x18005af03  jz      loc_18005B0DE
0x18005af09  cmp     cs:qword_1803135B0, r13
0x18005af10  jz      loc_18005B803
0x18005af16  cmp     cs:qword_1803135A8, r13
0x18005af1d  jz      loc_18005B826
0x18005af23  mov     [rsp+88h+var_44], esi
0x18005af27  mov     rbx, cs:qword_1803135B0
0x18005af2e  call    cs:__imp_GetCurrentThread
0x18005af34  mov     rcx, rax
0x18005af37  mov     r9d, 4
0x18005af3d  lea     r8, [rsp+88h+var_44]
0x18005af42  mov     edx, 1
0x18005af47  mov     rax, rbx
0x18005af4a  call    cs:__guard_dispatch_icall_fptr
0x18005af50  test    eax, eax
0x18005af52  jz      loc_18005B280
0x18005af58  mov     eax, [rsp+88h+var_44]
0x18005af5c  mov     edx, [rbp+2Ch]
0x18005af5f  cmp     edx, eax
0x18005af61  lea     rdi, WPP_GLOBAL_Control
0x18005af68  jz      loc_18005AC70
0x18005af6e  mov     [rsp+88h+var_58], rsi
0x18005af73  lea     rcx, [rsp+88h+var_58]
0x18005af78  call    UtilSetThreadPriority
0x18005af7d  mov     ebx, eax
0x18005af7f  test    cs:Microsoft_Antimalware_RTPEnableBits, 1
0x18005af86  jz      short loc_18005AFA6
0x18005af88  call    UtilGetThreadPriority
0x18005af8d  mov     dword ptr [rsp+88h+var_60], eax
0x18005af91  mov     dword ptr [rsp+88h+var_68], ebx
0x18005af95  mov     r9d, dword ptr [rsp+88h+var_58]
0x18005af9a  lea     r8, aPrioritynotres; "PriorityNotRestoredProperly"
0x18005afa1  call    McTemplateU0zqqq_EventWriteTransfer
0x18005afa6  mov     r15d, esi
0x18005afa9  lea     rdi, WPP_GLOBAL_Control
0x18005afb0  jmp     loc_18005AC70
0x18005afb5  cmp     r15d, 800702DFh
0x18005afbc  jnz     loc_18005B168
0x18005afc2  mov     rax, cs:WPP_GLOBAL_Control
0x18005afc9  lea     rdi, WPP_GLOBAL_Control
0x18005afd0  cmp     rax, rdi
0x18005afd3  jz      loc_18005B287
0x18005afd9  test    byte ptr [rax+1Ch], 2
0x18005afdd  jz      loc_18005B287
0x18005afe3  mov     ebx, [rbp+1Ch]
0x18005afe6  mov     rax, [r14]
0x18005afe9  mov     rcx, r14
0x18005afec  mov     rax, [rax+18h]
0x18005aff0  call    cs:__guard_dispatch_icall_fptr
0x18005aff6  mov     edx, 45h ; 'E'
0x18005affb  jmp     loc_18005B91A
0x18005b000  sub     ecx, 2
0x18005b003  jz      loc_18005B0E5
0x18005b009  cmp     ecx, 1
0x18005b00c  jnz     loc_18005AEEE
0x18005b012  lea     rcx, [r14+180h]; this
0x18005b019  call    ?PostHandleRequest@FilterCommunicatorStatistics@RealtimeProtection@@QEAAXXZ; RealtimeProtection::FilterCommunicatorStatistics::PostHandleRequest(void)
0x18005b01e  jmp     loc_18005AEEE
0x18005b023  mov     rcx, [rbp+38h]
0x18005b027  mov     rax, [rcx]
0x18005b02a  mov     rax, [rax+28h]
0x18005b02e  call    cs:__guard_dispatch_icall_fptr
0x18005b034  mov     ebx, eax
0x18005b036  mov     rdx, [rbp+38h]
0x18005b03a  mov     rcx, [rdx]
0x18005b03d  mov     rax, [rcx+20h]
0x18005b041  mov     rcx, rdx
0x18005b044  call    cs:__guard_dispatch_icall_fptr
0x18005b04a  mov     r8d, ebx; dwReplyBufferSize
0x18005b04d  mov     rdx, rax; lpReplyBuffer
0x18005b050  mov     rcx, r12; hPort
0x18005b053  call    cs:__imp_FilterReplyMessage
0x18005b059  mov     r15d, eax
0x18005b05c  test    eax, eax
0x18005b05e  jns     loc_18005AEFC
0x18005b064  mov     rcx, [rbp+38h]
0x18005b068  mov     rax, [rcx]
0x18005b06b  mov     rax, [rax+10h]
0x18005b06f  call    cs:__guard_dispatch_icall_fptr
0x18005b075  test    eax, eax
0x18005b077  js      loc_18005AEFC
0x18005b07d  mov     rax, cs:WPP_GLOBAL_Control
0x18005b084  lea     rcx, WPP_GLOBAL_Control
0x18005b08b  cmp     rax, rcx
0x18005b08e  jz      loc_18005AEFC
  ... truncated ...
```
