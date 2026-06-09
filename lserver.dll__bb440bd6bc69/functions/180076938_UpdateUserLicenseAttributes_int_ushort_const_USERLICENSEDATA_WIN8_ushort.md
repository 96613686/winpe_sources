# UpdateUserLicenseAttributes(int,ushort const *,USERLICENSEDATA_WIN8 *,ushort *)

- ea: `0x180076938`
- end: `0x1800772e9`
- name: `?UpdateUserLicenseAttributes@@YAJHPEBGPEAUUSERLICENSEDATA_WIN8@@PEAG@Z`
- size: `2481`
- prototype: `unsigned int __fastcall(int, const unsigned __int16 *, struct USERLICENSEDATA_WIN8 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180057958`

## callees

- `0x18000114c`
- `0x1800011d8`
- `0x1800012b0`
- `0x1800013c8`
- `0x18000d060`
- `0x180075980`
- `0x180075d6c`
- `0x180076938`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x180076984`
- `ole32!CoInitializeEx` at `0x180076984`
- `ole32!CoUninitialize` at `0x1800772b9`
- `ole32!CoUninitialize` at `0x1800772b9`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x1800769ea`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x1800769ea`
- `OLEAUT32!__imp_SysAllocString` at `0x180076ac5`
- `OLEAUT32!__imp_SysAllocString` at `0x180076bf6`
- `OLEAUT32!__imp_SysAllocString` at `0x180076d30`
- `OLEAUT32!__imp_SysAllocString` at `0x180076e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180076ac5`
- `OLEAUT32!__imp_SysAllocString` at `0x180076bf6`
- `OLEAUT32!__imp_SysAllocString` at `0x180076d30`
- `OLEAUT32!__imp_SysAllocString` at `0x180076e4e`
- `OLEAUT32!__imp_VariantInit` at `0x1800769b6`
- `OLEAUT32!__imp_VariantInit` at `0x1800769b6`
- `OLEAUT32!__imp_VariantClear` at `0x180076bce`
- `OLEAUT32!__imp_VariantClear` at `0x180076d07`
- `OLEAUT32!__imp_VariantClear` at `0x180076e3e`
- `OLEAUT32!__imp_VariantClear` at `0x180076f5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800771ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800772a4`
- `OLEAUT32!__imp_VariantClear` at `0x180076bce`
- `OLEAUT32!__imp_VariantClear` at `0x180076d07`
- `OLEAUT32!__imp_VariantClear` at `0x180076e3e`
- `OLEAUT32!__imp_VariantClear` at `0x180076f5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800771ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800772a4`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180076f8b`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180076f8b`
- `KERNEL32!FileTimeToSystemTime` at `0x180076f77`
- `KERNEL32!FileTimeToSystemTime` at `0x180076f77`

## string_xrefs

- `0x180076a14`: `ADsOpenObject() Failed for IID_IADs`
- `0x180076a9f`: `TLSUpdateUserObject: AD has new licensing attrs`
- `0x180076a0d`: `UpdateUserLicenseAttributes`
- `0x180076a7f`: `UpdateUserLicenseAttributes`
- `0x180076cc8`: `TLSUpdateUserObject: updated msTSLicenseVersion`
- `0x180077067`: `TLSUpdateUserObject: updated msTSExpireDate`
- `0x180076ba7`: `TLSUpdateUserObject: updated msTSManagingLS`
- `0x180077087`: `TLSUpdateUserObject: FAIL: SystemTimeToVariantTime`
- `0x1800771c9`: `TLSUpdateUserObject: updated terminalServer`

## pseudocode

```c
unsigned int __fastcall UpdateUserLicenseAttributes(
        int a1,
        const unsigned __int16 *a2,
        struct USERLICENSEDATA_WIN8 *a3,
        unsigned __int16 *a4)
{
  unsigned int result; // eax
  unsigned int v9; // r15d
  HRESULT v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  const unsigned __int16 *v15; // rcx
  unsigned int v16; // edx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 (__fastcall *v20)(void *, const wchar_t *, VARIANTARG *); // rax
  int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int64 (__fastcall *v25)(void *, const wchar_t *, VARIANTARG *); // rax
  int v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rax
  __int64 (__fastcall *v31)(void *, const wchar_t *, VARIANTARG *); // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rax
  __int64 (__fastcall *v36)(void *, const wchar_t *, VARIANTARG *); // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  const wchar_t *v43; // r14
  __int64 (__fastcall *v44)(void *, const wchar_t *, VARIANTARG *); // rax
  int v45; // eax
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  const char *v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // [rsp+50h] [rbp-B0h] BYREF
  int v57; // [rsp+54h] [rbp-ACh] BYREF
  const char *v58; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v59; // [rsp+60h] [rbp-A0h] BYREF
  const char *v60; // [rsp+68h] [rbp-98h] BYREF
  const char *v61; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  void *ppObject; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v64; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR psz[256]; // [rsp+D0h] [rbp-30h] BYREF

  if ( !a4 )
    return -2147467261;
  result = CoInitializeEx(0, 2u);
  v9 = result;
  if ( result == -2147417850 || result <= 1 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    ppObject = 0;
    v10 = ADsOpenObject(a4, 0, 0, 0x1C1u, &IID_IADs, &ppObject);
    v14 = v10;
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_1800E20E0 > 2 )
      {
        v57 = v10;
        v61 = "UpdateUserLicenseAttributes";
        v58 = "ADsOpenObject() Failed for IID_IADs";
        v56 = 1007;
        v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)word_1800D331A,
          v12,
          v13,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v60,
          (__int64)&v56,
          (__int64)&v61);
      }
