# ParseServerValidationNode(IXMLDOMNode *,bool,bool,ulong *,_EAPTLS_HASH * *,ulong *,ushort * *,ulong *)

- ea: `0x18000eb10`
- end: `0x18000fe83`
- name: `?ParseServerValidationNode@@YAKPEAUIXMLDOMNode@@_N1PEAKPEAPEAU_EAPTLS_HASH@@2PEAPEAG2@Z`
- size: `4979`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, bool, bool, unsigned int *, struct _EAPTLS_HASH **, unsigned int *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cbc4`
- `0x18000d660`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18000eb10`
- `0x18000fe90`
- `0x180010140`
- `0x1800104b0`
- `0x180018b10`
- `0x18001e400`
- `0x180021e74`
- `0x180038270`
- `0x180038e4c`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000efb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f0ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000efb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f0ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed7a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed96`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000edb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f716`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f95e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f97a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f996`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f9b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000faf4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb2c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed7a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed96`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000edb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f6fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f716`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f95e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f97a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f996`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f9b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000faf4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb2c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f39b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f3c6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f39b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f3c6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ebd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ecce`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ef1c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f2d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f553`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f5ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f7a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f81c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f902`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fa5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ebd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ecce`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ef1c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f2d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f553`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f5ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f7a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f81c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f902`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fa5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec21`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eec2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f248`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f326`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f425`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f462`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f63d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f77b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f891`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa23`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fab1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd87`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd99`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec21`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eec2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f248`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f326`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f425`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f462`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f63d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f77b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f891`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa23`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fab1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd87`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd99`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f049`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f3db`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f049`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f3db`

## string_xrefs

