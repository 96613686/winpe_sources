# ndesHttpGet(ushort const *,ushort const *,ulong,bool,bool,ulong,uchar const *,ulong,ushort const *,ushort const *,uchar * *,ulong *,long *,ushort * *)

- ea: `0x180028a64`
- end: `0x18002930a`
- name: `?ndesHttpGet@@YAJPEBG0K_N1KPEBEK00PEAPEAEPEAKPEAJPEAPEAG@Z`
- size: `2214`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, bool@<r9b>, bool, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, int *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028444`
- `0x180028638`
- `0x180029310`

## callees

- `0x18000ba10`
- `0x18001d97c`
- `0x18001f188`
- `0x18001f958`
- `0x1800200c0`
- `0x180020578`
- `0x180020a6c`
- `0x180021438`
- `0x180028730`
- `0x18002893c`
- `0x180028958`
- `0x180028a64`
- `0x180029448`
- `0x180029548`
- `0x180029594`
- `0x18002bb20`
- `0x18002bbd8`
- `0x18002be30`
- `0x18002c8a8`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002913a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029288`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029291`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002929a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002913a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029288`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029291`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002929a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180029215`
- `OLEAUT32!__imp_SysAllocString` at `0x180029215`
- `OLEAUT32!__imp_VariantInit` at `0x180028b68`
- `OLEAUT32!__imp_VariantInit` at `0x180028b73`
- `OLEAUT32!__imp_VariantInit` at `0x180029042`
- `OLEAUT32!__imp_VariantInit` at `0x180028b68`
- `OLEAUT32!__imp_VariantInit` at `0x180028b73`
- `OLEAUT32!__imp_VariantInit` at `0x180029042`
- `OLEAUT32!__imp_VariantClear` at `0x1800292a5`
- `OLEAUT32!__imp_VariantClear` at `0x1800292af`
- `OLEAUT32!__imp_VariantClear` at `0x1800292a5`
- `OLEAUT32!__imp_VariantClear` at `0x1800292af`
- `certca!__imp_?myCryptBinaryToString@@YAJPEBEKKPEAPEAG@Z` at `0x180028ccd`
- `certca!__imp_?myCryptBinaryToString@@YAJPEBEKKPEAPEAG@Z` at `0x180028ccd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028d38`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028dff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028e4f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028ef8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028f62`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028f85`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028ff1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029010`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029088`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800290da`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029178`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800291a3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029205`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029274`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028d38`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028dff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028e4f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028ef8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028f62`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028f85`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028ff1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029010`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029088`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800290da`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029178`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800291a3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029205`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180029274`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028b93`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028bbc`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028dbf`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028f36`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028fb6`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029037`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029189`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029240`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028b93`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028bbc`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028dbf`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028f36`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180028fb6`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029037`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029189`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180029240`

## string_xrefs

- `0x180029108`: `application/json; charset=utf-8`
- `0x180029121`: `application/json`
- `0x180028bd1`: `mscep/mscep.dll/pkiclient.exe`
- `0x180028cb0`: `mscep/mscep.dll/pkiclient.exe`
- `0x180028ce5`: `mscep/mscep.dll/pkiclient.exe`
- `0x180028e6c`: `Content-Type:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ndesHttpGet(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        char a4,
        bool a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        unsigned __int8 **a11,
        unsigned int *a12,
        int *a13,
        unsigned __int16 **a14)
{
  const WCHAR *v16; // rbx
  WCHAR *v17; // r12
  int v18; // eax
  int v19; // ebx
  int v20; // r8d
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rcx
  HLOCAL v23; // rdi
  void *v24; // rsi
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // r15
  const unsigned __int16 *v27; // rsi
  char v28; // r14
  int v29; // edx
  unsigned int v30; // ecx
  char v31; // r13
  int v32; // eax
  struct tagVARIANT *v33; // r9
  int v34; // eax
  int v35; // eax
  int v36; // edx
  unsigned int v37; // ecx
  const unsigned __int16 *v38; // rdx
  int v39; // eax
  int fixed; // edi
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // edx
  unsigned int v45; // ecx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  int v51; // eax
  const unsigned __int16 *v52; // rdx
  const WCHAR *TagValueCopy; // rax
  WCHAR *v54; // rbx
  unsigned int v55; // esi
  int v56; // eax
  int v57; // eax
  int v58; // edx
  unsigned int v59; // ecx
  const unsigned __int16 *v60; // rax
  HLOCAL v61; // rax
  unsigned int v62; // ebx
  bool v64; // [rsp+31h] [rbp-CFh] BYREF
  HLOCAL v65; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h]
  char v67; // [rsp+48h] [rbp-B8h]
  unsigned int v68; // [rsp+4Ch] [rbp-B4h] BYREF
  PCNZWCH lpString1; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v71; // [rsp+60h] [rbp-A0h] BYREF
  char *v72; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v73; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v74; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 **v75; // [rsp+90h] [rbp-70h]
  int *v76; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v78[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *Src[2]; // [rsp+E0h] [rbp-20h]
  __m128i si128; // [rsp+F0h] [rbp-10h]
  char v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+104h] [rbp+4h]
  __int16 v83; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v84; // [rsp+110h] [rbp+10h]
  unsigned int v85; // [rsp+118h] [rbp+18h]
  struct tagVARIANT v86; // [rsp+120h] [rbp+20h] BYREF
  PCNZWCH v87; // [rsp+140h] [rbp+40h]
  unsigned __int16 *v88; // [rsp+148h] [rbp+48h]
  unsigned __int16 **v89; // [rsp+150h] [rbp+50h]
  unsigned int *v90; // [rsp+158h] [rbp+58h]
  unsigned __int16 v91[64]; // [rsp+160h] [rbp+60h] BYREF

  v67 = a4;
  v88 = a2;
  lpString1 = a1;
  v75 = a11;
  v90 = a12;
  v76 = a13;
  v89 = a14;
  v65 = 0;
  v72 = 0;
  v68 = 0;
  memset(v78, 0, sizeof(v78));
  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  psz = 0;
  hMem = 0;
  v16 = L"POST";
  if ( !a4 )
    v16 = L"GET";
  v87 = v16;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v74, 0, sizeof(v74));
  v73 = 0;
  v71 = 0;
  VariantInit(&pvarg);
  VariantInit(&v74);
  *v75 = 0;
  *a13 = 0;
  *a14 = 0;
  CSPrintErrorLineFileData(v16, 0x18801D3u, 0);
  v64 = 0;
  v18 = ndesVerifyParameters(a1, &v64);
  v19 = v18;
  if ( v18 )
  {
    v20 = v18;
    v21 = 26280403;
    v22 = a1;
LABEL_5:
    CSPrintErrorLineFileData(v22, v21, v20);
LABEL_6:
    v23 = hMem;
LABEL_7:
    v24 = v65;
    goto LABEL_119;
  }
  v25 = L"mscep/mscep.dll/pkiclient.exe";
  v26 = 0;
  v27 = L"default";
  v28 = 1;
  if ( a3 <= 2 )
  {
    if ( a3 == 2 )
    {
      v32 = StringCchPrintfW(v91, 0x39u, L"?operation=NDESGenerateChallenge&keyUsage=0x%02x&Params=", 0);
      v19 = v32;
      if ( v32 )
      {
        v30 = 27722195;
        goto LABEL_38;
      }
      v27 = v91;
    }
    else
    {
      v27 = 0;
      if ( a3 == 1 )
        v26 = L"NDESGetCACertThumbprint";
    }
    v25 = L"mscep_admin";
    v31 = 1;
    goto LABEL_44;
  }
  switch ( a3 )
  {
    case 3u:
      v26 = L"GetCACert";
      break;
    case 4u:
      v26 = L"PKIOperation";
      goto LABEL_21;
    case 5u:
      v26 = L"GetCACaps";
      break;
    case 6u:
      v26 = L"GetCACertChain";
      break;
    case 7u:
LABEL_21:
      if ( v64 )
      {
        v19 = -2147024809;
        v20 = -2147024809;
        v21 = 31064531;
        v22 = lpString1;
        goto LABEL_5;
      }
      if ( !a7 || !a8 )
      {
        v19 = -2147467261;
        v29 = -2147467261;
        v30 = 31392211;
        goto LABEL_39;
      }
      if ( v67 )
      {
        v32 = myRegValueToVariant((unsigned int)L"mscep/mscep.dll/pkiclient.exe", a8, a7, &pvarg);
        v19 = v32;
        if ( v32 )
        {
          v30 = 32178643;
LABEL_38:
          v29 = v32;
          goto LABEL_39;
        }
        v27 = 0;
        v25 = L"mscep/mscep.dll/pkiclient.exe";
        v31 = 0;
      }
      else
      {
        v32 = myCryptBinaryToString(a7, a8, 0x48000001u, (unsigned __int16 **)&v71);
        v19 = v32;
        if ( v32 )
        {
          v30 = 33030611;
          goto LABEL_38;
        }
        v27 = (const unsigned __int16 *)v71;
        v25 = L"mscep/mscep.dll/pkiclient.exe";
        v31 = 0;
      }
LABEL_44:
      if ( a3 == 4 || a3 == 7 )
        goto LABEL_49;
      goto LABEL_46;
    default:
      v29 = -2147024809;
      v19 = -2147024809;
      v30 = 33554899;
LABEL_39:
      CSPrintErrorLineFile(v30, v29);
      goto LABEL_6;
  }
  if ( v64 )
    v27 = 0;
  v31 = 0;
