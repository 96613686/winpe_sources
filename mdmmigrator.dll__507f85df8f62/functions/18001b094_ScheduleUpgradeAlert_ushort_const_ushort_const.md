# ScheduleUpgradeAlert(ushort const *,ushort const *)

- ea: `0x18001b094`
- end: `0x18001ba03`
- name: `?ScheduleUpgradeAlert@@YAJPEBG0@Z`
- size: `2415`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008940`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180006294`
- `0x180006c98`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180012b58`
- `0x180012ed4`
- `0x18001b094`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001b486`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001b486`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b7a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b7a8`
- `OLEAUT32!__imp_VariantInit` at `0x18001b771`
- `OLEAUT32!__imp_VariantInit` at `0x18001b786`
- `OLEAUT32!__imp_VariantInit` at `0x18001b7ca`
- `OLEAUT32!__imp_VariantInit` at `0x18001b771`
- `OLEAUT32!__imp_VariantInit` at `0x18001b786`
- `OLEAUT32!__imp_VariantInit` at `0x18001b7ca`
- `OLEAUT32!__imp_VariantClear` at `0x18001b880`
- `OLEAUT32!__imp_VariantClear` at `0x18001b88f`
- `OLEAUT32!__imp_VariantClear` at `0x18001b899`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8a3`
- `OLEAUT32!__imp_VariantClear` at `0x18001b880`
- `OLEAUT32!__imp_VariantClear` at `0x18001b88f`
- `OLEAUT32!__imp_VariantClear` at `0x18001b899`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b938`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b9ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b938`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001b9ac`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b0f2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b0f2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001b497`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001b497`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001b4d5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001b4d5`

## string_xrefs

- `0x18001b1c7`: `%windir%\system32\deviceenroller.exe `
- `0x18001b7e6`: `Migration alert created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleUpgradeAlert(unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT v4; // eax
  signed int v5; // ebx
  int v7; // eax
  int Task; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  signed int LastError; // eax
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64); // rdi
  _bstr_t *v21; // rax
  __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, __int64); // rdi
  _bstr_t *v26; // rax
  __int64 v27; // rdx
  const struct std::nothrow_t *v28; // rdx
  __int64 *v29; // rdi
  __int64 v30; // r14
  __int128 v31; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v33; // xmm10
  IRecordInfo *v34; // xmm11_8
  VARIANTARG *v35; // rax
  char v36; // bl
  __int128 v37; // xmm6
  IRecordInfo *v38; // xmm7_8
  __int64 v39; // rsi
  _bstr_t *v40; // rax
  __int64 v41; // rdx
  int v42; // edi
  const struct std::nothrow_t *v43; // rdx
  int v44[2]; // [rsp+78h] [rbp-90h] BYREF
  int v45[2]; // [rsp+80h] [rbp-88h] BYREF
  int v46[2]; // [rsp+88h] [rbp-80h] BYREF
  int v47[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v48; // [rsp+98h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  struct _FILETIME FileTime; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v54; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v55; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v57; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v58; // [rsp+128h] [rbp+20h]
  __int128 v59; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v60; // [rsp+148h] [rbp+40h]
  int v61[4]; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v62; // [rsp+168h] [rbp+60h]
  VARIANTARG v63; // [rsp+178h] [rbp+70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+190h] [rbp+88h] BYREF
  unsigned __int16 v65[264]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v66[264]; // [rsp+3B8h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+660h] [rbp+558h]

  v44[0] = 0;
  v4 = CoInitializeEx(0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE64,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4);
    return (unsigned int)v5;
  }
  *(_QWORD *)v47 = 0;
  *(_QWORD *)v46 = 0;
  *(_QWORD *)v44 = 0;
  *(_QWORD *)v45 = 0;
  v7 = StringCchPrintfW(v66, 0x104u, L"/MigrationAlert /s %s", a1);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6C,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v7);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
    goto LABEL_8;
  }
  Task = CreateTask(
           v47,
           (__int64 *)v46,
           v44,
           v45,
           a1,
           L"%windir%\\system32\\deviceenroller.exe ",
           v66,
           a2,
           1u,
           0,
           1,
           1,
           0);
  v5 = Task;
  if ( Task < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6E,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)Task);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
    goto LABEL_8;
  }
  v48 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v44 + 72LL))(*(_QWORD *)v44, &v48);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE71,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v9);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v48);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
    goto LABEL_8;
  }
  v51 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 80LL))(v48, 7, &v51);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE74,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v10);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v51);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v48);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
    goto LABEL_8;
  }
  v50 = 0;
  v11 = (**v51)(v51, &IID_IRegistrationTrigger, &v50);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE77,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v11);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
