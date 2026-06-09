# CertEnrollHttp::CEnrollmentWebProxy::Request(ushort const *,IClientCred *,ulong,ushort const *,ushort const *,ushort * *,long *,short *,ushort const *,_CERTTRANSBLOB const *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)

- ea: `0x18001506c`
- end: `0x1800156dd`
- name: `?Request@CEnrollmentWebProxy@CertEnrollHttp@@SAJPEBGPEAUIClientCred@@K00PEAPEAGPEAJPEAF0PEBU_CERTTRANSBLOB@@PEAU4@66@Z`
- size: `1649`
- prototype: `__int64 __fastcall(CertEnrollHttp *, struct IClientCred *, unsigned int, const unsigned __int16 *, CertEnrollHttp *, unsigned __int16 **value, int *, __int16 *, unsigned __int16 *Src, const struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011700`

## callees

- `0x180002306`
- `0x180013de8`
- `0x180014474`
- `0x180014488`
- `0x1800149f8`
- `0x180014ae8`
- `0x180014e68`
- `0x18001506c`
- `0x1800156e4`
- `0x1800158ac`
- `0x180015930`
- `0x180020a6c`
- `0x180021438`
- `0x18002993c`
- `0x1800396f2`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180015435`
- `msvcrt!_wcsnicmp` at `0x180015435`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156b9`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800152be`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800152be`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001544a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800154ee`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001544a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800154ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001546e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001546e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156b0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001538a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800154a7`
- `OLEAUT32!__imp_SysStringLen` at `0x18001538a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800154a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800154b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001560b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800154b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001560b`
- `webservices!WsCreateError` at `0x180015118`
- `webservices!WsCreateError` at `0x180015118`
- `webservices!WsCreateHeap` at `0x180015154`
- `webservices!WsCreateHeap` at `0x180015154`
- `webservices!WsGetFaultErrorDetail` at `0x1800153ec`
- `webservices!WsGetFaultErrorDetail` at `0x1800153ec`
- `webservices!WsFreeHeap` at `0x180015698`
- `webservices!WsFreeHeap` at `0x180015698`
- `webservices!WsFreeError` at `0x1800156a8`
- `webservices!WsFreeError` at `0x1800156a8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800151dd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015272`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001534a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001537c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800153fd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015464`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015683`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800151dd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015272`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001534a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001537c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800153fd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015464`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015683`

## pseudocode

```c
__int64 __fastcall CertEnrollHttp::CEnrollmentWebProxy::Request(
        CertEnrollHttp *a1,
        struct IClientCred *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        CertEnrollHttp *a5,
        unsigned __int16 **value,
        int *a7,
        __int16 *a8,
        unsigned __int16 *Src,
        const struct _CERTTRANSBLOB *a10,
        struct _CERTTRANSBLOB *a11,
        struct _CERTTRANSBLOB *a12,
        struct _CERTTRANSBLOB *a13)
{
  struct _CERTTRANSBLOB *v15; // rsi
  unsigned __int16 **v16; // r14
  int *v17; // r15
  HRESULT v18; // eax
  int v19; // edi
  int v20; // edx
  unsigned int v21; // ecx
  HRESULT v22; // eax
  struct _WS_STRING *v23; // r9
  int v24; // eax
  int v25; // eax
  struct AdditionalContextType **v26; // r9
  BSTR v27; // rbx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ecx
  struct IClientCred *v31; // r9
  __int64 v32; // rax
  int v33; // eax
  int WSErrorString; // eax
  unsigned __int16 *v35; // rbx
  unsigned int v36; // edx
  CertSrv::CEventLog *v37; // rcx
  unsigned int v38; // r8d
  unsigned __int16 v39; // r9
  HRESULT FaultErrorDetail; // eax
  unsigned __int16 **v41; // rax
  unsigned __int16 *v42; // rcx
  BSTR v43; // rax
  unsigned int v44; // ecx
  unsigned __int16 *v45; // rax
  UINT v46; // eax
  BYTE *v47; // rax
  unsigned __int16 *v48; // rbx
  UINT v49; // edx
  BSTR v50; // rax
  __int64 v51; // rax
  CertEnrollHttp *v52; // rcx
  struct _CERTTRANSBLOB *v53; // r8
  CertEnrollHttp *v54; // rcx
  int v55; // eax
  int v56; // eax
  __int64 v57; // rcx
  CertEnrollHttp *v58; // rcx
  int v59; // eax
  __int64 v60; // rax
  unsigned int v61; // edi
  unsigned __int16 *v62; // rax
  int v63; // eax
  WS_HEAP **heap; // [rsp+28h] [rbp-C9h]
  unsigned int valueSize; // [rsp+30h] [rbp-C1h]
  unsigned __int8 *v67; // [rsp+38h] [rbp-B9h]
  struct RequestSecurityTokenResponseType **v68; // [rsp+48h] [rbp-A9h]
  struct _CERTTRANSBLOB *v69; // [rsp+50h] [rbp-A1h] BYREF
  WS_ERROR *error; // [rsp+58h] [rbp-99h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-91h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-89h] BYREF
  unsigned __int16 *v73[3]; // [rsp+70h] [rbp-81h] BYREF
  unsigned __int8 v74[16]; // [rsp+88h] [rbp-69h] BYREF
  int v75; // [rsp+98h] [rbp-59h]
  LPWSTR v76; // [rsp+A0h] [rbp-51h]
  __int128 v77; // [rsp+A8h] [rbp-49h]
  __int128 v78; // [rsp+B8h] [rbp-39h]
  _BYTE v79[8]; // [rsp+D8h] [rbp-19h] BYREF
  _BYTE v80[24]; // [rsp+E0h] [rbp-11h] BYREF
  char v82; // [rsp+130h] [rbp+3Fh]