LABEL_46:
  if ( v71 || pvarg.vt )
  {
    v29 = -2147024809;
    v19 = -2147024809;
    v30 = 34144723;
    goto LABEL_39;
  }
LABEL_49:
  v32 = ndesBuildUrl(lpString1, v25, v26, v27, (unsigned __int16 **)&v73);
  v19 = v32;
  if ( v32 )
  {
    v30 = 34800083;
    goto LABEL_38;
  }
  CSPrintErrorLineFileData((const unsigned __int16 *)v73, 0x21501D3u, 0);
  v32 = CEnrollHttpClient::Open((CEnrollHttpClient *)v78, v87, (const unsigned __int16 *)v73, v33);
  v19 = v32;
  if ( v32 )
  {
    v30 = 35193299;
    goto LABEL_38;
  }
  v34 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 0);
  v19 = v34;
  if ( v34 )
  {
    CSPrintErrorLineFile(0xF101D7u, v34);
    v29 = v19;
    v30 = 35652051;
    goto LABEL_39;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v31 )
  {
    v35 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 0);
    v19 = v35;
    if ( v35 )
    {
      v36 = v35;
      v37 = 17105367;
LABEL_60:
      CSPrintErrorLineFile(v37, v36);
      v29 = v19;
      v30 = 36569555;
      goto LABEL_39;
    }
    if ( !*(_QWORD *)&v78[0] )
    {
      v19 = -2147221497;
      v36 = -2147221497;
      v37 = 17433047;
      goto LABEL_60;
    }
    v81 = 1;
  }
  v38 = L"Content-Type:application/json";
  if ( a3 != 7 )
    v38 = L"Content-Type:application/x-pki-message";
  v32 = ndesPutRequestHeaders((struct CEnrollHttpClient *)v78, v38);
  v19 = v32;
  if ( v32 )
  {
    v30 = 37093843;
    goto LABEL_38;
  }
  v32 = ndesPutRequestHeaders((struct CEnrollHttpClient *)v78, v88);
  v19 = v32;
  if ( v32 )
  {
    v30 = 37290451;
    goto LABEL_38;
  }
  v86 = pvarg;
  v32 = CEnrollHttpClient::Send((CEnrollHttpClient *)v78, &v86);
  v19 = v32;
  if ( v32 )
  {
    v30 = 37487059;
    goto LABEL_38;
  }
  v39 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 1);
  v19 = v39;
  if ( v39 )
  {
    CSPrintErrorLineFile(0x12101D7u, v39);
    v29 = v19;
    v30 = 37683667;
    goto LABEL_39;
  }
  fixed = v82;
  if ( v82 != 200 )
  {
    fixed = ndesFixHResult(v82);
    *v76 = fixed;
    ndesTraceErrorMessageText(fixed);
  }
  CSPrintErrorLineFileData(v27, 0x24701D3u, fixed);
  hMem = 0;
  lpString1 = 0;
  v41 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 1);
  v19 = v41;
  if ( v41 )
  {
    CSPrintErrorLineFile(0x13401D7u, v41);
LABEL_78:
    v29 = v19;
    v30 = 38404563;
    goto LABEL_39;
  }
  v42 = myDupString(Src[1], (unsigned __int16 **)&lpString1);
  v19 = v42;
  if ( v42 < 0 )
  {
    CSPrintErrorLineFile(0x13701D7u, v42);
    hMem = (HLOCAL)lpString1;
    goto LABEL_78;
  }
  hMem = (HLOCAL)lpString1;
  CSPrintErrorLineFileData(lpString1, 0x24C01D3u, fixed);
  lpString1 = 0;
  v43 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 1);
  v19 = v43;
  if ( v43 )
  {
    v44 = v43;
    v45 = 21561815;
LABEL_83:
    CSPrintErrorLineFile(v45, v44);
LABEL_86:
    v29 = v19;
    v30 = 38732243;
    goto LABEL_39;
  }
  if ( !Src[0] )
  {
    v19 = -2146877436;
    v44 = -2146877436;
    v45 = 21889495;
    goto LABEL_83;
  }
  v46 = myDupString(Src[0], (unsigned __int16 **)&lpString1);
  v19 = v46;
  if ( v46 < 0 )
  {
    CSPrintErrorLineFile(0x15101D7u, v46);
    v17 = (WCHAR *)lpString1;
    goto LABEL_86;
  }
  v17 = (WCHAR *)lpString1;
  CSPrintErrorLineFileData(lpString1, 0x25101D3u, fixed);
  VariantInit(&v74);
  v47 = CEnrollHttpClient::p_VerifyState((CEnrollHttpClient *)v78, 1);
  v19 = v47;
  if ( v47 )
  {
    v50 = 23265751;
LABEL_93:
    CSPrintErrorLineFile(v50, v47);
    v29 = v19;
    v30 = 39059923;
    goto LABEL_39;
  }
  if ( v84 )
  {
    v48 = v85;
    if ( v85 )
    {
      v47 = myRegValueToVariant(v49, v85, v84, &v74);
      v19 = v47;
      if ( v47 )
      {
        v50 = 23855575;
        goto LABEL_93;
      }
    }
  }
  if ( v74.vt == 8209 )
  {
    LODWORD(v65) = 0;
    v51 = myVariantToRegValueEx(&v74, v48, (unsigned int *)&v65, &v68, (unsigned __int8 **)&v72);
    v19 = v51;
    if ( v51 )
    {
      CSPrintErrorLineFile(0x25B01D3u, v51);
      v24 = v72;
      v23 = hMem;
      goto LABEL_119;
    }
    TagValueCopy = ndesGetTagValueCopy(v17, v52);
    v54 = (WCHAR *)TagValueCopy;
    if ( !TagValueCopy
      || (unsigned int)mylstrcmpNLSub(TagValueCopy, L"application/json; charset=utf-8", -1, 1)
      && (unsigned int)mylstrcmpNLSub(v54, L"application/json", -1, 1) )
    {
      v28 = 0;
    }
    LocalFree(v54);
    v65 = v72;
    v55 = v68;
    if ( v28 && !myConvertMultiByteToWsz(&psz, 0xFDE9u, v72, v68) )
    {
      v56 = myHLastError();
      CSPrintErrorLineFile(0x26201D3u, v56);
    }
    CSPrintErrorLineFileData(v26, 0x26501D3u, 0);
  }
  else
  {
    if ( fixed == 200 )
    {
      CSPrintErrorLineFile(0x26B01D3u, v74.vt);
      if ( v74.vt || a5 )
      {
        v19 = -2147024292;
        v29 = -2147024292;
        v30 = 40829395;
        goto LABEL_39;
      }
    }
    v55 = v68;
  }
  v23 = hMem;
  *(_QWORD *)&v86.vt = hMem;
  v86.llVal = (LONGLONG)psz;
  v86.pRecInfo = (IRecordInfo *)v17;
  v57 = myCombineStringArray(3u, (const unsigned __int16 **)&v86, &psz);
  v19 = v57;
  if ( v57 )
  {
    v58 = v57;
    v59 = 41550291;
LABEL_112:
    CSPrintErrorLineFile(v59, v58);
    goto LABEL_7;
  }
  v60 = SysAllocString(psz);
  *v89 = (unsigned __int16 *)v60;
  if ( !v60 )
  {
    v19 = -2147024882;
    v58 = -2147024882;
    v59 = 41943507;
    goto LABEL_112;
  }
  CSPrintErrorLineFileData(v60, 0x28201D3u, 0);
  *v90 = v55;
  v61 = v65;
  *v75 = (unsigned __int8 *)v65;
  v24 = 0;
  if ( v61 )
  {
    v19 = 0;
  }
  else
  {
    v19 = *v76;
    if ( *v76 )
      CSPrintErrorLineFile(0x28901D3u, v19);
  }
