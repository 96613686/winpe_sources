# ScheduleMigrator::CreateLogonTaskForUser(ushort const *)

- ea: `0x18000ac08`
- end: `0x18000bdf8`
- name: `?CreateLogonTaskForUser@ScheduleMigrator@@QEAAJPEBG@Z`
- size: `4592`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008940`

## callees

- `0x1800022e0`
- `0x180007720`
- `0x180007b38`
- `0x18000977c`
- `0x18000aa2c`
- `0x18000ab84`
- `0x18000ac08`
- `0x1800117c8`
- `0x180016b88`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bab9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bab9`
- `OLEAUT32!__imp_VariantInit` at `0x18000ba69`
- `OLEAUT32!__imp_VariantInit` at `0x18000ba8b`
- `OLEAUT32!__imp_VariantInit` at `0x18000ba69`
- `OLEAUT32!__imp_VariantInit` at `0x18000ba8b`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbaa`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbb9`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbc8`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbaa`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbb9`
- `OLEAUT32!__imp_VariantClear` at `0x18000bbc8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000adad`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ae9d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b817`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b92f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bca7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bd99`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000adad`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ae9d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b817`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b92f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bca7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bd99`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ac5c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ac5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b59f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b86b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b59f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b86b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b07c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b07c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b1b6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b1b6`

## string_xrefs

- `0x18000bae1`: `MDMMaintenenceTaskUser`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser(const unsigned __int16 **this, const unsigned __int16 *a2)
{
  BOOL v4; // edi
  const unsigned __int16 *v5; // r9
  int v6; // ebx
  struct ITaskDefinition *v8; // rbx
  signed int v9; // esi
  signed int LastError; // eax
  signed int v11; // eax
  unsigned __int64 v12; // r8
  __int64 *v13; // rsi
  __int64 v14; // r15
  const unsigned __int16 *p_Src; // rdx
  __int64 *v16; // rax
  __int64 v17; // rdx
  int v18; // esi
  const struct std::nothrow_t *v19; // rdx
  int v20; // esi
  int v21; // esi
  struct ITaskFolder *v22; // rsi
  struct ITaskFolderVtbl *lpVtbl; // r15
  __int128 v24; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v26; // xmm10
  IRecordInfo *v27; // xmm11_8
  __int128 v28; // xmm6
  IRecordInfo *v29; // xmm7_8
  __int64 *v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // r15d
  const struct std::nothrow_t *v33; // rdx
  _QWORD *v34; // [rsp+50h] [rbp-3D8h] BYREF
  __int64 *v35; // [rsp+58h] [rbp-3D0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-3C8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-3C0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-3B8h] BYREF
  struct ITaskFolder *v39; // [rsp+78h] [rbp-3B0h] BYREF
  __int64 v40; // [rsp+80h] [rbp-3A8h] BYREF
  PSID Sid; // [rsp+88h] [rbp-3A0h] BYREF
  BOOL v42; // [rsp+90h] [rbp-398h]
  int v43; // [rsp+98h] [rbp-390h] BYREF
  struct ITaskDefinition *v44; // [rsp+A0h] [rbp-388h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp-380h] BYREF
  DWORD cchReferencedDomainName; // [rsp+ACh] [rbp-37Ch] BYREF
  DWORD cchName; // [rsp+B0h] [rbp-378h] BYREF
  PSID *p_Sid; // [rsp+B8h] [rbp-370h]
  char v49; // [rsp+C0h] [rbp-368h]
  VARIANTARG v50; // [rsp+C8h] [rbp-360h] BYREF
  VARIANTARG v51; // [rsp+E0h] [rbp-348h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-330h] BYREF
  __int128 v53; // [rsp+110h] [rbp-318h] BYREF
  IRecordInfo *v54; // [rsp+120h] [rbp-308h]
  __int128 v55; // [rsp+130h] [rbp-2F8h] BYREF
  IRecordInfo *v56; // [rsp+140h] [rbp-2E8h]
  __int128 v57; // [rsp+150h] [rbp-2D8h] BYREF
  IRecordInfo *v58; // [rsp+160h] [rbp-2C8h]
  __int128 Src; // [rsp+170h] [rbp-2B8h] BYREF
  __int128 v60; // [rsp+180h] [rbp-2A8h]
  WCHAR ReferencedDomainName[128]; // [rsp+190h] [rbp-298h] BYREF
  WCHAR Name[128]; // [rsp+290h] [rbp-198h] BYREF

  v4 = CoInitializeEx(0, 0) >= 0;
  v42 = v4;
  v44 = 0;
  v36 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  v37 = 0;
  v34 = 0;
  Sid = 0;
  cchName = 128;
  cchReferencedDomainName = 128;
  peUse = 0;
  v6 = CreateTaskForUser(*this, &v44, &v39, v5, a2);
  if ( v6 < 0 )
  {
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v44 )
      ((void (__fastcall *)(struct ITaskDefinition *))v44->lpVtbl->Release)(v44);
    if ( v4 )
      CoUninitialize();
    return (unsigned int)v6;
  }
  v8 = v44;
  v9 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v44->lpVtbl->get_Triggers)(v44, &v36);
  if ( v9 < 0 )
  {
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
LABEL_24:
    if ( v4 )
      CoUninitialize();
    return (unsigned int)v9;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 80LL))(v36, 9, &v38);
  if ( v9 < 0 )
  {
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v38)(v38, &IID_ILogonTrigger, &v35);
  if ( v9 < 0 )
  {
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  p_Sid = &Sid;
  v49 = 1;
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    LocalFree(Sid);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  v9 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v8->lpVtbl->get_Settings)(v8, &v37);
  if ( v9 < 0 )
  {
    LocalFree(Sid);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))v37)(
         v37,
         &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
         &v34);
  if ( v9 < 0 )
  {
    LocalFree(Sid);
    if ( v34 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 16LL))(v34, *v34);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v34 + 208LL))(v34, 0xFFFFFFFFLL);
  if ( v9 < 0 )
  {
    LocalFree(Sid);
    if ( v34 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 16LL))(v34, *v34);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v34 + 176LL))(v34, 0xFFFFFFFFLL);
  if ( v9 < 0 )
  {
    LocalFree(Sid);
    if ( v34 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 16LL))(v34, *v34);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    goto LABEL_24;
  }
  Src = 0;
  v60 = 0;
  v12 = -1;
  do
    ++v12;
  while ( ReferencedDomainName[v12] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, ReferencedDomainName, v12);
  std::wstring::append(&Src, L"\\");
  std::wstring::append(&Src, Name);
  v13 = v35;
  v14 = *v35;
  p_Src = (const unsigned __int16 *)&Src;
  if ( *((_QWORD *)&v60 + 1) > 7u )
    p_Src = (const unsigned __int16 *)Src;
  v16 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v43, p_Src);
  if ( v16 )
    v17 = *v16;
  else
    v17 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v14 + 184))(v13, v17);
  _bstr_t::~_bstr_t((_bstr_t *)&v43, v19);
  if ( v18 >= 0 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v35 + 152))(v35, 0xFFFFFFFFLL);
    if ( v20 >= 0 )
    {
      v21 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64))v8->lpVtbl->put_Triggers)(v8, v36);
      if ( v21 >= 0 )
      {
        v22 = v39;
        lpVtbl = v39->lpVtbl;
        VariantInit(&pvarg);
        v24 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v51);
        v26 = *(_OWORD *)&v51.vt;
        v27 = v51.pRecInfo;
        v50.vt = 8;
        v50.llVal = (LONGLONG)SysAllocString(L"S-1-5-18");
        if ( !v50.llVal )
          _com_issue_error(-2147024882);
        v28 = *(_OWORD *)&v50.vt;
        v29 = v50.pRecInfo;
        v30 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&v43, L"MDMMaintenenceTaskUser");
        if ( v30 )
          v31 = *v30;
        else
          v31 = 0;
        v53 = v24;
        v54 = pRecInfo;
        v55 = v26;
        v56 = v27;
        v57 = v28;
        v58 = v29;
        v32 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct ITaskDefinition *, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))lpVtbl->RegisterTaskDefinition)(
                v22,
                v31,
                v8,
                6,
                &v57,
                &v55,
                3,
                &v53,
                &v40);
        _bstr_t::~_bstr_t((_bstr_t *)&v43, v33);
        VariantClear(&v50);
        VariantClear(&v51);
        VariantClear(&pvarg);
        std::wstring::~wstring((char **)&Src);
        LocalFree(Sid);
        if ( v34 )
          (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v35 )
          (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        if ( v22 )
          ((void (__fastcall *)(struct ITaskFolder *))v22->lpVtbl->Release)(v22);
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        if ( v8 )
          ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
        if ( v4 )
          CoUninitialize();
        return v32;
      }
      else
      {
        std::wstring::~wstring((char **)&Src);
        v49 = 0;
        LocalFree(Sid);
        if ( v34 )
          (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v35 )
          (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        if ( v39 )
          ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        if ( v8 )
          ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
        if ( v4 )
        {
          CoUninitialize();
          v42 = 0;
        }
        return (unsigned int)v21;
      }
    }
    else
    {
      std::wstring::~wstring((char **)&Src);
      v49 = 0;
      LocalFree(Sid);
      if ( v34 )
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v35 )
        (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v39 )
        ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v8 )
        ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
      if ( v4 )
      {
        CoUninitialize();
        v42 = 0;
      }
      return (unsigned int)v20;
    }
  }
  else
  {
    std::wstring::~wstring((char **)&Src);
    v49 = 0;
    LocalFree(Sid);
    if ( v34 )
      (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v39 )
      ((void (__fastcall *)(struct ITaskFolder *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v8 )
      ((void (__fastcall *)(struct ITaskDefinition *))v8->lpVtbl->Release)(v8);
    if ( v4 )
    {
      CoUninitialize();
      v42 = 0;
    }
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x18000ac08  mov     rax, rsp
0x18000ac0b  mov     [rax+18h], rbx
0x18000ac0f  push    rsi
0x18000ac10  push    rdi
0x18000ac11  push    r12
0x18000ac13  push    r14
0x18000ac15  push    r15
0x18000ac17  sub     rsp, 400h
0x18000ac1e  movaps  xmmword ptr [rax-38h], xmm6
0x18000ac22  movaps  xmmword ptr [rax-48h], xmm7
0x18000ac26  movaps  xmmword ptr [rax-58h], xmm8
0x18000ac2b  movaps  xmmword ptr [rax-68h], xmm9
0x18000ac30  movaps  xmmword ptr [rax-78h], xmm10
0x18000ac35  movaps  xmmword ptr [rax-88h], xmm11
0x18000ac3d  mov     rax, cs:__security_cookie
0x18000ac44  xor     rax, rsp
0x18000ac47  mov     [rsp+428h+var_98], rax
0x18000ac4f  mov     r15, rdx
0x18000ac52  mov     rbx, rcx
0x18000ac55  xor     r14d, r14d
0x18000ac58  xor     edx, edx; dwCoInit
0x18000ac5a  xor     ecx, ecx; pvReserved
0x18000ac5c  call    cs:__imp_CoInitializeEx
0x18000ac62  mov     edi, r14d
0x18000ac65  lea     r12d, [r14+1]
0x18000ac69  test    eax, eax
0x18000ac6b  cmovns  edi, r12d
0x18000ac6f  mov     [rsp+428h+var_398], edi
0x18000ac76  mov     [rsp+428h+var_388], r14
0x18000ac7e  mov     [rsp+428h+var_3C8], r14
0x18000ac83  mov     [rsp+428h+var_3A8], r14
0x18000ac8b  mov     [rsp+428h+var_3B0], r14
0x18000ac90  mov     [rsp+428h+var_3B8], r14
0x18000ac95  mov     [rsp+428h+var_3D0], r14
0x18000ac9a  mov     [rsp+428h+var_3C0], r14
0x18000ac9f  mov     [rsp+428h+var_3D8], r14
0x18000aca4  mov     [rsp+428h+Sid], r14
0x18000acac  lea     eax, [r12+7Fh]
0x18000acb1  mov     [rsp+428h+cchName], eax
0x18000acb8  mov     [rsp+428h+var_37C], eax
0x18000acbf  mov     [rsp+428h+var_380], r14d
0x18000acc7  mov     [rsp+428h+ReferencedDomainName], r15; unsigned __int16 *
0x18000accc  lea     r8, [rsp+428h+var_3B0]; struct ITaskFolder **
0x18000acd1  lea     rdx, [rsp+428h+var_388]; struct ITaskDefinition **
0x18000acd9  mov     rcx, [rbx]; unsigned __int16 *
0x18000acdc  call    ?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z; CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)
0x18000ace1  mov     ebx, eax
0x18000ace3  test    eax, eax
0x18000ace5  jns     loc_18000ADBA
0x18000aceb  mov     rcx, [rsp+428h+var_3D8]
0x18000acf0  test    rcx, rcx
0x18000acf3  jz      short loc_18000AD02
0x18000acf5  mov     rdx, [rcx]
0x18000acf8  mov     rax, [rdx+10h]
0x18000acfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad01  nop
0x18000ad02  mov     rcx, [rsp+428h+var_3C0]
0x18000ad07  test    rcx, rcx
0x18000ad0a  jz      short loc_18000AD19
0x18000ad0c  mov     rax, [rcx]
0x18000ad0f  mov     rax, [rax+10h]
0x18000ad13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad18  nop
0x18000ad19  mov     rcx, [rsp+428h+var_3D0]
0x18000ad1e  test    rcx, rcx
0x18000ad21  jz      short loc_18000AD30
0x18000ad23  mov     rax, [rcx]
0x18000ad26  mov     rax, [rax+10h]
0x18000ad2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2f  nop
0x18000ad30  mov     rcx, [rsp+428h+var_3B8]
0x18000ad35  test    rcx, rcx
0x18000ad38  jz      short loc_18000AD47
0x18000ad3a  mov     rax, [rcx]
0x18000ad3d  mov     rax, [rax+10h]
0x18000ad41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad46  nop
0x18000ad47  mov     rcx, [rsp+428h+var_3B0]
0x18000ad4c  test    rcx, rcx
0x18000ad4f  jz      short loc_18000AD5E
0x18000ad51  mov     rax, [rcx]
0x18000ad54  mov     rax, [rax+10h]
0x18000ad58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5d  nop
0x18000ad5e  mov     rcx, [rsp+428h+var_3A8]
0x18000ad66  test    rcx, rcx
0x18000ad69  jz      short loc_18000AD78
0x18000ad6b  mov     rax, [rcx]
0x18000ad6e  mov     rax, [rax+10h]
0x18000ad72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad77  nop
0x18000ad78  mov     rcx, [rsp+428h+var_3C8]
0x18000ad7d  test    rcx, rcx
0x18000ad80  jz      short loc_18000AD8F
0x18000ad82  mov     rax, [rcx]
0x18000ad85  mov     rax, [rax+10h]
0x18000ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad8e  nop
0x18000ad8f  mov     rcx, [rsp+428h+var_388]
0x18000ad97  test    rcx, rcx
0x18000ad9a  jz      short loc_18000ADA9
0x18000ad9c  mov     rax, [rcx]
0x18000ad9f  mov     rax, [rax+10h]
0x18000ada3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada8  nop
0x18000ada9  test    edi, edi
0x18000adab  jz      short loc_18000ADB3
0x18000adad  call    cs:__imp_CoUninitialize
0x18000adb3  mov     eax, ebx
0x18000adb5  jmp     loc_18000BDA6
0x18000adba  mov     rbx, [rsp+428h+var_388]
0x18000adc2  mov     rax, [rbx]
0x18000adc5  lea     rdx, [rsp+428h+var_3C8]
0x18000adca  mov     rcx, rbx
0x18000adcd  mov     rax, [rax+48h]
0x18000add1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000add6  mov     esi, eax
0x18000add8  test    eax, eax
0x18000adda  jns     loc_18000AEAA
0x18000ade0  mov     rcx, [rsp+428h+var_3D8]
0x18000ade5  test    rcx, rcx
0x18000ade8  jz      short loc_18000ADF7
0x18000adea  mov     rdx, [rcx]
0x18000aded  mov     rax, [rdx+10h]
0x18000adf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf6  nop
0x18000adf7  mov     rcx, [rsp+428h+var_3C0]
0x18000adfc  test    rcx, rcx
0x18000adff  jz      short loc_18000AE0E
0x18000ae01  mov     rax, [rcx]
0x18000ae04  mov     rax, [rax+10h]
0x18000ae08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae0d  nop
0x18000ae0e  mov     rcx, [rsp+428h+var_3D0]
0x18000ae13  test    rcx, rcx
0x18000ae16  jz      short loc_18000AE25
0x18000ae18  mov     rax, [rcx]
0x18000ae1b  mov     rax, [rax+10h]
0x18000ae1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae24  nop
0x18000ae25  mov     rcx, [rsp+428h+var_3B8]
0x18000ae2a  test    rcx, rcx
0x18000ae2d  jz      short loc_18000AE3C
0x18000ae2f  mov     rax, [rcx]
0x18000ae32  mov     rax, [rax+10h]
0x18000ae36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3b  nop
0x18000ae3c  mov     rcx, [rsp+428h+var_3B0]
0x18000ae41  test    rcx, rcx
0x18000ae44  jz      short loc_18000AE53
0x18000ae46  mov     rax, [rcx]
0x18000ae49  mov     rax, [rax+10h]
0x18000ae4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae52  nop
0x18000ae53  mov     rcx, [rsp+428h+var_3A8]
0x18000ae5b  test    rcx, rcx
0x18000ae5e  jz      short loc_18000AE6D
0x18000ae60  mov     rax, [rcx]
0x18000ae63  mov     rax, [rax+10h]
0x18000ae67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae6c  nop
0x18000ae6d  mov     rcx, [rsp+428h+var_3C8]
0x18000ae72  test    rcx, rcx
0x18000ae75  jz      short loc_18000AE84
0x18000ae77  mov     rax, [rcx]
0x18000ae7a  mov     rax, [rax+10h]
0x18000ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae83  nop
0x18000ae84  test    rbx, rbx
0x18000ae87  jz      short loc_18000AE99
0x18000ae89  mov     rax, [rbx]
0x18000ae8c  mov     rcx, rbx
0x18000ae8f  mov     rax, [rax+10h]
0x18000ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae98  nop
0x18000ae99  test    edi, edi
0x18000ae9b  jz      short loc_18000AEA3
0x18000ae9d  call    cs:__imp_CoUninitialize
0x18000aea3  mov     eax, esi
0x18000aea5  jmp     loc_18000BDA6
0x18000aeaa  mov     rcx, [rsp+428h+var_3C8]
0x18000aeaf  mov     rax, [rcx]
0x18000aeb2  lea     r8, [rsp+428h+var_3B8]
0x18000aeb7  mov     edx, 9
0x18000aebc  mov     rax, [rax+50h]
0x18000aec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec5  mov     esi, eax
0x18000aec7  test    eax, eax
0x18000aec9  jns     loc_18000AF8D
0x18000aecf  mov     rcx, [rsp+428h+var_3D8]
0x18000aed4  test    rcx, rcx
0x18000aed7  jz      short loc_18000AEE6
0x18000aed9  mov     rdx, [rcx]
0x18000aedc  mov     rax, [rdx+10h]
0x18000aee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee5  nop
0x18000aee6  mov     rcx, [rsp+428h+var_3C0]
0x18000aeeb  test    rcx, rcx
0x18000aeee  jz      short loc_18000AEFD
0x18000aef0  mov     rax, [rcx]
0x18000aef3  mov     rax, [rax+10h]
0x18000aef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefc  nop
0x18000aefd  mov     rcx, [rsp+428h+var_3D0]
0x18000af02  test    rcx, rcx
0x18000af05  jz      short loc_18000AF14
0x18000af07  mov     rax, [rcx]
0x18000af0a  mov     rax, [rax+10h]
0x18000af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af13  nop
0x18000af14  mov     rcx, [rsp+428h+var_3B8]
0x18000af19  test    rcx, rcx
0x18000af1c  jz      short loc_18000AF2B
0x18000af1e  mov     rax, [rcx]
0x18000af21  mov     rax, [rax+10h]
0x18000af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2a  nop
0x18000af2b  mov     rcx, [rsp+428h+var_3B0]
0x18000af30  test    rcx, rcx
0x18000af33  jz      short loc_18000AF42
0x18000af35  mov     rax, [rcx]
0x18000af38  mov     rax, [rax+10h]
0x18000af3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af41  nop
0x18000af42  mov     rcx, [rsp+428h+var_3A8]
0x18000af4a  test    rcx, rcx
0x18000af4d  jz      short loc_18000AF5C
0x18000af4f  mov     rax, [rcx]
0x18000af52  mov     rax, [rax+10h]
0x18000af56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af5b  nop
0x18000af5c  mov     rcx, [rsp+428h+var_3C8]
0x18000af61  test    rcx, rcx
0x18000af64  jz      short loc_18000AF73
0x18000af66  mov     rax, [rcx]
0x18000af69  mov     rax, [rax+10h]
0x18000af6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af72  nop
0x18000af73  test    rbx, rbx
0x18000af76  jz      short loc_18000AF88
0x18000af78  mov     rax, [rbx]
0x18000af7b  mov     rcx, rbx
0x18000af7e  mov     rax, [rax+10h]
0x18000af82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af87  nop
0x18000af88  jmp     loc_18000AE99
0x18000af8d  mov     rcx, [rsp+428h+var_3B8]
0x18000af92  mov     rax, [rcx]
0x18000af95  lea     r8, [rsp+428h+var_3D0]
0x18000af9a  lea     rdx, IID_ILogonTrigger
0x18000afa1  mov     rax, [rax]
0x18000afa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa9  mov     esi, eax
0x18000afab  test    eax, eax
0x18000afad  jns     loc_18000B071
0x18000afb3  mov     rcx, [rsp+428h+var_3D8]
0x18000afb8  test    rcx, rcx
0x18000afbb  jz      short loc_18000AFCA
0x18000afbd  mov     rdx, [rcx]
0x18000afc0  mov     rax, [rdx+10h]
0x18000afc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afc9  nop
0x18000afca  mov     rcx, [rsp+428h+var_3C0]
0x18000afcf  test    rcx, rcx
0x18000afd2  jz      short loc_18000AFE1
0x18000afd4  mov     rax, [rcx]
0x18000afd7  mov     rax, [rax+10h]
0x18000afdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe0  nop
0x18000afe1  mov     rcx, [rsp+428h+var_3D0]
0x18000afe6  test    rcx, rcx
0x18000afe9  jz      short loc_18000AFF8
0x18000afeb  mov     rax, [rcx]
0x18000afee  mov     rax, [rax+10h]
0x18000aff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff7  nop
0x18000aff8  mov     rcx, [rsp+428h+var_3B8]
0x18000affd  test    rcx, rcx
0x18000b000  jz      short loc_18000B00F
0x18000b002  mov     rax, [rcx]
0x18000b005  mov     rax, [rax+10h]
0x18000b009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00e  nop
0x18000b00f  mov     rcx, [rsp+428h+var_3B0]
0x18000b014  test    rcx, rcx
0x18000b017  jz      short loc_18000B026
0x18000b019  mov     rax, [rcx]
0x18000b01c  mov     rax, [rax+10h]
0x18000b020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b025  nop
0x18000b026  mov     rcx, [rsp+428h+var_3A8]
0x18000b02e  test    rcx, rcx
0x18000b031  jz      short loc_18000B040
0x18000b033  mov     rax, [rcx]
0x18000b036  mov     rax, [rax+10h]
0x18000b03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03f  nop
0x18000b040  mov     rcx, [rsp+428h+var_3C8]
0x18000b045  test    rcx, rcx
0x18000b048  jz      short loc_18000B057
  ... truncated ...
```
