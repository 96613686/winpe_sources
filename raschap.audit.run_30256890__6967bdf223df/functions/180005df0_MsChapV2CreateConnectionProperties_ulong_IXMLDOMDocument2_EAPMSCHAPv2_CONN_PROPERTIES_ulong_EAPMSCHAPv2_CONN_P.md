# MsChapV2CreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_CONN_PROPERTIES * *,ulong *)

- ea: `0x180005df0`
- end: `0x1800065ef`
- name: `?MsChapV2CreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z`
- size: `2047`
- prototype: `unsigned int(unsigned int, struct IXMLDOMDocument2 *, struct _EAPMSCHAPv2_CONN_PROPERTIES *, unsigned int, struct _EAPMSCHAPv2_CONN_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004ac0`
- `0x18001cf30`

## callees

- `0x1800014c0`
- `0x180003bd0`
- `0x180004df0`
- `0x180005df0`
- `0x180006600`
- `0x180006a20`
- `0x180007060`
- `0x18000ea70`
- `0x1800147cc`
- `0x180017e80`
- `0x18001cbbc`
- `0x180025efc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006117`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006586`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006117`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006586`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000609e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000619c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000609e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000619c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000643d`
- `OLEAUT32!__imp_SysAllocString` at `0x180005f48`
- `OLEAUT32!__imp_SysAllocString` at `0x180006145`
- `OLEAUT32!__imp_SysAllocString` at `0x1800061b9`
- `OLEAUT32!__imp_SysAllocString` at `0x180005f48`
- `OLEAUT32!__imp_SysAllocString` at `0x180006145`
- `OLEAUT32!__imp_SysAllocString` at `0x1800061b9`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000618c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180006291`
- `OLEAUT32!__imp_SysFreeString` at `0x18000633f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000634d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000618c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180006291`
- `OLEAUT32!__imp_SysFreeString` at `0x18000633f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000634d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006236`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000624f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006268`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006478`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006236`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000624f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006268`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006478`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180005fde`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180005fde`

## string_xrefs

