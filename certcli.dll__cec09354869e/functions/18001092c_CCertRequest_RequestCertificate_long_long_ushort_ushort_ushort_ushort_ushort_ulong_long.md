# CCertRequest::_RequestCertificate(long,long,ushort *,ushort *,ushort *,ushort *,ushort *,ulong,long *)

- ea: `0x18001092c`
- end: `0x1800111e4`
- name: `?_RequestCertificate@CCertRequest@@AEAAJJJPEAG0000KPEAJ@Z`
- size: `2232`
- prototype: `__int64 __fastcall(unsigned __int16 **this, CCertRequest *, unsigned int, BSTR bstr, unsigned __int16 *, unsigned __int16 *Src, unsigned __int16 *, BSTR bstra, unsigned int, int *)`
- caller_count: `4`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f110`
- `0x18000f190`
- `0x18000f3f0`
- `0x18000f6b0`

## callees

- `0x18000dbfc`
- `0x18000f3b8`
- `0x18000f7e0`
- `0x18000fcb0`
- `0x18000fe00`
- `0x180010758`
- `0x18001092c`
- `0x180011700`
- `0x180011a14`
- `0x180011ba0`
- `0x18001cd98`
- `0x180020a6c`
- `0x1800213f0`
- `0x18002d8a4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001117d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001117d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011187`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010aa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010f85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010aa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180010f85`
- `crypttpmeksvc!FreeCMCResponse` at `0x1800110b8`
- `crypttpmeksvc!FreeCMCResponse` at `0x1800110b8`
- `crypttpmeksvc!IsCmcResponseForAttestation` at `0x180010ed6`
- `crypttpmeksvc!IsCmcResponseForAttestation` at `0x180010ed6`
- `crypttpmeksvc!ParseCMCResponse` at `0x180010e69`
- `crypttpmeksvc!ParseCMCResponse` at `0x180011104`
- `crypttpmeksvc!ParseCMCResponse` at `0x180010e69`
- `crypttpmeksvc!ParseCMCResponse` at `0x180011104`
- `OLEAUT32!__imp_SysFreeString` at `0x18001116c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001116c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010a5a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010bf9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010c25`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010c44`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010ddb`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010a5a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010bf9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010c25`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010c44`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180010ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111c3`
- `CRYPT32!CertCloseStore` at `0x1800110df`
- `CRYPT32!CertCloseStore` at `0x1800110df`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800109ff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010a37`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010b4c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010bb1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010cfd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011027`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001109c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011133`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800109ff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010a37`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010b4c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010bb1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010cfd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011027`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001109c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011133`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180010ce3`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180010ce3`

## pseudocode

```c
__int64 __fastcall CCertRequest::_RequestCertificate(
        unsigned __int16 **this,
        CCertRequest *a2,
        unsigned int a3,
        BSTR bstr,
        unsigned __int16 *a5,
        unsigned __int16 *Src,
        unsigned __int16 *a7,
        BSTR bstra,
        unsigned int a9,
        int *a10)
{
  BSTR v10; // r13
  unsigned int v11; // r12d
  unsigned int v12; // esi
  void *v14; // r14
  int v15; // ebx
  int v16; // eax
  const unsigned __int16 *v17; // r15
  unsigned int v18; // esi
  const unsigned __int16 *v19; // rcx
  int v20; // eax
  int v21; // eax
  int v22; // r14d
  unsigned int v23; // ecx
  int v24; // edx
  unsigned int v25; // ecx
  BSTR v26; // rbx
  unsigned int v27; // eax
  OLECHAR *v28; // rbx
  int v29; // r14d
  unsigned int *v30; // r12
  unsigned int v31; // r13d
  int v32; // edx
  CCertRequest *v33; // rcx
  int v34; // eax
  int v35; // eax
  int v36; // ebx
  unsigned __int16 *v37; // rcx
  _DWORD *v38; // r12
  _QWORD *v39; // r13
  int v40; // r8d
  int v41; // r9d
  int v42; // eax
  CCertRequest *v43; // rcx
  const unsigned __int16 *v44; // r8
  int appended; // eax
  int v46; // eax
  int v47; // eax
  unsigned __int16 *v48; // rcx
  int v49; // eax
  char v51; // [rsp+90h] [rbp-80h]
  __int16 v52[2]; // [rsp+94h] [rbp-7Ch] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-78h]
  unsigned int v54; // [rsp+A0h] [rbp-70h]
  unsigned int v55; // [rsp+A4h] [rbp-6Ch] BYREF
  unsigned int v56; // [rsp+A8h] [rbp-68h] BYREF
  unsigned int v57; // [rsp+ACh] [rbp-64h] BYREF
  unsigned __int16 *v58; // [rsp+B0h] [rbp-60h] BYREF
  BSTR v59; // [rsp+B8h] [rbp-58h] BYREF
  BSTR v60; // [rsp+C0h] [rbp-50h] BYREF
  DWORD TickCount; // [rsp+C8h] [rbp-48h]
  int v62; // [rsp+CCh] [rbp-44h]
  unsigned int v63; // [rsp+D0h] [rbp-40h] BYREF
  unsigned __int8 *v64; // [rsp+D8h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp-30h] BYREF
  int v66; // [rsp+E8h] [rbp-28h] BYREF
  unsigned __int16 *v67; // [rsp+F0h] [rbp-20h]
  struct _CERTTRANSBLOB v68; // [rsp+F8h] [rbp-18h] BYREF
  struct _CERTTRANSBLOB v69; // [rsp+108h] [rbp-8h] BYREF
  struct _CERTTRANSBLOB v70; // [rsp+118h] [rbp+8h] BYREF
  struct _CERTTRANSBLOB v71; // [rsp+128h] [rbp+18h] BYREF
  struct _CERTTRANSBLOB v72; // [rsp+138h] [rbp+28h] BYREF
  unsigned __int16 *v73; // [rsp+148h] [rbp+38h]
  unsigned __int16 *v74; // [rsp+150h] [rbp+40h] BYREF
  int *v75; // [rsp+158h] [rbp+48h]
  struct _CERTTRANSBLOB v76; // [rsp+160h] [rbp+50h] BYREF
  _DWORD v77[20]; // [rsp+170h] [rbp+60h] BYREF

  v10 = bstr;
  v67 = bstr;
  v11 = a3;
  v54 = a3;
  v12 = (unsigned int)a2;
  v59 = a5;
  v60 = a7;
  v73 = bstra;
  v75 = a10;
  v14 = 0;
  hMem = 0;
  v58 = 0;
  v57 = 0;
  bstrString = 0;
  v55 = 0;
  v52[0] = 0;
  v64 = 0;
  v56 = 0;
  *(_QWORD *)&v76.cb = 0;
  v76.pb = 0;
  *(_QWORD *)&v68.cb = 0;
  v68.pb = 0;
  *(_QWORD *)&v69.cb = 0;
  v69.pb = 0;
  *(_QWORD *)&v71.cb = 0;
  v71.pb = 0;
  *(_QWORD *)&v70.cb = 0;
  v70.pb = 0;
  *(_QWORD *)&v72.cb = 0;
  v72.pb = 0;
  v77[0] = 0;
  v77[1] = 1;
  v77[2] = 2;
  if ( !a10 )
  {
    v15 = -2147467261;
    CSPrintErrorLineFile(0x79C02C4u, -2147467261);
    goto LABEL_94;
  }
  CCertRequest::_CleanupResponse((CCertRequest *)this);
  *v75 = 0;
  if ( !Src )
  {
LABEL_7:
    if ( !bstra || !SysStringByteLen(bstra) )
    {
      v24 = -2147467261;
      v25 = 128582340;
      goto LABEL_91;
    }
    if ( (v12 & 0x100000) != 0 || IsWebServer(bstra) )
    {
      if ( (v12 & 0x800000) != 0 )
      {
        v24 = -2147024809;
        v25 = 129106628;
        goto LABEL_91;
      }
      CCertRequest::_Cleanup((CCertRequest *)this);
      v17 = 0;
      v51 = 0;
    }
    else
    {
      v17 = 0;
      v51 = 0;
      if ( (v12 & 0x800000) != 0 )
      {
LABEL_12:
        v18 = v12 | 0x40000;
        v60 = L"CallCA:SendRequest";
        TickCount = GetTickCount();
        v62 = 0;
        v19 = 0;
        if ( !v51 )
          v19 = v17;
        v20 = CCertRequest::_RequestCertificateToRemoteEndPoint(
                (CCertRequest *)this,
                v73,
                &v76,
                v18,
                v19,
                (unsigned __int16 *)hMem,
                a9,
                v11,
                this[15],
                &v57,
                &v55,
                v52,
                &bstrString,
                &v71,
                &v68,
                &v69,
                &v70);
        v15 = v20;
        if ( v20 )
          CSPrintErrorLineFile(0x85A02C4u, v20);
        v62 = v15;
        CCSEventTimer::~CCSEventTimer((CCSEventTimer *)&v60);
        v21 = CCertRequest::_SetInternalRequestState(
                (CCertRequest *)this,
                v52[0],
                v55,
                v57,
                bstrString,
                v15,
                &v69,
                &v71,
                &v68,
                &v70);
        v22 = v21;
        if ( v21 )
          CSPrintErrorLineFile(0x86802C4u, v21);
        if ( v15 )
        {
          v23 = 141099716;
LABEL_47:
          v32 = v15;
LABEL_48:
          CSPrintErrorLineFile(v23, v32);
LABEL_49:
          v14 = hMem;
          goto LABEL_93;
        }
        v63 = 0;
        (*((void (__fastcall **)(unsigned __int16 **, unsigned int *))*this + 10))(this, &v63);
        v74 = 0;
        (*((void (__fastcall **)(unsigned __int16 **, unsigned __int16 **))*this + 21))(this, &v74);
        v37 = this[24];
        if ( !v37 )
        {
LABEL_68:
          if ( v15 )
            v22 = v15;
          v15 = v22;
          if ( !v22 )
          {
            v15 = 0;
            goto LABEL_49;
          }
          v23 = 150143684;
          goto LABEL_47;
        }
        v38 = this + 28;
        v39 = this + 27;
        v15 = ParseCMCResponse(v37, *((unsigned int *)this + 50), this + 26, this + 27);
        if ( v15 )
        {
          this[22] = this[24];
          *((_DWORD *)this + 46) = *((_DWORD *)this + 50);
          this[24] = 0;
          *((_DWORD *)this + 50) = 0;
          v15 = 0;
          goto LABEL_68;
        }
        if ( *((_DWORD *)this + 32) != 5 )
          goto LABEL_68;
        if ( *v38 != 1 )
          goto LABEL_68;
        if ( !(unsigned int)IsCmcResponseForAttestation(*v39) )
          goto LABEL_68;
        *((_DWORD *)this + 26) = 1;
        if ( (v18 & 0x1000000) != 0 )
          goto LABEL_68;
        v59 = 0;
        v42 = Client_SSTpmEndorsementKeyDecryptChallenge(
                (unsigned int)this[24],
                *((_DWORD *)this + 50),
                v40,
                v41,
                (int)this + 224,
                (__int64)&v72.pb,
                (__int64)&v72);
        if ( v42 )
        {
          v15 = myHError(v42);
          v32 = v15;
          v23 = 145228484;
          goto LABEL_48;
        }
        v14 = hMem;
        appended = CCertRequest::_AppendAttribute(v43, (const unsigned __int16 *)hMem, v44, this[15], &v59);
        v15 = appended;
        if ( !appended )
        {
          LocalFree(v14);
          v14 = v59;
          hMem = v59;
          v60 = L"CallCA:SendChallenge";
          TickCount = GetTickCount();
          v62 = 0;
          v46 = CCertRequest::_RequestCertificateToRemoteEndPoint(
                  (CCertRequest *)this,
                  v73,
                  &v72,
                  v18 & 0xFFFF00FF | 0x500,
                  v17,
                  (unsigned __int16 *)v14,
                  a9,
                  v54,
                  v67,
                  &v57,
                  &v55,
                  v52,
                  &bstrString,
                  &v71,
                  &v68,
                  &v69,
                  &v70);
          v15 = v46;
          v62 = v46;
          if ( v46 )
          {
            CSPrintErrorLineFile(0x8C802C4u, v46);
            CCSEventTimer::~CCSEventTimer((CCSEventTimer *)&v60);
            goto LABEL_93;
          }
          CCSEventTimer::~CCSEventTimer((CCSEventTimer *)&v60);
          v47 = CCertRequest::_SetInternalRequestState(
                  (CCertRequest *)this,
                  v52[0],
                  v55,
                  v63,
                  v74,
                  0,
                  &v69,
                  &v71,
                  &v68,
                  &v70);
          v22 = v47;
          if ( v47 )
            CSPrintErrorLineFile(0x8D602C4u, v47);
          if ( this[24] )
          {
            FreeCMCResponse(*v39, (unsigned int)*v38);
            *v38 = 0;
            *v39 = 0;
            v48 = this[26];
            if ( v48 )
            {
              CertCloseStore(v48, 0);
              this[26] = 0;
            }
            v49 = ParseCMCResponse(this[24], *((unsigned int *)this + 50), this + 26, this + 27);
            v15 = v49;
            if ( v49 )
            {
              v32 = v49;
              v23 = 149553860;
              goto LABEL_48;
            }
          }
          goto LABEL_68;
        }
        v24 = appended;
        v25 = 145490628;
LABEL_92:
        CSPrintErrorLineFile(v25, v24);
        goto LABEL_93;
      }
    }
    v26 = v60;
    if ( v60 && SysStringByteLen(v60) )
      v17 = v26;
    v27 = 0;
    if ( v11 != -1 )
      v27 = v11;
    v11 = v27;
    v54 = v27;
    v28 = v59;
    if ( v59 && SysStringByteLen(v59) )
    {
      if ( !v11 && (!v10 || !SysStringByteLen(v10)) && !v17 )
      {
        v66 = (unsigned __int8)v12;
        if ( (_BYTE)v12 && (unsigned __int8)v12 != 1 && (unsigned __int8)v12 != 2 )
        {
          if ( (unsigned __int8)v12 == 255 )
          {
            v29 = 3;
            v30 = v77;
            goto LABEL_41;
          }
          v24 = -2147024809;
          v25 = 134873796;
          goto LABEL_91;
        }
        v29 = 1;
        v30 = (unsigned int *)&v66;
LABEL_41:
        while ( 1 )
        {
          v31 = *v30;
          v15 = DecodeCertString(v28, *v30, &v64, &v56);
          if ( !v15 )
            break;
          if ( v29 == 1 || v15 != -2147024883 && v15 != -2147024774 )
          {
            v23 = 136118980;
            goto LABEL_47;
          }
          CSPrintErrorLineFileData2(L"CR_IN_ENCODEANY", 0x82302C4u, v15, -2147024883);
          --v29;
          ++v30;
          v28 = v59;
        }
        v33 = (CCertRequest *)v12;
        v12 = v31 | v12 & 0xFFFFFF00;
        v76.pb = v64;
        v76.cb = v56;
        v14 = hMem;
        if ( ((unsigned int)v33 & 0x410000) == 0 )
        {
          v58 = 0;
          v34 = CCertRequest::_PrependSkippedRequestHeaderAppendClientId(
                  v33,
                  (const unsigned __int16 *)hMem,
                  (v12 & 0x10000) == 0,
                  v31,
                  v59,
                  &v58);
          v15 = v34;
          if ( v34 )
          {
            v24 = v34;
            v25 = 137822916;
            goto LABEL_92;
          }
          LocalFree(hMem);
          v14 = v58;
          hMem = v58;
        }
        v10 = v67;
        v11 = v54;
LABEL_55:
        v35 = CCertRequest::_SetRequestId((CCertRequest *)this, v11, v10);
        v15 = v35;
        if ( v35 )
        {
          v24 = v35;
          v25 = 138543812;
          goto LABEL_92;
        }
        goto LABEL_12;
      }
      v24 = -2147024809;
      v25 = 133300932;
    }
    else
    {
      v36 = (v17 != 0) + 1;
      if ( !v11 )
        v36 = v17 != 0;
      if ( v10 && SysStringByteLen(v10) )
      {
        ++v36;
        v17 = v10;
        v51 = 1;
      }
      if ( v36 == 1 )
        goto LABEL_55;
      v24 = -2147024809;
      v25 = 132514500;
    }
LABEL_91:
    v15 = v24;
    goto LABEL_92;
  }
  v16 = myDupString(Src, &v58);
  v15 = v16;
  if ( !v16 )
  {
    v14 = v58;
    hMem = v58;
    goto LABEL_7;
  }
  CSPrintErrorLineFile(0x7A402C4u, v16);
  v14 = v58;
LABEL_93:
  *v75 = *((_DWORD *)this + 32);
LABEL_94:
  this[18] = (unsigned __int16 *)v64;
  *((_DWORD *)this + 38) = v56;
  v64 = 0;
  v56 = 0;
  SysFreeString(bstrString);
  LocalFree(0);
  LocalFree(v14);
  LocalFree(v72.pb);
  if ( v68.pb )
    CoTaskMemFree(v68.pb);
  if ( v69.pb )
    CoTaskMemFree(v69.pb);
  if ( v70.pb )
    CoTaskMemFree(v70.pb);
  if ( v71.pb )
    CoTaskMemFree(v71.pb);
  return myHError(v15);
}

