# MapsBackgroundTransferService_CreateOrFindJob(MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *,IMapsBackgroundTransferJob * *)

- ea: `0x180004940`
- end: `0x180004feb`
- name: `?MapsBackgroundTransferService_CreateOrFindJob@@YAJW4MAPSBTSVC_JOB_TYPE@@PEBG1PEAPEAVIMapsBackgroundTransferJob@@@Z`
- size: `1707`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, std::_Ref_count_base **)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001e70`
- `0x18000224c`
- `0x1800033d4`
- `0x180003458`
- `0x1800039a4`
- `0x1800039d8`
- `0x180003eac`
- `0x180004094`
- `0x1800041d4`
- `0x18000430c`
- `0x1800043e4`
- `0x180004408`
- `0x180004664`
- `0x180004680`
- `0x1800046ac`
- `0x1800047cc`
- `0x180004910`
- `0x180004940`
- `0x180005b9c`
- `0x18000c834`
- `0x18000eb80`
- `0x18000ecb8`
- `0x18000edcc`
- `0x180012e84`
- `0x180013384`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004ad3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800049f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800049f2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180004d89`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180004d89`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800049a7`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800049a7`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180004d5b`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180004d5b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004e83`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004e83`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004e17`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004ea0`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004eda`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004eff`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004f19`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004f64`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004e17`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004ea0`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004eda`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004eff`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004f19`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180004f64`

## string_xrefs

