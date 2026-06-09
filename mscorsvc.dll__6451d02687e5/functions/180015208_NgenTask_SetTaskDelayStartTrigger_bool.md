# NgenTask::SetTaskDelayStartTrigger(bool)

- ea: `0x180015208`
- end: `0x180015de3`
- name: `?SetTaskDelayStartTrigger@NgenTask@@YAJ_N@Z`
- size: `3035`
- prototype: `__int64 __fastcall(NgenTask *__hidden this, bool)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008500`
- `0x180016fd4`
- `0x1800288f0`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x180013fec`
- `0x18001406c`
- `0x180015208`
- `0x180016a9c`
- `0x1800171a8`
- `0x180030568`
- `0x180030d84`
- `0x180032654`
- `0x1800366a8`
- `0x18003dc30`
- `0x18003e8f0`
- `0x18003f280`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x180015909`
- `KERNEL32!FileTimeToSystemTime` at `0x180015909`
- `KERNEL32!GetLastError` at `0x180015808`
- `KERNEL32!GetLastError` at `0x180015808`
- `KERNEL32!GetSystemTime` at `0x1800157e8`
- `KERNEL32!GetSystemTime` at `0x1800157e8`
- `KERNEL32!SystemTimeToFileTime` at `0x1800157fa`
- `KERNEL32!SystemTimeToFileTime` at `0x1800157fa`
- `ole32!CoCreateInstance` at `0x180015337`
- `ole32!CoCreateInstance` at `0x180015337`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b49`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b49`
- `OLEAUT32!__imp_VariantInit` at `0x180015363`
- `OLEAUT32!__imp_VariantInit` at `0x180015387`
- `OLEAUT32!__imp_VariantInit` at `0x1800153ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800153d1`
- `OLEAUT32!__imp_VariantInit` at `0x180015363`
- `OLEAUT32!__imp_VariantInit` at `0x180015387`
- `OLEAUT32!__imp_VariantInit` at `0x1800153ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800153d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001546f`
- `OLEAUT32!__imp_VariantClear` at `0x18001547a`
- `OLEAUT32!__imp_VariantClear` at `0x180015488`
- `OLEAUT32!__imp_VariantClear` at `0x180015493`
- `OLEAUT32!__imp_VariantClear` at `0x180015744`
- `OLEAUT32!__imp_VariantClear` at `0x18001585c`
- `OLEAUT32!__imp_VariantClear` at `0x180015c8a`
- `OLEAUT32!__imp_VariantClear` at `0x180015c98`
- `OLEAUT32!__imp_VariantClear` at `0x18001546f`
- `OLEAUT32!__imp_VariantClear` at `0x18001547a`
- `OLEAUT32!__imp_VariantClear` at `0x180015488`
- `OLEAUT32!__imp_VariantClear` at `0x180015493`
- `OLEAUT32!__imp_VariantClear` at `0x180015744`
- `OLEAUT32!__imp_VariantClear` at `0x18001585c`
- `OLEAUT32!__imp_VariantClear` at `0x180015c8a`
- `OLEAUT32!__imp_VariantClear` at `0x180015c98`

## pseudocode