LABEL_119:
  v62 = ndesFixHResult(v19);
  LocalFree(psz);
  LocalFree(v23);
  LocalFree(v17);
  VariantClear(&v74);
  VariantClear(&pvarg);
  LocalFree(v24);
  LocalFree(v73);
  LocalFree(v71);
  CEnrollHttpClient::p_Cleanup((CEnrollHttpClient *)v78);
  return v62;
}

```

## disassembly

```asm
0x180028a64  mov     [rsp-8+arg_10], rbx
0x180028a69  push    rbp
0x180028a6a  push    rsi
0x180028a6b  push    rdi
0x180028a6c  push    r12
0x180028a6e  push    r13
0x180028a70  push    r14
0x180028a72  push    r15
0x180028a74  lea     rbp, [rsp-0F0h]
0x180028a7c  sub     rsp, 1F0h
0x180028a83  mov     rax, cs:__security_cookie
0x180028a8a  xor     rax, rsp
0x180028a8d  mov     [rbp+120h+var_40], rax
0x180028a94  mov     [rsp+220h+var_1D8], r9b
0x180028a99  mov     edi, r8d
0x180028a9c  mov     [rbp+120h+var_D8], rdx
0x180028aa0  mov     rsi, rcx
0x180028aa3  mov     [rsp+220h+lpString1], rcx
0x180028aa8  mov     r13, [rbp+120h+arg_30]
0x180028aaf  mov     rax, [rbp+120h+arg_50]
0x180028ab6  mov     [rbp+120h+var_190], rax
0x180028aba  mov     rax, [rbp+120h+arg_58]
0x180028ac1  mov     [rbp+120h+var_C8], rax
0x180028ac5  mov     r14, [rbp+120h+arg_60]
0x180028acc  mov     [rbp+120h+var_188], r14
0x180028ad0  mov     r15, [rbp+120h+arg_68]
0x180028ad7  mov     [rbp+120h+var_D0], r15
0x180028adb  xor     ecx, ecx
0x180028add  mov     [rsp+220h+var_1E8], rcx
0x180028ae2  mov     [rsp+220h+var_1B8], rcx
0x180028ae7  mov     [rsp+220h+var_1D4], ecx
0x180028aeb  xorps   xmm0, xmm0
0x180028aee  movdqa  [rbp+120h+var_160], xmm0
0x180028af3  xorps   xmm1, xmm1
0x180028af6  movdqa  [rbp+120h+var_150], xmm1
0x180028afb  movdqa  xmmword ptr [rbp+120h+Src], xmm0
0x180028b00  movdqa  xmm1, cs:__xmm@0000ea600000ea600000753000007530
0x180028b08  movdqa  [rbp+120h+var_130], xmm1
0x180028b0d  mov     [rbp+120h+var_120], cl
0x180028b10  mov     [rbp+120h+var_11C], ecx
0x180028b13  mov     [rbp+120h+var_118], cx
0x180028b17  mov     [rbp+120h+var_110], rcx
0x180028b1b  mov     [rbp+120h+var_108], ecx
0x180028b1e  mov     [rsp+220h+psz], rcx
0x180028b23  mov     [rsp+220h+hMem], rcx
0x180028b28  lea     rax, pwszVerb; "GET"
0x180028b2f  lea     rbx, aPost; "POST"
0x180028b36  test    r9b, r9b
0x180028b39  cmovz   rbx, rax
0x180028b3d  mov     [rbp+120h+var_E0], rbx
0x180028b41  mov     r12d, ecx
0x180028b44  xor     eax, eax
0x180028b46  movups  xmmword ptr [rbp+120h+pvarg], xmm0
0x180028b4a  mov     qword ptr [rbp+120h+pvarg+10h], rax
0x180028b4e  xorps   xmm1, xmm1
0x180028b51  movups  xmmword ptr [rsp+220h+var_1A8], xmm1
0x180028b56  mov     qword ptr [rbp+120h+var_1A8+10h], rax
0x180028b5a  mov     [rsp+220h+var_1B0], rcx
0x180028b5f  mov     [rsp+220h+var_1C0], rcx
0x180028b64  lea     rcx, [rbp+120h+pvarg]; pvarg
0x180028b68  call    cs:__imp_VariantInit
0x180028b6e  lea     rcx, [rsp+220h+var_1A8]; pvarg
0x180028b73  call    cs:__imp_VariantInit
0x180028b79  mov     rax, [rbp+120h+var_190]
0x180028b7d  xor     ecx, ecx
0x180028b7f  mov     [rax], rcx
0x180028b82  mov     [r14], ecx
0x180028b85  mov     [r15], rcx
0x180028b88  xor     r8d, r8d
0x180028b8b  mov     edx, 18801D3h
0x180028b90  mov     rcx, rbx
0x180028b93  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180028b99  mov     [rsp+220h+var_1EF], r12b
0x180028b9e  lea     rdx, [rsp+220h+var_1EF]; bool *
0x180028ba3  mov     rcx, rsi; unsigned __int16 *
0x180028ba6  call    ?ndesVerifyParameters@@YAJPEBGPEA_N@Z; ndesVerifyParameters(ushort const *,bool *)
0x180028bab  mov     ebx, eax
0x180028bad  test    eax, eax
0x180028baf  jz      short loc_180028BD1
0x180028bb1  mov     r8d, eax
0x180028bb4  mov     edx, 19101D3h
0x180028bb9  mov     rcx, rsi
0x180028bbc  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180028bc2  mov     rdi, [rsp+220h+hMem]
0x180028bc7  mov     rsi, [rsp+220h+var_1E8]
0x180028bcc  jmp     loc_18002927A
0x180028bd1  lea     rcx, aMscepMscepDllP; "mscep/mscep.dll/pkiclient.exe"
0x180028bd8  xor     r15d, r15d
0x180028bdb  lea     rsi, aDefault; "default"
0x180028be2  mov     eax, edi
0x180028be4  lea     r14d, [r15+1]
0x180028be8  test    edi, edi
0x180028bea  jz      loc_180028D10
0x180028bf0  sub     eax, r14d
0x180028bf3  jz      loc_180028D10
0x180028bf9  sub     eax, r14d
0x180028bfc  jz      loc_180028D10
0x180028c02  sub     eax, r14d
0x180028c05  jz      loc_180028CFF
0x180028c0b  sub     eax, r14d
0x180028c0e  jz      short loc_180028C55
0x180028c10  sub     eax, r14d
0x180028c13  jz      short loc_180028C4C
0x180028c15  sub     eax, r14d
0x180028c18  jz      short loc_180028C30
0x180028c1a  cmp     eax, r14d
0x180028c1d  jz      short loc_180028C5C
0x180028c1f  mov     edx, 80070057h
0x180028c24  mov     ebx, edx
0x180028c26  mov     ecx, 20001D3h
0x180028c2b  jmp     loc_180028D38
0x180028c30  lea     r15, aGetcacertchain; "GetCACertChain"
0x180028c37  cmp     [rsp+220h+var_1EF], r12b
0x180028c3c  jz      loc_180028D0B
0x180028c42  xor     esi, esi
0x180028c44  mov     r13b, sil
0x180028c47  jmp     loc_180028D6B
0x180028c4c  lea     r15, aGetcacaps; "GetCACaps"
0x180028c53  jmp     short loc_180028C37
0x180028c55  lea     r15, aPkioperation; "PKIOperation"
0x180028c5c  cmp     [rsp+220h+var_1EF], r12b
0x180028c61  jz      short loc_180028C7C
0x180028c63  mov     edx, 80070057h
0x180028c68  mov     ebx, edx
0x180028c6a  mov     r8d, edx
0x180028c6d  mov     edx, 1DA01D3h
0x180028c72  mov     rcx, [rsp+220h+lpString1]
0x180028c77  jmp     loc_180028BBC
0x180028c7c  test    r13, r13
0x180028c7f  jz      short loc_180028CF1
0x180028c81  mov     edx, [rbp+120h+arg_38]; unsigned int
0x180028c87  test    edx, edx
0x180028c89  jz      short loc_180028CF1
0x180028c8b  cmp     [rsp+220h+var_1D8], r12b
0x180028c90  jz      short loc_180028CBF
0x180028c92  lea     r9, [rbp+120h+pvarg]; struct tagVARIANT *
0x180028c96  mov     r8, r13; unsigned __int8 *
0x180028c99  call    ?myRegValueToVariant@@YAJKKPEBEPEAUtagVARIANT@@@Z; myRegValueToVariant(ulong,ulong,uchar const *,tagVARIANT *)
0x180028c9e  mov     ebx, eax
0x180028ca0  test    eax, eax
0x180028ca2  jz      short loc_180028CAE
0x180028ca4  mov     ecx, 1EB01D3h
0x180028ca9  jmp     loc_180028D36
0x180028cae  xor     esi, esi
0x180028cb0  lea     rcx, aMscepMscepDllP; "mscep/mscep.dll/pkiclient.exe"
0x180028cb7  mov     r13b, sil
0x180028cba  jmp     loc_180028D61
0x180028cbf  lea     r9, [rsp+220h+var_1C0]
0x180028cc4  mov     r8d, 48000001h
0x180028cca  mov     rcx, r13
0x180028ccd  call    cs:__imp_?myCryptBinaryToString@@YAJPEBEKKPEAPEAG@Z; myCryptBinaryToString(uchar const *,ulong,ulong,ushort * *)
0x180028cd3  mov     ebx, eax
0x180028cd5  test    eax, eax
0x180028cd7  jz      short loc_180028CE0
0x180028cd9  mov     ecx, 1F801D3h
0x180028cde  jmp     short loc_180028D36
0x180028ce0  mov     rsi, [rsp+220h+var_1C0]
0x180028ce5  lea     rcx, aMscepMscepDllP; "mscep/mscep.dll/pkiclient.exe"
0x180028cec  mov     r13b, r12b
0x180028cef  jmp     short loc_180028D61
0x180028cf1  mov     ebx, 80004003h
0x180028cf6  mov     edx, ebx
0x180028cf8  mov     ecx, 1DF01D3h
0x180028cfd  jmp     short loc_180028D38
0x180028cff  lea     r15, aGetcacert; "GetCACert"
0x180028d06  jmp     loc_180028C37
0x180028d0b  mov     r13b, r12b
0x180028d0e  jmp     short loc_180028D6B
0x180028d10  cmp     edi, 2
0x180028d13  jnz     short loc_180028D49
0x180028d15  xor     r9d, r9d
0x180028d18  lea     r8, aOperationNdesg; "?operation=NDESGenerateChallenge&keyUsa"...
0x180028d1f  lea     edx, [rdi+37h]; unsigned __int64
0x180028d22  lea     rcx, [rbp+120h+var_C0]; unsigned __int16 *
0x180028d26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028d2b  mov     ebx, eax
0x180028d2d  test    eax, eax
0x180028d2f  jz      short loc_180028D43
0x180028d31  mov     ecx, 1A701D3h
0x180028d36  mov     edx, eax
0x180028d38  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180028d3e  jmp     loc_180028BC2
0x180028d43  lea     rsi, [rbp+120h+var_C0]
0x180028d47  jmp     short loc_180028D57
0x180028d49  xor     esi, esi
0x180028d4b  cmp     edi, r14d
0x180028d4e  jnz     short loc_180028D57
0x180028d50  lea     r15, aNdesgetcacertt; "NDESGetCACertThumbprint"
0x180028d57  lea     rcx, aMscepAdmin; "mscep_admin"
0x180028d5e  mov     r13b, r14b
0x180028d61  cmp     edi, 4
0x180028d64  jz      short loc_180028D88
0x180028d66  cmp     edi, 7
0x180028d69  jz      short loc_180028D88
0x180028d6b  cmp     [rsp+220h+var_1C0], r12
0x180028d70  jnz     short loc_180028D7A
0x180028d72  xor     eax, eax
0x180028d74  cmp     ax, word ptr [rbp+120h+pvarg]
0x180028d78  jz      short loc_180028D88
0x180028d7a  mov     edx, 80070057h
0x180028d7f  mov     ebx, edx
0x180028d81  mov     ecx, 20901D3h
0x180028d86  jmp     short loc_180028D38
0x180028d88  lea     rax, [rsp+220h+var_1B0]
0x180028d8d  mov     [rsp+220h+var_200], rax; unsigned __int16 **
0x180028d92  mov     r9, rsi; unsigned __int16 *
0x180028d95  mov     r8, r15; unsigned __int16 *
0x180028d98  mov     rdx, rcx; unsigned __int16 *
0x180028d9b  mov     rcx, [rsp+220h+lpString1]; unsigned __int16 *
0x180028da0  call    ?ndesBuildUrl@@YAJPEBG000PEAPEAG@Z; ndesBuildUrl(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x180028da5  mov     ebx, eax
0x180028da7  test    eax, eax
0x180028da9  jz      short loc_180028DB2
0x180028dab  mov     ecx, 21301D3h
0x180028db0  jmp     short loc_180028D36
0x180028db2  xor     r8d, r8d
0x180028db5  mov     edx, 21501D3h
0x180028dba  mov     rcx, [rsp+220h+var_1B0]
0x180028dbf  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180028dc5  mov     r8, [rsp+220h+var_1B0]; Src
0x180028dca  mov     rdx, [rbp+120h+var_E0]; lpString1
0x180028dce  lea     rcx, [rbp+120h+var_160]; this
0x180028dd2  call    ?Open@CEnrollHttpClient@@QEAAJPEBG0UtagVARIANT@@@Z; CEnrollHttpClient::Open(ushort const *,ushort const *,tagVARIANT)
0x180028dd7  mov     ebx, eax
0x180028dd9  test    eax, eax
0x180028ddb  jz      short loc_180028DE7
0x180028ddd  mov     ecx, 21901D3h
0x180028de2  jmp     loc_180028D36
0x180028de7  xor     edx, edx; bool
0x180028de9  lea     rcx, [rbp+120h+var_160]; this
0x180028ded  call    ?p_VerifyState@CEnrollHttpClient@@AEAAJ_N@Z; CEnrollHttpClient::p_VerifyState(bool)
0x180028df2  mov     ebx, eax
0x180028df4  test    eax, eax
0x180028df6  jz      short loc_180028E11
0x180028df8  mov     edx, eax
0x180028dfa  mov     ecx, 0F101D7h
0x180028dff  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180028e05  mov     edx, ebx
0x180028e07  mov     ecx, 22001D3h
0x180028e0c  jmp     loc_180028D38
0x180028e11  movdqa  xmm0, cs:__xmm@0000ea600000ea600000753000007530
0x180028e19  movdqa  [rbp+120h+var_130], xmm0
0x180028e1e  test    r13b, r13b
0x180028e21  jz      short loc_180028E65
0x180028e23  xor     edx, edx; bool
0x180028e25  lea     rcx, [rbp+120h+var_160]; this
0x180028e29  call    ?p_VerifyState@CEnrollHttpClient@@AEAAJ_N@Z; CEnrollHttpClient::p_VerifyState(bool)
0x180028e2e  mov     ebx, eax
0x180028e30  test    eax, eax
0x180028e32  jz      short loc_180028E3D
0x180028e34  mov     edx, eax
0x180028e36  mov     ecx, 10501D7h
0x180028e3b  jmp     short loc_180028E4F
0x180028e3d  cmp     qword ptr [rbp+120h+var_160], r12
0x180028e41  jnz     short loc_180028E61
0x180028e43  mov     ebx, 80040007h
0x180028e48  mov     edx, ebx
0x180028e4a  mov     ecx, 10A01D7h
0x180028e4f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180028e55  mov     edx, ebx
0x180028e57  mov     ecx, 22E01D3h
0x180028e5c  jmp     loc_180028D38
0x180028e61  mov     [rbp+120h+var_120], r14b
0x180028e65  lea     rax, aContentTypeApp_0; "Content-Type:application/x-pki-message"
0x180028e6c  lea     rdx, aContentTypeApp; "Content-Type:application/json"
0x180028e73  cmp     edi, 7
0x180028e76  cmovnz  rdx, rax; Src
0x180028e7a  lea     rcx, [rbp+120h+var_160]; this
0x180028e7e  call    ?ndesPutRequestHeaders@@YAJPEAVCEnrollHttpClient@@PEBG@Z; ndesPutRequestHeaders(CEnrollHttpClient *,ushort const *)
0x180028e83  mov     ebx, eax
0x180028e85  test    eax, eax
0x180028e87  jz      short loc_180028E93
0x180028e89  mov     ecx, 23601D3h
0x180028e8e  jmp     loc_180028D36
0x180028e93  mov     rdx, [rbp+120h+var_D8]; Src
0x180028e97  lea     rcx, [rbp+120h+var_160]; this
0x180028e9b  call    ?ndesPutRequestHeaders@@YAJPEAVCEnrollHttpClient@@PEBG@Z; ndesPutRequestHeaders(CEnrollHttpClient *,ushort const *)
0x180028ea0  mov     ebx, eax
0x180028ea2  test    eax, eax
0x180028ea4  jz      short loc_180028EB0
0x180028ea6  mov     ecx, 23901D3h
0x180028eab  jmp     loc_180028D36
0x180028eb0  movups  xmm0, xmmword ptr [rbp+120h+pvarg]
0x180028eb4  movaps  xmmword ptr [rbp+120h+var_100], xmm0
0x180028eb8  movsd   xmm1, qword ptr [rbp+120h+pvarg+10h]
0x180028ebd  movsd   qword ptr [rbp+120h+var_100+10h], xmm1
0x180028ec2  lea     rdx, [rbp+120h+var_100]; struct tagVARIANT
0x180028ec6  lea     rcx, [rbp+120h+var_160]; this
0x180028eca  call    ?Send@CEnrollHttpClient@@QEAAJUtagVARIANT@@@Z; CEnrollHttpClient::Send(tagVARIANT)
0x180028ecf  mov     ebx, eax
0x180028ed1  test    eax, eax
0x180028ed3  jz      short loc_180028EDF
0x180028ed5  mov     ecx, 23C01D3h
0x180028eda  jmp     loc_180028D36
0x180028edf  mov     dl, r14b; bool
0x180028ee2  lea     rcx, [rbp+120h+var_160]; this
0x180028ee6  call    ?p_VerifyState@CEnrollHttpClient@@AEAAJ_N@Z; CEnrollHttpClient::p_VerifyState(bool)
0x180028eeb  mov     ebx, eax
0x180028eed  test    eax, eax
0x180028eef  jz      short loc_180028F0A
  ... truncated ...
```
