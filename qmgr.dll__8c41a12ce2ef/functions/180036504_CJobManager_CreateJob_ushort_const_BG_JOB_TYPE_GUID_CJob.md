# CJobManager::CreateJob(ushort const *,BG_JOB_TYPE,_GUID,CJob * *)

- ea: `0x180036504`
- end: `0x180036f97`
- name: `?CreateJob@CJobManager@@QEAAJPEBGW4BG_JOB_TYPE@@U_GUID@@PEAPEAVCJob@@@Z`
- size: `2707`
- prototype: `__int64 __fastcall(CJobManager *this, unsigned __int16 *, enum BG_JOB_TYPE, struct _GUID *, struct CJob **)`
- caller_count: `2`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800361b8`
- `0x1800e4fb0`

## callees

- `0x180006640`
- `0x180016d60`
- `0x18001d7f0`
- `0x18001d830`
- `0x18001e1d0`
- `0x180027a10`
- `0x180027d18`
- `0x18002af10`
- `0x18002d040`
- `0x18002e5c0`
- `0x1800302e8`
- `0x180036504`
- `0x18003bf78`
- `0x18003df90`
- `0x18006263c`
- `0x180066e6c`
- `0x18006b4fc`
- `0x18007d8d4`
- `0x180081600`
- `0x1800898ac`
- `0x18008ddc8`
- `0x18008df60`
- `0x18008e2ec`
- `0x180090a10`
- `0x180091fe0`
- `0x180093b14`
- `0x180093dc4`
- `0x1800973a4`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800ab7b0`
- `0x1800b1fe8`
- `0x1800b6114`
- `0x1800b674c`
- `0x1800f64f4`
- `0x1800f9948`
- `0x1800f9954`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800368c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800368c4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800365da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800365da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036b4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036b4f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800366dd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036701`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036722`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800366dd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036701`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036722`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CJobManager::CreateJob(
        CJobManager *this,
        unsigned __int16 *a2,
        enum BG_JOB_TYPE a3,
        struct _GUID *a4,
        struct CJob **a5)
{
  DWORD v7; // ebx
  const char *CallbackName; // rax
  __int64 v9; // r10
  _QWORD *v10; // r12
  _QWORD *i; // rbx
  __int64 v12; // rax
  _QWORD *j; // rbx
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // ebx
  unsigned int v17; // r14d
  unsigned int ActiveJobsForAllUsers; // eax
  unsigned int v19; // edi
  unsigned int v20; // ebx
  unsigned __int64 v21; // rax
  unsigned __int16 *v22; // rdi
  int v23; // eax
  const unsigned __int16 *v24; // r15
  unsigned __int16 *v25; // r14
  unsigned __int16 *v26; // rax
  unsigned __int16 k; // cx
  wchar_t **v28; // rdi
  enum BG_JOB_TYPE v29; // ebx
  CJob *v30; // rax
  CJob *v31; // rax
  struct TaskSchedulerWorkItem *v32; // rdi
  CJob *v33; // rax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rbx
  unsigned __int64 JobInactivityTimeout100NanoSec; // rbx
  unsigned __int16 **v38; // rcx
  __int64 v39; // rcx
  const unsigned __int16 *v40; // rbx
  _DWORD *v41; // rax
  __int64 v42; // rcx
  CTelemetry *v43; // rcx
  __int64 result; // rax
  EVENT_LOG *v45; // rcx
  unsigned int v46; // [rsp+40h] [rbp-368h] BYREF
  __int128 Buf2; // [rsp+48h] [rbp-360h] BYREF
  __int128 v48; // [rsp+58h] [rbp-350h] BYREF
  enum BG_JOB_TYPE v49; // [rsp+68h] [rbp-340h]
  unsigned __int16 *v50; // [rsp+70h] [rbp-338h]
  __int128 v51; // [rsp+78h] [rbp-330h] BYREF
  char *v52; // [rsp+88h] [rbp-320h] BYREF
  struct _GUID *v53; // [rsp+90h] [rbp-318h]
  struct TaskSchedulerWorkItem *v54; // [rsp+98h] [rbp-310h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-308h] BYREF
  unsigned __int16 *v56; // [rsp+A8h] [rbp-300h] BYREF
  struct CJob **v57; // [rsp+B0h] [rbp-2F8h]
  __int128 v58; // [rsp+B8h] [rbp-2F0h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-2E0h]
  _QWORD v60[3]; // [rsp+D0h] [rbp-2D8h] BYREF
  DWORD v61; // [rsp+E8h] [rbp-2C0h]
  const ComError *v62; // [rsp+F0h] [rbp-2B8h] BYREF
  void **pExceptionObject; // [rsp+100h] [rbp-2A8h] BYREF
  __int128 v64; // [rsp+108h] [rbp-2A0h]
  int v65; // [rsp+118h] [rbp-290h]
  int v66; // [rsp+11Ch] [rbp-28Ch]
  int v67; // [rsp+120h] [rbp-288h]
  void **v68; // [rsp+160h] [rbp-248h] BYREF
  __int128 v69; // [rsp+168h] [rbp-240h]
  int v70; // [rsp+178h] [rbp-230h]
  int v71; // [rsp+17Ch] [rbp-22Ch]
  int v72; // [rsp+180h] [rbp-228h]
  void **v73; // [rsp+1C0h] [rbp-1E8h] BYREF
  __int128 v74; // [rsp+1C8h] [rbp-1E0h]
  int v75; // [rsp+1D8h] [rbp-1D0h]
  int v76; // [rsp+1DCh] [rbp-1CCh]
  int v77; // [rsp+1E0h] [rbp-1C8h]
  void **v78; // [rsp+220h] [rbp-188h] BYREF
  __int128 v79; // [rsp+228h] [rbp-180h]
  int v80; // [rsp+238h] [rbp-170h]
  int v81; // [rsp+23Ch] [rbp-16Ch]
  int v82; // [rsp+240h] [rbp-168h]
  void **v83; // [rsp+280h] [rbp-128h] BYREF
  __int128 v84; // [rsp+288h] [rbp-120h]
  int v85; // [rsp+298h] [rbp-110h]
  int v86; // [rsp+29Ch] [rbp-10Ch]
  int v87; // [rsp+2A0h] [rbp-108h]
  void **v88; // [rsp+2E0h] [rbp-C8h] BYREF
  __int128 v89; // [rsp+2E8h] [rbp-C0h]
  int v90; // [rsp+2F8h] [rbp-B0h]
  int v91; // [rsp+2FCh] [rbp-ACh]
  int v92; // [rsp+300h] [rbp-A8h]
  unsigned __int16 *v93[2]; // [rsp+340h] [rbp-68h] BYREF
  __int64 v94; // [rsp+350h] [rbp-58h]
  unsigned __int64 v95; // [rsp+358h] [rbp-50h]

