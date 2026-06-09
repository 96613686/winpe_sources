# HConfigurationDataCollector::QueryManagement(IXMLDOMElement *)

- ea: `0x18008b99c`
- end: `0x18008c6b7`
- name: `?QueryManagement@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@@Z`
- size: `3355`
- prototype: `__int64 __fastcall(HConfigurationDataCollector *__hidden this, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180135d78`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x180018420`
- `0x1800198b0`
- `0x18001b4fc`
- `0x18001cbe0`
- `0x18002b3a0`
- `0x18006c908`
- `0x18008b99c`
- `0x18009cadc`
- `0x1800b6a74`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008c33e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008c33e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008c21d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008c21d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008c611`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008c611`

## string_xrefs

- `0x18008baa7`: `HConfigurationDataCollector::QueryManagement`
- `0x18008bbae`: `HConfigurationDataCollector::QueryManagement`
- `0x18008bcae`: `HConfigurationDataCollector::QueryManagement`
- `0x18008c599`: `HConfigurationDataCollector::QueryManagement`
- `0x18008bf3d`: `managementObjectsRelativePath`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::QueryManagement(
        HConfigurationDataCollector *this,
        struct IXMLDOMElement *a2)
{
  struct IXMLDOMElement *v4; // r12
  struct IXMLDOMElement *v5; // r15
  const unsigned __int16 *v6; // r9
  unsigned __int16 *v7; // r13
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  const char *v16; // rdx
  int v17; // r8d
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  HRESULT v33; // eax
  __int64 v34; // rax
  unsigned int i; // edi
  _WORD *v36; // rcx
  int v37; // eax
  int v38; // eax
  unsigned int Wbem; // eax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v51; // [rsp+88h] [rbp-78h] BYREF
  struct IXMLDOMElement *v52; // [rsp+90h] [rbp-70h] BYREF
  struct IXMLDOMElement *v53; // [rsp+98h] [rbp-68h] BYREF
  struct IXMLDOMElement *v54; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-58h]
  struct IXMLDOMElement *v56; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v57[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v58[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v59[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v60[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v61[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v62[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v63[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v64[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v65[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v66[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v67[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v68[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v69[64]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v70[64]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v71[64]; // [rsp+7C0h] [rbp+6C0h] BYREF
  unsigned __int16 v72[64]; // [rsp+840h] [rbp+740h] BYREF
  unsigned __int16 v73[64]; // [rsp+8C0h] [rbp+7C0h] BYREF

  ppvData = 0;
  v56 = 0;
  v54 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v4 = 0;
  bstrString = 0;
  v5 = 0;
  v7 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v47);
  if ( !v7 )
  {
    v8 = -2147024882;
    v49 = -2147024882;
    v48 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v57, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v57[v9] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v49,
        4,
        qword_180147320,
        1,
        &v48,
        4,
        "HConfigurationDataCollector::QueryManagement",
        45);
    }
    goto LABEL_132;
  }
  v10 = PlaiCreateReportTable(*((struct IXMLDOMDocument **)this + 32), a2, L"managementObjects", v6, 0, &v56, &v54);
  v8 = v10;
  if ( v10 < 0 )
  {
    v49 = 0;
    v48 = v10;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v58[v11] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v48,
        4,
        qword_180147320,
        1,
        &v49,
        4,
        "HConfigurationDataCollector::QueryManagement",
        45);
    }
    v4 = v54;
    goto LABEL_132;
  }
  v4 = v54;
  v12 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v54, L"managementObjectsQuery", L"string");
  v8 = v12;
  if ( v12 < 0 )
  {
    v49 = 0;
    v48 = v12;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v59, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v59[v13] );
    goto LABEL_22;
  }
  v14 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v4, L"managementObjectsResult", L"number");
  v8 = v14;
  if ( v14 < 0 )
  {
    v49 = 0;
    v48 = v14;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v60, 0x4000000000000800uLL);
    v15 = -1;
    do
      ++v15;
    while ( v60[v15] );
    goto LABEL_22;
  }
  PlaiFreeString(0);
  bstrString = PlaiAllocStringEx(L"Header", v16, v17);
  if ( !bstrString )
  {
    v8 = -2147024882;
    v48 = -2147024882;
    v49 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v61[v18] );
    goto LABEL_22;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, BSTR, struct IXMLDOMElement **))(**((_QWORD **)this + 32) + 376LL))(
          *((_QWORD *)this + 32),
          bstrString,
          &v51);
  v8 = v19;
  if ( v19 < 0 )
  {
    v49 = 0;
    v48 = v19;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v62, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v62[v20] );
    goto LABEL_22;
  }
  v21 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v4->lpVtbl->appendChild)(
          v4,
          v51,
          0);
  v8 = v21;
  if ( v21 < 0 )
  {
    v49 = 0;
    v48 = v21;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v63, 0x4000000000000800uLL);
    v22 = -1;
    do
      ++v22;
    while ( v63[v22] );
    goto LABEL_22;
  }
  v23 = PlaiAddDataToReportHeader(
          *((struct IXMLDOMDocument **)this + 32),
          v51,
          L"managementObjectsRelativePath",
          L"string");
  v8 = v23;
  if ( v23 < 0 )
  {
    v49 = 0;
    v48 = v23;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v64, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v64[v24] );
    goto LABEL_22;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD, BSTR, struct IXMLDOMElement **))(**((_QWORD **)this + 32) + 376LL))(
          *((_QWORD *)this + 32),
          bstrString,
          &v52);
  v8 = v25;
  if ( v25 < 0 )
  {
    v49 = 0;
    v48 = v25;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v65, 0x4000000000000800uLL);
    v26 = -1;
    do
      ++v26;
    while ( v65[v26] );
    goto LABEL_22;
  }
  v27 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v51->lpVtbl->appendChild)(
          v51,
          v52,
          0);
  v8 = v27;
  if ( v27 < 0 )
  {
    v49 = 0;
    v48 = v27;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v66, 0x4000000000000800uLL);
    v28 = -1;
    do
      ++v28;
    while ( v66[v28] );
    goto LABEL_22;
  }
  v29 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v52, L"managementObjectsProperty", L"string");
  v8 = v29;
  if ( v29 < 0 )
  {
    v49 = 0;
    v48 = v29;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v67, 0x4000000000000800uLL);
    v30 = -1;
    do
      ++v30;
    while ( v67[v30] );
    goto LABEL_22;
  }
  v31 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v52, L"managementObjectsValue", L"string");
  v8 = v31;
  if ( v31 < 0 )
  {
    v49 = 0;
    v48 = v31;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v68, 0x4000000000000800uLL);
    v32 = -1;
    do
      ++v32;
    while ( v68[v32] );
    goto LABEL_22;
  }
  v33 = SafeArrayAccessData(*((SAFEARRAY **)this + 26), &ppvData);
  v8 = v33;
  if ( v33 < 0 )
  {
    v49 = 0;
    v48 = v33;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_132;
    }
    PlaiWhoAmI(v69, 0x4000000000000800uLL);
    v34 = -1;
    do
      ++v34;
    while ( v69[v34] );
LABEL_22:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v48,
      4,
      qword_180147320,
      1,
      &v49,
      4,
      "HConfigurationDataCollector::QueryManagement",
      45);
    goto LABEL_132;
  }
  for ( i = 0; i < *(_DWORD *)(*((_QWORD *)this + 26) + 24LL); ++i )
  {
    v36 = (_WORD *)*((_QWORD *)ppvData + i);
    if ( v36 && *v36 )
    {
      if ( v5 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
        v53 = 0;
      }
      v37 = PlaiAddItemToReport(*((struct IXMLDOMDocument **)this + 32), v56, &v53);
      v8 = v37;
      if ( v37 < 0 )
      {
        v48 = v37;
        v49 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v73, 0x4000000000000800uLL);
          v45 = -1;
          do
            ++v45;
          while ( v73[v45] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v48,
            4,
            qword_180147320,
            1,
            &v49,
            4,
            "HConfigurationDataCollector::QueryManagement",
            45);
        }
        v5 = v53;
        break;
      }
      v5 = v53;
      v38 = PlaiAddDataToReportItem(
              *((struct IXMLDOMDocument **)this + 32),
              v53,
              L"managementObjectsQuery",
              *((const unsigned __int16 **)ppvData + i));
      v8 = v38;
      if ( v38 < 0 )
      {
        v48 = v38;
        v49 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v72, 0x4000000000000800uLL);
          v44 = -1;
          do
            ++v44;
          while ( v72[v44] );
          goto LABEL_22;
        }
        break;
      }
      if ( WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 16LL), 0) == 258 )
        Wbem = HConfigurationDataCollector::QueryWbem(this, v5, *((unsigned __int16 **)ppvData + i));
      else
        Wbem = PlaiHResultFromWin32(0x4D3u);
      v40 = StringCchPrintfW(v7, 0x400u, L"0x%x", Wbem);
      v8 = v40;
      if ( v40 < 0 )
      {
        v49 = 0;
        v48 = v40;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v71, 0x4000000000000800uLL);
          v43 = -1;
          do
            ++v43;
          while ( v71[v43] );
          goto LABEL_22;
        }
        break;
      }
      v41 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)this + 32), v5, L"managementObjectsResult", v7);
      v8 = v41;
      if ( v41 < 0 )
      {
        v49 = 0;
        v48 = v41;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v70, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v70[v42] );
          goto LABEL_22;
        }
        break;
      }
    }
  }
LABEL_132:
  PlaiFreeString(bstrString);
  if ( v7 )
    PlaiFree(v7, 1);
  if ( ppvData )
  {
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 26));
    ppvData = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v51 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v51->lpVtbl->Release)(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v52->lpVtbl->Release)(v52);
    v52 = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v56 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v56->lpVtbl->Release)(v56);
  return v8;
}

```