  v82 = (char)a2;
  CertEnrollHttp::MemZero<_CERTTRANSBLOB>(a11);
  CertEnrollHttp::MemZero<_CERTTRANSBLOB>(a12);
  v15 = a13;
  CertEnrollHttp::MemZero<_CERTTRANSBLOB>(a13);
  error = 0;
  memset_0(v74, 0, 0x68u);
  v69 = 0;
  v73[0] = 0;
  v68 = 0;
  pbstr = 0;
  v16 = value;
  if ( !value || (v17 = a7) == 0 || !a8 )
  {
    v19 = -2147467261;
    v21 = 23595961;
    goto LABEL_90;
  }
  v18 = WsCreateError(0, 0, &error);
  v19 = v18;
  if ( v18 )
  {
    v20 = v18;
    v21 = 24185785;
LABEL_91:
    CSPrintErrorLineFile(v21, v20);
    goto LABEL_92;
  }
  v22 = WsCreateHeap(0xA00000u, 0x400u, 0, 0, (WS_HEAP **)&v69, error);
  v19 = v22;
  if ( v22 )
  {
    v20 = v22;
    v21 = 24513465;
    goto LABEL_91;
  }
  if ( a10 && a10->pb )
  {
    v24 = CertEnrollHttp::FillInRequestElements(
            (CertEnrollHttp *)a3,
            (unsigned int)a10,
            v69,
            (struct _WS_HEAP *)v74,
            (struct RequestSecurityTokenType *)heap);
    v19 = v24;
    if ( v24 )
    {
      v20 = v24;
      v21 = 26151865;
      goto LABEL_91;
    }
    v78 = *(_OWORD *)&qword_180042558;
  }
  else
  {
    if ( !a5 || !*(_WORD *)a5 )
    {
      v20 = -2147024809;
      v19 = -2147024809;
      v21 = 24972217;
      goto LABEL_91;
    }
    if ( a4 )
    {
      v20 = -2147024809;
      v19 = -2147024809;
      v21 = 25299897;
      goto LABEL_91;
    }
    v78 = *(_OWORD *)&qword_180042568;
    v28 = CertEnrollHttp::StringToWsString(a5, (const unsigned __int16 *)v69, (struct _WS_HEAP *)v80, v23);
    v19 = v28;
    if ( v28 )
    {
      v20 = v28;
      v21 = 25758649;
      goto LABEL_91;
    }
  }
  v77 = *(_OWORD *)&qword_180042538;
  if ( Src )
  {
    v25 = myDupString(Src, &pbstr);
    v19 = v25;
    if ( v25 )
    {
      CSPrintErrorLineFile(0x1990BB9u, v25);
      v27 = pbstr;
      goto LABEL_93;
    }
    v27 = pbstr;
    v68 = (struct RequestSecurityTokenResponseType **)pbstr;
    v29 = CertEnrollHttp::ParseAttributes((CertEnrollHttp *)pbstr, (unsigned __int16 *)v69, (struct _WS_HEAP *)v79, v26);
    v19 = v29;
    if ( v29 )
    {
      v30 = 27003833;
LABEL_24:
      CSPrintErrorLineFile(v30, v29);
      goto LABEL_93;
    }
  }
  else
  {
    v27 = 0;
  }
  lpName = 0;
  v29 = CertEnrollHttp::WsAllocT<unsigned short>(v69, &lpName, 85);
  v19 = v29;
  if ( v29 )
  {
    v30 = 27331513;
    goto LABEL_24;
  }
  if ( !LCIDToLocaleName(0x400u, lpName, 85, 0) )
  {
    v29 = myHLastError();
    v19 = v29;
    v30 = 27659193;
    goto LABEL_24;
  }
  v76 = lpName;
  v32 = -1;
  do
    ++v32;
  while ( lpName[v32] );
  v75 = v32;
  LOBYTE(v31) = (a3 & 0x100000) != 0;
  v33 = CertEnrollHttp::RequestSecurityToken(
          a1,
          0,
          v82,
          v31,
          (WS_HEAP *)v69,
          error,
          (struct _WS_ERROR *)v74,
          (struct RequestSecurityTokenType *)v73,
          v68);
  v19 = v33;
  LODWORD(value) = v33;
  if ( v33 < 0 )
  {
    CSPrintErrorLineFile(0x1B60BB9u, v33);
    *v17 = 1;
    pbstr = 0;
    WSErrorString = GetWSErrorString((int *)&value, error, &pbstr);
    if ( WSErrorString )
      CSPrintErrorLineFile(0x1BC0BB9u, WSErrorString);
    v35 = pbstr;
    if ( SysStringLen(pbstr) )
    {
      v73[0] = (unsigned __int16 *)a1;
      v73[1] = v35;
      CertSrv::CEventLog::LogEvent(v37, v36, v38, v39, (const unsigned __int16 *const *)v73, valueSize, v67);
    }
    v19 = (int)value;
    if ( (_DWORD)value != -2143485933 )
      goto LABEL_48;
    *v16 = 0;
    value = 0;
    FaultErrorDetail = WsGetFaultErrorDetail(
                         error,
                         &faultDetailDescription,
                         WS_READ_OPTIONAL_POINTER,
                         (WS_HEAP *)v69,
                         &value,
                         8u);
    if ( FaultErrorDetail )
    {
      CSPrintErrorLineFile(0x1D60BB9u, FaultErrorDetail);
    }
    else
    {
      v41 = value;
      if ( value )
      {
        v42 = value[2];
        if ( v42 )
          v19 = *(_DWORD *)v42;
        if ( *((_DWORD *)value + 8) )
        {
          if ( _wcsnicmp(L"-1", value[5], *((unsigned int *)value + 8)) )
          {
            v43 = SysAllocStringLen(value[5], *((_DWORD *)value + 8));
            *v16 = v43;
            if ( !v43 )
            {
              v44 = 31984569;
              goto LABEL_47;
            }
            if ( v19 >= 0 )
              v19 = 2;
            *v17 = v19;
            v19 = 0;
          }
          v41 = value;
        }
        v45 = v41[3];
        if ( v45 )
          *a8 = -(*(_DWORD *)v45 != 0);
      }
    }
    v46 = 2 * SysStringLen(v35) + 2;
    v15->cb = v46;
    v47 = (BYTE *)CoTaskMemAlloc(v46);
    v15->pb = v47;
    if ( v47 )
    {
      memcpy_0(v47, v35, v15->cb);
      goto LABEL_48;
    }
    v44 = 33491897;
LABEL_47:
    v19 = -2147024882;
    CSPrintErrorLineFile(v44, -2147024882);
LABEL_48:
    SysFreeString(v35);
    goto LABEL_92;
  }
  v48 = v73[0];
  v49 = *((_DWORD *)v73[0] + 14);
  if ( v49 )
  {
    v50 = SysAllocStringLen(*((const OLECHAR **)v73[0] + 8), v49);
    *v16 = v50;
    if ( !v50 )
    {
      v20 = -2147024882;
      v19 = -2147024882;
      v21 = 34474937;
      goto LABEL_91;
    }
  }
  else
  {
    *v16 = 0;
  }
  v51 = *((_QWORD *)v48 + 6);
  if ( !v51 )
  {
    v20 = -2147024883;
    v19 = -2147024883;
    v21 = 35195833;
    goto LABEL_91;
  }
  if ( *(_DWORD *)v51 == 1 )
  {
    v52 = *(CertEnrollHttp **)(v51 + 8);
    if ( !v52 )
    {
      v20 = -2147024883;
      v19 = -2147024883;
      v21 = 35851193;
      goto LABEL_91;
    }
    v19 = CertEnrollHttp::CopyResponse(v52, (struct BinarySecurityTokenType *)a12, 0);
    if ( v19 )
    {
      v21 = 36113337;
LABEL_90:
      v20 = v19;
      goto LABEL_91;
    }
    v54 = (CertEnrollHttp *)*((_QWORD *)v48 + 5);
    if ( v54 )
    {
      v55 = CertEnrollHttp::CopyResponse(v54, (struct BinarySecurityTokenType *)a11, v53);
      v19 = v55;
      if ( v55 )
      {
        v20 = v55;
        v21 = 36441017;
        goto LABEL_91;
      }
    }
    v56 = 3;
  }
  else
  {
    if ( *(_DWORD *)v51 != 2 )
    {
      v20 = -2147024883;
      v19 = -2147024883;
      v21 = 38276025;
      goto LABEL_91;
    }
    v57 = *(_QWORD *)(v51 + 8);
    if ( !v57 || !*(_DWORD *)(v57 + 48) )
    {
      v20 = -2147024883;
      v19 = -2147024883;
      v21 = 37292985;
      goto LABEL_91;
    }
    v58 = (CertEnrollHttp *)*((_QWORD *)v48 + 5);
    if ( v58 )
    {
      v59 = CertEnrollHttp::CopyResponse(v58, (struct BinarySecurityTokenType *)a11, 0);
      v19 = v59;
      if ( v59 )
      {
        v20 = v59;
        v21 = 37686201;
        goto LABEL_91;
      }
    }
    v56 = 5;
  }
  *v17 = v56;
  if ( !v15 )
    goto LABEL_92;
  v60 = *((_QWORD *)v48 + 4);
  if ( !v60 )
    goto LABEL_92;
  v61 = *(_DWORD *)(v60 + 16) + 1;
  v15->cb = 2 * v61;
  v62 = (unsigned __int16 *)CoTaskMemAlloc(2 * v61);
  v15->pb = (BYTE *)v62;
  if ( !v62 )
  {
    v20 = -2147024882;
    v19 = -2147024882;
    v21 = 39062457;
    goto LABEL_91;
  }
  v63 = StringCchCopyNW(
          v62,
          v61,
          *(const unsigned __int16 **)(*((_QWORD *)v48 + 4) + 24LL),
          *(unsigned int *)(*((_QWORD *)v48 + 4) + 16LL));
  v19 = v63;
  if ( v63 )
  {
    v20 = v63;
    v21 = 39455673;
    goto LABEL_91;
  }
LABEL_92:
  v27 = (BSTR)v68;
LABEL_93:
  if ( v69 )
    WsFreeHeap((WS_HEAP *)v69);
  if ( error )
    WsFreeError(error);
  SysFreeString(0);
  LocalFree(v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18001506c  mov     rax, rsp
0x18001506f  mov     [rax+18h], rbx
0x180015073  mov     [rax+20h], rsi
0x180015077  mov     [rax+10h], rdx
0x18001507b  mov     [rax+8], rcx
0x18001507f  push    rbp
0x180015080  push    rdi
0x180015081  push    r12
0x180015083  push    r14
0x180015085  push    r15
0x180015087  lea     rbp, [rax-2Fh]
0x18001508b  sub     rsp, 0F0h
0x180015092  mov     rbx, r9
0x180015095  mov     r12d, r8d
0x180015098  mov     rcx, [rbp+27h+arg_50]
0x18001509f  call    ??$MemZero@U_CERTTRANSBLOB@@@CertEnrollHttp@@YAXPEAU_CERTTRANSBLOB@@H@Z; CertEnrollHttp::MemZero<_CERTTRANSBLOB>(_CERTTRANSBLOB *,int)
0x1800150a4  mov     rcx, [rbp+27h+arg_58]
0x1800150ab  call    ??$MemZero@U_CERTTRANSBLOB@@@CertEnrollHttp@@YAXPEAU_CERTTRANSBLOB@@H@Z; CertEnrollHttp::MemZero<_CERTTRANSBLOB>(_CERTTRANSBLOB *,int)
0x1800150b0  mov     rsi, [rbp+27h+arg_60]
0x1800150b7  mov     rcx, rsi
0x1800150ba  call    ??$MemZero@U_CERTTRANSBLOB@@@CertEnrollHttp@@YAXPEAU_CERTTRANSBLOB@@H@Z; CertEnrollHttp::MemZero<_CERTTRANSBLOB>(_CERTTRANSBLOB *,int)
0x1800150bf  xor     edi, edi
0x1800150c1  mov     [rsp+110h+error], rdi
0x1800150c6  xor     edx, edx; Val
0x1800150c8  lea     r8d, [rdi+68h]; Size
0x1800150cc  lea     rcx, [rbp+27h+var_90]; void *
0x1800150d0  call    memset_0
0x1800150d5  mov     [rsp+110h+var_C8], rdi
0x1800150da  mov     [rsp+110h+var_A8], rdi
0x1800150df  mov     eax, edi
0x1800150e1  mov     [rsp+110h+var_D0], rax; struct RequestSecurityTokenResponseType **
0x1800150e6  mov     [rsp+110h+pbstr], rax
0x1800150eb  mov     r14, [rbp+27h+value]
0x1800150ef  test    r14, r14
0x1800150f2  jz      loc_180015677
0x1800150f8  mov     r15, [rbp+27h+arg_30]
0x1800150fc  test    r15, r15
0x1800150ff  jz      loc_180015677
0x180015105  cmp     [rbp+27h+arg_38], rdi
0x180015109  jz      loc_180015677
0x18001510f  lea     r8, [rsp+110h+error]; error
0x180015114  xor     edx, edx; propertyCount
0x180015116  xor     ecx, ecx; properties
0x180015118  call    cs:__imp_WsCreateError
0x18001511e  mov     edi, eax
0x180015120  test    eax, eax
0x180015122  jz      short loc_180015130
0x180015124  mov     edx, eax
0x180015126  mov     ecx, 1710BB9h
0x18001512b  jmp     loc_180015683
0x180015130  mov     rax, [rsp+110h+error]
0x180015135  mov     qword ptr [rsp+110h+valueSize], rax; error
0x18001513a  lea     rax, [rsp+110h+var_C8]
0x18001513f  mov     [rsp+110h+heap], rax; struct RequestSecurityTokenType *
0x180015144  xor     r9d, r9d; propertyCount
0x180015147  xor     r8d, r8d; properties
0x18001514a  mov     edx, 400h; trimSize
0x18001514f  mov     ecx, 0A00000h; maxSize
0x180015154  call    cs:__imp_WsCreateHeap
0x18001515a  mov     edi, eax
0x18001515c  xor     r8d, r8d
0x18001515f  test    eax, eax
0x180015161  jz      short loc_18001516F
0x180015163  mov     edx, eax
0x180015165  mov     ecx, 1760BB9h
0x18001516a  jmp     loc_180015683
0x18001516f  mov     rdx, [rbp+27h+arg_48]; unsigned int
0x180015173  test    rdx, rdx
0x180015176  jz      short loc_1800151ED
0x180015178  cmp     [rdx+8], r8
0x18001517c  jz      short loc_1800151ED
0x18001517e  lea     r9, [rbp+27h+var_90]; struct _WS_HEAP *
0x180015182  mov     r8, [rsp+110h+var_C8]; struct _CERTTRANSBLOB *
0x180015187  mov     ecx, r12d; this
0x18001518a  call    ?FillInRequestElements@CertEnrollHttp@@YAJKPEBU_CERTTRANSBLOB@@PEAU_WS_HEAP@@PEAURequestSecurityTokenType@@@Z; CertEnrollHttp::FillInRequestElements(ulong,_CERTTRANSBLOB const *,_WS_HEAP *,RequestSecurityTokenType *)
0x18001518f  mov     edi, eax
0x180015191  test    eax, eax
0x180015193  jz      short loc_1800151A1
0x180015195  mov     edx, eax
0x180015197  mov     ecx, 18F0BB9h
0x18001519c  jmp     loc_180015683
0x1800151a1  movups  xmm0, xmmword ptr cs:qword_180042558
0x1800151a8  movdqu  [rbp+27h+var_60], xmm0
0x1800151ad  movups  xmm0, xmmword ptr cs:qword_180042538
0x1800151b4  movdqu  [rbp+27h+var_70], xmm0
0x1800151b9  mov     rcx, [rbp+27h+Src]; Src
0x1800151bd  test    rcx, rcx
0x1800151c0  jz      loc_18001527D
0x1800151c6  lea     rdx, [rsp+110h+pbstr]; unsigned __int16 **
0x1800151cb  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x1800151d0  mov     edi, eax
0x1800151d2  test    eax, eax
0x1800151d4  jz      short loc_18001524A
0x1800151d6  mov     edx, eax
0x1800151d8  mov     ecx, 1990BB9h
0x1800151dd  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800151e3  mov     rbx, [rsp+110h+pbstr]
0x1800151e8  jmp     loc_18001568E
0x1800151ed  mov     rcx, [rbp+27h+arg_20]; this
0x1800151f1  test    rcx, rcx
0x1800151f4  jz      loc_180015669
0x1800151fa  cmp     r8w, [rcx]
0x1800151fe  jz      loc_180015669
0x180015204  test    rbx, rbx
0x180015207  jz      short loc_18001521A
0x180015209  mov     edx, 80070057h
0x18001520e  mov     edi, edx
0x180015210  mov     ecx, 1820BB9h
0x180015215  jmp     loc_180015683
0x18001521a  movups  xmm0, xmmword ptr cs:qword_180042568
0x180015221  movdqu  [rbp+27h+var_60], xmm0
0x180015226  lea     r8, [rbp+27h+var_38]; struct _WS_HEAP *
0x18001522a  mov     rdx, [rsp+110h+var_C8]; unsigned __int16 *
0x18001522f  call    ?StringToWsString@CertEnrollHttp@@YAJPEBGPEAU_WS_HEAP@@PEAU_WS_STRING@@@Z; CertEnrollHttp::StringToWsString(ushort const *,_WS_HEAP *,_WS_STRING *)
0x180015234  mov     edi, eax
0x180015236  test    eax, eax
0x180015238  jz      loc_1800151AD
0x18001523e  mov     edx, eax
0x180015240  mov     ecx, 1890BB9h
0x180015245  jmp     loc_180015683
0x18001524a  lea     r8, [rbp+27h+var_40]; struct _WS_HEAP *
0x18001524e  mov     rdx, [rsp+110h+var_C8]; unsigned __int16 *
0x180015253  mov     rbx, [rsp+110h+pbstr]
0x180015258  mov     [rsp+110h+var_D0], rbx
0x18001525d  mov     rcx, rbx; this
0x180015260  call    ?ParseAttributes@CertEnrollHttp@@YAJPEAGPEAU_WS_HEAP@@PEAPEAUAdditionalContextType@@@Z; CertEnrollHttp::ParseAttributes(ushort *,_WS_HEAP *,AdditionalContextType * *)
0x180015265  mov     edi, eax
0x180015267  test    eax, eax
0x180015269  jz      short loc_180015282
0x18001526b  mov     ecx, 19C0BB9h
0x180015270  mov     edx, eax
0x180015272  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180015278  jmp     loc_18001568E
0x18001527d  mov     rbx, [rsp+110h+var_D0]
0x180015282  mov     [rsp+110h+lpName], 0
0x18001528b  mov     r8d, 55h ; 'U'
0x180015291  lea     rdx, [rsp+110h+lpName]
0x180015296  mov     rcx, [rsp+110h+var_C8]
0x18001529b  call    ??$WsAllocT@G@CertEnrollHttp@@YAJPEAU_WS_HEAP@@PEAPEAGH@Z; CertEnrollHttp::WsAllocT<ushort>(_WS_HEAP *,ushort * *,int)
0x1800152a0  mov     edi, eax
0x1800152a2  test    eax, eax
0x1800152a4  jz      short loc_1800152AD
0x1800152a6  mov     ecx, 1A10BB9h
0x1800152ab  jmp     short loc_180015270
0x1800152ad  xor     r9d, r9d; dwFlags
0x1800152b0  lea     r8d, [r9+55h]; cchName
0x1800152b4  mov     rdx, [rsp+110h+lpName]; lpName
0x1800152b9  mov     ecx, 400h; Locale
0x1800152be  call    cs:__imp_LCIDToLocaleName
0x1800152c4  xor     edx, edx; unsigned __int16 *
0x1800152c6  test    eax, eax
0x1800152c8  jnz     short loc_1800152D8
0x1800152ca  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800152cf  mov     edi, eax
0x1800152d1  mov     ecx, 1A60BB9h
0x1800152d6  jmp     short loc_180015270
0x1800152d8  mov     rcx, [rsp+110h+lpName]
0x1800152dd  mov     [rbp+27h+var_78], rcx
0x1800152e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800152e5  inc     rax
0x1800152e8  cmp     [rcx+rax*2], dx
0x1800152ec  jnz     short loc_1800152E5
0x1800152ee  mov     [rbp+27h+var_80], eax
0x1800152f1  shr     r12d, 14h
0x1800152f5  and     r12b, 1
0x1800152f9  lea     rax, [rsp+110h+var_A8]
0x1800152fe  mov     [rsp+110h+var_D8], rax; struct RequestSecurityTokenType *
0x180015303  lea     rax, [rbp+27h+var_90]
0x180015307  mov     [rsp+110h+var_E0], rax; unsigned __int8 *
0x18001530c  mov     rax, [rsp+110h+error]
0x180015311  mov     qword ptr [rsp+110h+valueSize], rax; unsigned int
0x180015316  mov     rax, [rsp+110h+var_C8]
0x18001531b  mov     [rsp+110h+heap], rax; heap
0x180015320  mov     r9b, r12b; struct IClientCred *
0x180015323  mov     r8, qword ptr [rbp+27h+arg_8]; bool
0x180015327  mov     r12, [rbp+27h+arg_0]
0x18001532b  mov     rcx, r12; this
0x18001532e  call    ?RequestSecurityToken@CertEnrollHttp@@YAJPEBG_NPEAUIClientCred@@1PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAURequestSecurityTokenType@@PEAPEAURequestSecurityTokenResponseType@@@Z; CertEnrollHttp::RequestSecurityToken(ushort const *,bool,IClientCred *,bool,_WS_HEAP *,_WS_ERROR *,RequestSecurityTokenType *,RequestSecurityTokenResponseType * *)
0x180015333  mov     edi, eax
0x180015335  mov     dword ptr [rbp+27h+value], eax
0x180015338  xor     r8d, r8d; struct _CERTTRANSBLOB *
0x18001533b  test    eax, eax
0x18001533d  jns     loc_1800154DE
0x180015343  mov     edx, eax
0x180015345  mov     ecx, 1B60BB9h
0x18001534a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180015350  mov     dword ptr [r15], 1
0x180015357  xor     edi, edi
0x180015359  mov     [rsp+110h+pbstr], rdi
0x18001535e  lea     r8, [rsp+110h+pbstr]; unsigned __int16 **
0x180015363  mov     rdx, [rsp+110h+error]; struct _WS_ERROR *
0x180015368  lea     rcx, [rbp+27h+value]; int *
0x18001536c  call    ?GetWSErrorString@@YAJPEAJPEAU_WS_ERROR@@PEAPEAG@Z; GetWSErrorString(long *,_WS_ERROR *,ushort * *)
0x180015371  test    eax, eax
0x180015373  jz      short loc_180015382
0x180015375  mov     edx, eax
0x180015377  mov     ecx, 1BC0BB9h
0x18001537c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180015382  mov     rbx, [rsp+110h+pbstr]
0x180015387  mov     rcx, rbx; pbstr
0x18001538a  call    cs:__imp_SysStringLen
0x180015390  test    eax, eax
0x180015392  jz      short loc_1800153AC
0x180015394  mov     [rsp+110h+var_A8], r12
0x180015399  mov     [rbp+27h+var_A0], rbx
0x18001539d  lea     rax, [rsp+110h+var_A8]
0x1800153a2  mov     [rsp+110h+heap], rax; unsigned __int16 **
0x1800153a7  call    ?LogEvent@CEventLog@CertSrv@@QEAAJKKGPEBQEBGKPEAE@Z; CertSrv::CEventLog::LogEvent(ulong,ulong,ushort,ushort const * const *,ulong,uchar *)
0x1800153ac  mov     edi, dword ptr [rbp+27h+value]
0x1800153af  cmp     edi, 803D0013h
0x1800153b5  jnz     loc_18001546B
0x1800153bb  xor     r12d, r12d
0x1800153be  mov     [r14], r12
0x1800153c1  mov     [rbp+27h+value], r12
0x1800153c5  mov     [rsp+110h+valueSize], 8; valueSize
0x1800153cd  lea     rax, [rbp+27h+value]
0x1800153d1  mov     [rsp+110h+heap], rax; value
0x1800153d6  mov     r9, [rsp+110h+var_C8]; heap
0x1800153db  lea     r8d, [r12+3]; readOption
0x1800153e0  lea     rdx, faultDetailDescription; faultDetailDescription
0x1800153e7  mov     rcx, [rsp+110h+error]; error
0x1800153ec  call    cs:__imp_WsGetFaultErrorDetail
0x1800153f2  test    eax, eax
0x1800153f4  jz      short loc_180015408
0x1800153f6  mov     edx, eax
0x1800153f8  mov     ecx, 1D60BB9h
0x1800153fd  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180015403  jmp     loc_1800154A4
0x180015408  mov     rax, [rbp+27h+value]
0x18001540c  test    rax, rax
0x18001540f  jz      loc_1800154A4
0x180015415  mov     rcx, [rax+10h]
0x180015419  test    rcx, rcx
0x18001541c  jz      short loc_180015420
0x18001541e  mov     edi, [rcx]
0x180015420  cmp     [rax+20h], r12d
0x180015424  jbe     short loc_18001548D
0x180015426  mov     r8d, [rax+20h]; MaxCount
0x18001542a  mov     rdx, [rax+28h]; String2
0x18001542e  lea     rcx, a1; "-1"
0x180015435  call    cs:__imp__wcsnicmp
0x18001543b  test    eax, eax
0x18001543d  jz      short loc_180015489
0x18001543f  mov     rcx, [rbp+27h+value]
0x180015443  mov     edx, [rcx+20h]; ui
0x180015446  mov     rcx, [rcx+28h]; strIn
0x18001544a  call    cs:__imp_SysAllocStringLen
0x180015450  mov     [r14], rax
0x180015453  test    rax, rax
0x180015456  jnz     short loc_180015479
0x180015458  mov     ecx, 1E80BB9h
0x18001545d  mov     edx, 8007000Eh
0x180015462  mov     edi, edx
0x180015464  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001546a  nop
0x18001546b  mov     rcx, rbx; bstrString
0x18001546e  call    cs:__imp_SysFreeString
0x180015474  jmp     loc_180015689
0x180015479  mov     ecx, 2
0x18001547e  test    edi, edi
0x180015480  cmovns  edi, ecx
0x180015483  mov     [r15], edi
0x180015486  mov     edi, r12d
0x180015489  mov     rax, [rbp+27h+value]
0x18001548d  mov     rax, [rax+18h]
0x180015491  test    rax, rax
0x180015494  jz      short loc_1800154A4
0x180015496  mov     eax, [rax]
0x180015498  neg     eax
0x18001549a  sbb     cx, cx
0x18001549d  mov     rax, [rbp+27h+arg_38]
0x1800154a1  mov     [rax], cx
0x1800154a4  mov     rcx, rbx; pbstr
0x1800154a7  call    cs:__imp_SysStringLen
0x1800154ad  lea     eax, ds:2[rax*2]
0x1800154b4  mov     [rsi], eax
0x1800154b6  mov     ecx, eax; cb
0x1800154b8  call    cs:__imp_CoTaskMemAlloc
0x1800154be  mov     [rsi+8], rax
0x1800154c2  test    rax, rax
0x1800154c5  jnz     short loc_1800154CE
0x1800154c7  mov     ecx, 1FF0BB9h
0x1800154cc  jmp     short loc_18001545D
0x1800154ce  mov     r8d, [rsi]; Size
0x1800154d1  mov     rdx, rbx; Src
0x1800154d4  mov     rcx, rax; void *
0x1800154d7  call    memcpy_0
0x1800154dc  jmp     short loc_18001546B
0x1800154de  mov     rbx, [rsp+110h+var_A8]
0x1800154e3  mov     edx, [rbx+38h]; ui
0x1800154e6  test    edx, edx
0x1800154e8  jz      short loc_180015510
0x1800154ea  mov     rcx, [rbx+40h]; strIn
0x1800154ee  call    cs:__imp_SysAllocStringLen
0x1800154f4  mov     [r14], rax
0x1800154f7  xor     r8d, r8d
0x1800154fa  test    rax, rax
0x1800154fd  jnz     short loc_180015513
0x1800154ff  mov     edx, 8007000Eh
0x180015504  mov     edi, edx
  ... truncated ...
```