- `0x180005e2a`: `http://www.microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1`
- `0x180005e5b`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mschapv2connectionpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1' xmlns:help='http://www.microsoft.com/provisioning/Help' xmlns:locations='http://www.microsoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.com/provisioning/Master' xmlns:register='http://www.microsoft.com`
- `0x180005e1f`: `http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MsChapV2CreateConnectionProperties(
        char a1,
        struct IXMLDOMDocument2 *a2,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a3,
        unsigned int a4,
        struct _EAPMSCHAPv2_CONN_PROPERTIES **a5,
        unsigned int *a6)
{
  SIZE_T v6; // r14
  void *v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  unsigned int v15; // eax
  __int64 v16; // rdi
  BSTR v17; // rax
  int v18; // ecx
  OLECHAR *v19; // rbx
  _DWORD *v20; // rax
  _DWORD *v21; // rbx
  int v22; // edi
  _DWORD *v23; // rax
  DWORD LastError; // eax
  _QWORD *v25; // rcx
  __int64 v26; // r14
  const WCHAR *v27; // rax
  int v28; // ecx
  OLECHAR *v29; // rbx
  void *v30; // r15
  _DWORD *v31; // r14
  BSTR v32; // r12
  const WCHAR *v33; // rax
  int v34; // ecx
  OLECHAR *v35; // rbx
  char v36; // dl
  unsigned int v37; // ecx
  __int64 v38; // rdx
  __int64 v39; // rdx
  DWORD v40; // eax
  const char *v41; // r9
  LPCWSTR lpString1; // [rsp+20h] [rbp-59h] BYREF
  BSTR v43; // [rsp+28h] [rbp-51h] BYREF
  __int64 v44; // [rsp+30h] [rbp-49h] BYREF
  __int64 v45; // [rsp+38h] [rbp-41h] BYREF
  __int64 v46; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v47[3]; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v48[12]; // [rsp+60h] [rbp-19h] BYREF

  v6 = a4;
  v10 = 0;
  v45 = 0;
  v46 = 0;
  v48[0] = L"http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1";
  v48[1] = L"http://www.microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1";
  v48[2] = 0;
  v47[0] = L"BaseEapConnectionPropertiesV1.xsd";
  v47[1] = L"MsChapV2ConnectionPropertiesV1.xsd";
  v47[2] = 0;
  v11 = SetNsAndSchema(
          a2,
          L"xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://ww"
           "w.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mschapv2connectionpropertiesv1='http://www."
           "microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1' xmlns:help='http://www.microsoft.com/provisioning/"
           "Help' xmlns:locations='http://www.microsoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.co"
           "m/provisioning/Master' xmlns:register='http://www.microsoft.com/provisioning/Register' xmlns:ssid='http://www"
           ".microsoft.com/provisioning/SSID'",
          (const unsigned __int16 **)v48,
          (const unsigned __int16 **)v47);
  if ( v11 )
  {
    v12 = (unsigned __int16)v11;
    if ( (v11 & 0x1FFF0000) != 0x70000 )
      v12 = v11;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v38 = 40;
LABEL_83:
    WPP_SF_d(v13[2], v38, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v11);
    goto LABEL_5;
  }
  v11 = validate(a2);
  if ( v11 )
  {
    v12 = (unsigned __int16)v11;
    if ( (v11 & 0x1FFF0000) != 0x70000 )
      v12 = v11;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v38 = 41;
      goto LABEL_83;
    }
  }
  else
  {
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IXMLDOMNode,
            &v46);
    v12 = v15;
    if ( !v15 )
    {
      v16 = v46;
      v17 = SysAllocString(L"/baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=26][1]");
      v19 = v17;
      v43 = v17;
      if ( !v17 )
        ATL::AtlThrowImpl(v18);
      if ( (*(unsigned int (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v16 + 296LL))(v16, v17, &v45) || !v45 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_47d2ae5abdbe322473422603828ba620_Traceguids,
            L"/baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=26][1]");
        SysFreeString(v19);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
        v12 = 87;
        goto LABEL_27;
      }
      SysFreeString(v19);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
      if ( (unsigned int)v6 >= 8 && a3 )
      {
        v23 = LocalAlloc(0x40u, v6);
        v21 = v23;
        if ( v23 )
        {
          memcpy_0(v23, a3, v6);
          v12 = 13;
          if ( !(unsigned int)IsLogonCredAllowed() )
            v21[1] &= ~2u;
LABEL_37:
          v10 = v21;
          LocalFree(0);
          goto LABEL_47;
        }
        LastError = GetLastError();
        v12 = LastError;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = 14;
LABEL_89:
          WPP_SF_d(v25[2], v39, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
        }
      }
      else
      {
        v20 = LocalAlloc(0x40u, 8u);
        v21 = v20;
        if ( v20 )
        {
          v22 = 0;
          *v20 = 1;
          if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
          {
            if ( !(unsigned int)RasChapExt_GetConfigForceNotDomainJoined() )
              v22 = isMachineJoinedToDomain();
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
          }
          if ( a1 < 0 && ((a1 & 0x20) != 0 || v22) && (unsigned int)IsLogonCredAllowed() )
          {
            v12 = 13;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
            v21[1] = 2;
          }
          else
          {
            v12 = 13;
          }
          goto LABEL_37;
        }
        LastError = GetLastError();
        v12 = LastError;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = 11;
          goto LABEL_89;
        }
      }
      LocalFree(0);
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v12);
        goto LABEL_71;
      }
      v12 = 13;
LABEL_47:
      v43 = 0;
      v44 = 0;
      v26 = v45;
      v27 = SysAllocString(L"mschapv2connectionpropertiesv1:EapType[1]");
      v29 = (OLECHAR *)v27;
      lpString1 = v27;
      if ( !v27 )
        ATL::AtlThrowImpl(v28);
      v30 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, const WCHAR *, BSTR *))(*(_QWORD *)v26 + 296LL))(v26, v27, &v43)
        || !v43 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_47d2ae5abdbe322473422603828ba620_Traceguids,
            L"mschapv2connectionpropertiesv1:EapType[1]");
        SysFreeString(v29);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
        v12 = 87;
        goto LABEL_64;
      }
      SysFreeString(v29);
      v31 = LocalAlloc(0x40u, 8u);
      if ( !v31 )
      {
        v12 = 14;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v40 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v40);
        }
        goto LABEL_64;
      }
      v32 = v43;
      v33 = SysAllocString(L"mschapv2connectionpropertiesv1:UseWinLogonCredentials[1]");
      v35 = (OLECHAR *)v33;
      lpString1 = v33;
      if ( !v33 )
        ATL::AtlThrowImpl(v34);
      if ( (*(unsigned int (__fastcall **)(BSTR, const WCHAR *, __int64 *))(*(_QWORD *)v32 + 296LL))(v32, v33, &v44)
        || !v44 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_47d2ae5abdbe322473422603828ba620_Traceguids,
            L"mschapv2connectionpropertiesv1:UseWinLogonCredentials[1]");
        SysFreeString(v35);
        v31[1] |= 2u;
        goto LABEL_62;
      }
      SysFreeString(v35);
      v48[3] = 0;
      lpString1 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v44 + 208LL))(v44, &lpString1) )
      {
        if ( !lstrcmpiW(lpString1, L"true") || !lstrcmpiW(lpString1, L"1") )
        {
          v36 = 1;
          goto LABEL_59;
        }
        if ( !lstrcmpiW(lpString1, L"false") || !lstrcmpiW(lpString1, L"0") )
        {
          v36 = 0;
LABEL_59:
          v37 = v31[1] | 2;
          if ( !v36 )
            v37 = v31[1] & 0xFFFFFFFD;
          v31[1] = v37;
          SysFreeString((BSTR)lpString1);
LABEL_62:
          v12 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v41 = "Yes";
            if ( (v31[1] & 2) == 0 )
              v41 = "No";
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v41);
          }
          *v31 = 1;
          v30 = v31;
LABEL_64:
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          if ( v43 )
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v43 + 16LL))(v43);
          if ( v12 )
          {
            if ( v30 )
              LocalFree(v30);
          }
          else if ( v30 )
          {
            *a5 = (struct _EAPMSCHAPv2_CONN_PROPERTIES *)v30;
            *a6 = 8;
          }
LABEL_71:
          if ( v10 )
            LocalFree(v10);
          goto LABEL_5;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
      SysFreeString(0);
      goto LABEL_64;
    }
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v15;
  }
LABEL_5:
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
    goto LABEL_8;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v12);
LABEL_8:
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  return v12;
}

```