LABEL_50:
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v51);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v48);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
LABEL_8:
    if ( *(_QWORD *)v47 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 16LL))(*(_QWORD *)v47);
LABEL_68:
    CoUninitialize();
    return (unsigned int)v5;
  }
  v12 = v50;
  v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 168LL);
  v14 = _bstr_t::_bstr_t((_bstr_t *)&v49, L"PT1M");
  if ( *(_QWORD *)v14 )
    v15 = **(_QWORD **)v14;
  else
    v15 = 0;
  v5 = v13(v12, v15);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v16);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE78,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    goto LABEL_50;
  }
  SystemTime = 0;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime)
    || (v49 = *(_QWORD *)&FileTime + 2400000000LL,
        *(_QWORD *)&FileTime += 2400000000LL,
        !FileTimeToSystemTime(&FileTime, &SystemTime)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7B,
        (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v5);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      goto LABEL_50;
    }
  }
  memset_0(v65, 0, 0x208u);
  v18 = CreateDelayTimeString(&SystemTime, v65);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7E,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v18);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    goto LABEL_50;
  }
  v19 = v50;
  v20 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 136LL);
  v21 = _bstr_t::_bstr_t((_bstr_t *)&v49, v65);
  if ( *(_QWORD *)v21 )
    v22 = **(_QWORD **)v21;
  else
    v22 = 0;
  v5 = v20(v19, v22);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v23);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7F,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    goto LABEL_50;
  }
  v24 = *(_QWORD *)v45;
  v25 = *(__int64 (__fastcall **)(__int64, __int64))(**(_QWORD **)v45 + 256LL);
  v26 = _bstr_t::_bstr_t((_bstr_t *)&v49, L"PT1M");
  if ( *(_QWORD *)v26 )
    v27 = **(_QWORD **)v26;
  else
    v27 = 0;
  v5 = v25(v24, v27);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v28);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE81,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    goto LABEL_50;
  }
  v53 = 0;
  v29 = *(__int64 **)v46;
  v30 = **(_QWORD **)v46;
  VariantInit(&pvarg);
  v31 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v55);
  v33 = *(_OWORD *)&v55.vt;
  v34 = v55.pRecInfo;
  if ( a2 )
  {
    v54.vt = 8;
    v54.llVal = (LONGLONG)SysAllocString(a2);
    if ( !v54.llVal )
      _com_issue_error(-2147024882);
    v35 = &v54;
    v36 = 1;
  }
  else
  {
    VariantInit(&v63);
    v35 = &v63;
    v36 = 2;
  }
  v37 = *(_OWORD *)&v35->vt;
  v38 = v35->pRecInfo;
  v39 = *(_QWORD *)v44;
  v40 = _bstr_t::_bstr_t((_bstr_t *)&v49, L"Migration alert created by enrollment client");
  if ( *(_QWORD *)v40 )
    v41 = **(_QWORD **)v40;
  else
    v41 = 0;
  v57 = v31;
  v58 = pRecInfo;
  v59 = v33;
  v60 = v34;
  *(_OWORD *)v61 = v37;
  v62 = v38;
  v42 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, int *, __int128 *, int, __int128 *, __int64 *))(v30 + 136))(
          v29,
          v41,
          v39,
          6,
          v61,
          &v59,
          3,
          &v57,
          &v53);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v43);
  if ( (v36 & 2) != 0 )
  {
    v36 &= ~2u;
    VariantClear(&v63);
  }
  if ( (v36 & 1) != 0 )
    VariantClear(&v54);
  VariantClear(&v55);
  VariantClear(&pvarg);
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE84,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v42);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v51);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v48);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
    if ( *(_QWORD *)v47 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 16LL))(*(_QWORD *)v47);
    v5 = v42;
    goto LABEL_68;
  }
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v53);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v51);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v48);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v45);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v46);
  if ( *(_QWORD *)v47 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 16LL))(*(_QWORD *)v47);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18001b094  mov     rax, rsp
