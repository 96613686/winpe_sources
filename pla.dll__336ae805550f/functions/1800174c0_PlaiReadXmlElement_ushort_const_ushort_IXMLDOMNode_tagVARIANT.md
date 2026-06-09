# PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)

- ea: `0x1800174c0`
- end: `0x18001829d`
- name: `?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `3549`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16, struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `13`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800133cc`
- `0x180014310`
- `0x180016024`
- `0x180044924`
- `0x1800482e8`
- `0x18004946c`
- `0x18004fa78`
- `0x180057f9c`
- `0x180097fbc`
- `0x1800a10c4`
- `0x1800e64d8`
- `0x1800f2fa0`
- `0x180107368`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800174c0`
- `0x180018420`
- `0x18005179c`
- `0x18006770c`
- `0x1800e4ffc`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800180f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800180f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180017683`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180018292`
- `OLEAUT32!__imp_SysFreeString` at `0x180017683`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180018292`
- `OLEAUT32!__imp_VariantInit` at `0x180017529`
- `OLEAUT32!__imp_VariantInit` at `0x18001753b`
- `OLEAUT32!__imp_VariantInit` at `0x180017529`
- `OLEAUT32!__imp_VariantInit` at `0x18001753b`
- `OLEAUT32!__imp_VariantClear` at `0x180017642`
- `OLEAUT32!__imp_VariantClear` at `0x1800176c3`
- `OLEAUT32!__imp_VariantClear` at `0x180017770`
- `OLEAUT32!__imp_VariantClear` at `0x1800177ba`
- `OLEAUT32!__imp_VariantClear` at `0x180017b95`
- `OLEAUT32!__imp_VariantClear` at `0x180017d55`
- `OLEAUT32!__imp_VariantClear` at `0x180017642`
- `OLEAUT32!__imp_VariantClear` at `0x1800176c3`
- `OLEAUT32!__imp_VariantClear` at `0x180017770`
- `OLEAUT32!__imp_VariantClear` at `0x1800177ba`
- `OLEAUT32!__imp_VariantClear` at `0x180017b95`
- `OLEAUT32!__imp_VariantClear` at `0x180017d55`
- `OLEAUT32!__imp_VariantCopy` at `0x180018248`
- `OLEAUT32!__imp_VariantCopy` at `0x180018248`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001762e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001762e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180018272`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180018272`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180018175`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180018175`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800181f6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180018260`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800181f6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180018260`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001815c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001815c`

## string_xrefs

- `0x180017830`: `PlaiReadXmlElement`
- `0x180017930`: `PlaiReadXmlElement`
- `0x180017b50`: `PlaiReadXmlElement`
- `0x180017d10`: `PlaiReadXmlElement`

## pseudocode

```c
__int64 __fastcall PlaiReadXmlElement(
        const unsigned __int16 *a1,
        __int16 a2,
        struct IXMLDOMNode *a3,
        struct tagVARIANT *a4)
{
  SAFEARRAY *v5; // r12
  __int16 v8; // di
  OLECHAR *v9; // r14
  HRESULT (__stdcall *get_namespaceURI)(IXMLDOMNode *, BSTR *); // r15
  unsigned int v11; // eax
  const char *v12; // rdx
  __int64 v13; // rcx
  int v14; // r8d
  OLECHAR *v15; // r14
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v17; // eax
  unsigned int v18; // edi
  VARTYPE v19; // si
  HRESULT v20; // eax
  __int64 v22; // rax
  bool v23; // zf
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  DWORD LastError; // edi
  int v38; // eax
  int v39; // eax
  SAFEARRAY *Vector; // rax
  HRESULT v41; // eax
  signed int i; // esi
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  HRESULT v47; // eax
  int v48; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v49; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h] BYREF
  ULONG cElements; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  void *ppvData; // [rsp+B0h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v56[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v57[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v58[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v59[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v60[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v61[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v62[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v63[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v64[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v65[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v66[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v67[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v68[64]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v69[64]; // [rsp+740h] [rbp+640h] BYREF

  LOWORD(v49) = a2;
  cElements = 0;
  ppvData = 0;
  v51 = 0;
  v53 = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  v8 = a2;
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( a4 )
  {
    VariantInit(a4);
    a4->llVal = 0;
  }
  v9 = bstrString;
  get_namespaceURI = a3->lpVtbl->get_namespaceURI;
  if ( bstrString )
  {
    LastError = GetLastError();
    SysFreeString(v9);
    SetLastError(LastError);
    v8 = (__int16)v49;
  }
  bstrString = 0;
  v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))get_namespaceURI)(a3, &bstrString);
  if ( v11 != 1 )
    MicrosoftTelemetryAssertTriggeredArgs(v13, v11);
  v15 = PlaiAllocStringEx(a1, v12, v14);
  if ( v15 )
  {
    lpVtbl = a3->lpVtbl;
    if ( (v8 & 0x2000) == 0 )
    {
      if ( ((int (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))lpVtbl->selectSingleNode)(a3, v15, &v51) >= 0
        && v51 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v51 + 208LL))(v51, &pvarg.cyVal);
        v18 = v17;
        if ( v17 >= 0 )
        {
          v19 = (unsigned __int16)v49;
          pvarg.vt = 8;
          if ( (_WORD)v49 )
          {
            if ( (unsigned __int16)v49 == 3 || (unsigned __int16)v49 == 19 )
            {
              v46 = PlaiHexToLong(pvarg.bstrVal, &a4->lVal);
              v18 = v46;
              if ( v46 < 0 )
              {
                v48 = 0;
                LODWORD(v49) = v46;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_72;
                }
                PlaiWhoAmI(v67, 0x4000000000000800uLL);
                v35 = -1;
                do
                  v23 = v67[++v35] == 0;
                while ( !v23 );
                goto LABEL_88;
              }
            }
            else
            {
              if ( (unsigned int)(unsigned __int16)v49 - 20 >= 2 )
              {
                v20 = VariantChangeType(a4, &pvarg, 0, (VARTYPE)v49);
                v18 = v20;
                if ( v20 >= 0 )
                {
LABEL_17:
                  VariantClear(&pvarg);
                  pvarg.llVal = 0;
                  goto LABEL_18;
                }
                v48 = 0;
                LODWORD(v49) = v20;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_72;
                }
                PlaiWhoAmI(v65, 0x4000000000000800uLL);
                v33 = -1;
                do
                  v23 = v65[++v33] == 0;
                while ( !v23 );
LABEL_88:
                EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v49, 4, byte_180147320, 1, &v48, 4);
                goto LABEL_72;
              }
              v45 = PlaiHexToLongLong(pvarg.bstrVal, &a4->llVal);
              v18 = v45;
              if ( v45 < 0 )
              {
                v48 = 0;
                LODWORD(v49) = v45;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_72;
                }
                PlaiWhoAmI(v66, 0x4000000000000800uLL);
                v34 = -1;
                do
                  v23 = v66[++v34] == 0;
                while ( !v23 );
                goto LABEL_88;
              }
            }