```c
// Hidden C++ exception states: #wind=116
__int64 __fastcall NgenTask::SetTaskDelayStartTrigger(NgenTask *this, __int64 a2, bool a3)
{
  char v3; // r12
  bool v4; // dl
  int started; // ebx
  NgenTask *v6; // rcx
  LONG v7; // r14d
  int v8; // eax
  LPVOID v9; // rbx
  _bstr_t *v10; // rax
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdi
  unsigned __int16 *v14; // r15
  _bstr_t *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdi
  int v19; // eax
  __int64 v20; // rdi
  int v21; // esi
  int v22; // eax
  __int64 *v23; // rdi
  __int64 v24; // rbx
  unsigned int v25; // eax
  int v26; // eax
  bool v27; // dl
  signed int LastError; // eax
  _FILETIME v29; // rbx
  __int64 *v30; // rbx
  int v31; // eax
  __int64 v32; // rdi
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  _bstr_t *v36; // rax
  __int64 v37; // rdx
  __int128 v38; // xmm2
  IRecordInfo *v39; // xmm3_8
  __int64 v40; // rbx
  _bstr_t *v41; // rax
  __int64 v42; // rdx
  int v43; // eax
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  IRecordInfo *p_SystemTime; // [rsp+60h] [rbp-A8h] BYREF
  bool v47[8]; // [rsp+68h] [rbp-A0h] BYREF
  _FILETIME FileTime; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v49; // [rsp+78h] [rbp-90h] BYREF
  int v50; // [rsp+80h] [rbp-88h]
  int v51; // [rsp+88h] [rbp-80h] BYREF
  LPVOID v52; // [rsp+90h] [rbp-78h] BYREF
  int v53; // [rsp+98h] [rbp-70h]
  __int64 v54; // [rsp+A0h] [rbp-68h] BYREF
  int v55; // [rsp+A8h] [rbp-60h]
  __int64 v56; // [rsp+B0h] [rbp-58h] BYREF
  int v57; // [rsp+B8h] [rbp-50h]
  __int64 v58; // [rsp+C0h] [rbp-48h] BYREF
  int v59; // [rsp+C8h] [rbp-40h]
  __int64 v60; // [rsp+D0h] [rbp-38h] BYREF
  int v61; // [rsp+D8h] [rbp-30h]
  __int64 v62; // [rsp+E0h] [rbp-28h] BYREF
  int v63; // [rsp+E8h] [rbp-20h]
  IRecordInfo *pRecInfo; // [rsp+F0h] [rbp-18h]
  VARIANTARG v65; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v66; // [rsp+118h] [rbp+10h] BYREF
  _DWORD v67[2]; // [rsp+138h] [rbp+30h] BYREF
  int v68; // [rsp+140h] [rbp+38h]
  unsigned __int16 *v69; // [rsp+148h] [rbp+40h]
  VARIANTARG pvarg; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG v71; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG v72; // [rsp+190h] [rbp+88h] BYREF
  __int128 v73; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v74; // [rsp+1B8h] [rbp+B0h]
  VARIANTARG v75; // [rsp+1C8h] [rbp+C0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+1E8h] [rbp+E0h] BYREF
  _FILETIME v77; // [rsp+1F8h] [rbp+F0h]
  int v78; // [rsp+208h] [rbp+100h] BYREF
  __int64 v79; // [rsp+20Ch] [rbp+104h]
  void *lpMem; // [rsp+218h] [rbp+110h]
  __int16 v81; // [rsp+220h] [rbp+118h] BYREF

  v3 = (char)this;
  v52 = 0;
  v53 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  v56 = 0;
  v57 = 0;
  v49 = 0;
  v50 = 0;
  v54 = 0;
  v55 = 0;
  v60 = 0;
  v61 = 0;
  if ( (_BYTE)this )
  {
    if ( NgenTask::IsTaskPaused(this) )
    {
      started = 0;
      goto LABEL_111;
    }
    if ( !CLRConfig::GetConfigValue(
            (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGenTaskDelayStartAmount,
            v4,
            v47) )
    {
      started = NgenTask::StartTask(v6);
      goto LABEL_111;
    }
  }
  v67[0] = 2;
  v67[1] = 2;
  v68 = 16;
  v69 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  NgenTask::GetTaskName((NgenTask *)v67, 0, a3);
  p_SystemTime = (IRecordInfo *)&v52;
  if ( v53 )
  {
    if ( v52 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = 0;
  }
  v52 = 0;
  v7 = 1;
  started = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v52);
  v8 = v53;
  if ( v52 )
    v8 = 1;
  v53 = v8;
  if ( started >= 0 )
  {
    VariantInit(&pvarg);
    SystemTime = *(_SYSTEMTIME *)&pvarg.vt;
    FileTime = (_FILETIME)pvarg.pRecInfo;
    VariantInit(&v75);
    v73 = *(_OWORD *)&v75.vt;
    pRecInfo = v75.pRecInfo;
    VariantInit(&v71);
    *(_OWORD *)&v65.vt = *(_OWORD *)&v71.vt;
    p_SystemTime = v71.pRecInfo;
    VariantInit(&v72);
    v77 = FileTime;
    v74 = pRecInfo;
    v65.pRecInfo = p_SystemTime;
    v66 = v72;
    started = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, __int128 *, _SYSTEMTIME *))(*(_QWORD *)v52 + 80LL))(
                v52,
                &v66,
                &v65,
                &v73,
                &SystemTime);
    VariantClear(&v72);
    VariantClear(&v71);
    VariantClear(&v75);
    VariantClear(&pvarg);
    if ( started >= 0 )
    {
      v9 = v52;
      pRecInfo = (IRecordInfo *)&v58;
      if ( v59 )
      {
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v59 = 0;
      }
      v58 = 0;
      v10 = _bstr_t::_bstr_t((_bstr_t *)&p_SystemTime, L"\\Microsoft\\Windows\\.NET Framework");
      if ( *(_QWORD *)v10 )
        v11 = **(_QWORD **)v10;
      else
        v11 = 0;
      started = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v9 + 56LL))(v9, v11, &v58);
      _bstr_t::~_bstr_t((_bstr_t *)&p_SystemTime);
      v12 = v59;
      v13 = v58;
      if ( v58 )
        v12 = 1;
      v59 = v12;
      if ( started >= 0 )
      {
        pRecInfo = (IRecordInfo *)&v62;
        if ( v63 )
        {
          if ( v62 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          v63 = 0;
        }
        v62 = 0;
        SString::ConvertToUnicode((SString *)v67);
        v14 = v69;
        v15 = _bstr_t::_bstr_t((_bstr_t *)&p_SystemTime, v69);
        if ( *(_QWORD *)v15 )
          v16 = **(_QWORD **)v15;
        else
          v16 = 0;
        started = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v13 + 104LL))(v13, v16, &v62);
        _bstr_t::~_bstr_t((_bstr_t *)&p_SystemTime);
        v17 = v63;
        v18 = v62;
        if ( v62 )
          v17 = 1;
        v63 = v17;
        if ( started < 0 )
          goto LABEL_109;
        p_SystemTime = (IRecordInfo *)&v56;
        if ( v57 )
        {
          if ( v56 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          v57 = 0;
        }
        v56 = 0;
        started = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 152LL))(v18, &v56);
        v19 = v57;
        v20 = v56;
        if ( v56 )
          v19 = 1;
        v57 = v19;
        if ( started < 0 )
          goto LABEL_109;
        p_SystemTime = (IRecordInfo *)&v49;
        if ( v50 )
        {
          if ( v49 )
            (*(void (__fastcall **)(__int64 *))(*v49 + 16))(v49);
          v50 = 0;
        }
        v49 = 0;
        started = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v20 + 72LL))(v20, &v49);
        v21 = 0;
        v22 = v50;
        if ( v49 )
          v22 = 1;
        v50 = v22;
        if ( started < 0 )
          goto LABEL_109;
        v51 = 0;
        started = (*(__int64 (__fastcall **)(__int64 *, int *))(*v49 + 56))(v49, &v51);
        if ( started < 0 )
          goto LABEL_109;
        if ( v51 >= 1 )
        {
          while ( 1 )
          {
            *(_DWORD *)&SystemTime.wHour = 0;
            v23 = v49;
            p_SystemTime = (IRecordInfo *)&SystemTime;
            *(_QWORD *)&SystemTime.wYear = 0;
            pvarg.vt = 3;
            pvarg.lVal = v7;
            v24 = *v49;
            v25 = _variant_t::operator long(&pvarg);
            started = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _SYSTEMTIME *))(v24 + 64))(v23, v25, &SystemTime);
            VariantClear(&pvarg);
            v21 &= ~0x20u;
            v26 = *(_DWORD *)&SystemTime.wHour;
            if ( *(_QWORD *)&SystemTime.wYear )
              v26 = 1;
            *(_DWORD *)&SystemTime.wHour = v26;
            if ( started < 0 )
              goto LABEL_66;
            started = (*(__int64 (__fastcall **)(_QWORD, _FILETIME *))(**(_QWORD **)&SystemTime.wYear + 56LL))(
                        *(_QWORD *)&SystemTime.wYear,
                        &FileTime);
            if ( started < 0 )
              goto LABEL_66;
            if ( FileTime.dwLowDateTime == 1 )
              break;
            if ( *(_DWORD *)&SystemTime.wHour )
            {
              if ( *(_QWORD *)&SystemTime.wYear )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SystemTime.wYear + 16LL))(*(_QWORD *)&SystemTime.wYear);
              *(_DWORD *)&SystemTime.wHour = 0;
            }
            if ( ++v7 > v51 )
              goto LABEL_60;
          }
          v65.vt = 3;
          v65.lVal = v7;
          v66 = v65;
          started = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(*v49 + 88))(v49, &v66);
          VariantClear(&v65);
          if ( started < 0 )
          {
LABEL_66:
            if ( *(_DWORD *)&SystemTime.wHour )
            {
              if ( *(_QWORD *)&SystemTime.wYear )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SystemTime.wYear + 16LL))(*(_QWORD *)&SystemTime.wYear);
              *(_DWORD *)&SystemTime.wHour = 0;
            }
            goto LABEL_109;
          }
          if ( *(_DWORD *)&SystemTime.wHour )
          {
            if ( *(_QWORD *)&SystemTime.wYear )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SystemTime.wYear + 16LL))(*(_QWORD *)&SystemTime.wYear);
            *(_DWORD *)&SystemTime.wHour = 0;
          }
        }
LABEL_60:
        if ( v3 )
        {
          GetSystemTime(&SystemTime);
          if ( !SystemTimeToFileTime(&SystemTime, &FileTime)
            || (v29 = FileTime,
                FileTime = (_FILETIME)(10000000LL
                                     * CLRConfig::GetConfigValue(
                                         (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGenTaskDelayStartAmount,
                                         v27,
                                         v47)
                                     + *(_QWORD *)&v29),
                !FileTimeToSystemTime(&FileTime, &SystemTime)) )
          {
            LastError = GetLastError();
            started = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              started = LastError;
            goto LABEL_109;
          }
          v79 = 512;
          lpMem = &v81;
          v78 = 2;
          v81 = 0;
          LODWORD(ppv) = SystemTime.wDay;
          SString::Printf(
            (SString *)&v78,
            L"%04hu-%02hu-%02huT%02hu:%02hu:%02huZ",
            SystemTime.wYear,
            SystemTime.wMonth,
            ppv,
            SystemTime.wHour,
            SystemTime.wMinute,
            SystemTime.wSecond);
          v30 = v49;
          p_SystemTime = (IRecordInfo *)&v54;
          if ( v55 )
          {
            if ( v54 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            v55 = 0;
          }
          v54 = 0;
          started = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v30 + 80))(v30, 1, &v54);
          v31 = v55;
          v32 = v54;
          if ( v54 )
            v31 = 1;
          v55 = v31;
          if ( started < 0 )
            goto LABEL_84;
          SString::ConvertToUnicode((SString *)&v78);
          v33 = _bstr_t::_bstr_t((_bstr_t *)&p_SystemTime, (const unsigned __int16 *)lpMem);
          v34 = *(_QWORD *)v33 ? **(_QWORD **)v33 : 0LL;
          started = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 120LL))(v32, v34);
          _bstr_t::~_bstr_t((_bstr_t *)&p_SystemTime);
          if ( started < 0
            || ((v35 = v54, v36 = _bstr_t::_bstr_t((_bstr_t *)&p_SystemTime, L"DelayStartTrigger1"), !*(_QWORD *)v36)
              ? (v37 = 0)
              : (v37 = **(_QWORD **)v36),
                started = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 72LL))(v35, v37),
                _bstr_t::~_bstr_t((_bstr_t *)&p_SystemTime),
                started < 0) )
          {
LABEL_84:
            if ( (v79 & 0x800000000LL) != 0 )
              operator delete(lpMem);
            goto LABEL_109;
          }
          if ( (v79 & 0x800000000LL) != 0 )
            operator delete(lpMem);
        }
        v66.vt = 0;
        v72.vt = 8;
        v72.llVal = (LONGLONG)SysAllocString(&psz);
        if ( v72.llVal )
        {
          v73 = *(_OWORD *)&v72.vt;
          pRecInfo = v72.pRecInfo;
          v71.vt = 8;
          v71.llVal = (LONGLONG)SysAllocString(L"SYSTEM");
          if ( v71.llVal )
          {
            v38 = *(_OWORD *)&v71.vt;
            *(_OWORD *)&v65.vt = *(_OWORD *)&v71.vt;
            v39 = v71.pRecInfo;
            p_SystemTime = v71.pRecInfo;
            v40 = v58;
            *(_QWORD *)&SystemTime.wYear = &v60;
            if ( v61 )
            {
              if ( v60 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                v38 = *(_OWORD *)&v65.vt;
                v39 = p_SystemTime;
              }
              v61 = 0;
            }
            v60 = 0;
            *(_OWORD *)&pvarg.vt = v73;
            pvarg.pRecInfo = pRecInfo;
            v75 = v66;
            *(_OWORD *)&v66.vt = v38;
            v66.pRecInfo = v39;
            SString::ConvertToUnicode((SString *)v67);
            v14 = v69;
            v41 = _bstr_t::_bstr_t((_bstr_t *)&FileTime, v69);
            if ( *(_QWORD *)v41 )
              v42 = **(_QWORD **)v41;
            else
              v42 = 0;
            started = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v40 + 136LL))(
                        v40,
                        v42,
                        v56,
                        6,
                        &v66,
                        &v75,
                        5,
                        &pvarg,
                        &v60);
            _bstr_t::~_bstr_t((_bstr_t *)&FileTime);
            v43 = v61;
            if ( v60 )
              v43 = 1;
            v61 = v43;
            VariantClear(&v71);
            VariantClear(&v72);
            goto LABEL_109;
          }
          _com_issue_error(2147942414LL);
        }
        _com_issue_error(2147942414LL);
        JUMPOUT(0x180015DE2LL);
      }
    }
  }
  v14 = v69;
LABEL_109:
  if ( (v68 & 8) != 0 )
    operator delete(v14);
LABEL_111:
  if ( v61 )
  {
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = 0;
  }
  if ( v55 )
  {
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v55 = 0;
  }
  if ( v50 )
  {
    if ( v49 )
      (*(void (__fastcall **)(__int64 *))(*v49 + 16))(v49);
    v50 = 0;
  }
  if ( v57 )
  {
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v57 = 0;
  }
  if ( v63 )
  {
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v63 = 0;
  }
  if ( v59 )
  {
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v59 = 0;
  }
  if ( v53 )
  {
    if ( v52 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = 0;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180015208  mov     rax, rsp
0x18001520b  mov     [rax+8], rbx
0x18001520f  mov     [rax+10h], rsi
0x180015213  mov     [rax+18h], rdi
0x180015217  push    rbp
0x180015218  push    r12
0x18001521a  push    r13
0x18001521c  push    r14
0x18001521e  push    r15
0x180015220  lea     rbp, [rax-358h]
0x180015227  sub     rsp, 430h
0x18001522e  mov     rax, cs:__security_cookie
0x180015235  xor     rax, rsp
0x180015238  mov     [rbp+350h+var_30], rax
0x18001523f  mov     r12b, cl
0x180015242  xor     r13d, r13d
0x180015245  mov     dword ptr [rsp+450h+var_400], r13d
0x18001524a  mov     [rbp+350h+var_3C8], r13
0x18001524e  mov     [rbp+350h+var_3C0], r13d
0x180015252  mov     [rbp+350h+var_398], r13
0x180015256  mov     [rbp+350h+var_390], r13d
0x18001525a  mov     [rbp+350h+var_378], r13
0x18001525e  mov     [rbp+350h+var_370], r13d
0x180015262  mov     [rbp+350h+var_3A8], r13
0x180015266  mov     [rbp+350h+var_3A0], r13d
0x18001526a  mov     [rsp+450h+var_3E0], r13
0x18001526f  mov     [rsp+450h+var_3D8], r13d
0x180015274  mov     [rbp+350h+var_3B8], r13
0x180015278  mov     [rbp+350h+var_3B0], r13d
0x18001527c  mov     [rbp+350h+var_388], r13
0x180015280  mov     [rbp+350h+var_380], r13d
0x180015284  test    cl, cl
0x180015286  jz      short loc_1800152BA
0x180015288  call    ?IsTaskPaused@NgenTask@@YA_NXZ; NgenTask::IsTaskPaused(void)
0x18001528d  test    al, al
0x18001528f  jz      short loc_180015299
0x180015291  mov     ebx, r13d
0x180015294  jmp     loc_180015CB8
0x180015299  lea     r8, [rsp+450h+var_3F0]; bool *
0x18001529e  lea     rcx, ?INTERNAL_NGenTaskDelayStartAmount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800152a5  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800152aa  test    eax, eax
0x1800152ac  jnz     short loc_1800152BA
0x1800152ae  call    ?StartTask@NgenTask@@YAJXZ; NgenTask::StartTask(void)
0x1800152b3  mov     ebx, eax
0x1800152b5  jmp     loc_180015CB8
0x1800152ba  mov     edi, 2
0x1800152bf  mov     [rbp+350h+var_320], edi
0x1800152c2  mov     [rbp+350h+var_31C], edi
0x1800152c5  mov     [rbp+350h+var_318], 10h
0x1800152cc  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x1800152d3  mov     [rbp+350h+var_310], rax
0x1800152d7  xor     edx, edx; struct SString *
0x1800152d9  lea     rcx, [rbp+350h+var_320]; this
0x1800152dd  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x1800152e2  nop
0x1800152e3  lea     rax, [rbp+350h+var_3C8]
0x1800152e7  mov     [rsp+450h+var_3F8], rax
0x1800152ec  cmp     [rbp+350h+var_3C0], r13d
0x1800152f0  jz      short loc_18001530C
0x1800152f2  mov     rcx, [rbp+350h+var_3C8]
0x1800152f6  test    rcx, rcx
0x1800152f9  jz      short loc_180015308
0x1800152fb  mov     rax, [rcx]
0x1800152fe  mov     rax, [rax+10h]
0x180015302  call    cs:__guard_dispatch_icall_fptr
0x180015308  mov     [rbp+350h+var_3C0], r13d
0x18001530c  mov     [rbp+350h+var_3C8], r13
0x180015310  mov     r14d, 1
0x180015316  mov     dword ptr [rsp+450h+var_400], r14d
0x18001531b  lea     rax, [rbp+350h+var_3C8]
0x18001531f  mov     [rsp+450h+ppv], rax; ppv
0x180015324  lea     r9, IID_ITaskService; riid
0x18001532b  mov     r8d, r14d; dwClsContext
0x18001532e  xor     edx, edx; pUnkOuter
0x180015330  lea     rcx, CLSID_TaskScheduler; rclsid
0x180015337  call    cs:__imp_CoCreateInstance
0x18001533d  mov     ebx, eax
0x18001533f  mov     esi, r14d
0x180015342  and     esi, 0FFFFFFFEh
0x180015345  mov     dword ptr [rsp+450h+var_400], esi
0x180015349  mov     eax, [rbp+350h+var_3C0]
0x18001534c  cmp     [rbp+350h+var_3C8], r13
0x180015350  cmovnz  eax, r14d
0x180015354  mov     [rbp+350h+var_3C0], eax
0x180015357  test    ebx, ebx
0x180015359  js      loc_180015CA0
0x18001535f  lea     rcx, [rbp+350h+pvarg]; pvarg
0x180015363  call    cs:__imp_VariantInit
0x180015369  nop
0x18001536a  movups  xmm0, xmmword ptr [rbp+350h+pvarg]
0x18001536e  movups  xmmword ptr [rbp+350h+SystemTime.wYear], xmm0
0x180015375  movsd   xmm0, qword ptr [rbp+350h+pvarg+10h]
0x18001537a  movsd   qword ptr [rsp+450h+FileTime.dwLowDateTime], xmm0
0x180015380  lea     rcx, [rbp+350h+var_290]; pvarg
0x180015387  call    cs:__imp_VariantInit
0x18001538d  nop
0x18001538e  movups  xmm0, xmmword ptr [rbp+350h+var_290]
0x180015395  movups  [rbp+350h+var_2B0], xmm0
0x18001539c  movsd   xmm0, qword ptr [rbp+350h+var_290+10h]
0x1800153a4  movsd   [rbp+350h+var_368], xmm0
0x1800153a9  lea     rcx, [rbp+350h+var_2E0]; pvarg
0x1800153ad  call    cs:__imp_VariantInit
0x1800153b3  nop
0x1800153b4  movups  xmm0, xmmword ptr [rbp+350h+var_2E0]
0x1800153b8  movups  xmmword ptr [rbp+350h+var_360], xmm0
0x1800153bc  movsd   xmm0, qword ptr [rbp+350h+var_2E0+10h]
0x1800153c4  movsd   [rsp+450h+var_3F8], xmm0
0x1800153ca  lea     rcx, [rbp+350h+var_2C8]; pvarg
0x1800153d1  call    cs:__imp_VariantInit
0x1800153d7  nop
0x1800153d8  movups  xmm0, xmmword ptr [rbp+350h+SystemTime.wYear]
0x1800153df  movaps  xmmword ptr [rbp+350h+SystemTime.wYear], xmm0
0x1800153e6  movsd   xmm0, qword ptr [rsp+450h+FileTime.dwLowDateTime]
0x1800153ec  movsd   [rbp+350h+var_260], xmm0
0x1800153f4  movups  xmm0, [rbp+350h+var_2B0]
0x1800153fb  movaps  [rbp+350h+var_2B0], xmm0
0x180015402  movsd   xmm0, [rbp+350h+var_368]
0x180015407  movsd   [rbp+350h+var_2A0], xmm0
0x18001540f  movups  xmm0, xmmword ptr [rbp+350h+var_360]
0x180015413  movaps  xmmword ptr [rbp+350h+var_360], xmm0
0x180015417  movsd   xmm0, [rsp+450h+var_3F8]
0x18001541d  movsd   qword ptr [rbp+350h+var_360+10h], xmm0
0x180015422  movups  xmm0, xmmword ptr [rbp+350h+var_2C8]
0x180015429  movaps  [rbp+350h+var_340], xmm0
0x18001542d  movsd   xmm1, qword ptr [rbp+350h+var_2C8+10h]
0x180015435  movsd   [rbp+350h+var_330], xmm1
0x18001543a  mov     rcx, [rbp+350h+var_3C8]
0x18001543e  mov     rax, [rcx]
0x180015441  lea     rdx, [rbp+350h+SystemTime]
0x180015448  mov     [rsp+450h+ppv], rdx
0x18001544d  lea     r9, [rbp+350h+var_2B0]
0x180015454  lea     r8, [rbp+350h+var_360]
0x180015458  lea     rdx, [rbp+350h+var_340]
0x18001545c  mov     rax, [rax+50h]
0x180015460  call    cs:__guard_dispatch_icall_fptr
0x180015466  mov     ebx, eax
0x180015468  lea     rcx, [rbp+350h+var_2C8]; pvarg
0x18001546f  call    cs:__imp_VariantClear
0x180015475  nop
0x180015476  lea     rcx, [rbp+350h+var_2E0]; pvarg
0x18001547a  call    cs:__imp_VariantClear
0x180015480  nop
0x180015481  lea     rcx, [rbp+350h+var_290]; pvarg
0x180015488  call    cs:__imp_VariantClear
0x18001548e  nop
0x18001548f  lea     rcx, [rbp+350h+pvarg]; pvarg
0x180015493  call    cs:__imp_VariantClear
0x180015499  test    ebx, ebx
0x18001549b  js      loc_180015CA0
0x1800154a1  mov     rbx, [rbp+350h+var_3C8]
0x1800154a5  lea     rax, [rbp+350h+var_398]
0x1800154a9  mov     [rbp+350h+var_368], rax
0x1800154ad  cmp     [rbp+350h+var_390], r13d
0x1800154b1  jz      short loc_1800154CD
0x1800154b3  mov     rcx, [rbp+350h+var_398]
0x1800154b7  test    rcx, rcx
0x1800154ba  jz      short loc_1800154C9
0x1800154bc  mov     rax, [rcx]
0x1800154bf  mov     rax, [rax+10h]
0x1800154c3  call    cs:__guard_dispatch_icall_fptr
0x1800154c9  mov     [rbp+350h+var_390], r13d
0x1800154cd  mov     [rbp+350h+var_398], r13
0x1800154d1  or      esi, edi
0x1800154d3  mov     dword ptr [rsp+450h+var_400], esi
0x1800154d7  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x1800154de  lea     rcx, [rsp+450h+var_3F8]; this
0x1800154e3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800154e8  nop
0x1800154e9  mov     rcx, [rax]
0x1800154ec  test    rcx, rcx
0x1800154ef  jz      short loc_1800154F6
0x1800154f1  mov     rdx, [rcx]
0x1800154f4  jmp     short loc_1800154F9
0x1800154f6  mov     rdx, r13
0x1800154f9  mov     rax, [rbx]
0x1800154fc  lea     r8, [rbp+350h+var_398]
0x180015500  mov     rcx, rbx
0x180015503  mov     rax, [rax+38h]
0x180015507  call    cs:__guard_dispatch_icall_fptr
0x18001550d  mov     ebx, eax
0x18001550f  lea     rcx, [rsp+450h+var_3F8]; this
0x180015514  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180015519  and     esi, 0FFFFFFFDh
0x18001551c  mov     dword ptr [rsp+450h+var_400], esi
0x180015520  mov     eax, [rbp+350h+var_390]
0x180015523  mov     rdi, [rbp+350h+var_398]
0x180015527  test    rdi, rdi
0x18001552a  cmovnz  eax, r14d
0x18001552e  mov     [rbp+350h+var_390], eax
0x180015531  test    ebx, ebx
0x180015533  js      loc_180015CA0
0x180015539  lea     rax, [rbp+350h+var_378]
0x18001553d  mov     [rbp+350h+var_368], rax
0x180015541  cmp     [rbp+350h+var_370], r13d
0x180015545  jz      short loc_180015561
0x180015547  mov     rcx, [rbp+350h+var_378]
0x18001554b  test    rcx, rcx
0x18001554e  jz      short loc_18001555D
0x180015550  mov     rax, [rcx]
0x180015553  mov     rax, [rax+10h]
0x180015557  call    cs:__guard_dispatch_icall_fptr
0x18001555d  mov     [rbp+350h+var_370], r13d
0x180015561  mov     [rbp+350h+var_378], r13
0x180015565  or      esi, 4
0x180015568  mov     dword ptr [rsp+450h+var_400], esi
0x18001556c  lea     rcx, [rbp+350h+var_320]; this
0x180015570  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180015575  mov     r15, [rbp+350h+var_310]
0x180015579  mov     rdx, r15; unsigned __int16 *
0x18001557c  lea     rcx, [rsp+450h+var_3F8]; this
0x180015581  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180015586  nop
0x180015587  mov     rcx, [rax]
0x18001558a  test    rcx, rcx
0x18001558d  jz      short loc_180015594
0x18001558f  mov     rdx, [rcx]
0x180015592  jmp     short loc_180015597
0x180015594  mov     rdx, r13
0x180015597  mov     rax, [rdi]
0x18001559a  lea     r8, [rbp+350h+var_378]
0x18001559e  mov     rcx, rdi
0x1800155a1  mov     rax, [rax+68h]
0x1800155a5  call    cs:__guard_dispatch_icall_fptr
0x1800155ab  mov     ebx, eax
0x1800155ad  lea     rcx, [rsp+450h+var_3F8]; this
0x1800155b2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800155b7  and     esi, 0FFFFFFFBh
0x1800155ba  mov     dword ptr [rsp+450h+var_400], esi
0x1800155be  mov     eax, [rbp+350h+var_370]
0x1800155c1  mov     rdi, [rbp+350h+var_378]
0x1800155c5  test    rdi, rdi
0x1800155c8  cmovnz  eax, r14d
0x1800155cc  mov     [rbp+350h+var_370], eax
0x1800155cf  test    ebx, ebx
0x1800155d1  js      loc_180015CA4
0x1800155d7  lea     rax, [rbp+350h+var_3A8]
0x1800155db  mov     [rsp+450h+var_3F8], rax
0x1800155e0  cmp     [rbp+350h+var_3A0], r13d
0x1800155e4  jz      short loc_180015600
0x1800155e6  mov     rcx, [rbp+350h+var_3A8]
0x1800155ea  test    rcx, rcx
0x1800155ed  jz      short loc_1800155FC
0x1800155ef  mov     rax, [rcx]
0x1800155f2  mov     rax, [rax+10h]
0x1800155f6  call    cs:__guard_dispatch_icall_fptr
0x1800155fc  mov     [rbp+350h+var_3A0], r13d
0x180015600  mov     [rbp+350h+var_3A8], r13
0x180015604  or      esi, 8
0x180015607  mov     dword ptr [rsp+450h+var_400], esi
0x18001560b  mov     rax, [rdi]
0x18001560e  lea     rdx, [rbp+350h+var_3A8]
0x180015612  mov     rcx, rdi
0x180015615  mov     rax, [rax+98h]
0x18001561c  call    cs:__guard_dispatch_icall_fptr
0x180015622  mov     ebx, eax
0x180015624  and     esi, 0FFFFFFF7h
0x180015627  mov     dword ptr [rsp+450h+var_400], esi
0x18001562b  mov     eax, [rbp+350h+var_3A0]
0x18001562e  mov     rdi, [rbp+350h+var_3A8]
0x180015632  test    rdi, rdi
0x180015635  cmovnz  eax, r14d
0x180015639  mov     [rbp+350h+var_3A0], eax
0x18001563c  test    ebx, ebx
0x18001563e  js      loc_180015CA4
0x180015644  lea     rax, [rsp+450h+var_3E0]
0x180015649  mov     [rsp+450h+var_3F8], rax
0x18001564e  cmp     [rsp+450h+var_3D8], r13d
0x180015653  jz      short loc_180015671
0x180015655  mov     rcx, [rsp+450h+var_3E0]
0x18001565a  test    rcx, rcx
0x18001565d  jz      short loc_18001566C
0x18001565f  mov     rax, [rcx]
0x180015662  mov     rax, [rax+10h]
0x180015666  call    cs:__guard_dispatch_icall_fptr
0x18001566c  mov     [rsp+450h+var_3D8], r13d
0x180015671  mov     [rsp+450h+var_3E0], r13
0x180015676  or      esi, 10h
0x180015679  mov     dword ptr [rsp+450h+var_400], esi
0x18001567d  mov     rax, [rdi]
0x180015680  lea     rdx, [rsp+450h+var_3E0]
0x180015685  mov     rcx, rdi
0x180015688  mov     rax, [rax+48h]
0x18001568c  call    cs:__guard_dispatch_icall_fptr
0x180015692  mov     ebx, eax
0x180015694  and     esi, 0FFFFFFEFh
0x180015697  mov     dword ptr [rsp+450h+var_400], esi
0x18001569b  mov     eax, [rsp+450h+var_3D8]
0x18001569f  mov     rcx, [rsp+450h+var_3E0]
0x1800156a4  test    rcx, rcx
0x1800156a7  cmovnz  eax, r14d
0x1800156ab  mov     [rsp+450h+var_3D8], eax
0x1800156af  test    ebx, ebx
0x1800156b1  js      loc_180015CA4
0x1800156b7  mov     [rbp+350h+var_3D0], r13d
0x1800156bb  mov     rax, [rcx]
0x1800156be  lea     rdx, [rbp+350h+var_3D0]
0x1800156c2  mov     rax, [rax+38h]
0x1800156c6  call    cs:__guard_dispatch_icall_fptr
0x1800156cc  mov     ebx, eax
  ... truncated ...
```