0x18001b097  mov     [rax+18h], rbx
0x18001b09b  push    rbp
0x18001b09c  push    rsi
0x18001b09d  push    rdi
0x18001b09e  push    r14
0x18001b0a0  push    r15
0x18001b0a2  lea     rbp, [rax-558h]
0x18001b0a9  sub     rsp, 630h
0x18001b0b0  movaps  xmmword ptr [rax-38h], xmm6
0x18001b0b4  movaps  xmmword ptr [rax-48h], xmm7
0x18001b0b8  movaps  xmmword ptr [rax-58h], xmm8
0x18001b0bd  movaps  xmmword ptr [rax-68h], xmm9
0x18001b0c2  movaps  xmmword ptr [rax-78h], xmm10
0x18001b0c7  movaps  xmmword ptr [rax-88h], xmm11
0x18001b0cf  mov     rax, cs:__security_cookie
0x18001b0d6  xor     rax, rsp
0x18001b0d9  mov     [rbp+550h+var_90], rax
0x18001b0e0  mov     rsi, rdx
0x18001b0e3  mov     rdi, rcx
0x18001b0e6  xor     r15d, r15d
0x18001b0e9  mov     [rsp+650h+var_5E0], r15d
0x18001b0ee  xor     edx, edx; dwCoInit
0x18001b0f0  xor     ecx, ecx; pvReserved
0x18001b0f2  call    cs:__imp_CoInitializeEx
0x18001b0f8  mov     ebx, eax
0x18001b0fa  test    eax, eax
0x18001b0fc  jns     short loc_18001B120
0x18001b0fe  mov     rcx, [rbp+558h]; this
0x18001b105  mov     r9d, eax; char *
0x18001b108  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b10f  mov     edx, 0E64h; void *
0x18001b114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b119  mov     eax, ebx
0x18001b11b  jmp     loc_18001B9B4
0x18001b120  mov     qword ptr [rbp+550h+var_5C8], r15
0x18001b124  mov     qword ptr [rbp+550h+var_5D0], r15
0x18001b128  mov     qword ptr [rsp+650h+var_5E0], r15
0x18001b12d  mov     qword ptr [rsp+650h+var_5D8], r15
0x18001b132  mov     r9, rdi
0x18001b135  lea     r8, aMigrationalert; "/MigrationAlert /s %s"
0x18001b13c  mov     edx, 104h; unsigned __int64
0x18001b141  lea     rcx, [rbp+550h+var_2A0]; unsigned __int16 *
0x18001b148  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b14d  mov     ebx, eax
0x18001b14f  test    eax, eax
0x18001b151  jns     short loc_18001B194
0x18001b153  mov     rcx, [rbp+558h]; this
0x18001b15a  mov     r9d, eax; char *
0x18001b15d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b164  mov     edx, 0E6Ch; void *
0x18001b169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b16e  nop
0x18001b16f  lea     rcx, [rsp+650h+var_5D8]
0x18001b174  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b179  nop
0x18001b17a  lea     rcx, [rsp+650h+var_5E0]
0x18001b17f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b184  nop
0x18001b185  lea     rcx, [rbp+550h+var_5D0]
0x18001b189  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b18e  nop
0x18001b18f  jmp     loc_18001B231
0x18001b194  mov     [rsp+650h+var_5F0], r15d; int
0x18001b199  mov     [rsp+650h+var_5F8], 1; int
0x18001b1a1  mov     [rsp+650h+var_600], 1; int
0x18001b1a9  mov     [rsp+650h+var_608], r15d; int
0x18001b1ae  mov     [rsp+650h+var_610], 1; int
0x18001b1b6  mov     [rsp+650h+var_618], rsi; unsigned __int16 *
0x18001b1bb  lea     rax, [rbp+550h+var_2A0]
0x18001b1c2  mov     [rsp+650h+var_620], rax; unsigned __int16 *
0x18001b1c7  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x18001b1ce  mov     [rsp+650h+var_628], rax; unsigned __int16 *
0x18001b1d3  mov     [rsp+650h+var_630], rdi; int
0x18001b1d8  lea     r9, [rsp+650h+var_5D8]; int
0x18001b1dd  lea     r8, [rsp+650h+var_5E0]; int
0x18001b1e2  lea     rdx, [rbp+550h+var_5D0]; int
0x18001b1e6  lea     rcx, [rbp+550h+var_5C8]; int
0x18001b1ea  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18001b1ef  mov     ebx, eax
0x18001b1f1  test    eax, eax
0x18001b1f3  jns     short loc_18001B24F
0x18001b1f5  mov     rcx, [rbp+558h]; this
0x18001b1fc  mov     r9d, eax; char *
0x18001b1ff  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b206  mov     edx, 0E6Eh; void *
0x18001b20b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b210  nop
0x18001b211  lea     rcx, [rsp+650h+var_5D8]
0x18001b216  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b21b  nop
0x18001b21c  lea     rcx, [rsp+650h+var_5E0]
0x18001b221  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b226  nop
0x18001b227  lea     rcx, [rbp+550h+var_5D0]
0x18001b22b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b230  nop
0x18001b231  mov     rcx, qword ptr [rbp+550h+var_5C8]
0x18001b235  test    rcx, rcx
0x18001b238  jz      loc_18001B938
0x18001b23e  mov     rax, [rcx]
0x18001b241  mov     rax, [rax+10h]
0x18001b245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b24a  jmp     loc_18001B938
0x18001b24f  mov     [rbp+550h+var_5C0], r15
0x18001b253  mov     rcx, qword ptr [rsp+650h+var_5E0]
0x18001b258  mov     rax, [rcx]
0x18001b25b  lea     rdx, [rbp+550h+var_5C0]
0x18001b25f  mov     rax, [rax+48h]
0x18001b263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b268  mov     ebx, eax
0x18001b26a  test    eax, eax
0x18001b26c  jns     short loc_18001B2B9
0x18001b26e  mov     rcx, [rbp+558h]; this
0x18001b275  mov     r9d, eax; char *
0x18001b278  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b27f  mov     edx, 0E71h; void *
0x18001b284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b289  nop
0x18001b28a  lea     rcx, [rbp+550h+var_5C0]
0x18001b28e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b293  nop
0x18001b294  lea     rcx, [rsp+650h+var_5D8]
0x18001b299  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b29e  nop
0x18001b29f  lea     rcx, [rsp+650h+var_5E0]
0x18001b2a4  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b2a9  nop
0x18001b2aa  lea     rcx, [rbp+550h+var_5D0]
0x18001b2ae  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b2b3  nop
0x18001b2b4  jmp     loc_18001B231
0x18001b2b9  mov     [rbp+550h+var_5A8], r15
0x18001b2bd  mov     rcx, [rbp+550h+var_5C0]
0x18001b2c1  mov     rax, [rcx]
0x18001b2c4  lea     r8, [rbp+550h+var_5A8]
0x18001b2c8  mov     edx, 7
0x18001b2cd  mov     rax, [rax+50h]
0x18001b2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d6  mov     ebx, eax
0x18001b2d8  test    eax, eax
0x18001b2da  jns     short loc_18001B331
0x18001b2dc  mov     rcx, [rbp+558h]; this
0x18001b2e3  mov     r9d, eax; char *
0x18001b2e6  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b2ed  mov     edx, 0E74h; void *
0x18001b2f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b2f7  nop
0x18001b2f8  lea     rcx, [rbp+550h+var_5A8]
0x18001b2fc  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b301  nop
0x18001b302  lea     rcx, [rbp+550h+var_5C0]
0x18001b306  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b30b  nop
0x18001b30c  lea     rcx, [rsp+650h+var_5D8]
0x18001b311  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b316  nop
0x18001b317  lea     rcx, [rsp+650h+var_5E0]
0x18001b31c  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b321  nop
0x18001b322  lea     rcx, [rbp+550h+var_5D0]
0x18001b326  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b32b  nop
0x18001b32c  jmp     loc_18001B231
0x18001b331  mov     [rbp+550h+var_5B0], r15
0x18001b335  mov     rcx, [rbp+550h+var_5A8]
0x18001b339  mov     rax, [rcx]
0x18001b33c  lea     r8, [rbp+550h+var_5B0]
0x18001b340  lea     rdx, IID_IRegistrationTrigger
0x18001b347  mov     rax, [rax]
0x18001b34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b34f  mov     ebx, eax
0x18001b351  test    eax, eax
0x18001b353  jns     short loc_18001B3BF
0x18001b355  mov     rcx, [rbp+558h]; this
0x18001b35c  mov     r9d, eax; char *
0x18001b35f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b366  mov     edx, 0E77h; void *
0x18001b36b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b370  mov     rcx, [rbp+550h+var_5B0]
0x18001b374  test    rcx, rcx
0x18001b377  jz      short loc_18001B386
0x18001b379  mov     rdx, [rcx]
0x18001b37c  mov     rax, [rdx+10h]
0x18001b380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b385  nop
0x18001b386  lea     rcx, [rbp+550h+var_5A8]
0x18001b38a  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b38f  nop
0x18001b390  lea     rcx, [rbp+550h+var_5C0]
0x18001b394  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b399  nop
0x18001b39a  lea     rcx, [rsp+650h+var_5D8]
0x18001b39f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b3a4  nop
0x18001b3a5  lea     rcx, [rsp+650h+var_5E0]
0x18001b3aa  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b3af  nop
0x18001b3b0  lea     rcx, [rbp+550h+var_5D0]
0x18001b3b4  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b3b9  nop
0x18001b3ba  jmp     loc_18001B231
0x18001b3bf  mov     rbx, [rbp+550h+var_5B0]
0x18001b3c3  mov     rax, [rbx]
0x18001b3c6  mov     rdi, [rax+0A8h]
0x18001b3cd  lea     rdx, aPt1m; "PT1M"
0x18001b3d4  lea     rcx, [rbp+550h+var_5B8]; this
0x18001b3d8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b3dd  mov     rdx, [rax]
0x18001b3e0  test    rdx, rdx
0x18001b3e3  jz      short loc_18001B3EA
0x18001b3e5  mov     rdx, [rdx]
0x18001b3e8  jmp     short loc_18001B3ED
0x18001b3ea  mov     rdx, r15
0x18001b3ed  mov     rcx, rbx
0x18001b3f0  mov     rax, rdi
0x18001b3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3f8  mov     ebx, eax
0x18001b3fa  lea     rcx, [rbp+550h+var_5B8]; this
0x18001b3fe  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b403  test    ebx, ebx
0x18001b405  jns     short loc_18001B471
0x18001b407  mov     rcx, [rbp+558h]; this
0x18001b40e  mov     r9d, ebx; char *
0x18001b411  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b418  mov     edx, 0E78h; void *
0x18001b41d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b422  mov     rcx, [rbp+550h+var_5B0]
0x18001b426  test    rcx, rcx
0x18001b429  jz      short loc_18001B438
0x18001b42b  mov     rax, [rcx]
0x18001b42e  mov     rax, [rax+10h]
0x18001b432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b437  nop
0x18001b438  lea     rcx, [rbp+550h+var_5A8]
0x18001b43c  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b441  nop
0x18001b442  lea     rcx, [rbp+550h+var_5C0]
0x18001b446  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b44b  nop
0x18001b44c  lea     rcx, [rsp+650h+var_5D8]
0x18001b451  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b456  nop
0x18001b457  lea     rcx, [rsp+650h+var_5E0]
0x18001b45c  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b461  nop
0x18001b462  lea     rcx, [rbp+550h+var_5D0]
0x18001b466  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b46b  nop
0x18001b46c  jmp     loc_18001B231
0x18001b471  xorps   xmm0, xmm0
0x18001b474  movups  xmmword ptr [rbp+550h+SystemTime.wYear], xmm0
0x18001b47b  mov     qword ptr [rbp+550h+FileTime.dwLowDateTime], r15
0x18001b47f  lea     rcx, [rbp+550h+SystemTime]; lpSystemTime
0x18001b486  call    cs:__imp_GetSystemTime
0x18001b48c  lea     rdx, [rbp+550h+FileTime]; lpFileTime
0x18001b490  lea     rcx, [rbp+550h+SystemTime]; lpSystemTime
0x18001b497  call    cs:__imp_SystemTimeToFileTime
0x18001b49d  test    eax, eax
0x18001b49f  jz      short loc_18001B4E3
0x18001b4a1  mov     eax, [rbp+550h+FileTime.dwHighDateTime]
0x18001b4a4  mov     dword ptr [rbp+550h+var_5B8+4], eax
0x18001b4a7  mov     eax, [rbp+550h+FileTime.dwLowDateTime]
0x18001b4aa  mov     dword ptr [rbp+550h+var_5B8], eax
0x18001b4ad  mov     ecx, 8F0D1800h
0x18001b4b2  mov     rax, [rbp+550h+var_5B8]
0x18001b4b6  add     rax, rcx
0x18001b4b9  mov     [rbp+550h+var_5B8], rax
0x18001b4bd  shr     rax, 20h
0x18001b4c1  mov     [rbp+550h+FileTime.dwHighDateTime], eax
0x18001b4c4  mov     eax, dword ptr [rbp+550h+var_5B8]
0x18001b4c7  mov     [rbp+550h+FileTime.dwLowDateTime], eax
0x18001b4ca  lea     rdx, [rbp+550h+SystemTime]; lpSystemTime
0x18001b4d1  lea     rcx, [rbp+550h+FileTime]; lpFileTime
0x18001b4d5  call    cs:__imp_FileTimeToSystemTime
0x18001b4db  test    eax, eax
0x18001b4dd  jnz     loc_18001B566
0x18001b4e3  call    cs:__imp_GetLastError
0x18001b4e9  test    eax, eax
0x18001b4eb  mov     ebx, eax
0x18001b4ed  jle     short loc_18001B4F8
0x18001b4ef  movzx   ebx, ax
0x18001b4f2  or      ebx, 80070000h
0x18001b4f8  test    ebx, ebx
0x18001b4fa  jns     short loc_18001B566
0x18001b4fc  mov     rcx, [rbp+558h]; this
0x18001b503  mov     r9d, ebx; char *
0x18001b506  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001b50d  mov     edx, 0E7Bh; void *
0x18001b512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b517  mov     rcx, [rbp+550h+var_5B0]
0x18001b51b  test    rcx, rcx
0x18001b51e  jz      short loc_18001B52D
0x18001b520  mov     rax, [rcx]
0x18001b523  mov     rax, [rax+10h]
0x18001b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b52c  nop
0x18001b52d  lea     rcx, [rbp+550h+var_5A8]
0x18001b531  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001b536  nop
  ... truncated ...
```