LABEL_151:
            a4->vt = v19;
            goto LABEL_17;
          }
          v47 = VariantCopy(a4, &pvarg);
          v18 = v47;
          if ( v47 >= 0 )
            goto LABEL_17;
          v48 = 0;
          LODWORD(v49) = v47;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_72;
          }
          PlaiWhoAmI(v68, 0x4000000000000800uLL);
          v36 = -1;
          do
            v23 = v68[++v36] == 0;
          while ( !v23 );
          goto LABEL_88;
        }
        LODWORD(v49) = v17;
        v48 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_37;
        }
        PlaiWhoAmI(v64, 0x4000000000000800uLL);
        v24 = -1;
        do
          v23 = v64[++v24] == 0;
        while ( !v23 );
      }
      else
      {
        v18 = -2147024637;
        v48 = 0;
        LODWORD(v49) = -2147024637;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          VariantClear(&pvarg);
          goto LABEL_38;
        }
        PlaiWhoAmI(v69, 0x4000000000000800uLL);
        v26 = -1;
        do
          v23 = v69[++v26] == 0;
        while ( !v23 );
      }
      goto LABEL_53;
    }
    v38 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))lpVtbl->selectNodes)(a3, v15, &v53);
    v18 = v38;
    if ( v38 < 0 )
    {
      LODWORD(v49) = v38;
      v48 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_37;
      }
      PlaiWhoAmI(v57, 0x4000000000000800uLL);
      v25 = -1;
      do
        v23 = v57[++v25] == 0;
      while ( !v23 );
      goto LABEL_53;
    }
    if ( !v53 )
    {
      v18 = -2147467259;
      v48 = 0;
      LODWORD(v49) = -2147467259;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_37;
      }
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v27 = -1;
      do
        v23 = v58[++v27] == 0;
      while ( !v23 );
      goto LABEL_53;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v53 + 64LL))(v53, &cElements);
    v18 = v39;
    if ( v39 < 0 )
    {
      LODWORD(v49) = v39;
      v48 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_37;
      }
      PlaiWhoAmI(v59, 0x4000000000000800uLL);
      v28 = -1;
      do
        v23 = v59[++v28] == 0;
      while ( !v23 );
