# EapSetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *)

- ea: `0x18002dd30`
- end: `0x18002e05a`
- name: `?EapSetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2@Z`
- size: `810`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e118`

## callees

- `0x18002dc94`
- `0x18002dcb8`
- `0x18002dd10`
- `0x18002dd30`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002def0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002def0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002df53`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002df53`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002df38`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002df38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dea0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e01b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e01b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002de80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002debd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002de80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002debd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ddb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ddb9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002df0f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002df0f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e037`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e037`
- `OLEAUT32!__imp_VariantInit` at `0x18002dd63`
- `OLEAUT32!__imp_VariantInit` at `0x18002dd63`
- `OLEAUT32!__imp_VariantClear` at `0x18002dda3`
- `OLEAUT32!__imp_VariantClear` at `0x18002defc`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfb1`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfbf`
- `OLEAUT32!__imp_VariantClear` at `0x18002e02e`
- `OLEAUT32!__imp_VariantClear` at `0x18002dda3`
- `OLEAUT32!__imp_VariantClear` at `0x18002defc`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfb1`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfbf`
- `OLEAUT32!__imp_VariantClear` at `0x18002e02e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002de4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002de4a`

## string_xrefs

- `0x18002ddae`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mschapv2connectionpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1' xmlns:help='http://www.microsoft.com/provisioning/Help' xmlns:locations='http://www.microsoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.com/provisioning/Master' xmlns:register='http://www.microsoft.com`

## pseudocode

