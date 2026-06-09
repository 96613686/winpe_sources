# ParseConfigXmlFile

- ea: `0x1800072ec`
- end: `0x180007b77`
- name: `ParseConfigXmlFile`
- size: `2187`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003ff0`

## callees

- `0x18000384c`
- `0x180004f68`
- `0x1800072ec`
- `0x180008f24`
- `0x180020dbc`
- `0x18002c050`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180007994`
- `msvcrt!wcscpy_s` at `0x180007994`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007979`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007979`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800075f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800075f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180007653`
- `OLEAUT32!__imp_SysAllocString` at `0x180007680`
- `OLEAUT32!__imp_SysAllocString` at `0x180007738`
- `OLEAUT32!__imp_SysAllocString` at `0x18000779b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800077bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180007844`
- `OLEAUT32!__imp_SysAllocString` at `0x180007653`
- `OLEAUT32!__imp_SysAllocString` at `0x180007680`
- `OLEAUT32!__imp_SysAllocString` at `0x180007738`
- `OLEAUT32!__imp_SysAllocString` at `0x18000779b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800077bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180007844`
- `OLEAUT32!__imp_SysFreeString` at `0x18000782f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007923`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a08`
- `OLEAUT32!__imp_SysFreeString` at `0x18000782f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007923`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a08`
- `OLEAUT32!__imp_VariantInit` at `0x1800074d6`
- `OLEAUT32!__imp_VariantInit` at `0x1800074e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800074ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800074f4`
- `OLEAUT32!__imp_VariantInit` at `0x1800074d6`
- `OLEAUT32!__imp_VariantInit` at `0x1800074e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800074ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800074f4`
- `OLEAUT32!__imp_VariantClear` at `0x180007a52`
- `OLEAUT32!__imp_VariantClear` at `0x180007a5c`
- `OLEAUT32!__imp_VariantClear` at `0x180007a66`
- `OLEAUT32!__imp_VariantClear` at `0x180007a70`
- `OLEAUT32!__imp_VariantClear` at `0x180007a52`
- `OLEAUT32!__imp_VariantClear` at `0x180007a5c`
- `OLEAUT32!__imp_VariantClear` at `0x180007a66`
- `OLEAUT32!__imp_VariantClear` at `0x180007a70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800075af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800075dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800075af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800075dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000757a`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000757a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007a90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007a90`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000753a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000753a`

## string_xrefs

- `0x18000734e`: `//d3c:DCCloneConfig/SiteName`
- `0x18000736d`: `//d3c:DCCloneConfig/ComputerName`
- `0x1800073a1`: `//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/Address`
- `0x1800073dc`: `//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/SubnetMask`
- `0x180007404`: `//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/DefaultGateway`
- `0x180007428`: `//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/DNSResolver`
- `0x18000732e`: `//d3c:DCCloneConfig/IPSettings/IPv4Settings/DynamicSettings/DNSResolver`
- `0x180007448`: `//d3c:DCCloneConfig/IPSettings/IPv6Settings/StaticSettings/DNSResolver`
- `0x18000745d`: `//d3c:DCCloneConfig/IPSettings/IPv6Settings/DynamicSettings/DNSResolver`
- `0x18000751f`: `vDC Cloning: Clone config file %ws is considered to be a blank file (containing %d bytes)\n`
- `0x18000762a`: `DCCloneConfigSchema.xsd`
- `0x18000764c`: `uri:microsoft.com:schemas:DCCloneConfig`
- `0x1800076be`: `IXMLDOCSchemaCollection::add failed, schema path: %ws: error: 0x%x\n`
- `0x180007723`: `IXMLDOMDocument::putref_schemas failed, schema path: %ws: error: 0x%x\n`
- `0x180007b1c`: `Failed to load CloneConfig XML, error: 0x%x\n`
- `0x1800077b0`: `xmlns:d3c='uri:microsoft.com:schemas:DCCloneConfig'`
- `0x180007804`: `IXMLDOMDocument::setProperty(SelectionNamespaces) failed, error: 0x%x\n`
- `0x180007ac5`: `IXMLDOMNodeList::get_item() failed, error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall ParseConfigXmlFile(OLECHAR *psz, __int64 a2)
{
  char v3; // r15
  OLECHAR *v4; // rsi
  OLECHAR *v5; // rbx
  OLECHAR *v6; // r13
  int FileSize; // eax
  int SystemDirectoryW; // edi
  HRESULT v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  unsigned int i; // r14d
  const OLECHAR *v18; // r15
  int v19; // r9d
  wchar_t **v20; // r12
  _DWORD *v21; // rbx
  unsigned int j; // r15d
  int v23; // eax
  __int64 v24; // rax
  wchar_t *v25; // rax
  int v27; // ebx
  unsigned int v28; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v29; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v38; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v40; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG v41; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v42; // [rsp+108h] [rbp+8h] BYREF
  OLECHAR *psza; // [rsp+120h] [rbp+20h]
  _DWORD v44[2]; // [rsp+128h] [rbp+28h]
  __int64 v45; // [rsp+130h] [rbp+30h]
  _QWORD v46[2]; // [rsp+138h] [rbp+38h]
  int v47; // [rsp+148h] [rbp+48h]
  __int64 v48; // [rsp+150h] [rbp+50h]
  __int64 v49; // [rsp+158h] [rbp+58h]
  const wchar_t *v50; // [rsp+160h] [rbp+60h]
  int v51; // [rsp+168h] [rbp+68h]
  __int64 v52; // [rsp+170h] [rbp+70h]
  __int64 v53; // [rsp+178h] [rbp+78h]
  const wchar_t *v54; // [rsp+180h] [rbp+80h]
  int v55; // [rsp+188h] [rbp+88h]
  __int64 v56; // [rsp+190h] [rbp+90h]
  __int64 v57; // [rsp+198h] [rbp+98h]
  const wchar_t *v58; // [rsp+1A0h] [rbp+A0h]
  int v59; // [rsp+1A8h] [rbp+A8h]
  __int64 v60; // [rsp+1B0h] [rbp+B0h]
  __int64 v61; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v62; // [rsp+1C0h] [rbp+C0h]
  int v63; // [rsp+1C8h] [rbp+C8h]
  __int64 v64; // [rsp+1D0h] [rbp+D0h]
  __int64 v65; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v66; // [rsp+1E0h] [rbp+E0h]
  int v67; // [rsp+1E8h] [rbp+E8h]
  __int64 v68; // [rsp+1F0h] [rbp+F0h]
  __int64 v69; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v70; // [rsp+200h] [rbp+100h]
  int v71; // [rsp+208h] [rbp+108h]
  __int64 v72; // [rsp+210h] [rbp+110h]
  __int64 v73; // [rsp+218h] [rbp+118h]
  const wchar_t *v74; // [rsp+220h] [rbp+120h]
  int v75; // [rsp+228h] [rbp+128h]
  __int64 v76; // [rsp+230h] [rbp+130h]
  __int64 v77; // [rsp+238h] [rbp+138h]
  WCHAR Buffer[264]; // [rsp+240h] [rbp+140h] BYREF

  v45 = a2;
  v28 = 0;
  v44[0] = 1;
  psza = L"//d3c:DCCloneConfig/SiteName";
  v47 = 1;
  v46[0] = a2 + 8;
  v51 = 1;
  v46[1] = L"//d3c:DCCloneConfig/ComputerName";
  v3 = 0;
  v55 = 1;
  v48 = a2 + 16;
  v4 = 0;
  v59 = 1;
  v49 = a2 + 24;
  v64 = a2 + 80;
  v50 = L"//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/Address";
  v5 = 0;
  v68 = a2 + 80;
  v52 = a2 + 32;
  ppv = 0;
  v53 = a2 + 40;
  v6 = 0;
  v35 = 0;
  v54 = L"//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/SubnetMask";
  v56 = a2 + 48;
  v57 = a2 + 56;
  v58 = L"//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/DefaultGateway";
  v60 = a2 + 64;
  v61 = a2 + 72;
  v62 = L"//d3c:DCCloneConfig/IPSettings/IPv4Settings/StaticSettings/DNSResolver";
  v65 = a2 + 112;
  v69 = a2 + 112;
  v70 = L"//d3c:DCCloneConfig/IPSettings/IPv6Settings/StaticSettings/DNSResolver";
  v36 = 0;
  v74 = L"//d3c:DCCloneConfig/IPSettings/IPv6Settings/DynamicSettings/DNSResolver";
  v34 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  v29 = 0;
  memset(&v40, 0, sizeof(v40));
  v63 = 4;
  memset(&v41, 0, sizeof(v41));
  v66 = L"//d3c:DCCloneConfig/IPSettings/IPv4Settings/DynamicSettings/DNSResolver";
  memset(&v42, 0, sizeof(v42));
  v67 = 4;
  v71 = 4;
  v72 = a2 + 128;
  v73 = a2 + 160;
  v76 = a2 + 128;
  v75 = 4;
  v77 = a2 + 160;
  v31 = 0;
  VariantInit(&pvarg);
  VariantInit(&v40);
  VariantInit(&v41);
  VariantInit(&v42);
  FileSize = DsRolepGetFileSize(psz, &v28);
  SystemDirectoryW = FileSize;
  if ( FileSize )
  {
    if ( FileSize > 0 )
      SystemDirectoryW = (unsigned __int16)FileSize | 0x80070000;
  }
  else
  {
    if ( v28 <= 4 )
    {
      DsRolepLogPrintRoutine(
        4,
        "vDC Cloning: Clone config file %ws is considered to be a blank file (containing %d bytes)\n",
        psz);
      SystemDirectoryW = 0;
      goto LABEL_57;
    }
    SystemDirectoryW = CoInitializeEx(0, 0);
    if ( (unsigned int)SystemDirectoryW <= 1 )
    {
      v3 = 1;
      v9 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
      SystemDirectoryW = v9;
      if ( v9 == -2147417831 || !v9 )
      {
        SystemDirectoryW = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, &ppv);
        if ( !SystemDirectoryW )
        {
          SystemDirectoryW = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 0x15u, &IID_IXMLDOMSchemaCollection, &v36);
          if ( SystemDirectoryW >= 0 )
          {
            SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
            if ( SystemDirectoryW >= 0 )
            {
              SystemDirectoryW = StringCchCatW(Buffer, 0x104u, L"\\");
              if ( SystemDirectoryW >= 0 )
              {
                SystemDirectoryW = StringCchCatW(Buffer, 0x104u, L"DCCloneConfigSchema.xsd");
                if ( SystemDirectoryW >= 0 )
                {
                  v30 = SysAllocString(L"uri:microsoft.com:schemas:DCCloneConfig");
                  v5 = v30;
                  if ( v30 )
                  {
                    v40.vt = 8;
                    v40.llVal = (LONGLONG)SysAllocString(Buffer);
                    if ( v40.llVal )
                    {
                      v10 = *(_QWORD *)v36;
                      v38 = v40;
                      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v10 + 56))(v36, v5, &v38);
                      SystemDirectoryW = v11;
                      if ( v11 < 0 )
                      {
                        DsRolepLogPrintRoutine(
                          1,
                          "IXMLDOCSchemaCollection::add failed, schema path: %ws: error: 0x%x\n",
                          Buffer,
                          (unsigned int)v11);
                        goto LABEL_57;
                      }
                      v41.vt = 13;
                      v41.llVal = (LONGLONG)v36;
                      v36 = 0;
                      v12 = *(_QWORD *)ppv;
                      v38 = v41;
                      v13 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(v12 + 624))(ppv, &v38);
                      SystemDirectoryW = v13;
                      if ( v13 < 0 )
                      {
                        DsRolepLogPrintRoutine(
                          1,
                          "IXMLDOMDocument::putref_schemas failed, schema path: %ws: error: 0x%x\n",
                          Buffer,
                          (unsigned int)v13);
                        goto LABEL_57;
                      }
                      pvarg.vt = 8;
                      pvarg.llVal = (LONGLONG)SysAllocString(psz);
                      if ( pvarg.llVal )
                      {
                        v14 = *(_QWORD *)ppv;
                        v38 = pvarg;
                        v28 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v14 + 464))(ppv, &v38, &v29);
                        SystemDirectoryW = v28;
                        if ( v28 || !v29 )
                        {
                          v37 = 0;
                          v27 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 480LL))(ppv, &v37);
                          DsRolepLogPrintRoutine(1, "Failed to load CloneConfig XML, error: 0x%x\n", SystemDirectoryW);
                          if ( v27 >= 0 )
                          {
                            DsRoleReportXmlError(v37, &v28);
                            if ( v37 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                            SystemDirectoryW = v28;
                          }
LABEL_56:
                          v5 = v30;
                          goto LABEL_57;
                        }
                        v6 = SysAllocString(L"SelectionNamespaces");
                        if ( v6 )
                        {
                          v42.vt = SystemDirectoryW + 8;
                          v42.llVal = (LONGLONG)SysAllocString(L"xmlns:d3c='uri:microsoft.com:schemas:DCCloneConfig'");
                          if ( v42.llVal )
                          {
                            v15 = *(_QWORD *)ppv;
                            v38 = v42;
                            v16 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v15 + 640))(
                                    ppv,
                                    v6,
                                    &v38);
                            SystemDirectoryW = v16;
                            if ( v16 )
                            {
                              DsRolepLogPrintRoutine(
                                1,
                                "IXMLDOMDocument::setProperty(SelectionNamespaces) failed, error: 0x%x\n",
                                v16);
                              goto LABEL_57;
                            }
                            for ( i = 0; i < 9; ++i )
                            {
                              if ( v4 )
                                SysFreeString(v4);
                              v18 = *(const OLECHAR **)&v44[8 * i - 2];
                              v4 = SysAllocString(v18);
                              if ( !v4 )
                              {
LABEL_54:
                                SystemDirectoryW = -2147024882;
                                break;
                              }
                              if ( v34 )
                              {
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                                v34 = 0;
                              }
                              if ( (*(unsigned int (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 288LL))(
                                     ppv,
                                     v4,
                                     &v34)
                                || (SystemDirectoryW = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 64LL))(
                                                         v34,
                                                         &v31)) != 0 )
                              {
                                SystemDirectoryW = 0;
                              }
                              else
                              {
                                v19 = v31;
                                if ( v31 > v44[8 * i] )
                                {
                                  DsRolepLogPrintRoutine(1, "%ws node count (%d) > expected maxOccurs (%d)\n", v18);
                                  SystemDirectoryW = -2147467259;
                                  break;
                                }
                                v20 = (wchar_t **)v46[4 * i - 1];
                                v21 = (_DWORD *)v46[4 * i];
                                for ( j = 0; (int)j < v19; ++j )
                                {
                                  if ( v35 )
                                  {
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                                    v35 = 0;
                                  }
                                  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 56LL))(
                                          v34,
                                          j,
                                          &v35);
                                  SystemDirectoryW = v23;
                                  if ( v23 )
                                  {
                                    DsRolepLogPrintRoutine(1, "IXMLDOMNodeList::get_item() failed, error: 0x%x\n", v23);
                                    goto LABEL_55;
                                  }
                                  if ( bstrString )
                                  {
                                    SysFreeString(bstrString);
                                    bstrString = 0;
                                  }
                                  SystemDirectoryW = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 208LL))(
                                                       v35,
                                                       &bstrString);
                                  if ( SystemDirectoryW )
                                  {
                                    SystemDirectoryW = 0;
                                  }
                                  else
                                  {
                                    v24 = -1;
                                    do
                                      ++v24;
                                    while ( bstrString[v24] );
                                    *v21 = v24;
                                    if ( (_DWORD)v24 )
                                    {
                                      v25 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned int)(v24 + 1));
                                      *v20 = v25;
                                      if ( !v25 )
                                      {
                                        *v21 = 0;
                                        goto LABEL_54;
                                      }
                                      wcscpy_s(v25, (unsigned int)(*v21 + 1), bstrString);
                                      ++v20;
                                      ++v21;
                                    }
                                  }
                                  v19 = v31;
                                }
                              }
                            }
LABEL_55:
                            v3 = 1;
                            goto LABEL_56;
                          }
                        }
                      }
                    }
                  }
                  SystemDirectoryW = -2147024882;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_57:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v4 )
    SysFreeString(v4);
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SysFreeString(v6);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  VariantClear(&pvarg);
  VariantClear(&v40);
  VariantClear(&v41);
  VariantClear(&v42);
  if ( v36 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v3 )
    CoUninitialize();
  return (unsigned int)SystemDirectoryW;
}

```