## disassembly

```asm
0x180005df0  push    rbp
0x180005df2  push    rbx
0x180005df3  push    rsi
0x180005df4  push    rdi
0x180005df5  push    r12
0x180005df7  push    r13
0x180005df9  push    r14
0x180005dfb  push    r15
0x180005dfd  lea     rbp, [rsp-0Fh]
0x180005e02  sub     rsp, 88h
0x180005e09  mov     r14d, r9d
0x180005e0c  mov     r12, r8
0x180005e0f  mov     rbx, rdx
0x180005e12  mov     r15d, ecx
0x180005e15  xor     esi, esi
0x180005e17  mov     [rbp+47h+var_88], rsi
0x180005e1b  mov     [rbp+47h+var_80], rsi
0x180005e1f  lea     rax, aHttpWwwMicroso_1; "http://www.microsoft.com/provisioning/B"...
0x180005e26  mov     [rbp+47h+var_60], rax
0x180005e2a  lea     rax, aHttpWwwMicroso_0; "http://www.microsoft.com/provisioning/M"...
0x180005e31  mov     [rbp+47h+var_58], rax
0x180005e35  mov     [rbp+47h+var_50], rsi
0x180005e39  lea     rax, aBaseeapconnect_0; "BaseEapConnectionPropertiesV1.xsd"
0x180005e40  mov     [rbp+47h+var_78], rax
0x180005e44  lea     rax, aMschapv2connec_0; "MsChapV2ConnectionPropertiesV1.xsd"
0x180005e4b  mov     [rbp+47h+var_70], rax
0x180005e4f  mov     [rbp+47h+var_68], rsi
0x180005e53  lea     r9, [rbp+47h+var_78]; unsigned __int16 **
0x180005e57  lea     r8, [rbp+47h+var_60]; unsigned __int16 **
0x180005e5b  lea     rdx, aXmlnsBrandingH; "xmlns:branding='http://www.microsoft.co"...
0x180005e62  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180005e65  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *)
0x180005e6a  lea     r13, WPP_GLOBAL_Control
0x180005e71  test    eax, eax
0x180005e73  jz      loc_180005F0A
0x180005e79  mov     ecx, eax
0x180005e7b  and     ecx, 1FFF0000h
0x180005e81  cmp     ecx, 70000h
0x180005e87  movzx   edi, ax
0x180005e8a  jz      short loc_180005E8E
0x180005e8c  mov     edi, eax
0x180005e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e95  cmp     rcx, r13
0x180005e98  jnz     loc_1800063AF
0x180005e9e  test    edi, edi
0x180005ea0  jnz     loc_180005FFB
0x180005ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ead  cmp     rcx, r13
0x180005eb0  jz      short loc_180005EC8
0x180005eb2  mov     edx, 2Ch ; ','
0x180005eb7  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180005ebe  mov     rcx, [rcx+10h]
0x180005ec2  call    WPP_SF_
0x180005ec7  nop
0x180005ec8  mov     rcx, [rbp+47h+var_80]
0x180005ecc  test    rcx, rcx
0x180005ecf  jz      short loc_180005EDE
0x180005ed1  mov     rax, [rcx]
0x180005ed4  mov     rax, [rax+10h]
0x180005ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005edd  nop
0x180005ede  mov     rcx, [rbp+47h+var_88]
0x180005ee2  test    rcx, rcx
0x180005ee5  jz      short loc_180005EF4
0x180005ee7  mov     rdx, [rcx]
0x180005eea  mov     rax, [rdx+10h]
0x180005eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef3  nop
0x180005ef4  mov     eax, edi
0x180005ef6  add     rsp, 88h
0x180005efd  pop     r15
0x180005eff  pop     r14
0x180005f01  pop     r13
0x180005f03  pop     r12
0x180005f05  pop     rdi
0x180005f06  pop     rsi
0x180005f07  pop     rbx
0x180005f08  pop     rbp
0x180005f09  retn
0x180005f0a  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180005f0d  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x180005f12  test    eax, eax
0x180005f14  jnz     loc_18000636D
0x180005f1a  mov     rax, [rbx]
0x180005f1d  lea     r8, [rbp+47h+var_80]
0x180005f21  lea     rdx, IID_IXMLDOMNode
0x180005f28  mov     rcx, rbx
0x180005f2b  mov     rax, [rax]
0x180005f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f33  mov     edi, eax
0x180005f35  test    eax, eax
0x180005f37  jnz     loc_180006028
0x180005f3d  mov     rdi, [rbp+47h+var_80]
0x180005f41  lea     rcx, aBaseeapconnect; "/baseeapconnectionpropertiesv1:Eap[base"...
0x180005f48  call    cs:__imp_SysAllocString
0x180005f4e  mov     rbx, rax
0x180005f51  mov     [rbp+47h+var_98], rax
0x180005f55  test    rax, rax
0x180005f58  jz      loc_1800063B6
0x180005f5e  mov     rax, [rdi]
0x180005f61  lea     r8, [rbp+47h+var_88]
0x180005f65  mov     rdx, rbx
0x180005f68  mov     rcx, rdi
0x180005f6b  mov     rax, [rax+128h]
0x180005f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f77  test    eax, eax
0x180005f79  jnz     loc_180006591
0x180005f7f  cmp     [rbp+47h+var_88], 0
0x180005f84  jz      loc_180006591
0x180005f8a  mov     rcx, rbx; bstrString
0x180005f8d  call    cs:__imp_SysFreeString
0x180005f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f9a  cmp     rcx, r13
0x180005f9d  jnz     loc_180006307
0x180005fa3  cmp     r14d, 8
0x180005fa7  jnb     loc_18000608D
0x180005fad  mov     edx, 8; uBytes
0x180005fb2  mov     ecx, 40h ; '@'; uFlags
0x180005fb7  call    cs:__imp_LocalAlloc
0x180005fbd  mov     rbx, rax
0x180005fc0  test    rax, rax
0x180005fc3  jz      loc_1800060FC
0x180005fc9  xor     edi, edi
0x180005fcb  mov     dword ptr [rax], 1
0x180005fd1  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x180005fd6  test    al, al
0x180005fd8  jz      loc_1800060D2
0x180005fde  call    cs:__imp_RasChapExt_GetConfigForceNotDomainJoined
0x180005fe4  test    eax, eax
0x180005fe6  jz      loc_180006321
0x180005fec  test    r15b, r15b
0x180005fef  js      short loc_180006040
0x180005ff1  mov     edi, 0Dh
0x180005ff6  jmp     loc_18000607D
0x180005ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006002  cmp     rcx, r13
0x180006005  jz      loc_180005EC8
0x18000600b  mov     edx, 2Dh ; '-'
0x180006010  mov     r9d, edi
0x180006013  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18000601a  mov     rcx, [rcx+10h]
0x18000601e  call    WPP_SF_d
0x180006023  jmp     loc_180005EC8
0x180006028  and     eax, 1FFF0000h
0x18000602d  cmp     eax, 70000h
0x180006032  jnz     loc_180005E9E
0x180006038  movzx   edi, di
0x18000603b  jmp     loc_180005E9E
0x180006040  test    r15b, 20h
0x180006044  jnz     short loc_18000604A
0x180006046  test    edi, edi
0x180006048  jz      short loc_180005FF1
0x18000604a  call    IsLogonCredAllowed
0x18000604f  test    eax, eax
0x180006051  jz      short loc_180005FF1
0x180006053  mov     edi, 0Dh
0x180006058  mov     rcx, cs:WPP_GLOBAL_Control
0x18000605f  cmp     rcx, r13
0x180006062  jz      short loc_180006076
0x180006064  mov     edx, edi
0x180006066  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x18000606d  mov     rcx, [rcx+10h]
0x180006071  call    WPP_SF_
0x180006076  mov     dword ptr [rbx+4], 2
0x18000607d  mov     rsi, rbx
0x180006080  xor     ecx, ecx; hMem
0x180006082  call    cs:__imp_LocalFree
0x180006088  jmp     loc_18000612A
0x18000608d  test    r12, r12
0x180006090  jz      loc_180005FAD
0x180006096  mov     rdx, r14; uBytes
0x180006099  mov     ecx, 40h ; '@'; uFlags
0x18000609e  call    cs:__imp_LocalAlloc
0x1800060a4  mov     rbx, rax
0x1800060a7  test    rax, rax
0x1800060aa  jz      loc_1800063BC
0x1800060b0  mov     r8, r14; Size
0x1800060b3  mov     rdx, r12; Src
0x1800060b6  mov     rcx, rax; void *
0x1800060b9  call    memcpy_0
0x1800060be  call    IsLogonCredAllowed
0x1800060c3  mov     edi, 0Dh
0x1800060c8  test    eax, eax
0x1800060ca  jnz     short loc_18000607D
0x1800060cc  and     dword ptr [rbx+4], 0FFFFFFFDh
0x1800060d0  jmp     short loc_18000607D
0x1800060d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060d9  cmp     rcx, r13
0x1800060dc  jz      loc_180005FEC
0x1800060e2  mov     edx, 0Ch
0x1800060e7  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800060ee  mov     rcx, [rcx+10h]
0x1800060f2  call    WPP_SF_
0x1800060f7  jmp     loc_180005FEC
0x1800060fc  call    cs:__imp_GetLastError
0x180006102  mov     edi, eax
0x180006104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000610b  cmp     rcx, r13
0x18000610e  jnz     loc_1800063DB
0x180006114  mov     rcx, rbx; hMem
0x180006117  call    cs:__imp_LocalFree
0x18000611d  test    edi, edi
0x18000611f  jnz     loc_1800063F8
0x180006125  mov     edi, 0Dh
0x18000612a  mov     [rbp+47h+var_98], 0
0x180006132  mov     [rbp+47h+var_90], 0
0x18000613a  mov     r14, [rbp+47h+var_88]
0x18000613e  lea     rcx, aMschapv2connec; "mschapv2connectionpropertiesv1:EapType["...
0x180006145  call    cs:__imp_SysAllocString
0x18000614b  mov     rbx, rax
0x18000614e  mov     [rbp+47h+lpString1], rax
0x180006152  test    rax, rax
0x180006155  jz      loc_180006425
0x18000615b  xor     r15d, r15d
0x18000615e  mov     rax, [r14]
0x180006161  lea     r8, [rbp+47h+var_98]
0x180006165  mov     rdx, rbx
0x180006168  mov     rcx, r14
0x18000616b  mov     rax, [rax+128h]
0x180006172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006177  test    eax, eax
0x180006179  jnz     loc_180006519
0x18000617f  cmp     [rbp+47h+var_98], r15
0x180006183  jz      loc_180006519
0x180006189  mov     rcx, rbx; bstrString
0x18000618c  call    cs:__imp_SysFreeString
0x180006192  mov     edx, 8; uBytes
0x180006197  mov     ecx, 40h ; '@'; uFlags
0x18000619c  call    cs:__imp_LocalAlloc
0x1800061a2  mov     r14, rax
0x1800061a5  test    rax, rax
0x1800061a8  jz      loc_18000642B
0x1800061ae  mov     r12, [rbp+47h+var_98]
0x1800061b2  lea     rcx, aMschapv2connec_1; "mschapv2connectionpropertiesv1:UseWinLo"...
0x1800061b9  call    cs:__imp_SysAllocString
0x1800061bf  mov     rbx, rax
0x1800061c2  mov     [rbp+47h+lpString1], rax
0x1800061c6  test    rax, rax
0x1800061c9  jz      loc_180006467
0x1800061cf  mov     rax, [r12]
0x1800061d3  lea     r8, [rbp+47h+var_90]
0x1800061d7  mov     rdx, rbx
0x1800061da  mov     rcx, r12
0x1800061dd  mov     rax, [rax+128h]
0x1800061e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e9  test    eax, eax
0x1800061eb  jnz     loc_1800064AC
0x1800061f1  cmp     [rbp+47h+var_90], r15
0x1800061f5  jz      loc_1800064AC
0x1800061fb  mov     rcx, rbx; bstrString
0x1800061fe  call    cs:__imp_SysFreeString
0x180006204  mov     [rbp+47h+var_48], r15
0x180006208  mov     rcx, [rbp+47h+var_90]
0x18000620c  mov     [rbp+47h+lpString1], r15
0x180006210  mov     rax, [rcx]
0x180006213  lea     rdx, [rbp+47h+lpString1]
0x180006217  mov     rax, [rax+0D0h]
0x18000621e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006223  test    eax, eax
0x180006225  jnz     loc_18000632D
0x18000622b  lea     rdx, aTrue; "true"
0x180006232  mov     rcx, [rbp+47h+lpString1]; lpString1
0x180006236  call    cs:__imp_lstrcmpiW
0x18000623c  test    eax, eax
0x18000623e  jz      loc_18000648B
0x180006244  lea     rdx, a1; "1"
0x18000624b  mov     rcx, [rbp+47h+lpString1]; lpString1
0x18000624f  call    cs:__imp_lstrcmpiW
0x180006255  test    eax, eax
0x180006257  jz      loc_18000648B
0x18000625d  lea     rdx, aFalse; "false"
0x180006264  mov     rcx, [rbp+47h+lpString1]; lpString1
0x180006268  call    cs:__imp_lstrcmpiW
0x18000626e  test    eax, eax
0x180006270  jnz     loc_18000646D
0x180006276  xor     dl, dl
0x180006278  mov     ecx, [r14+4]
0x18000627c  mov     eax, ecx
0x18000627e  and     eax, 0FFFFFFFDh
0x180006281  or      ecx, 2
0x180006284  test    dl, dl
0x180006286  cmovz   ecx, eax
0x180006289  mov     [r14+4], ecx
0x18000628d  mov     rcx, [rbp+47h+lpString1]; bstrString
0x180006291  call    cs:__imp_SysFreeString
0x180006297  xor     edi, edi
0x180006299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062a0  cmp     rcx, r13
0x1800062a3  jnz     loc_1800064E8
0x1800062a9  mov     dword ptr [r14], 1
0x1800062b0  mov     r15, r14
0x1800062b3  mov     rcx, [rbp+47h+var_90]
0x1800062b7  test    rcx, rcx
0x1800062ba  jz      short loc_1800062C9
0x1800062bc  mov     rax, [rcx]
0x1800062bf  mov     rax, [rax+10h]
0x1800062c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c8  nop
0x1800062c9  mov     rcx, [rbp+47h+var_98]
0x1800062cd  test    rcx, rcx
  ... truncated ...
```