```c
__int64 __fastcall EapSetNsAndSchema(
        struct IXMLDOMDocument2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4)
{
  int v5; // ecx
  OLECHAR *v6; // rbx
  WCHAR *v7; // rsi
  HRESULT (__stdcall *setProperty)(IXMLDOMDocument2 *, BSTR, VARIANT); // rax
  HRESULT v9; // edi
  int i; // r14d
  DWORD v11; // eax
  DWORD v12; // edi
  DWORD v13; // r13d
  WCHAR *v14; // rax
  UINT v15; // edi
  BSTR v16; // rax
  __int64 v17; // rax
  LPVOID v18; // rdi
  HRESULT (__stdcall *putref_schemas)(IXMLDOMDocument2 *, VARIANT); // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpSrc[3]; // [rsp+48h] [rbp-38h]
  VARIANTARG v23; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp+58h] BYREF

  ppv = a3;
  bstrString = 0;
  VariantInit(&pvarg);
  ppv = 0;
  lpSrc[0] = L"%windir%\\schemas\\EAPHost\\";
  lpSrc[2] = 0;
  lpSrc[1] = L"%windir%\\schemas\\EAPMethods\\";
  ATL::CComBSTR::operator=(&bstrString, L"SelectionNamespaces");
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(
                            L"xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionprope"
                             "rtiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mschapv"
                             "2connectionpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2ConnectionProperties"
                             "V1' xmlns:help='http://www.microsoft.com/provisioning/Help' xmlns:locations='http://www.mic"
                             "rosoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.com/provisioning/Mast"
                             "er' xmlns:register='http://www.microsoft.com/provisioning/Register' xmlns:ssid='http://www."
                             "microsoft.com/provisioning/SSID'");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(v5);
  }
  v6 = bstrString;
  v7 = 0;
  if ( bstrString )
  {
    setProperty = a1->lpVtbl->setProperty;
    v23 = pvarg;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, VARIANTARG *))setProperty)(a1, bstrString, &v23);
    if ( v9 >= 0 )
    {
      v9 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection2, &ppv);
      if ( v9 >= 0 )
      {
        for ( i = 0; (&g_wszNsArray)[i]; ++i )
        {
          v11 = ExpandEnvironmentStringsW(lpSrc[i], 0, 0);
          v12 = v11;
          if ( !v11 )
          {
            v9 = -2147467259;
            goto LABEL_17;
          }
          v13 = v11;
          v14 = (WCHAR *)LocalAlloc(0x40u, 2LL * v11);
          v7 = v14;
          if ( !v14 )
            goto LABEL_21;
          if ( ExpandEnvironmentStringsW(lpSrc[i], v14, v12) > v12 )
          {
            v9 = -2147467259;
            goto LABEL_22;
          }
          ATL::CComBSTR::operator=(&bstrString, (&g_wszNsArray)[i]);
          v15 = wcsnlen((const wchar_t *)(&g_wszSchemaUriArray)[i], 0x400u) + v12;
          VariantClear(&pvarg);
          pvarg.vt = 8;
          v16 = SysAllocStringLen(0, v15);
          v6 = bstrString;
          pvarg.llVal = (LONGLONG)v16;
          if ( !bstrString || !v16 )
            goto LABEL_21;
          _o_wcscpy_s(v16, v13, v7);
          _o_wcscat_s(pvarg.llVal, v15, (&g_wszSchemaUriArray)[i]);
          v17 = *(_QWORD *)ppv;
          v23 = pvarg;
          v9 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v17 + 56))(ppv, v6, &v23);
          if ( v9 < 0 )
            goto LABEL_22;
          LocalFree(v7);
        }
        VariantClear(&pvarg);
        v18 = ppv;
        VariantClear(&pvarg);
        pvarg.llVal = (LONGLONG)v18;
        pvarg.vt = 9;
        if ( v18 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 8LL))(v18);
        putref_schemas = a1->lpVtbl->putref_schemas;
        v23 = pvarg;
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))putref_schemas)(a1, &v23);
LABEL_17:
        v7 = 0;
      }
    }
  }
  else
  {
LABEL_21:
    v9 = -2147024882;
  }
LABEL_22:
  LocalFree(v7);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&ppv);
  VariantClear(&pvarg);
  SysFreeString(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002dd30  mov     [rsp-38h+arg_0], rbx
0x18002dd35  mov     [rsp-38h+bstrString], r9
0x18002dd3a  mov     [rsp-38h+arg_10], r8
0x18002dd3f  push    rbp
0x18002dd40  push    rsi
0x18002dd41  push    rdi
0x18002dd42  push    r12
0x18002dd44  push    r13
0x18002dd46  push    r14
0x18002dd48  push    r15
0x18002dd4a  mov     rbp, rsp
0x18002dd4d  sub     rsp, 80h
0x18002dd54  mov     r12, rcx
0x18002dd57  mov     [rbp+bstrString], 0
0x18002dd5f  lea     rcx, [rbp+pvarg]; pvarg
0x18002dd63  call    cs:__imp_VariantInit
0x18002dd69  lea     rax, aWindirSchemasE_0; "%windir%\\schemas\\EAPHost\\"
0x18002dd70  mov     [rbp+arg_10], 0
0x18002dd78  mov     [rbp+lpSrc], rax
0x18002dd7c  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002dd83  lea     rax, aWindirSchemasE; "%windir%\\schemas\\EAPMethods\\"
0x18002dd8a  mov     [rbp+var_28], 0
0x18002dd92  lea     rcx, [rbp+bstrString]
0x18002dd96  mov     [rbp+var_30], rax
0x18002dd9a  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002dd9f  lea     rcx, [rbp+pvarg]; pvarg
0x18002dda3  call    cs:__imp_VariantClear
0x18002dda9  mov     eax, 8
0x18002ddae  lea     rcx, psz; "xmlns:branding='http://www.microsoft.co"...
0x18002ddb5  mov     word ptr [rbp+pvarg], ax
0x18002ddb9  call    cs:__imp_SysAllocString
0x18002ddbf  mov     qword ptr [rbp+pvarg+8], rax
0x18002ddc3  test    rax, rax
0x18002ddc6  jnz     short loc_18002DDDF
0x18002ddc8  mov     eax, 0Ah
0x18002ddcd  mov     edi, 8007000Eh
0x18002ddd2  mov     word ptr [rbp+pvarg], ax
0x18002ddd6  mov     dword ptr [rbp+pvarg+8], edi
0x18002ddd9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002dddf  mov     rbx, [rbp+bstrString]
0x18002dde3  xor     esi, esi
0x18002dde5  test    rbx, rbx
0x18002dde8  jz      loc_18002E013
0x18002ddee  test    rax, rax
0x18002ddf1  jz      loc_18002E013
0x18002ddf7  mov     rax, [r12]
0x18002ddfb  lea     r8, [rbp+var_20]
0x18002ddff  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002de03  mov     rdx, rbx
0x18002de06  mov     rcx, r12
0x18002de09  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002de0e  mov     rax, [rax+280h]
0x18002de15  movaps  [rbp+var_20], xmm0
0x18002de19  movsd   [rbp+var_10], xmm1
0x18002de1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de23  mov     edi, eax
0x18002de25  test    eax, eax
0x18002de27  js      loc_18002E018
0x18002de2d  lea     rax, [rbp+arg_10]
0x18002de31  xor     edx, edx; pUnkOuter
0x18002de33  lea     r9, IID_IXMLDOMSchemaCollection2; riid
0x18002de3a  mov     [rsp+80h+ppv], rax; ppv
0x18002de3f  lea     r8d, [rsi+1]; dwClsContext
0x18002de43  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x18002de4a  call    cs:__imp_CoCreateInstance
0x18002de50  mov     edi, eax
0x18002de52  test    eax, eax
0x18002de54  js      loc_18002E018
0x18002de5a  xor     r14d, r14d
0x18002de5d  movsxd  r15, r14d
0x18002de60  lea     rax, __ImageBase
0x18002de67  cmp     rva ?g_wszNsArray@@3PAPEBGA[rax+r15*8], 0; ushort const * near * g_wszNsArray ...
0x18002de70  jz      loc_18002DFAD
0x18002de76  mov     rcx, [rbp+r15*8+lpSrc]; lpSrc
0x18002de7b  xor     r8d, r8d; nSize
0x18002de7e  xor     edx, edx; lpDst
0x18002de80  call    cs:__imp_ExpandEnvironmentStringsW
0x18002de86  mov     edi, eax
0x18002de88  test    eax, eax
0x18002de8a  jz      loc_18002DFA4
0x18002de90  lea     rdx, ds:0[rdi*2]; uBytes
0x18002de98  mov     ecx, 40h ; '@'; uFlags
0x18002de9d  mov     r13d, edi
0x18002dea0  call    cs:__imp_LocalAlloc
0x18002dea6  mov     rsi, rax
0x18002dea9  test    rax, rax
0x18002deac  jz      loc_18002E013
0x18002deb2  mov     rcx, [rbp+r15*8+lpSrc]; lpSrc
0x18002deb7  mov     r8d, edi; nSize
0x18002deba  mov     rdx, rax; lpDst
0x18002debd  call    cs:__imp_ExpandEnvironmentStringsW
0x18002dec3  cmp     eax, edi
0x18002dec5  ja      loc_18002DF9D
0x18002decb  lea     rbx, __ImageBase
0x18002ded2  mov     rdx, rva ?g_wszNsArray@@3PAPEBGA[rbx+r15*8]; ushort const * near * g_wszNsArray ...
0x18002deda  lea     rcx, [rbp+bstrString]
0x18002dede  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002dee3  mov     rcx, rva ?g_wszSchemaUriArray@@3PAPEBGA[rbx+r15*8]; Source
0x18002deeb  mov     edx, 400h; MaxCount
0x18002def0  call    cs:__imp_wcsnlen
0x18002def6  lea     rcx, [rbp+pvarg]; pvarg
0x18002defa  add     edi, eax
0x18002defc  call    cs:__imp_VariantClear
0x18002df02  mov     eax, 8
0x18002df07  mov     edx, edi; ui
0x18002df09  xor     ecx, ecx; strIn
0x18002df0b  mov     word ptr [rbp+pvarg], ax
0x18002df0f  call    cs:__imp_SysAllocStringLen
0x18002df15  mov     rbx, [rbp+bstrString]
0x18002df19  mov     qword ptr [rbp+pvarg+8], rax
0x18002df1d  test    rbx, rbx
0x18002df20  jz      loc_18002E013
0x18002df26  test    rax, rax
0x18002df29  jz      loc_18002E013
0x18002df2f  mov     r8, rsi
0x18002df32  mov     edx, r13d
0x18002df35  mov     rcx, rax
0x18002df38  call    cs:__imp__o_wcscpy_s
0x18002df3e  mov     rcx, qword ptr [rbp+pvarg+8]
0x18002df42  lea     r8, __ImageBase
0x18002df49  mov     r8, rva ?g_wszSchemaUriArray@@3PAPEBGA[r8+r15*8]; ushort const * near * g_wszSchemaUriArray ...
0x18002df51  mov     edx, edi
0x18002df53  call    cs:__imp__o_wcscat_s
0x18002df59  mov     rcx, [rbp+arg_10]
0x18002df5d  lea     r8, [rbp+var_20]
0x18002df61  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002df65  mov     rdx, rbx
0x18002df68  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002df6d  mov     rax, [rcx]
0x18002df70  movaps  [rbp+var_20], xmm0
0x18002df74  movsd   [rbp+var_10], xmm1
0x18002df79  mov     rax, [rax+38h]
0x18002df7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df82  mov     edi, eax
0x18002df84  test    eax, eax
0x18002df86  js      loc_18002E018
0x18002df8c  mov     rcx, rsi; hMem
0x18002df8f  call    cs:__imp_LocalFree
0x18002df95  inc     r14d
0x18002df98  jmp     loc_18002DE5D
0x18002df9d  mov     edi, 80004005h
0x18002dfa2  jmp     short loc_18002E018
0x18002dfa4  mov     edi, 80004005h
0x18002dfa9  xor     esi, esi
0x18002dfab  jmp     short loc_18002E018
0x18002dfad  lea     rcx, [rbp+pvarg]; pvarg
0x18002dfb1  call    cs:__imp_VariantClear
0x18002dfb7  mov     rdi, [rbp+arg_10]
0x18002dfbb  lea     rcx, [rbp+pvarg]; pvarg
0x18002dfbf  call    cs:__imp_VariantClear
0x18002dfc5  mov     qword ptr [rbp+pvarg+8], rdi
0x18002dfc9  mov     eax, 9
0x18002dfce  mov     word ptr [rbp+pvarg], ax
0x18002dfd2  test    rdi, rdi
0x18002dfd5  jz      short loc_18002DFE6
0x18002dfd7  mov     rax, [rdi]
0x18002dfda  mov     rcx, rdi
0x18002dfdd  mov     rax, [rax+8]
0x18002dfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfe6  mov     rax, [r12]
0x18002dfea  lea     rdx, [rbp+var_20]
0x18002dfee  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002dff2  mov     rcx, r12
0x18002dff5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002dffa  mov     rax, [rax+270h]
0x18002e001  movaps  [rbp+var_20], xmm0
0x18002e005  movsd   [rbp+var_10], xmm1
0x18002e00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e00f  mov     edi, eax
0x18002e011  jmp     short loc_18002DFA9
0x18002e013  mov     edi, 8007000Eh
0x18002e018  mov     rcx, rsi; hMem
0x18002e01b  call    cs:__imp_LocalFree
0x18002e021  lea     rcx, [rbp+arg_10]
0x18002e025  call    ??1?$CComPtrBase@UIXMLDOMSchemaCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(void)
0x18002e02a  lea     rcx, [rbp+pvarg]; pvarg
0x18002e02e  call    cs:__imp_VariantClear
0x18002e034  mov     rcx, rbx; bstrString
0x18002e037  call    cs:__imp_SysFreeString
0x18002e03d  mov     rbx, [rsp+80h+arg_0]
0x18002e045  mov     eax, edi
0x18002e047  add     rsp, 80h
0x18002e04e  pop     r15
0x18002e050  pop     r14
0x18002e052  pop     r13
0x18002e054  pop     r12
0x18002e056  pop     rdi
0x18002e057  pop     rsi
0x18002e058  pop     rbp
0x18002e059  retn
```
