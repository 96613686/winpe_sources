# HConfigurationDataCollector::QueryFiles(IXMLDOMElement *)

- ea: `0x1800e8f0c`
- end: `0x1800e9ce7`
- name: `?QueryFiles@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@@Z`
- size: `3547`
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
- `0x18009cadc`
- `0x1800b6a74`
- `0x1800e8f0c`
- `0x1801032d8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e9931`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e9931`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e9831`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e9831`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e9cb5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e9cb5`

## string_xrefs

- `0x1800e9030`: `HConfigurationDataCollector::QueryFiles`
- `0x1800e913f`: `HConfigurationDataCollector::QueryFiles`
- `0x1800e9397`: `HConfigurationDataCollector::QueryFiles`
- `0x1800e9b57`: `HConfigurationDataCollector::QueryFiles`
- `0x1800e9507`: `configurationFilesFrom`
- `0x1800e9598`: `configurationFilesTo`
- `0x1800e9637`: `configurationFilesCopyResult`
- `0x1800e908a`: `configurationFiles`
- `0x1800e919f`: `configurationFilesQuery`
- `0x1800e98fe`: `configurationFilesQuery`
- `0x1800e9250`: `configurationFilesOpenResult`
- `0x1800e99b8`: `configurationFilesOpenResult`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::QueryFiles(
        HConfigurationDataCollector *this,
        struct IXMLDOMElement *a2)
{
  int v2; // r15d
  struct IXMLDOMElement *v5; // rsi
  struct IXMLDOMElement *v6; // r12
  struct IXMLDOMElement *v7; // r14
  const unsigned __int16 *v8; // r9
  unsigned int v9; // edi
  __int64 v10; // rbx
  int *v11; // r9
  int *v12; // rcx
  int v13; // eax
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rbx
  const char *v19; // rdx
  int v20; // r8d
  __int64 v21; // rbx
  int v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rbx
  int v32; // eax
  __int64 v33; // rbx
  int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rbx
  __int64 v37; // rax
  OLECHAR *i; // rcx
  int v39; // eax
  bool v40; // zf
  SAFEARRAY *v41; // rcx
  HRESULT v42; // eax
  _WORD *v43; // rcx
  int v44; // eax
  int v45; // eax
  unsigned int v46; // eax
  unsigned int *v47; // rcx
  int v48; // eax
  int v49; // eax
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMElement *v54; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v55; // [rsp+88h] [rbp-78h] BYREF
  int v56; // [rsp+90h] [rbp-70h] BYREF
  struct IXMLDOMElement *v57; // [rsp+98h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v59; // [rsp+A8h] [rbp-58h] BYREF
  void *ppvData; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v62; // [rsp+C0h] [rbp-40h] BYREF
  LPCVOID lpMem; // [rsp+C8h] [rbp-38h]
  struct IXMLDOMElement *v64; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v65[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v66[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v67[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v68[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v69[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v70[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v71[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v72[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v73[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v74[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v75[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v76[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v77[64]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v78[64]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v79[64]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned __int16 v80[64]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v81[64]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v2 = 0;
  v61 = 0;
  v64 = 0;
  ppvData = 0;
  bstrString = 0;
  v54 = 0;
  v5 = 0;
  v57 = 0;
  v6 = 0;
  v55 = 0;
  v7 = 0;
  v59 = 0;
  v56 = 0;
  v62 = 0;
  lpMem = PlaiAlloc(0x800u, 1, 0, byte_180147320, v51);
  if ( !lpMem )
  {
    v9 = -2147024882;
    v53 = -2147024882;
    v52 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_139;
    }
    PlaiWhoAmI(v65, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v65[v10] );
    v11 = &v53;
    v12 = &v52;
LABEL_8:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
    goto LABEL_139;
  }
  v13 = PlaiCreateReportTable(*((struct IXMLDOMDocument **)this + 32), a2, L"configurationFiles", v8, 0, &v64, &v54);
  v9 = v13;
  if ( v13 < 0 )
  {
    v53 = 0;
    v52 = v13;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v66, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v66[v14] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v52, 4, byte_180147320, 1, &v53, 4);
    }
    v6 = v54;
    goto LABEL_139;
  }
  v6 = v54;
  v15 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v54, L"configurationFilesQuery", L"string");
  v9 = v15;
  if ( v15 < 0 )
  {
    v53 = 0;
    v52 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_139;
    }
    PlaiWhoAmI(v67, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v67[v16] );
LABEL_23:
    v11 = &v52;
    v12 = &v53;
    goto LABEL_8;
  }
  v17 = PlaiAddDataToReportHeader(
          *((struct IXMLDOMDocument **)this + 32),
          v6,
          L"configurationFilesOpenResult",
          L"number");
  v9 = v17;
  if ( v17 < 0 )
  {
    v53 = 0;
    v52 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_139;
    }
    PlaiWhoAmI(v68, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v68[v18] );
    goto LABEL_23;
  }
  PlaiFreeString(0);
  v54 = (struct IXMLDOMElement *)PlaiAllocStringEx(L"Header", v19, v20);
  if ( !v54 )
  {
    v9 = -2147024882;
    v52 = -2147024882;
    v53 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v69, 0x4000000000000800uLL);
      v21 = -1;
      do
        ++v21;
      while ( v69[v21] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, struct IXMLDOMElement **))(**((_QWORD **)this + 32)
                                                                                             + 376LL))(
          *((_QWORD *)this + 32),
          v54,
          &v57);
  v9 = v22;
  if ( v22 < 0 )
  {
    v53 = 0;
    v52 = v22;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v70, 0x4000000000000800uLL);
      v23 = -1;
      do
        ++v23;
      while ( v70[v23] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v24 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v6->lpVtbl->appendChild)(
          v6,
          v57,
          0);
  v9 = v24;
  if ( v24 < 0 )
  {
    v53 = 0;
    v52 = v24;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v71, 0x4000000000000800uLL);
      v25 = -1;
      do
        ++v25;
      while ( v71[v25] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v26 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v57, L"configurationFilesFrom", L"string");
  v9 = v26;
  if ( v26 < 0 )
  {
    v53 = 0;
    v52 = v26;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v72, 0x4000000000000800uLL);
      v27 = -1;
      do
        ++v27;
      while ( v72[v27] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v28 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v57, L"configurationFilesTo", L"string");
  v9 = v28;
  if ( v28 < 0 )
  {
    v53 = 0;
    v52 = v28;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v73, 0x4000000000000800uLL);
      v29 = -1;
      do
        ++v29;
      while ( v73[v29] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v30 = PlaiAddDataToReportHeader(
          *((struct IXMLDOMDocument **)this + 32),
          v57,
          L"configurationFilesCopyResult",
          L"number");
  v9 = v30;
  if ( v30 < 0 )
  {
    v53 = 0;
    v52 = v30;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v74, 0x4000000000000800uLL);
      v31 = -1;
      do
        ++v31;
      while ( v74[v31] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v32 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 31) + 56LL))(*((_QWORD *)this + 31), &v61);
  v9 = v32;
  if ( v32 < 0 )
  {
    v53 = 0;
    v52 = v32;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v75, 0x4000000000000800uLL);
      v33 = -1;
      do
        ++v33;
      while ( v75[v33] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v61 + 144LL))(v61, &bstrString);
  v9 = v34;
  if ( v34 < 0 )
  {
    v53 = 0;
    v52 = v34;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v76, 0x4000000000000800uLL);
      v35 = -1;
      do
        ++v35;
      while ( v76[v35] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  v36 = -1;
  v37 = -1;
  do
    ++v37;
  while ( bstrString[v37] );
  for ( i = &bstrString[v37 - 1]; i >= bstrString; --i )
  {
    if ( *i != 92 )
      break;
    *i = 0;
  }
  v39 = *((_DWORD *)this + 56);
  v40 = *((_DWORD *)this + 54) == 0;
  v59 = *((_DWORD *)this + 54);
  v41 = (SAFEARRAY *)*((_QWORD *)this + 25);
  LOBYTE(v2) = !v40;
  v56 = v39;
  v42 = SafeArrayAccessData(v41, &ppvData);
  v9 = v42;
  if ( v42 < 0 )
  {
    v52 = v42;
    v53 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v77, 0x4000000000000800uLL);
      do
        ++v36;
      while ( v77[v36] );
      goto LABEL_37;
    }
    goto LABEL_138;
  }
  while ( 1 )
  {
    if ( (unsigned int)v5 >= *(_DWORD *)(*((_QWORD *)this + 25) + 24LL) )
      goto LABEL_138;
    v43 = (_WORD *)*((_QWORD *)ppvData + (unsigned int)v5);
    if ( !v43 || !*v43 )
    {
      v7 = v55;
      goto LABEL_118;
    }
    v44 = PlaiAddItemToReport(*((struct IXMLDOMDocument **)this + 32), v64, &v55);
    v9 = v44;
    if ( v44 < 0 )
    {
      v52 = v44;
      v53 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_131;
      }
      PlaiWhoAmI(v81, 0x4000000000000800uLL);
      do
        ++v36;
      while ( v81[v36] );
      goto LABEL_130;
    }
    v45 = PlaiAddDataToReportItem(
            *((struct IXMLDOMDocument **)this + 32),
            v55,
            L"configurationFilesQuery",
            *((const unsigned __int16 **)ppvData + (unsigned int)v5));
    v9 = v45;
    if ( v45 < 0 )
    {
      v52 = v45;
      v53 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_131;
      }
      PlaiWhoAmI(v80, 0x4000000000000800uLL);
      do
        ++v36;
      while ( v80[v36] );
LABEL_130:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v52, 4, byte_180147320, 1, &v53, 4);
LABEL_131:
      v7 = v55;
      goto LABEL_138;
    }
    if ( WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 16LL), 0) == 258 )
    {
      v47 = (unsigned int *)&v56;
      v7 = v55;
      if ( !v56 )
        v47 = 0;
      v46 = HConfigurationDataCollector::QueryFile(
              this,
              v55,
              bstrString,
              *((unsigned __int16 **)ppvData + (unsigned int)v5),
              v2,
              &v59,
              v47,
              &v62);
    }
    else
    {
      v46 = PlaiHResultFromWin32(0x4D3u);
      v7 = v55;
    }
    v48 = StringCchPrintfW((unsigned __int16 *)lpMem, 0x400u, L"0x%x", v46);
    v9 = v48;
    if ( v48 < 0 )
      break;
    v49 = PlaiAddDataToReportItem(
            *((struct IXMLDOMDocument **)this + 32),
            v7,
            L"configurationFilesOpenResult",
            (const unsigned __int16 *)lpMem);
    v9 = v49;
    if ( v49 < 0 )
    {
      v52 = v49;
      v53 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v78, 0x4000000000000800uLL);
        do
          ++v36;
        while ( v78[v36] );
        goto LABEL_37;
      }
      goto LABEL_138;
    }
