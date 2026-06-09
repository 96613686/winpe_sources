# MapsBackgroundTransferJob::AddRequestWithRanges(ushort const *,ulong,MAPSBTSVC_RANGE *,void (*)(ushort const *,long,ushort *,void *,void *),void *,void *)

- ea: `0x18000bb70`
- end: `0x18000c340`
- name: `?AddRequestWithRanges@MapsBackgroundTransferJob@@UEAAJPEBGKPEAUMAPSBTSVC_RANGE@@P6AX0JPEAGPEAX3@Z33@Z`
- size: `2000`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *this, const unsigned __int16 *, unsigned int, struct MAPSBTSVC_RANGE *, void (*)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *), void *, void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9c0`
- `0x18000fe80`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x180002924`
- `0x1800033d4`
- `0x180003a00`
- `0x180004094`
- `0x1800043e4`
- `0x180004408`
- `0x180004680`
- `0x1800047cc`
- `0x180008d3c`
- `0x18000a564`
- `0x18000a974`
- `0x18000adf0`
- `0x18000b3a4`
- `0x18000bb70`
- `0x18000c4dc`
- `0x18000c99c`
- `0x18000cf70`
- `0x18000ef18`
- `0x18000fb10`
- `0x180010420`
- `0x180010448`
- `0x18001074c`
- `0x180010954`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bde4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bde4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000be6a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000be6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be48`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c1ac`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c1ac`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bd12`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bd83`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000be00`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000be86`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bef4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bfc2`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c046`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c134`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c1d8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c309`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bd12`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bd83`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000be00`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000be86`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bef4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000bfc2`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c046`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c134`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c1d8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c309`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000bc06`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c0bc`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000bc06`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c0bc`

## string_xrefs

- `0x18000c18b`: `New file request | JobType: %d | RequestId: %ls | Path: %ls`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::AddRequestWithRanges(
        MapsBackgroundTransferJob *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct MAPSBTSVC_RANGE *a4,
        void (*a5)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *),
        void *a6,
        void *a7)
{
  unsigned __int64 v8; // r12
  unsigned int v11; // esi
  int v12; // r8d
  int v13; // ecx
  unsigned int v14; // eax
  int JobState; // eax
  int v16; // ebx
  _QWORD *v17; // rdx
  unsigned __int16 *v18; // rbx
  int v19; // eax
  int v20; // eax
  HRESULT v21; // eax
  void *v22; // rbx
  HRESULT v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rax
  unsigned __int16 *v26; // rbx
  unsigned int v27; // r8d
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rax
  _QWORD *v35; // rbx
  __int64 v36; // r14
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  bool *v41; // [rsp+30h] [rbp-348h]
  bool v42; // [rsp+40h] [rbp-338h] BYREF
  bool v43; // [rsp+41h] [rbp-337h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-330h] BYREF
  unsigned __int16 *v45; // [rsp+50h] [rbp-328h] BYREF
  __int64 v46; // [rsp+58h] [rbp-320h] BYREF
  _BYTE v47[16]; // [rsp+60h] [rbp-318h] BYREF
  void *v48; // [rsp+70h] [rbp-308h]
  unsigned __int16 *v49; // [rsp+78h] [rbp-300h] BYREF
  void *v50[3]; // [rsp+80h] [rbp-2F8h] BYREF
  _QWORD v51[3]; // [rsp+98h] [rbp-2E0h] BYREF
  _BYTE v52[32]; // [rsp+B0h] [rbp-2C8h] BYREF
  GUID pguid; // [rsp+D0h] [rbp-2A8h] BYREF
  _QWORD v54[7]; // [rsp+E0h] [rbp-298h] BYREF
  _QWORD *v55; // [rsp+118h] [rbp-260h]
  unsigned __int16 v56[264]; // [rsp+120h] [rbp-258h] BYREF

  v8 = a3;
  v50[2] = this;
  v48 = a6;
  v50[0] = a7;
  memset_0(v56, 0, 0x208u);
  v11 = 0;
  v49 = 0;
  v43 = 0;
  v42 = 0;
  if ( !a2 )
  {
    v12 = 767;
    v13 = -2147467261;
LABEL_3:
    v14 = ZTraceReportOrigination(v13, "MapsBackgroundTransferJob::AddRequestWithRanges", v12, this);
LABEL_52:
    v11 = v14;
    goto LABEL_53;
  }
  if ( !*a2 )
  {
    v12 = 768;
    v13 = -2147024809;
    goto LABEL_3;
  }
  JobState = MapsBackgroundTransferJob::GetJobState(this);
  if ( JobState == 5 )
  {
    v12 = 771;
    v13 = -2147019873;
    goto LABEL_3;
  }
  if ( (unsigned int)(JobState - 3) <= 1 )
  {
    v12 = 774;
    v13 = -2147023673;
    goto LABEL_3;
  }
  v45 = 0;
  v54[0] = off_1800162D8;
  v54[1] = a4;
  v55 = v54;
  v16 = MapsBackgroundTransferJob::GenerateRequestId(a2, (unsigned int)v8, v54, &v45);
  if ( v55 )
  {
    v17 = v54;
    LOBYTE(v17) = v55 != v54;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v55 + 32LL))(v55, v17);
  }
  if ( v16 < 0 )
  {
    v14 = ZTraceReportPropagation(v16, "MapsBackgroundTransferJob::AddRequestWithRanges", 786, this);
    goto LABEL_52;
  }
  v18 = v45;
  v49 = v45;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v47,
    (char *)this + 784);
  if ( _InterlockedExchange((volatile __int32 *)this + 20, 2) == 2
    || (v19 = MapsBackgroundTransferJob::SetUserProxySettings(this), v19 >= 0) )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
    v20 = MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob(this, v18, a5, v48, v50[0], &v43, &v42);
    if ( v20 >= 0 )
    {
      if ( !v42 )
      {
        std::wstring::wstring(v52, v18);
        pv = 0;
        pguid = 0;
        ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
          v47,
          (char *)this + 784);
        if ( !v43 )
        {
          v21 = CoCreateGuid(&pguid);
          if ( v21 < 0 )
          {
            v11 = ZTraceReportPropagation(v21, "MapsBackgroundTransferJob::AddRequestWithRanges", 825, this);
            ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
            std::wstring::_Tidy_deallocate(v52);
            goto LABEL_53;
          }
          v22 = pv;
          if ( pv )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v45);
            CoTaskMemFree(v22);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v45);
          }
          pv = 0;
          v23 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
          if ( v23 < 0 )
          {
            v11 = ZTraceReportPropagation(v23, "MapsBackgroundTransferJob::AddRequestWithRanges", 826, this);
            ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
            std::wstring::_Tidy_deallocate(v52);
            goto LABEL_53;
          }
          v24 = StringCchPrintfW(v56, 0x104u, L"%s\\%s.tmp", (char *)this + 84, pv);
          if ( v24 < 0 )
          {
            v11 = ZTraceReportPropagation(v24, "MapsBackgroundTransferJob::AddRequestWithRanges", 828, this);
            ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
            std::wstring::_Tidy_deallocate(v52);
            goto LABEL_53;
          }
          if ( (_DWORD)v8 )
          {
            v46 = 0;
            v25 = 16 * v8;
            if ( !is_mul_ok(v8, 0x10u) )
              v25 = -1;
            v26 = (unsigned __int16 *)operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
            v45 = v26;
            if ( !v26 )
            {
              v11 = ZTraceReportOrigination(-2147024882, "MapsBackgroundTransferJob::AddRequestWithRanges", 838, this);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v45);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              std::wstring::_Tidy_deallocate(v52);
              goto LABEL_53;
            }
            v27 = 0;
            v28 = 0;
            do
            {
              v29 = 2 * v28;
              *(_QWORD *)&v26[4 * v29] = *((_QWORD *)a4 + 2 * v28);
              *(_QWORD *)&v26[4 * v29 + 4] = *((_QWORD *)a4 + 2 * v28 + 1);
              ++v27;
              ++v28;
            }
            while ( v27 < (unsigned int)v8 );
            v30 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
                    *((_QWORD *)this + 3),
                    &GUID_443c8934_90ff_48ed_bcde_26f5c7450042,
                    &v46);
            if ( v30 < 0 )
            {
              v11 = ZTraceReportPropagation(v30, "MapsBackgroundTransferJob::AddRequestWithRanges", 846, this);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v45);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              std::wstring::_Tidy_deallocate(v52);
              goto LABEL_53;
            }
            v31 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, _QWORD, unsigned __int16 *))(*(_QWORD *)v46 + 352LL))(
                    v46,
                    a2,
                    v56,
                    (unsigned int)v8,
                    v26);
            if ( v31 < 0 )
            {
              v11 = ZTraceReportPropagation(v31, "MapsBackgroundTransferJob::AddRequestWithRanges", 847, this);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v45);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              std::wstring::_Tidy_deallocate(v52);
              goto LABEL_53;
            }
            std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v45);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
          }
          else
          {
            v32 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 *))(**((_QWORD **)this + 3)
                                                                                                  + 32LL))(
                    *((_QWORD *)this + 3),
                    a2,
                    v56);
            if ( v32 < 0 )
            {
              v11 = ZTraceReportPropagation(v32, "MapsBackgroundTransferJob::AddRequestWithRanges", 851, this);
              ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              std::wstring::_Tidy_deallocate(v52);
              goto LABEL_53;
            }
          }
          v41 = (bool *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
          ZTraceHelper(
            5,
            "MapsBackgroundTransferJob::AddRequestWithRanges",
            854,
            this,
            "New file request | JobType: %d | RequestId: %ls | Path: %ls",
            *((_DWORD *)this + 10),
            (const wchar_t *)v41,
            v56);
        }
        v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
        if ( v33 >= 0 )
        {
          v51[0] = a5;
          v51[1] = v48;
          v51[2] = v50[0];
          v34 = std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Try_emplace<std::wstring const &,>(
                  (char *)this + 608,
                  v50,
                  v52);
          v35 = (_QWORD *)(*(_QWORD *)v34 + 48LL);
          if ( *(_QWORD *)(*(_QWORD *)v34 + 64LL) <= (unsigned __int64)(*(_QWORD *)(*(_QWORD *)v34 + 80LL) + 1LL) )
            std::deque<MapsBackgroundTransferJob::RequestContext>::_Growmap(v35);
          v35[3] &= v35[2] - 1LL;
          v36 = v35[3] + v35[4];
          v37 = std::deque<MapsBackgroundTransferJob::RequestContext>::_Getblock(v35, v36);
          if ( !*(_QWORD *)(v35[1] + 8 * v37) )
            *(_QWORD *)(v35[1] + 8 * v37) = std::_Allocate<16,std::_Default_allocate_traits>(24);
          v38 = std::_Deque_val<std::_Deque_simple_types<MapsBackgroundTransferJob::RequestContext>>::_Address_subscript(
                  v35,
                  v36);
          std::_Default_allocator_traits<std::allocator<MapsBackgroundTransferJob::RequestContext>>::construct<MapsBackgroundTransferJob::RequestContext,MapsBackgroundTransferJob::RequestContext const &>(
            v39,
            v38,
            v51);
          ++v35[4];
          ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
          std::wstring::_Tidy_deallocate(v52);
        }
        else
        {
          v11 = ZTraceReportPropagation(v33, "MapsBackgroundTransferJob::AddRequestWithRanges", 859, this);
          ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
          std::wstring::_Tidy_deallocate(v52);
        }
      }
    }
    else
    {
      v11 = ZTraceReportPropagation(v20, "MapsBackgroundTransferJob::AddRequestWithRanges", 808, this);
    }
  }
  else
  {
    v11 = ZTraceReportPropagation(v19, "MapsBackgroundTransferJob::AddRequestWithRanges", 797, this);
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v47);
  }
LABEL_53:
  std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v49);
  return v11;
}

```

