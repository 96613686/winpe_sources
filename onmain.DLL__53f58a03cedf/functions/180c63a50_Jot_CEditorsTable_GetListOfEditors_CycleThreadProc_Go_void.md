# Jot::CEditorsTable_GetListOfEditors::CycleThreadProc_Go(void)

- ea: `0x180c63a50`
- end: `0x180c64266`
- name: `?CycleThreadProc_Go@CEditorsTable_GetListOfEditors@Jot@@MEAAXXZ`
- size: `2070`
- prototype: `void __fastcall(Jot::CEditorsTable_GetListOfEditors *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180032260`
- `0x1800769c0`
- `0x18007b364`
- `0x18019968c`
- `0x180284f0c`
- `0x180284f60`
- `0x1802e2190`
- `0x1802e4c00`
- `0x1802e5170`
- `0x1802e5190`
- `0x18032efc8`
- `0x1803a12e0`
- `0x180444d58`
- `0x180444f90`
- `0x1804834c4`
- `0x180485a14`
- `0x1805adc20`
- `0x180655854`
- `0x180c63a50`

## import_xrefs

- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180c63e56`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180c63f9f`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180c63e56`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180c63f9f`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180c63d74`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180c63d74`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180c63e21`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180c641c2`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180c63e21`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180c641c2`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63e60`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63eed`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63fa9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c640ae`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63e60`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63eed`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c63fa9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180c640ae`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180c63eba`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180c6407b`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180c63eba`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180c6407b`
- `Csi!?CreateCellStorageOverHttp@Csi@@YAXPEB_WPEAPEAUICellStorage@CsiCell@@AEBU_GUID@@PEAUIWebServiceSubRequestUserManager@1@PEAUIWebServiceRequest@1@0_N@Z` at `0x180c63b21`
- `Csi!?CreateCellStorageOverHttp@Csi@@YAXPEB_WPEAPEAUICellStorage@CsiCell@@AEBU_GUID@@PEAUIWebServiceSubRequestUserManager@1@PEAUIWebServiceRequest@1@0_N@Z` at `0x180c63b21`
- `Csi!?GetCellStorageMultiRoundTrip@Csi@@YAXPEAUICellStorage@CsiCell@@PEAUIMultiRoundTripSuspend@3@PEAPEAU23@@Z` at `0x180c63b3f`
- `Csi!?GetCellStorageMultiRoundTrip@Csi@@YAXPEAUICellStorage@CsiCell@@PEAUIMultiRoundTripSuspend@3@PEAPEAU23@@Z` at `0x180c63b3f`
- `Csi!HrCreateEditorsTableXmlManager` at `0x180c63e30`
- `Csi!HrCreateEditorsTableXmlManager` at `0x180c63e30`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c63a9d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c63a9d`

## string_xrefs

- `0x180c63e7a`: `HrCreateEditorsTableXmlManagerFailed`

## pseudocode

```c
void __fastcall Jot::CEditorsTable_GetListOfEditors::CycleThreadProc_Go(Jot::CEditorsTable_GetListOfEditors *this)
{
  struct Csi::IWebServiceRequest *v2; // rbx
  Csi *v3; // rax
  struct CsiCell::ICellStorage **v4; // r9
  __int64 v5; // rdi
  __int64 v6; // rcx
  GUID *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r14
  void (__fastcall *v13)(__int64, __int64, __int64); // rbx
  __int64 v14; // rax
  const void *v15; // rax
  void (__fastcall *v16)(Jot::CEditorsTable_GetListOfEditors *, __int128 *); // rbx
  Jot *v17; // rax
  const struct std::exception_ptr *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int128 *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  const void *v24; // rax
  const struct Jot::Logging::ErrorData *v25; // r9
  void (__fastcall *v26)(Jot::CEditorsTable_GetListOfEditors *, __int128 *); // rbx
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, __int64, char *); // r15
  __int64 v29; // rax
  __int64 v30; // r14
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  const void *v34; // rax
  void (__fastcall *v35)(Jot::CEditorsTable_GetListOfEditors *, __int128 *); // rbx
  __int64 v36; // rax
  int v37; // [rsp+28h] [rbp-E0h]
  int v38; // [rsp+30h] [rbp-D8h]
  const wchar_t *v39; // [rsp+38h] [rbp-D0h]
  bool v40; // [rsp+40h] [rbp-C8h]
  __int128 v41; // [rsp+68h] [rbp-A0h] BYREF
  Csi *v42; // [rsp+78h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h] BYREF
  __int64 v44; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v45[2]; // [rsp+90h] [rbp-78h] BYREF
  const char *v46; // [rsp+98h] [rbp-70h]
  __m128i si128; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-58h] BYREF
  void **v49; // [rsp+B8h] [rbp-50h] BYREF
  void **v50; // [rsp+C0h] [rbp-48h]
  const wchar_t *v51; // [rsp+C8h] [rbp-40h]
  __int64 v52; // [rsp+D0h] [rbp-38h]
  __int128 *v53; // [rsp+D8h] [rbp-30h]
  __int16 v54; // [rsp+E0h] [rbp-28h]
  __int64 v55; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-18h] BYREF
  int v57; // [rsp+F8h] [rbp-10h]
  int v58; // [rsp+FCh] [rbp-Ch]
  GUID v59; // [rsp+100h] [rbp-8h] BYREF
  Csi **v60; // [rsp+110h] [rbp+8h]
  GUID v61; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v62[16]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v63[16]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v64[56]; // [rsp+150h] [rbp+48h] BYREF

  if ( !*((_QWORD *)this + 50) )
  {
    CrashWithRecovery(0x1E3CC344u, 0);
    __debugbreak();
  }
  Jot::WrapCsi::InitCsi(this);
  v56 = 0x49D623857808F4DDLL;
  v57 = -1405628745;
  v58 = 37151909;
  v42 = 0;
  v2 = (Jot::CEditorsTable_GetListOfEditors *)((char *)this + 472);
  if ( *((_QWORD *)this + 62) > 7u )
    v2 = *(struct Csi::IWebServiceRequest **)v2;
  v3 = (Csi *)(*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD))(**((_QWORD **)this + 50) + 112LL))(
                *((_QWORD *)this + 50),
                &v59,
                0);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(Csi **)v3;
  LOBYTE(v39) = 0;
  Csi::CreateCellStorageOverHttp(v3, (const wchar_t *)&v42, (struct CsiCell::ICellStorage **)&v56, 0, 0, v2, v39, v40);
  std::wstring::~wstring(&v59);
  v44 = 0;
  Csi::GetCellStorageMultiRoundTrip(v42, 0, (struct CsiCell::IMultiRoundTripSuspend *)&v44, v4);
  LOBYTE(v38) = 1;
  LOBYTE(v37) = 1;
  Jot::ExecuteQueryChanges(
    &v55,
    v44,
    0,
    (char *)this + 416,
    v37,
    v38,
    &CsiCell::c_ccidNull,
    *((_QWORD *)this + 51),
    0,
    0,
    0,
    0);
  v5 = v55;
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v55 + 72LL))(v55, -1, 0);
  v6 = 0;
  v43 = 0;
  if ( v42 )
  {
    (**(void (__fastcall ***)(Csi *, GUID *, __int64 *))v42)(v42, &GUID_d8a64a06_ff59_466f_ba6d_d6a96c902030, &v43);
    v6 = v43;
  }
  if ( v6 )
  {
    v7 = (GUID *)(*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v6 + 72LL))(v6, &v59);
  }
  else
  {
    v59 = GUID_NULL;
    v7 = &v59;
  }
  v61 = *v7;
  *(GUID *)((char *)this + 504) = *v7;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
  v49 = &Jot::Logging::details::StructuredTraceImplementation<std::exception_ptr>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v50 = &Jot::Logging::details::StructuredTraceImplementation<std::exception_ptr>::`vftable'{for `Mso::Telemetry::IDataField'};
  v51 = L"Error";
  v52 = -1;
  v53 = (__int128 *)v8;
  v54 = 4;
  v10 = Jot::Logging::details::LogNonPIIDataValidated<_GUID>(v62, v9, &v61);
  *(_QWORD *)v45 = &off_1811FD050;
  v46 = "RequestInfo";
  *(_QWORD *)&v41 = v10;
  *((_QWORD *)&v41 + 1) = &v49;
  *(_QWORD *)&v59.Data1 = &Mso::Logging::CompositeStructuredTrace::`vftable';
  *(_QWORD *)v59.Data4 = &v41;
  v60 = &v42;
  Jot::Logging::details::SendStructuredTraceTag(507298624, 50, v45, &v59);
  std::wstring::~wstring(v63);
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 152LL))(v5, v45);
  if ( (_BYTE)v46 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 50) + 232LL))(
            *((_QWORD *)this + 50),
            &v41);
    v12 = *(_QWORD *)v11;
    v13 = *(void (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)v11 + 248LL);
    v14 = std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(v45);
    v13(v12, 3, v14);
    if ( (_QWORD)v41 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v15 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
  if ( __ExceptionPtrToBool(v15) )
  {
    v16 = *(void (__fastcall **)(Jot::CEditorsTable_GetListOfEditors *, __int128 *))(*(_QWORD *)this + 96LL);
    v17 = (Jot *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
    v19 = Jot::Win32ErrorCodeFromCsiOrCellError(v17, v18);
    v20 = Jot::CreateWin32ExceptionTag(&v59, v19, 17147419);
LABEL_17:
    v21 = (__int128 *)v20;
LABEL_39:
    v16(this, v21);
    goto LABEL_40;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 112LL))(v5)
    || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5) )
  {
    v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 144LL))(v5);
    MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign((char *)this + 408, v36);
    *((_BYTE *)this + 464) = 1;
    (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v5 + 152LL))(v5, &v59);
    if ( v59.Data4[0] )
    {
      *(_QWORD *)&v41 = *(_QWORD *)std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(&v59)
                      / 10000LL;
      v49 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
      v50 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'};
      v51 = L"MsecsInterval";
      v52 = -1;
      v53 = &v41;
      v54 = 4;
      *(_QWORD *)v45 = &off_1811FD050;
      v46 = "GetEditorsSuggestedInterval";
      Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceImplementation<_GUID>>(507298595, v45, 100, &v49);
    }
    v16 = *(void (__fastcall **)(Jot::CEditorsTable_GetListOfEditors *, __int128 *))(*(_QWORD *)this + 96LL);
    v41 = 0;
    __ExceptionPtrCreate(&v41);
    v21 = &v41;
    goto LABEL_39;
  }
  if ( *((_BYTE *)this + 177) )
  {
    v16 = *(void (__fastcall **)(Jot::CEditorsTable_GetListOfEditors *, __int128 *))(*(_QWORD *)this + 96LL);
    v22 = Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(v62, 17147420);
    v20 = std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(&v59, v22);
    goto LABEL_17;
  }
  si128 = 0;
  __ExceptionPtrCreate(&si128);
  v48 = 0;
  v23 = HrCreateEditorsTableXmlManager(&v48);
  if ( v23 >= 0 )
  {
    v27 = v48;
    v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v48 + 16LL);
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
    v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 120LL))(v29);
    v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 136LL))(v5);
    v32 = v28(v27, v31, v30, (char *)this + 520);
    if ( v32 < 0 )
    {
      v34 = (const void *)Jot::CreateHRESULTExceptionTag(&v59, (unsigned int)v32, 17147422);
      __ExceptionPtrAssign(&si128, v34);
      __ExceptionPtrDestroy(&v59);
    }
    else
    {
      v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 144LL))(v5);
      MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign((char *)this + 408, v33);
    }
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 152LL))(v5, v45);
    if ( (_BYTE)v46 )
    {
      *(_QWORD *)&v41 = *(_QWORD *)std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(v45)
                      / 10000LL;
      v49 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
      v50 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'};
      v51 = L"MsecsInterval";
      v52 = -1;
      v53 = &v41;
      v54 = 4;
      *(_QWORD *)&v59.Data1 = &off_1811FD050;
      *(_QWORD *)v59.Data4 = "GetEditorsSuggestedInterval";
      Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceImplementation<_GUID>>(507298592, &v59, 100, &v49);
    }
    v35 = *(void (__fastcall **)(Jot::CEditorsTable_GetListOfEditors *, __int128 *))(*(_QWORD *)this + 96LL);
    v41 = 0;
    __ExceptionPtrCopy(&v41, &si128);
    v35(this, &v41);
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
    __ExceptionPtrDestroy(&si128);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    goto LABEL_43;
  }
  v24 = (const void *)Jot::CreateHRESULTExceptionTag(&v59, (unsigned int)v23, 17147421);
  __ExceptionPtrAssign(&si128, v24);
  __ExceptionPtrDestroy(&v59);
  Jot::ToErrorData(v62, &si128, 0);
  *(_QWORD *)v45 = &off_1811FD050;
  v46 = "HrCreateEditorsTableXmlManagerFailed";
  Jot::Logging::LogUnexpectedTag(
    (Jot::Logging *)0x1E3CC322,
    (unsigned int)v45,
    (const struct Mso::Telemetry::EventName *)v62,
    v25);
  std::_Optional_destruct_base<std::string,0>::~_Optional_destruct_base<std::string,0>(v64);
  v26 = *(void (__fastcall **)(Jot::CEditorsTable_GetListOfEditors *, __int128 *))(*(_QWORD *)this + 96LL);
  v41 = 0;
  __ExceptionPtrCopy(&v41, &si128);
  v26(this, &v41);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
  __ExceptionPtrDestroy(&si128);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_40:
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v5 )
LABEL_43:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v42 )
    (*(void (__fastcall **)(Csi *))(*(_QWORD *)v42 + 16LL))(v42);
}

```