  v53 = a4;
  v49 = a3;
  v50 = a2;
  v57 = a5;
  *a5 = 0;
  v7 = *((_DWORD *)g_GlobalInfo + 52);
  v60[0] = *((_QWORD *)g_GlobalInfo + 24);
  v60[1] = *((_QWORD *)g_GlobalInfo + 25);
  v60[2] = 0x800000000LL;
  v61 = v7;
  if ( (v60[0] & 0x800000000LL) != 0 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CallbackName = CallbackSleepHelper::GetCallbackName(0x800000000uLL);
      WPP_SF_s(*(_QWORD *)(v9 + 16), 10, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, CallbackName);
    }
    Sleep(v7);
    a3 = v49;
  }
  try
  {
    if ( (unsigned int)a3 > BG_JOB_TYPE_UPLOAD_REPLY )
    {
      v64 = 0;
      pExceptionObject = &ComError::`vftable';
      v65 = -2147467263;
      v66 = 0;
      v67 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v10 = (_QWORD *)((char *)this + 688);
    for ( i = (_QWORD *)*((_QWORD *)this + 87); ; i = (_QWORD *)i[1] )
    {
      if ( i == v10 )
        goto LABEL_14;
      v12 = (__int64)i + 52;
      if ( !i )
        v12 = 676;
      Buf2 = *(_OWORD *)v12;
      if ( !memcmp_0(a4, &Buf2, 0x10u) )
        break;
    }
    if ( ((unsigned __int64)(i - 78) & -(__int64)(i != 0)) == 0 )
    {
LABEL_14:
      for ( j = (_QWORD *)*((_QWORD *)this + 92); ; j = (_QWORD *)j[1] )
      {
        if ( j == (_QWORD *)((char *)this + 728) )
          goto LABEL_21;
        v14 = (__int64)j + 52;
        if ( !j )
          v14 = 676;
        Buf2 = *(_OWORD *)v14;
        if ( !memcmp_0(a4, &Buf2, 0x10u) )
          break;
      }
      if ( ((unsigned __int64)(j - 78) & -(__int64)(j != 0)) == 0 )
      {
LABEL_21:
        GetThreadClientSid(&Buf2);
        if ( !EqualSid((PSID)Buf2, *((PSID *)g_GlobalInfo + 11))
          && !EqualSid((PSID)Buf2, *((PSID *)g_GlobalInfo + 17))
          && !EqualSid((PSID)Buf2, *((PSID *)g_GlobalInfo + 19)) )
        {
          v48 = *(_OWORD *)((char *)g_GlobalInfo + 56);
          _InterlockedIncrement(*((volatile signed __int32 **)&v48 + 1));
          if ( (unsigned int)CheckClientGroupMembership((SidHandle *)&v48) )
          {
            if ( *((_BYTE *)this + 1496) )
            {
              std::_Tree<std::_Tmap_traits<SidHandle,unsigned long,CSidSorter,std::allocator<std::pair<SidHandle const,unsigned long>>,0>>::find(
                (char *)this + 768,
                &v48,
                &Buf2);
              if ( (_QWORD)v48 != *((_QWORD *)this + 96) )
              {
                v16 = *(_DWORD *)(v48 + 48);
                if ( v16 )
                {
                  v17 = *((_DWORD *)this + 375);
                  if ( v17 <= v16 )
                  {
                    v45 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        52,
                        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
                        v16,
                        *((_DWORD *)this + 375));
                    }
                    v48 = Buf2;
                    _InterlockedIncrement(*((volatile signed __int32 **)&Buf2 + 1));
                    EVENT_LOG::ReportJobLimitExceededPerUserFailure(v45, v15, &v48, v16, v17);
                    v74 = 0;
                    v73 = &ComError::`vftable';
                    v75 = -2145386423;
                    v76 = 1298;
                    v77 = 1;
                    throw (ComError *)&v73;
                  }
                }
              }
              ActiveJobsForAllUsers = CUserJobsMap::GetActiveJobsForAllUsers((CJobManager *)((char *)this + 768));
              v19 = ActiveJobsForAllUsers;
              v20 = *((_DWORD *)this + 376);
              if ( v20 <= ActiveJobsForAllUsers )
              {
                if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    53,
                    &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
                    ActiveJobsForAllUsers,
                    *((_DWORD *)this + 376));
                }
                EVENT_LOG::ReportObjectLimitExceededFailure(
                  g_EventLogger,
                  &EVT_EXCEEDED_JOBLIMIT_PER_MACHINE,
                  0,
                  v19,
                  v20);
                v79 = 0;
                v78 = &ComError::`vftable';
                v80 = -2145386416;
                v81 = 1315;
                v82 = 1;
                throw (ComError *)&v78;
              }
            }
          }
        }
        v56 = 0;
        v21 = -1;
        v22 = v50;
        do
          ++v21;
        while ( v50[v21] );
        if ( v21 > 0xFF )
        {
          v52 = (char *)operator new(0x200u);
          std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(&v56, &v52);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v52);
          v50 = v56;
          v23 = StringCchCopyW(v56, 0x100u, v22);
          if ( v23 < 0 && v23 != -2147024774 )
          {
            v84 = 0;
            v83 = &ComError::`vftable';
            v85 = v23;
            v86 = 927;
            v87 = 1;
            throw (ComError *)&v83;
          }
        }
        v46 = 0;
        _InterlockedIncrement(&dword_180145058);
        v52 = (char *)&GenericStringHandle<unsigned short>::s_EmptyString;
        *(_QWORD *)&v48 = 0;
        CJobManager::TryGetCallingProcessInformation(&v52, &v46, &v48);
        v24 = (const unsigned __int16 *)(v52 + 12);
        if ( (*((_BYTE *)g_GlobalInfo + 216) & 0x20) != 0 )
        {
          v25 = (unsigned __int16 *)(v52 + 12);
          v26 = (unsigned __int16 *)(v52 + 12);
          for ( k = *v24; k; k = *v26 )
          {
            ++v26;
            if ( k == 92 )
              v25 = v26;
          }
          v28 = off_1801160E0;
          while ( (unsigned int)_o__wcsicmp(v25, *v28) )
          {
            if ( ++v28 == (wchar_t **)&unk_180116108 )
            {
              v89 = 0;
              v88 = &ComError::`vftable';
              v90 = -2145386426;
              v91 = 1270;
              v92 = 1;
              throw (ComError *)&v88;
            }
          }
        }
        v54 = 0;
        v29 = v49;
        if ( v49 )
        {
          v33 = (CJob *)operator new(0x670u);
          v32 = v33;
          *(_QWORD *)&v51 = v33;
          if ( v33 )
          {
            CJob::CJob(v33, v50, v29, v53, v24);
            *(_QWORD *)v32 = &CUploadJob::`vftable'{for `CJobInactivityTimeout'};
            *((_QWORD *)v32 + 12) = &CUploadJob::`vftable'{for `CJobRetryItem'};
            *((_QWORD *)v32 + 24) = &CUploadJob::`vftable'{for `CJobCallbackItem'};
            *((_QWORD *)v32 + 38) = &CUploadJob::`vftable'{for `CJobNoProgressItem'};
            *((_QWORD *)v32 + 50) = &CUploadJob::`vftable'{for `CJobMaxDownloadTimeItem'};
            *((_QWORD *)v32 + 62) = &CUploadJob::`vftable'{for `CJobModificationItem'};
            *((_QWORD *)v32 + 75) = &CUploadJob::`vftable'{for `RefCountedObject'};
            *((_QWORD *)v32 + 77) = &CUploadJob::`vftable'{for `IServerCertificateValidator'};
            UPLOAD_DATA::UPLOAD_DATA((struct TaskSchedulerWorkItem *)((char *)v32 + 1552));
            *((_QWORD *)v32 + 203) = 0;
            _InterlockedIncrement(&dword_180145058);
            *((_QWORD *)v32 + 204) = &GenericStringHandle<unsigned short>::s_EmptyString;
          }
          else
          {
            v32 = 0;
          }
          v54 = v32;
        }
        else
        {
          v30 = (CJob *)operator new(0x608u);
          *(_QWORD *)&v51 = v30;
          if ( v30 )
            v31 = CJob::CJob(v30, v50, BG_JOB_TYPE_DOWNLOAD, v53, v24);
          else
            v31 = 0;
          Microsoft::WRL::ComPtr<CJob>::Attach(&v54, v31);
          v32 = v54;
        }
        v34 = CJobManager::PopulatePackagedAppSpecificState(this, v32);
        if ( v34 < 0
          && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
            (unsigned int)v34);
        }
        *((_QWORD *)v32 + 79) = v10;
        *((_QWORD *)v32 + 78) = *v10;
        *((_QWORD *)v32 + 80) = *((_QWORD *)this + 88);
        *v10 = (char *)v32 + 624;
        *(_QWORD *)(*((_QWORD *)v32 + 78) + 8LL) = (char *)v32 + 624;
        ++*((_QWORD *)this + 89);
        if ( *((_BYTE *)v32 + 936) )
          _InterlockedIncrement((volatile signed __int32 *)this + 180);
        std::_Tree<std::_Tmap_traits<SidHandle,unsigned long,CSidSorter,std::allocator<std::pair<SidHandle const,unsigned long>>,0>>::_Find_lower_bound<SidHandle>(
          (__int64)this + 768,
          &v58,
          (PSID *)&Buf2);
        v36 = v59;
        if ( *(_BYTE *)(v59 + 25)
          || CSidSorter::operator()(v35, (void **)&Buf2, (void **)(v59 + 32))
          || v36 == *((_QWORD *)this + 96) )
        {
          v58 = Buf2;
          _InterlockedIncrement(*((volatile signed __int32 **)&Buf2 + 1));
          LODWORD(v59) = 1;
          std::map<SidHandle,unsigned long,CSidSorter,std::allocator<std::pair<SidHandle const,unsigned long>>>::insert<std::pair<SidHandle,int>,0>(
            (char *)this + 768,
            &v51,
            &v58);
          SidHandle::~SidHandle((SidHandle *)&v58);
        }
        else
        {
          ++*(_DWORD *)(v36 + 48);
        }
        JobInactivityTimeout100NanoSec = PolicyMonitor::GetJobInactivityTimeout100NanoSec((LPCRITICAL_SECTION)((char *)this + 1144));
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(_QWORD *)&v51 = JobInactivityTimeout100NanoSec + *(_QWORD *)&SystemTimeAsFileTime;
        TaskScheduler::InsertWorkItem((CJobManager *)((char *)this + 520), v32, (struct _FILETIME *)&v51);
        *(_OWORD *)v93 = 0;
        v95 = 0;
        std::wstring::_Construct_empty(v93);
        v94 = 0;
        v38 = v93;
        if ( v95 > 7 )
          v38 = (unsigned __int16 **)v93[0];
        *(_WORD *)v38 = 0;
        v39 = *((_QWORD *)v32 + 92);
        if ( v39 )
          AppPackageInfo::GetAppUserModelId(v39, v93);
        v40 = (const unsigned __int16 *)v93;
        if ( v95 > 7 )
          v40 = v93[0];
        v41 = *(_DWORD **)(wil::details::static_lazy<CTelemetry>::get(
                             v39,
                             _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_)
                         + 8);
        if ( v41 && *v41 )
        {
          wil::details::static_lazy<CTelemetry>::get(
            v42,
            _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
          CTelemetry::JobCreated_(v43, v50, v24, v53, v49, v40);
        }
        v51 = Buf2;
        _InterlockedIncrement(*((volatile signed __int32 **)&Buf2 + 1));
        EVENT_LOG::ReportJobCreated(v42, v50, v53, &v51, v46, v24, v48);
        *v57 = v32;
        std::wstring::~wstring(v93);
        GenericStringHandle<unsigned short>::FreeIt(&v52);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v56);
        SidHandle::~SidHandle((SidHandle *)&Buf2);
        CallbackSleepHelper::~CallbackSleepHelper((CallbackSleepHelper *)v60);
        return 0;
      }
    }
    v69 = 0;
    v68 = &ComError::`vftable';
    v70 = -2147024809;
    v71 = 0;
    v72 = 1;
    throw (ComError *)&v68;
  }
  catch ( const ComError *v62 )
  {
    v46 = *((_DWORD *)v62 + 6);
    CallbackSleepHelper::~CallbackSleepHelper((CallbackSleepHelper *)v60);
    return v46;
  }
  return result;
}

```

