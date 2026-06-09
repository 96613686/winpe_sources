# CreatePkcs10RequestFromKey(IX509PrivateKey *,bool,ushort const *,ushort const *,uchar const *,ulong,IX509CertificateRequestPkcs10 * *)

- ea: `0x1800322b0`
- end: `0x180033a98`
- name: `?CreatePkcs10RequestFromKey@@YAJPEAUIX509PrivateKey@@_NPEBG2PEBEKPEAPEAUIX509CertificateRequestPkcs10@@@Z`
- size: `6120`
- prototype: `int(struct IX509PrivateKey *, bool, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, struct IX509CertificateRequestPkcs10 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800141b0`
- `0x180019f44`
- `0x1800322b0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032314`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003242e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800326b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032826`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032a27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032ed5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033043`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800335fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032314`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003242e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800326b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032826`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032a27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032ed5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033043`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800335fe`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180032781`
- `OLEAUT32!__imp_SysAllocString` at `0x180032f9e`
- `OLEAUT32!__imp_SysAllocString` at `0x180033554`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180032781`
- `OLEAUT32!__imp_SysAllocString` at `0x180032f9e`
- `OLEAUT32!__imp_SysAllocString` at `0x180033554`
- `OLEAUT32!__imp_SysFreeString` at `0x180032482`
- `OLEAUT32!__imp_SysFreeString` at `0x180032516`
- `OLEAUT32!__imp_SysFreeString` at `0x1800325ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180032662`
- `OLEAUT32!__imp_SysFreeString` at `0x180032744`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18003287e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800328dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180032973`
- `OLEAUT32!__imp_SysFreeString` at `0x1800329d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a99`
- `OLEAUT32!__imp_SysFreeString` at `0x180032af7`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ba7`
- `OLEAUT32!__imp_SysFreeString` at `0x180032c05`
- `OLEAUT32!__imp_SysFreeString` at `0x180032cb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d13`
- `OLEAUT32!__imp_SysFreeString` at `0x180032dc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180032e21`
- `OLEAUT32!__imp_SysFreeString` at `0x180032e8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f61`
- `OLEAUT32!__imp_SysFreeString` at `0x180033007`
- `OLEAUT32!__imp_SysFreeString` at `0x18003309b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003318e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180033262`
- `OLEAUT32!__imp_SysFreeString` at `0x1800332c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003332d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033357`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180033436`
- `OLEAUT32!__imp_SysFreeString` at `0x180033460`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033521`
- `OLEAUT32!__imp_SysFreeString` at `0x1800335a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180033656`
- `OLEAUT32!__imp_SysFreeString` at `0x18003369a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003372f`
- `OLEAUT32!__imp_SysFreeString` at `0x180033773`
- `OLEAUT32!__imp_SysFreeString` at `0x18003380c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033850`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003392b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033a50`
- `OLEAUT32!__imp_SysFreeString` at `0x180032482`
- `OLEAUT32!__imp_SysFreeString` at `0x180032516`
- `OLEAUT32!__imp_SysFreeString` at `0x1800325ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180032662`
- `OLEAUT32!__imp_SysFreeString` at `0x180032744`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18003287e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800328dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180032973`
- `OLEAUT32!__imp_SysFreeString` at `0x1800329d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a99`
- `OLEAUT32!__imp_SysFreeString` at `0x180032af7`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ba7`
- `OLEAUT32!__imp_SysFreeString` at `0x180032c05`
- `OLEAUT32!__imp_SysFreeString` at `0x180032cb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d13`
- `OLEAUT32!__imp_SysFreeString` at `0x180032dc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180032e21`
- `OLEAUT32!__imp_SysFreeString` at `0x180032e8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f61`
- `OLEAUT32!__imp_SysFreeString` at `0x180033007`
- `OLEAUT32!__imp_SysFreeString` at `0x18003309b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003318e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180033262`
- `OLEAUT32!__imp_SysFreeString` at `0x1800332c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003332d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033357`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180033436`
- `OLEAUT32!__imp_SysFreeString` at `0x180033460`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033521`
- `OLEAUT32!__imp_SysFreeString` at `0x1800335a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180033656`
- `OLEAUT32!__imp_SysFreeString` at `0x18003369a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003372f`
- `OLEAUT32!__imp_SysFreeString` at `0x180033773`
- `OLEAUT32!__imp_SysFreeString` at `0x18003380c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033850`
- `OLEAUT32!__imp_SysFreeString` at `0x1800338a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003392b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033a50`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180033229`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180033229`

## string_xrefs

- `0x18003284b`: `CoCreateInstance IObjectId`
- `0x180033068`: `CoCreateInstance IObjectId`
- `0x180033623`: `CoCreateInstance IObjectId`
- `0x180032335`: `CoCreateInstance IX509CertificateRequestPkcs10`
- `0x1800322e0`: `CreatePkcs10RequestFromKey`
- `0x18003244f`: `CoCreateInstance IX500DistinguishedName`
- `0x1800326dd`: `CoCreateInstance IX509ExtensionEnhancedKeyUsage`
- `0x180032efa`: `CoCreateInstance IX509ExtensionEnhancedKeyUsage`
- `0x180032615`: `IX500DistinguishedName->get_X509Extensions`
- `0x180032a4c`: `CoCreateInstance IObjectIds`
- `0x180032d76`: `IX509Extensions->Add`
- `0x18003341c`: `IX509Extensions->Add`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CreatePkcs10RequestFromKey(
        struct IX509PrivateKey *a1,
        unsigned __int8 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const CHAR *psz,
        UINT len,
        struct IX509CertificateRequestPkcs10 **a7)
{
  int v9; // esi
  HRESULT v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  LPVOID v14; // rcx
  int v16; // eax
  __int64 v17; // rcx
  LPVOID v18; // rcx
  OLECHAR *v19; // rbx
  HRESULT v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // edi
  LPVOID v23; // rcx
  LPVOID v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  LPVOID v27; // rcx
  LPVOID v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  LPVOID v31; // rcx
  LPVOID v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  LPVOID v36; // rcx
  LPVOID v37; // rcx
  HRESULT v38; // eax
  __int64 v39; // rcx
  LPVOID v40; // rcx
  __int64 v41; // rcx
  LPVOID v42; // rcx
  LPVOID v43; // rcx
  OLECHAR *v44; // rdi
  LPVOID v45; // rcx
  __int64 v46; // rcx
  LPVOID v47; // rcx
  HRESULT v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // esi
  LPVOID v51; // rcx
  LPVOID v52; // rcx
  __int64 v53; // rcx
  LPVOID v54; // rcx
  LPVOID v55; // rcx
  int v56; // eax
  __int64 v57; // rcx
  LPVOID v58; // rcx
  LPVOID v59; // rcx
  __int64 v60; // rcx
  LPVOID v61; // rcx
  LPVOID v62; // rcx
  HRESULT v63; // eax
  __int64 v64; // rcx
  LPVOID v65; // rcx
  LPVOID v66; // rcx
  LPVOID v67; // rcx
  __int64 v68; // rcx
  LPVOID v69; // rcx
  LPVOID v70; // rcx
  int v71; // eax
  __int64 v72; // rcx
  LPVOID v73; // rcx
  LPVOID v74; // rcx
  LPVOID v75; // rcx
  __int64 v76; // rcx
  LPVOID v77; // rcx
  LPVOID v78; // rcx
  int v79; // eax
  __int64 v80; // rcx
  LPVOID v81; // rcx
  LPVOID v82; // rcx
  LPVOID v83; // rcx
  __int64 v84; // rcx
  LPVOID v85; // rcx
  LPVOID v86; // rcx
  int v87; // eax
  __int64 v88; // rcx
  LPVOID v89; // rcx
  LPVOID v90; // rcx
  LPVOID v91; // rcx
  __int64 v92; // rcx
  LPVOID v93; // rcx
  LPVOID v94; // rcx
  LPVOID v95; // rcx
  LPVOID v96; // rcx
  LPVOID v97; // rcx
  HRESULT v98; // eax
  __int64 v99; // rcx
  LPVOID v100; // rcx
  __int64 v101; // rcx
  LPVOID v102; // rcx
  LPVOID v103; // rcx
  OLECHAR *v104; // rdi
  LPVOID v105; // rcx
  __int64 v106; // rcx
  LPVOID v107; // rcx
  HRESULT v108; // eax
  __int64 v109; // rcx
  LPVOID v110; // rcx
  LPVOID v111; // rcx
  __int64 v112; // rcx
  LPVOID v113; // rcx
  LPVOID v114; // rcx
  int v115; // eax
  __int64 v116; // rcx
  LPVOID v117; // rcx
  LPVOID v118; // rcx
  __int64 v119; // rcx
  LPVOID v120; // rcx
  LPVOID v121; // rcx
  BSTR v122; // rax
  OLECHAR *v123; // rsi
  LPVOID v124; // rcx
  LPVOID v125; // rcx
  __int64 v126; // rcx
  LPVOID v127; // rcx
  int v128; // eax
  __int64 v129; // rcx
  unsigned int v130; // r14d
  LPVOID v131; // rcx
  LPVOID v132; // rcx
  __int64 v133; // rcx
  LPVOID v134; // rcx
  LPVOID v135; // rcx
  int v136; // eax
  __int64 v137; // rcx
  LPVOID v138; // rcx
  LPVOID v139; // rcx
  __int64 v140; // rcx
  LPVOID v141; // rcx
  LPVOID v142; // rcx
  LPVOID v143; // rcx
  LPVOID v144; // rcx
  OLECHAR *v145; // rdi
  __int64 v146; // rcx
  LPVOID v147; // rcx
  LPVOID v148; // rcx
  HRESULT v149; // eax
  __int64 v150; // rcx
  LPVOID v151; // rcx
  __int64 v152; // rcx
  LPVOID v153; // rcx
  LPVOID v154; // rcx
  int v155; // eax
  __int64 v156; // rcx
  LPVOID v157; // rcx
  __int64 v158; // rcx
  LPVOID v159; // rcx
  LPVOID v160; // rcx
  int v161; // eax
  __int64 v162; // rcx
  LPVOID v163; // rcx
  __int64 v164; // rcx
  LPVOID v165; // rcx
  LPVOID v166; // rcx
  LPVOID v167; // rcx
  int v168; // eax
  __int64 v169; // rcx
  __int64 v170; // rcx
  LPVOID v171; // rcx
  LPVOID v172; // rcx
  int v173; // eax
  __int64 v174; // rcx
  __int64 v175; // rcx
  LPVOID v176; // rcx
  LPVOID v177; // rcx
  struct IX509CertificateRequestPkcs10 *v178; // rcx
  __int64 v179; // rcx
  LPVOID v180; // rcx
  LPVOID v181; // rcx
  HRESULT v182; // [rsp+30h] [rbp-61h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-59h] BYREF
  LPVOID v184; // [rsp+40h] [rbp-51h] BYREF
  __int64 v185; // [rsp+48h] [rbp-49h] BYREF
  LPVOID v186; // [rsp+50h] [rbp-41h] BYREF
  LPVOID v187; // [rsp+58h] [rbp-39h] BYREF
  LPVOID v188; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v189[2]; // [rsp+68h] [rbp-29h] BYREF
  OLECHAR *v190; // [rsp+78h] [rbp-19h]
  OLECHAR *v191; // [rsp+80h] [rbp-11h]

  v9 = a2;
  v182 = 0;
  ppv = 0;
  v189[0] = "CreatePkcs10RequestFromKey";
  v189[1] = &v182;
  v11 = CoCreateInstance(
          &GUID_884e2042_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab342_217d_11da_b2a4_000e7bbb2b09,
          &ppv);
  v13 = v11;
  v182 = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        v12,
        FunctionFailedEvent,
        L"CoCreateInstance IX509CertificateRequestPkcs10",
        (unsigned int)v11);
      v13 = v182;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
    v14 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v13;
  }
  v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IX509PrivateKey *, _QWORD))(*(_QWORD *)ppv + 264LL))(
          ppv,
          (unsigned int)(v9 + 1),
          a1,
          0);
  v13 = v16;
  v182 = v16;
  if ( v16 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        v17,
        FunctionFailedEvent,
        L"IX509CertificateRequestPkcs10->InitializeFromPrivateKey",
        (unsigned int)v16);
      v13 = v182;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
    v18 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v13;
  }
  v19 = SysAllocString(a3);
  v191 = v19;
  if ( v19 )
  {
    v184 = 0;
    v20 = CoCreateInstance(
            &GUID_884e2003_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab303_217d_11da_b2a4_000e7bbb2b09,
            &v184);
    v22 = v20;
    v182 = v20;
    if ( v20 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v21,
          FunctionFailedEvent,
          L"CoCreateInstance IX500DistinguishedName",
          (unsigned int)v20);
        v22 = v182;
      }
      v23 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v24 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v22;
    }
    v25 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v184 + 64LL))(v184, v19, 0);
    v22 = v25;
    v182 = v25;
    if ( v25 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v26,
          FunctionFailedEvent,
          L"IX500DistinguishedName->Encode",
          (unsigned int)v25);
        v22 = v182;
      }
      v27 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v28 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
      }
      return v22;
    }
    v29 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 368LL))(ppv, v184);
    v22 = v29;
    v182 = v29;
    if ( v29 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v30,
          FunctionFailedEvent,
          L"IX500DistinguishedName->put_Subject",
          (unsigned int)v29);
        v22 = v182;
      }
      v31 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v32 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
      }
      return v22;
    }
    v185 = 0;
    v33 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 432LL))(ppv, &v185);
    v22 = v33;
    v182 = v33;
    if ( v33 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v34,
          FunctionFailedEvent,
          L"IX500DistinguishedName->get_X509Extensions",
          (unsigned int)v33);
        v22 = v182;
      }
      v35 = v185;
      if ( v185 )
      {
        v185 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v36 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v37 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
      }
      return v22;
    }
    v186 = 0;
    v38 = CoCreateInstance(
            &GUID_884e2010_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab310_217d_11da_b2a4_000e7bbb2b09,
            &v186);
    v22 = v38;
    v182 = v38;
    if ( v38 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v39,
          FunctionFailedEvent,
          L"CoCreateInstance IX509ExtensionEnhancedKeyUsage",
          (unsigned int)v38);
        v22 = v182;
      }
      v40 = v186;
      if ( v186 )
      {
        v186 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v185;
      if ( v185 )
      {
        v185 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v42 + 16LL))(v42);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v43 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
      }
      return v22;
    }
    v44 = SysAllocString(L"1.3.6.1.5.5.7.3.2");
    v190 = v44;
    if ( !v44 )
    {
      v45 = v186;
      if ( v186 )
      {
        v186 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v46 = v185;
      if ( v185 )
      {
        v185 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
      }
LABEL_263:
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      goto LABEL_264;
    }
    v187 = 0;
    v48 = CoCreateInstance(
            &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
            &v187);
    v50 = v48;
    v182 = v48;
    if ( v48 >= 0 )
    {
      v56 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v187 + 64LL))(v187, v44);
      v50 = v56;
      v182 = v56;
      if ( v56 >= 0 )
      {
        v188 = 0;
        v63 = CoCreateInstance(
                &GUID_884e2001_217d_11da_b2a4_000e7bbb2b09,
                0,
                1u,
                &GUID_728ab301_217d_11da_b2a4_000e7bbb2b09,
                &v188);
        v50 = v63;
        v182 = v63;
        if ( v63 >= 0 )
        {
          v71 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v188 + 80LL))(v188, v187);
          v50 = v71;
          v182 = v71;
          if ( v71 >= 0 )
          {
            v79 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v186 + 96LL))(v186, v188);
            v50 = v79;
            v182 = v79;
            if ( v79 >= 0 )
            {
              v87 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v185 + 80LL))(v185, v186);
              v50 = v87;
              v182 = v87;
              if ( v87 >= 0 )
              {
                v95 = v188;
                if ( v188 )
                {
                  v188 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v95 + 16LL))(v95);
                }
                v96 = v187;
                if ( v187 )
                {
                  v187 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
                }
                SysFreeString(v44);
                v97 = v186;
                if ( v186 )
                {
                  v186 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v97 + 16LL))(v97);
                }
                v186 = 0;
                v98 = CoCreateInstance(
                        &GUID_884e200d_217d_11da_b2a4_000e7bbb2b09,
                        0,
                        1u,
                        &GUID_728ab30d_217d_11da_b2a4_000e7bbb2b09,
                        &v186);
                v22 = v98;
                v182 = v98;
                if ( v98 < 0 )
                {
                  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                  {
                    McTemplateU0zq_EventWriteTransfer(
                      v99,
                      FunctionFailedEvent,
                      L"CoCreateInstance IX509ExtensionEnhancedKeyUsage",
                      (unsigned int)v98);
                    v22 = v182;
                  }
                  v100 = v186;
                  if ( v186 )
                  {
                    v186 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
                  }
                  v101 = v185;
                  if ( v185 )
                  {
                    v185 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
                  }
                  v102 = v184;
                  if ( v184 )
                  {
                    v184 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v102 + 16LL))(v102);
                  }
                  SysFreeString(v19);
                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                  v103 = ppv;
                  if ( ppv )
                  {
                    ppv = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v103 + 16LL))(v103);
                  }
                  return v22;
                }
                v104 = SysAllocString(L"1.3.6.1.4.1.311.66.1.0");
                v190 = v104;
                if ( !v104 )
                {
                  v105 = v186;
                  if ( v186 )
                  {
                    v186 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v105 + 16LL))(v105);
                  }
                  v106 = v185;
                  if ( v185 )
                  {
                    v185 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
                  }
                  v107 = v184;
                  if ( v184 )
                  {
                    v184 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v107 + 16LL))(v107);
                  }
                  goto LABEL_263;
                }
                v187 = 0;
                v108 = CoCreateInstance(
                         &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
                         0,
                         1u,
                         &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
                         &v187);
                v50 = v108;
                v182 = v108;
                if ( v108 >= 0 )
                {
                  v115 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v187 + 64LL))(v187, v104);
                  v50 = v115;
                  v182 = v115;
                  if ( v115 >= 0 )
                  {
                    v122 = SysAllocStringByteLen(psz, len);
                    v123 = v122;
                    v188 = v122;
                    if ( !v122 )
                    {
                      v124 = v187;
                      if ( v187 )
                      {
                        v187 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v124 + 16LL))(v124);
                      }
                      SysFreeString(v104);
                      v125 = v186;
                      if ( v186 )
                      {
                        v186 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v125 + 16LL))(v125);
                      }
                      v126 = v185;
                      if ( v185 )
                      {
                        v185 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
                      }
                      v127 = v184;
                      if ( v184 )
                      {
                        v184 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v127 + 16LL))(v127);
                      }
                      goto LABEL_263;
                    }
                    v128 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64, BSTR))(*(_QWORD *)v186 + 56LL))(
                             v186,
                             v187,
                             2,
                             v122);
                    v130 = v128;
                    v182 = v128;
                    if ( v128 >= 0 )
                    {
                      v136 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v185 + 80LL))(v185, v186);
                      v130 = v136;
                      v182 = v136;
                      if ( v136 >= 0 )
                      {
                        SysFreeString(v123);
                        v143 = v187;
                        if ( v187 )
                        {
                          v187 = 0;
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v143 + 16LL))(v143);
                        }
                        SysFreeString(v104);
                        v144 = v186;
                        if ( v186 )
                        {
                          v186 = 0;
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v144 + 16LL))(v144);
                        }
                        if ( a4 )
                        {
                          v145 = SysAllocString(a4);
                          v190 = v145;
                          if ( !v145 )
                          {
                            v146 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
                            }
                            v147 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v147 + 16LL))(v147);
                            }
                            goto LABEL_263;
                          }
                          v188 = 0;
                          v149 = CoCreateInstance(
                                   &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
                                   0,
                                   1u,
                                   &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
                                   &v188);
                          v50 = v149;
                          v182 = v149;
                          if ( v149 < 0 )
                          {
                            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                            {
                              McTemplateU0zq_EventWriteTransfer(
                                v150,
                                FunctionFailedEvent,
                                L"CoCreateInstance IObjectId",
                                (unsigned int)v149);
                              v50 = v182;
                            }
                            v151 = v188;
                            if ( v188 )
                            {
                              v188 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v151 + 16LL))(v151);
                            }
                            SysFreeString(v145);
                            v152 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v152 + 16LL))(v152);
                            }
                            v153 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v153 + 16LL))(v153);
                            }
                            SysFreeString(v19);
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                            v154 = ppv;
                            if ( ppv )
                            {
                              ppv = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v154 + 16LL))(v154);
                            }
                            return v50;
                          }
                          v155 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v188 + 64LL))(v188, v145);
                          v50 = v155;
                          v182 = v155;
                          if ( v155 < 0 )
                          {
                            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                            {
                              McTemplateU0zq_EventWriteTransfer(
                                v156,
                                FunctionFailedEvent,
                                L"IObjectId->InitializeFromValue",
                                (unsigned int)v155);
                              v50 = v182;
                            }
                            v157 = v188;
                            if ( v188 )
                            {
                              v188 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v157 + 16LL))(v157);
                            }
                            SysFreeString(v145);
                            v158 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v158 + 16LL))(v158);
                            }
                            v159 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v159 + 16LL))(v159);
                            }
                            SysFreeString(v19);
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                            v160 = ppv;
                            if ( ppv )
                            {
                              ppv = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v160 + 16LL))(v160);
                            }
                            return v50;
                          }
                          v161 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 224LL))(ppv, v188);
                          v50 = v161;
                          v182 = v161;
                          if ( v161 < 0 )
                          {
                            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                            {
                              McTemplateU0zq_EventWriteTransfer(
                                v162,
                                FunctionFailedEvent,
                                L"IX509CertificateRequestPkcs10->put_HashAlgorithm",
                                (unsigned int)v161);
                              v50 = v182;
                            }
                            v163 = v188;
                            if ( v188 )
                            {
                              v188 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v163 + 16LL))(v163);
                            }
                            SysFreeString(v145);
                            v164 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v164 + 16LL))(v164);
                            }
                            v165 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v165 + 16LL))(v165);
                            }
                            SysFreeString(v19);
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                            v166 = ppv;
                            if ( ppv )
                            {
                              ppv = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v166 + 16LL))(v166);
                            }
                            return v50;
                          }
                          v167 = v188;
                          if ( v188 )
                          {
                            v188 = 0;
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v167 + 16LL))(v167);
                          }
                          SysFreeString(v145);
                        }
                        v168 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, 1);
                        v22 = v168;
                        v182 = v168;
                        if ( v168 >= 0 )
                        {
                          v173 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 64LL))(ppv);
                          v22 = v173;
                          v182 = v173;
                          if ( v173 >= 0 )
                          {
                            v178 = (struct IX509CertificateRequestPkcs10 *)ppv;
                            ppv = 0;
                            *a7 = v178;
                            v179 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 16LL))(v179);
                            }
                            v180 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v180 + 16LL))(v180);
                            }
                            SysFreeString(v19);
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                            v181 = ppv;
                            if ( ppv )
                            {
                              ppv = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v181 + 16LL))(v181);
                            }
                          }
                          else
                          {
                            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                            {
                              McTemplateU0zq_EventWriteTransfer(
                                v174,
                                FunctionFailedEvent,
                                L"IX509CertificateRequestPkcs10->Encode",
                                (unsigned int)v173);
                              v22 = v182;
                            }
                            v175 = v185;
                            if ( v185 )
                            {
                              v185 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v175 + 16LL))(v175);
                            }
                            v176 = v184;
                            if ( v184 )
                            {
                              v184 = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v176 + 16LL))(v176);
                            }
                            SysFreeString(v19);
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                            v177 = ppv;
                            if ( ppv )
                            {
                              ppv = 0;
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v177 + 16LL))(v177);
                            }
                          }
                        }
                        else
                        {
                          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                          {
                            McTemplateU0zq_EventWriteTransfer(
                              v169,
                              FunctionFailedEvent,
                              L"IX509CertificateRequestPkcs10->put_SuppressDefaults",
                              (unsigned int)v168);
                            v22 = v182;
                          }
                          v170 = v185;
                          if ( v185 )
                          {
                            v185 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v170 + 16LL))(v170);
                          }
                          v171 = v184;
                          if ( v184 )
                          {
                            v184 = 0;
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v171 + 16LL))(v171);
                          }
                          SysFreeString(v19);
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                          v172 = ppv;
                          if ( ppv )
                          {
                            ppv = 0;
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v172 + 16LL))(v172);
                          }
                        }
                        return v22;
                      }
                      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                      {
                        McTemplateU0zq_EventWriteTransfer(
                          v137,
                          FunctionFailedEvent,
                          L"IX509Extensions->Add",
                          (unsigned int)v136);
                        v130 = v182;
                      }
                      SysFreeString(v123);
                      v138 = v187;
                      if ( v187 )
                      {
                        v187 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v138 + 16LL))(v138);
                      }
                      SysFreeString(v104);
                      v139 = v186;
                      if ( v186 )
                      {
                        v186 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v139 + 16LL))(v139);
                      }
                      v140 = v185;
                      if ( v185 )
                      {
                        v185 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
                      }
                      v141 = v184;
                      if ( v184 )
                      {
                        v184 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v141 + 16LL))(v141);
                      }
                      SysFreeString(v19);
                      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                      v142 = ppv;
                      if ( ppv )
                      {
                        ppv = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v142 + 16LL))(v142);
                      }
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                      {
                        McTemplateU0zq_EventWriteTransfer(
                          v129,
                          FunctionFailedEvent,
                          L"IObjectIds->InitializeEncode",
                          (unsigned int)v128);
                        v130 = v182;
                      }
                      SysFreeString(v123);
                      v131 = v187;
                      if ( v187 )
                      {
                        v187 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v131 + 16LL))(v131);
                      }
                      SysFreeString(v104);
                      v132 = v186;
                      if ( v186 )
                      {
                        v186 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v132 + 16LL))(v132);
                      }
                      v133 = v185;
                      if ( v185 )
                      {
                        v185 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
                      }
                      v134 = v184;
                      if ( v184 )
                      {
                        v184 = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v134 + 16LL))(v134);
                      }
                      SysFreeString(v19);
                      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                      v135 = ppv;
                      if ( ppv )
                      {
                        ppv = 0;
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v135 + 16LL))(v135);
                      }
                    }
                    return v130;
                  }
                  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                  {
                    McTemplateU0zq_EventWriteTransfer(
                      v116,
                      FunctionFailedEvent,
                      L"IObjectId->InitializeFromValue",
                      (unsigned int)v115);
                    v50 = v182;
                  }
                  v117 = v187;
                  if ( v187 )
                  {
                    v187 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v117 + 16LL))(v117);
                  }
                  SysFreeString(v104);
                  v118 = v186;
                  if ( v186 )
                  {
                    v186 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v118 + 16LL))(v118);
                  }
                  v119 = v185;
                  if ( v185 )
                  {
                    v185 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
                  }
                  v120 = v184;
                  if ( v184 )
                  {
                    v184 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v120 + 16LL))(v120);
                  }
                  SysFreeString(v19);
                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                  v121 = ppv;
                  if ( ppv )
                  {
                    ppv = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v121 + 16LL))(v121);
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                  {
                    McTemplateU0zq_EventWriteTransfer(
                      v109,
                      FunctionFailedEvent,
                      L"CoCreateInstance IObjectId",
                      (unsigned int)v108);
                    v50 = v182;
                  }
                  v110 = v187;
                  if ( v187 )
                  {
                    v187 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v110 + 16LL))(v110);
                  }
                  SysFreeString(v104);
                  v111 = v186;
                  if ( v186 )
                  {
                    v186 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v111 + 16LL))(v111);
                  }
                  v112 = v185;
                  if ( v185 )
                  {
                    v185 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
                  }
                  v113 = v184;
                  if ( v184 )
                  {
                    v184 = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v113 + 16LL))(v113);
                  }
                  SysFreeString(v19);
                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                  v114 = ppv;
                  if ( ppv )
                  {
                    ppv = 0;
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v114 + 16LL))(v114);
                  }
                }
              }
              else
              {
                if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                {
                  McTemplateU0zq_EventWriteTransfer(
                    v88,
                    FunctionFailedEvent,
                    L"IX509Extensions->Add",
                    (unsigned int)v87);
                  v50 = v182;
                }
                v89 = v188;
                if ( v188 )
                {
                  v188 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v89 + 16LL))(v89);
                }
                v90 = v187;
                if ( v187 )
                {
                  v187 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
                }
                SysFreeString(v44);
                v91 = v186;
                if ( v186 )
                {
                  v186 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v91 + 16LL))(v91);
                }
                v92 = v185;
                if ( v185 )
                {
                  v185 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                }
                v93 = v184;
                if ( v184 )
                {
                  v184 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v93 + 16LL))(v93);
                }
                SysFreeString(v19);
                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
                v94 = ppv;
                if ( ppv )
                {
                  ppv = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v94 + 16LL))(v94);
                }
              }
            }
            else
            {
              if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
              {
                McTemplateU0zq_EventWriteTransfer(
                  v80,
                  FunctionFailedEvent,
                  L"IObjectIds->InitializeEncode",
                  (unsigned int)v79);
                v50 = v182;
              }
              v81 = v188;
              if ( v188 )
              {
                v188 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v81 + 16LL))(v81);
              }
              v82 = v187;
              if ( v187 )
              {
                v187 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v82 + 16LL))(v82);
              }
              SysFreeString(v44);
              v83 = v186;
              if ( v186 )
              {
                v186 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v83 + 16LL))(v83);
              }
              v84 = v185;
              if ( v185 )
              {
                v185 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
              }
              v85 = v184;
              if ( v184 )
              {
                v184 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v85 + 16LL))(v85);
              }
              SysFreeString(v19);
              EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
              v86 = ppv;
              if ( ppv )
              {
                ppv = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v86 + 16LL))(v86);
              }
            }
          }
          else
          {
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
            {
              McTemplateU0zq_EventWriteTransfer(v72, FunctionFailedEvent, L"IObjectIds->Add", (unsigned int)v71);
              v50 = v182;
            }
            v73 = v188;
            if ( v188 )
            {
              v188 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 16LL))(v73);
            }
            v74 = v187;
            if ( v187 )
            {
              v187 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v74 + 16LL))(v74);
            }
            SysFreeString(v44);
            v75 = v186;
            if ( v186 )
            {
              v186 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
            }
            v76 = v185;
            if ( v185 )
            {
              v185 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            }
            v77 = v184;
            if ( v184 )
            {
              v184 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
            }
            SysFreeString(v19);
            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
            v78 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v78 + 16LL))(v78);
            }
          }
        }
        else
        {
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
          {
            McTemplateU0zq_EventWriteTransfer(
              v64,
              FunctionFailedEvent,
              L"CoCreateInstance IObjectIds",
              (unsigned int)v63);
            v50 = v182;
          }
          v65 = v188;
          if ( v188 )
          {
            v188 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 16LL))(v65);
          }
          v66 = v187;
          if ( v187 )
          {
            v187 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
          }
          SysFreeString(v44);
          v67 = v186;
          if ( v186 )
          {
            v186 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v67 + 16LL))(v67);
          }
          v68 = v185;
          if ( v185 )
          {
            v185 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
          }
          v69 = v184;
          if ( v184 )
          {
            v184 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v69 + 16LL))(v69);
          }
          SysFreeString(v19);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
          v70 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
          }
        }
      }
      else
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        {
          McTemplateU0zq_EventWriteTransfer(
            v57,
            FunctionFailedEvent,
            L"IObjectId->InitializeFromValue",
            (unsigned int)v56);
          v50 = v182;
        }
        v58 = v187;
        if ( v187 )
        {
          v187 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v58 + 16LL))(v58);
        }
        SysFreeString(v44);
        v59 = v186;
        if ( v186 )
        {
          v186 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v59 + 16LL))(v59);
        }
        v60 = v185;
        if ( v185 )
        {
          v185 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        }
        v61 = v184;
        if ( v184 )
        {
          v184 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
        }
        SysFreeString(v19);
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
        v62 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v62 + 16LL))(v62);
        }
      }
    }
    else
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(v49, FunctionFailedEvent, L"CoCreateInstance IObjectId", (unsigned int)v48);
        v50 = v182;
      }
      v51 = v187;
      if ( v187 )
      {
        v187 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v51 + 16LL))(v51);
      }
      SysFreeString(v44);
      v52 = v186;
      if ( v186 )
      {
        v186 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v185;
      if ( v185 )
      {
        v185 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      v54 = v184;
      if ( v184 )
      {
        v184 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v54 + 16LL))(v54);
      }
      SysFreeString(v19);
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
      v55 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
      }
    }
    return v50;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v189);
LABEL_264:
  v148 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v148 + 16LL))(v148);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800322b0  push    rbp
0x1800322b2  push    rbx
0x1800322b3  push    rsi
0x1800322b4  push    rdi
0x1800322b5  push    r12
0x1800322b7  push    r13
0x1800322b9  push    r14
0x1800322bb  push    r15
0x1800322bd  lea     rbp, [rsp-7]
0x1800322c2  sub     rsp, 98h
0x1800322c9  mov     r15, r9
0x1800322cc  mov     rdi, r8
0x1800322cf  movzx   esi, dl
0x1800322d2  mov     r14, rcx
0x1800322d5  xor     r12d, r12d
0x1800322d8  mov     [rbp+3Fh+var_A0], r12d
0x1800322dc  mov     [rbp+3Fh+var_98], r12
0x1800322e0  lea     rax, aCreatepkcs10re_0; "CreatePkcs10RequestFromKey"
0x1800322e7  mov     [rbp+3Fh+var_68], rax
0x1800322eb  lea     rax, [rbp+3Fh+var_A0]
0x1800322ef  mov     [rbp+3Fh+var_60], rax
0x1800322f3  lea     rax, [rbp+3Fh+var_98]
0x1800322f7  mov     [rsp+0D0h+ppv], rax; ppv
0x1800322fc  lea     r9, _GUID_728ab342_217d_11da_b2a4_000e7bbb2b09; riid
0x180032303  lea     r13d, [r12+1]
0x180032308  mov     r8d, r13d; dwClsContext
0x18003230b  xor     edx, edx; pUnkOuter
0x18003230d  lea     rcx, _GUID_884e2042_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180032314  call    cs:__imp_CoCreateInstance
0x18003231b  nop     dword ptr [rax+rax+00h]
0x180032320  mov     ebx, eax
0x180032322  mov     [rbp+3Fh+var_A0], eax
0x180032325  test    eax, eax
0x180032327  jns     short loc_180032376
0x180032329  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180032330  jz      short loc_18003234B
0x180032332  mov     r9d, eax
0x180032335  lea     r8, aCocreateinstan_3; "CoCreateInstance IX509CertificateReques"...
0x18003233c  lea     rdx, FunctionFailedEvent
0x180032343  call    McTemplateU0zq_EventWriteTransfer
0x180032348  mov     ebx, [rbp+3Fh+var_A0]
0x18003234b  lea     rcx, [rbp+3Fh+var_68]; this
0x18003234f  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180032354  nop
0x180032355  mov     rcx, [rbp+3Fh+var_98]
0x180032359  test    rcx, rcx
0x18003235c  jz      short loc_18003236F
0x18003235e  mov     [rbp+3Fh+var_98], r12
0x180032362  mov     rdx, [rcx]
0x180032365  mov     rax, [rdx+10h]
0x180032369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003236e  nop
0x18003236f  mov     eax, ebx
0x180032371  jmp     loc_180033A83
0x180032376  mov     rcx, [rbp+3Fh+var_98]
0x18003237a  mov     rax, [rcx]
0x18003237d  lea     edx, [rsi+r13]
0x180032381  xor     r9d, r9d
0x180032384  mov     r8, r14
0x180032387  mov     rax, [rax+108h]
0x18003238e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032393  mov     ebx, eax
0x180032395  mov     [rbp+3Fh+var_A0], eax
0x180032398  test    eax, eax
0x18003239a  jns     short loc_1800323E4
0x18003239c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800323a3  jz      short loc_1800323BE
0x1800323a5  mov     r9d, eax
0x1800323a8  lea     r8, aIx509certifica_6; "IX509CertificateRequestPkcs10->Initiali"...
0x1800323af  lea     rdx, FunctionFailedEvent
0x1800323b6  call    McTemplateU0zq_EventWriteTransfer
0x1800323bb  mov     ebx, [rbp+3Fh+var_A0]
0x1800323be  lea     rcx, [rbp+3Fh+var_68]; this
0x1800323c2  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800323c7  nop
0x1800323c8  mov     rcx, [rbp+3Fh+var_98]
0x1800323cc  test    rcx, rcx
0x1800323cf  jz      short loc_1800323E2
0x1800323d1  mov     [rbp+3Fh+var_98], r12
0x1800323d5  mov     rdx, [rcx]
0x1800323d8  mov     rax, [rdx+10h]
0x1800323dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323e1  nop
0x1800323e2  jmp     short loc_18003236F
0x1800323e4  mov     rcx, rdi; psz
0x1800323e7  call    cs:__imp_SysAllocString
0x1800323ee  nop     dword ptr [rax+rax+00h]
0x1800323f3  mov     rbx, rax
0x1800323f6  mov     [rbp+3Fh+var_50], rax
0x1800323fa  test    rax, rax
0x1800323fd  jnz     short loc_18003240E
0x1800323ff  lea     rcx, [rbp+3Fh+var_68]; this
0x180032403  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180032408  nop
0x180032409  jmp     loc_1800335BA
0x18003240e  mov     [rbp+3Fh+var_90], r12
0x180032412  lea     rax, [rbp+3Fh+var_90]
0x180032416  mov     [rsp+0D0h+ppv], rax; ppv
0x18003241b  lea     r9, _GUID_728ab303_217d_11da_b2a4_000e7bbb2b09; riid
0x180032422  mov     r8d, r13d; dwClsContext
0x180032425  xor     edx, edx; pUnkOuter
0x180032427  lea     rcx, _GUID_884e2003_217d_11da_b2a4_000e7bbb2b09; rclsid
0x18003242e  call    cs:__imp_CoCreateInstance
0x180032435  nop     dword ptr [rax+rax+00h]
0x18003243a  mov     edi, eax
0x18003243c  mov     [rbp+3Fh+var_A0], eax
0x18003243f  test    eax, eax
0x180032441  jns     short loc_1800324B8
0x180032443  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18003244a  jz      short loc_180032465
0x18003244c  mov     r9d, eax
0x18003244f  lea     r8, aCocreateinstan_2; "CoCreateInstance IX500DistinguishedName"
0x180032456  lea     rdx, FunctionFailedEvent
0x18003245d  call    McTemplateU0zq_EventWriteTransfer
0x180032462  mov     edi, [rbp+3Fh+var_A0]
0x180032465  mov     rcx, [rbp+3Fh+var_90]
0x180032469  test    rcx, rcx
0x18003246c  jz      short loc_18003247F
0x18003246e  mov     [rbp+3Fh+var_90], r12
0x180032472  mov     rax, [rcx]
0x180032475  mov     rax, [rax+10h]
0x180032479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003247e  nop
0x18003247f  mov     rcx, rbx; bstrString
0x180032482  call    cs:__imp_SysFreeString
0x180032489  nop     dword ptr [rax+rax+00h]
0x18003248e  nop
0x18003248f  lea     rcx, [rbp+3Fh+var_68]; this
0x180032493  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180032498  nop
0x180032499  mov     rcx, [rbp+3Fh+var_98]
0x18003249d  test    rcx, rcx
0x1800324a0  jz      short loc_1800324B3
0x1800324a2  mov     [rbp+3Fh+var_98], r12
0x1800324a6  mov     rdx, [rcx]
0x1800324a9  mov     rax, [rdx+10h]
0x1800324ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324b2  nop
0x1800324b3  jmp     loc_180033A81
0x1800324b8  mov     rcx, [rbp+3Fh+var_90]
0x1800324bc  mov     rax, [rcx]
0x1800324bf  xor     r8d, r8d
0x1800324c2  mov     rdx, rbx
0x1800324c5  mov     rax, [rax+40h]
0x1800324c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324ce  mov     edi, eax
0x1800324d0  mov     [rbp+3Fh+var_A0], eax
0x1800324d3  test    eax, eax
0x1800324d5  jns     short loc_18003254C
0x1800324d7  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800324de  jz      short loc_1800324F9
0x1800324e0  mov     r9d, eax
0x1800324e3  lea     r8, aIx500distingui_1; "IX500DistinguishedName->Encode"
0x1800324ea  lea     rdx, FunctionFailedEvent
0x1800324f1  call    McTemplateU0zq_EventWriteTransfer
0x1800324f6  mov     edi, [rbp+3Fh+var_A0]
0x1800324f9  mov     rcx, [rbp+3Fh+var_90]
0x1800324fd  test    rcx, rcx
0x180032500  jz      short loc_180032513
0x180032502  mov     [rbp+3Fh+var_90], r12
0x180032506  mov     rax, [rcx]
0x180032509  mov     rax, [rax+10h]
0x18003250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032512  nop
0x180032513  mov     rcx, rbx; bstrString
0x180032516  call    cs:__imp_SysFreeString
0x18003251d  nop     dword ptr [rax+rax+00h]
0x180032522  nop
0x180032523  lea     rcx, [rbp+3Fh+var_68]; this
0x180032527  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18003252c  nop
0x18003252d  mov     rcx, [rbp+3Fh+var_98]
0x180032531  test    rcx, rcx
0x180032534  jz      short loc_180032547
0x180032536  mov     [rbp+3Fh+var_98], r12
0x18003253a  mov     rdx, [rcx]
0x18003253d  mov     rax, [rdx+10h]
0x180032541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032546  nop
0x180032547  jmp     loc_180033A81
0x18003254c  mov     rcx, [rbp+3Fh+var_98]
0x180032550  mov     rax, [rcx]
0x180032553  mov     rdx, [rbp+3Fh+var_90]
0x180032557  mov     rax, [rax+170h]
0x18003255e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032563  mov     edi, eax
0x180032565  mov     [rbp+3Fh+var_A0], eax
0x180032568  test    eax, eax
0x18003256a  jns     short loc_1800325E1
0x18003256c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180032573  jz      short loc_18003258E
0x180032575  mov     r9d, eax
0x180032578  lea     r8, aIx500distingui; "IX500DistinguishedName->put_Subject"
0x18003257f  lea     rdx, FunctionFailedEvent
0x180032586  call    McTemplateU0zq_EventWriteTransfer
0x18003258b  mov     edi, [rbp+3Fh+var_A0]
0x18003258e  mov     rcx, [rbp+3Fh+var_90]
0x180032592  test    rcx, rcx
0x180032595  jz      short loc_1800325A8
0x180032597  mov     [rbp+3Fh+var_90], r12
0x18003259b  mov     rax, [rcx]
0x18003259e  mov     rax, [rax+10h]
0x1800325a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a7  nop
0x1800325a8  mov     rcx, rbx; bstrString
0x1800325ab  call    cs:__imp_SysFreeString
0x1800325b2  nop     dword ptr [rax+rax+00h]
0x1800325b7  nop
0x1800325b8  lea     rcx, [rbp+3Fh+var_68]; this
0x1800325bc  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800325c1  nop
0x1800325c2  mov     rcx, [rbp+3Fh+var_98]
0x1800325c6  test    rcx, rcx
0x1800325c9  jz      short loc_1800325DC
0x1800325cb  mov     [rbp+3Fh+var_98], r12
0x1800325cf  mov     rdx, [rcx]
0x1800325d2  mov     rax, [rdx+10h]
0x1800325d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325db  nop
0x1800325dc  jmp     loc_180033A81
0x1800325e1  mov     [rbp+3Fh+var_88], r12
0x1800325e5  mov     rcx, [rbp+3Fh+var_98]
0x1800325e9  mov     rax, [rcx]
0x1800325ec  lea     rdx, [rbp+3Fh+var_88]
0x1800325f0  mov     rax, [rax+1B0h]
0x1800325f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325fc  mov     edi, eax
0x1800325fe  mov     [rbp+3Fh+var_A0], eax
0x180032601  test    eax, eax
0x180032603  jns     loc_180032698
0x180032609  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180032610  jz      short loc_18003262B
0x180032612  mov     r9d, eax
0x180032615  lea     r8, aIx500distingui_0; "IX500DistinguishedName->get_X509Extensi"...
0x18003261c  lea     rdx, FunctionFailedEvent
0x180032623  call    McTemplateU0zq_EventWriteTransfer
0x180032628  mov     edi, [rbp+3Fh+var_A0]
0x18003262b  mov     rcx, [rbp+3Fh+var_88]
0x18003262f  test    rcx, rcx
0x180032632  jz      short loc_180032645
0x180032634  mov     [rbp+3Fh+var_88], r12
0x180032638  mov     rax, [rcx]
0x18003263b  mov     rax, [rax+10h]
0x18003263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032644  nop
0x180032645  mov     rcx, [rbp+3Fh+var_90]
0x180032649  test    rcx, rcx
0x18003264c  jz      short loc_18003265F
0x18003264e  mov     [rbp+3Fh+var_90], r12
0x180032652  mov     rax, [rcx]
0x180032655  mov     rax, [rax+10h]
0x180032659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003265e  nop
0x18003265f  mov     rcx, rbx; bstrString
0x180032662  call    cs:__imp_SysFreeString
0x180032669  nop     dword ptr [rax+rax+00h]
0x18003266e  nop
0x18003266f  lea     rcx, [rbp+3Fh+var_68]; this
0x180032673  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180032678  nop
0x180032679  mov     rcx, [rbp+3Fh+var_98]
0x18003267d  test    rcx, rcx
0x180032680  jz      short loc_180032693
0x180032682  mov     [rbp+3Fh+var_98], r12
0x180032686  mov     rdx, [rcx]
0x180032689  mov     rax, [rdx+10h]
0x18003268d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032692  nop
0x180032693  jmp     loc_180033A81
0x180032698  mov     [rbp+3Fh+var_80], r12
0x18003269c  lea     rax, [rbp+3Fh+var_80]
0x1800326a0  mov     [rsp+0D0h+ppv], rax; ppv
0x1800326a5  lea     r9, _GUID_728ab310_217d_11da_b2a4_000e7bbb2b09; riid
0x1800326ac  mov     r8d, r13d; dwClsContext
0x1800326af  xor     edx, edx; pUnkOuter
0x1800326b1  lea     rcx, _GUID_884e2010_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800326b8  call    cs:__imp_CoCreateInstance
0x1800326bf  nop     dword ptr [rax+rax+00h]
0x1800326c4  mov     edi, eax
0x1800326c6  mov     [rbp+3Fh+var_A0], eax
0x1800326c9  test    eax, eax
0x1800326cb  jns     loc_18003277A
0x1800326d1  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800326d8  jz      short loc_1800326F3
0x1800326da  mov     r9d, eax
0x1800326dd  lea     r8, aCocreateinstan_6; "CoCreateInstance IX509ExtensionEnhanced"...
0x1800326e4  lea     rdx, FunctionFailedEvent
0x1800326eb  call    McTemplateU0zq_EventWriteTransfer
0x1800326f0  mov     edi, [rbp+3Fh+var_A0]
0x1800326f3  mov     rcx, [rbp+3Fh+var_80]
0x1800326f7  test    rcx, rcx
0x1800326fa  jz      short loc_18003270D
0x1800326fc  mov     [rbp+3Fh+var_80], r12
0x180032700  mov     rax, [rcx]
0x180032703  mov     rax, [rax+10h]
0x180032707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003270c  nop
0x18003270d  mov     rcx, [rbp+3Fh+var_88]
0x180032711  test    rcx, rcx
0x180032714  jz      short loc_180032727
  ... truncated ...
```
