# CManagerThread::WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x180003f00`
- end: `0x180004e28`
- name: `?WaitCallback@CManagerThread@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `3880`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800011b0`
- `0x180003f00`
- `0x180004e30`
- `0x180004e50`
- `0x180004e80`
- `0x180006dd0`
- `0x180007300`
- `0x180007330`
- `0x1800076d0`
- `0x180007f50`
- `0x1800086e0`
- `0x1800093e0`
- `0x180009af0`
- `0x18000bc98`
- `0x18000bcc4`
- `0x18000bd64`
- `0x18000ca14`
- `0x18000cadc`
- `0x18000d840`
- `0x18000d910`
- `0x18000eefc`
- `0x18000f670`
- `0x18000f7c8`
- `0x180010158`
- `0x1800101e0`
- `0x1800103d4`
- `0x180010704`
- `0x180010de8`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800041c3`
- `KERNEL32!SetEvent` at `0x180004b9c`
- `KERNEL32!SetEvent` at `0x1800041c3`
- `KERNEL32!SetEvent` at `0x180004b9c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003fea`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800048e9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003fea`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800048e9`
- `KERNEL32!SetThreadpoolWait` at `0x180004df9`
- `KERNEL32!SetThreadpoolWait` at `0x180004df9`
- `KERNEL32!EnterCriticalSection` at `0x180004032`
- `KERNEL32!EnterCriticalSection` at `0x180004032`
- `KERNEL32!LeaveCriticalSection` at `0x18000437e`
- `KERNEL32!LeaveCriticalSection` at `0x180004bd4`
- `KERNEL32!LeaveCriticalSection` at `0x180004d01`
- `KERNEL32!LeaveCriticalSection` at `0x18000437e`
- `KERNEL32!LeaveCriticalSection` at `0x180004bd4`
- `KERNEL32!LeaveCriticalSection` at `0x180004d01`
- `KERNEL32!ResetEvent` at `0x180003fdc`
- `KERNEL32!ResetEvent` at `0x180003fdc`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x180004375`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x180004375`
- `KERNEL32!SubmitThreadpoolWork` at `0x180004582`
- `KERNEL32!SubmitThreadpoolWork` at `0x180004b81`
- `KERNEL32!SubmitThreadpoolWork` at `0x180004582`
- `KERNEL32!SubmitThreadpoolWork` at `0x180004b81`
- `KERNEL32!CallbackMayRunLong` at `0x180004d4e`
- `KERNEL32!CallbackMayRunLong` at `0x180004d4e`
- `KERNEL32!WaitForSingleObject` at `0x180004d66`
- `KERNEL32!WaitForSingleObject` at `0x180004d66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004e06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004e06`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003f2d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003f2d`

## pseudocode