```

## disassembly

```asm
0x18001092c  push    rbp
0x18001092e  push    rbx
0x18001092f  push    rsi
0x180010930  push    rdi
0x180010931  push    r12
0x180010933  push    r13
0x180010935  push    r14
0x180010937  push    r15
0x180010939  lea     rbp, [rsp-78h]
0x18001093e  sub     rsp, 188h
0x180010945  mov     r13, r9
0x180010948  mov     [rbp+0B0h+var_D0], r9
0x18001094c  mov     r12d, r8d
0x18001094f  mov     [rbp+0B0h+var_120], r8d
0x180010953  mov     esi, edx
0x180010955  mov     rdi, rcx
0x180010958  mov     rax, [rbp+0B0h+arg_20]
0x18001095f  mov     [rbp+0B0h+var_108], rax
0x180010963  mov     rbx, [rbp+0B0h+Src]
0x18001096a  mov     rax, [rbp+0B0h+arg_30]
0x180010971  mov     [rbp+0B0h+var_100], rax
0x180010975  mov     r15, [rbp+0B0h+bstr]
0x18001097c  mov     [rbp+0B0h+var_78], r15
0x180010980  mov     rcx, [rbp+0B0h+arg_48]
0x180010987  mov     [rbp+0B0h+var_68], rcx
0x18001098b  xor     edx, edx
0x18001098d  mov     r14d, edx
0x180010990  mov     [rbp+0B0h+hMem], rdx
0x180010994  mov     [rbp+0B0h+var_110], rdx
0x180010998  mov     [rbp+0B0h+var_114], edx
0x18001099b  mov     [rbp+0B0h+bstrString], rdx
0x18001099f  mov     [rbp+0B0h+var_11C], edx
0x1800109a2  mov     [rbp+0B0h+var_12C], dx
0x1800109a6  mov     [rbp+0B0h+var_E8], rdx
0x1800109aa  mov     [rbp+0B0h+var_118], edx
0x1800109ad  mov     qword ptr [rbp+0B0h+var_60.cb], rdx
0x1800109b1  mov     [rbp+0B0h+var_60.pb], rdx
0x1800109b5  mov     qword ptr [rbp+0B0h+var_C8.cb], rdx
0x1800109b9  mov     [rbp+0B0h+var_C8.pb], rdx
0x1800109bd  mov     qword ptr [rbp+0B0h+var_B8.cb], rdx
0x1800109c1  mov     [rbp+0B0h+var_B8.pb], rdx
0x1800109c5  mov     qword ptr [rbp+0B0h+var_98.cb], rdx
0x1800109c9  mov     [rbp+0B0h+var_98.pb], rdx
0x1800109cd  mov     qword ptr [rbp+0B0h+var_A8.cb], rdx
0x1800109d1  mov     [rbp+0B0h+var_A8.pb], rdx
0x1800109d5  mov     qword ptr [rbp+0B0h+var_88.cb], rdx
0x1800109d9  mov     [rbp+0B0h+var_88.pb], rdx
0x1800109dd  mov     [rbp+0B0h+var_50], edx
0x1800109e0  mov     [rbp+0B0h+var_4C], 1
0x1800109e7  mov     [rbp+0B0h+var_48], 2
0x1800109ee  test    rcx, rcx
0x1800109f1  jnz     short loc_180010A0A
0x1800109f3  mov     edx, 80004003h
0x1800109f8  mov     ebx, edx
0x1800109fa  mov     ecx, 79C02C4h
0x1800109ff  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010a05  jmp     loc_180011145
0x180010a0a  mov     rcx, rdi; this
0x180010a0d  call    ?_CleanupResponse@CCertRequest@@AEAAXXZ; CCertRequest::_CleanupResponse(void)
0x180010a12  mov     rax, [rbp+0B0h+var_68]
0x180010a16  mov     [rax], r14d
0x180010a19  test    rbx, rbx
0x180010a1c  jz      short loc_180010A4E
0x180010a1e  lea     rdx, [rbp+0B0h+var_110]; unsigned __int16 **
0x180010a22  mov     rcx, rbx; Src
0x180010a25  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180010a2a  mov     ebx, eax
0x180010a2c  test    eax, eax
0x180010a2e  jz      short loc_180010A46
0x180010a30  mov     edx, eax
0x180010a32  mov     ecx, 7A402C4h
0x180010a37  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010a3d  mov     r14, [rbp+0B0h+var_110]
0x180010a41  jmp     loc_180011139
0x180010a46  mov     r14, [rbp+0B0h+var_110]
0x180010a4a  mov     [rbp+0B0h+hMem], r14
0x180010a4e  test    r15, r15
0x180010a51  jz      loc_180011127
0x180010a57  mov     rcx, r15; bstr
0x180010a5a  call    cs:__imp_SysStringByteLen
0x180010a60  test    eax, eax
0x180010a62  jz      loc_180011127
0x180010a68  bt      esi, 14h
0x180010a6c  jb      loc_180010BC9
0x180010a72  mov     rcx, r15; unsigned __int16 *
0x180010a75  call    ?IsWebServer@@YA_NPEBG@Z; IsWebServer(ushort const *)
0x180010a7a  test    al, al
0x180010a7c  jnz     loc_180010BC9
0x180010a82  xor     r15d, r15d
0x180010a85  mov     [rbp+0B0h+var_130], r15b
0x180010a89  bt      esi, 17h
0x180010a8d  jnb     loc_180010BED
0x180010a93  bts     esi, 12h
0x180010a97  lea     rax, aCallcaSendrequ; "CallCA:SendRequest"
0x180010a9e  mov     [rbp+0B0h+var_100], rax
0x180010aa2  call    cs:__imp_GetTickCount
0x180010aa8  mov     [rbp+0B0h+var_F8], eax
0x180010aab  mov     [rbp+0B0h+var_F4], 0
0x180010ab2  xor     ecx, ecx
0x180010ab4  cmp     [rbp+0B0h+var_130], cl
0x180010ab7  cmovz   rcx, r15
0x180010abb  lea     rax, [rbp+0B0h+var_A8]
0x180010abf  mov     [rsp+1C0h+var_140], rax; struct _CERTTRANSBLOB *
0x180010ac7  lea     rax, [rbp+0B0h+var_B8]
0x180010acb  mov     [rsp+1C0h+var_148], rax; struct _CERTTRANSBLOB *
0x180010ad0  lea     rax, [rbp+0B0h+var_C8]
0x180010ad4  mov     [rsp+1C0h+var_150], rax; struct _CERTTRANSBLOB *
0x180010ad9  lea     rax, [rbp+0B0h+var_98]
0x180010add  mov     [rsp+1C0h+var_158], rax; struct _CERTTRANSBLOB *
0x180010ae2  lea     rax, [rbp+0B0h+bstrString]
0x180010ae6  mov     [rsp+1C0h+var_160], rax; unsigned __int16 **
0x180010aeb  lea     rax, [rbp+0B0h+var_12C]
0x180010aef  mov     [rsp+1C0h+var_168], rax; __int16 *
0x180010af4  lea     rax, [rbp+0B0h+var_11C]
0x180010af8  mov     [rsp+1C0h+var_170], rax; unsigned int *
0x180010afd  lea     rax, [rbp+0B0h+var_114]
0x180010b01  mov     [rsp+1C0h+var_178], rax; unsigned int *
0x180010b06  mov     rax, [rdi+78h]
0x180010b0a  mov     [rsp+1C0h+var_180], rax; unsigned __int16 *
0x180010b0f  mov     dword ptr [rsp+1C0h+var_188], r12d; unsigned int
0x180010b14  mov     eax, [rbp+0B0h+arg_40]
0x180010b1a  mov     dword ptr [rsp+1C0h+var_190], eax; unsigned int
0x180010b1e  mov     rax, [rbp+0B0h+hMem]
0x180010b22  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x180010b27  mov     [rsp+1C0h+var_1A0], rcx; unsigned __int16 *
0x180010b2c  mov     r9d, esi; unsigned int
0x180010b2f  lea     r8, [rbp+0B0h+var_60]; struct _CERTTRANSBLOB *
0x180010b33  mov     rdx, [rbp+0B0h+var_78]; unsigned __int16 *
0x180010b37  mov     rcx, rdi; this
0x180010b3a  call    ?_RequestCertificateToRemoteEndPoint@CCertRequest@@AEAAJPEAGPEAU_CERTTRANSBLOB@@KPEBG0KK0PEAKPEAJPEAFPEAPEAG1111@Z; CCertRequest::_RequestCertificateToRemoteEndPoint(ushort *,_CERTTRANSBLOB *,ulong,ushort const *,ushort *,ulong,ulong,ushort *,ulong *,long *,short *,ushort * *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)
0x180010b3f  mov     ebx, eax
0x180010b41  test    eax, eax
0x180010b43  jz      short loc_180010B52
0x180010b45  mov     edx, eax
0x180010b47  mov     ecx, 85A02C4h
0x180010b4c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010b52  mov     [rbp+0B0h+var_F4], ebx
0x180010b55  lea     rcx, [rbp+0B0h+var_100]; this
0x180010b59  call    ??1CCSEventTimer@@QEAA@XZ; CCSEventTimer::~CCSEventTimer(void)
0x180010b5e  lea     rax, [rbp+0B0h+var_A8]
0x180010b62  mov     [rsp+1C0h+var_178], rax; struct _CERTTRANSBLOB *
0x180010b67  lea     rax, [rbp+0B0h+var_C8]
0x180010b6b  mov     [rsp+1C0h+var_180], rax; struct _CERTTRANSBLOB *
0x180010b70  lea     rax, [rbp+0B0h+var_98]
0x180010b74  mov     [rsp+1C0h+var_188], rax; struct _CERTTRANSBLOB *
0x180010b79  lea     rax, [rbp+0B0h+var_B8]
0x180010b7d  mov     [rsp+1C0h+var_190], rax; struct _CERTTRANSBLOB *
0x180010b82  mov     dword ptr [rsp+1C0h+var_198], ebx; int
0x180010b86  mov     rax, [rbp+0B0h+bstrString]
0x180010b8a  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 *
0x180010b8f  mov     r9d, [rbp+0B0h+var_114]; unsigned int
0x180010b93  mov     r8d, [rbp+0B0h+var_11C]; int
0x180010b97  movzx   edx, [rbp+0B0h+var_12C]; __int16
0x180010b9b  mov     rcx, rdi; this
0x180010b9e  call    ?_SetInternalRequestState@CCertRequest@@AEAAJFJKPEAGJPEAU_CERTTRANSBLOB@@111@Z; CCertRequest::_SetInternalRequestState(short,long,ulong,ushort *,long,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)
0x180010ba3  mov     r14d, eax
0x180010ba6  test    eax, eax
0x180010ba8  jz      short loc_180010BB7
0x180010baa  mov     edx, eax
0x180010bac  mov     ecx, 86802C4h
0x180010bb1  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010bb7  test    ebx, ebx
0x180010bb9  jz      loc_180010E02
0x180010bbf  mov     ecx, 86902C4h
0x180010bc4  jmp     loc_180010CFB
0x180010bc9  bt      esi, 17h
0x180010bcd  jnb     short loc_180010BDE
0x180010bcf  mov     edx, 80070057h
0x180010bd4  mov     ecx, 7B202C4h
0x180010bd9  jmp     loc_180011131
0x180010bde  mov     rcx, rdi; this
0x180010be1  call    ?_Cleanup@CCertRequest@@AEAAXXZ; CCertRequest::_Cleanup(void)
0x180010be6  xor     r15d, r15d
0x180010be9  mov     [rbp+0B0h+var_130], r15b
0x180010bed  mov     rbx, [rbp+0B0h+var_100]
0x180010bf1  test    rbx, rbx
0x180010bf4  jz      short loc_180010C05
0x180010bf6  mov     rcx, rbx; bstr
0x180010bf9  call    cs:__imp_SysStringByteLen
0x180010bff  test    eax, eax
0x180010c01  cmovnz  r15, rbx
0x180010c05  xor     eax, eax
0x180010c07  cmp     r12d, 0FFFFFFFFh
0x180010c0b  cmovnz  eax, r12d
0x180010c0f  mov     r12d, eax
0x180010c12  mov     [rbp+0B0h+var_120], eax
0x180010c15  mov     rbx, [rbp+0B0h+var_108]
0x180010c19  test    rbx, rbx
0x180010c1c  jz      loc_180010DC2
0x180010c22  mov     rcx, rbx; bstr
0x180010c25  call    cs:__imp_SysStringByteLen
0x180010c2b  test    eax, eax
0x180010c2d  jz      loc_180010DC2
0x180010c33  test    r12d, r12d
0x180010c36  jnz     loc_180010DB3
0x180010c3c  test    r13, r13
0x180010c3f  jz      short loc_180010C52
0x180010c41  mov     rcx, r13; bstr
0x180010c44  call    cs:__imp_SysStringByteLen
0x180010c4a  test    eax, eax
0x180010c4c  jnz     loc_180010DB3
0x180010c52  test    r15, r15
0x180010c55  jnz     loc_180010DB3
0x180010c5b  movzx   eax, sil
0x180010c5f  mov     [rbp+0B0h+var_D8], eax
0x180010c62  test    sil, sil
0x180010c65  jz      short loc_180010C93
0x180010c67  sub     eax, 1
0x180010c6a  jz      short loc_180010C93
0x180010c6c  sub     eax, 1
0x180010c6f  jz      short loc_180010C93
0x180010c71  cmp     eax, 0FDh
0x180010c76  jz      short loc_180010C87
0x180010c78  mov     edx, 80070057h
0x180010c7d  mov     ecx, 80A02C4h
0x180010c82  jmp     loc_180011131
0x180010c87  mov     r14d, 3
0x180010c8d  lea     r12, [rbp+0B0h+var_50]
0x180010c91  jmp     short loc_180010C9D
0x180010c93  mov     r14d, 1
0x180010c99  lea     r12, [rbp+0B0h+var_D8]
0x180010c9d  mov     r13d, [r12]
0x180010ca1  lea     r9, [rbp+0B0h+var_118]; unsigned int *
0x180010ca5  lea     r8, [rbp+0B0h+var_E8]; unsigned __int8 **
0x180010ca9  mov     edx, r13d; unsigned int
0x180010cac  mov     rcx, rbx; bstr
0x180010caf  call    ?DecodeCertString@@YAJQEAGKPEAPEAEPEAK@Z; DecodeCertString(ushort * const,ulong,uchar * *,ulong *)
0x180010cb4  mov     ebx, eax
0x180010cb6  test    eax, eax
0x180010cb8  jz      short loc_180010D0C
0x180010cba  cmp     r14d, 1
0x180010cbe  jz      short loc_180010CF6
0x180010cc0  mov     eax, 8007000Dh
0x180010cc5  cmp     ebx, eax
0x180010cc7  jz      short loc_180010CD1
0x180010cc9  cmp     ebx, 8007007Ah
0x180010ccf  jnz     short loc_180010CF6
0x180010cd1  mov     r9d, eax
0x180010cd4  mov     r8d, ebx
0x180010cd7  mov     edx, 82302C4h
0x180010cdc  lea     rcx, aCrInEncodeany; "CR_IN_ENCODEANY"
0x180010ce3  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010ce9  dec     r14d
0x180010cec  add     r12, 4
0x180010cf0  mov     rbx, [rbp+0B0h+var_108]
0x180010cf4  jmp     short loc_180010C9D
0x180010cf6  mov     ecx, 81D02C4h
0x180010cfb  mov     edx, ebx
0x180010cfd  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010d03  mov     r14, [rbp+0B0h+hMem]
0x180010d07  jmp     loc_180011139
0x180010d0c  mov     ecx, esi; this
0x180010d0e  and     esi, 0FFFFFF00h
0x180010d14  or      esi, r13d
0x180010d17  mov     rax, [rbp+0B0h+var_E8]
0x180010d1b  mov     [rbp+0B0h+var_60.pb], rax
0x180010d1f  mov     eax, [rbp+0B0h+var_118]
0x180010d22  mov     [rbp+0B0h+var_60.cb], eax
0x180010d25  mov     r14, [rbp+0B0h+hMem]
0x180010d29  test    ecx, 410000h
0x180010d2f  jnz     short loc_180010D87
0x180010d31  mov     [rbp+0B0h+var_110], 0
0x180010d39  mov     r8d, esi
0x180010d3c  shr     r8d, 10h
0x180010d40  not     r8b
0x180010d43  and     r8b, 1; bool
0x180010d47  lea     rax, [rbp+0B0h+var_110]
0x180010d4b  mov     [rsp+1C0h+var_198], rax; unsigned __int16 **
0x180010d50  mov     rax, [rbp+0B0h+var_108]
0x180010d54  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 *
0x180010d59  mov     r9d, r13d; unsigned int
0x180010d5c  mov     rdx, r14; unsigned __int16 *
0x180010d5f  call    ?_PrependSkippedRequestHeaderAppendClientId@CCertRequest@@AEAAJPEBG_NK0PEAPEAG@Z; CCertRequest::_PrependSkippedRequestHeaderAppendClientId(ushort const *,bool,ulong,ushort const *,ushort * *)
0x180010d64  mov     ebx, eax
0x180010d66  test    eax, eax
0x180010d68  jz      short loc_180010D76
0x180010d6a  mov     edx, eax
0x180010d6c  mov     ecx, 83702C4h
0x180010d71  jmp     loc_180011133
0x180010d76  mov     rcx, r14; hMem
0x180010d79  call    cs:__imp_LocalFree
0x180010d7f  mov     r14, [rbp+0B0h+var_110]
0x180010d83  mov     [rbp+0B0h+hMem], r14
0x180010d87  mov     r13, [rbp+0B0h+var_D0]
0x180010d8b  mov     r12d, [rbp+0B0h+var_120]
0x180010d8f  mov     r8, r13; unsigned __int16 *
0x180010d92  mov     edx, r12d; unsigned int
0x180010d95  mov     rcx, rdi; this
0x180010d98  call    ?_SetRequestId@CCertRequest@@AEAAJKPEAG@Z; CCertRequest::_SetRequestId(ulong,ushort *)
0x180010d9d  mov     ebx, eax
0x180010d9f  test    eax, eax
0x180010da1  jz      loc_180010A93
0x180010da7  mov     edx, eax
0x180010da9  mov     ecx, 84202C4h
0x180010dae  jmp     loc_180011133
0x180010db3  mov     edx, 80070057h
0x180010db8  mov     ecx, 7F202C4h
0x180010dbd  jmp     loc_180011131
0x180010dc2  xor     eax, eax
0x180010dc4  test    r15, r15
  ... truncated ...
```