- `0x18000f490`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`
- `0x18000f8fb`: `mspeapconnectionpropertiesv2:PeapExtensionsV2`
- `0x18000fc82`: `mspeapconnectionpropertiesv2:PeapExtensionsV2`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall ParseServerValidationNode(
        struct IXMLDOMNode *a1,
        char a2,
        char a3,
        unsigned int *a4,
        struct _EAPTLS_HASH **a5,
        unsigned int *a6,
        unsigned __int16 **a7,
        unsigned int *a8)
{
  unsigned int v11; // r15d
  const OLECHAR *v12; // rdi
  BSTR v13; // rax
  int v14; // ecx
  OLECHAR *v15; // rbx
  int AttributeValueFromNode; // eax
  unsigned int v17; // ebx
  struct _EAPTLS_HASH *v18; // r14
  unsigned int v19; // r15d
  const OLECHAR *v20; // rdi
  struct IXMLDOMNode *v21; // rsi
  BSTR v22; // rax
  int v23; // ecx
  OLECHAR *v24; // rbx
  char v25; // al
  int v26; // r15d
  unsigned int v27; // r15d
  int v28; // r15d
  const OLECHAR *v29; // rdi
  struct IXMLDOMNode *v30; // rsi
  BSTR v31; // rax
  int v32; // ecx
  OLECHAR *v33; // rbx
  DWORD LastError; // eax
  unsigned __int16 *v35; // r12
  UINT v36; // eax
  int v37; // r8d
  unsigned __int16 *v38; // rcx
  char i; // bl
  unsigned __int16 v40; // r9
  unsigned __int16 *v41; // rcx
  int v42; // r8d
  unsigned __int16 *v43; // rdi
  unsigned __int16 v44; // dx
  SIZE_T v45; // r14
  _BYTE *v46; // rax
  _BYTE *v47; // rsi
  unsigned __int16 v48; // dx
  _BYTE *v49; // r8
  unsigned __int16 v50; // cx
  char v51; // cl
  char v52; // cl
  unsigned __int16 v53; // dx
  char v54; // dl
  int v55; // edi
  __int64 v56; // rcx
  BSTR v57; // rbx
  __int64 v58; // rcx
  const OLECHAR *v59; // rdi
  struct IXMLDOMNode *v60; // rsi
  BSTR v61; // rax
  int v62; // ecx
  OLECHAR *v63; // rbx
  unsigned int v64; // eax
  int v65; // eax
  int v66; // edi
  struct IXMLDOMNode *v67; // rsi
  int SingleNode; // eax
  LPCWSTR v69; // rax
  struct IXMLDOMNode *v70; // rsi
  BSTR v71; // rax
  int v72; // ecx
  OLECHAR *v73; // rbx
  int v74; // esi
  BSTR v75; // rax
  int v76; // ecx
  char v77; // al
  OLECHAR *v78; // rcx
  struct IXMLDOMNode *v79; // rsi
  struct IXMLDOMNode *v80; // rax
  int v81; // ecx
  OLECHAR *v82; // rbx
  int v83; // esi
  BSTR v84; // rax
  int v85; // ecx
  struct IXMLDOMNode *v86; // rdi
  struct IXMLDOMNode *v87; // rax
  int v88; // ecx
  OLECHAR *v89; // rbx
  char v90; // bl
  int v91; // eax
  LPCWSTR v92; // rdi
  struct IXMLDOMNode *v93; // rax
  int v94; // ecx
  OLECHAR *v95; // rbx
  char v96; // bl
  struct _EAPTLS_CONTROL_BLOCK *v97; // rcx
  const wchar_t *v98; // r9
  struct _EAPTLS_CONTROL_BLOCK *v99; // rcx
  __int64 v100; // rdx
  LPCWSTR v102; // [rsp+20h] [rbp-C9h] BYREF
  BSTR v103; // [rsp+28h] [rbp-C1h] BYREF
  int v104; // [rsp+30h] [rbp-B9h] BYREF
  char v105; // [rsp+34h] [rbp-B5h]
  LPCWSTR lpString1; // [rsp+38h] [rbp-B1h] BYREF
  struct IXMLDOMNode *v107; // [rsp+40h] [rbp-A9h]
  unsigned int v108; // [rsp+48h] [rbp-A1h] BYREF
  LPCWSTR lpString2; // [rsp+50h] [rbp-99h] BYREF
  struct IXMLDOMNode *v110; // [rsp+58h] [rbp-91h] BYREF
  __int64 v111; // [rsp+60h] [rbp-89h] BYREF
  __int64 v112; // [rsp+68h] [rbp-81h] BYREF
  __int64 v113; // [rsp+70h] [rbp-79h] BYREF
  __int64 v114; // [rsp+78h] [rbp-71h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp-69h] BYREF
  struct IXMLDOMNode *v116; // [rsp+88h] [rbp-61h] BYREF
  struct IXMLDOMNode *v117; // [rsp+90h] [rbp-59h] BYREF
  __int64 v118; // [rsp+98h] [rbp-51h] BYREF
  unsigned int *v119; // [rsp+A0h] [rbp-49h]
  struct _EAPTLS_HASH **v120; // [rsp+A8h] [rbp-41h]
  unsigned int *v121; // [rsp+B0h] [rbp-39h]
  unsigned __int16 **v122; // [rsp+B8h] [rbp-31h]
  unsigned int *v123; // [rsp+C0h] [rbp-29h]
  __int128 v124; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v125; // [rsp+D8h] [rbp-11h]

  v119 = a4;
  v105 = a3;
  v107 = a1;
  v120 = a5;
  v121 = a6;
  v122 = a7;
  v123 = a8;
  v11 = *a4;
  v108 = 0;
  v114 = 0;
  v110 = 0;
  v118 = 0;
  v113 = 0;
  v117 = 0;
  v116 = 0;
  v112 = 0;
  v111 = 0;
  lpString2 = 0;
  pbstr = 0;
  v104 = 1;
  LODWORD(v102) = 1;
  v12 = L"mspeapconnectionpropertiesv1:ServerValidation[1]";
  if ( !a2 )
    v12 = L"eaptlsconnectionpropertiesv1:ServerValidation[1]";
  v13 = SysAllocString(v12);
  v15 = v13;
  v103 = v13;
  if ( !v13 )
    ATL::AtlThrowImpl(v14);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
         a1,
         v13,
         &v110)
    || !v110 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v12);
    SysFreeString(v15);
    v27 = v11 & 0xFFFFFFD9 | 6;
    v18 = 0;
    v104 = 0;
    goto LABEL_130;
  }
  SysFreeString(v15);
  AttributeValueFromNode = GetAttributeValueFromNode(v110, L"PerformServerValidation", 1, &v104);
  v17 = AttributeValueFromNode;
  if ( AttributeValueFromNode )
  {
    if ( (AttributeValueFromNode & 0x1FFF0000) == 0x70000 )
      v17 = (unsigned __int16)AttributeValueFromNode;
    goto LABEL_10;
  }
  if ( v104 == 1 )
  {
    v19 = v11 & 0xFFFFFFFD;
  }
  else
  {
    if ( a3 )
    {
      v17 = 1206;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
LABEL_10:
        v18 = 0;
        goto LABEL_252;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      v18 = 0;
      goto LABEL_252;
    }
    v19 = v11 | 2;
  }
  v20 = L"mspeapconnectionpropertiesv1:DisableUserPromptForServerValidation";
  if ( !a2 )
    v20 = L"eaptlsconnectionpropertiesv1:DisableUserPromptForServerValidation";
  v21 = v110;
  v22 = SysAllocString(v20);
  v24 = v22;
  v103 = v22;
  if ( !v22 )
    ATL::AtlThrowImpl(v23);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v21->lpVtbl->selectSingleNode)(
         v21,
         v22,
         &v118)
    || !v118 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v20);
    SysFreeString(v24);
    v28 = v19 | 4;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v27 = v28 & 0xFFFFFFDF;
    v18 = 0;
    v104 = 0;
    goto LABEL_46;
  }
  SysFreeString(v24);
  v103 = 0;
  lpString1 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v118 + 208LL))(v118, &lpString1) )
    goto LABEL_38;
  if ( !lstrcmpiW(lpString1, L"true") || !lstrcmpiW(lpString1, L"1") )
  {
    v25 = 1;
    goto LABEL_30;
  }
  if ( lstrcmpiW(lpString1, L"false") && lstrcmpiW(lpString1, L"0") )
  {
LABEL_38:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, 0);
    v17 = 13;
    SysFreeString(0);
    v18 = 0;
    goto LABEL_252;
  }
  v25 = 0;
LABEL_30:
  v26 = v19 | 4;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v27 = v26 | 0x20;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v27 = v26 & 0xFFFFFFDF;
  }
  SysFreeString((BSTR)lpString1);
  v104 = 0;
  v18 = 0;
LABEL_46:
  v29 = L"mspeapconnectionpropertiesv1:TrustedRootCA";
  if ( !a2 )
    v29 = L"eaptlsconnectionpropertiesv1:TrustedRootCA";
  v30 = v110;
  v31 = SysAllocString(v29);
  v33 = v31;
  v103 = v31;
  if ( !v31 )
    ATL::AtlThrowImpl(v32);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v30->lpVtbl->selectNodes)(v30, v31, &v114)
    || !v114 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v29);
    SysFreeString(v33);
  }
  else
  {
    SysFreeString(v33);
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v114 + 64LL))(v114, &v108);
    if ( v108 )
    {
      v124 = 0;
      v125 = 0;
      v18 = (struct _EAPTLS_HASH *)LocalAlloc(0x40u, 24LL * v108);
      v103 = (BSTR)v18;
      if ( !v18 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, LastError);
        }
        v17 = 14;
        goto LABEL_252;
      }
      LODWORD(lpString1) = 0;
      while ( 1 )
      {
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v114 + 72LL))(v114, &v113);
        if ( !v113 )
          break;
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v113 + 208LL))(v113, &pbstr);
        v35 = pbstr;
        v36 = SysStringLen(pbstr);
        v37 = v36;
        v38 = v35;
        for ( i = 0; v37 > 0; --v37 )
        {
          v40 = *v38;
          if ( (unsigned __int16)(*v38 - 48) <= 9u
            || (unsigned __int16)(v40 - 65) <= 5u
            || (unsigned __int16)(v40 - 97) <= 5u )
          {
            ++i;
          }
          ++v38;
        }
        v41 = v35;
        v42 = 0;
        v43 = &v35[v36];
        if ( v35 < v43 )
        {
          do
          {
            v44 = *v41;
            if ( (unsigned __int16)(*v41 - 48) <= 9u
              || (unsigned __int16)(v44 - 65) <= 5u
              || (unsigned __int16)(v44 - 97) <= 5u )
            {
              ++v42;
            }
            ++v41;
          }
          while ( v41 < v43 );
        }
        v45 = (unsigned int)(v42 + 1) >> 1;
        v46 = LocalAlloc(0x40u, v45);
        v47 = v46;
        if ( v46 )
        {
          if ( (i & 1) != 0 )
          {
            for ( ; !IsHexDigit(*v35); ++v35 )
              ;
            *v47 = ConvertHexWCharToInteger(v48);
            ++v35;
            v49 = v47 + 1;
          }
          else
          {
            v49 = v46;
          }
          for ( ; v35 < v43; ++v49 )
          {
            while ( 1 )
            {
              v50 = *v35;
              if ( (unsigned __int16)(*v35 - 48) <= 9u
                || (unsigned __int16)(v50 - 65) <= 5u
                || (unsigned __int16)(v50 - 97) <= 5u )
              {
                break;
              }
              ++v35;
            }
            if ( (unsigned __int16)(v50 - 48) > 9u )
            {
              if ( (unsigned __int16)(v50 - 65) > 5u )
                v51 = v50 - 87;
              else
                v51 = v50 - 55;
            }
            else
            {
              v51 = v50 - 48;
            }
            v52 = 16 * v51;
            *v49 = v52;
            do
              v53 = *++v35;
            while ( (unsigned __int16)(*v35 - 48) > 9u
                 && (unsigned __int16)(v53 - 65) > 5u
                 && (unsigned __int16)(v53 - 97) > 5u );
            if ( (unsigned __int16)(v53 - 48) > 9u )
            {
              if ( (unsigned __int16)(v53 - 65) > 5u )
                v54 = v53 - 87;
              else
                v54 = v53 - 55;
            }
            else
            {
              v54 = v53 - 48;
            }
            *v49 = v54 | v52;
            ++v35;
          }
          if ( (unsigned int)(v45 - 1) <= 0x13 )
          {
            LODWORD(v124) = v45;
            memcpy_0((char *)&v124 + 4, v47, v45);
            v55 = (int)lpString1;
            v56 = 3LL * (unsigned int)lpString1;
            v57 = v103;
            *(_OWORD *)&v103[4 * v56] = v124;
            *(_QWORD *)&v57[4 * v56 + 8] = v125;
            LODWORD(lpString1) = v55 + 1;
          }
        }
        LocalFree(v47);
        SysFreeString(pbstr);
        pbstr = 0;
        v58 = v113;
        if ( v113 )
        {
          v113 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
      }
      v18 = (struct _EAPTLS_HASH *)v103;
    }
  }
  v59 = L"mspeapconnectionpropertiesv1:ServerNames";
  if ( !a2 )
    v59 = L"eaptlsconnectionpropertiesv1:ServerNames";
  v60 = v110;
  v61 = SysAllocString(v59);
  v63 = v61;
  v103 = v61;
  if ( !v61 )
    ATL::AtlThrowImpl(v62);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v60->lpVtbl->selectSingleNode)(
         v60,
         v61,
         &v117)
    || !v117 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v59);
    SysFreeString(v63);
    goto LABEL_130;
  }
  SysFreeString(v63);
  v64 = GetAttributeValueFromNode(v117, L"AcceptServerName", 1, (int *)&v102);
  v17 = v64;
  if ( v64 > 1 )
  {
    if ( (v64 & 0x1FFF0000) == 0x70000 )
      v17 = (unsigned __int16)v64;
    goto LABEL_252;
  }
  v65 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LPCWSTR *))v117->lpVtbl->get_text)(v117, &lpString2);
  v66 = v65;
  if ( v17 != 1 )
    goto LABEL_118;
  if ( v65 )
    goto LABEL_123;
  if ( lstrcmpW(&String, lpString2) )
  {
LABEL_118:
    if ( (_DWORD)v102 == 1 )
      v27 &= ~4u;
    if ( v66 )
      goto LABEL_123;
  }
  if ( lstrcmpW(&String, lpString2) )
  {
    v104 = SysStringLen((BSTR)lpString2);
    goto LABEL_130;
  }
LABEL_123:
  v104 = 0;
LABEL_130:
  v67 = v107;
  if ( a2 )
  {
    SingleNode = getSingleNode(v107, L"mspeapconnectionpropertiesv1:PeapExtensions[1]", &v116);
    if ( SingleNode )
    {
      if ( SingleNode == -2147024882 )
      {
        v17 = 14;
        goto LABEL_252;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      goto LABEL_136;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 270, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  if ( a2 )
  {
    v70 = v116;
    v71 = SysAllocString(L"mspeapconnectionpropertiesv2:PerformServerValidation");
    v73 = v71;
    v103 = v71;
    if ( !v71 )
      ATL::AtlThrowImpl(v72);
    v74 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v70->lpVtbl->selectSingleNode)(
            v70,
            v71,
            &v111);
    if ( v74 || !v111 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"mspeapconnectionpropertiesv2:PerformServerValidation");
      v74 = -2147024809;
    }
  }
  else
  {
    v75 = SysAllocString(L"eaptlsconnectionpropertiesv2:PerformServerValidation");
    v73 = v75;
    v103 = v75;
    if ( !v75 )
      ATL::AtlThrowImpl(v76);
    v74 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v67->lpVtbl->selectSingleNode)(
            v67,
            v75,
            &v111);
    if ( v74 || !v111 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"eaptlsconnectionpropertiesv2:PerformServerValidation");
      v74 = -2147024809;
    }
  }
  SysFreeString(v73);
  if ( v74 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_172;
  }
  v103 = 0;
  v102 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v111 + 208LL))(v111, &v102) )
    goto LABEL_247;
  if ( !lstrcmpiW(v102, L"true") || !lstrcmpiW(v102, L"1") )
  {
    v77 = 1;
    goto LABEL_164;
  }
  if ( lstrcmpiW(v102, L"false") && lstrcmpiW(v102, L"0") )
  {
LABEL_247:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 272, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, 0);
    v17 = 13;
    goto LABEL_250;
  }
  v77 = 0;
LABEL_164:
  if ( v77 )
  {
    v27 &= ~2u;
  }
  else
  {
    if ( v105 )
    {
      v17 = 1206;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      v78 = (OLECHAR *)v102;
      goto LABEL_251;
    }
    v27 |= 2u;
  }
  SysFreeString((BSTR)v102);
LABEL_172:
  if ( a2 )
  {
    v79 = v116;
    v80 = (struct IXMLDOMNode *)SysAllocString(L"mspeapconnectionpropertiesv2:AcceptServerName");
    v82 = (OLECHAR *)v80;
    v107 = v80;
    if ( !v80 )
      ATL::AtlThrowImpl(v81);
    v83 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, __int64 *))v79->lpVtbl->selectSingleNode)(
            v79,
            v80,
            &v112);
    if ( v83 || !v112 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"mspeapconnectionpropertiesv2:AcceptServerName");
      v83 = -2147024809;
    }
  }
  else
  {
    v84 = SysAllocString(L"eaptlsconnectionpropertiesv2:AcceptServerName");
    v82 = v84;
    v103 = v84;
    if ( !v84 )
      ATL::AtlThrowImpl(v85);
    v83 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v107->lpVtbl->selectSingleNode)(
            v107,
            v84,
            &v112);
    if ( v83 || !v112 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"eaptlsconnectionpropertiesv2:AcceptServerName");
      v83 = -2147024809;
    }
  }
  SysFreeString(v82);
  if ( v83 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 274, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_190;
  }
  v107 = 0;
  v102 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v112 + 208LL))(v112, &v102) )
  {
LABEL_244:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, 0);
    v17 = 13;
LABEL_250:
    v78 = 0;
LABEL_251:
    SysFreeString(v78);
    goto LABEL_252;
  }
  if ( lstrcmpiW(v102, L"true") && lstrcmpiW(v102, L"1") )
  {
    if ( !lstrcmpiW(v102, L"false") || !lstrcmpiW(v102, L"0") )
    {
      v90 = 0;
      goto LABEL_201;
    }
    goto LABEL_244;
  }
  v90 = 1;
LABEL_201:
  SysFreeString((BSTR)v102);
  v91 = v27 | 4;
  v27 &= ~4u;
  if ( !v90 )
    v27 = v91;
LABEL_190:
  if ( !a2 || (v27 & 0x20) != 0 )
  {
LABEL_136:
    v17 = 0;
    *v119 = v27;
    *v120 = v18;
    *v121 = v108;
    v69 = lpString2;
    lpString2 = 0;
    *v122 = (unsigned __int16 *)v69;
    *v123 = v104;
    v18 = 0;
    goto LABEL_252;
  }
  lpString1 = 0;
  v103 = 0;
  v86 = v116;
  v87 = (struct IXMLDOMNode *)SysAllocString(L"mspeapconnectionpropertiesv2:PeapExtensionsV2");
  v89 = (OLECHAR *)v87;
  v107 = v87;
  if ( !v87 )
    ATL::AtlThrowImpl(v88);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, LPCWSTR *))v86->lpVtbl->selectSingleNode)(
         v86,
         v87,
         &lpString1)
    || !lpString1 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"mspeapconnectionpropertiesv2:PeapExtensionsV2");
    SysFreeString(v89);
    v27 &= ~0x200u;
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_239;
    v100 = 276;
LABEL_238:
    WPP_SF_(*((_QWORD *)v99 + 2), v100, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
LABEL_239:
    if ( v103 )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v103 + 16LL))(v103);
    if ( lpString1 )
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpString1 + 16LL))(lpString1);
    goto LABEL_136;
  }
  SysFreeString(v89);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  v92 = lpString1;
  v93 = (struct IXMLDOMNode *)SysAllocString(L"mspeapconnectionpropertiesv3:AllowPromptingWhenServerCANotFound");
  v95 = (OLECHAR *)v93;
  v107 = v93;
  if ( !v93 )
    ATL::AtlThrowImpl(v94);
  v27 &= ~0x200u;
  if ( (*(unsigned int (__fastcall **)(LPCWSTR, struct IXMLDOMNode *, BSTR *))(*(_QWORD *)v92 + 296LL))(v92, v93, &v103)
    || !v103 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"mspeapconnectionpropertiesv3:AllowPromptingWhenServerCANotFound");
    SysFreeString(v95);
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_239;
    v100 = 278;
    goto LABEL_238;
  }
  SysFreeString(v95);
  v107 = 0;
  v102 = 0;
  if ( !(*(unsigned int (__fastcall **)(BSTR, LPCWSTR *))(*(_QWORD *)v103 + 208LL))(v103, &v102) )
  {
    if ( !lstrcmpiW(v102, L"true") || !lstrcmpiW(v102, L"1") )
    {
      v96 = 1;
      goto LABEL_219;
    }
    if ( !lstrcmpiW(v102, L"false") || !lstrcmpiW(v102, L"0") )
    {
      v96 = 0;
LABEL_219:
      v97 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v98 = L"TRUE";
        if ( !v96 )
          v98 = L"FALSE";
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v98);
        v97 = WPP_GLOBAL_Control;
      }
      if ( v96 )
      {
        v27 |= 0x200u;
        if ( v97 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)v97 + 2), 281, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      }
      SysFreeString((BSTR)v102);
      goto LABEL_239;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, 0);
  v17 = 13;
  SysFreeString(0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v103);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&lpString1);
LABEL_252:
  LocalFree(v18);
  LocalFree(0);
  SysFreeString(pbstr);
  SysFreeString((BSTR)lpString2);
  if ( v111 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
  if ( v112 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
  if ( v116 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v116->lpVtbl->Release)(v116);
  if ( v117 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v117->lpVtbl->Release)(v117);
  if ( v113 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  if ( v118 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  if ( v110 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v110->lpVtbl->Release)(v110);
  if ( v114 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
  return v17;
}

```

