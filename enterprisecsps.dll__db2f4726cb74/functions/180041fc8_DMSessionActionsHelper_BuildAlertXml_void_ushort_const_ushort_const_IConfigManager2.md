# DMSessionActionsHelper::BuildAlertXml(void * *,ushort const *,ushort const *,IConfigManager2 *)

- ea: `0x180041fc8`
- end: `0x180043474`
- name: `?BuildAlertXml@DMSessionActionsHelper@@QEAAJPEAPEAXPEBG1PEAUIConfigManager2@@@Z`
- size: `5292`
- prototype: `int(DMSessionActionsHelper *__hidden this, void **, const unsigned __int16 *, const unsigned __int16 *, struct IConfigManager2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800412e0`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a78`
- `0x180025a9c`
- `0x18002dc38`
- `0x18002dc94`
- `0x18003fb44`
- `0x180041fc8`
- `0x180043c0c`
- `0x180043e60`
- `0x180044604`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004207d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180042191`
- `OLEAUT32!__imp_SysFreeString` at `0x18004222a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180042350`
- `OLEAUT32!__imp_SysFreeString` at `0x1800423df`
- `OLEAUT32!__imp_SysFreeString` at `0x18004246c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042501`
- `OLEAUT32!__imp_SysFreeString` at `0x180042596`
- `OLEAUT32!__imp_SysFreeString` at `0x180042778`
- `OLEAUT32!__imp_SysFreeString` at `0x180042872`
- `OLEAUT32!__imp_SysFreeString` at `0x180042a6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042afa`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d93`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e17`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042f16`
- `OLEAUT32!__imp_SysFreeString` at `0x180042f90`
- `OLEAUT32!__imp_SysFreeString` at `0x18004300a`
- `OLEAUT32!__imp_SysFreeString` at `0x180043084`
- `OLEAUT32!__imp_SysFreeString` at `0x1800430fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18004318f`
- `OLEAUT32!__imp_SysFreeString` at `0x180043218`
- `OLEAUT32!__imp_SysFreeString` at `0x1800432a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004333b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800433d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180043439`
- `OLEAUT32!__imp_SysFreeString` at `0x18004207d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180042191`
- `OLEAUT32!__imp_SysFreeString` at `0x18004222a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180042350`
- `OLEAUT32!__imp_SysFreeString` at `0x1800423df`
- `OLEAUT32!__imp_SysFreeString` at `0x18004246c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042501`
- `OLEAUT32!__imp_SysFreeString` at `0x180042596`
- `OLEAUT32!__imp_SysFreeString` at `0x180042778`
- `OLEAUT32!__imp_SysFreeString` at `0x180042872`
- `OLEAUT32!__imp_SysFreeString` at `0x180042a6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042afa`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d93`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e17`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042f16`
- `OLEAUT32!__imp_SysFreeString` at `0x180042f90`
- `OLEAUT32!__imp_SysFreeString` at `0x18004300a`
- `OLEAUT32!__imp_SysFreeString` at `0x180043084`
- `OLEAUT32!__imp_SysFreeString` at `0x1800430fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18004318f`
- `OLEAUT32!__imp_SysFreeString` at `0x180043218`
- `OLEAUT32!__imp_SysFreeString` at `0x1800432a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004333b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800433d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180043439`
- `DMCmnUtils!EncodeBase64W` at `0x1800427ad`
- `DMCmnUtils!EncodeBase64W` at `0x1800427ad`
- `XmlLite!CreateXmlWriter` at `0x1800421c4`
- `XmlLite!CreateXmlWriter` at `0x1800421c4`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180042260`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180042260`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180043363`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180043363`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004212b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004212b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043453`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DMSessionActionsHelper::BuildAlertXml(
        DMSessionActionsHelper *this,
        void **a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IConfigManager2 *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int AllNodeIds; // eax
  unsigned int v11; // edi
  BSTR *v12; // rax
  BSTR *v13; // rax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  char v22; // si
  unsigned int i; // r15d
  const unsigned __int16 *v24; // rbx
  DMSessionActionsHelper *v25; // rcx
  int NodeUri; // eax
  unsigned __int16 *v27; // rbx
  const unsigned __int8 *v28; // rdi
  int v29; // eax
  unsigned int v30; // esi
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  BSTR *v45; // rax
  __int64 m; // rbx
  unsigned int k; // ebx
  __int64 j; // rbx
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  HRESULT HGlobalFromStream; // eax
  HGLOBAL v54; // rax
  int v55; // [rsp+20h] [rbp-60h]
  const char *v56; // [rsp+20h] [rbp-60h]
  int v57; // [rsp+20h] [rbp-60h]
  int v58; // [rsp+20h] [rbp-60h]
  int v59; // [rsp+20h] [rbp-60h]
  int v60; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-48h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-40h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+48h] [rbp-38h] BYREF
  HGLOBAL phglobal; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v66; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v67; // [rsp+60h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+68h] [rbp-18h]
  DMSessionActionsHelper **v69; // [rsp+70h] [rbp-10h]
  char v70; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  DMSessionActionsHelper *v72; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int16 *v73; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 *v74; // [rsp+D0h] [rbp+50h]

  v74 = a3;
  v72 = this;
  v7 = 0;
  if ( !a2 )
  {
    v8 = 1093;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)0x80070057LL,
      v55);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    v8 = 1094;
    goto LABEL_3;
  }
  LODWORD(v72) = 0;
  pv = 0;
  p_pv = &pv;
  v69 = &v72;
  v70 = 1;
  AllNodeIds = DMSessionActionsHelper::GetAllNodeIds(
                 (DMSessionActionsHelper *)&v72,
                 (unsigned int *)&v72,
                 (unsigned __int16 ***)&pv,
                 a3,
                 a4);
  v11 = AllNodeIds;
  if ( AllNodeIds == -2147024894 )
  {
    *a2 = 0;
    v12 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v12[v7++]);
          v12 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
LABEL_182:
      CoTaskMemFree(v12);
      return 0;
    }
    return 0;
  }
  if ( AllNodeIds < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x462,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)AllNodeIds,
      (int)v56);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v12 = (BSTR *)pv;
  if ( !pv || !(_DWORD)v72 )
    goto LABEL_179;
  ppvObject = 0;
  ppOutput = 0;
  ppstm = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  v14 = CreateStreamOnHGlobal(0, 0, &ppstm);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v14,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  v15 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v15,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
  v16 = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-16", &ppOutput);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v16,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v17 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v17,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v18 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
  v11 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x470,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v18,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v19 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
  v11 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v19,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v20 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"CustomAlertData",
          0);
  v11 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x473,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v20,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v21 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"Nodes",
          0);
  v11 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x474,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
      (const char *)(unsigned int)v21,
      (int)v56);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    v13 = (BSTR *)pv;
    if ( pv )
    {
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    return v11;
  }
  v22 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v72 )
    {
      if ( v22 )
      {
        v49 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
        v11 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4BE,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v49,
            (int)v56);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( !pv )
            return v11;
          if ( (_DWORD)v72 )
          {
            do
            {
              SysFreeString(v13[v7++]);
              v13 = (BSTR *)pv;
            }
            while ( v7 < (unsigned int)v72 );
          }
          goto LABEL_15;
        }
        v50 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
        v11 = v50;
        if ( v50 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4BF,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v50,
            (int)v56);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( !pv )
            return v11;
          if ( (_DWORD)v72 )
          {
            do
            {
              SysFreeString(v13[v7++]);
              v13 = (BSTR *)pv;
            }
            while ( v7 < (unsigned int)v72 );
          }
          goto LABEL_15;
        }
        v51 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
        v11 = v51;
        if ( v51 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C1,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v51,
            (int)v56);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( !pv )
            return v11;
          if ( (_DWORD)v72 )
          {
            do
            {
              SysFreeString(v13[v7++]);
              v13 = (BSTR *)pv;
            }
            while ( v7 < (unsigned int)v72 );
          }
          goto LABEL_15;
        }
        LODWORD(v73) = 0;
        v52 = (*(__int64 (__fastcall **)(LPSTREAM, const OLECHAR *, __int64, unsigned __int16 **))(*(_QWORD *)ppstm
                                                                                                 + 32LL))(
                ppstm,
                &Class,
                2,
                &v73);
        v11 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C5,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v52,
            (int)v56);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( !pv )
            return v11;
          if ( (_DWORD)v72 )
          {
            do
            {
              SysFreeString(v13[v7++]);
              v13 = (BSTR *)pv;
            }
            while ( v7 < (unsigned int)v72 );
          }
          goto LABEL_15;
        }
        phglobal = 0;
        HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
        v11 = HGlobalFromStream;
        if ( HGlobalFromStream < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C8,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)HGlobalFromStream,
            (int)v56);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phglobal);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( !pv )
            return v11;
          if ( (_DWORD)v72 )
          {
            do
            {
              SysFreeString(v13[v7++]);
              v13 = (BSTR *)pv;
            }
            while ( v7 < (unsigned int)v72 );
          }
LABEL_15:
          CoTaskMemFree(v13);
          return v11;
        }
        v54 = phglobal;
        phglobal = 0;
        *a2 = v54;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phglobal);
      }
      else
      {
        *a2 = 0;
      }
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v12 = (BSTR *)pv;
LABEL_179:
      if ( v12 )
      {
        if ( (_DWORD)v72 )
        {
          do
          {
            SysFreeString(v12[v7++]);
            v12 = (BSTR *)pv;
          }
          while ( v7 < (unsigned int)v72 );
        }
        goto LABEL_182;
      }
      return 0;
    }
    v66 = 0;
    v24 = (const unsigned __int16 *)*((_QWORD *)pv + i);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v66,
      0);
    NodeUri = DMSessionActionsHelper::GetNodeUri(v25, &v66, v74, a4, v24);
    v11 = NodeUri;
    if ( NodeUri < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
        (const char *)(unsigned int)NodeUri,
        v57);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v13 = (BSTR *)pv;
      if ( !pv )
        return v11;
      for ( j = 0; (unsigned int)j < (unsigned int)v72; v13 = (BSTR *)pv )
      {
        SysFreeString(v13[j]);
        j = (unsigned int)(j + 1);
      }
      goto LABEL_15;
    }
    v27 = v66;
    if ( v66 )
    {
      v67 = 0;
      LODWORD(v73) = 13;
      phglobal = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &phglobal,
        0);
      if ( (int)GetCspNodeValueAndType(a5, v27, (unsigned __int16 **)&phglobal, &v67, (enum ConfigDataType *)&v73) < 0
        || (v28 = (const unsigned __int8 *)phglobal) == 0
        || (int)v73 > 13 )
      {
        v37 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                ppvObject,
                0,
                L"Node",
                0);
        v11 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4A8,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v37,
            v58);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( pv )
          {
            for ( k = 0; k < (unsigned int)v72; v13 = (BSTR *)pv )
              SysFreeString(v13[k++]);
            goto LABEL_15;
          }
          return v11;
        }
        v60 = (int)v27;
        v38 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
                ppvObject,
                0,
                L"Uri",
                0);
        v11 = v38;
        v7 = 0;
        if ( v38 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4AB,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v38,
            v60);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( pv )
          {
            if ( (_DWORD)v72 )
            {
              do
              {
                SysFreeString(v13[v7++]);
                v13 = (BSTR *)pv;
              }
              while ( v7 < (unsigned int)v72 );
            }
            goto LABEL_15;
          }
          return v11;
        }
        v56 = L"1";
        v39 = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
                ppvObject,
                0,
                L"Status",
                0);
        v11 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4AC,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v39,
            (int)L"1");
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( pv )
          {
            if ( (_DWORD)v72 )
            {
              do
              {
                SysFreeString(v13[v7++]);
                v13 = (BSTR *)pv;
              }
              while ( v7 < (unsigned int)v72 );
            }
            goto LABEL_15;
          }
          return v11;
        }
        v40 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
        v11 = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4AD,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v40,
            (int)L"1");
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v13 = (BSTR *)pv;
          if ( pv )
          {
            if ( (_DWORD)v72 )
            {
              do
              {
                SysFreeString(v13[v7++]);
                v13 = (BSTR *)pv;
              }
              while ( v7 < (unsigned int)v72 );
            }
            goto LABEL_15;
          }
          return v11;
        }
LABEL_87:
        v22 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
        goto LABEL_92;
      }
      v29 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
              ppvObject,
              0,
              L"Node",
              0);
      v30 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
          (const char *)(unsigned int)v29,
          v58);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
        v45 = (BSTR *)pv;
        if ( pv )
        {
          for ( m = 0; (unsigned int)m < (unsigned int)v72; v45 = (BSTR *)pv )
          {
            SysFreeString(v45[m]);
            m = (unsigned int)(m + 1);
          }
          goto LABEL_112;
        }
      }
      else
      {
        v59 = (int)v27;
        v31 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
                ppvObject,
                0,
                L"Uri",
                0);
        v30 = v31;
        v7 = 0;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v31,
            v59);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v45 = (BSTR *)pv;
          if ( pv )
          {
            if ( (_DWORD)v72 )
            {
              do
              {
                SysFreeString(v45[v7++]);
                v45 = (BSTR *)pv;
              }
              while ( v7 < (unsigned int)v72 );
            }
            goto LABEL_112;
          }
        }
        else
        {
          v56 = L"0";
          v32 = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
                  ppvObject,
                  0,
                  L"Status",
                  0);
          v30 = v32;
          if ( v32 >= 0 )
          {
            if ( (_DWORD)v73 == 6 )
            {
              v73 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v73,
                0);
              v34 = EncodeBase64W(v28, v67, &v73);
              v11 = v34;
              if ( v34 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x49A,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
                  (const char *)(unsigned int)v34,
                  (int)L"0");
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                v13 = (BSTR *)pv;
                if ( !pv )
                  return v11;
                if ( (_DWORD)v72 )
                {
                  do
                  {
                    SysFreeString(v13[v7++]);
                    v13 = (BSTR *)pv;
                  }
                  while ( v7 < (unsigned int)v72 );
                }
                goto LABEL_15;
              }
              v35 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *))(*(_QWORD *)ppvObject + 224LL))(
                      ppvObject,
                      v73);
              v11 = v35;
              if ( v35 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x49B,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
                  (const char *)(unsigned int)v35,
                  (int)L"0");
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                v13 = (BSTR *)pv;
                if ( !pv )
                  return v11;
                if ( (_DWORD)v72 )
                {
                  do
                  {
                    SysFreeString(v13[v7++]);
                    v13 = (BSTR *)pv;
                  }
                  while ( v7 < (unsigned int)v72 );
                }
                goto LABEL_15;
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
            }
            else
            {
              v33 = (*(__int64 (__fastcall **)(void *, const unsigned __int8 *))(*(_QWORD *)ppvObject + 224LL))(
                      ppvObject,
                      v28);
              v11 = v33;
              if ( v33 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4A0,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
                  (const char *)(unsigned int)v33,
                  (int)L"0");
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                v13 = (BSTR *)pv;
                if ( !pv )
                  return v11;
                if ( (_DWORD)v72 )
                {
                  do
                  {
                    SysFreeString(v13[v7++]);
                    v13 = (BSTR *)pv;
                  }
                  while ( v7 < (unsigned int)v72 );
                }
                goto LABEL_15;
              }
            }
            v36 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
            v11 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4A3,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
                (const char *)(unsigned int)v36,
                (int)L"0");
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
              v13 = (BSTR *)pv;
              if ( !pv )
                return v11;
              if ( (_DWORD)v72 )
              {
                do
                {
                  SysFreeString(v13[v7++]);
                  v13 = (BSTR *)pv;
                }
                while ( v7 < (unsigned int)v72 );
              }
              goto LABEL_15;
            }
            goto LABEL_87;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
            (const char *)(unsigned int)v32,
            (int)L"0");
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&phglobal);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          v45 = (BSTR *)pv;
          if ( pv )
          {
            if ( (_DWORD)v72 )
            {
              do
              {
                SysFreeString(v45[v7++]);
                v45 = (BSTR *)pv;
              }
              while ( v7 < (unsigned int)v72 );
            }
LABEL_112:
            CoTaskMemFree(v45);
          }
        }
      }
      return v30;
    }
    v41 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
            ppvObject,
            0,
            L"Node",
            0);
    v11 = v41;
    v7 = 0;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B3,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
        (const char *)(unsigned int)v41,
        v57);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v13 = (BSTR *)pv;
      if ( !pv )
        return v11;
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    v42 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
            ppvObject,
            0,
            L"Uri",
            0);
    v11 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
        (const char *)(unsigned int)v42,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v13 = (BSTR *)pv;
      if ( !pv )
        return v11;
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    v56 = L"1";
    v43 = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD))(*(_QWORD *)ppvObject + 56LL))(
            ppvObject,
            0,
            L"Status",
            0);
    v11 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
        (const char *)(unsigned int)v43,
        (int)L"1");
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v13 = (BSTR *)pv;
      if ( !pv )
        return v11;
      if ( (_DWORD)v72 )
      {
        do
        {
          SysFreeString(v13[v7++]);
          v13 = (BSTR *)pv;
        }
        while ( v7 < (unsigned int)v72 );
      }
      goto LABEL_15;
    }
    v44 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
    v11 = v44;
    if ( v44 < 0 )
      break;
LABEL_92:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4B8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionshelper.cpp",
    (const char *)(unsigned int)v44,
    (int)L"1");
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  v13 = (BSTR *)pv;
  if ( pv )
  {
    if ( (_DWORD)v72 )
    {
      do
      {
        SysFreeString(v13[v7++]);
        v13 = (BSTR *)pv;
      }
      while ( v7 < (unsigned int)v72 );
    }
    goto LABEL_15;
  }
  return v11;
}

```