LABEL_118:
    LODWORD(v5) = (_DWORD)v5 + 1;
  }
  v52 = v48;
  v53 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v79, 0x4000000000000800uLL);
    do
      ++v36;
    while ( v79[v36] );
LABEL_37:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v52, 4, byte_180147320, 1, &v53, 4);
  }
LABEL_138:
  v5 = v54;
LABEL_139:
  PlaiFreeString((BSTR)v5);
  if ( lpMem )
    PlaiFree(lpMem, 1);
  PlaiFreeString(bstrString);
  bstrString = 0;
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v64 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v64->lpVtbl->Release)(v64);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  if ( v57 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v57->lpVtbl->Release)(v57);
    v57 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v7->lpVtbl->Release)(v7);
  if ( ppvData )
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 25));
  return v9;
}

```

## disassembly

```asm
0x1800e8f0c  mov     [rsp-8+arg_10], rbx
0x1800e8f11  push    rbp
0x1800e8f12  push    rsi
0x1800e8f13  push    rdi
0x1800e8f14  push    r12
0x1800e8f16  push    r13
0x1800e8f18  push    r14
0x1800e8f1a  push    r15
0x1800e8f1c  lea     rbp, [rsp-870h]
0x1800e8f24  sub     rsp, 970h
0x1800e8f2b  mov     rax, cs:__security_cookie
0x1800e8f32  xor     rax, rsp
0x1800e8f35  mov     [rbp+8A0h+var_40], rax
0x1800e8f3c  xor     r15d, r15d
0x1800e8f3f  lea     r9, byte_180147320; char *
0x1800e8f46  mov     rbx, rdx
0x1800e8f49  mov     [rbp+8A0h+var_8E8], r15
0x1800e8f4d  mov     r13, rcx
0x1800e8f50  mov     [rbp+8A0h+var_8D0], r15
0x1800e8f54  xor     r8d, r8d; int
0x1800e8f57  mov     [rbp+8A0h+ppvData], r15
0x1800e8f5b  lea     edx, [r15+1]; int
0x1800e8f5f  mov     [rbp+8A0h+bstrString], r15
0x1800e8f63  mov     ecx, 800h; dwBytes
0x1800e8f68  mov     [rbp+8A0h+var_920], r15
0x1800e8f6c  mov     esi, r15d
0x1800e8f6f  mov     [rbp+8A0h+var_908], r15
0x1800e8f73  mov     r12d, r15d
0x1800e8f76  mov     [rbp+8A0h+var_918], r15
0x1800e8f7a  mov     r14d, r15d
0x1800e8f7d  mov     [rbp+8A0h+var_8F8], r15d
0x1800e8f81  mov     [rbp+8A0h+var_910], r15d
0x1800e8f85  mov     [rbp+8A0h+var_8E0], r15d
0x1800e8f89  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800e8f8e  mov     [rbp+8A0h+lpMem], rax
0x1800e8f92  test    rax, rax
0x1800e8f95  jnz     loc_1800E907A
0x1800e8f9b  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e8fa2  mov     eax, 8007000Eh
0x1800e8fa7  mov     edi, eax
0x1800e8fa9  mov     [rsp+9A0h+var_928], eax
0x1800e8fad  mov     [rsp+9A0h+var_930], r15d
0x1800e8fb2  jz      loc_1800E9C0D
0x1800e8fb8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e8fc2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e8fc9  jz      loc_1800E9C0D
0x1800e8fcf  mov     rax, cs:qword_180169748
0x1800e8fd6  and     rax, rdx
0x1800e8fd9  cmp     cs:qword_180169748, rax
0x1800e8fe0  jnz     loc_1800E9C0D
0x1800e8fe6  lea     rcx, [rbp+8A0h+var_8C0]; unsigned __int16 *
0x1800e8fea  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e8fef  lea     rax, [rbp+8A0h+var_8C0]
0x1800e8ff3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e8ff7  inc     rbx
0x1800e8ffa  cmp     [rax+rbx*2], r15w
0x1800e8fff  jnz     short loc_1800E8FF7
0x1800e9001  lea     ecx, [rbx+rbx]
0x1800e9004  add     rcx, 2
0x1800e9008  lea     rax, [rbp+8A0h+var_8C0]
0x1800e900c  mov     [rsp+9A0h+var_940], rcx
0x1800e9011  lea     r9, [rsp+9A0h+var_928]
0x1800e9016  lea     rcx, [rsp+9A0h+var_930]
0x1800e901b  mov     [rsp+9A0h+var_948], rax
0x1800e9020  lea     rdx, PLA_EVENT_ERROR
0x1800e9027  mov     [rsp+9A0h+var_950], 28h ; '('
0x1800e9030  lea     rax, aHconfiguration_4; "HConfigurationDataCollector::QueryFiles"
0x1800e9037  mov     [rsp+9A0h+var_958], rax
0x1800e903c  mov     eax, 4
0x1800e9041  mov     [rsp+9A0h+var_960], rax
0x1800e9046  mov     [rsp+9A0h+var_968], rcx
0x1800e904b  lea     rcx, byte_180147320
0x1800e9052  mov     [rsp+9A0h+var_970], 1
0x1800e905b  mov     [rsp+9A0h+var_978], rcx
0x1800e9060  lea     r8d, [rax+1]
0x1800e9064  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800e906b  mov     [rsp+9A0h+var_980], rax
0x1800e9070  call    EventingWriteEvent
0x1800e9075  jmp     loc_1800E9C0D
0x1800e907a  mov     rcx, [r13+100h]; struct IXMLDOMDocument *
0x1800e9081  lea     rax, [rbp+8A0h+var_920]
0x1800e9085  mov     [rsp+9A0h+var_970], rax; struct IXMLDOMElement **
0x1800e908a  lea     r8, aConfigurationf_3; "configurationFiles"
0x1800e9091  lea     rax, [rbp+8A0h+var_8D0]
0x1800e9095  mov     rdx, rbx; struct IXMLDOMElement *
0x1800e9098  mov     [rsp+9A0h+var_978], rax; struct IXMLDOMElement **
0x1800e909d  mov     [rsp+9A0h+var_980], r15; unsigned __int16 *
0x1800e90a2  call    ?PlaiCreateReportTable@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG22PEAPEAU2@3@Z; PlaiCreateReportTable(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *,IXMLDOMElement * *)
0x1800e90a7  mov     edi, eax
0x1800e90a9  test    eax, eax
0x1800e90ab  jns     loc_1800E918D
0x1800e90b1  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e90b8  mov     [rsp+9A0h+var_928], r15d
0x1800e90bd  mov     [rsp+9A0h+var_930], eax
0x1800e90c1  jz      loc_1800E9184
0x1800e90c7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e90d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e90d8  jz      loc_1800E9184
0x1800e90de  mov     rax, cs:qword_180169748
0x1800e90e5  and     rax, rdx
0x1800e90e8  cmp     cs:qword_180169748, rax
0x1800e90ef  jnz     loc_1800E9184
0x1800e90f5  lea     rcx, [rbp+8A0h+var_840]; unsigned __int16 *
0x1800e90f9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e90fe  lea     rax, [rbp+8A0h+var_840]
0x1800e9102  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e9106  inc     rbx
0x1800e9109  cmp     [rax+rbx*2], r15w
0x1800e910e  jnz     short loc_1800E9106
0x1800e9110  lea     rax, [rbp+8A0h+var_840]
0x1800e9114  lea     ecx, [rbx+rbx]
0x1800e9117  add     rcx, 2
0x1800e911b  lea     r9, [rsp+9A0h+var_930]
0x1800e9120  mov     [rsp+9A0h+var_940], rcx
0x1800e9125  lea     rdx, PLA_EVENT_ERROR
0x1800e912c  mov     [rsp+9A0h+var_948], rax
0x1800e9131  lea     rcx, [rsp+9A0h+var_928]
0x1800e9136  mov     [rsp+9A0h+var_950], 28h ; '('
0x1800e913f  lea     rax, aHconfiguration_4; "HConfigurationDataCollector::QueryFiles"
0x1800e9146  mov     [rsp+9A0h+var_958], rax
0x1800e914b  mov     eax, 4
0x1800e9150  mov     [rsp+9A0h+var_960], rax
0x1800e9155  mov     [rsp+9A0h+var_968], rcx
0x1800e915a  lea     rcx, byte_180147320
0x1800e9161  mov     [rsp+9A0h+var_970], 1
0x1800e916a  mov     [rsp+9A0h+var_978], rcx
0x1800e916f  lea     r8d, [rax+1]
0x1800e9173  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800e917a  mov     [rsp+9A0h+var_980], rax
0x1800e917f  call    EventingWriteEvent
0x1800e9184  mov     r12, [rbp+8A0h+var_920]
0x1800e9188  jmp     loc_1800E9C0D
0x1800e918d  mov     r12, [rbp+8A0h+var_920]
0x1800e9191  lea     rbx, aString; "string"
0x1800e9198  mov     rcx, [r13+100h]; struct IXMLDOMDocument *
0x1800e919f  lea     r8, aConfigurationf_4; "configurationFilesQuery"
0x1800e91a6  mov     r9, rbx; unsigned __int16 *
0x1800e91a9  mov     rdx, r12; struct IXMLDOMElement *
0x1800e91ac  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800e91b1  mov     edi, eax
0x1800e91b3  test    eax, eax
0x1800e91b5  jns     loc_1800E9242
0x1800e91bb  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e91c2  mov     [rsp+9A0h+var_928], r15d
0x1800e91c7  mov     [rsp+9A0h+var_930], eax
0x1800e91cb  jz      loc_1800E9C0D
0x1800e91d1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e91db  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e91e2  jz      loc_1800E9C0D
0x1800e91e8  mov     rax, cs:qword_180169748
0x1800e91ef  and     rax, rdx
0x1800e91f2  cmp     cs:qword_180169748, rax
0x1800e91f9  jnz     loc_1800E9C0D
0x1800e91ff  lea     rcx, [rbp+8A0h+var_7C0]; unsigned __int16 *
0x1800e9206  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e920b  lea     rax, [rbp+8A0h+var_7C0]
0x1800e9212  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e9216  inc     rbx
0x1800e9219  cmp     [rax+rbx*2], r15w
0x1800e921e  jnz     short loc_1800E9216
0x1800e9220  lea     rax, [rbp+8A0h+var_7C0]
0x1800e9227  lea     ecx, [rbx+rbx]
0x1800e922a  add     rcx, 2
0x1800e922e  lea     r9, [rsp+9A0h+var_930]
0x1800e9233  mov     [rsp+9A0h+var_940], rcx
0x1800e9238  lea     rcx, [rsp+9A0h+var_928]
0x1800e923d  jmp     loc_1800E901B
0x1800e9242  mov     rcx, [r13+100h]; struct IXMLDOMDocument *
0x1800e9249  lea     r9, aNumber; "number"
0x1800e9250  lea     r8, aConfigurationf; "configurationFilesOpenResult"
0x1800e9257  mov     rdx, r12; struct IXMLDOMElement *
0x1800e925a  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800e925f  mov     edi, eax
0x1800e9261  test    eax, eax
0x1800e9263  jns     short loc_1800E92D6
0x1800e9265  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e926c  mov     [rsp+9A0h+var_928], r15d
0x1800e9271  mov     [rsp+9A0h+var_930], eax
0x1800e9275  jz      loc_1800E9C0D
0x1800e927b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e9285  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e928c  jz      loc_1800E9C0D
0x1800e9292  mov     rax, cs:qword_180169748
0x1800e9299  and     rax, rdx
0x1800e929c  cmp     cs:qword_180169748, rax
0x1800e92a3  jnz     loc_1800E9C0D
0x1800e92a9  lea     rcx, [rbp+8A0h+var_740]; unsigned __int16 *
0x1800e92b0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e92b5  lea     rax, [rbp+8A0h+var_740]
0x1800e92bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e92c0  inc     rbx
0x1800e92c3  cmp     [rax+rbx*2], r15w
0x1800e92c8  jnz     short loc_1800E92C0
0x1800e92ca  lea     rax, [rbp+8A0h+var_740]
0x1800e92d1  jmp     loc_1800E9227
0x1800e92d6  xor     ecx, ecx; bstrString
0x1800e92d8  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800e92dd  lea     rcx, aHeader; "Header"
0x1800e92e4  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800e92e9  mov     [rbp+8A0h+var_920], rax
0x1800e92ed  mov     rdx, rax
0x1800e92f0  test    rax, rax
0x1800e92f3  jnz     loc_1800E93E1
0x1800e92f9  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e9300  mov     eax, 8007000Eh
0x1800e9305  mov     edi, eax
0x1800e9307  mov     [rsp+9A0h+var_930], eax
0x1800e930b  mov     [rsp+9A0h+var_928], r15d
0x1800e9310  jz      loc_1800E9C09
0x1800e9316  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e9320  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e9327  jz      loc_1800E9C09
0x1800e932d  mov     rax, cs:qword_180169748
0x1800e9334  and     rax, rdx
0x1800e9337  cmp     cs:qword_180169748, rax
0x1800e933e  jnz     loc_1800E9C09
0x1800e9344  lea     rcx, [rbp+8A0h+var_6C0]; unsigned __int16 *
0x1800e934b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e9350  lea     rax, [rbp+8A0h+var_6C0]
0x1800e9357  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e935b  inc     rbx
0x1800e935e  cmp     [rax+rbx*2], r15w
0x1800e9363  jnz     short loc_1800E935B
0x1800e9365  lea     rax, [rbp+8A0h+var_6C0]
0x1800e936c  lea     ecx, [rbx+rbx]
0x1800e936f  add     rcx, 2
0x1800e9373  lea     r9, [rsp+9A0h+var_930]
0x1800e9378  mov     [rsp+9A0h+var_940], rcx
0x1800e937d  lea     rdx, PLA_EVENT_ERROR
0x1800e9384  mov     [rsp+9A0h+var_948], rax
0x1800e9389  lea     rcx, [rsp+9A0h+var_928]
0x1800e938e  mov     [rsp+9A0h+var_950], 28h ; '('
0x1800e9397  lea     rax, aHconfiguration_4; "HConfigurationDataCollector::QueryFiles"
0x1800e939e  mov     [rsp+9A0h+var_958], rax
0x1800e93a3  mov     eax, 4
0x1800e93a8  mov     [rsp+9A0h+var_960], rax
0x1800e93ad  mov     [rsp+9A0h+var_968], rcx
0x1800e93b2  lea     rcx, byte_180147320
0x1800e93b9  mov     [rsp+9A0h+var_970], 1
0x1800e93c2  mov     [rsp+9A0h+var_978], rcx
0x1800e93c7  lea     r8d, [rax+1]
0x1800e93cb  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800e93d2  mov     [rsp+9A0h+var_980], rax
0x1800e93d7  call    EventingWriteEvent
0x1800e93dc  jmp     loc_1800E9C09
0x1800e93e1  mov     rcx, [r13+100h]
0x1800e93e8  lea     r8, [rbp+8A0h+var_908]
0x1800e93ec  mov     rax, [rcx]
0x1800e93ef  mov     rax, [rax+178h]
0x1800e93f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e93fb  mov     edi, eax
0x1800e93fd  test    eax, eax
0x1800e93ff  jns     short loc_1800E9472
0x1800e9401  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e9408  mov     [rsp+9A0h+var_928], r15d
0x1800e940d  mov     [rsp+9A0h+var_930], eax
0x1800e9411  jz      loc_1800E9C09
0x1800e9417  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e9421  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e9428  jz      loc_1800E9C09
0x1800e942e  mov     rax, cs:qword_180169748
0x1800e9435  and     rax, rdx
0x1800e9438  cmp     cs:qword_180169748, rax
0x1800e943f  jnz     loc_1800E9C09
0x1800e9445  lea     rcx, [rbp+8A0h+var_640]; unsigned __int16 *
0x1800e944c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e9451  lea     rax, [rbp+8A0h+var_640]
0x1800e9458  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e945c  inc     rbx
0x1800e945f  cmp     [rax+rbx*2], r15w
0x1800e9464  jnz     short loc_1800E945C
0x1800e9466  lea     rax, [rbp+8A0h+var_640]
0x1800e946d  jmp     loc_1800E936C
0x1800e9472  mov     rax, [r12]
0x1800e9476  xor     r8d, r8d
0x1800e9479  mov     rdx, [rbp+8A0h+var_908]
0x1800e947d  mov     rcx, r12
0x1800e9480  mov     rax, [rax+0A8h]
0x1800e9487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e948c  mov     edi, eax
0x1800e948e  test    eax, eax
0x1800e9490  jns     short loc_1800E9503
0x1800e9492  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800e9499  mov     [rsp+9A0h+var_928], r15d
0x1800e949e  mov     [rsp+9A0h+var_930], eax
0x1800e94a2  jz      loc_1800E9C09
0x1800e94a8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e94b2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e94b9  jz      loc_1800E9C09
0x1800e94bf  mov     rax, cs:qword_180169748
0x1800e94c6  and     rax, rdx
0x1800e94c9  cmp     cs:qword_180169748, rax
0x1800e94d0  jnz     loc_1800E9C09
0x1800e94d6  lea     rcx, [rbp+8A0h+var_5C0]; unsigned __int16 *
0x1800e94dd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e94e2  lea     rax, [rbp+8A0h+var_5C0]
0x1800e94e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e94ed  inc     rbx
0x1800e94f0  cmp     [rax+rbx*2], r15w
0x1800e94f5  jnz     short loc_1800E94ED
  ... truncated ...
```