## disassembly

```asm
0x18000eb10  mov     [rsp-8+arg_8], rbx
0x18000eb15  push    rbp
0x18000eb16  push    rsi
0x18000eb17  push    rdi
0x18000eb18  push    r12
0x18000eb1a  push    r13
0x18000eb1c  push    r14
0x18000eb1e  push    r15
0x18000eb20  lea     rbp, [rsp-7]
0x18000eb25  sub     rsp, 0F0h
0x18000eb2c  mov     rax, cs:__security_cookie
0x18000eb33  xor     rax, rsp
0x18000eb36  mov     [rbp+37h+var_40], rax
0x18000eb3a  mov     [rbp+37h+var_80], r9
0x18000eb3e  movzx   r14d, r8b
0x18000eb42  mov     [rsp+120h+var_EC], r8b
0x18000eb47  movzx   r13d, dl
0x18000eb4b  mov     rsi, rcx
0x18000eb4e  mov     [rsp+120h+var_E0], rcx
0x18000eb53  mov     rcx, [rbp+37h+arg_20]
0x18000eb57  mov     [rbp+37h+var_78], rcx
0x18000eb5b  mov     rcx, [rbp+37h+arg_28]
0x18000eb5f  mov     [rbp+37h+var_70], rcx
0x18000eb63  mov     rcx, [rbp+37h+arg_30]
0x18000eb67  mov     [rbp+37h+var_68], rcx
0x18000eb6b  mov     rcx, [rbp+37h+arg_38]
0x18000eb6f  mov     [rbp+37h+var_60], rcx
0x18000eb73  mov     r15d, [r9]
0x18000eb76  xor     r12d, r12d
0x18000eb79  mov     [rsp+120h+var_D8], r12d
0x18000eb7e  mov     [rbp+37h+var_A8], r12
0x18000eb82  mov     [rsp+120h+var_C8], r12
0x18000eb87  mov     [rbp+37h+var_88], r12
0x18000eb8b  mov     [rbp+37h+var_B0], r12
0x18000eb8f  mov     [rbp+37h+var_90], r12
0x18000eb93  mov     [rbp+37h+var_98], r12
0x18000eb97  mov     [rsp+120h+var_B8], r12
0x18000eb9c  mov     [rsp+120h+var_C0], r12
0x18000eba1  mov     [rsp+120h+lpString2], r12
0x18000eba6  mov     [rbp+37h+pbstr], r12
0x18000ebaa  mov     [rsp+120h+var_F0], 1
0x18000ebb2  mov     dword ptr [rsp+120h+var_100], 1
0x18000ebba  lea     rax, aEaptlsconnecti_3; "eaptlsconnectionpropertiesv1:ServerVali"...
0x18000ebc1  lea     rdi, aMspeapconnecti_10; "mspeapconnectionpropertiesv1:ServerVali"...
0x18000ebc8  test    dl, dl
0x18000ebca  cmovz   rdi, rax
0x18000ebce  mov     rcx, rdi; psz
0x18000ebd1  call    cs:__imp_SysAllocString
0x18000ebd8  nop     dword ptr [rax+rax+00h]
0x18000ebdd  mov     rbx, rax
0x18000ebe0  mov     [rsp+120h+var_F8], rax
0x18000ebe5  test    rax, rax
0x18000ebe8  jnz     short loc_18000EBF0
0x18000ebea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ebf0  mov     rax, [rsi]
0x18000ebf3  lea     r8, [rsp+120h+var_C8]
0x18000ebf8  mov     rdx, rbx
0x18000ebfb  mov     rcx, rsi
0x18000ebfe  mov     rax, [rax+128h]
0x18000ec05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec0a  test    eax, eax
0x18000ec0c  jnz     loc_18000F433
0x18000ec12  cmp     [rsp+120h+var_C8], 0
0x18000ec18  jz      loc_18000F433
0x18000ec1e  mov     rcx, rbx; bstrString
0x18000ec21  call    cs:__imp_SysFreeString
0x18000ec28  nop     dword ptr [rax+rax+00h]
0x18000ec2d  lea     r9, [rsp+120h+var_F0]; int *
0x18000ec32  mov     r8d, 1; int
0x18000ec38  lea     rdx, aPerformserverv; "PerformServerValidation"
0x18000ec3f  mov     rcx, [rsp+120h+var_C8]; struct IXMLDOMNode *
0x18000ec44  call    ?GetAttributeValueFromNode@@YAJPEAUIXMLDOMNode@@PEAGHPEAH@Z; GetAttributeValueFromNode(IXMLDOMNode *,ushort *,int,int *)
0x18000ec49  mov     ebx, eax
0x18000ec4b  test    eax, eax
0x18000ec4d  jz      short loc_18000EC66
0x18000ec4f  and     eax, 1FFF0000h
0x18000ec54  cmp     eax, 70000h
0x18000ec59  jnz     short loc_18000EC5E
0x18000ec5b  movzx   ebx, bx
0x18000ec5e  mov     r14, r12
0x18000ec61  jmp     loc_18000FD65
0x18000ec66  cmp     [rsp+120h+var_F0], 1
0x18000ec6b  jnz     short loc_18000EC73
0x18000ec6d  and     r15d, 0FFFFFFFDh
0x18000ec71  jmp     short loc_18000ECB1
0x18000ec73  test    r14b, r14b
0x18000ec76  jz      short loc_18000ECAD
0x18000ec78  mov     ebx, 4B6h
0x18000ec7d  lea     rax, WPP_GLOBAL_Control
0x18000ec84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec8b  cmp     rcx, rax
0x18000ec8e  jz      short loc_18000EC5E
0x18000ec90  mov     edx, 107h
0x18000ec95  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ec9c  mov     rcx, [rcx+10h]
0x18000eca0  call    WPP_SF_
0x18000eca5  mov     r14, r12
0x18000eca8  jmp     loc_18000FD65
0x18000ecad  or      r15d, 2
0x18000ecb1  lea     rax, aEaptlsconnecti_24; "eaptlsconnectionpropertiesv1:DisableUse"...
0x18000ecb8  lea     rdi, aMspeapconnecti_8; "mspeapconnectionpropertiesv1:DisableUse"...
0x18000ecbf  test    r13b, r13b
0x18000ecc2  cmovz   rdi, rax
0x18000ecc6  mov     rsi, [rsp+120h+var_C8]
0x18000eccb  mov     rcx, rdi; psz
0x18000ecce  call    cs:__imp_SysAllocString
0x18000ecd5  nop     dword ptr [rax+rax+00h]
0x18000ecda  mov     rbx, rax
0x18000ecdd  mov     [rsp+120h+var_F8], rax
0x18000ece2  test    rax, rax
0x18000ece5  jnz     short loc_18000ECED
0x18000ece7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000eced  mov     rax, [rsi]
0x18000ecf0  lea     r8, [rbp+37h+var_88]
0x18000ecf4  mov     rdx, rbx
0x18000ecf7  mov     rcx, rsi
0x18000ecfa  mov     rax, [rax+128h]
0x18000ed01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed06  test    eax, eax
0x18000ed08  jnz     loc_18000EE93
0x18000ed0e  cmp     [rbp+37h+var_88], 0
0x18000ed13  jz      loc_18000EE93
0x18000ed19  mov     rcx, rbx; bstrString
0x18000ed1c  call    cs:__imp_SysFreeString
0x18000ed23  nop     dword ptr [rax+rax+00h]
0x18000ed28  mov     [rsp+120h+var_F8], r12
0x18000ed2d  mov     rcx, [rbp+37h+var_88]
0x18000ed31  mov     [rsp+120h+lpString1], r12
0x18000ed36  mov     rax, [rcx]
0x18000ed39  lea     rdx, [rsp+120h+lpString1]
0x18000ed3e  mov     rax, [rax+0D0h]
0x18000ed45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed4a  test    eax, eax
0x18000ed4c  jnz     loc_18000EE4D
0x18000ed52  lea     rdx, String2; "true"
0x18000ed59  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000ed5e  call    cs:__imp_lstrcmpiW
0x18000ed65  nop     dword ptr [rax+rax+00h]
0x18000ed6a  test    eax, eax
0x18000ed6c  jz      short loc_18000EDCA
0x18000ed6e  lea     rdx, a1; "1"
0x18000ed75  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000ed7a  call    cs:__imp_lstrcmpiW
0x18000ed81  nop     dword ptr [rax+rax+00h]
0x18000ed86  test    eax, eax
0x18000ed88  jz      short loc_18000EDCA
0x18000ed8a  lea     rdx, aFalse; "false"
0x18000ed91  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000ed96  call    cs:__imp_lstrcmpiW
0x18000ed9d  nop     dword ptr [rax+rax+00h]
0x18000eda2  test    eax, eax
0x18000eda4  jz      short loc_18000EDC6
0x18000eda6  lea     rdx, a0; "0"
0x18000edad  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000edb2  call    cs:__imp_lstrcmpiW
0x18000edb9  nop     dword ptr [rax+rax+00h]
0x18000edbe  test    eax, eax
0x18000edc0  jnz     loc_18000EE4D
0x18000edc6  xor     al, al
0x18000edc8  jmp     short loc_18000EDCC
0x18000edca  mov     al, 1
0x18000edcc  or      r15d, 4
0x18000edd0  test    al, al
0x18000edd2  jz      short loc_18000EE02
0x18000edd4  lea     r12, WPP_GLOBAL_Control
0x18000eddb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ede2  cmp     rcx, r12
0x18000ede5  jz      short loc_18000EDFC
0x18000ede7  mov     edx, 10Ah
0x18000edec  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000edf3  mov     rcx, [rcx+10h]
0x18000edf7  call    WPP_SF_
0x18000edfc  or      r15d, 20h
0x18000ee00  jmp     short loc_18000EE2E
0x18000ee02  lea     r12, WPP_GLOBAL_Control
0x18000ee09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee10  cmp     rcx, r12
0x18000ee13  jz      short loc_18000EE2A
0x18000ee15  mov     edx, 10Bh
0x18000ee1a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ee21  mov     rcx, [rcx+10h]
0x18000ee25  call    WPP_SF_
0x18000ee2a  and     r15d, 0FFFFFFDFh
0x18000ee2e  mov     rcx, [rsp+120h+lpString1]; bstrString
0x18000ee33  call    cs:__imp_SysFreeString
0x18000ee3a  nop     dword ptr [rax+rax+00h]
0x18000ee3f  xor     eax, eax
0x18000ee41  mov     [rsp+120h+var_F0], eax
0x18000ee45  mov     r14d, eax
0x18000ee48  jmp     loc_18000EEFF
0x18000ee4d  lea     rax, WPP_GLOBAL_Control
0x18000ee54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee5b  cmp     rcx, rax
0x18000ee5e  jz      short loc_18000EE78
0x18000ee60  mov     edx, 109h
0x18000ee65  xor     r9d, r9d
0x18000ee68  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ee6f  mov     rcx, [rcx+10h]
0x18000ee73  call    WPP_SF_S
0x18000ee78  mov     ebx, 0Dh
0x18000ee7d  xor     ecx, ecx; bstrString
0x18000ee7f  call    cs:__imp_SysFreeString
0x18000ee86  nop     dword ptr [rax+rax+00h]
0x18000ee8b  mov     r14, r12
0x18000ee8e  jmp     loc_18000FD65
0x18000ee93  lea     r12, WPP_GLOBAL_Control
0x18000ee9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eea1  cmp     rcx, r12
0x18000eea4  jz      short loc_18000EEBF
0x18000eea6  mov     edx, 0FCh
0x18000eeab  mov     r9, rdi
0x18000eeae  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000eeb5  mov     rcx, [rcx+10h]
0x18000eeb9  call    WPP_SF_S
0x18000eebe  nop
0x18000eebf  mov     rcx, rbx; bstrString
0x18000eec2  call    cs:__imp_SysFreeString
0x18000eec9  nop     dword ptr [rax+rax+00h]
0x18000eece  or      r15d, 4
0x18000eed2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eed9  cmp     rcx, r12
0x18000eedc  jz      short loc_18000EEF3
0x18000eede  mov     edx, 108h
0x18000eee3  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000eeea  mov     rcx, [rcx+10h]
0x18000eeee  call    WPP_SF_
0x18000eef3  and     r15d, 0FFFFFFDFh
0x18000eef7  xor     r14d, r14d
0x18000eefa  mov     [rsp+120h+var_F0], r14d
0x18000eeff  lea     rax, aEaptlsconnecti_18; "eaptlsconnectionpropertiesv1:TrustedRoo"...
0x18000ef06  lea     rdi, aMspeapconnecti_12; "mspeapconnectionpropertiesv1:TrustedRoo"...
0x18000ef0d  test    r13b, r13b
0x18000ef10  cmovz   rdi, rax
0x18000ef14  mov     rsi, [rsp+120h+var_C8]
0x18000ef19  mov     rcx, rdi; psz
0x18000ef1c  call    cs:__imp_SysAllocString
0x18000ef23  nop     dword ptr [rax+rax+00h]
0x18000ef28  mov     rbx, rax
0x18000ef2b  mov     [rsp+120h+var_F8], rax
0x18000ef30  test    rax, rax
0x18000ef33  jnz     short loc_18000EF3B
0x18000ef35  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ef3b  mov     rax, [rsi]
0x18000ef3e  lea     r8, [rbp+37h+var_A8]
0x18000ef42  mov     rdx, rbx
0x18000ef45  mov     rcx, rsi
0x18000ef48  mov     rax, [rax+120h]
0x18000ef4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef54  test    eax, eax
0x18000ef56  jnz     loc_18000F279
0x18000ef5c  cmp     [rbp+37h+var_A8], 0
0x18000ef61  jz      loc_18000F279
0x18000ef67  mov     rcx, rbx; bstrString
0x18000ef6a  call    cs:__imp_SysFreeString
0x18000ef71  nop     dword ptr [rax+rax+00h]
0x18000ef76  mov     rcx, [rbp+37h+var_A8]
0x18000ef7a  mov     rax, [rcx]
0x18000ef7d  lea     rdx, [rsp+120h+var_D8]
0x18000ef82  mov     rax, [rax+40h]
0x18000ef86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef8b  mov     eax, [rsp+120h+var_D8]
0x18000ef8f  test    eax, eax
0x18000ef91  jz      loc_18000F2BB
0x18000ef97  xorps   xmm0, xmm0
0x18000ef9a  xor     ecx, ecx
0x18000ef9c  movups  [rbp+37h+var_58], xmm0
0x18000efa0  mov     [rbp+37h+var_48], rcx
0x18000efa4  lea     rdx, [rax+rax*2]
0x18000efa8  shl     rdx, 3; uBytes
0x18000efac  mov     ecx, 40h ; '@'; uFlags
0x18000efb1  call    cs:__imp_LocalAlloc
0x18000efb8  nop     dword ptr [rax+rax+00h]
0x18000efbd  mov     r14, rax
0x18000efc0  mov     [rsp+120h+var_F8], rax
0x18000efc5  test    rax, rax
0x18000efc8  jnz     short loc_18000F008
0x18000efca  cmp     cs:WPP_GLOBAL_Control, r12
0x18000efd1  jz      short loc_18000EFFE
0x18000efd3  call    cs:__imp_GetLastError
0x18000efda  nop     dword ptr [rax+rax+00h]
0x18000efdf  mov     edx, 10Ch
0x18000efe4  mov     r9d, eax
0x18000efe7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000efee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eff5  mov     rcx, [rcx+10h]
0x18000eff9  call    WPP_SF_d
0x18000effe  mov     ebx, 0Eh
0x18000f003  jmp     loc_18000FD65
0x18000f008  xor     edi, edi
0x18000f00a  mov     dword ptr [rsp+120h+lpString1], edi
0x18000f00e  mov     rcx, [rbp+37h+var_A8]
0x18000f012  mov     rax, [rcx]
0x18000f015  lea     rdx, [rbp+37h+var_B0]
0x18000f019  mov     rax, [rax+48h]
0x18000f01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f022  mov     rcx, [rbp+37h+var_B0]
0x18000f026  test    rcx, rcx
0x18000f029  jz      loc_18000F2AF
0x18000f02f  mov     rax, [rcx]
0x18000f032  lea     rdx, [rbp+37h+pbstr]
  ... truncated ...
```
