# ParseServerValidationNode(IXMLDOMNode *,bool,bool,ulong *,_EAPTLS_HASH * *,ulong *,ushort * *,ulong *)

- ea: `0x18000deb0`
- end: `0x18000f0b6`
- name: `?ParseServerValidationNode@@YAKPEAUIXMLDOMNode@@_N1PEAKPEAPEAU_EAPTLS_HASH@@2PEAPEAG2@Z`
- size: `4614`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, bool, bool, unsigned int *, struct _EAPTLS_HASH **, unsigned int *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c1e0`
- `0x18000cbb0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000deb0`
- `0x18000f0c0`
- `0x18000f350`
- `0x18000f690`
- `0x180017a90`
- `0x18001e110`
- `0x1800200b4`
- `0x180035680`
- `0x18003623c`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e303`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e42c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e303`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e578`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e578`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efbc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e0e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e0fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e112`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec3c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000eda2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000edb8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e0e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e0fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e112`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e9f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec3c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ec52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ed8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000eda2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000edb8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e6bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e6e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e6bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e6e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df71`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e062`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e27a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e606`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e851`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e8c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ea73`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eae4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ebba`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ecea`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df71`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e062`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e27a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e606`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e851`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e8c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ea73`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eae4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ebba`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ecea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e1a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e1e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e226`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e2c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e582`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e5d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e64e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e72f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e766`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e92f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb53`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed39`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee63`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eeb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efab`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efd3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e1a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e1e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e226`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e2c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e582`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e5d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e64e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e72f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e766`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e92f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb53`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed39`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee63`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eeb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efab`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efd3`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e38f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6f1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e38f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6f1`

## string_xrefs