## disassembly

```asm
0x18000bb70  push    rbx
0x18000bb72  push    rsi
0x18000bb73  push    rdi
0x18000bb74  push    r12
0x18000bb76  push    r13
0x18000bb78  push    r14
0x18000bb7a  push    r15
0x18000bb7c  sub     rsp, 340h
0x18000bb83  mov     rax, cs:__security_cookie
0x18000bb8a  xor     rax, rsp
0x18000bb8d  mov     [rsp+378h+var_48], rax
0x18000bb95  mov     r13, r9
0x18000bb98  mov     r12d, r8d
0x18000bb9b  mov     r15, rdx
0x18000bb9e  mov     rdi, rcx
0x18000bba1  mov     [rsp+378h+var_2E8], rcx
0x18000bba9  mov     rax, [rsp+378h+arg_28]
0x18000bbb1  mov     [rsp+378h+var_308], rax
0x18000bbb6  mov     rax, [rsp+378h+arg_30]
0x18000bbbe  mov     [rsp+378h+var_2F8], rax
0x18000bbc6  xor     edx, edx; Val
0x18000bbc8  mov     r8d, 208h; Size
0x18000bbce  lea     rcx, [rsp+378h+var_258]; void *
0x18000bbd6  call    memset_0
0x18000bbdb  xor     esi, esi
0x18000bbdd  mov     [rsp+378h+var_300], rsi
0x18000bbe2  mov     [rsp+378h+var_337], sil
0x18000bbe7  mov     [rsp+378h+var_338], sil
0x18000bbec  test    r15, r15
0x18000bbef  jnz     short loc_18000BC11
0x18000bbf1  mov     r8d, 2FFh
0x18000bbf7  mov     ecx, 80004003h
0x18000bbfc  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bc03  mov     r9, rdi
0x18000bc06  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000bc0c  jmp     loc_18000C30F
0x18000bc11  cmp     [r15], si
0x18000bc15  jnz     short loc_18000BC24
0x18000bc17  mov     r8d, 300h
0x18000bc1d  mov     ecx, 80070057h
0x18000bc22  jmp     short loc_18000BBFC
0x18000bc24  mov     rcx, rdi
0x18000bc27  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x18000bc2c  cmp     eax, 5
0x18000bc2f  jnz     short loc_18000BC3E
0x18000bc31  mov     r8d, 303h
0x18000bc37  mov     ecx, 8007139Fh
0x18000bc3c  jmp     short loc_18000BBFC
0x18000bc3e  add     eax, 0FFFFFFFDh
0x18000bc41  cmp     eax, 1
0x18000bc44  ja      short loc_18000BC53
0x18000bc46  mov     r8d, 306h
0x18000bc4c  mov     ecx, 800704C7h
0x18000bc51  jmp     short loc_18000BBFC
0x18000bc53  mov     [rsp+378h+var_328], rsi
0x18000bc58  lea     rax, off_1800162D8
0x18000bc5f  mov     [rsp+378h+var_298], rax
0x18000bc67  mov     [rsp+378h+var_290], r13
0x18000bc6f  lea     rax, [rsp+378h+var_298]
0x18000bc77  mov     [rsp+378h+var_260], rax
0x18000bc7f  lea     r9, [rsp+378h+var_328]
0x18000bc84  lea     r8, [rsp+378h+var_298]
0x18000bc8c  mov     edx, r12d
0x18000bc8f  mov     rcx, r15
0x18000bc92  call    ?GenerateRequestId@MapsBackgroundTransferJob@@CAJPEBGKAEBV?$function@$$A6AJKPEA_K0@Z@std@@PEAPEAG@Z; MapsBackgroundTransferJob::GenerateRequestId(ushort const *,ulong,std::function<long (ulong,unsigned __int64 *,unsigned __int64 *)> const &,ushort * *)
0x18000bc97  mov     ebx, eax
0x18000bc99  mov     rcx, [rsp+378h+var_260]
0x18000bca1  test    rcx, rcx
0x18000bca4  jz      short loc_18000BCC0
0x18000bca6  mov     rax, [rcx]
0x18000bca9  lea     rdx, [rsp+378h+var_298]
0x18000bcb1  cmp     rcx, rdx
0x18000bcb4  setnz   dl
0x18000bcb7  mov     rax, [rax+20h]
0x18000bcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc0  test    ebx, ebx
0x18000bcc2  js      loc_18000C2F7
0x18000bcc8  mov     rbx, [rsp+378h+var_328]
0x18000bccd  mov     [rsp+378h+var_300], rbx
0x18000bcd2  lea     r14, [rdi+310h]
0x18000bcd9  mov     rdx, r14
0x18000bcdc  lea     rcx, [rsp+378h+var_318]
0x18000bce1  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000bce6  nop
0x18000bce7  mov     eax, 2
0x18000bcec  xchg    eax, [rdi+50h]
0x18000bcef  cmp     eax, 2
0x18000bcf2  jz      short loc_18000BD2A
0x18000bcf4  mov     rcx, rdi; this
0x18000bcf7  call    ?SetUserProxySettings@MapsBackgroundTransferJob@@AEAAJXZ; MapsBackgroundTransferJob::SetUserProxySettings(void)
0x18000bcfc  test    eax, eax
0x18000bcfe  jns     short loc_18000BD2A
0x18000bd00  mov     r9, rdi
0x18000bd03  mov     r8d, 31Dh
0x18000bd09  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bd10  mov     ecx, eax
0x18000bd12  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000bd18  mov     esi, eax
0x18000bd1a  lea     rcx, [rsp+378h+var_318]
0x18000bd1f  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000bd24  nop
0x18000bd25  jmp     loc_18000C311
0x18000bd2a  lea     rcx, [rsp+378h+var_318]
0x18000bd2f  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000bd34  lea     rax, [rsp+378h+var_338]
0x18000bd39  mov     [rsp+378h+var_348], rax; bool *
0x18000bd3e  lea     rax, [rsp+378h+var_337]
0x18000bd43  mov     [rsp+378h+var_350], rax; bool *
0x18000bd48  mov     rax, [rsp+378h+var_2F8]
0x18000bd50  mov     [rsp+378h+var_358], rax; void *
0x18000bd55  mov     r9, [rsp+378h+var_308]; void *
0x18000bd5a  mov     r8, [rsp+378h+arg_20]; void (*)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *)
0x18000bd62  mov     rdx, rbx; unsigned __int16 *
0x18000bd65  mov     rcx, rdi; this
0x18000bd68  call    ?CompleteRequestIfAlreadyPartOfJob@MapsBackgroundTransferJob@@AEAAJPEBGP6AX0JPEAGPEAX2@Z22PEA_N4@Z; MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob(ushort const *,void (*)(ushort const *,long,ushort *,void *,void *),void *,void *,bool *,bool *)
0x18000bd6d  test    eax, eax
0x18000bd6f  jns     short loc_18000BD90
0x18000bd71  mov     r9, rdi
0x18000bd74  mov     r8d, 328h
0x18000bd7a  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bd81  mov     ecx, eax
0x18000bd83  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000bd89  mov     esi, eax
0x18000bd8b  jmp     loc_18000C311
0x18000bd90  cmp     [rsp+378h+var_338], 0
0x18000bd95  jnz     loc_18000C2EF
0x18000bd9b  mov     rdx, rbx
0x18000bd9e  lea     rcx, [rsp+378h+var_2C8]
0x18000bda6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bdab  nop
0x18000bdac  mov     [rsp+378h+pv], 0
0x18000bdb5  xorps   xmm0, xmm0
0x18000bdb8  movups  xmmword ptr [rsp+378h+pguid.Data1], xmm0
0x18000bdc0  mov     rdx, r14
0x18000bdc3  lea     rcx, [rsp+378h+var_318]
0x18000bdc8  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000bdcd  nop
0x18000bdce  xor     r14d, r14d
0x18000bdd1  cmp     [rsp+378h+var_337], r14b
0x18000bdd6  jnz     loc_18000C1B2
0x18000bddc  lea     rcx, [rsp+378h+pguid]; pguid
0x18000bde4  call    cs:__imp_CoCreateGuid
0x18000bdea  test    eax, eax
0x18000bdec  jns     short loc_18000BE31
0x18000bdee  mov     r9, rdi
0x18000bdf1  mov     r8d, 339h
0x18000bdf7  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bdfe  mov     ecx, eax
0x18000be00  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000be06  mov     esi, eax
0x18000be08  lea     rcx, [rsp+378h+var_318]
0x18000be0d  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000be12  nop
0x18000be13  lea     rcx, [rsp+378h+pv]
0x18000be18  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000be1d  nop
0x18000be1e  lea     rcx, [rsp+378h+var_2C8]
0x18000be26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000be2b  nop
0x18000be2c  jmp     loc_18000C311
0x18000be31  mov     rbx, [rsp+378h+pv]
0x18000be36  test    rbx, rbx
0x18000be39  jz      short loc_18000BE58
0x18000be3b  lea     rcx, [rsp+378h+var_328]; this
0x18000be40  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000be45  mov     rcx, rbx; pv
0x18000be48  call    cs:__imp_CoTaskMemFree
0x18000be4e  lea     rcx, [rsp+378h+var_328]; this
0x18000be53  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000be58  mov     [rsp+378h+pv], r14
0x18000be5d  lea     rdx, [rsp+378h+pv]; lplpsz
0x18000be62  lea     rcx, [rsp+378h+pguid]; rclsid
0x18000be6a  call    cs:__imp_StringFromCLSID
0x18000be70  test    eax, eax
0x18000be72  jns     short loc_18000BEB7
0x18000be74  mov     r9, rdi
0x18000be77  mov     r8d, 33Ah
0x18000be7d  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000be84  mov     ecx, eax
0x18000be86  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000be8c  mov     esi, eax
0x18000be8e  lea     rcx, [rsp+378h+var_318]
0x18000be93  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000be98  nop
0x18000be99  lea     rcx, [rsp+378h+pv]
0x18000be9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bea3  nop
0x18000bea4  lea     rcx, [rsp+378h+var_2C8]
0x18000beac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000beb1  nop
0x18000beb2  jmp     loc_18000C311
0x18000beb7  lea     r9, [rdi+54h]
0x18000bebb  mov     rax, [rsp+378h+pv]
0x18000bec0  mov     [rsp+378h+var_358], rax
0x18000bec5  lea     r8, aSSTmp; "%s\\%s.tmp"
0x18000becc  mov     edx, 104h; unsigned __int64
0x18000bed1  lea     rcx, [rsp+378h+var_258]; unsigned __int16 *
0x18000bed9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bede  test    eax, eax
0x18000bee0  jns     short loc_18000BF25
0x18000bee2  mov     r9, rdi
0x18000bee5  mov     r8d, 33Ch
0x18000beeb  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bef2  mov     ecx, eax
0x18000bef4  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000befa  mov     esi, eax
0x18000befc  lea     rcx, [rsp+378h+var_318]
0x18000bf01  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000bf06  nop
0x18000bf07  lea     rcx, [rsp+378h+pv]
0x18000bf0c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bf11  nop
0x18000bf12  lea     rcx, [rsp+378h+var_2C8]
0x18000bf1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bf1f  nop
0x18000bf20  jmp     loc_18000C311
0x18000bf25  test    r12d, r12d
0x18000bf28  jz      loc_18000C103
0x18000bf2e  mov     [rsp+378h+var_320], r14
0x18000bf33  mov     eax, 10h
0x18000bf38  mul     r12
0x18000bf3b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf42  cmovb   rax, rcx
0x18000bf46  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf4d  mov     rcx, rax; unsigned __int64
0x18000bf50  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bf55  mov     rbx, rax
0x18000bf58  mov     [rsp+378h+var_328], rax
0x18000bf5d  test    rax, rax
0x18000bf60  jz      loc_18000C0A7
0x18000bf66  mov     r8d, r14d
0x18000bf69  mov     rdx, r14
0x18000bf6c  mov     rcx, rdx
0x18000bf6f  add     rcx, rcx
0x18000bf72  mov     rax, [r13+rcx*8+0]
0x18000bf77  mov     [rbx+rcx*8], rax
0x18000bf7b  mov     rax, [r13+rcx*8+8]
0x18000bf80  mov     [rbx+rcx*8+8], rax
0x18000bf85  inc     r8d
0x18000bf88  inc     rdx
0x18000bf8b  cmp     r8d, r12d
0x18000bf8e  jb      short loc_18000BF6C
0x18000bf90  mov     rcx, [rdi+18h]
0x18000bf94  mov     rax, [rcx]
0x18000bf97  lea     r8, [rsp+378h+var_320]
0x18000bf9c  lea     rdx, _GUID_443c8934_90ff_48ed_bcde_26f5c7450042
0x18000bfa3  mov     rax, [rax]
0x18000bfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfab  nop
0x18000bfac  test    eax, eax
0x18000bfae  jns     short loc_18000C009
0x18000bfb0  mov     r9, rdi
0x18000bfb3  mov     r8d, 34Eh
0x18000bfb9  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000bfc0  mov     ecx, eax
0x18000bfc2  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000bfc8  mov     esi, eax
0x18000bfca  lea     rcx, [rsp+378h+var_328]
0x18000bfcf  call    ??1?$unique_ptr@$$BY0A@U_BG_FILE_RANGE@@U?$default_delete@$$BY0A@U_BG_FILE_RANGE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(void)
0x18000bfd4  nop
0x18000bfd5  lea     rcx, [rsp+378h+var_320]
0x18000bfda  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bfdf  nop
0x18000bfe0  lea     rcx, [rsp+378h+var_318]
0x18000bfe5  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000bfea  nop
0x18000bfeb  lea     rcx, [rsp+378h+pv]
0x18000bff0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bff5  nop
0x18000bff6  lea     rcx, [rsp+378h+var_2C8]
0x18000bffe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c003  nop
0x18000c004  jmp     loc_18000C311
0x18000c009  mov     rcx, [rsp+378h+var_320]
0x18000c00e  mov     rax, [rcx]
0x18000c011  mov     [rsp+378h+var_358], rbx
0x18000c016  mov     r9d, r12d
0x18000c019  lea     r8, [rsp+378h+var_258]
0x18000c021  mov     rdx, r15
0x18000c024  mov     rax, [rax+160h]
0x18000c02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c030  test    eax, eax
0x18000c032  jns     short loc_18000C08D
0x18000c034  mov     r9, rdi
0x18000c037  mov     r8d, 34Fh
0x18000c03d  lea     rdx, aMapsbackground_37; "MapsBackgroundTransferJob::AddRequestWi"...
0x18000c044  mov     ecx, eax
0x18000c046  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c04c  mov     esi, eax
0x18000c04e  lea     rcx, [rsp+378h+var_328]
0x18000c053  call    ??1?$unique_ptr@$$BY0A@U_BG_FILE_RANGE@@U?$default_delete@$$BY0A@U_BG_FILE_RANGE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(void)
0x18000c058  nop
0x18000c059  lea     rcx, [rsp+378h+var_320]
0x18000c05e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c063  nop
0x18000c064  lea     rcx, [rsp+378h+var_318]
0x18000c069  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000c06e  nop
0x18000c06f  lea     rcx, [rsp+378h+pv]
0x18000c074  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