LABEL_53:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v49, 4, byte_180147320, 1, &v48, 4);
LABEL_37:
      VariantClear(&pvarg);
LABEL_38:
      pvarg.llVal = 0;
      goto LABEL_18;
    }
    Vector = SafeArrayCreateVector(8u, 0, cElements);
    v5 = Vector;
    if ( Vector )
    {
      v41 = SafeArrayAccessData(Vector, &ppvData);
      v18 = v41;
      if ( v41 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= (int)cElements )
          {
            SafeArrayUnaccessData(v5);
            v19 = (unsigned __int16)v49;
            a4->llVal = (LONGLONG)v5;
            v5 = 0;
            goto LABEL_151;
          }
          if ( v51 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
            v51 = 0;
          }
          v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 72LL))(v53, &v51);
          v18 = v43;
          if ( v43 < 0 )
            break;
          v44 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 208LL))(v51, (char *)ppvData + 8 * i);
          v18 = v44;
          if ( v44 < 0 )
          {
            v48 = 0;
            LODWORD(v49) = v44;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v62, 0x4000000000000800uLL);
              v31 = -1;
              do
                v23 = v62[++v31] == 0;
              while ( !v23 );
              goto LABEL_71;
            }
            goto LABEL_72;
          }
        }
        v48 = 0;
        LODWORD(v49) = v43;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v63, 0x4000000000000800uLL);
          v32 = -1;
          do
            v23 = v63[++v32] == 0;
          while ( !v23 );
          goto LABEL_71;
        }
        goto LABEL_72;
      }
      v48 = 0;
      LODWORD(v49) = v41;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
LABEL_72:
        VariantClear(&pvarg);
        pvarg.llVal = 0;
LABEL_18:
        v49 = v15;
        v48 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
        {
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_FREE_STRING, 3, byte_180147320, 1, &v48, 4, &v49, 8);
        }
        SysFreeString(v15);
        goto LABEL_24;
      }
      PlaiWhoAmI(v61, 0x4000000000000800uLL);
      v30 = -1;
      do
        v23 = v61[++v30] == 0;
      while ( !v23 );
    }
    else
    {
      v18 = -2147024882;
      v48 = 0;
      LODWORD(v49) = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_72;
      }
      PlaiWhoAmI(v60, 0x4000000000000800uLL);
      v29 = -1;
      do
        v23 = v60[++v29] == 0;
      while ( !v23 );
    }
LABEL_71:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v49, 4, byte_180147320, 1, &v48, 4);
    goto LABEL_72;
  }
  v18 = -2147024882;
  LODWORD(v49) = 0;
  v48 = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v22 = -1;
    do
      v23 = v56[++v22] == 0;
    while ( !v23 );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v48, 4, byte_180147320, 1, &v49, 4);
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
LABEL_24:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v5);
    ppvData = 0;
  }
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v18;
}