## disassembly

```asm
0x180c63a50  mov     rax, rsp
0x180c63a53  mov     [rax+10h], rbx
0x180c63a57  mov     [rax+18h], rsi
0x180c63a5b  mov     [rax+20h], rdi
0x180c63a5f  push    rbp
0x180c63a60  push    r12
0x180c63a62  push    r13
0x180c63a64  push    r14
0x180c63a66  push    r15
0x180c63a68  lea     rbp, [rax-0B8h]
0x180c63a6f  sub     rsp, 190h
0x180c63a76  mov     rax, cs:__security_cookie
0x180c63a7d  xor     rax, rsp
0x180c63a80  mov     [rbp+0B0h+var_30], rax
0x180c63a87  mov     r12, rcx
0x180c63a8a  xor     r15d, r15d
0x180c63a8d  cmp     [rcx+190h], r15
0x180c63a94  jnz     short loc_180C63AA4
0x180c63a96  xor     edx, edx
0x180c63a98  mov     ecx, 1E3CC344h
0x180c63a9d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180c63aa3  int     3; Trap to Debugger
0x180c63aa4  call    ?InitCsi@WrapCsi@Jot@@YAXXZ; Jot::WrapCsi::InitCsi(void)
0x180c63aa9  mov     [rbp+0B0h+var_C8], 7808F4DDh
0x180c63ab0  mov     [rbp+0B0h+var_C4], 49D62385h
0x180c63ab7  mov     [rbp+0B0h+var_C0], 0AC37CEB7h
0x180c63abe  mov     [rbp+0B0h+var_BC], 236E4A5h
0x180c63ac5  mov     [rsp+1B0h+var_140], r15
0x180c63aca  lea     rbx, [r12+1D8h]
0x180c63ad2  cmp     qword ptr [rbx+18h], 7
0x180c63ad7  jbe     short loc_180C63ADC
0x180c63ad9  mov     rbx, [rbx]
0x180c63adc  mov     rcx, [r12+190h]
0x180c63ae4  mov     rax, [rcx]
0x180c63ae7  xor     r8d, r8d
0x180c63aea  lea     rdx, [rbp+0B0h+var_B8]
0x180c63aee  mov     rax, [rax+70h]
0x180c63af2  call    cs:__guard_dispatch_icall_fptr
0x180c63af8  cmp     qword ptr [rax+18h], 7
0x180c63afd  jbe     short loc_180C63B03
0x180c63aff  nop
0x180c63b00  mov     rax, [rax]
0x180c63b03  mov     byte ptr [rsp+1B0h+var_180], r15b
0x180c63b08  mov     [rsp+1B0h+var_188], rbx
0x180c63b0d  mov     [rsp+1B0h+var_190], r15
0x180c63b12  xor     r9d, r9d
0x180c63b15  lea     r8, [rbp+0B0h+var_C8]
0x180c63b19  lea     rdx, [rsp+1B0h+var_140]
0x180c63b1e  mov     rcx, rax
0x180c63b21  call    cs:__imp_?CreateCellStorageOverHttp@Csi@@YAXPEB_WPEAPEAUICellStorage@CsiCell@@AEBU_GUID@@PEAUIWebServiceSubRequestUserManager@1@PEAUIWebServiceRequest@1@0_N@Z; Csi::CreateCellStorageOverHttp(wchar_t const *,CsiCell::ICellStorage * *,_GUID const &,Csi::IWebServiceSubRequestUserManager *,Csi::IWebServiceRequest *,wchar_t const *,bool)
0x180c63b27  lea     rcx, [rbp+0B0h+var_B8]; void *
0x180c63b2b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180c63b30  mov     [rbp+0B0h+var_130], r15
0x180c63b34  lea     r8, [rbp+0B0h+var_130]
0x180c63b38  xor     edx, edx
0x180c63b3a  mov     rcx, [rsp+1B0h+var_140]
0x180c63b3f  call    cs:__imp_?GetCellStorageMultiRoundTrip@Csi@@YAXPEAUICellStorage@CsiCell@@PEAUIMultiRoundTripSuspend@3@PEAPEAU23@@Z; Csi::GetCellStorageMultiRoundTrip(CsiCell::ICellStorage *,CsiCell::IMultiRoundTripSuspend *,CsiCell::ICellStorage * *)
0x180c63b45  lea     r13, [r12+198h]
0x180c63b4d  mov     rax, [r13+0]
0x180c63b51  lea     r9, [r12+1A0h]
0x180c63b59  mov     byte ptr [rsp+1B0h+var_158], r15b
0x180c63b5e  mov     [rsp+1B0h+var_160], r15b
0x180c63b63  mov     [rsp+1B0h+var_168], r15b
0x180c63b68  mov     [rsp+1B0h+var_170], r15b
0x180c63b6d  mov     qword ptr [rsp+1B0h+var_178], rax
0x180c63b72  lea     rax, ?c_ccidNull@CsiCell@@3UContextAndCellID@1@B; CsiCell::ContextAndCellID const CsiCell::c_ccidNull
0x180c63b79  mov     [rsp+1B0h+var_180], rax
0x180c63b7e  mov     byte ptr [rsp+1B0h+var_188], 1
0x180c63b83  mov     byte ptr [rsp+1B0h+var_190], 1
0x180c63b88  xor     r8d, r8d
0x180c63b8b  mov     rdx, [rbp+0B0h+var_130]
0x180c63b8f  lea     rcx, [rbp+0B0h+var_D0]
0x180c63b93  call    ?ExecuteQueryChanges@Jot@@YA?AV?$CIPtr@UIAsyncResult_CellStorageQueryChanges@Jot@@U12@@MsoCF@@PEAUICellStorage@CsiCell@@PEAUIDataElementCallbacks@5@AEBUCellRequestMetadata@1@_N3AEBUContextAndCellID@5@PEAUIKnowledge@Csi@@3333@Z; Jot::ExecuteQueryChanges(CsiCell::ICellStorage *,CsiCell::IDataElementCallbacks *,Jot::CellRequestMetadata const &,bool,bool,CsiCell::ContextAndCellID const &,Csi::IKnowledge *,bool,bool,bool,bool)
0x180c63b98  nop
0x180c63b99  mov     rdi, [rbp+0B0h+var_D0]
0x180c63b9d  mov     rax, [rdi]
0x180c63ba0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180c63ba4  xor     r8d, r8d
0x180c63ba7  mov     rdx, rsi
0x180c63baa  mov     rcx, rdi
0x180c63bad  mov     rax, [rax+48h]
0x180c63bb1  call    cs:__guard_dispatch_icall_fptr
0x180c63bb7  mov     rcx, r15
0x180c63bba  mov     [rsp+1B0h+var_138], rcx
0x180c63bbf  mov     r9, [rsp+1B0h+var_140]
0x180c63bc4  test    r9, r9
0x180c63bc7  jz      short loc_180C63BE9
0x180c63bc9  mov     rax, [r9]
0x180c63bcc  lea     r8, [rsp+1B0h+var_138]
0x180c63bd1  lea     rdx, _GUID_d8a64a06_ff59_466f_ba6d_d6a96c902030
0x180c63bd8  mov     rcx, r9
0x180c63bdb  mov     rax, [rax]
0x180c63bde  call    cs:__guard_dispatch_icall_fptr
0x180c63be4  mov     rcx, [rsp+1B0h+var_138]
0x180c63be9  test    rcx, rcx
0x180c63bec  jz      short loc_180C63C01
0x180c63bee  mov     rax, [rcx]
0x180c63bf1  lea     rdx, [rbp+0B0h+var_B8]
0x180c63bf5  mov     rax, [rax+48h]
0x180c63bf9  call    cs:__guard_dispatch_icall_fptr
0x180c63bff  jmp     short loc_180C63C11
0x180c63c01  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180c63c08  movdqu  [rbp+0B0h+var_B8], xmm0
0x180c63c0d  lea     rax, [rbp+0B0h+var_B8]
0x180c63c11  movups  xmm0, xmmword ptr [rax]
0x180c63c14  movdqu  [rbp+0B0h+var_98], xmm0
0x180c63c19  movups  xmm1, xmmword ptr [rax]
0x180c63c1c  movdqu  xmmword ptr [r12+1F8h], xmm1
0x180c63c26  mov     rax, [rdi]
0x180c63c29  mov     rcx, rdi
0x180c63c2c  mov     rax, [rax+50h]
0x180c63c30  call    cs:__guard_dispatch_icall_fptr
0x180c63c36  lea     rcx, ??_7?$StructuredTraceImplementation@Vexception_ptr@std@@@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<std::exception_ptr>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x180c63c3d  mov     [rbp+0B0h+var_100], rcx
0x180c63c41  lea     rcx, ??_7?$StructuredTraceImplementation@Vexception_ptr@std@@@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<std::exception_ptr>::`vftable'{for `Mso::Telemetry::IDataField'}
0x180c63c48  mov     [rbp+0B0h+var_F8], rcx
0x180c63c4c  lea     rcx, aError_0; "Error"
0x180c63c53  mov     [rbp+0B0h+var_F0], rcx
0x180c63c57  mov     [rbp+0B0h+var_E8], rsi
0x180c63c5b  mov     [rbp+0B0h+var_E0], rax
0x180c63c5f  mov     r14d, 4
0x180c63c65  mov     [rbp+0B0h+var_D8], r14w
0x180c63c6a  lea     r8, [rbp+0B0h+var_98]
0x180c63c6e  lea     rcx, [rbp+0B0h+var_88]
0x180c63c72  call    ??$LogNonPIIDataValidated@U_GUID@@@details@Logging@Jot@@YA?A_PPEB_WAEBU_GUID@@W4DataClassifications@1Mso@@@Z
0x180c63c77  lea     rbx, off_1811FD050
0x180c63c7e  mov     qword ptr [rbp+0B0h+var_128], rbx
0x180c63c82  lea     rcx, aRequestinfo; "RequestInfo"
0x180c63c89  mov     [rbp+0B0h+var_120], rcx
0x180c63c8d  mov     qword ptr [rsp+1B0h+var_158+8], rax
0x180c63c92  lea     rax, [rbp+0B0h+var_100]
0x180c63c96  mov     [rsp+1B0h+var_148], rax
0x180c63c9b  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180c63ca2  mov     qword ptr [rbp+0B0h+var_B8], rax
0x180c63ca6  lea     rax, [rsp+1B0h+var_158+8]
0x180c63cab  mov     qword ptr [rbp+0B0h+var_B8+8], rax
0x180c63caf  lea     rax, [rsp+1B0h+var_140]
0x180c63cb4  mov     [rbp+0B0h+var_A8], rax
0x180c63cb8  lea     r9, [rbp+0B0h+var_B8]
0x180c63cbc  lea     r8, [rbp+0B0h+var_128]
0x180c63cc0  lea     edx, [r14+2Eh]
0x180c63cc4  mov     ecx, 1E3CC340h
0x180c63cc9  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x180c63cce  lea     rcx, [rbp+0B0h+var_78]; void *
0x180c63cd2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180c63cd7  mov     rax, [rdi]
0x180c63cda  lea     rdx, [rbp+0B0h+var_128]
0x180c63cde  mov     rcx, rdi
0x180c63ce1  mov     rax, [rax+98h]
0x180c63ce8  call    cs:__guard_dispatch_icall_fptr
0x180c63cee  cmp     byte ptr [rbp+0B0h+var_120], r15b
0x180c63cf2  jz      short loc_180C63D61
0x180c63cf4  mov     rcx, [r12+190h]
0x180c63cfc  mov     rax, [rcx]
0x180c63cff  lea     rdx, [rsp+1B0h+var_158+8]
0x180c63d04  mov     rax, [rax+0E8h]
0x180c63d0b  call    cs:__guard_dispatch_icall_fptr
0x180c63d11  nop
0x180c63d12  mov     r14, [rax]
0x180c63d15  mov     rax, [r14]
0x180c63d18  mov     rbx, [rax+0F8h]
0x180c63d1f  lea     rcx, [rbp+0B0h+var_128]
0x180c63d23  call    ??D?$_Optional_construct_base@V?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@@std@@QEHAA$$QEAV?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@XZ; std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(void)
0x180c63d28  mov     r8, rax
0x180c63d2b  mov     edx, 3
0x180c63d30  mov     rcx, r14
0x180c63d33  mov     rax, rbx
0x180c63d36  call    cs:__guard_dispatch_icall_fptr
0x180c63d3c  nop
0x180c63d3d  mov     rcx, qword ptr [rsp+1B0h+var_158+8]
0x180c63d42  test    rcx, rcx
0x180c63d45  jz      short loc_180C63D54
0x180c63d47  mov     rax, [rcx]
0x180c63d4a  mov     rax, [rax+10h]
0x180c63d4e  call    cs:__guard_dispatch_icall_fptr
0x180c63d54  mov     r14d, 4
0x180c63d5a  lea     rbx, off_1811FD050
0x180c63d61  mov     rax, [rdi]
0x180c63d64  mov     rcx, rdi
0x180c63d67  mov     rax, [rax+50h]
0x180c63d6b  call    cs:__guard_dispatch_icall_fptr
0x180c63d71  mov     rcx, rax
0x180c63d74  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180c63d7a  mov     rcx, rdi
0x180c63d7d  test    al, al
0x180c63d7f  jz      short loc_180C63DB7
0x180c63d81  mov     rax, [r12]
0x180c63d85  mov     rbx, [rax+60h]
0x180c63d89  mov     rax, [rdi]
0x180c63d8c  mov     rax, [rax+50h]
0x180c63d90  call    cs:__guard_dispatch_icall_fptr
0x180c63d96  mov     rcx, rax; this
0x180c63d99  call    ?Win32ErrorCodeFromCsiOrCellError@Jot@@YAKAEBVexception_ptr@std@@@Z; Jot::Win32ErrorCodeFromCsiOrCellError(std::exception_ptr const &)
0x180c63d9e  mov     edx, eax
0x180c63da0  mov     r8d, 105A61Bh
0x180c63da6  lea     rcx, [rbp+0B0h+var_B8]
0x180c63daa  call    ?CreateWin32ExceptionTag@Jot@@YA?AVexception_ptr@std@@KK@Z; Jot::CreateWin32ExceptionTag(ulong,ulong)
0x180c63daf  mov     rdx, rax
0x180c63db2  jmp     loc_180C641CD
0x180c63db7  mov     rax, [rdi]
0x180c63dba  mov     rax, [rax+70h]
0x180c63dbe  call    cs:__guard_dispatch_icall_fptr
0x180c63dc4  test    al, al
0x180c63dc6  jz      loc_180C640DE
0x180c63dcc  mov     rax, [rdi]
0x180c63dcf  mov     rcx, rdi
0x180c63dd2  mov     rax, [rax+60h]
0x180c63dd6  call    cs:__guard_dispatch_icall_fptr
0x180c63ddc  test    rax, rax
0x180c63ddf  jz      loc_180C640DE
0x180c63de5  mov     al, [r12+0B1h]
0x180c63ded  test    al, al
0x180c63def  jz      short loc_180C63E15
0x180c63df1  mov     rax, [r12]
0x180c63df5  mov     rbx, [rax+60h]
0x180c63df9  mov     edx, 105A61Ch
0x180c63dfe  lea     rcx, [rbp+0B0h+var_88]
0x180c63e02  call    ??0ErrAbortedCurrentOperation@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(Jot::ExceptionTag)
0x180c63e07  mov     rdx, rax
0x180c63e0a  lea     rcx, [rbp+0B0h+var_B8]
0x180c63e0e  call    ??$make_exception_ptr@UErrAbortedCurrentOperation@Jot@@@std@@YA?AVexception_ptr@0@UErrAbortedCurrentOperation@Jot@@@Z; std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(Jot::ErrAbortedCurrentOperation)
0x180c63e13  jmp     short loc_180C63DAF
0x180c63e15  xorps   xmm0, xmm0
0x180c63e18  movdqu  [rbp+0B0h+var_118], xmm0
0x180c63e1d  lea     rcx, [rbp+0B0h+var_118]
0x180c63e21  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180c63e27  nop
0x180c63e28  mov     [rbp+0B0h+var_108], r15
0x180c63e2c  lea     rcx, [rbp+0B0h+var_108]
0x180c63e30  call    cs:__imp_HrCreateEditorsTableXmlManager
0x180c63e36  test    eax, eax
0x180c63e38  jns     loc_180C63F05
0x180c63e3e  mov     r8d, 105A61Dh
0x180c63e44  mov     edx, eax
0x180c63e46  lea     rcx, [rbp+0B0h+var_B8]
0x180c63e4a  call    ?CreateHRESULTExceptionTag@Jot@@YA?AVexception_ptr@std@@JK@Z; Jot::CreateHRESULTExceptionTag(long,ulong)
0x180c63e4f  mov     rdx, rax
0x180c63e52  lea     rcx, [rbp+0B0h+var_118]
0x180c63e56  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180c63e5c  lea     rcx, [rbp+0B0h+var_B8]
0x180c63e60  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180c63e66  xor     r8d, r8d
0x180c63e69  lea     rdx, [rbp+0B0h+var_118]
0x180c63e6d  lea     rcx, [rbp+0B0h+var_88]
0x180c63e71  call    ?ToErrorData@Jot@@YA?AVErrorData@Logging@1@AEBVexception_ptr@std@@H@Z; Jot::ToErrorData(std::exception_ptr const &,int)
0x180c63e76  mov     qword ptr [rbp+0B0h+var_128], rbx
0x180c63e7a  lea     rax, aHrcreateeditor_0; "HrCreateEditorsTableXmlManagerFailed"
0x180c63e81  mov     [rbp+0B0h+var_120], rax
0x180c63e85  lea     r8, [rbp+0B0h+var_88]; struct Mso::Telemetry::EventName *
0x180c63e89  lea     rdx, [rbp+0B0h+var_128]; unsigned int
0x180c63e8d  mov     ecx, 1E3CC322h; this
0x180c63e92  call    ?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@AEBVErrorData@12@@Z; Jot::Logging::LogUnexpectedTag(ulong,Mso::Telemetry::EventName const &,Jot::Logging::ErrorData const &)
0x180c63e97  lea     rcx, [rbp+0B0h+var_68]
0x180c63e9b  call    ??1?$_Optional_destruct_base@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::string,0>::~_Optional_destruct_base<std::string,0>(void)
0x180c63ea0  mov     rax, [r12]
0x180c63ea4  mov     rbx, [rax+60h]
0x180c63ea8  xorps   xmm0, xmm0
0x180c63eab  movdqu  [rsp+1B0h+var_158+8], xmm0
0x180c63eb1  lea     rdx, [rbp+0B0h+var_118]
0x180c63eb5  lea     rcx, [rsp+1B0h+var_158+8]
0x180c63eba  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180c63ec0  lea     rdx, [rsp+1B0h+var_158+8]
0x180c63ec5  mov     rcx, r12
0x180c63ec8  mov     rax, rbx
0x180c63ecb  call    cs:__guard_dispatch_icall_fptr
0x180c63ed1  nop
0x180c63ed2  mov     rcx, [rbp+0B0h+var_108]
0x180c63ed6  test    rcx, rcx
0x180c63ed9  jz      short loc_180C63EE9
0x180c63edb  mov     rax, [rcx]
0x180c63ede  mov     rax, [rax+8]
0x180c63ee2  call    cs:__guard_dispatch_icall_fptr
0x180c63ee8  nop
0x180c63ee9  lea     rcx, [rbp+0B0h+var_118]
0x180c63eed  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180c63ef3  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x180c63efb  movdqu  [rbp+0B0h+var_118], xmm0
0x180c63f00  jmp     loc_180C641DA
0x180c63f05  mov     rbx, [rbp+0B0h+var_108]
0x180c63f09  mov     rax, [rbx]
0x180c63f0c  mov     r15, [rax+10h]
0x180c63f10  mov     rax, [rdi]
0x180c63f13  mov     rcx, rdi
0x180c63f16  mov     rax, [rax+60h]
0x180c63f1a  call    cs:__guard_dispatch_icall_fptr
0x180c63f20  mov     rdx, rax
0x180c63f23  mov     rcx, [rax]
0x180c63f26  mov     rax, [rcx+78h]
0x180c63f2a  mov     rcx, rdx
0x180c63f2d  call    cs:__guard_dispatch_icall_fptr
0x180c63f33  mov     r14, rax
0x180c63f36  mov     rcx, [rdi]
0x180c63f39  mov     rax, [rcx+88h]
0x180c63f40  mov     rcx, rdi
0x180c63f43  call    cs:__guard_dispatch_icall_fptr
0x180c63f49  lea     r9, [r12+208h]
0x180c63f51  mov     r8, r14
0x180c63f54  mov     rdx, rax
0x180c63f57  mov     rcx, rbx
0x180c63f5a  mov     rax, r15
  ... truncated ...
```