```c
void __fastcall CManagerThread::WaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  HRESULT v5; // eax
  DWORD dwLowDateTime; // edi
  int v7; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD **v9; // r15
  int v10; // r12d
  int v11; // r13d
  struct _FILETIME v12; // rsi
  _QWORD *v13; // r15
  _QWORD *v14; // rcx
  unsigned int v15; // edx
  const FILETIME **v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  const FILETIME *v20; // rdx
  FILETIME v21; // rax
  __int64 v22; // rcx
  unsigned int *v23; // rdi
  int v24; // eax
  CManagerThread *v25; // rcx
  __int64 v26; // rcx
  bool v27; // zf
  HANDLE *v28; // r9
  _QWORD *v29; // rax
  PVOID v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 i; // rax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  int v38; // r13d
  __int64 *v39; // rbx
  __int64 v40; // r15
  DWORD v41; // r12d
  __int64 v42; // rdi
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 j; // rax
  CConfigDescriptor **v46; // rbx
  CConfigDescriptor *v47; // r9
  _QWORD *v48; // rax
  int v49; // r12d
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rtt
  unsigned int v52; // edx
  int v53; // r8d
  __int64 v54; // r15
  __int64 v55; // rax
  unsigned __int64 v56; // rdi
  __int64 v57; // r9
  __int64 v58; // rbx
  __int64 v59; // rdx
  unsigned __int64 v60; // r8
  struct _FILETIME **v61; // rbx
  struct _FILETIME *v62; // rax
  DWORD dwHighDateTime; // r12d
  unsigned int v64; // edi
  const char *v65; // r9
  __int64 v66; // rcx
  unsigned int v67; // eax
  const FILETIME *v68; // r8
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  CWorkerThread *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  int v74; // edi
  FILETIME *v75; // rcx
  const FILETIME *v76; // rdx
  const FILETIME *v77; // rcx
  const FILETIME *v78; // rdi
  __int64 *v79; // rax
  __int64 v80; // r13
  int v81; // r12d
  const FILETIME *v82; // r15
  __int64 v83; // rcx
  LPCWSTR *v84; // rax
  FILETIME v85; // r15
  const wchar_t *v86; // rdx
  int v87; // r8d
  __int64 v88; // r15
  const FILETIME *v89; // rdi
  DWORD v90; // edi
  const wchar_t *v91; // r9
  __int64 v92; // rdi
  __int64 v93; // rbx
  __int64 v94; // rcx
  __int64 v95; // r9
  __int64 v96; // rdx
  _QWORD *v97; // rax
  unsigned __int64 v98; // rax
  unsigned __int64 v99; // rax
  unsigned __int64 v100; // rtt
  unsigned __int64 v101; // rax
  unsigned __int64 v102; // rax
  unsigned __int64 v103; // rax
  __int64 v104; // rbx
  DWORD v105; // eax
  struct _FILETIME *v106; // r8
  int v107; // [rsp+30h] [rbp-39h]
  int v108; // [rsp+34h] [rbp-35h]
  const FILETIME **v109; // [rsp+38h] [rbp-31h] BYREF
  struct _FILETIME v110; // [rsp+40h] [rbp-29h] BYREF
  const FILETIME **v111; // [rsp+48h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-19h] BYREF
  int v113; // [rsp+58h] [rbp-11h]
  const FILETIME **v114; // [rsp+60h] [rbp-9h] BYREF
  __int64 *v115; // [rsp+68h] [rbp-1h] BYREF
  CConfigDescriptor **v116; // [rsp+70h] [rbp+7h] BYREF
  struct _FILETIME **v117; // [rsp+78h] [rbp+Fh] BYREF
  __int64 *v118; // [rsp+80h] [rbp+17h] BYREF
  __int64 v119[7]; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v121; // [rsp+D8h] [rbp+6Fh] BYREF
  PTP_WAIT pwa; // [rsp+E0h] [rbp+77h]

  pwa = Wait;
  v5 = CoInitializeEx(0, 0);
  dwLowDateTime = 0;
  if ( v5 < 0 )
  {
    v107 = 0;
    if ( v5 == -2147417850 )
      goto LABEL_10;
    v7 = 0;
  }
  else
  {
    v7 = 1;
    v107 = 1;
  }
  if ( v5 != 1 )
  {
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          158,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          (unsigned int)v5);
      goto LABEL_258;
    }
    goto LABEL_13;
  }
LABEL_10:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      157,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      (unsigned int)v5);
LABEL_13:
  v113 = 1;
  v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
  while ( 2 )
  {
    v9 = (_QWORD **)(Context + 16);
LABEL_15:
    LODWORD(v121) = 0;
    v10 = 0;
    v11 = 0;
    ResetEvent(*((HANDLE *)Context + 31));
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v12 = SystemTimeAsFileTime;
    SystemTimeAsFileTime.dwLowDateTime = (*((__int64 (__fastcall **)(_QWORD))Context + 53))(0);
    LOBYTE(dwLowDateTime) = SystemTimeAsFileTime.dwLowDateTime >= 0xA;
    v110.dwLowDateTime = dwLowDateTime;
    if ( *((_DWORD *)Context + 55) != dwLowDateTime )
    {
      *((_DWORD *)Context + 55) = dwLowDateTime;
      v11 = 1;
    }
    v108 = *((_DWORD *)Context + 54);
    EnterCriticalSection(v8);
    v13 = *v9;
    if ( !v13 )
      goto LABEL_70;
    v14 = (_QWORD *)*((_QWORD *)Context + 7);
    if ( v13 == v14 )
      goto LABEL_70;
    while ( (_QWORD *)v13[3] != v14 )
      v13 = (_QWORD *)v13[3];
    if ( !v13 )
    {
LABEL_70:
      if ( *((_DWORD *)Context + 2) || *((_DWORD *)Context + 66) )
        goto LABEL_82;
      if ( !*((_DWORD *)Context + 59) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
        *((_QWORD *)Context + 30) = *(_QWORD *)&v12 + 300000000LL;
        *((_DWORD *)Context + 59) = 1;
        goto LABEL_93;
      }
      if ( *(unsigned __int64 *)&v12 < *((_QWORD *)Context + 30) )
        goto LABEL_93;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, 30);
      SetEventWhenCallbackReturns(Instance, *((HANDLE *)Context + 32));
      LeaveCriticalSection(v8);
      goto LABEL_257;
    }
    do
    {
      SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v114);
      v16 = v114;
      if ( v114 != (const FILETIME **)v13[1] )
      {
        if ( v114 )
          SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v114, v15);
        v16 = (const FILETIME **)v13[1];
        v114 = v16;
        if ( v16 )
          ++*((_DWORD *)v16 + 2);
      }
      v17 = (__int64 *)(*v16)[17];
      if ( v17 )
      {
        v18 = *v17;
        if ( *v17 )
        {
          if ( *(_DWORD *)(v18 + 48) )
          {
            if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))McTemplateU0z_EventWriteTransfer)(
                v18,
                BackupCycleStop,
                **v16);
            (*v16)[18].dwLowDateTime = (unsigned __int8)(*v16)[18].dwLowDateTime;
            v19 = **(_QWORD **)&(*v16)[17];
            if ( *(_DWORD *)(v19 + 76) )
              (*v16)[18].dwLowDateTime = *(_DWORD *)(v19 + 80);
            v20 = *v16;
            v21 = (*v16)[17];
            v22 = **(_QWORD **)&v21;
            if ( *(_DWORD *)(**(_QWORD **)&v21 + 76LL)
              && (*(_QWORD *)(v22 + 84) > *(_QWORD *)&v20[18].dwHighDateTime
               || !*(_DWORD *)(v22 + 88) && !*(_DWORD *)(v22 + 84)) )
            {
              *(const FILETIME *)((char *)v20 + 148) = *(const FILETIME *)(v22 + 84);
            }
            v23 = (unsigned int *)*v16;
            v24 = CConfigDescriptor::ReloadPolicies((HANDLE *)*v16);
            CManagerThread::MapHrToProtectionState(v25, v24, v23 + 36);
            v109 = v16;
            ++*((_DWORD *)v16 + 2);
            CManagerThread::PublishProtectionState(v26, &v109);
            CConfigDescriptor::CachePropertiesInRegistry((CConfigDescriptor *)*v16);
            (*v16)[3].dwLowDateTime = *(_DWORD *)(**(_QWORD **)&(*v16)[17] + 92LL);
            SmartPtr<CWorkerThread>::operator=(&(*v16)[17], 0);
            (*v16)[4] = v12;
            if ( (*v16)[11].dwLowDateTime == 2 && !(*v16)[2].dwHighDateTime )
            {
              v27 = (*((_DWORD *)Context + 27))-- == 1;
              if ( v27 )
                SetEvent(*((HANDLE *)Context + 14));
            }
            (*v16)[11].dwLowDateTime = 0;
            dwLowDateTime = v110.dwLowDateTime;
          }
          else
          {
            if ( v11 )
              CConfigDescriptor::RefreshPoliciesInEngine((CConfigDescriptor *)*v16, dwLowDateTime, v108);
            LODWORD(v121) = v121 + 1;
          }
        }
      }
      v28 = (HANDLE *)*v16;
      v29 = (_QWORD *)(*v16)[17];
      if ( v29 && *v29 || !*((_DWORD *)v28 + 10) || *((_DWORD *)v28 + 11) )
      {
        ++v10;
        v34 = *((_QWORD *)Context + 7);
        v32 = v13[4];
        if ( v32 == v34 )
        {
          for ( i = v13[5]; i != v34; i = *(_QWORD *)(i + 40) )
          {
            if ( v13 != *(_QWORD **)(i + 32) )
              goto LABEL_65;
            v13 = (_QWORD *)i;
          }
          i = 0;
        }
        else
        {
          i = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
                (__int64)(Context + 16),
                v32);
        }
LABEL_65:
        v13 = (_QWORD *)i;
        v33 = (__int64)v16;
LABEL_66:
        SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v33, v32);
        continue;
      }
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *v28);
      if ( (*v16)[18].dwLowDateTime > 8 )
        (*v16)[18].dwLowDateTime = 1;
      v121 = (__int64)v16;
      ++*((_DWORD *)v16 + 2);
      CManagerThread::PublishProtectionState((__int64)v30, (const FILETIME ***)&v121);
      ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RBDelete(
        (__int64 *)Context + 2,
        (__int64)v13,
        v31);
      SmartPtr<CConfigDescriptor>::operator=(&v114, 0);
      v13 = (_QWORD *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
                        (__int64)(Context + 16),
                        *((_QWORD *)Context + 2));
      LODWORD(v121) = 0;
      v10 = 0;
      v33 = (__int64)v114;
      if ( v114 )
        goto LABEL_66;
    }
    while ( v13 );
    if ( !v10 )
    {
      v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
      goto LABEL_70;
    }
LABEL_82:
    if ( *((_DWORD *)Context + 59) )
    {
      if ( v10 || *((_DWORD *)Context + 2) )
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v37 = 162;
LABEL_91:
          WPP_SF_(v36[2], v37, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
        }
      }
      else
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v37 = 163;
          goto LABEL_91;
        }
      }
      *((_DWORD *)Context + 59) = 0;
      *((_QWORD *)Context + 30) = 0;
    }
LABEL_93:
    v38 = 0;
    LODWORD(v109) = 0;
    v39 = (__int64 *)(Context + 16);
    if ( !*((_DWORD *)Context + 58) )
    {
      v40 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
              (__int64)(Context + 16),
              *v39);
      if ( v40 )
      {
        v41 = v110.dwLowDateTime;
        do
        {
          SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v116);
          v42 = v40;
          v43 = *((_QWORD *)Context + 7);
          v44 = *(_QWORD *)(v40 + 32);
          if ( v44 == v43 )
          {
            for ( j = *(_QWORD *)(v40 + 40); j != v43; j = *(_QWORD *)(j + 40) )
            {
              if ( v40 != *(_QWORD *)(j + 32) )
                goto LABEL_103;
              v40 = j;
            }
            j = 0;
          }
          else
          {
            j = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
                  (__int64)(Context + 16),
                  v44);
          }
LABEL_103:
          v40 = j;
          v46 = v116;
          if ( v116 != *(CConfigDescriptor ***)(v42 + 8) )
          {
            if ( v116 )
              SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v116, v44);
            v46 = *(CConfigDescriptor ***)(v42 + 8);
            v116 = v46;
            if ( v46 )
              ++*((_DWORD *)v46 + 2);
          }
          v47 = *v46;
          v48 = (_QWORD *)*((_QWORD *)*v46 + 17);
          if ( (!v48 || !*v48) && *((_DWORD *)v47 + 6) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                164,
                &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                *(_QWORD *)v47);
            *((_DWORD *)*v46 + 6) = 0;
            v110 = (struct _FILETIME)v46;
            ++*((_DWORD *)v46 + 2);
            if ( (int)CManagerThread::CreateWorkerThread((__int64)Context, (struct _FILETIME ***)&v110, 3u) >= 0 )
            {
              CConfigDescriptor::RefreshPoliciesInEngine(*v46, v41, v108);
              SubmitThreadpoolWork(*(PTP_WORK *)(**((_QWORD **)*v46 + 17) + 40LL));
              LODWORD(v121) = v121 + 1;
            }
            if ( *((_DWORD *)*v46 + 10) )
              v38 = 1;
          }
          SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v46, v44);
        }
        while ( v40 );
        LODWORD(v109) = v38;
        v39 = (__int64 *)(Context + 16);
      }
    }
    v49 = v121;
    if ( !*((_DWORD *)Context + 58) && !(_DWORD)v121 )
    {
      if ( (Context[408] & 1) != 0 )
        goto LABEL_126;
      _m_prefetchw(Context + 208);
      v50 = *((_QWORD *)Context + 26);
      do
      {
        v51 = v50;
        v50 = _InterlockedCompareExchange64((volatile signed __int64 *)Context + 26, v50, v50);
      }
      while ( v51 != v50 );
      if ( *(_QWORD *)&v12 >= v50 )
      {
LABEL_126:
        SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v117);
        v54 = *v39;
        if ( *v39 )
        {
          v55 = *((_QWORD *)Context + 7);
          if ( v54 != v55 )
          {
            v56 = -1;
            while ( *(_QWORD *)(v54 + 24) != v55 )
              v54 = *(_QWORD *)(v54 + 24);
            if ( v54 )
            {
              do
              {
                SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v115);
                v54 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
                        (__int64)(Context + 16),
                        v54);
                SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v115, (__int64 *)(v57 + 8));
                v58 = (__int64)v115;
                v59 = *v115;
                if ( !*(_DWORD *)(*v115 + 44) )
                {
                  v60 = *(_QWORD *)(v59 + 32);
                  if ( v60 < v56
                    && (*(_DWORD *)(v59 + 16) && *(_QWORD *)&v12 > v60 + *(_QWORD *)(v59 + 48) || *(_DWORD *)(v59 + 20)) )
                  {
                    v56 = *(_QWORD *)(v59 + 32);
                    SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v117, (__int64 *)&v115);
                  }
                }
                SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v58, v59);
              }
              while ( v54 );
              v38 = (int)v109;
            }
          }
        }
        v61 = v117;
        if ( v117 )
        {
          v62 = *v117;
          if ( *v117 )
          {
            dwHighDateTime = v62[2].dwHighDateTime;
            v64 = (dwHighDateTime != 0) + 1;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v65 = "maintenance";
              if ( !dwHighDateTime )
                v65 = "periodic";
              WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"periodic", v53, (_DWORD)v65, (__int64)*v62);
            }
            if ( v61 )
              ++*((_DWORD *)v61 + 2);
            v66 = (__int64)*v61;
            v67 = (*v61)[18].dwLowDateTime;
            if ( v67 > 8 )
            {
              *(_DWORD *)(v66 + 144) = v67 | 0x100;
              v111 = (const FILETIME **)v61;
              ++*((_DWORD *)v61 + 2);
              CManagerThread::PublishProtectionState(v66, &v111);
            }
            v68 = *v61;
            (*v61)[11].dwLowDateTime = v64;
            if ( dwHighDateTime )
            {
              if ( (unsigned int)(dwHighDateTime != 0) - 1 <= 1 )
              {
                v68[11].dwHighDateTime = 2;
                v68[12].dwLowDateTime = v68[10].dwLowDateTime;
                v68[13] = (const FILETIME)-1LL;
                v68[14] = (const FILETIME)-1LL;
                v68[15] = (const FILETIME)-1LL;
                v68[16] = (const FILETIME)-1LL;
              }
              goto LABEL_165;
            }
            *(_QWORD *)&v68[11].dwHighDateTime = 2;
            v68[13] = (const FILETIME)-1LL;
            v68[14] = (const FILETIME)-1LL;
            v68[15] = (const FILETIME)-1LL;
            v68[16] = (const FILETIME)-1LL;
            if ( LOBYTE(v68[18].dwLowDateTime) == 0xF0 )
            {
              v69 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_165;
              v70 = 25;
LABEL_163:
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_S)(
                v69[2],
                v70,
                &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                *v68);
              goto LABEL_165;
            }
            if ( v68[19].dwLowDateTime || v68[18].dwHighDateTime )
            {
              v68[14] = v68[7];
              v68[15] = v68[8];
              v68[16] = v68[9];
              goto LABEL_165;
            }
            v69 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v70 = 26;
              goto LABEL_163;
            }
LABEL_165:
            v71 = (CWorkerThread *)operator new(0x60u);
            if ( v71 )
              v71 = CWorkerThread::CWorkerThread(v71);
            SmartPtr<CWorkerThread>::operator=(&(*v61)[17], v71);
            if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0zq_EventWriteTransfer)(
                v73,
                v72,
                **v61,
                v64);
            v74 = CWorkerThread::Create(
                    **(LPVOID ***)&(*v61)[17],
                    *(HANDLE *)&(*v61)[1],
                    v64,
                    (*v61)[10].dwHighDateTime,
                    (struct _TP_CALLBACK_ENVIRON_V3 *)(Context + 136),
                    *((void **)Context + 31));
            v75 = *v61;
            (*v61)[10].dwHighDateTime = 0;
            if ( v74 < 0 )
            {
              if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))McTemplateU0z_EventWriteTransfer)(
                  v75,
                  BackupCycleStop,
                  **v61);
              (*v61)[18].dwLowDateTime &= ~0x100u;
              CManagerThread::MapHrToProtectionState((CManagerThread *)v75, v74, (unsigned int *)&(*v61)[18]);
              v111 = (const FILETIME **)v61;
              ++*((_DWORD *)v61 + 2);
              CManagerThread::PublishProtectionState(v83, &v111);
              if ( (unsigned int)(v74 + 2147219967) <= 2 )
              {
                (*v61)[5].dwLowDateTime = 1;
                v84 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                   v119,
                                   *v61);
                CManagerThread::AddRemoveRegisteredConfig((__int64)Context, v84, 0);
              }
              SmartPtr<CWorkerThread>::operator=(&(*v61)[17], 0);
              (*v61)[11].dwLowDateTime = 0;
            }
            else
            {
              v110 = 0;
              GetSystemTimeAsFileTime(&v110);
              v76 = *v61;
              (*v61)[4] = v110;
              v77 = *v61;
              if ( (*v61)[18].dwLowDateTime <= 8 )
              {
                v77[18].dwLowDateTime = 511;
                v111 = (const FILETIME **)v61;
                ++*((_DWORD *)v61 + 2);
                CManagerThread::PublishProtectionState((__int64)v77, &v111);
              }
            }
            SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v61, (unsigned int)v76);
            (*v61)[2].dwHighDateTime = 0;
            if ( v74 < 0 )
            {
              if ( dwHighDateTime )
              {
                v27 = (*((_DWORD *)Context + 27))-- == 1;
                if ( v27 )
                  SetEvent(*((HANDLE *)Context + 14));
              }
              (*v61)[11].dwLowDateTime = 0;
              v49 = v121;
            }
            else
            {
              v78 = *v61;
              v79 = (__int64 *)(*v61)[17];
              if ( v79 )
              {
                v80 = *v79;
                if ( *v79 )
                {
                  if ( SystemTimeAsFileTime.dwLowDateTime < 0xA )
                  {
                    if ( v108 )
                    {
                      v82 = v78 + 16;
                      v81 = 3;
                    }
                    else
                    {
                      v82 = v78 + 15;
                      v81 = 1;
                    }
                  }
                  else
                  {
                    v81 = v108 != 0 ? 2 : 0;
                    if ( v108 )
                      v82 = v78 + 14;
                    else
                      v82 = v78 + 13;
                  }
                  v85 = *v82;
                  if ( v85 == -1 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        45,
                        &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                        *(_QWORD *)(v80 + 24));
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_Si(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      44,
                      (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                      *(_QWORD *)(v80 + 24),
                      (unsigned __int64)(*(_QWORD *)&v85 + 0xFFFFFLL) >> 20);
                  }
                  *(_DWORD *)(v80 + 72) = v81;
                  (*(void (__fastcall **)(_QWORD, FILETIME))(**(_QWORD **)(v80 + 16) + 48LL))(
                    *(_QWORD *)(v80 + 16),
                    v85);
                  v88 = **(_QWORD **)&v78[17];
                  if ( SystemTimeAsFileTime.dwLowDateTime < 0xA )
                    v89 = v78 + 12;
                  else
                    v89 = (const FILETIME *)((char *)v78 + 92);
                  v90 = v89->dwLowDateTime;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    if ( v90 == 2 )
                    {
                      v91 = L"IoPriorityHintNormal";
                    }
                    else
                    {
                      v91 = L"IoPriorityHintLow";
                      v86 = L"IoPriorityHintVeryLow";
                      if ( v90 != 1 )
                        v91 = L"IoPriorityHintVeryLow";
                    }
                    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v86, v87, (_DWORD)v91, *(_QWORD *)(v88 + 24));
                  }
                  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v88 + 16) + 40LL))(*(_QWORD *)(v88 + 16), v90);
                }
                v38 = (int)v109;
              }
              SubmitThreadpoolWork(*(PTP_WORK *)(**(_QWORD **)&(*v61)[17] + 40LL));
              v49 = 1;
            }
            if ( (*v61)[5].dwLowDateTime )
              v38 = 1;
          }
          if ( v61 )
            SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v61, v52);
        }
      }
    }
    if ( v38 )
    {
      v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 64));
      dwLowDateTime = 0;
      continue;
    }
    break;
  }
  v92 = 0x7FFFFFFFFFFFFFFFLL;
  v9 = (_QWORD **)(Context + 16);
  v93 = *((_QWORD *)Context + 2);
  if ( v93 )
  {
    v94 = *((_QWORD *)Context + 7);
    if ( v93 != v94 )
    {
      while ( *(_QWORD *)(v93 + 24) != v94 )
        v93 = *(_QWORD *)(v93 + 24);
      while ( v93 )
      {
        SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v118);
        v93 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
                (__int64)(Context + 16),
                v93);
        SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v118, (__int64 *)(v95 + 8));
        v96 = *v118;
        v97 = *(_QWORD **)(*v118 + 136);
        if ( v97 && *v97 )
        {
          v98 = 20000000;
          if ( *(_DWORD *)(v96 + 88) != 1 )
            v98 = -1;
        }
        else
        {
          v98 = -1;
          if ( *(_DWORD *)(v96 + 16) )
            v98 = *(_QWORD *)(v96 + 32) + *(_QWORD *)(v96 + 48) - *(_QWORD *)&v12;
        }
        if ( v98 < v92 )
          v92 = v98;
        SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v118, v96);
      }
    }
  }
  if ( (Context[408] & 1) == 0 )
  {
    _m_prefetchw(Context + 208);
    v99 = *((_QWORD *)Context + 26);
    do
    {
      v100 = v99;
      v99 = _InterlockedCompareExchange64((volatile signed __int64 *)Context + 26, v99, v99);
    }
    while ( v100 != v99 );
    if ( v99 > *(_QWORD *)&v12 )
    {
      v101 = v99 - *(_QWORD *)&v12;
      if ( v101 < v92 )
        v92 = v101;
    }
  }
  if ( *((_DWORD *)Context + 59) )
  {
    v102 = *((_QWORD *)Context + 30);
    if ( *(_QWORD *)&v12 < v102 )
    {
      v103 = v102 - *(_QWORD *)&v12;
      if ( v103 < v92 )
        v92 = v103;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 64));
  if ( v49 )
  {
    if ( v92 >= 42949672950000LL )
      LODWORD(v104) = -1;
    else
      v104 = v92 / 10000;
    if ( v113 )
    {
      CallbackMayRunLong(Instance);
      dwLowDateTime = 0;
      v113 = 0;
    }
    else
    {
      dwLowDateTime = 0;
    }
    v105 = WaitForSingleObject(*((HANDLE *)Context + 31), v104);
    v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
    if ( v105 )
    {
      v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
      if ( v105 != 258 )
      {
        v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v105);
            v8 = (struct _RTL_CRITICAL_SECTION *)(Context + 64);
          }
        }
      }
    }
    goto LABEL_15;
  }
  v121 = -v92;
  v106 = (struct _FILETIME *)&v121;
  if ( v92 == 0x7FFFFFFFFFFFFFFFLL )
    v106 = 0;
  SetThreadpoolWait(pwa, *((HANDLE *)Context + 31), v106);
LABEL_257:
  v7 = v107;
LABEL_258:
  if ( v7 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180003f00  mov     [rsp-8+arg_18], rbx
0x180003f05  mov     [rsp-8+pwa], r8
0x180003f0a  mov     [rsp-8+pci], rcx
0x180003f0f  push    rbp
0x180003f10  push    rsi
0x180003f11  push    rdi
0x180003f12  push    r12
0x180003f14  push    r13
0x180003f16  push    r14
0x180003f18  push    r15
0x180003f1a  lea     rbp, [rsp-27h]
0x180003f1f  sub     rsp, 90h
0x180003f26  mov     r14, rdx
0x180003f29  xor     edx, edx; dwCoInit
0x180003f2b  xor     ecx, ecx; pvReserved
0x180003f2d  call    cs:__imp_CoInitializeEx
0x180003f33  lea     rdx, WPP_GLOBAL_Control
0x180003f3a  xor     edi, edi
0x180003f3c  mov     esi, 1
0x180003f41  test    eax, eax
0x180003f43  js      short loc_180003F4C
0x180003f45  mov     ebx, esi
0x180003f47  mov     [rbp+57h+var_90], ebx
0x180003f4a  jmp     short loc_180003F58
0x180003f4c  mov     [rbp+57h+var_90], edi
0x180003f4f  cmp     eax, 80010106h
0x180003f54  jz      short loc_180003F97
0x180003f56  mov     ebx, edi
0x180003f58  cmp     eax, esi
0x180003f5a  jz      short loc_180003F97
0x180003f5c  test    eax, eax
0x180003f5e  jns     short loc_180003FC1
0x180003f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f67  cmp     rcx, rdx
0x180003f6a  jz      loc_180004E02
0x180003f70  test    [rcx+1Ch], sil
0x180003f74  jz      loc_180004E02
0x180003f7a  mov     edx, 9Eh
0x180003f7f  mov     r9d, eax
0x180003f82  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003f89  mov     rcx, [rcx+10h]
0x180003f8d  call    WPP_SF_d
0x180003f92  jmp     loc_180004E02
0x180003f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f9e  cmp     rcx, rdx
0x180003fa1  jz      short loc_180003FC1
0x180003fa3  test    byte ptr [rcx+1Ch], 2
0x180003fa7  jz      short loc_180003FC1
0x180003fa9  mov     edx, 9Dh
0x180003fae  mov     r9d, eax
0x180003fb1  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003fb8  mov     rcx, [rcx+10h]
0x180003fbc  call    WPP_SF_d
0x180003fc1  mov     [rbp+57h+var_68], esi
0x180003fc4  lea     rbx, [r14+40h]
0x180003fc8  lea     r15, [r14+10h]
0x180003fcc  mov     dword ptr [rbp+57h+arg_8], edi
0x180003fcf  mov     r12d, edi
0x180003fd2  mov     r13d, edi
0x180003fd5  mov     rcx, [r14+0F8h]; hEvent
0x180003fdc  call    cs:__imp_ResetEvent
0x180003fe2  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180003fe6  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003fea  call    cs:__imp_GetSystemTimeAsFileTime
0x180003ff0  mov     rsi, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180003ff4  xor     ecx, ecx
0x180003ff6  mov     rax, [r14+1A8h]
0x180003ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004002  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180004005  cmp     eax, 0Ah
0x180004008  setnb   dil
0x18000400c  mov     [rbp+57h+var_80.dwLowDateTime], edi
0x18000400f  cmp     [r14+0DCh], edi
0x180004016  jz      short loc_180004025
0x180004018  mov     [r14+0DCh], edi
0x18000401f  mov     r13d, 1
0x180004025  mov     eax, [r14+0D8h]
0x18000402c  mov     [rbp+57h+var_8C], eax
0x18000402f  mov     rcx, rbx; lpCriticalSection
0x180004032  call    cs:__imp_EnterCriticalSection
0x180004038  mov     r15, [r15]
0x18000403b  test    r15, r15
0x18000403e  jz      loc_180004306
0x180004044  mov     rcx, [r14+38h]
0x180004048  cmp     r15, rcx
0x18000404b  jz      loc_180004306
0x180004051  mov     rax, [r15+18h]
0x180004055  cmp     rax, rcx
0x180004058  jz      short loc_18000405F
0x18000405a  mov     r15, rax
0x18000405d  jmp     short loc_180004051
0x18000405f  test    r15, r15
0x180004062  jz      loc_180004306
0x180004068  nop     dword ptr [rax+rax+00000000h]
0x180004070  lea     rcx, [rbp+57h+var_60]
0x180004074  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x180004079  mov     rbx, [rbp+57h+var_60]
0x18000407d  cmp     rbx, [r15+8]
0x180004081  jz      short loc_1800040A0
0x180004083  test    rbx, rbx
0x180004086  jz      short loc_180004090
0x180004088  mov     rcx, rbx
0x18000408b  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x180004090  mov     rbx, [r15+8]
0x180004094  mov     [rbp+57h+var_60], rbx
0x180004098  test    rbx, rbx
0x18000409b  jz      short loc_1800040A0
0x18000409d  inc     dword ptr [rbx+8]
0x1800040a0  mov     r9, [rbx]
0x1800040a3  mov     rax, [r9+88h]
0x1800040aa  test    rax, rax
0x1800040ad  jz      loc_1800041EE
0x1800040b3  mov     rcx, [rax]
0x1800040b6  test    rcx, rcx
0x1800040b9  jz      loc_1800041EE
0x1800040bf  cmp     dword ptr [rcx+30h], 0
0x1800040c3  jz      loc_1800041D8
0x1800040c9  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x1800040d0  jz      short loc_1800040E1
0x1800040d2  mov     r8, [r9]
0x1800040d5  lea     rdx, BackupCycleStop
0x1800040dc  call    McTemplateU0z_EventWriteTransfer
0x1800040e1  mov     rax, [rbx]
0x1800040e4  and     dword ptr [rax+90h], 0FFh
0x1800040ee  mov     rcx, [rbx]
0x1800040f1  mov     rax, [rcx+88h]
0x1800040f8  mov     rax, [rax]
0x1800040fb  cmp     dword ptr [rax+4Ch], 0
0x1800040ff  jz      short loc_18000410A
0x180004101  mov     eax, [rax+50h]
0x180004104  mov     [rcx+90h], eax
0x18000410a  mov     rdx, [rbx]
0x18000410d  mov     rax, [rdx+88h]
0x180004114  mov     rcx, [rax]
0x180004117  cmp     dword ptr [rcx+4Ch], 0
0x18000411b  jz      short loc_18000414D
0x18000411d  mov     r8d, [rcx+58h]
0x180004121  cmp     r8d, [rdx+98h]
0x180004128  ja      short loc_180004142
0x18000412a  jnz     short loc_180004137
0x18000412c  mov     eax, [rdx+94h]
0x180004132  cmp     [rcx+54h], eax
0x180004135  ja      short loc_180004142
0x180004137  test    r8d, r8d
0x18000413a  jnz     short loc_18000414D
0x18000413c  cmp     [rcx+54h], r8d
0x180004140  jnz     short loc_18000414D
0x180004142  mov     rax, [rcx+54h]
0x180004146  mov     [rdx+94h], rax
0x18000414d  mov     rdi, [rbx]
0x180004150  mov     rcx, rdi; this
0x180004153  call    ?ReloadPolicies@CConfigDescriptor@@QEAAJXZ; CConfigDescriptor::ReloadPolicies(void)
0x180004158  lea     r8, [rdi+90h]; unsigned int *
0x18000415f  mov     edx, eax; int
0x180004161  call    ?MapHrToProtectionState@CManagerThread@@AEAAHJPEAK@Z; CManagerThread::MapHrToProtectionState(long,ulong *)
0x180004166  mov     [rbp+57h+var_88], rbx
0x18000416a  inc     dword ptr [rbx+8]
0x18000416d  lea     rdx, [rbp+57h+var_88]
0x180004171  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x180004176  mov     rcx, [rbx]; this
0x180004179  call    ?CachePropertiesInRegistry@CConfigDescriptor@@QEAAXXZ; CConfigDescriptor::CachePropertiesInRegistry(void)
0x18000417e  mov     rdx, [rbx]
0x180004181  mov     rax, [rdx+88h]
0x180004188  mov     rcx, [rax]
0x18000418b  mov     eax, [rcx+5Ch]
0x18000418e  mov     [rdx+18h], eax
0x180004191  mov     rcx, [rbx]
0x180004194  add     rcx, 88h
0x18000419b  xor     edx, edx
0x18000419d  call    ??4?$SmartPtr@VCWorkerThread@@@@QEAAAEAV0@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::operator=(CWorkerThread *)
0x1800041a2  mov     rax, [rbx]
0x1800041a5  mov     [rax+20h], rsi
0x1800041a9  mov     rax, [rbx]
0x1800041ac  cmp     dword ptr [rax+58h], 2
0x1800041b0  jnz     short loc_1800041C9
0x1800041b2  cmp     dword ptr [rax+14h], 0
0x1800041b6  jnz     short loc_1800041C9
0x1800041b8  sub     dword ptr [r14+6Ch], 1
0x1800041bd  jnz     short loc_1800041C9
0x1800041bf  mov     rcx, [r14+70h]; hEvent
0x1800041c3  call    cs:__imp_SetEvent
0x1800041c9  mov     rax, [rbx]
0x1800041cc  mov     dword ptr [rax+58h], 0
0x1800041d3  mov     edi, [rbp+57h+var_80.dwLowDateTime]
0x1800041d6  jmp     short loc_1800041EE
0x1800041d8  test    r13d, r13d
0x1800041db  jz      short loc_1800041EB
0x1800041dd  mov     r8d, [rbp+57h+var_8C]; int
0x1800041e1  mov     edx, edi; int
0x1800041e3  mov     rcx, r9; this
0x1800041e6  call    ?RefreshPoliciesInEngine@CConfigDescriptor@@QEAAXHH@Z; CConfigDescriptor::RefreshPoliciesInEngine(int,int)
0x1800041eb  inc     dword ptr [rbp+57h+arg_8]
0x1800041ee  mov     r9, [rbx]
0x1800041f1  mov     rax, [r9+88h]
0x1800041f8  test    rax, rax
0x1800041fb  jz      short loc_180004207
0x1800041fd  cmp     qword ptr [rax], 0
0x180004201  jnz     loc_1800042B0
0x180004207  cmp     dword ptr [r9+28h], 0
0x18000420c  jz      loc_1800042B0
0x180004212  cmp     dword ptr [r9+2Ch], 0
0x180004217  jnz     loc_1800042B0
0x18000421d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004224  lea     rax, WPP_GLOBAL_Control
0x18000422b  cmp     rcx, rax
0x18000422e  jz      short loc_18000424E
0x180004230  test    byte ptr [rcx+1Ch], 8
0x180004234  jz      short loc_18000424E
0x180004236  mov     edx, 9Fh
0x18000423b  mov     r9, [r9]
0x18000423e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180004245  mov     rcx, [rcx+10h]
0x180004249  call    WPP_SF_S
0x18000424e  mov     rax, [rbx]
0x180004251  cmp     dword ptr [rax+90h], 8
0x180004258  jbe     short loc_180004264
0x18000425a  mov     dword ptr [rax+90h], 1
0x180004264  mov     [rbp+57h+arg_8], rbx
0x180004268  inc     dword ptr [rbx+8]
0x18000426b  lea     rdx, [rbp+57h+arg_8]
0x18000426f  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x180004274  mov     rdx, r15
0x180004277  lea     rcx, [r14+10h]
0x18000427b  call    ?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAA_NPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180004280  xor     edx, edx
0x180004282  lea     rcx, [rbp+57h+var_60]
0x180004286  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::operator=(CConfigDescriptor *)
0x18000428b  mov     rdx, [r14+10h]
0x18000428f  lea     rcx, [r14+10h]
0x180004293  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180004298  mov     r15, rax
0x18000429b  mov     dword ptr [rbp+57h+arg_8], 0
0x1800042a2  xor     r12d, r12d
0x1800042a5  mov     rcx, [rbp+57h+var_60]
0x1800042a9  test    rcx, rcx
0x1800042ac  jnz     short loc_1800042EB
0x1800042ae  jmp     short loc_1800042F0
0x1800042b0  inc     r12d
0x1800042b3  mov     rcx, [r14+38h]
0x1800042b7  mov     rdx, [r15+20h]
0x1800042bb  cmp     rdx, rcx
0x1800042be  jz      short loc_1800042CB
0x1800042c0  lea     rcx, [r14+10h]
0x1800042c4  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x1800042c9  jmp     short loc_1800042E5
0x1800042cb  mov     rax, [r15+28h]
0x1800042cf  cmp     rax, rcx
0x1800042d2  jz      short loc_1800042E3
0x1800042d4  cmp     r15, [rax+20h]
0x1800042d8  jnz     short loc_1800042E5
0x1800042da  mov     r15, rax
0x1800042dd  mov     rax, [rax+28h]
0x1800042e1  jmp     short loc_1800042CF
0x1800042e3  xor     eax, eax
0x1800042e5  mov     r15, rax
0x1800042e8  mov     rcx, rbx
0x1800042eb  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x1800042f0  test    r15, r15
0x1800042f3  jnz     loc_180004070
0x1800042f9  test    r12d, r12d
0x1800042fc  jnz     loc_1800043D2
0x180004302  lea     rbx, [r14+40h]
0x180004306  cmp     dword ptr [r14+8], 0
0x18000430b  jnz     loc_1800043D2
0x180004311  cmp     dword ptr [r14+108h], 0
0x180004319  jnz     loc_1800043D2
0x18000431f  cmp     dword ptr [r14+0ECh], 0
0x180004327  jz      short loc_180004389
0x180004329  cmp     rsi, [r14+0F0h]
0x180004330  jb      loc_18000444B
0x180004336  mov     rcx, cs:WPP_GLOBAL_Control
0x18000433d  lea     rax, WPP_GLOBAL_Control
0x180004344  cmp     rcx, rax
0x180004347  jz      short loc_18000436A
0x180004349  test    byte ptr [rcx+1Ch], 8
0x18000434d  jz      short loc_18000436A
0x18000434f  mov     edx, 0A0h
0x180004354  mov     r9d, 1Eh
0x18000435a  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180004361  mov     rcx, [rcx+10h]
0x180004365  call    WPP_SF_d
0x18000436a  mov     rdx, [r14+100h]; evt
0x180004371  mov     rcx, [rbp+57h+pci]; pci
0x180004375  call    cs:__imp_SetEventWhenCallbackReturns
0x18000437b  mov     rcx, rbx; lpCriticalSection
0x18000437e  call    cs:__imp_LeaveCriticalSection
0x180004384  jmp     loc_180004DFF
0x180004389  mov     rcx, cs:WPP_GLOBAL_Control
0x180004390  lea     rax, WPP_GLOBAL_Control
0x180004397  cmp     rcx, rax
0x18000439a  jz      short loc_1800043B7
0x18000439c  test    byte ptr [rcx+1Ch], 8
0x1800043a0  jz      short loc_1800043B7
0x1800043a2  mov     edx, 0A1h
0x1800043a7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800043ae  mov     rcx, [rcx+10h]
0x1800043b2  call    WPP_SF_
0x1800043b7  lea     rax, [rsi+11E1A300h]
0x1800043be  mov     [r14+0F0h], rax
0x1800043c5  mov     dword ptr [r14+0ECh], 1
  ... truncated ...
```