LABEL_51:
      if ( ppObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
      VariantClear(&pvarg);
      if ( v9 != -2147417850 )
        CoUninitialize();
      return v14;
    }
    v15 = 0;
    if ( !a1 )
      v15 = a2;
    if ( (unsigned int)ADHasLicensingAttrs(v15) == 1 )
    {
      if ( (unsigned int)dword_1800E20E0 > 5 )
      {
        v58 = "TLSUpdateUserObject: AD has new licensing attrs";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (unsigned int)word_1800D336A,
          v18,
          v19,
          (__int64)&v58);
      }
      pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)a3 + 6);
      v64.pRecInfo = pvarg.pRecInfo;
      pvarg.vt = 8;
      v20 = *(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppObject + 128LL);
      *(_OWORD *)&v64.vt = *(_OWORD *)&pvarg.vt;
      v21 = v20(ppObject, L"msTSManagingLS", &v64);
      v14 = v21;
      if ( v21 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v56 = v21;
          v58 = (const char *)L"msTSManagingLS";
          v59 = (const wchar_t *)"pAD->Put failed";
          v60 = "UpdateUserLicenseAttributes";
          v57 = 1025;
          v61 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v22,
            (unsigned int)&word_1800D3396,
            v23,
            v24,
            (__int64)&v59,
            (__int64)&v56,
            (__int64)&v61,
            (__int64)&v57,
            (__int64)&v60,
            (__int64)&v58);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 > 5 )
      {
        v59 = (const wchar_t *)"TLSUpdateUserObject: updated msTSManagingLS";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v22,
          (unsigned int)word_1800D336A,
          v23,
          v24,
          (__int64)&v59);
      }
      VariantClear(&pvarg);
      StringCchPrintfW(psz, 0xFFu, L"%d", *(unsigned int *)a3);
      pvarg.llVal = (LONGLONG)SysAllocString(psz);
      v64.pRecInfo = pvarg.pRecInfo;
      pvarg.vt = 8;
      v25 = *(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppObject + 128LL);
      *(_OWORD *)&v64.vt = *(_OWORD *)&pvarg.vt;
      v26 = v25(ppObject, L"msTSLicenseVersion", &v64);
      v14 = v26;
      if ( v26 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v56 = v26;
          v59 = L"msTSLicenseVersion";
          v61 = "pAD->Put failed";
          v58 = "UpdateUserLicenseAttributes";
          v57 = 1042;
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v27,
            (unsigned int)&word_1800D3396,
            v28,
            v29,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 > 5 )
      {
        v58 = "TLSUpdateUserObject: updated msTSLicenseVersion";
        v59 = L"msTSLicenseVersion";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v27,
          (unsigned int)byte_1800D32E1,
          v28,
          v29,
          (__int64)&v58,
          (__int64)&v59);
      }
      VariantClear(&pvarg);
      StringCchPrintfW(psz, 0xFFu, L"%d", *((unsigned int *)a3 + 15));
      pvarg.llVal = (LONGLONG)SysAllocString(psz);
      pvarg.vt = 8;
      v30 = *(_QWORD *)ppObject;
      v64.pRecInfo = pvarg.pRecInfo;
      v31 = *(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(v30 + 128);
      *(_OWORD *)&v64.vt = *(_OWORD *)&pvarg.vt;
      v14 = v31(ppObject, L"msTSLicenseVersion2", &v64);
      if ( v14 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v58 = "UpdateUserLicenseAttributes";
          v59 = L"msTSLicenseVersion2";
          v57 = 1058;
          v61 = "pAD->Put failed";
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          v56 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v32,
            (unsigned int)&word_1800D3396,
            v33,
            v34,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 > 5 )
      {
        v58 = "TLSUpdateUserObject: updated msTSLicenseVersion";
        v59 = L"msTSLicenseVersion2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v32,
          (unsigned int)byte_1800D32E1,
          v33,
          v34,
          (__int64)&v58,
          (__int64)&v59);
      }
      VariantClear(&pvarg);
      pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)a3 + 32);
      pvarg.vt = 8;
      v35 = *(_QWORD *)ppObject;
      v64.pRecInfo = pvarg.pRecInfo;
      v36 = *(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(v35 + 128);
      *(_OWORD *)&v64.vt = *(_OWORD *)&pvarg.vt;
      v14 = v36(ppObject, L"msTSLicenseVersion3", &v64);
      if ( v14 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v58 = "UpdateUserLicenseAttributes";
          v59 = L"msTSLicenseVersion3";
          v57 = 1073;
          v61 = "pAD->Put failed";
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          v56 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v37,
            (unsigned int)&word_1800D3396,
            v38,
            v39,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 > 5 )
      {
        v58 = "TLSUpdateUserObject: updated msTSLicenseVersion";
        v59 = L"msTSLicenseVersion3";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v37,
          (unsigned int)byte_1800D32E1,
          v38,
          v39,
          (__int64)&v58,
          (__int64)&v59);
      }
      VariantClear(&pvarg);
      SystemTime = 0;
      FileTimeToSystemTime((const FILETIME *)((char *)a3 + 4), &SystemTime);
      if ( !SystemTimeToVariantTime(&SystemTime, &pvarg.dblVal) )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v58 = "UpdateUserLicenseAttributes";
          v61 = "TLSUpdateUserObject: FAIL: SystemTimeToVariantTime";
          v59 = L"msTSExpireDate";
          v57 = 1102;
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          v56 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v40,
            (unsigned int)&word_1800D3396,
            v41,
            v42,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_48;
      }
      v43 = L"msTSExpireDate";
      v64.pRecInfo = pvarg.pRecInfo;
      pvarg.vt = 7;
      v44 = *(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppObject + 128LL);
      *(_OWORD *)&v64.vt = *(_OWORD *)&pvarg.vt;
      v45 = v44(ppObject, L"msTSExpireDate", &v64);
      v14 = v45;
      if ( v45 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v56 = v45;
          v59 = L"msTSExpireDate";
          v61 = "pAD->Put failed";
          v58 = "UpdateUserLicenseAttributes";
          v57 = 1092;
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v46,
            (unsigned int)&word_1800D3396,
            v47,
            v48,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 <= 5 )
      {
LABEL_48:
        VariantClear(&pvarg);
        v52 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppObject + 112LL))(ppObject);
        v14 = v52;
        if ( v52 < 0 && (unsigned int)dword_1800E20E0 > 2 )
        {
          v56 = v52;
          v59 = (const wchar_t *)"UpdateUserLicenseAttributes";
          v60 = "pAD->SetInfo failed";
          v57 = 1131;
          v58 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v53,
            (unsigned int)word_1800D331A,
            v54,
            v55,
            (__int64)&v60,
            (__int64)&v56,
            (__int64)&v58,
            (__int64)&v57,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      v49 = "TLSUpdateUserObject: updated msTSExpireDate";
    }
    else
    {
      BytesToVariantArray((unsigned __int8 *)a3, v16, &pvarg);
      v43 = L"terminalServer";
      v50 = *(_QWORD *)ppObject;
      v64 = pvarg;
      v51 = (*(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(v50 + 128))(
              ppObject,
              L"terminalServer",
              &v64);
      v14 = v51;
      if ( v51 < 0 )
      {
        if ( (unsigned int)dword_1800E20E0 > 2 )
        {
          v56 = v51;
          v59 = L"terminalServer";
          v61 = "pAD->Put failed";
          v58 = "UpdateUserLicenseAttributes";
          v57 = 1116;
          v60 = "clientcore\\termsrv\\license\\peruserhelper\\peruserhelper.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v46,
            (unsigned int)&word_1800D3396,
            v47,
            v48,
            (__int64)&v61,
            (__int64)&v56,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v59);
        }
        goto LABEL_51;
      }
      if ( (unsigned int)dword_1800E20E0 <= 5 )
        goto LABEL_48;
      v49 = "TLSUpdateUserObject: updated terminalServer";
    }
    v58 = v49;
    v59 = v43;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v46,
      (unsigned int)byte_1800D32E1,
      v47,
      v48,
      (__int64)&v58,
      (__int64)&v59);
    goto LABEL_48;
  }
  return result;
}