```

## disassembly

```asm
0x1800174c0  push    rbp
0x1800174c2  push    rbx
0x1800174c3  push    rsi
0x1800174c4  push    rdi
0x1800174c5  push    r12
0x1800174c7  push    r13
0x1800174c9  push    r14
0x1800174cb  push    r15
0x1800174cd  lea     rbp, [rsp-6D8h]
0x1800174d5  sub     rsp, 7D8h
0x1800174dc  mov     rax, cs:__security_cookie
0x1800174e3  xor     rax, rsp
0x1800174e6  mov     [rbp+710h+var_50], rax
0x1800174ed  xor     r14d, r14d
0x1800174f0  mov     word ptr [rsp+810h+var_798], dx
0x1800174f5  mov     r13, rcx
0x1800174f8  mov     [rbp+710h+cElements], r14d
0x1800174fc  xorps   xmm0, xmm0
0x1800174ff  mov     [rbp+710h+ppvData], r14
0x180017503  xor     eax, eax
0x180017505  mov     [rbp+710h+var_778], r14
0x180017509  lea     rcx, [rbp+710h+pvarg]; pvarg
0x18001750d  mov     [rbp+710h+var_768], r14
0x180017511  mov     r12d, r14d
0x180017514  mov     qword ptr [rbp+710h+pvarg+10h], rax
0x180017518  movups  xmmword ptr [rbp+710h+pvarg], xmm0
0x18001751c  mov     [rbp+710h+bstrString], r14
0x180017520  mov     rbx, r9
0x180017523  mov     rsi, r8
0x180017526  movzx   edi, dx
0x180017529  call    cs:__imp_VariantInit
0x18001752f  mov     qword ptr [rbp+710h+pvarg+8], r14
0x180017533  test    rbx, rbx
0x180017536  jz      short loc_180017545
0x180017538  mov     rcx, rbx; pvarg
0x18001753b  call    cs:__imp_VariantInit
0x180017541  mov     [rbx+8], r14
0x180017545  mov     rax, [rsi]
0x180017548  mov     r14, [rbp+710h+bstrString]
0x18001754c  mov     r15, [rax+138h]
0x180017553  test    r14, r14
0x180017556  jnz     loc_1800180DD
0x18001755c  lea     rdx, [rbp+710h+bstrString]
0x180017560  mov     [rbp+710h+bstrString], r12
0x180017564  mov     rcx, rsi
0x180017567  mov     rax, r15
0x18001756a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001756f  cmp     eax, 1
0x180017572  jnz     loc_180018100
0x180017578  mov     rcx, r13; unsigned __int16 *
0x18001757b  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x180017580  mov     r14, rax
0x180017583  test    rax, rax
0x180017586  jz      loc_18001768E
0x18001758c  bt      di, 0Dh
0x180017591  mov     rax, [rsi]
0x180017594  mov     rdx, r14
0x180017597  mov     rcx, rsi
0x18001759a  jb      loc_18001810C
0x1800175a0  mov     rax, [rax+128h]
0x1800175a7  lea     r8, [rbp+710h+var_778]
0x1800175ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175b0  test    eax, eax
0x1800175b2  js      loc_180017785
0x1800175b8  mov     rcx, [rbp+710h+var_778]
0x1800175bc  test    rcx, rcx
0x1800175bf  jz      loc_180017785
0x1800175c5  mov     rax, [rcx]
0x1800175c8  lea     rdx, [rbp+710h+pvarg+8]
0x1800175cc  mov     rax, [rax+0D0h]
0x1800175d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d8  mov     edi, eax
0x1800175da  test    eax, eax
0x1800175dc  js      loc_180017739
0x1800175e2  movzx   esi, word ptr [rsp+810h+var_798]
0x1800175e7  mov     r15d, 8
0x1800175ed  mov     word ptr [rbp+710h+pvarg], r15w
0x1800175f2  mov     ecx, esi
0x1800175f4  test    esi, esi
0x1800175f6  jz      loc_180018241
0x1800175fc  sub     ecx, 3
0x1800175ff  jz      loc_180018222
0x180017605  sub     ecx, 10h
0x180017608  jz      loc_180018222
0x18001760e  sub     ecx, 1
0x180017611  jz      loc_18001820A
0x180017617  cmp     ecx, 1
0x18001761a  jz      loc_18001820A
0x180017620  xor     r8d, r8d; wFlags
0x180017623  lea     rdx, [rbp+710h+pvarg]; pvarSrc
0x180017627  movzx   r9d, si; vt
0x18001762b  mov     rcx, rbx; pvargDest
0x18001762e  call    cs:__imp_VariantChangeType
0x180017634  mov     edi, eax
0x180017636  test    eax, eax
0x180017638  js      loc_180017FF9
0x18001763e  lea     rcx, [rbp+710h+pvarg]; pvarg
0x180017642  call    cs:__imp_VariantClear
0x180017648  mov     qword ptr [rbp+710h+pvarg+8], r12
0x18001764c  lea     rbx, byte_180147320
0x180017653  cmp     dword ptr cs:xmmword_180169738, 0
0x18001765a  mov     [rsp+810h+var_798], r14
0x18001765f  mov     [rsp+810h+var_7A0], 0
0x180017667  jz      short loc_180017680
0x180017669  mov     rdx, 4000000000000200h
0x180017673  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001767a  jnz     loc_1800179D2
0x180017680  mov     rcx, r14; bstrString
0x180017683  call    cs:__imp_SysFreeString
0x180017689  xor     r14d, r14d
0x18001768c  jmp     short loc_1800176CD
0x18001768e  xor     r14d, r14d
0x180017691  mov     edi, 8007000Eh
0x180017696  cmp     dword ptr cs:xmmword_180169738, r12d
0x18001769d  mov     dword ptr [rsp+810h+var_798], r14d
0x1800176a2  mov     [rsp+810h+var_7A0], edi
0x1800176a6  jz      short loc_1800176BF
0x1800176a8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800176b2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800176b9  jnz     loc_1800177C9
0x1800176bf  lea     rcx, [rbp+710h+pvarg]; pvarg
0x1800176c3  call    cs:__imp_VariantClear
0x1800176c9  mov     qword ptr [rbp+710h+pvarg+8], r14
0x1800176cd  cmp     [rbp+710h+ppvData], 0
0x1800176d2  jnz     loc_18001825D
0x1800176d8  test    r12, r12
0x1800176db  jnz     loc_18001826F
0x1800176e1  mov     rcx, [rbp+710h+var_768]
0x1800176e5  test    rcx, rcx
0x1800176e8  jnz     loc_18001827D
0x1800176ee  mov     rcx, [rbp+710h+var_778]
0x1800176f2  test    rcx, rcx
0x1800176f5  jz      short loc_180017707
0x1800176f7  mov     rax, [rcx]
0x1800176fa  mov     rax, [rax+10h]
0x1800176fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017703  mov     [rbp+710h+var_778], r14
0x180017707  mov     rcx, [rbp+710h+bstrString]; bstrString
0x18001770b  test    rcx, rcx
0x18001770e  jnz     loc_180018292
0x180017714  mov     eax, edi
0x180017716  mov     rcx, [rbp+710h+var_50]
0x18001771d  xor     rcx, rsp; StackCookie
0x180017720  call    __security_check_cookie
0x180017725  add     rsp, 7D8h
0x18001772c  pop     r15
0x18001772e  pop     r14
0x180017730  pop     r13
0x180017732  pop     r12
0x180017734  pop     rdi
0x180017735  pop     rsi
0x180017736  pop     rbx
0x180017737  pop     rbp
0x180017738  retn
0x180017739  xor     r15d, r15d
0x18001773c  mov     dword ptr [rsp+810h+var_798], eax
0x180017740  cmp     dword ptr cs:xmmword_180169738, r12d
0x180017747  lea     rbx, byte_180147320
0x18001774e  mov     [rsp+810h+var_7A0], r15d
0x180017753  jz      short loc_18001776C
0x180017755  mov     rdx, 4000000000000800h; unsigned __int64
0x18001775f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180017766  jnz     loc_18001787E
0x18001776c  lea     rcx, [rbp+710h+pvarg]; pvarg
0x180017770  call    cs:__imp_VariantClear
0x180017776  mov     qword ptr [rbp+710h+pvarg+8], r15
0x18001777a  mov     r15d, 8
0x180017780  jmp     loc_180017653
0x180017785  xor     r15d, r15d
0x180017788  mov     edi, 80070103h
0x18001778d  cmp     dword ptr cs:xmmword_180169738, r12d
0x180017794  mov     [rsp+810h+var_7A0], r15d
0x180017799  mov     dword ptr [rsp+810h+var_798], edi
0x18001779d  jz      short loc_1800177B6
0x18001779f  mov     rdx, 4000000000000800h; unsigned __int64
0x1800177a9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800177b0  jnz     loc_180017976
0x1800177b6  lea     rcx, [rbp+710h+pvarg]; pvarg
0x1800177ba  call    cs:__imp_VariantClear
0x1800177c0  lea     rbx, byte_180147320
0x1800177c7  jmp     short loc_180017776
0x1800177c9  mov     rax, cs:qword_180169748
0x1800177d0  and     rax, rdx
0x1800177d3  cmp     cs:qword_180169748, rax
0x1800177da  jnz     loc_1800176BF
0x1800177e0  lea     rcx, [rbp+710h+var_750]; unsigned __int16 *
0x1800177e4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800177e9  lea     rcx, [rbp+710h+var_750]
0x1800177ed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800177f4  cmp     [rcx+rax*2+2], r12w
0x1800177fa  lea     rax, [rax+1]
0x1800177fe  jnz     short loc_1800177F4
0x180017800  lea     ecx, [rax+rax]
0x180017803  mov     r8d, 5
0x180017809  add     rcx, 2
0x18001780d  lea     rax, [rbp+710h+var_750]
0x180017811  mov     [rsp+810h+var_7B0], rcx
0x180017816  lea     rbx, byte_180147320
0x18001781d  mov     [rsp+810h+var_7B8], rax
0x180017822  lea     r9, [rsp+810h+var_7A0]
0x180017827  mov     [rsp+810h+var_7C0], 13h
0x180017830  lea     rax, aPlaireadxmlele; "PlaiReadXmlElement"
0x180017837  mov     [rsp+810h+var_7C8], rax
0x18001783c  lea     rdx, PLA_EVENT_ERROR
0x180017843  mov     [rsp+810h+var_7D0], 4
0x18001784c  lea     rax, [rsp+810h+var_798]
0x180017851  mov     [rsp+810h+var_7D8], rax
0x180017856  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001785d  mov     [rsp+810h+var_7E0], 1
0x180017866  mov     [rsp+810h+var_7E8], rbx
0x18001786b  mov     [rsp+810h+var_7F0], 4
0x180017874  call    EventingWriteEvent
0x180017879  jmp     loc_1800176BF
0x18001787e  mov     rax, cs:qword_180169748
0x180017885  and     rax, rdx
0x180017888  cmp     cs:qword_180169748, rax
0x18001788f  jnz     loc_18001776C
0x180017895  lea     rcx, [rbp+710h+var_350]; unsigned __int16 *
0x18001789c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800178a1  lea     rcx, [rbp+710h+var_350]
0x1800178a8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800178af  nop
0x1800178b0  cmp     [rcx+rax*2+2], r12w
0x1800178b6  lea     rax, [rax+1]
0x1800178ba  jnz     short loc_1800178B0
0x1800178bc  lea     ecx, [rax+rax]
0x1800178bf  lea     rax, [rbp+710h+var_350]
0x1800178c6  jmp     short loc_180017906
0x1800178c8  mov     rax, cs:qword_180169748
0x1800178cf  and     rax, rdx
0x1800178d2  cmp     cs:qword_180169748, rax
0x1800178d9  jnz     loc_18001776C
0x1800178df  lea     rcx, [rbp+710h+var_6D0]; unsigned __int16 *
0x1800178e3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800178e8  lea     rcx, [rbp+710h+var_6D0]
0x1800178ec  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800178f3  cmp     [rcx+rax*2+2], r12w
0x1800178f9  lea     rax, [rax+1]
0x1800178fd  jnz     short loc_1800178F3
0x1800178ff  lea     ecx, [rax+rax]
0x180017902  lea     rax, [rbp+710h+var_6D0]
0x180017906  add     rcx, 2
0x18001790a  lea     r9, [rsp+810h+var_798]
0x18001790f  mov     [rsp+810h+var_7B0], rcx
0x180017914  lea     rdx, PLA_EVENT_ERROR
0x18001791b  mov     [rsp+810h+var_7B8], rax
0x180017920  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180017927  mov     [rsp+810h+var_7C0], 13h
0x180017930  lea     rax, aPlaireadxmlele; "PlaiReadXmlElement"
0x180017937  mov     [rsp+810h+var_7C8], rax
0x18001793c  mov     r8d, 5
0x180017942  mov     [rsp+810h+var_7D0], 4
0x18001794b  lea     rax, [rsp+810h+var_7A0]
0x180017950  mov     [rsp+810h+var_7D8], rax
0x180017955  mov     [rsp+810h+var_7E0], 1
0x18001795e  mov     [rsp+810h+var_7E8], rbx
0x180017963  mov     [rsp+810h+var_7F0], 4
0x18001796c  call    EventingWriteEvent
0x180017971  jmp     loc_18001776C
0x180017976  mov     rax, cs:qword_180169748
0x18001797d  and     rax, rdx
0x180017980  cmp     cs:qword_180169748, rax
0x180017987  jnz     loc_1800177B6
0x18001798d  lea     rcx, [rbp+710h+var_D0]; unsigned __int16 *
0x180017994  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180017999  lea     rcx, [rbp+710h+var_D0]
0x1800179a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800179a7  nop     word ptr [rax+rax+00000000h]
0x1800179b0  cmp     [rcx+rax*2+2], r12w
0x1800179b6  lea     rax, [rax+1]
0x1800179ba  jnz     short loc_1800179B0
0x1800179bc  lea     ecx, [rax+rax]
0x1800179bf  lea     rax, [rbp+710h+var_D0]
0x1800179c6  lea     rbx, byte_180147320
0x1800179cd  jmp     loc_180017906
0x1800179d2  mov     rax, cs:qword_180169748
0x1800179d9  and     rax, rdx
0x1800179dc  cmp     cs:qword_180169748, rax
0x1800179e3  jnz     loc_180017680
0x1800179e9  mov     [rsp+810h+var_7D0], r15
0x1800179ee  lea     rax, [rsp+810h+var_798]
0x1800179f3  mov     [rsp+810h+var_7D8], rax
0x1800179f8  lea     rdx, PLA_EVENT_FREE_STRING
0x1800179ff  lea     rax, [rsp+810h+var_7A0]
0x180017a04  mov     [rsp+810h+var_7E0], 4
0x180017a0d  mov     [rsp+810h+var_7E8], rax
0x180017a12  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180017a19  mov     r9, rbx
0x180017a1c  mov     [rsp+810h+var_7F0], 1
0x180017a25  mov     r8d, 3
0x180017a2b  call    EventingWriteEvent
0x180017a30  jmp     loc_180017680
0x180017a35  mov     rax, cs:qword_180169748
0x180017a3c  and     rax, rdx
0x180017a3f  cmp     cs:qword_180169748, rax
0x180017a46  jnz     loc_18001776C
0x180017a4c  lea     rcx, [rbp+710h+var_650]; unsigned __int16 *
0x180017a53  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180017a58  lea     rcx, [rbp+710h+var_650]
0x180017a5f  mov     rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