## disassembly

```asm
0x18008b99c  mov     [rsp-8+arg_10], rbx
0x18008b9a1  push    rbp
0x18008b9a2  push    rsi
0x18008b9a3  push    rdi
0x18008b9a4  push    r12
0x18008b9a6  push    r13
0x18008b9a8  push    r14
0x18008b9aa  push    r15
0x18008b9ac  lea     rbp, [rsp-850h]
0x18008b9b4  sub     rsp, 950h
0x18008b9bb  mov     rax, cs:__security_cookie
0x18008b9c2  xor     rax, rsp
0x18008b9c5  mov     [rbp+880h+var_40], rax
0x18008b9cc  xor     esi, esi
0x18008b9ce  lea     rdi, qword_180147320
0x18008b9d5  mov     rbx, rdx
0x18008b9d8  mov     [rbp+880h+ppvData], rsi
0x18008b9dc  mov     r14, rcx
0x18008b9df  mov     [rbp+880h+var_8D0], rsi
0x18008b9e3  mov     r9, rdi; char *
0x18008b9e6  mov     [rbp+880h+var_8E0], rsi
0x18008b9ea  lea     edx, [rsi+1]; int
0x18008b9ed  mov     [rbp+880h+var_8F8], rsi
0x18008b9f1  xor     r8d, r8d; int
0x18008b9f4  mov     [rbp+880h+var_8F0], rsi
0x18008b9f8  mov     ecx, 800h; dwBytes
0x18008b9fd  mov     [rbp+880h+var_8E8], rsi
0x18008ba01  mov     r12d, esi
0x18008ba04  mov     [rbp+880h+bstrString], rsi
0x18008ba08  mov     r15d, esi
0x18008ba0b  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18008ba10  mov     r13, rax
0x18008ba13  test    rax, rax
0x18008ba16  jnz     loc_18008BAF3
0x18008ba1c  cmp     dword ptr cs:xmmword_180169738, esi
0x18008ba22  mov     eax, 8007000Eh
0x18008ba27  mov     ebx, eax
0x18008ba29  mov     [rsp+980h+var_908], eax
0x18008ba2d  mov     [rsp+980h+var_910], esi
0x18008ba31  jz      loc_18008C5E9
0x18008ba37  mov     rdx, 4000000000000800h; unsigned __int64
0x18008ba41  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008ba48  jz      loc_18008C5E9
0x18008ba4e  mov     rax, cs:qword_180169748
0x18008ba55  and     rax, rdx
0x18008ba58  cmp     cs:qword_180169748, rax
0x18008ba5f  jnz     loc_18008C5E9
0x18008ba65  lea     rcx, [rbp+880h+var_8C0]; unsigned __int16 *
0x18008ba69  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008ba6e  lea     rcx, [rbp+880h+var_8C0]
0x18008ba72  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ba76  inc     rax
0x18008ba79  cmp     [rcx+rax*2], si
0x18008ba7d  jnz     short loc_18008BA76
0x18008ba7f  lea     ecx, [rax+rax]
0x18008ba82  add     rcx, 2
0x18008ba86  lea     rax, [rbp+880h+var_8C0]
0x18008ba8a  mov     [rsp+980h+var_920], rcx
0x18008ba8f  lea     r9, [rsp+980h+var_908]
0x18008ba94  mov     [rsp+980h+var_928], rax
0x18008ba99  lea     rcx, [rsp+980h+var_910]
0x18008ba9e  mov     [rsp+980h+var_930], 2Dh ; '-'
0x18008baa7  lea     rax, aHconfiguration_8; "HConfigurationDataCollector::QueryManag"...
0x18008baae  mov     [rsp+980h+var_938], rax
0x18008bab3  mov     eax, 4
0x18008bab8  mov     [rsp+980h+var_940], rax
0x18008babd  mov     [rsp+980h+var_948], rcx
0x18008bac2  mov     [rsp+980h+var_950], 1
0x18008bacb  mov     [rsp+980h+var_958], rdi
0x18008bad0  mov     r8d, 5
0x18008bad6  mov     [rsp+980h+var_960], rax
0x18008badb  lea     rdx, PLA_EVENT_ERROR
0x18008bae2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008bae9  call    EventingWriteEvent
0x18008baee  jmp     loc_18008C5E9
0x18008baf3  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18008bafa  lea     rax, [rbp+880h+var_8E0]
0x18008bafe  mov     [rsp+980h+var_950], rax; struct IXMLDOMElement **
0x18008bb03  lea     r8, aManagementobje_0; "managementObjects"
0x18008bb0a  lea     rax, [rbp+880h+var_8D0]
0x18008bb0e  mov     rdx, rbx; struct IXMLDOMElement *
0x18008bb11  mov     [rsp+980h+var_958], rax; struct IXMLDOMElement **
0x18008bb16  mov     [rsp+980h+var_960], rsi; unsigned __int16 *
0x18008bb1b  call    ?PlaiCreateReportTable@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG22PEAPEAU2@3@Z; PlaiCreateReportTable(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *,IXMLDOMElement * *)
0x18008bb20  mov     ebx, eax
0x18008bb22  test    eax, eax
0x18008bb24  jns     loc_18008BBFC
0x18008bb2a  cmp     dword ptr cs:xmmword_180169738, esi
0x18008bb30  mov     [rsp+980h+var_908], esi
0x18008bb34  mov     [rsp+980h+var_910], eax
0x18008bb38  jz      loc_18008BBF3
0x18008bb3e  mov     rdx, 4000000000000800h; unsigned __int64
0x18008bb48  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008bb4f  jz      loc_18008BBF3
0x18008bb55  mov     rax, cs:qword_180169748
0x18008bb5c  and     rax, rdx
0x18008bb5f  cmp     cs:qword_180169748, rax
0x18008bb66  jnz     loc_18008BBF3
0x18008bb6c  lea     rcx, [rbp+880h+var_840]; unsigned __int16 *
0x18008bb70  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008bb75  lea     rcx, [rbp+880h+var_840]
0x18008bb79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008bb7d  inc     rax
0x18008bb80  cmp     [rcx+rax*2], si
0x18008bb84  jnz     short loc_18008BB7D
0x18008bb86  lea     ecx, [rax+rax]
0x18008bb89  add     rcx, 2
0x18008bb8d  lea     rax, [rbp+880h+var_840]
0x18008bb91  mov     [rsp+980h+var_920], rcx
0x18008bb96  lea     r9, [rsp+980h+var_910]
0x18008bb9b  mov     [rsp+980h+var_928], rax
0x18008bba0  lea     rcx, [rsp+980h+var_908]
0x18008bba5  mov     [rsp+980h+var_930], 2Dh ; '-'
0x18008bbae  lea     rax, aHconfiguration_8; "HConfigurationDataCollector::QueryManag"...
0x18008bbb5  mov     [rsp+980h+var_938], rax
0x18008bbba  lea     rdx, PLA_EVENT_ERROR
0x18008bbc1  mov     eax, 4
0x18008bbc6  mov     [rsp+980h+var_940], rax
0x18008bbcb  mov     [rsp+980h+var_948], rcx
0x18008bbd0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008bbd7  mov     [rsp+980h+var_950], 1
0x18008bbe0  mov     [rsp+980h+var_958], rdi
0x18008bbe5  lea     r8d, [rax+1]
0x18008bbe9  mov     [rsp+980h+var_960], rax
0x18008bbee  call    EventingWriteEvent
0x18008bbf3  mov     r12, [rbp+880h+var_8E0]
0x18008bbf7  jmp     loc_18008C5E9
0x18008bbfc  mov     r12, [rbp+880h+var_8E0]
0x18008bc00  lea     rdi, aString; "string"
0x18008bc07  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18008bc0e  lea     r8, aManagementobje; "managementObjectsQuery"
0x18008bc15  mov     r9, rdi; unsigned __int16 *
0x18008bc18  mov     rdx, r12; struct IXMLDOMElement *
0x18008bc1b  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18008bc20  mov     ebx, eax
0x18008bc22  test    eax, eax
0x18008bc24  jns     loc_18008BCEC
0x18008bc2a  cmp     dword ptr cs:xmmword_180169738, esi
0x18008bc30  mov     [rsp+980h+var_908], esi
0x18008bc34  mov     [rsp+980h+var_910], eax
0x18008bc38  jz      loc_18008C5E9
0x18008bc3e  mov     rdx, 4000000000000800h; unsigned __int64
0x18008bc48  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008bc4f  jz      loc_18008C5E9
0x18008bc55  mov     rax, cs:qword_180169748
0x18008bc5c  and     rax, rdx
0x18008bc5f  cmp     cs:qword_180169748, rax
0x18008bc66  jnz     loc_18008C5E9
0x18008bc6c  lea     rcx, [rbp+880h+var_7C0]; unsigned __int16 *
0x18008bc73  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008bc78  lea     rcx, [rbp+880h+var_7C0]
0x18008bc7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008bc83  inc     rax
0x18008bc86  cmp     [rcx+rax*2], si
0x18008bc8a  jnz     short loc_18008BC83
0x18008bc8c  lea     ecx, [rax+rax]
0x18008bc8f  lea     rax, [rbp+880h+var_7C0]
0x18008bc96  add     rcx, 2
0x18008bc9a  lea     r9, [rsp+980h+var_910]
0x18008bc9f  mov     [rsp+980h+var_920], rcx
0x18008bca4  lea     rcx, [rsp+980h+var_908]
0x18008bca9  mov     [rsp+980h+var_928], rax
0x18008bcae  lea     rax, aHconfiguration_8; "HConfigurationDataCollector::QueryManag"...
0x18008bcb5  mov     [rsp+980h+var_930], 2Dh ; '-'
0x18008bcbe  mov     [rsp+980h+var_938], rax
0x18008bcc3  mov     eax, 4
0x18008bcc8  mov     [rsp+980h+var_940], rax
0x18008bccd  mov     [rsp+980h+var_948], rcx
0x18008bcd2  lea     rcx, qword_180147320
0x18008bcd9  mov     [rsp+980h+var_950], 1
0x18008bce2  mov     [rsp+980h+var_958], rcx
0x18008bce7  jmp     loc_18008BAD0
0x18008bcec  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18008bcf3  lea     r9, aNumber; "number"
0x18008bcfa  lea     r8, aManagementobje_1; "managementObjectsResult"
0x18008bd01  mov     rdx, r12; struct IXMLDOMElement *
0x18008bd04  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18008bd09  mov     ebx, eax
0x18008bd0b  test    eax, eax
0x18008bd0d  jns     short loc_18008BD80
0x18008bd0f  cmp     dword ptr cs:xmmword_180169738, esi
0x18008bd15  mov     [rsp+980h+var_908], esi
0x18008bd19  mov     [rsp+980h+var_910], eax
0x18008bd1d  jz      loc_18008C5E9
0x18008bd23  mov     rdx, 4000000000000800h; unsigned __int64
0x18008bd2d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008bd34  jz      loc_18008C5E9
0x18008bd3a  mov     rax, cs:qword_180169748
0x18008bd41  and     rax, rdx
0x18008bd44  cmp     cs:qword_180169748, rax
0x18008bd4b  jnz     loc_18008C5E9
0x18008bd51  lea     rcx, [rbp+880h+var_740]; unsigned __int16 *
0x18008bd58  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008bd5d  lea     rcx, [rbp+880h+var_740]
0x18008bd64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008bd68  inc     rax
0x18008bd6b  cmp     [rcx+rax*2], si
0x18008bd6f  jnz     short loc_18008BD68
0x18008bd71  lea     ecx, [rax+rax]
0x18008bd74  lea     rax, [rbp+880h+var_740]
0x18008bd7b  jmp     loc_18008BC96
0x18008bd80  xor     ecx, ecx; bstrString
0x18008bd82  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18008bd87  lea     rcx, aHeader; "Header"
0x18008bd8e  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18008bd93  mov     [rbp+880h+bstrString], rax
0x18008bd97  mov     rdx, rax
0x18008bd9a  test    rax, rax
0x18008bd9d  jnz     short loc_18008BE17
0x18008bd9f  cmp     dword ptr cs:xmmword_180169738, esi
0x18008bda5  mov     eax, 8007000Eh
0x18008bdaa  mov     ebx, eax
0x18008bdac  mov     [rsp+980h+var_910], eax
0x18008bdb0  mov     [rsp+980h+var_908], esi
0x18008bdb4  jz      loc_18008C5E9
0x18008bdba  mov     rdx, 4000000000000800h; unsigned __int64
0x18008bdc4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008bdcb  jz      loc_18008C5E9
0x18008bdd1  mov     rax, cs:qword_180169748
0x18008bdd8  and     rax, rdx
0x18008bddb  cmp     cs:qword_180169748, rax
0x18008bde2  jnz     loc_18008C5E9
0x18008bde8  lea     rcx, [rbp+880h+var_6C0]; unsigned __int16 *
0x18008bdef  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008bdf4  lea     rcx, [rbp+880h+var_6C0]
0x18008bdfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008bdff  inc     rax
0x18008be02  cmp     [rcx+rax*2], si
0x18008be06  jnz     short loc_18008BDFF
0x18008be08  lea     ecx, [rax+rax]
0x18008be0b  lea     rax, [rbp+880h+var_6C0]
0x18008be12  jmp     loc_18008BC96
0x18008be17  mov     rcx, [r14+100h]
0x18008be1e  lea     r8, [rbp+880h+var_8F8]
0x18008be22  mov     rax, [rcx]
0x18008be25  mov     rax, [rax+178h]
0x18008be2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008be31  mov     ebx, eax
0x18008be33  test    eax, eax
0x18008be35  jns     short loc_18008BEA8
0x18008be37  cmp     dword ptr cs:xmmword_180169738, esi
0x18008be3d  mov     [rsp+980h+var_908], esi
0x18008be41  mov     [rsp+980h+var_910], eax
0x18008be45  jz      loc_18008C5E9
0x18008be4b  mov     rdx, 4000000000000800h; unsigned __int64
0x18008be55  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008be5c  jz      loc_18008C5E9
0x18008be62  mov     rax, cs:qword_180169748
0x18008be69  and     rax, rdx
0x18008be6c  cmp     cs:qword_180169748, rax
0x18008be73  jnz     loc_18008C5E9
0x18008be79  lea     rcx, [rbp+880h+var_640]; unsigned __int16 *
0x18008be80  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008be85  lea     rcx, [rbp+880h+var_640]
0x18008be8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008be90  inc     rax
0x18008be93  cmp     [rcx+rax*2], si
0x18008be97  jnz     short loc_18008BE90
0x18008be99  lea     ecx, [rax+rax]
0x18008be9c  lea     rax, [rbp+880h+var_640]
0x18008bea3  jmp     loc_18008BC96
0x18008bea8  mov     rax, [r12]
0x18008beac  xor     r8d, r8d
0x18008beaf  mov     rdx, [rbp+880h+var_8F8]
0x18008beb3  mov     rcx, r12
0x18008beb6  mov     rax, [rax+0A8h]
0x18008bebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bec2  mov     ebx, eax
0x18008bec4  test    eax, eax
0x18008bec6  jns     short loc_18008BF39
0x18008bec8  cmp     dword ptr cs:xmmword_180169738, esi
0x18008bece  mov     [rsp+980h+var_908], esi
0x18008bed2  mov     [rsp+980h+var_910], eax
0x18008bed6  jz      loc_18008C5E9
0x18008bedc  mov     rdx, 4000000000000800h; unsigned __int64
0x18008bee6  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008beed  jz      loc_18008C5E9
0x18008bef3  mov     rax, cs:qword_180169748
0x18008befa  and     rax, rdx
0x18008befd  cmp     cs:qword_180169748, rax
0x18008bf04  jnz     loc_18008C5E9
0x18008bf0a  lea     rcx, [rbp+880h+var_5C0]; unsigned __int16 *
0x18008bf11  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008bf16  lea     rcx, [rbp+880h+var_5C0]
0x18008bf1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008bf21  inc     rax
0x18008bf24  cmp     [rcx+rax*2], si
0x18008bf28  jnz     short loc_18008BF21
0x18008bf2a  lea     ecx, [rax+rax]
0x18008bf2d  lea     rax, [rbp+880h+var_5C0]
0x18008bf34  jmp     loc_18008BC96
0x18008bf39  mov     rdx, [rbp+880h+var_8F8]; struct IXMLDOMElement *
0x18008bf3d  lea     r8, aManagementobje_4; "managementObjectsRelativePath"
0x18008bf44  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18008bf4b  mov     r9, rdi; unsigned __int16 *
0x18008bf4e  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18008bf53  mov     ebx, eax
0x18008bf55  test    eax, eax
0x18008bf57  jns     short loc_18008BFCA
0x18008bf59  cmp     dword ptr cs:xmmword_180169738, esi
  ... truncated ...
```