## disassembly

```asm
0x180041fc8  mov     [rsp-38h+arg_10], r8
0x180041fcd  mov     [rsp-38h+arg_0], rcx
0x180041fd2  push    rbp
0x180041fd3  push    rbx
0x180041fd4  push    rsi
0x180041fd5  push    rdi
0x180041fd6  push    r13
0x180041fd8  push    r14
0x180041fda  push    r15
0x180041fdc  mov     rbp, rsp
0x180041fdf  sub     rsp, 80h
0x180041fe6  mov     r13, r9
0x180041fe9  mov     r14, rdx
0x180041fec  xor     ebx, ebx
0x180041fee  test    rdx, rdx
0x180041ff1  jnz     short loc_180042017
0x180041ff3  mov     edx, 445h; void *
0x180041ff8  mov     ebx, 80070057h
0x180041ffd  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180042004  mov     r9d, ebx; char *
0x180042007  mov     rcx, [rbp+38h]; this
0x18004200b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042010  mov     eax, ebx
0x180042012  jmp     loc_180043461
0x180042017  cmp     [rbp+arg_20], rbx
0x18004201b  jnz     short loc_180042024
0x18004201d  mov     edx, 446h
0x180042022  jmp     short loc_180041FF8
0x180042024  mov     dword ptr [rbp+arg_0], ebx
0x180042027  mov     [rbp+pv], rbx
0x18004202b  lea     rcx, [rbp+pv]
0x18004202f  mov     [rbp+var_18], rcx
0x180042033  lea     rcx, [rbp+arg_0]; this
0x180042037  mov     [rbp+var_10], rcx
0x18004203b  mov     [rbp+var_8], 1
0x18004203f  mov     [rsp+80h+var_60], r13; int
0x180042044  mov     r9, r8; unsigned __int16 *
0x180042047  lea     r8, [rbp+pv]; unsigned __int16 ***
0x18004204b  lea     rdx, [rbp+arg_0]; unsigned int *
0x18004204f  call    ?GetAllNodeIds@DMSessionActionsHelper@@QEAAJPEAKPEAPEAPEAGPEBG2@Z; DMSessionActionsHelper::GetAllNodeIds(ulong *,ushort * * *,ushort const *,ushort const *)
0x180042054  mov     edi, eax
0x180042056  cmp     eax, 80070002h
0x18004205b  jnz     short loc_180042099
0x18004205d  mov     [r14], rbx
0x180042060  mov     rax, [rbp+pv]
0x180042064  test    rax, rax
0x180042067  jz      loc_18004345F
0x18004206d  cmp     dword ptr [rbp+arg_0], 0
0x180042071  jbe     loc_180043450
0x180042077  mov     ecx, ebx
0x180042079  mov     rcx, [rax+rcx*8]; bstrString
0x18004207d  call    cs:__imp_SysFreeString
0x180042084  nop     dword ptr [rax+rax+00h]
0x180042089  inc     ebx
0x18004208b  mov     rax, [rbp+pv]
0x18004208f  cmp     ebx, dword ptr [rbp+arg_0]
0x180042092  jb      short loc_180042077
0x180042094  jmp     loc_180043450
0x180042099  test    edi, edi
0x18004209b  jns     short loc_1800420F8
0x18004209d  mov     rcx, [rbp+38h]; this
0x1800420a1  mov     r9d, edi; char *
0x1800420a4  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800420ab  mov     edx, 462h; void *
0x1800420b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800420b5  nop
0x1800420b6  mov     rax, [rbp+pv]
0x1800420ba  test    rax, rax
0x1800420bd  jz      short loc_1800420F1
0x1800420bf  cmp     dword ptr [rbp+arg_0], 0
0x1800420c3  jbe     short loc_1800420E2
0x1800420c5  mov     ecx, ebx
0x1800420c7  mov     rcx, [rax+rcx*8]; bstrString
0x1800420cb  call    cs:__imp_SysFreeString
0x1800420d2  nop     dword ptr [rax+rax+00h]
0x1800420d7  inc     ebx
0x1800420d9  mov     rax, [rbp+pv]
0x1800420dd  cmp     ebx, dword ptr [rbp+arg_0]
0x1800420e0  jb      short loc_1800420C5
0x1800420e2  mov     rcx, rax; pv
0x1800420e5  call    cs:__imp_CoTaskMemFree
0x1800420ec  nop     dword ptr [rax+rax+00h]
0x1800420f1  mov     eax, edi
0x1800420f3  jmp     loc_180043461
0x1800420f8  mov     rax, [rbp+pv]
0x1800420fc  test    rax, rax
0x1800420ff  jz      loc_180043428
0x180042105  cmp     dword ptr [rbp+arg_0], ebx
0x180042108  jbe     loc_180043428
0x18004210e  mov     [rbp+ppvObject], rbx
0x180042112  mov     [rbp+ppOutput], rbx
0x180042116  mov     [rbp+ppstm], rbx
0x18004211a  lea     rcx, [rbp+ppstm]
0x18004211e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042123  lea     r8, [rbp+ppstm]; ppstm
0x180042127  xor     edx, edx; fDeleteOnRelease
0x180042129  xor     ecx, ecx; hGlobal
0x18004212b  call    cs:__imp_CreateStreamOnHGlobal
0x180042132  nop     dword ptr [rax+rax+00h]
0x180042137  mov     edi, eax
0x180042139  test    eax, eax
0x18004213b  jns     short loc_1800421AD
0x18004213d  mov     rcx, [rbp+38h]; this
0x180042141  mov     r9d, eax; char *
0x180042144  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18004214b  mov     edx, 46Bh; void *
0x180042150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042155  nop
0x180042156  lea     rcx, [rbp+ppstm]
0x18004215a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004215f  nop
0x180042160  lea     rcx, [rbp+ppOutput]
0x180042164  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042169  nop
0x18004216a  lea     rcx, [rbp+ppvObject]
0x18004216e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042173  nop
0x180042174  mov     rax, [rbp+pv]
0x180042178  test    rax, rax
0x18004217b  jz      loc_1800420F1
0x180042181  cmp     dword ptr [rbp+arg_0], 0
0x180042185  jbe     loc_1800420E2
0x18004218b  mov     ecx, ebx
0x18004218d  mov     rcx, [rax+rcx*8]; bstrString
0x180042191  call    cs:__imp_SysFreeString
0x180042198  nop     dword ptr [rax+rax+00h]
0x18004219d  inc     ebx
0x18004219f  mov     rax, [rbp+pv]
0x1800421a3  cmp     ebx, dword ptr [rbp+arg_0]
0x1800421a6  jb      short loc_18004218B
0x1800421a8  jmp     loc_1800420E2
0x1800421ad  lea     rcx, [rbp+ppvObject]
0x1800421b1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800421b6  xor     r8d, r8d; pMalloc
0x1800421b9  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800421bd  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800421c4  call    cs:__imp_CreateXmlWriter
0x1800421cb  nop     dword ptr [rax+rax+00h]
0x1800421d0  mov     edi, eax
0x1800421d2  test    eax, eax
0x1800421d4  jns     short loc_180042246
0x1800421d6  mov     rcx, [rbp+38h]; this
0x1800421da  mov     r9d, eax; char *
0x1800421dd  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800421e4  mov     edx, 46Ch; void *
0x1800421e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800421ee  nop
0x1800421ef  lea     rcx, [rbp+ppstm]
0x1800421f3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800421f8  nop
0x1800421f9  lea     rcx, [rbp+ppOutput]
0x1800421fd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042202  nop
0x180042203  lea     rcx, [rbp+ppvObject]
0x180042207  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004220c  nop
0x18004220d  mov     rax, [rbp+pv]
0x180042211  test    rax, rax
0x180042214  jz      loc_1800420F1
0x18004221a  cmp     dword ptr [rbp+arg_0], 0
0x18004221e  jbe     loc_1800420E2
0x180042224  mov     ecx, ebx
0x180042226  mov     rcx, [rax+rcx*8]; bstrString
0x18004222a  call    cs:__imp_SysFreeString
0x180042231  nop     dword ptr [rax+rax+00h]
0x180042236  inc     ebx
0x180042238  mov     rax, [rbp+pv]
0x18004223c  cmp     ebx, dword ptr [rbp+arg_0]
0x18004223f  jb      short loc_180042224
0x180042241  jmp     loc_1800420E2
0x180042246  lea     rcx, [rbp+ppOutput]
0x18004224a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004224f  lea     r9, [rbp+ppOutput]; ppOutput
0x180042253  lea     r8, pwszEncodingName; "UTF-16"
0x18004225a  xor     edx, edx; pMalloc
0x18004225c  mov     rcx, [rbp+ppstm]; pOutputStream
0x180042260  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180042267  nop     dword ptr [rax+rax+00h]
0x18004226c  mov     edi, eax
0x18004226e  test    eax, eax
0x180042270  jns     short loc_1800422E2
0x180042272  mov     rcx, [rbp+38h]; this
0x180042276  mov     r9d, eax; char *
0x180042279  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180042280  mov     edx, 46Dh; void *
0x180042285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004228a  nop
0x18004228b  lea     rcx, [rbp+ppstm]
0x18004228f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042294  nop
0x180042295  lea     rcx, [rbp+ppOutput]
0x180042299  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004229e  nop
0x18004229f  lea     rcx, [rbp+ppvObject]
0x1800422a3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800422a8  nop
0x1800422a9  mov     rax, [rbp+pv]
0x1800422ad  test    rax, rax
0x1800422b0  jz      loc_1800420F1
0x1800422b6  cmp     dword ptr [rbp+arg_0], 0
0x1800422ba  jbe     loc_1800420E2
0x1800422c0  mov     ecx, ebx
0x1800422c2  mov     rcx, [rax+rcx*8]; bstrString
0x1800422c6  call    cs:__imp_SysFreeString
0x1800422cd  nop     dword ptr [rax+rax+00h]
0x1800422d2  inc     ebx
0x1800422d4  mov     rax, [rbp+pv]
0x1800422d8  cmp     ebx, dword ptr [rbp+arg_0]
0x1800422db  jb      short loc_1800422C0
0x1800422dd  jmp     loc_1800420E2
0x1800422e2  mov     rcx, [rbp+ppvObject]
0x1800422e6  mov     rax, [rcx]
0x1800422e9  mov     rdx, [rbp+ppOutput]
0x1800422ed  mov     rax, [rax+18h]
0x1800422f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422f6  mov     edi, eax
0x1800422f8  test    eax, eax
0x1800422fa  jns     short loc_18004236C
0x1800422fc  mov     rcx, [rbp+38h]; this
0x180042300  mov     r9d, eax; char *
0x180042303  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18004230a  mov     edx, 46Eh; void *
0x18004230f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042314  nop
0x180042315  lea     rcx, [rbp+ppstm]
0x180042319  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004231e  nop
0x18004231f  lea     rcx, [rbp+ppOutput]
0x180042323  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042328  nop
0x180042329  lea     rcx, [rbp+ppvObject]
0x18004232d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180042332  nop
0x180042333  mov     rax, [rbp+pv]
0x180042337  test    rax, rax
0x18004233a  jz      loc_1800420F1
0x180042340  cmp     dword ptr [rbp+arg_0], 0
0x180042344  jbe     loc_1800420E2
0x18004234a  mov     ecx, ebx
0x18004234c  mov     rcx, [rax+rcx*8]; bstrString
0x180042350  call    cs:__imp_SysFreeString
0x180042357  nop     dword ptr [rax+rax+00h]
0x18004235c  inc     ebx
0x18004235e  mov     rax, [rbp+pv]
0x180042362  cmp     ebx, dword ptr [rbp+arg_0]
0x180042365  jb      short loc_18004234A
0x180042367  jmp     loc_1800420E2
0x18004236c  mov     rcx, [rbp+ppvObject]
0x180042370  mov     rax, [rcx]
0x180042373  mov     edx, 4
0x180042378  lea     r8d, [rdx-3]
0x18004237c  mov     rax, [rax+28h]
0x180042380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042385  mov     edi, eax
0x180042387  test    eax, eax
0x180042389  jns     short loc_1800423FB
0x18004238b  mov     rcx, [rbp+38h]; this
0x18004238f  mov     r9d, eax; char *
0x180042392  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180042399  mov     edx, 470h; void *
0x18004239e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800423a3  nop
0x1800423a4  lea     rcx, [rbp+ppstm]
0x1800423a8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800423ad  nop
0x1800423ae  lea     rcx, [rbp+ppOutput]
0x1800423b2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800423b7  nop
0x1800423b8  lea     rcx, [rbp+ppvObject]
0x1800423bc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800423c1  nop
0x1800423c2  mov     rax, [rbp+pv]
0x1800423c6  test    rax, rax
0x1800423c9  jz      loc_1800420F1
0x1800423cf  cmp     dword ptr [rbp+arg_0], 0
0x1800423d3  jbe     loc_1800420E2
0x1800423d9  mov     ecx, ebx
0x1800423db  mov     rcx, [rax+rcx*8]; bstrString
0x1800423df  call    cs:__imp_SysFreeString
0x1800423e6  nop     dword ptr [rax+rax+00h]
0x1800423eb  inc     ebx
0x1800423ed  mov     rax, [rbp+pv]
0x1800423f1  cmp     ebx, dword ptr [rbp+arg_0]
0x1800423f4  jb      short loc_1800423D9
0x1800423f6  jmp     loc_1800420E2
0x1800423fb  mov     rcx, [rbp+ppvObject]
0x1800423ff  mov     rax, [rcx]
0x180042402  xor     r8d, r8d
0x180042405  lea     edx, [r8+2]
0x180042409  mov     rax, [rax+28h]
0x18004240d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042412  mov     edi, eax
0x180042414  test    eax, eax
0x180042416  jns     short loc_180042488
0x180042418  mov     rcx, [rbp+38h]; this
0x18004241c  mov     r9d, eax; char *
0x18004241f  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180042426  mov     edx, 471h; void *
0x18004242b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042430  nop
  ... truncated ...
```