```

## disassembly

```asm
0x180076938  push    rbp
0x18007693a  push    rbx
0x18007693b  push    rsi
0x18007693c  push    rdi
0x18007693d  push    r13
0x18007693f  push    r14
0x180076941  push    r15
0x180076943  lea     rbp, [rsp-1E0h]
0x18007694b  sub     rsp, 2E0h
0x180076952  mov     rax, cs:__security_cookie
0x180076959  xor     rax, rsp
0x18007695c  mov     [rbp+210h+var_40], rax
0x180076963  mov     rbx, r9
0x180076966  mov     r14, r8
0x180076969  mov     rdi, rdx
0x18007696c  mov     esi, ecx
0x18007696e  test    r9, r9
0x180076971  jnz     short loc_18007697D
0x180076973  mov     eax, 80004003h
0x180076978  jmp     loc_1800772C7
0x18007697d  mov     edx, 2; dwCoInit
0x180076982  xor     ecx, ecx; pvReserved
0x180076984  call    cs:__imp_CoInitializeEx
0x18007698b  nop     dword ptr [rax+rax+00h]
0x180076990  mov     r15d, eax
0x180076993  cmp     eax, 80010106h
0x180076998  jz      short loc_1800769A3
0x18007699a  cmp     eax, 1
0x18007699d  ja      loc_1800772C7
0x1800769a3  xorps   xmm0, xmm0
0x1800769a6  lea     rcx, [rsp+310h+pvarg]; pvarg
0x1800769ab  xor     eax, eax
0x1800769ad  movups  xmmword ptr [rsp+310h+pvarg], xmm0
0x1800769b2  mov     qword ptr [rbp+210h+pvarg+10h], rax
0x1800769b6  call    cs:__imp_VariantInit
0x1800769bd  nop     dword ptr [rax+rax+00h]
0x1800769c2  and     [rbp+210h+var_280], 0
0x1800769c7  lea     rax, [rbp+210h+var_280]
0x1800769cb  mov     [rsp+310h+ppObject], rax; ppObject
0x1800769d0  mov     r9d, 1C1h; dwReserved
0x1800769d6  lea     rax, IID_IADs
0x1800769dd  xor     r8d, r8d; lpszPassword
0x1800769e0  xor     edx, edx; lpszUserName
0x1800769e2  mov     [rsp+310h+riid], rax; riid
0x1800769e7  mov     rcx, rbx; lpszPathName
0x1800769ea  call    cs:__imp_ADsOpenObject
0x1800769f1  nop     dword ptr [rax+rax+00h]
0x1800769f6  mov     ebx, eax
0x1800769f8  test    eax, eax
0x1800769fa  jns     short loc_180076A72
0x1800769fc  cmp     cs:dword_1800E20E0, 2
0x180076a03  jbe     loc_18007728A
0x180076a09  mov     [rsp+310h+var_2BC], eax
0x180076a0d  lea     rdi, aUpdateuserlice; "UpdateUserLicenseAttributes"
0x180076a14  lea     rax, aAdsopenobjectF; "ADsOpenObject() Failed for IID_IADs"
0x180076a1b  mov     [rsp+310h+var_2A0], rdi
0x180076a20  mov     [rsp+310h+var_2B8], rax
0x180076a25  lea     rsi, aClientcoreTerm; "clientcore\\termsrv\\license\\peruserhe"...
0x180076a2c  lea     rax, [rsp+310h+var_2A0]
0x180076a31  mov     [rsp+310h+var_2C0], 3EFh
0x180076a39  mov     [rsp+310h+var_2D0], rax
0x180076a3e  lea     rdx, word_1800D331A
0x180076a45  lea     rax, [rsp+310h+var_2C0]
0x180076a4a  mov     [rsp+310h+var_2A8], rsi
0x180076a4f  mov     [rsp+310h+var_2D8], rax
0x180076a54  lea     rax, [rsp+310h+var_2A8]
0x180076a59  mov     [rsp+310h+var_2E0], rax
0x180076a5e  lea     rax, [rsp+310h+var_2BC]
0x180076a63  mov     [rsp+310h+ppObject], rax
0x180076a68  lea     rax, [rsp+310h+var_2B8]
0x180076a6d  jmp     loc_180077280
0x180076a72  xor     ecx, ecx
0x180076a74  test    esi, esi
0x180076a76  cmovz   rcx, rdi; unsigned __int16 *
0x180076a7a  call    ?ADHasLicensingAttrs@@YAHPEBG@Z; ADHasLicensingAttrs(ushort const *)
0x180076a7f  lea     rdi, aUpdateuserlice; "UpdateUserLicenseAttributes"
0x180076a86  lea     rsi, aClientcoreTerm; "clientcore\\termsrv\\license\\peruserhe"...
0x180076a8d  cmp     eax, 1
0x180076a90  jnz     loc_180077102
0x180076a96  cmp     cs:dword_1800E20E0, 5
0x180076a9d  jbe     short loc_180076AC1
0x180076a9f  lea     rax, aTlsupdateusero_2; "TLSUpdateUserObject: AD has new licensi"...
0x180076aa6  mov     [rsp+310h+var_2B8], rax
0x180076aab  lea     rdx, word_1800D336A
0x180076ab2  lea     rax, [rsp+310h+var_2B8]
0x180076ab7  mov     [rsp+310h+riid], rax
0x180076abc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180076ac1  lea     rcx, [r14+0Ch]; psz
0x180076ac5  call    cs:__imp_SysAllocString
0x180076acc  nop     dword ptr [rax+rax+00h]
0x180076ad1  mov     rcx, [rbp+210h+var_280]
0x180076ad5  lea     r13, aMstsmanagingls; "msTSManagingLS"
0x180076adc  movsd   xmm1, qword ptr [rbp+210h+pvarg+10h]
0x180076ae1  lea     r8, [rbp+210h+var_270]
0x180076ae5  mov     qword ptr [rbp+210h+pvarg+8], rax
0x180076ae9  mov     rdx, r13
0x180076aec  mov     eax, 8
0x180076af1  movsd   [rbp+210h+var_260], xmm1
0x180076af6  mov     word ptr [rsp+310h+pvarg], ax
0x180076afb  mov     rax, [rcx]
0x180076afe  movups  xmm0, xmmword ptr [rsp+310h+pvarg]
0x180076b03  mov     rax, [rax+80h]
0x180076b0a  movaps  [rbp+210h+var_270], xmm0
0x180076b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b13  mov     ebx, eax
0x180076b15  test    eax, eax
0x180076b17  jns     loc_180076B9E
0x180076b1d  cmp     cs:dword_1800E20E0, 2
0x180076b24  jbe     loc_18007728A
0x180076b2a  mov     [rsp+310h+var_2C0], eax
0x180076b2e  lea     rdx, word_1800D3396
0x180076b35  lea     rax, aPadPutFailed; "pAD->Put failed"
0x180076b3c  mov     [rsp+310h+var_2B8], r13
0x180076b41  mov     [rsp+310h+var_2B0], rax
0x180076b46  lea     rax, [rsp+310h+var_2B8]
0x180076b4b  mov     [rsp+310h+var_2C8], rax
0x180076b50  lea     rax, [rsp+310h+var_2A8]
0x180076b55  mov     [rsp+310h+var_2D0], rax
0x180076b5a  lea     rax, [rsp+310h+var_2BC]
0x180076b5f  mov     [rsp+310h+var_2D8], rax
0x180076b64  lea     rax, [rsp+310h+var_2A0]
0x180076b69  mov     [rsp+310h+var_2E0], rax
0x180076b6e  lea     rax, [rsp+310h+var_2C0]
0x180076b73  mov     [rsp+310h+ppObject], rax
0x180076b78  lea     rax, [rsp+310h+var_2B0]
0x180076b7d  mov     [rsp+310h+var_2A8], rdi
0x180076b82  mov     [rsp+310h+var_2BC], 401h
0x180076b8a  mov     [rsp+310h+var_2A0], rsi
0x180076b8f  mov     [rsp+310h+riid], rax
0x180076b94  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180076b99  jmp     loc_18007728A
0x180076b9e  cmp     cs:dword_1800E20E0, 5
0x180076ba5  jbe     short loc_180076BC9
0x180076ba7  lea     rax, aTlsupdateusero_4; "TLSUpdateUserObject: updated msTSManagi"...
0x180076bae  mov     [rsp+310h+var_2B0], rax
0x180076bb3  lea     rdx, word_1800D336A
0x180076bba  lea     rax, [rsp+310h+var_2B0]
0x180076bbf  mov     [rsp+310h+riid], rax
0x180076bc4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180076bc9  lea     rcx, [rsp+310h+pvarg]; pvarg
0x180076bce  call    cs:__imp_VariantClear
0x180076bd5  nop     dword ptr [rax+rax+00h]
0x180076bda  mov     r9d, [r14]
0x180076bdd  lea     r8, aD; "%d"
0x180076be4  mov     edx, 0FFh; unsigned __int64
0x180076be9  lea     rcx, [rbp+210h+psz]; unsigned __int16 *
0x180076bed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076bf2  lea     rcx, [rbp+210h+psz]; psz
0x180076bf6  call    cs:__imp_SysAllocString
0x180076bfd  nop     dword ptr [rax+rax+00h]
0x180076c02  mov     rcx, [rbp+210h+var_280]
0x180076c06  lea     r13, aMstslicensever; "msTSLicenseVersion"
0x180076c0d  movsd   xmm1, qword ptr [rbp+210h+pvarg+10h]
0x180076c12  lea     r8, [rbp+210h+var_270]
0x180076c16  mov     qword ptr [rbp+210h+pvarg+8], rax
0x180076c1a  mov     rdx, r13
0x180076c1d  mov     eax, 8
0x180076c22  movsd   [rbp+210h+var_260], xmm1
0x180076c27  mov     word ptr [rsp+310h+pvarg], ax
0x180076c2c  mov     rax, [rcx]
0x180076c2f  movups  xmm0, xmmword ptr [rsp+310h+pvarg]
0x180076c34  mov     rax, [rax+80h]
0x180076c3b  movaps  [rbp+210h+var_270], xmm0
0x180076c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c44  mov     ebx, eax
0x180076c46  test    eax, eax
0x180076c48  jns     short loc_180076CC1
0x180076c4a  cmp     cs:dword_1800E20E0, 2
0x180076c51  jbe     loc_18007728A
0x180076c57  mov     [rsp+310h+var_2C0], eax
0x180076c5b  lea     rdx, word_1800D3396
0x180076c62  lea     rax, aPadPutFailed; "pAD->Put failed"
0x180076c69  mov     [rsp+310h+var_2B0], r13
0x180076c6e  mov     [rsp+310h+var_2A0], rax
0x180076c73  lea     rax, [rsp+310h+var_2B0]
0x180076c78  mov     [rsp+310h+var_2C8], rax
0x180076c7d  lea     rax, [rsp+310h+var_2B8]
0x180076c82  mov     [rsp+310h+var_2D0], rax
0x180076c87  lea     rax, [rsp+310h+var_2BC]
0x180076c8c  mov     [rsp+310h+var_2D8], rax
0x180076c91  lea     rax, [rsp+310h+var_2A8]
0x180076c96  mov     [rsp+310h+var_2E0], rax
0x180076c9b  lea     rax, [rsp+310h+var_2C0]
0x180076ca0  mov     [rsp+310h+ppObject], rax
0x180076ca5  lea     rax, [rsp+310h+var_2A0]
0x180076caa  mov     [rsp+310h+var_2B8], rdi
0x180076caf  mov     [rsp+310h+var_2BC], 412h
0x180076cb7  mov     [rsp+310h+var_2A8], rsi
0x180076cbc  jmp     loc_180076B8F
0x180076cc1  cmp     cs:dword_1800E20E0, 5
0x180076cc8  lea     r13, aTlsupdateusero_3; "TLSUpdateUserObject: updated msTSLicens"...
0x180076ccf  jbe     short loc_180076D02
0x180076cd1  lea     rax, aMstslicensever; "msTSLicenseVersion"
0x180076cd8  mov     [rsp+310h+var_2B8], r13
0x180076cdd  mov     [rsp+310h+var_2B0], rax
0x180076ce2  lea     rdx, byte_1800D32E1
0x180076ce9  lea     rax, [rsp+310h+var_2B0]
0x180076cee  mov     [rsp+310h+ppObject], rax
0x180076cf3  lea     rax, [rsp+310h+var_2B8]
0x180076cf8  mov     [rsp+310h+riid], rax
0x180076cfd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180076d02  lea     rcx, [rsp+310h+pvarg]; pvarg
0x180076d07  call    cs:__imp_VariantClear
0x180076d0e  nop     dword ptr [rax+rax+00h]
0x180076d13  mov     r9d, [r14+3Ch]
0x180076d17  lea     r8, aD; "%d"
0x180076d1e  mov     edx, 0FFh; unsigned __int64
0x180076d23  lea     rcx, [rbp+210h+psz]; unsigned __int16 *
0x180076d27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076d2c  lea     rcx, [rbp+210h+psz]; psz
0x180076d30  call    cs:__imp_SysAllocString
0x180076d37  nop     dword ptr [rax+rax+00h]
0x180076d3c  mov     rcx, [rbp+210h+var_280]
0x180076d40  lea     r8, [rbp+210h+var_270]
0x180076d44  movsd   xmm1, qword ptr [rbp+210h+pvarg+10h]
0x180076d49  lea     rdx, aMstslicensever_0; "msTSLicenseVersion2"
0x180076d50  mov     qword ptr [rbp+210h+pvarg+8], rax
0x180076d54  mov     eax, 8
0x180076d59  mov     word ptr [rsp+310h+pvarg], ax
0x180076d5e  mov     rax, [rcx]
0x180076d61  movups  xmm0, xmmword ptr [rsp+310h+pvarg]
0x180076d66  movsd   [rbp+210h+var_260], xmm1
0x180076d6b  mov     rax, [rax+80h]
0x180076d72  movaps  [rbp+210h+var_270], xmm0
0x180076d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d7b  mov     ebx, eax
0x180076d7d  test    eax, eax
0x180076d7f  jns     short loc_180076DFF
0x180076d81  cmp     cs:dword_1800E20E0, 2
0x180076d88  jbe     loc_18007728A
0x180076d8e  lea     rax, aMstslicensever_0; "msTSLicenseVersion2"
0x180076d95  mov     [rsp+310h+var_2B8], rdi
0x180076d9a  mov     [rsp+310h+var_2B0], rax
0x180076d9f  lea     rdx, word_1800D3396
0x180076da6  lea     rax, aPadPutFailed; "pAD->Put failed"
0x180076dad  mov     [rsp+310h+var_2BC], 422h
0x180076db5  mov     [rsp+310h+var_2A0], rax
0x180076dba  lea     rax, [rsp+310h+var_2B0]
0x180076dbf  mov     [rsp+310h+var_2C8], rax
0x180076dc4  lea     rax, [rsp+310h+var_2B8]
0x180076dc9  mov     [rsp+310h+var_2D0], rax
0x180076dce  lea     rax, [rsp+310h+var_2BC]
0x180076dd3  mov     [rsp+310h+var_2D8], rax
0x180076dd8  lea     rax, [rsp+310h+var_2A8]
0x180076ddd  mov     [rsp+310h+var_2E0], rax
0x180076de2  lea     rax, [rsp+310h+var_2C0]
0x180076de7  mov     [rsp+310h+ppObject], rax
0x180076dec  lea     rax, [rsp+310h+var_2A0]
0x180076df1  mov     [rsp+310h+var_2A8], rsi
0x180076df6  mov     [rsp+310h+var_2C0], ebx
0x180076dfa  jmp     loc_180076B8F
0x180076dff  cmp     cs:dword_1800E20E0, 5
0x180076e06  jbe     short loc_180076E39
0x180076e08  lea     rax, aMstslicensever_0; "msTSLicenseVersion2"
0x180076e0f  mov     [rsp+310h+var_2B8], r13
0x180076e14  mov     [rsp+310h+var_2B0], rax
0x180076e19  lea     rdx, byte_1800D32E1
0x180076e20  lea     rax, [rsp+310h+var_2B0]
0x180076e25  mov     [rsp+310h+ppObject], rax
0x180076e2a  lea     rax, [rsp+310h+var_2B8]
0x180076e2f  mov     [rsp+310h+riid], rax
0x180076e34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180076e39  lea     rcx, [rsp+310h+pvarg]; pvarg
0x180076e3e  call    cs:__imp_VariantClear
0x180076e45  nop     dword ptr [rax+rax+00h]
0x180076e4a  lea     rcx, [r14+40h]; psz
0x180076e4e  call    cs:__imp_SysAllocString
0x180076e55  nop     dword ptr [rax+rax+00h]
0x180076e5a  mov     rcx, [rbp+210h+var_280]
0x180076e5e  lea     r8, [rbp+210h+var_270]
0x180076e62  movsd   xmm1, qword ptr [rbp+210h+pvarg+10h]
0x180076e67  lea     rdx, aMstslicensever_1; "msTSLicenseVersion3"
0x180076e6e  mov     qword ptr [rbp+210h+pvarg+8], rax
0x180076e72  mov     eax, 8
0x180076e77  mov     word ptr [rsp+310h+pvarg], ax
0x180076e7c  mov     rax, [rcx]
0x180076e7f  movups  xmm0, xmmword ptr [rsp+310h+pvarg]
0x180076e84  movsd   [rbp+210h+var_260], xmm1
0x180076e89  mov     rax, [rax+80h]
0x180076e90  movaps  [rbp+210h+var_270], xmm0
0x180076e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e99  mov     ebx, eax
0x180076e9b  test    eax, eax
0x180076e9d  jns     short loc_180076F1D
0x180076e9f  cmp     cs:dword_1800E20E0, 2
0x180076ea6  jbe     loc_18007728A
0x180076eac  lea     rax, aMstslicensever_1; "msTSLicenseVersion3"
0x180076eb3  mov     [rsp+310h+var_2B8], rdi
0x180076eb8  mov     [rsp+310h+var_2B0], rax
0x180076ebd  lea     rdx, word_1800D3396
0x180076ec4  lea     rax, aPadPutFailed; "pAD->Put failed"
0x180076ecb  mov     [rsp+310h+var_2BC], 431h
0x180076ed3  mov     [rsp+310h+var_2A0], rax
0x180076ed8  lea     rax, [rsp+310h+var_2B0]
0x180076edd  mov     [rsp+310h+var_2C8], rax
0x180076ee2  lea     rax, [rsp+310h+var_2B8]
0x180076ee7  mov     [rsp+310h+var_2D0], rax
0x180076eec  lea     rax, [rsp+310h+var_2BC]
0x180076ef1  mov     [rsp+310h+var_2D8], rax
0x180076ef6  lea     rax, [rsp+310h+var_2A8]
  ... truncated ...
```