- `0x1800049a0`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004e0e`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004e97`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004ed1`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004ef6`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004f10`: `MapsBackgroundTransferService_CreateOrFindJob`
- `0x180004f5b`: `MapsBackgroundTransferService_CreateOrFindJob`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferService_CreateOrFindJob(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        std::_Ref_count_base **a4)
{
  int v5; // r8d
  int v6; // ecx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  unsigned int i; // ebx
  int v11; // eax
  struct IUnknown *v12; // rsi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  void *v14; // rdi
  __int64 v15; // rax
  struct IUnknown *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r10
  int v20; // eax
  __int128 v21; // xmm6
  int Instance; // eax
  std::_Ref_count_base *v23; // rbx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  _QWORD *v29; // rax
  int MapsVolatileRegDword; // eax
  TimerQueue *v31; // rax
  void (*v32)(void *); // rdx
  struct IUnknown *v33; // rbx
  void *v34; // r8
  struct IUnknownVtbl *TimerQueue; // rax
  int v36; // eax
  int v37; // r8d
  int v38; // r8d
  signed int LastError; // eax
  int v40; // r8d
  int v41; // r8d
  int v42; // r8d
  std::_Ref_count_base *v43; // rdi
  __int64 v45; // [rsp+38h] [rbp-89h] BYREF
  void *v46; // [rsp+40h] [rbp-81h] BYREF
  struct IUnknown *v47; // [rsp+48h] [rbp-79h] BYREF
  struct IUnknown *v48[3]; // [rsp+50h] [rbp-71h] BYREF
  __int128 v49; // [rsp+68h] [rbp-59h] BYREF
  unsigned int v50; // [rsp+78h] [rbp-49h] BYREF
  __int64 v51; // [rsp+80h] [rbp-41h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-39h] BYREF
  std::_Ref_count_base *v53[2]; // [rsp+90h] [rbp-31h] BYREF
  std::_Ref_count_base **v54; // [rsp+A0h] [rbp-21h]
  __int128 v55; // [rsp+A8h] [rbp-19h] BYREF

  v54 = a4;
  ppv = 0;
  v51 = 0;
  v47 = 0;
  *(_OWORD *)v53 = 0;
  v50 = 0;
  if ( a1 > 1 )
  {
    v5 = 126;
    v6 = -2147024809;
LABEL_3:
    v7 = ZTraceReportOriginationNoThis(v6, "MapsBackgroundTransferService_CreateOrFindJob", v5);
LABEL_4:
    v8 = v7;
    goto LABEL_80;
  }
  if ( !a2 )
  {
    v5 = 127;
    v6 = -2147467261;
    goto LABEL_3;
  }
  CallingStateTracker::CallingStateTracker(&v45, 1);
  v9 = CoCreateInstance(
         &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
         0,
         4u,
         &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
         &ppv);
  if ( v9 < 0 )
  {
    v38 = 132;
    goto LABEL_78;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, 0, &v51);
  if ( v9 < 0 )
  {
    v38 = 135;
    goto LABEL_78;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v51 + 56LL))(v51, &v50);
  if ( v9 < 0 )
  {
    v38 = 137;
    goto LABEL_78;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v50 )
      goto LABEL_21;
    v46 = 0;
    v48[0] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, struct IUnknown **))(*(_QWORD *)v51 + 24LL))(v51, 1, v48);
    if ( v11 < 0 )
    {
      v37 = 148;
      goto LABEL_52;
    }
    v12 = v48[0];
    QueryInterface = v48[0]->lpVtbl[6].QueryInterface;
    v14 = v46;
    if ( v46 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v55);
      CoTaskMemFree(v14);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v55);
    }
    v46 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, void **))QueryInterface)(v12, &v46);
    if ( v11 < 0 )
    {
      v37 = 150;
LABEL_52:
      v8 = ZTraceReportPropagationNoThis(v11, "MapsBackgroundTransferService_CreateOrFindJob", v37);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v48);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      goto LABEL_79;
    }
    v15 = JobName(a1);
    if ( !(unsigned int)_o__wcsicmp(v46, v15) )
      break;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v48);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
  }
  if ( v47 != v48[0] )
    ATL::AtlComPtrAssign(&v47, v48[0]);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v48);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
LABEL_21:
  if ( !v47 )
    goto LABEL_28;
  LODWORD(v46) = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, void **))v47->lpVtbl[4].Release)(v47, &v46);
  if ( v9 < 0 )
  {
    v38 = 164;
    goto LABEL_78;
  }
  if ( (_DWORD)v46 != 4 )
    goto LABEL_27;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *))v47->lpVtbl[2].Release)(v47);
  if ( v9 < 0 )
  {
    v38 = 168;
LABEL_78:
    v8 = ZTraceReportPropagationNoThis(v9, "MapsBackgroundTransferService_CreateOrFindJob", v38);
    goto LABEL_79;
  }
  v16 = v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
  }
LABEL_27:
  if ( v47 )
    goto LABEL_33;
LABEL_28:
  v55 = 0;
  v49 = 0;
  v46 = 0;
  v17 = JobName(a1);
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, struct IUnknown **))(v18 + 24))(
          v19,
          v17,
          0,
          &v55,
          &v47);
  if ( v20 < 0 )
  {
    v42 = 184;
    goto LABEL_71;
  }
  LODWORD(v49) = 1;
  v20 = ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>(&v47, &v46);
  if ( v20 < 0 )
  {
    v42 = 187;
    goto LABEL_71;
  }
  v21 = v49;
  v20 = (*(__int64 (__fastcall **)(void *, __int64, __int128 *))(*(_QWORD *)v46 + 424LL))(v46, 4, &v49);
  if ( v20 < 0 )
  {
    v42 = 199;
    goto LABEL_71;
  }
  v49 = v21;
  v20 = (*(__int64 (__fastcall **)(void *, __int64, __int128 *))(*(_QWORD *)v46 + 424LL))(v46, 3, &v49);
  if ( v20 < 0 )
  {
    v42 = 210;
LABEL_71:
    v8 = ZTraceReportPropagationNoThis(v20, "MapsBackgroundTransferService_CreateOrFindJob", v42);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
LABEL_79:
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v45);
    goto LABEL_80;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
LABEL_33:
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v45);
  Instance = MapsBackgroundTransferJob::CreateInstance((struct IBackgroundCopyJob *)v47, (__int64)v53);
  if ( Instance < 0 )
  {
    v7 = ZTraceReportPropagationNoThis(Instance, "MapsBackgroundTransferService_CreateOrFindJob", 219);
    goto LABEL_4;
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    &v49,
    qword_18001D860);
  v23 = v53[0];
  v24 = MapsBackgroundTransferJob::SetPriority(v53[0], (unsigned int)dword_18001D4F4);
  if ( v24 < 0 )
  {
    v41 = 225;
    goto LABEL_67;
  }
  v24 = MapsBackgroundTransferJob::SetPowerPolicy(v23, (unsigned int)dword_18001D62C);
  if ( v24 < 0 )
  {
    v41 = 226;
    goto LABEL_67;
  }
  v24 = MapsBackgroundTransferJob::SetNetworkCostPolicy(v23, (unsigned int)dword_18001D628);
  if ( v24 < 0 )
  {
    v41 = 227;
LABEL_67:
    v8 = ZTraceReportPropagationNoThis(v24, "MapsBackgroundTransferService_CreateOrFindJob", v41);
    goto LABEL_68;
  }
  v25 = qword_18001D640;
  if ( qword_18001D640 )
  {
    *((_DWORD *)v23 + 184) = dword_18001D648;
    *((_QWORD *)v23 + 93) = v25;
    *((_QWORD *)v23 + 94) = qword_18001D638;
    *((_QWORD *)v23 + 95) = qword_18001D630;
  }
  *(_QWORD *)&v55 = v23;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::emplace<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(
    v25,
    v48,
    &v55,
    v53);
  v29 = (_QWORD *)qword_18001D8A0;
  if ( qword_18001D8A0 )
    goto LABEL_48;
  LODWORD(v46) = 60;
  MapsVolatileRegDword = RegUtils::GetMapsVolatileRegDword(v27, v26, v28, &v46);
  if ( MapsVolatileRegDword < 0 )
    ZTraceReportIgnoreNoThis(MapsVolatileRegDword, "GetPollingTimerFrequency", 52);
  v31 = (TimerQueue *)operator new(0x20u);
  *(_OWORD *)v31 = 0;
  *((_OWORD *)v31 + 1) = 0;
  v33 = (struct IUnknown *)TimerQueue::TimerQueue(v31);
  v48[0] = v33;
  if ( !v33->lpVtbl )
  {
    TimerQueue = (struct IUnknownVtbl *)CreateTimerQueue();
    v33->lpVtbl = TimerQueue;
    if ( TimerQueue )
    {
      if ( v33[1].lpVtbl != v33[2].lpVtbl )
        __int2c();
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v36 = ZTraceReportOrigination(LastError, "TimerQueue::Initialize", 40, v33);
      if ( v36 < 0 )
      {
        v40 = 249;
LABEL_62:
        v8 = ZTraceReportPropagationNoThis(v36, "MapsBackgroundTransferService_CreateOrFindJob", v40);
        std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(v48);
LABEL_68:
        ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(&v49);
        goto LABEL_80;
      }
    }
  }
  v36 = TimerQueue::QueueTimer((TimerQueue *)v33, v32, v34, 1000 * (_DWORD)v46, 1000 * (_DWORD)v46);
  if ( v36 < 0 )
  {
    v40 = 250;
    goto LABEL_62;
  }
  std::unique_ptr<TimerQueue>::operator=<std::default_delete<TimerQueue>,0>(&qword_18001D8A0, v48);
  std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(v48);
  v29 = (_QWORD *)qword_18001D8A0;
LABEL_48:
  v8 = 0;
  if ( !*v29 )
    __int2c();
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(&v49);
  *v54 = v53[0];
LABEL_80:
  v43 = v53[1];
  if ( v53[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v53[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v43)(v43);
    std::_Ref_count_base::_Decwref(v43);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180004940  mov     rax, rsp
0x180004943  push    rbp
0x180004944  push    rbx
0x180004945  push    rsi
0x180004946  push    rdi
0x180004947  push    r12
0x180004949  push    r13
0x18000494b  push    r14
0x18000494d  push    r15
0x18000494f  lea     rbp, [rax-5Fh]
0x180004953  sub     rsp, 0D8h
0x18000495a  movaps  xmmword ptr [rax-58h], xmm6
0x18000495e  mov     rax, cs:__security_cookie
0x180004965  xor     rax, rsp
0x180004968  mov     [rbp+57h+var_60], rax
0x18000496c  mov     [rbp+57h+var_78], r9
0x180004970  mov     r13, r8
0x180004973  mov     r12, rdx
0x180004976  mov     r15d, ecx
0x180004979  xor     edi, edi
0x18000497b  mov     [rbp+57h+ppv], rdi
0x18000497f  mov     [rbp+57h+var_98], rdi
0x180004983  mov     [rbp+57h+var_D0], rdi
0x180004987  xorps   xmm0, xmm0
0x18000498a  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18000498f  mov     [rbp+57h+var_A0], edi
0x180004992  cmp     ecx, 1
0x180004995  jbe     short loc_1800049B4
0x180004997  lea     r8d, [rdi+7Eh]
0x18000499b  mov     ecx, 80070057h
0x1800049a0  lea     rdx, aMapsbackground_24; "MapsBackgroundTransferService_CreateOrF"...
0x1800049a7  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800049ad  mov     ebx, eax
0x1800049af  jmp     loc_180004F77
0x1800049b4  test    r12, r12
0x1800049b7  jnz     short loc_1800049C5
0x1800049b9  lea     r8d, [r12+7Fh]
0x1800049be  mov     ecx, 80004003h
0x1800049c3  jmp     short loc_1800049A0
0x1800049c5  mov     edx, 1
0x1800049ca  lea     rcx, [rsp+110h+var_E0]
0x1800049cf  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x1800049d4  nop
0x1800049d5  lea     rax, [rbp+57h+ppv]
0x1800049d9  mov     [rsp+20h], rax; ppv
0x1800049de  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x1800049e5  xor     edx, edx; pUnkOuter
0x1800049e7  lea     r8d, [rdx+4]; dwClsContext
0x1800049eb  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x1800049f2  call    cs:__imp_CoCreateInstance
0x1800049f8  test    eax, eax
0x1800049fa  js      loc_180004F55
0x180004a00  mov     rcx, [rbp+57h+ppv]
0x180004a04  mov     rax, [rcx]
0x180004a07  lea     r8, [rbp+57h+var_98]
0x180004a0b  xor     edx, edx
0x180004a0d  mov     rax, [rax+28h]
0x180004a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a16  test    eax, eax
0x180004a18  js      loc_180004F4D
0x180004a1e  mov     rcx, [rbp+57h+var_98]
0x180004a22  mov     rax, [rcx]
0x180004a25  lea     rdx, [rbp+57h+var_A0]
0x180004a29  mov     rax, [rax+38h]
0x180004a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a32  test    eax, eax
0x180004a34  js      loc_180004F45
0x180004a3a  mov     ebx, edi
0x180004a3c  cmp     ebx, [rbp+57h+var_A0]
0x180004a3f  jnb     loc_180004B20
0x180004a45  mov     [rsp+110h+var_D8], rdi
0x180004a4a  mov     [rbp+57h+var_C8], rdi
0x180004a4e  mov     rcx, [rbp+57h+var_98]
0x180004a52  mov     rax, [rcx]
0x180004a55  xor     r9d, r9d
0x180004a58  lea     r8, [rbp+57h+var_C8]
0x180004a5c  lea     edx, [r9+1]
0x180004a60  mov     rax, [rax+18h]
0x180004a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a69  test    eax, eax
0x180004a6b  js      loc_180004E38
0x180004a71  mov     rsi, [rbp+57h+var_C8]
0x180004a75  mov     rax, [rsi]
0x180004a78  mov     r14, [rax+90h]
0x180004a7f  mov     rdi, [rsp+110h+var_D8]
0x180004a84  test    rdi, rdi
0x180004a87  jz      short loc_180004AA4
0x180004a89  lea     rcx, [rbp+57h+var_70]; this
0x180004a8d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004a92  mov     rcx, rdi; pv
0x180004a95  call    cs:__imp_CoTaskMemFree
0x180004a9b  lea     rcx, [rbp+57h+var_70]; this
0x180004a9f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004aa4  xor     edi, edi
0x180004aa6  mov     [rsp+110h+var_D8], rdi
0x180004aab  lea     rdx, [rsp+110h+var_D8]
0x180004ab0  mov     rcx, rsi
0x180004ab3  mov     rax, r14
0x180004ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abb  test    eax, eax
0x180004abd  js      loc_180004E08
0x180004ac3  mov     ecx, r15d
0x180004ac6  call    JobName
0x180004acb  mov     rdx, rax
0x180004ace  mov     rcx, [rsp+110h+var_D8]
0x180004ad3  call    cs:__imp__o__wcsicmp
0x180004ad9  test    eax, eax
0x180004adb  jz      short loc_180004AF8
0x180004add  lea     rcx, [rbp+57h+var_C8]
0x180004ae1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004ae6  nop
0x180004ae7  lea     rcx, [rsp+110h+var_D8]
0x180004aec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004af1  inc     ebx
0x180004af3  jmp     loc_180004A3C
0x180004af8  mov     rdx, [rbp+57h+var_C8]; struct IUnknown *
0x180004afc  cmp     [rbp+57h+var_D0], rdx
0x180004b00  jz      short loc_180004B0C
0x180004b02  lea     rcx, [rbp+57h+var_D0]; struct IUnknown **
0x180004b06  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004b0b  nop
0x180004b0c  lea     rcx, [rbp+57h+var_C8]
0x180004b10  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b15  nop
0x180004b16  lea     rcx, [rsp+110h+var_D8]
0x180004b1b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004b20  mov     rcx, [rbp+57h+var_D0]
0x180004b24  test    rcx, rcx
0x180004b27  jz      short loc_180004B89
0x180004b29  mov     dword ptr [rsp+110h+var_D8], edi
0x180004b2d  mov     rax, [rcx]
0x180004b30  lea     rdx, [rsp+110h+var_D8]
0x180004b35  mov     rax, [rax+70h]
0x180004b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3e  test    eax, eax
0x180004b40  js      loc_180004E4B
0x180004b46  cmp     dword ptr [rsp+110h+var_D8], 4
0x180004b4b  jnz     short loc_180004B7F
0x180004b4d  mov     rcx, [rbp+57h+var_D0]
0x180004b51  mov     rax, [rcx]
0x180004b54  mov     rax, [rax+40h]
0x180004b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5d  test    eax, eax
0x180004b5f  js      loc_180004E40
0x180004b65  mov     rcx, [rbp+57h+var_D0]
0x180004b69  test    rcx, rcx
0x180004b6c  jz      short loc_180004B7F
0x180004b6e  mov     [rbp+57h+var_D0], rdi
0x180004b72  mov     rax, [rcx]
0x180004b75  mov     rax, [rax+10h]
0x180004b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7e  nop
0x180004b7f  cmp     [rbp+57h+var_D0], rdi
0x180004b83  jnz     loc_180004C52
0x180004b89  xorps   xmm0, xmm0
0x180004b8c  movups  [rbp+57h+var_70], xmm0
0x180004b90  xorps   xmm1, xmm1
0x180004b93  movups  [rbp+57h+var_B0], xmm1
0x180004b97  mov     [rsp+110h+var_D8], rdi
0x180004b9c  mov     r10, [rbp+57h+ppv]
0x180004ba0  mov     r8, [r10]
0x180004ba3  mov     ecx, r15d
0x180004ba6  call    JobName
0x180004bab  mov     rdx, rax
0x180004bae  mov     rax, [r8+18h]
0x180004bb2  lea     rcx, [rbp+57h+var_D0]
0x180004bb6  mov     [rsp+20h], rcx
0x180004bbb  lea     r9, [rbp+57h+var_70]
0x180004bbf  xor     r8d, r8d
0x180004bc2  mov     rcx, r10
0x180004bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bca  test    eax, eax
0x180004bcc  js      loc_180004F3D
0x180004bd2  mov     dword ptr [rbp+57h+var_B0], 1
0x180004bd9  lea     rdx, [rsp+110h+var_D8]
0x180004bde  lea     rcx, [rbp+57h+var_D0]
0x180004be2  call    ??$QueryInterface@UIBackgroundCopyJob5@@@?$CComPtrBase@UIBackgroundCopyJob@@@ATL@@QEBAJPEAPEAUIBackgroundCopyJob5@@@Z; ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>(IBackgroundCopyJob5 * *)
0x180004be7  test    eax, eax
0x180004be9  js      loc_180004F35
0x180004bef  mov     rcx, [rsp+110h+var_D8]
0x180004bf4  movaps  xmm6, [rbp+57h+var_B0]
0x180004bf8  movdqa  [rbp+57h+var_B0], xmm6
0x180004bfd  mov     rax, [rcx]
0x180004c00  lea     r8, [rbp+57h+var_B0]
0x180004c04  mov     edx, 4
0x180004c09  mov     rax, [rax+1A8h]
0x180004c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c15  test    eax, eax
0x180004c17  js      loc_180004F2D
0x180004c1d  mov     rcx, [rsp+110h+var_D8]
0x180004c22  movdqa  [rbp+57h+var_B0], xmm6
0x180004c27  mov     rax, [rcx]
0x180004c2a  lea     r8, [rbp+57h+var_B0]
0x180004c2e  mov     edx, 3
0x180004c33  mov     rax, [rax+1A8h]
0x180004c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3f  test    eax, eax
0x180004c41  js      loc_180004F0A
0x180004c47  lea     rcx, [rsp+110h+var_D8]
0x180004c4c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004c51  nop
0x180004c52  lea     rcx, [rsp+110h+var_E0]; this
0x180004c57  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180004c5c  lea     rax, [rbp+57h+var_88]
0x180004c60  mov     [rsp+20h], rax; __int64
0x180004c65  mov     r9, r13
0x180004c68  mov     r8, r12
0x180004c6b  mov     edx, r15d
0x180004c6e  mov     rcx, [rbp+57h+var_D0]; struct IBackgroundCopyJob *
0x180004c72  call    ?CreateInstance@MapsBackgroundTransferJob@@SAJPEAUIBackgroundCopyJob@@W4MAPSBTSVC_JOB_TYPE@@PEBG2PEAV?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@Z; MapsBackgroundTransferJob::CreateInstance(IBackgroundCopyJob *,MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *,std::shared_ptr<MapsBackgroundTransferJob> *)
0x180004c77  test    eax, eax
0x180004c79  js      loc_180004EF0
0x180004c7f  lea     rdx, qword_18001D860
0x180004c86  lea     rcx, [rbp+57h+var_B0]
0x180004c8a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180004c8f  nop
0x180004c90  mov     edx, cs:dword_18001D4F4
0x180004c96  mov     rbx, [rbp+57h+var_88]
0x180004c9a  mov     rcx, rbx
0x180004c9d  call    ?SetPriority@MapsBackgroundTransferJob@@QEAAJW4MAPSBTSVC_JOB_PRIORITY@@@Z; MapsBackgroundTransferJob::SetPriority(MAPSBTSVC_JOB_PRIORITY)
0x180004ca2  test    eax, eax
0x180004ca4  js      loc_180004ECB
0x180004caa  mov     edx, cs:dword_18001D62C
0x180004cb0  mov     rcx, rbx
0x180004cb3  call    ?SetPowerPolicy@MapsBackgroundTransferJob@@QEAAJW4MAPSBTSVC_POWER_POLICY_FLAG@@@Z; MapsBackgroundTransferJob::SetPowerPolicy(MAPSBTSVC_POWER_POLICY_FLAG)
0x180004cb8  test    eax, eax
0x180004cba  js      loc_180004EC3
0x180004cc0  mov     edx, cs:dword_18001D628
0x180004cc6  mov     rcx, rbx
0x180004cc9  call    ?SetNetworkCostPolicy@MapsBackgroundTransferJob@@QEAAJW4MAPSBTSVC_NETWORK_COST_POLICY@@@Z; MapsBackgroundTransferJob::SetNetworkCostPolicy(MAPSBTSVC_NETWORK_COST_POLICY)
0x180004cce  test    eax, eax
0x180004cd0  js      loc_180004EBB
0x180004cd6  mov     rcx, cs:qword_18001D640
0x180004cdd  test    rcx, rcx
0x180004ce0  jz      short loc_180004D11
0x180004ce2  mov     eax, cs:dword_18001D648
0x180004ce8  mov     [rbx+2E0h], eax
0x180004cee  mov     [rbx+2E8h], rcx
0x180004cf5  mov     rax, cs:qword_18001D638
0x180004cfc  mov     [rbx+2F0h], rax
0x180004d03  mov     rax, cs:qword_18001D630
0x180004d0a  mov     [rbx+2F8h], rax
0x180004d11  mov     qword ptr [rbp+57h+var_70], rbx
0x180004d15  lea     r9, [rbp+57h+var_88]
0x180004d19  lea     r8, [rbp+57h+var_70]
0x180004d1d  lea     rdx, [rbp+57h+var_C8]
0x180004d21  call    ??$emplace@PEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@1@@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::emplace<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(MapsBackgroundTransferJob * &&,std::shared_ptr<MapsBackgroundTransferJob> &)
0x180004d26  mov     rax, cs:qword_18001D8A0
0x180004d2d  test    rax, rax
0x180004d30  jnz     loc_180004DE6
0x180004d36  mov     dword ptr [rsp+110h+var_D8], 3Ch ; '<'
0x180004d3e  lea     r9, [rsp+110h+var_D8]
0x180004d43  call    ?GetMapsVolatileRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsVolatileRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x180004d48  test    eax, eax
0x180004d4a  jns     short loc_180004D61
0x180004d4c  mov     r8d, 34h ; '4'
0x180004d52  lea     rdx, aGetpollingtime; "GetPollingTimerFrequency"
0x180004d59  mov     ecx, eax
0x180004d5b  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x180004d61  mov     ecx, 20h ; ' '; Size
0x180004d66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d6b  xorps   xmm0, xmm0
0x180004d6e  movups  xmmword ptr [rax], xmm0
0x180004d71  movups  xmmword ptr [rax+10h], xmm0
0x180004d75  mov     rcx, rax; this
0x180004d78  call    ??0TimerQueue@@QEAA@XZ; TimerQueue::TimerQueue(void)
0x180004d7d  mov     rbx, rax
0x180004d80  mov     [rbp+57h+var_C8], rax
0x180004d84  cmp     [rax], rdi
0x180004d87  jnz     short loc_180004DA7
0x180004d89  call    cs:__imp_CreateTimerQueue
0x180004d8f  mov     [rbx], rax
0x180004d92  test    rax, rax
0x180004d95  jz      loc_180004E56
0x180004d9b  mov     rcx, [rbx+10h]
0x180004d9f  cmp     [rbx+8], rcx
0x180004da3  jz      short loc_180004DA7
0x180004da5  int     2Ch; Windows NT - assertion failure
0x180004da7  imul    r9d, dword ptr [rsp+110h+var_D8], 3E8h; unsigned int
0x180004db0  mov     [rsp+20h], r9d; unsigned int
0x180004db5  mov     rcx, rbx; this
0x180004db8  call    ?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z; TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)
0x180004dbd  test    eax, eax
0x180004dbf  js      loc_180004EB3
0x180004dc5  lea     rdx, [rbp+57h+var_C8]
0x180004dc9  lea     rcx, qword_18001D8A0
0x180004dd0  call    ??$?4U?$default_delete@VTimerQueue@@@std@@$0A@@?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TimerQueue>::operator=<std::default_delete<TimerQueue>,0>(std::unique_ptr<TimerQueue> &&)
0x180004dd5  nop
0x180004dd6  lea     rcx, [rbp+57h+var_C8]
0x180004dda  call    ??1?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(void)
0x180004ddf  mov     rax, cs:qword_18001D8A0
0x180004de6  mov     ebx, edi
0x180004de8  cmp     [rax], rdi
0x180004deb  jnz     short loc_180004DEF
0x180004ded  int     2Ch; Windows NT - assertion failure
0x180004def  lea     rcx, [rbp+57h+var_B0]
0x180004df3  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180004df8  mov     rax, [rbp+57h+var_88]
0x180004dfc  mov     rcx, [rbp+57h+var_78]
0x180004e00  mov     [rcx], rax
  ... truncated ...
```