## disassembly

```asm
0x1800072ec  mov     [rsp-8+arg_10], rbx
0x1800072f1  push    rbp
0x1800072f2  push    rsi
0x1800072f3  push    rdi
0x1800072f4  push    r12
0x1800072f6  push    r13
0x1800072f8  push    r14
0x1800072fa  push    r15
0x1800072fc  lea     rbp, [rsp-360h]
0x180007304  sub     rsp, 460h
0x18000730b  mov     rax, cs:__security_cookie
0x180007312  xor     rax, rsp
0x180007315  mov     [rbp+390h+var_40], rax
0x18000731c  xor     r12d, r12d
0x18000731f  mov     [rbp+390h+var_360], rdx
0x180007323  xor     eax, eax
0x180007325  mov     [rsp+490h+var_43C], r12d
0x18000732a  mov     qword ptr [rbp+390h+pvarg+10h], rax
0x18000732e  lea     r8, aD3cDccloneconf_5; "//d3c:DCCloneConfig/IPSettings/IPv4Sett"...
0x180007335  mov     qword ptr [rbp+390h+var_3B8+10h], rax
0x180007339  mov     r14, rcx
0x18000733c  mov     qword ptr [rbp+390h+var_3A0+10h], rax
0x180007340  lea     ecx, [r12+1]
0x180007345  mov     qword ptr [rbp+390h+var_388+10h], rax
0x180007349  lea     r9d, [r12+4]
0x18000734e  lea     rax, aD3cDccloneconf_3; "//d3c:DCCloneConfig/SiteName"
0x180007355  mov     [rbp+390h+var_368], ecx
0x180007358  mov     [rbp+390h+psz], rax
0x18000735c  xorps   xmm0, xmm0
0x18000735f  lea     rax, [rdx+8]
0x180007363  mov     [rbp+390h+var_348], ecx
0x180007366  mov     [rbp+390h+var_358], rax
0x18000736a  xorps   xmm1, xmm1
0x18000736d  lea     rax, aD3cDccloneconf; "//d3c:DCCloneConfig/ComputerName"
0x180007374  mov     [rbp+390h+var_328], ecx
0x180007377  mov     [rbp+390h+var_350], rax
0x18000737b  mov     r15b, r12b
0x18000737e  lea     rax, [rdx+10h]
0x180007382  mov     [rbp+390h+var_308], ecx
0x180007388  mov     [rbp+390h+var_340], rax
0x18000738c  mov     esi, r12d
0x18000738f  lea     rax, [rdx+18h]
0x180007393  mov     [rbp+390h+var_2E8], ecx
0x180007399  mov     [rbp+390h+var_338], rax
0x18000739d  lea     rcx, [rdx+50h]
0x1800073a1  lea     rax, aD3cDccloneconf_1; "//d3c:DCCloneConfig/IPSettings/IPv4Sett"...
0x1800073a8  mov     [rbp+390h+var_2C0], rcx
0x1800073af  mov     [rbp+390h+var_330], rax
0x1800073b3  mov     ebx, r12d
0x1800073b6  lea     rax, [rdx+20h]
0x1800073ba  mov     [rbp+390h+var_2A0], rcx
0x1800073c1  mov     [rbp+390h+var_320], rax
0x1800073c5  lea     rcx, [rdx+80h]
0x1800073cc  lea     rax, [rdx+28h]
0x1800073d0  mov     [rsp+490h+ppv], r12
0x1800073d5  mov     [rbp+390h+var_318], rax
0x1800073d9  mov     r13d, r12d
0x1800073dc  lea     rax, aD3cDccloneconf_7; "//d3c:DCCloneConfig/IPSettings/IPv4Sett"...
0x1800073e3  mov     [rbp+390h+var_408], r12
0x1800073e7  mov     [rbp+390h+var_310], rax
0x1800073ee  lea     rax, [rdx+30h]
0x1800073f2  mov     [rbp+390h+var_300], rax
0x1800073f9  lea     rax, [rdx+38h]
0x1800073fd  mov     [rbp+390h+var_2F8], rax
0x180007404  lea     rax, aD3cDccloneconf_4; "//d3c:DCCloneConfig/IPSettings/IPv4Sett"...
0x18000740b  mov     [rbp+390h+var_2F0], rax
0x180007412  lea     rax, [rdx+40h]
0x180007416  mov     [rbp+390h+var_2E0], rax
0x18000741d  lea     rax, [rdx+48h]
0x180007421  mov     [rbp+390h+var_2D8], rax
0x180007428  lea     rax, aD3cDccloneconf_0; "//d3c:DCCloneConfig/IPSettings/IPv4Sett"...
0x18000742f  mov     [rbp+390h+var_2D0], rax
0x180007436  lea     rax, [rdx+70h]
0x18000743a  mov     [rbp+390h+var_2B8], rax
0x180007441  mov     [rbp+390h+var_298], rax
0x180007448  lea     rax, aD3cDccloneconf_2; "//d3c:DCCloneConfig/IPSettings/IPv6Sett"...
0x18000744f  mov     [rbp+390h+var_290], rax
0x180007456  lea     rax, [rdx+0A0h]
0x18000745d  lea     rdx, aD3cDccloneconf_6; "//d3c:DCCloneConfig/IPSettings/IPv6Sett"...
0x180007464  mov     [rbp+390h+var_400], r12
0x180007468  mov     [rbp+390h+var_270], rdx
0x18000746f  mov     [rbp+390h+var_410], r12
0x180007473  movups  xmmword ptr [rbp+390h+pvarg], xmm0
0x180007477  mov     [rsp+490h+bstrString], r12
0x18000747c  mov     [rsp+490h+var_438], r12w
0x180007482  movups  xmmword ptr [rbp+390h+var_3B8], xmm0
0x180007486  mov     [rbp+390h+var_2C8], r9d
0x18000748d  movups  xmmword ptr [rbp+390h+var_3A0], xmm1
0x180007491  mov     [rbp+390h+var_2B0], r8
0x180007498  movups  xmmword ptr [rbp+390h+var_388], xmm0
0x18000749c  mov     [rbp+390h+var_2A8], r9d
0x1800074a3  mov     [rbp+390h+var_288], r9d
0x1800074aa  mov     [rbp+390h+var_280], rcx
0x1800074b1  mov     [rbp+390h+var_278], rax
0x1800074b8  mov     [rbp+390h+var_260], rcx
0x1800074bf  lea     rcx, [rbp+390h+pvarg]; pvarg
0x1800074c3  mov     [rbp+390h+var_268], r9d
0x1800074ca  mov     [rbp+390h+var_258], rax
0x1800074d1  mov     [rsp+490h+var_428], r12d
0x1800074d6  call    cs:__imp_VariantInit
0x1800074dc  lea     rcx, [rbp+390h+var_3B8]; pvarg
0x1800074e0  call    cs:__imp_VariantInit
0x1800074e6  lea     rcx, [rbp+390h+var_3A0]; pvarg
0x1800074ea  call    cs:__imp_VariantInit
0x1800074f0  lea     rcx, [rbp+390h+var_388]; pvarg
0x1800074f4  call    cs:__imp_VariantInit
0x1800074fa  lea     rdx, [rsp+490h+var_43C]
0x1800074ff  mov     rcx, r14
0x180007502  call    DsRolepGetFileSize
0x180007507  mov     edi, eax
0x180007509  test    eax, eax
0x18000750b  jnz     loc_180007B63
0x180007511  mov     r9d, [rsp+490h+var_43C]
0x180007516  cmp     r9d, 4
0x18000751a  ja      short loc_180007536
0x18000751c  mov     r8, r14
0x18000751f  lea     rdx, aVdcCloningClon_1; "vDC Cloning: Clone config file %ws is c"...
0x180007526  lea     ecx, [rax+4]
0x180007529  call    DsRolepLogPrintRoutine
0x18000752e  mov     edi, r12d
0x180007531  jmp     loc_1800079D4
0x180007536  xor     edx, edx; dwCoInit
0x180007538  xor     ecx, ecx; pvReserved
0x18000753a  call    cs:__imp_CoInitializeEx
0x180007540  mov     edi, eax
0x180007542  cmp     eax, 1
0x180007545  ja      loc_1800079D4
0x18000754b  mov     [rsp+490h+pReserved3], r12; pReserved3
0x180007550  mov     r15b, 1
0x180007553  mov     [rsp+490h+dwCapabilities], r12d; dwCapabilities
0x180007558  xor     r9d, r9d; pReserved1
0x18000755b  mov     [rsp+490h+pAuthList], r12; pAuthList
0x180007560  xor     r8d, r8d; asAuthSvc
0x180007563  mov     [rsp+490h+dwImpLevel], 3; dwImpLevel
0x18000756b  or      edx, 0FFFFFFFFh; cAuthSvc
0x18000756e  xor     ecx, ecx; pSecDesc
0x180007570  mov     [rsp+490h+dwAuthnLevel], r12d; dwAuthnLevel
0x180007575  mov     [rsp+490h+var_440], r15b
0x18000757a  call    cs:__imp_CoInitializeSecurity
0x180007580  mov     edi, eax
0x180007582  cmp     eax, 80010119h
0x180007587  jz      short loc_180007591
0x180007589  test    eax, eax
0x18000758b  jnz     loc_1800079D4
0x180007591  xor     edx, edx; pUnkOuter
0x180007593  lea     rax, [rsp+490h+ppv]
0x180007598  lea     r9, IID_IXMLDOMDocument3; riid
0x18000759f  mov     qword ptr [rsp+490h+dwAuthnLevel], rax; ppv
0x1800075a4  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800075ab  lea     r8d, [rdx+1]; dwClsContext
0x1800075af  call    cs:__imp_CoCreateInstance
0x1800075b5  mov     edi, eax
0x1800075b7  test    eax, eax
0x1800075b9  jnz     loc_1800079D4
0x1800075bf  lea     rax, [rbp+390h+var_400]
0x1800075c3  xor     edx, edx; pUnkOuter
0x1800075c5  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x1800075cc  mov     qword ptr [rsp+490h+dwAuthnLevel], rax; ppv
0x1800075d1  lea     r8d, [rdi+15h]; dwClsContext
0x1800075d5  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x1800075dc  call    cs:__imp_CoCreateInstance
0x1800075e2  mov     edi, eax
0x1800075e4  test    eax, eax
0x1800075e6  js      loc_1800079D4
0x1800075ec  mov     edx, 104h; uSize
0x1800075f1  lea     rcx, [rbp+390h+Buffer]; lpBuffer
0x1800075f8  call    cs:__imp_GetSystemDirectoryW
0x1800075fe  mov     edi, eax
0x180007600  test    eax, eax
0x180007602  js      loc_1800079D4
0x180007608  lea     r8, pszSrc; "\\"
0x18000760f  mov     edx, 104h; cchDest
0x180007614  lea     rcx, [rbp+390h+Buffer]; pszDest
0x18000761b  call    StringCchCatW
0x180007620  mov     edi, eax
0x180007622  test    eax, eax
0x180007624  js      loc_1800079D4
0x18000762a  lea     r8, aDccloneconfigs; "DCCloneConfigSchema.xsd"
0x180007631  mov     edx, 104h; cchDest
0x180007636  lea     rcx, [rbp+390h+Buffer]; pszDest
0x18000763d  call    StringCchCatW
0x180007642  mov     edi, eax
0x180007644  test    eax, eax
0x180007646  js      loc_1800079D4
0x18000764c  lea     rcx, aUriMicrosoftCo_0; "uri:microsoft.com:schemas:DCCloneConfig"
0x180007653  call    cs:__imp_SysAllocString
0x180007659  mov     [rsp+490h+var_430], rax
0x18000765e  mov     rbx, rax
0x180007661  test    rax, rax
0x180007664  jnz     short loc_180007670
0x180007666  mov     edi, 8007000Eh
0x18000766b  jmp     loc_1800079D4
0x180007670  mov     eax, 8
0x180007675  lea     rcx, [rbp+390h+Buffer]; psz
0x18000767c  mov     word ptr [rbp+390h+var_3B8], ax
0x180007680  call    cs:__imp_SysAllocString
0x180007686  mov     qword ptr [rbp+390h+var_3B8+8], rax
0x18000768a  test    rax, rax
0x18000768d  jz      short loc_180007666
0x18000768f  mov     rcx, [rbp+390h+var_400]
0x180007693  lea     r8, [rbp+390h+var_3F0]
0x180007697  movups  xmm0, xmmword ptr [rbp+390h+var_3B8]
0x18000769b  mov     rdx, rbx
0x18000769e  movsd   xmm1, qword ptr [rbp+390h+var_3B8+10h]
0x1800076a3  mov     rax, [rcx]
0x1800076a6  movaps  [rbp+390h+var_3F0], xmm0
0x1800076aa  movsd   [rbp+390h+var_3E0], xmm1
0x1800076af  mov     rax, [rax+38h]
0x1800076b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b8  mov     edi, eax
0x1800076ba  test    eax, eax
0x1800076bc  jns     short loc_1800076DE
0x1800076be  lea     rdx, aIxmldocschemac; "IXMLDOCSchemaCollection::add failed, sc"...
0x1800076c5  lea     r8, [rbp+390h+Buffer]
0x1800076cc  mov     r9d, eax
0x1800076cf  mov     ecx, 1
0x1800076d4  call    DsRolepLogPrintRoutine
0x1800076d9  jmp     loc_1800079D4
0x1800076de  mov     rcx, [rsp+490h+ppv]
0x1800076e3  lea     rdx, [rbp+390h+var_3F0]
0x1800076e7  movsd   xmm1, qword ptr [rbp+390h+var_3A0+10h]
0x1800076ec  mov     eax, 0Dh
0x1800076f1  mov     word ptr [rbp+390h+var_3A0], ax
0x1800076f5  mov     rax, [rbp+390h+var_400]
0x1800076f9  mov     qword ptr [rbp+390h+var_3A0+8], rax
0x1800076fd  movups  xmm0, xmmword ptr [rbp+390h+var_3A0]
0x180007701  mov     [rbp+390h+var_400], r12
0x180007705  mov     rax, [rcx]
0x180007708  movaps  [rbp+390h+var_3F0], xmm0
0x18000770c  movsd   [rbp+390h+var_3E0], xmm1
0x180007711  mov     rax, [rax+270h]
0x180007718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771d  mov     edi, eax
0x18000771f  test    eax, eax
0x180007721  jns     short loc_18000772C
0x180007723  lea     rdx, aIxmldomdocumen; "IXMLDOMDocument::putref_schemas failed,"...
0x18000772a  jmp     short loc_1800076C5
0x18000772c  mov     eax, 8
0x180007731  mov     rcx, r14; psz
0x180007734  mov     word ptr [rbp+390h+pvarg], ax
0x180007738  call    cs:__imp_SysAllocString
0x18000773e  mov     qword ptr [rbp+390h+pvarg+8], rax
0x180007742  test    rax, rax
0x180007745  jz      loc_180007666
0x18000774b  mov     rcx, [rsp+490h+ppv]
0x180007750  lea     r8, [rsp+490h+var_438]
0x180007755  movups  xmm0, xmmword ptr [rbp+390h+pvarg]
0x180007759  lea     rdx, [rbp+390h+var_3F0]
0x18000775d  movsd   xmm1, qword ptr [rbp+390h+pvarg+10h]
0x180007762  mov     rax, [rcx]
0x180007765  movaps  [rbp+390h+var_3F0], xmm0
0x180007769  movsd   [rbp+390h+var_3E0], xmm1
0x18000776e  mov     rax, [rax+1D0h]
0x180007775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777a  mov     [rsp+490h+var_43C], eax
0x18000777e  mov     edi, eax
0x180007780  test    eax, eax
0x180007782  jnz     loc_180007AFD
0x180007788  cmp     [rsp+490h+var_438], r12w
0x18000778e  jz      loc_180007AFD
0x180007794  lea     rcx, psz; "SelectionNamespaces"
0x18000779b  call    cs:__imp_SysAllocString
0x1800077a1  mov     r13, rax
0x1800077a4  test    rax, rax
0x1800077a7  jz      loc_180007666
0x1800077ad  lea     eax, [rdi+8]
0x1800077b0  lea     rcx, aXmlnsD3cUriMic; "xmlns:d3c='uri:microsoft.com:schemas:DC"...
0x1800077b7  mov     word ptr [rbp+390h+var_388], ax
0x1800077bb  call    cs:__imp_SysAllocString
0x1800077c1  mov     qword ptr [rbp+390h+var_388+8], rax
0x1800077c5  test    rax, rax
0x1800077c8  jz      loc_180007666
0x1800077ce  mov     rcx, [rsp+490h+ppv]
0x1800077d3  lea     r8, [rbp+390h+var_3F0]
0x1800077d7  movups  xmm0, xmmword ptr [rbp+390h+var_388]
0x1800077db  mov     rdx, r13
0x1800077de  movsd   xmm1, qword ptr [rbp+390h+var_388+10h]
0x1800077e3  mov     rax, [rcx]
0x1800077e6  movaps  [rbp+390h+var_3F0], xmm0
0x1800077ea  movsd   [rbp+390h+var_3E0], xmm1
0x1800077ef  mov     rax, [rax+280h]
0x1800077f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fb  mov     edi, eax
0x1800077fd  test    eax, eax
0x1800077ff  jz      short loc_18000781A
0x180007801  mov     r8d, eax
0x180007804  lea     rdx, aIxmldomdocumen_0; "IXMLDOMDocument::setProperty(SelectionN"...
0x18000780b  mov     ecx, 1
0x180007810  call    DsRolepLogPrintRoutine
0x180007815  jmp     loc_1800079D4
0x18000781a  mov     r14d, r12d
0x18000781d  cmp     r14d, 9
0x180007821  jnb     loc_1800079CA
0x180007827  test    rsi, rsi
0x18000782a  jz      short loc_180007835
0x18000782c  mov     rcx, rsi; bstrString
0x18000782f  call    cs:__imp_SysFreeString
0x180007835  mov     ebx, r14d
0x180007838  shl     rbx, 5
0x18000783c  mov     r15, [rbp+rbx+390h+psz]
  ... truncated ...
```