- `0x18000e78e`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`
- `0x18000ebb3`: `mspeapconnectionpropertiesv2:PeapExtensionsV2`
- `0x18000eeda`: `mspeapconnectionpropertiesv2:PeapExtensionsV2`

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
0x18000deb0  mov     [rsp-8+arg_8], rbx
0x18000deb5  push    rbp
0x18000deb6  push    rsi
0x18000deb7  push    rdi
0x18000deb8  push    r12
0x18000deba  push    r13
0x18000debc  push    r14
0x18000debe  push    r15
0x18000dec0  lea     rbp, [rsp-7]
0x18000dec5  sub     rsp, 0F0h
0x18000decc  mov     rax, cs:__security_cookie
0x18000ded3  xor     rax, rsp
0x18000ded6  mov     [rbp+37h+var_40], rax
0x18000deda  mov     [rbp+37h+var_80], r9
0x18000dede  movzx   r14d, r8b
0x18000dee2  mov     [rsp+120h+var_EC], r8b
0x18000dee7  movzx   r13d, dl
0x18000deeb  mov     rsi, rcx
0x18000deee  mov     [rsp+120h+var_E0], rcx
0x18000def3  mov     rcx, [rbp+37h+arg_20]
0x18000def7  mov     [rbp+37h+var_78], rcx
0x18000defb  mov     rcx, [rbp+37h+arg_28]
0x18000deff  mov     [rbp+37h+var_70], rcx
0x18000df03  mov     rcx, [rbp+37h+arg_30]
0x18000df07  mov     [rbp+37h+var_68], rcx
0x18000df0b  mov     rcx, [rbp+37h+arg_38]
0x18000df0f  mov     [rbp+37h+var_60], rcx
0x18000df13  mov     r15d, [r9]
0x18000df16  xor     r12d, r12d
0x18000df19  mov     [rsp+120h+var_D8], r12d
0x18000df1e  mov     [rbp+37h+var_A8], r12
0x18000df22  mov     [rsp+120h+var_C8], r12
0x18000df27  mov     [rbp+37h+var_88], r12
0x18000df2b  mov     [rbp+37h+var_B0], r12
0x18000df2f  mov     [rbp+37h+var_90], r12
0x18000df33  mov     [rbp+37h+var_98], r12
0x18000df37  mov     [rsp+120h+var_B8], r12
0x18000df3c  mov     [rsp+120h+var_C0], r12
0x18000df41  mov     [rsp+120h+lpString2], r12
0x18000df46  mov     [rbp+37h+pbstr], r12
0x18000df4a  mov     [rsp+120h+var_F0], 1
0x18000df52  mov     dword ptr [rsp+120h+var_100], 1
0x18000df5a  lea     rax, aEaptlsconnecti_3; "eaptlsconnectionpropertiesv1:ServerVali"...
0x18000df61  lea     rdi, aMspeapconnecti_10; "mspeapconnectionpropertiesv1:ServerVali"...
0x18000df68  test    dl, dl
0x18000df6a  cmovz   rdi, rax
0x18000df6e  mov     rcx, rdi; psz
0x18000df71  call    cs:__imp_SysAllocString
0x18000df77  mov     rbx, rax
0x18000df7a  mov     [rsp+120h+var_F8], rax
0x18000df7f  test    rax, rax
0x18000df82  jnz     short loc_18000DF8A
0x18000df84  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000df8a  mov     rax, [rsi]
0x18000df8d  lea     r8, [rsp+120h+var_C8]
0x18000df92  mov     rdx, rbx
0x18000df95  mov     rcx, rsi
0x18000df98  mov     rax, [rax+128h]
0x18000df9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa4  test    eax, eax
0x18000dfa6  jnz     loc_18000E737
0x18000dfac  cmp     [rsp+120h+var_C8], 0
0x18000dfb2  jz      loc_18000E737
0x18000dfb8  mov     rcx, rbx; bstrString
0x18000dfbb  call    cs:__imp_SysFreeString
0x18000dfc1  lea     r9, [rsp+120h+var_F0]; int *
0x18000dfc6  mov     r8d, 1; int
0x18000dfcc  lea     rdx, aPerformserverv; "PerformServerValidation"
0x18000dfd3  mov     rcx, [rsp+120h+var_C8]; struct IXMLDOMNode *
0x18000dfd8  call    ?GetAttributeValueFromNode@@YAJPEAUIXMLDOMNode@@PEAGHPEAH@Z; GetAttributeValueFromNode(IXMLDOMNode *,ushort *,int,int *)
0x18000dfdd  mov     ebx, eax
0x18000dfdf  test    eax, eax
0x18000dfe1  jz      short loc_18000DFFA
0x18000dfe3  and     eax, 1FFF0000h
0x18000dfe8  cmp     eax, 70000h
0x18000dfed  jnz     short loc_18000DFF2
0x18000dfef  movzx   ebx, bx
0x18000dff2  mov     r14, r12
0x18000dff5  jmp     loc_18000EFB1
0x18000dffa  cmp     [rsp+120h+var_F0], 1
0x18000dfff  jnz     short loc_18000E007
0x18000e001  and     r15d, 0FFFFFFFDh
0x18000e005  jmp     short loc_18000E045
0x18000e007  test    r14b, r14b
0x18000e00a  jz      short loc_18000E041
0x18000e00c  mov     ebx, 4B6h
0x18000e011  lea     rax, WPP_GLOBAL_Control
0x18000e018  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e01f  cmp     rcx, rax
0x18000e022  jz      short loc_18000DFF2
0x18000e024  mov     edx, 107h
0x18000e029  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e030  mov     rcx, [rcx+10h]
0x18000e034  call    WPP_SF_
0x18000e039  mov     r14, r12
0x18000e03c  jmp     loc_18000EFB1
0x18000e041  or      r15d, 2
0x18000e045  lea     rax, aEaptlsconnecti_24; "eaptlsconnectionpropertiesv1:DisableUse"...
0x18000e04c  lea     rdi, aMspeapconnecti_8; "mspeapconnectionpropertiesv1:DisableUse"...
0x18000e053  test    r13b, r13b
0x18000e056  cmovz   rdi, rax
0x18000e05a  mov     rsi, [rsp+120h+var_C8]
0x18000e05f  mov     rcx, rdi; psz
0x18000e062  call    cs:__imp_SysAllocString
0x18000e068  mov     rbx, rax
0x18000e06b  mov     [rsp+120h+var_F8], rax
0x18000e070  test    rax, rax
0x18000e073  jnz     short loc_18000E07B
0x18000e075  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e07b  mov     rax, [rsi]
0x18000e07e  lea     r8, [rbp+37h+var_88]
0x18000e082  mov     rdx, rbx
0x18000e085  mov     rcx, rsi
0x18000e088  mov     rax, [rax+128h]
0x18000e08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e094  test    eax, eax
0x18000e096  jnz     loc_18000E1F7
0x18000e09c  cmp     [rbp+37h+var_88], 0
0x18000e0a1  jz      loc_18000E1F7
0x18000e0a7  mov     rcx, rbx; bstrString
0x18000e0aa  call    cs:__imp_SysFreeString
0x18000e0b0  mov     [rsp+120h+var_F8], r12
0x18000e0b5  mov     rcx, [rbp+37h+var_88]
0x18000e0b9  mov     [rsp+120h+lpString1], r12
0x18000e0be  mov     rax, [rcx]
0x18000e0c1  lea     rdx, [rsp+120h+lpString1]
0x18000e0c6  mov     rax, [rax+0D0h]
0x18000e0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d2  test    eax, eax
0x18000e0d4  jnz     loc_18000E1B7
0x18000e0da  lea     rdx, String2; "true"
0x18000e0e1  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000e0e6  call    cs:__imp_lstrcmpiW
0x18000e0ec  test    eax, eax
0x18000e0ee  jz      short loc_18000E13A
0x18000e0f0  lea     rdx, a1; "1"
0x18000e0f7  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000e0fc  call    cs:__imp_lstrcmpiW
0x18000e102  test    eax, eax
0x18000e104  jz      short loc_18000E13A
0x18000e106  lea     rdx, aFalse; "false"
0x18000e10d  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000e112  call    cs:__imp_lstrcmpiW
0x18000e118  test    eax, eax
0x18000e11a  jz      short loc_18000E136
0x18000e11c  lea     rdx, a0; "0"
0x18000e123  mov     rcx, [rsp+120h+lpString1]; lpString1
0x18000e128  call    cs:__imp_lstrcmpiW
0x18000e12e  test    eax, eax
0x18000e130  jnz     loc_18000E1B7
0x18000e136  xor     al, al
0x18000e138  jmp     short loc_18000E13C
0x18000e13a  mov     al, 1
0x18000e13c  or      r15d, 4
0x18000e140  test    al, al
0x18000e142  jz      short loc_18000E172
0x18000e144  lea     r12, WPP_GLOBAL_Control
0x18000e14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e152  cmp     rcx, r12
0x18000e155  jz      short loc_18000E16C
0x18000e157  mov     edx, 10Ah
0x18000e15c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e163  mov     rcx, [rcx+10h]
0x18000e167  call    WPP_SF_
0x18000e16c  or      r15d, 20h
0x18000e170  jmp     short loc_18000E19E
0x18000e172  lea     r12, WPP_GLOBAL_Control
0x18000e179  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e180  cmp     rcx, r12
0x18000e183  jz      short loc_18000E19A
0x18000e185  mov     edx, 10Bh
0x18000e18a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e191  mov     rcx, [rcx+10h]
0x18000e195  call    WPP_SF_
0x18000e19a  and     r15d, 0FFFFFFDFh
0x18000e19e  mov     rcx, [rsp+120h+lpString1]; bstrString
0x18000e1a3  call    cs:__imp_SysFreeString
0x18000e1a9  xor     eax, eax
0x18000e1ab  mov     [rsp+120h+var_F0], eax
0x18000e1af  mov     r14d, eax
0x18000e1b2  jmp     loc_18000E25D
0x18000e1b7  lea     rax, WPP_GLOBAL_Control
0x18000e1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1c5  cmp     rcx, rax
0x18000e1c8  jz      short loc_18000E1E2
0x18000e1ca  mov     edx, 109h
0x18000e1cf  xor     r9d, r9d
0x18000e1d2  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e1d9  mov     rcx, [rcx+10h]
0x18000e1dd  call    WPP_SF_S
0x18000e1e2  mov     ebx, 0Dh
0x18000e1e7  xor     ecx, ecx; bstrString
0x18000e1e9  call    cs:__imp_SysFreeString
0x18000e1ef  mov     r14, r12
0x18000e1f2  jmp     loc_18000EFB1
0x18000e1f7  lea     r12, WPP_GLOBAL_Control
0x18000e1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e205  cmp     rcx, r12
0x18000e208  jz      short loc_18000E223
0x18000e20a  mov     edx, 0FCh
0x18000e20f  mov     r9, rdi
0x18000e212  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e219  mov     rcx, [rcx+10h]
0x18000e21d  call    WPP_SF_S
0x18000e222  nop
0x18000e223  mov     rcx, rbx; bstrString
0x18000e226  call    cs:__imp_SysFreeString
0x18000e22c  or      r15d, 4
0x18000e230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e237  cmp     rcx, r12
0x18000e23a  jz      short loc_18000E251
0x18000e23c  mov     edx, 108h
0x18000e241  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e248  mov     rcx, [rcx+10h]
0x18000e24c  call    WPP_SF_
0x18000e251  and     r15d, 0FFFFFFDFh
0x18000e255  xor     r14d, r14d
0x18000e258  mov     [rsp+120h+var_F0], r14d
0x18000e25d  lea     rax, aEaptlsconnecti_18; "eaptlsconnectionpropertiesv1:TrustedRoo"...
0x18000e264  lea     rdi, aMspeapconnecti_12; "mspeapconnectionpropertiesv1:TrustedRoo"...
0x18000e26b  test    r13b, r13b
0x18000e26e  cmovz   rdi, rax
0x18000e272  mov     rsi, [rsp+120h+var_C8]
0x18000e277  mov     rcx, rdi; psz
0x18000e27a  call    cs:__imp_SysAllocString
0x18000e280  mov     rbx, rax
0x18000e283  mov     [rsp+120h+var_F8], rax
0x18000e288  test    rax, rax
0x18000e28b  jnz     short loc_18000E293
0x18000e28d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e293  mov     rax, [rsi]
0x18000e296  lea     r8, [rbp+37h+var_A8]
0x18000e29a  mov     rdx, rbx
0x18000e29d  mov     rcx, rsi
0x18000e2a0  mov     rax, [rax+120h]
0x18000e2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ac  test    eax, eax
0x18000e2ae  jnz     loc_18000E5AD
0x18000e2b4  cmp     [rbp+37h+var_A8], 0
0x18000e2b9  jz      loc_18000E5AD
0x18000e2bf  mov     rcx, rbx; bstrString
0x18000e2c2  call    cs:__imp_SysFreeString
0x18000e2c8  mov     rcx, [rbp+37h+var_A8]
0x18000e2cc  mov     rax, [rcx]
0x18000e2cf  lea     rdx, [rsp+120h+var_D8]
0x18000e2d4  mov     rax, [rax+40h]
0x18000e2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2dd  mov     eax, [rsp+120h+var_D8]
0x18000e2e1  test    eax, eax
0x18000e2e3  jz      loc_18000E5E9
0x18000e2e9  xorps   xmm0, xmm0
0x18000e2ec  xor     ecx, ecx
0x18000e2ee  movups  [rbp+37h+var_58], xmm0
0x18000e2f2  mov     [rbp+37h+var_48], rcx
0x18000e2f6  lea     rdx, [rax+rax*2]
0x18000e2fa  shl     rdx, 3; uBytes
0x18000e2fe  mov     ecx, 40h ; '@'; uFlags
0x18000e303  call    cs:__imp_LocalAlloc
0x18000e309  mov     r14, rax
0x18000e30c  mov     [rsp+120h+var_F8], rax
0x18000e311  test    rax, rax
0x18000e314  jnz     short loc_18000E34E
0x18000e316  cmp     cs:WPP_GLOBAL_Control, r12
0x18000e31d  jz      short loc_18000E344
0x18000e31f  call    cs:__imp_GetLastError
0x18000e325  mov     edx, 10Ch
0x18000e32a  mov     r9d, eax
0x18000e32d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e334  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e33b  mov     rcx, [rcx+10h]
0x18000e33f  call    WPP_SF_d
0x18000e344  mov     ebx, 0Eh
0x18000e349  jmp     loc_18000EFB1
0x18000e34e  xor     edi, edi
0x18000e350  mov     dword ptr [rsp+120h+lpString1], edi
0x18000e354  mov     rcx, [rbp+37h+var_A8]
0x18000e358  mov     rax, [rcx]
0x18000e35b  lea     rdx, [rbp+37h+var_B0]
0x18000e35f  mov     rax, [rax+48h]
0x18000e363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e368  mov     rcx, [rbp+37h+var_B0]
0x18000e36c  test    rcx, rcx
0x18000e36f  jz      loc_18000E5DD
0x18000e375  mov     rax, [rcx]
0x18000e378  lea     rdx, [rbp+37h+pbstr]
0x18000e37c  mov     rax, [rax+0D0h]
0x18000e383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e388  mov     r12, [rbp+37h+pbstr]
0x18000e38c  mov     rcx, r12; pbstr
0x18000e38f  call    cs:__imp_SysStringLen
0x18000e395  mov     r10d, eax
0x18000e398  mov     r8d, eax
0x18000e39b  mov     rcx, r12
0x18000e39e  mov     ebx, edi
0x18000e3a0  test    eax, eax
0x18000e3a2  jle     short loc_18000E3E2
0x18000e3a4  nop     dword ptr [rax+00h]
0x18000e3a8  nop     dword ptr [rax+rax+00000000h]
0x18000e3b0  movzx   r9d, word ptr [rcx]
0x18000e3b4  lea     edx, [r9-30h]
  ... truncated ...
```