## disassembly

```asm
0x180036504  push    rbx
0x180036506  push    rdi
0x180036507  push    r12
0x180036509  push    r13
0x18003650b  push    r14
0x18003650d  push    r15
0x18003650f  sub     rsp, 378h
0x180036516  mov     rax, cs:__security_cookie
0x18003651d  xor     rax, rsp
0x180036520  mov     [rsp+3A8h+var_48], rax
0x180036528  mov     r14, r9
0x18003652b  mov     [rsp+3A8h+var_318], r9
0x180036533  mov     [rsp+3A8h+var_340], r8d
0x180036538  mov     [rsp+3A8h+var_338], rdx
0x18003653d  mov     r13, rcx
0x180036540  mov     rax, [rsp+3A8h+arg_20]
0x180036548  mov     [rsp+3A8h+var_2F8], rax
0x180036550  xor     edx, edx
0x180036552  mov     [rax], rdx
0x180036555  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18003655c  mov     ebx, [rax+0D0h]
0x180036562  mov     rcx, [rax+0C0h]
0x180036569  mov     [rsp+3A8h+var_2D8], rcx
0x180036571  mov     rax, [rax+0C8h]
0x180036578  mov     [rsp+3A8h+var_2D0], rax
0x180036580  mov     rax, 800000000h
0x18003658a  mov     [rsp+3A8h+var_2C8], rax
0x180036592  mov     [rsp+3A8h+var_2C0], ebx
0x180036599  test    rax, rcx
0x18003659c  jz      short loc_1800365E9
0x18003659e  lea     r15, WPP_GLOBAL_Control
0x1800365a5  mov     r10, cs:WPP_GLOBAL_Control
0x1800365ac  cmp     r10, r15
0x1800365af  jz      short loc_1800365D8
0x1800365b1  test    byte ptr [r10+1Ch], 1
0x1800365b6  jz      short loc_1800365D8
0x1800365b8  mov     rcx, rax; unsigned __int64
0x1800365bb  call    ?GetCallbackName@CallbackSleepHelper@@KAPEBD_K@Z; CallbackSleepHelper::GetCallbackName(unsigned __int64)
0x1800365c0  mov     r9, rax
0x1800365c3  mov     edx, 0Ah
0x1800365c8  lea     r8, WPP_263cc8d6529f371e5fb175aafd999872_Traceguids
0x1800365cf  mov     rcx, [r10+10h]
0x1800365d3  call    WPP_SF_s
0x1800365d8  mov     ecx, ebx; dwMilliseconds
0x1800365da  call    cs:__imp_Sleep
0x1800365e0  mov     r8d, [rsp+3A8h+var_340]
0x1800365e5  xor     edx, edx
0x1800365e7  jmp     short loc_1800365F0
0x1800365e9  lea     r15, WPP_GLOBAL_Control
0x1800365f0  cmp     r8d, 1
0x1800365f4  jbe     short loc_180036600
0x1800365f6  cmp     r8d, 2
0x1800365fa  jnz     loc_180036D2F
0x180036600  lea     r12, [r13+2B0h]
0x180036607  mov     rbx, [r12+8]
0x18003660c  mov     ecx, 2A4h
0x180036611  cmp     rbx, r12
0x180036614  jz      short loc_180036664
0x180036616  lea     rax, [rbx+34h]
0x18003661a  test    rbx, rbx
0x18003661d  cmovz   rax, rcx
0x180036621  movups  xmm0, xmmword ptr [rax]
0x180036624  movdqu  [rsp+3A8h+Buf2], xmm0
0x18003662a  mov     r8d, 10h; Size
0x180036630  lea     rdx, [rsp+3A8h+Buf2]; Buf2
0x180036635  mov     rcx, r14; Buf1
0x180036638  call    memcmp_0
0x18003663d  xor     edx, edx
0x18003663f  test    eax, eax
0x180036641  jz      short loc_180036649
0x180036643  mov     rbx, [rbx+8]
0x180036647  jmp     short loc_18003660C
0x180036649  lea     rcx, [rbx-270h]
0x180036650  neg     rbx
0x180036653  sbb     rax, rax
0x180036656  and     rax, rcx
0x180036659  jnz     loc_180036D7A
0x18003665f  mov     ecx, 2A4h
0x180036664  lea     rdi, [r13+2D8h]
0x18003666b  mov     rbx, [rdi+8]
0x18003666f  cmp     rbx, rdi
0x180036672  jz      short loc_1800366C2
0x180036674  lea     rax, [rbx+34h]
0x180036678  test    rbx, rbx
0x18003667b  cmovz   rax, rcx
0x18003667f  movups  xmm0, xmmword ptr [rax]
0x180036682  movdqu  [rsp+3A8h+Buf2], xmm0
0x180036688  mov     r8d, 10h; Size
0x18003668e  lea     rdx, [rsp+3A8h+Buf2]; Buf2
0x180036693  mov     rcx, r14; Buf1
0x180036696  call    memcmp_0
0x18003669b  xor     edx, edx
0x18003669d  test    eax, eax
0x18003669f  jz      short loc_1800366AC
0x1800366a1  mov     rbx, [rbx+8]
0x1800366a5  mov     ecx, 2A4h
0x1800366aa  jmp     short loc_18003666F
0x1800366ac  lea     rcx, [rbx-270h]
0x1800366b3  neg     rbx
0x1800366b6  sbb     rax, rax
0x1800366b9  and     rax, rcx
0x1800366bc  jnz     loc_180036D7A
0x1800366c2  lea     rcx, [rsp+3A8h+Buf2]
0x1800366c7  call    ?GetThreadClientSid@@YA?AVSidHandle@@XZ; GetThreadClientSid(void)
0x1800366cc  nop
0x1800366cd  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x1800366d4  mov     rdx, [rdx+58h]; pSid2
0x1800366d8  mov     rcx, qword ptr [rsp+3A8h+Buf2]; pSid1
0x1800366dd  call    cs:__imp_EqualSid
0x1800366e3  xor     r14d, r14d
0x1800366e6  test    eax, eax
0x1800366e8  jnz     loc_1800367B6
0x1800366ee  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x1800366f5  mov     rdx, [rdx+88h]; pSid2
0x1800366fc  mov     rcx, qword ptr [rsp+3A8h+Buf2]; pSid1
0x180036701  call    cs:__imp_EqualSid
0x180036707  test    eax, eax
0x180036709  jnz     loc_1800367B6
0x18003670f  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180036716  mov     rdx, [rdx+98h]; pSid2
0x18003671d  mov     rcx, qword ptr [rsp+3A8h+Buf2]; pSid1
0x180036722  call    cs:__imp_EqualSid
0x180036728  test    eax, eax
0x18003672a  jnz     loc_1800367B6
0x180036730  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180036737  mov     rax, [rcx+38h]
0x18003673b  mov     qword ptr [rsp+3A8h+var_350], rax
0x180036740  mov     rax, [rcx+40h]
0x180036744  mov     qword ptr [rsp+3A8h+var_350+8], rax
0x180036749  lock inc dword ptr [rax]
0x18003674c  lea     rcx, [rsp+3A8h+var_350]
0x180036751  call    ?CheckClientGroupMembership@@YAJVSidHandle@@@Z; CheckClientGroupMembership(SidHandle)
0x180036756  test    eax, eax
0x180036758  jz      short loc_1800367B6
0x18003675a  cmp     [r13+5D8h], r14b
0x180036761  jz      short loc_1800367B6
0x180036763  lea     rdi, [r13+300h]
0x18003676a  lea     r8, [rsp+3A8h+Buf2]
0x18003676f  lea     rdx, [rsp+3A8h+var_350]
0x180036774  mov     rcx, rdi
0x180036777  call    ?find@?$_Tree@V?$_Tmap_traits@VSidHandle@@KVCSidSorter@@V?$allocator@U?$pair@$$CBVSidHandle@@K@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSidHandle@@K@std@@@std@@@std@@@2@AEBVSidHandle@@@Z; std::_Tree<std::_Tmap_traits<SidHandle,ulong,CSidSorter,std::allocator<std::pair<SidHandle const,ulong>>,0>>::find(SidHandle const &)
0x18003677c  mov     rax, qword ptr [rsp+3A8h+var_350]
0x180036781  cmp     rax, [rdi]
0x180036784  jz      short loc_18003679D
0x180036786  mov     ebx, [rax+30h]
0x180036789  test    ebx, ebx
0x18003678b  jz      short loc_18003679D
0x18003678d  mov     r14d, [r13+5DCh]
0x180036794  cmp     r14d, ebx
0x180036797  jbe     loc_180036DC6
0x18003679d  mov     rcx, rdi; this
0x1800367a0  call    ?GetActiveJobsForAllUsers@CUserJobsMap@@QEAAKXZ; CUserJobsMap::GetActiveJobsForAllUsers(void)
0x1800367a5  mov     edi, eax
0x1800367a7  mov     ebx, [r13+5E0h]
0x1800367ae  cmp     ebx, eax
0x1800367b0  jbe     loc_180036E6D
0x1800367b6  lea     rbx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800367bd  xor     r14d, r14d
0x1800367c0  mov     [rsp+3A8h+var_300], r14
0x1800367c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800367cc  mov     rdi, [rsp+3A8h+var_338]
0x1800367d1  inc     rax
0x1800367d4  cmp     [rdi+rax*2], r14w
0x1800367d9  jnz     short loc_1800367D1
0x1800367db  cmp     rax, 0FFh
0x1800367e1  jbe     short loc_180036843
0x1800367e3  mov     ecx, 200h; dwBytes
0x1800367e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800367ed  mov     [rsp+3A8h+var_320], rax
0x1800367f5  lea     rdx, [rsp+3A8h+var_320]
0x1800367fd  lea     rcx, [rsp+3A8h+var_300]
0x180036805  call    ??$?4U?$default_delete@G@std@@$0A@@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort>::operator=<std::default_delete<ushort>,0>(std::unique_ptr<ushort> &&)
0x18003680a  lea     rcx, [rsp+3A8h+var_320]; void *
0x180036812  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180036817  mov     r8, rdi; unsigned __int16 *
0x18003681a  mov     edx, 100h; unsigned __int64
0x18003681f  mov     rdi, [rsp+3A8h+var_300]
0x180036827  mov     [rsp+3A8h+var_338], rdi
0x18003682c  mov     rcx, rdi; unsigned __int16 *
0x18003682f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036834  test    eax, eax
0x180036836  jns     short loc_180036843
0x180036838  cmp     eax, 8007007Ah
0x18003683d  jnz     loc_180036F08
0x180036843  mov     [rsp+3A8h+var_368], r14d
0x180036848  lock inc cs:dword_180145058
0x18003684f  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180036856  mov     [rsp+3A8h+var_320], rax
0x18003685e  mov     qword ptr [rsp+3A8h+var_350], r14
0x180036863  lea     r8, [rsp+3A8h+var_350]
0x180036868  lea     rdx, [rsp+3A8h+var_368]
0x18003686d  lea     rcx, [rsp+3A8h+var_320]
0x180036875  call    ?TryGetCallingProcessInformation@CJobManager@@SAXAEAV?$GenericStringHandle@G@@PEAKAEA_K@Z; CJobManager::TryGetCallingProcessInformation(GenericStringHandle<ushort> &,ulong *,unsigned __int64 &)
0x18003687a  mov     r15, [rsp+3A8h+var_320]
0x180036882  add     r15, 0Ch
0x180036886  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18003688d  test    byte ptr [rax+0D8h], 20h
0x180036894  jz      short loc_1800368E7
0x180036896  mov     r14, r15
0x180036899  mov     rax, r15
0x18003689c  movzx   ecx, word ptr [r15]
0x1800368a0  jmp     short loc_1800368B2
0x1800368a2  add     rax, 2
0x1800368a6  cmp     cx, 5Ch ; '\'
0x1800368aa  jnz     short loc_1800368AF
0x1800368ac  mov     r14, rax
0x1800368af  movzx   ecx, word ptr [rax]
0x1800368b2  test    cx, cx
0x1800368b5  jnz     short loc_1800368A2
0x1800368b7  lea     rdi, off_1801160E0; "te.exe"
0x1800368be  mov     rdx, [rdi]
0x1800368c1  mov     rcx, r14
0x1800368c4  call    cs:__imp__o__wcsicmp
0x1800368ca  test    eax, eax
0x1800368cc  jz      short loc_1800368E4
0x1800368ce  add     rdi, 8
0x1800368d2  lea     rax, unk_180116108
0x1800368d9  cmp     rdi, rax
0x1800368dc  jz      loc_180036F4D
0x1800368e2  jmp     short loc_1800368BE
0x1800368e4  xor     r14d, r14d
0x1800368e7  mov     [rsp+3A8h+var_310], r14
0x1800368ef  mov     ebx, [rsp+3A8h+var_340]
0x1800368f3  test    ebx, ebx
0x1800368f5  jnz     short loc_18003694A
0x1800368f7  mov     ecx, 608h; dwBytes
0x1800368fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036901  mov     qword ptr [rsp+3A8h+var_330], rax
0x180036906  test    rax, rax
0x180036909  jz      short loc_18003692A
0x18003690b  mov     qword ptr [rsp+3A8h+var_388], r15; unsigned __int16 *
0x180036910  mov     r9, [rsp+3A8h+var_318]; struct _GUID *
0x180036918  xor     r8d, r8d; enum BG_JOB_TYPE
0x18003691b  mov     rdx, [rsp+3A8h+var_338]; unsigned __int16 *
0x180036920  mov     rcx, rax; this
0x180036923  call    ??0CJob@@QEAA@PEBGW4BG_JOB_TYPE@@AEBU_GUID@@0@Z; CJob::CJob(ushort const *,BG_JOB_TYPE,_GUID const &,ushort const *)
0x180036928  jmp     short loc_18003692D
0x18003692a  mov     rax, r14
0x18003692d  mov     rdx, rax
0x180036930  lea     rcx, [rsp+3A8h+var_310]
0x180036938  call    ?Attach@?$ComPtr@VCJob@@@WRL@Microsoft@@QEAAXPEAVCJob@@@Z; Microsoft::WRL::ComPtr<CJob>::Attach(CJob *)
0x18003693d  mov     rdi, [rsp+3A8h+var_310]
0x180036945  jmp     loc_180036A22
0x18003694a  mov     ecx, 670h; dwBytes
0x18003694f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036954  mov     rdi, rax
0x180036957  mov     qword ptr [rsp+3A8h+var_330], rax
0x18003695c  test    rax, rax
0x18003695f  jz      loc_180036A17
0x180036965  mov     qword ptr [rsp+3A8h+var_388], r15; unsigned __int16 *
0x18003696a  mov     r9, [rsp+3A8h+var_318]; struct _GUID *
0x180036972  mov     r8d, ebx; enum BG_JOB_TYPE
0x180036975  mov     rdx, [rsp+3A8h+var_338]; unsigned __int16 *
0x18003697a  mov     rcx, rax; this
0x18003697d  call    ??0CJob@@QEAA@PEBGW4BG_JOB_TYPE@@AEBU_GUID@@0@Z; CJob::CJob(ushort const *,BG_JOB_TYPE,_GUID const &,ushort const *)
0x180036982  nop
0x180036983  lea     rax, ??_7CUploadJob@@6BCJobInactivityTimeout@@@; const CUploadJob::`vftable'{for `CJobInactivityTimeout'}
0x18003698a  mov     [rdi], rax
0x18003698d  lea     rax, ??_7CUploadJob@@6BCJobRetryItem@@@; const CUploadJob::`vftable'{for `CJobRetryItem'}
0x180036994  mov     [rdi+60h], rax
0x180036998  lea     rax, ??_7CUploadJob@@6BCJobCallbackItem@@@; const CUploadJob::`vftable'{for `CJobCallbackItem'}
0x18003699f  mov     [rdi+0C0h], rax
0x1800369a6  lea     rax, ??_7CUploadJob@@6BCJobNoProgressItem@@@; const CUploadJob::`vftable'{for `CJobNoProgressItem'}
0x1800369ad  mov     [rdi+130h], rax
0x1800369b4  lea     rax, ??_7CUploadJob@@6BCJobMaxDownloadTimeItem@@@; const CUploadJob::`vftable'{for `CJobMaxDownloadTimeItem'}
0x1800369bb  mov     [rdi+190h], rax
0x1800369c2  lea     rax, ??_7CUploadJob@@6BCJobModificationItem@@@; const CUploadJob::`vftable'{for `CJobModificationItem'}
0x1800369c9  mov     [rdi+1F0h], rax
0x1800369d0  lea     rax, ??_7CUploadJob@@6BRefCountedObject@@@; const CUploadJob::`vftable'{for `RefCountedObject'}
0x1800369d7  mov     [rdi+258h], rax
0x1800369de  lea     rax, ??_7CUploadJob@@6BIServerCertificateValidator@@@; const CUploadJob::`vftable'{for `IServerCertificateValidator'}
0x1800369e5  mov     [rdi+268h], rax
0x1800369ec  lea     rcx, [rdi+610h]; this
0x1800369f3  call    ??0UPLOAD_DATA@@QEAA@XZ; UPLOAD_DATA::UPLOAD_DATA(void)
0x1800369f8  nop
0x1800369f9  mov     [rdi+658h], r14
0x180036a00  lock inc cs:dword_180145058
0x180036a07  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180036a0e  mov     [rdi+660h], rax
0x180036a15  jmp     short loc_180036A1A
0x180036a17  mov     rdi, r14
0x180036a1a  mov     [rsp+3A8h+var_310], rdi
0x180036a22  mov     rdx, rdi; struct CJob *
0x180036a25  mov     rcx, r13; this
0x180036a28  call    ?PopulatePackagedAppSpecificState@CJobManager@@AEAAJPEAVCJob@@@Z; CJobManager::PopulatePackagedAppSpecificState(CJob *)
0x180036a2d  test    eax, eax
0x180036a2f  jns     short loc_180036A62
0x180036a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a38  lea     rdx, WPP_GLOBAL_Control
0x180036a3f  cmp     rcx, rdx
0x180036a42  jz      short loc_180036A62
0x180036a44  test    byte ptr [rcx+1Ch], 2
0x180036a48  jz      short loc_180036A62
0x180036a4a  mov     edx, 36h ; '6'
0x180036a4f  mov     r9d, eax
0x180036a52  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x180036a59  mov     rcx, [rcx+10h]
0x180036a5d  call    WPP_SF_d
0x180036a62  lea     rcx, [rdi+270h]
0x180036a69  mov     [rcx+8], r12
  ... truncated ...
```
