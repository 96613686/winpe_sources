# HConfigurationDataCollector::QueryRegistryKeys(IXMLDOMElement *)

- ea: `0x1800ab454`
- end: `0x1800ac0ed`
- name: `?QueryRegistryKeys@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@@Z`
- size: `3225`
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
- `0x1800ab454`
- `0x1800b6a74`
- `0x1800f4804`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800abd19`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800abd19`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800abc14`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800abc14`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ac046`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ac046`

## string_xrefs

- `0x1800abb86`: `registryKeysLookupResult`
- `0x1800abaf1`: `registryKeysType`
- `0x1800aba5c`: `registryKeysValue`
- `0x1800ab9c7`: `registryKeysKey`
- `0x1800ab55d`: `HConfigurationDataCollector::QueryRegistryKeys`
- `0x1800ab662`: `HConfigurationDataCollector::QueryRegistryKeys`
- `0x1800abe1f`: `HConfigurationDataCollector::QueryRegistryKeys`
- `0x1800abfe5`: `HConfigurationDataCollector::QueryRegistryKeys`
- `0x1800ab5b7`: `registryKeys`
- `0x1800ab6c9`: `registryKeysQuery`
- `0x1800abce3`: `registryKeysQuery`
- `0x1800ab774`: `registryKeysOpenResult`
- `0x1800abd6f`: `registryKeysOpenResult`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::QueryRegistryKeys(
        HConfigurationDataCollector *this,
        struct IXMLDOMElement *a2)
{
  struct IXMLDOMElement *v4; // rdi
  struct IXMLDOMElement *v5; // r15
  struct IXMLDOMElement *v6; // r12
  const unsigned __int16 *v7; // r9
  unsigned __int16 *v8; // r13
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  int *v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  const char *v19; // rdx
  int v20; // r8d
  struct IXMLDOMElement *v21; // rax
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
  int v33; // eax
  __int64 v34; // rax
  HRESULT v35; // eax
  __int64 v36; // rax
  unsigned int i; // edi
  _WORD *v38; // rcx
  int v39; // eax
  int v40; // eax
  unsigned int v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMElement *v52; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v53; // [rsp+88h] [rbp-78h] BYREF
  void *ppvData; // [rsp+90h] [rbp-70h] BYREF
  struct IXMLDOMElement *v55; // [rsp+98h] [rbp-68h] BYREF
  struct IXMLDOMElement *v56; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v57[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v58[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v59[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v60[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v61[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v62[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v63[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v64[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v65[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v66[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v67[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v68[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v69[64]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v70[64]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v71[64]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v72[64]; // [rsp+830h] [rbp+730h] BYREF

  ppvData = 0;
  v56 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v8 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v49);
  if ( !v8 )
  {
    v9 = -2147024882;
    v51 = -2147024882;
    v50 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v57, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v57[v10] );
    v11 = &v51;
    v12 = &v50;
LABEL_8:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
    goto LABEL_125;
  }
  v13 = PlaiCreateReportTable(*((struct IXMLDOMDocument **)this + 32), a2, L"registryKeys", v7, 0, &v56, &v52);
  v9 = v13;
  if ( v13 < 0 )
  {
    v51 = 0;
    v50 = v13;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v58[v14] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v50, 4, byte_180147320, 1, &v51, 4);
    }
    v5 = v52;
    goto LABEL_125;
  }
  v5 = v52;
  v15 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v52, L"registryKeysQuery", L"string");
  v9 = v15;
  if ( v15 < 0 )
  {
    v51 = 0;
    v50 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v59, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v59[v16] );
LABEL_23:
    v11 = &v50;
    v12 = &v51;
    goto LABEL_8;
  }
  v17 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v5, L"registryKeysOpenResult", L"number");
  v9 = v17;
  if ( v17 < 0 )
  {
    v51 = 0;
    v50 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v60, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v60[v18] );
    goto LABEL_23;
  }
  PlaiFreeString(0);
  v21 = (struct IXMLDOMElement *)PlaiAllocStringEx(L"Header", v19, v20);
  v52 = v21;
  v4 = v21;
  if ( !v21 )
  {
    v9 = -2147024882;
    v50 = -2147024882;
    v51 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v22 = -1;
    do
      ++v22;
    while ( v61[v22] );
    goto LABEL_23;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, struct IXMLDOMElement **))(**((_QWORD **)this + 32)
                                                                                             + 376LL))(
          *((_QWORD *)this + 32),
          v21,
          &v53);
  v9 = v23;
  if ( v23 < 0 )
  {
    v51 = 0;
    v50 = v23;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v62, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v62[v24] );
    goto LABEL_23;
  }
  v25 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v5->lpVtbl->appendChild)(
          v5,
          v53,
          0);
  v9 = v25;
  if ( v25 < 0 )
  {
    v51 = 0;
    v50 = v25;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v63, 0x4000000000000800uLL);
    v26 = -1;
    do
      ++v26;
    while ( v63[v26] );
    goto LABEL_23;
  }
  v27 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v53, L"registryKeysKey", L"string");
  v9 = v27;
  if ( v27 < 0 )
  {
    v51 = 0;
    v50 = v27;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v64, 0x4000000000000800uLL);
    v28 = -1;
    do
      ++v28;
    while ( v64[v28] );
    goto LABEL_23;
  }
  v29 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v53, L"registryKeysValue", L"string");
  v9 = v29;
  if ( v29 < 0 )
  {
    v51 = 0;
    v50 = v29;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v65, 0x4000000000000800uLL);
    v30 = -1;
    do
      ++v30;
    while ( v65[v30] );
    goto LABEL_23;
  }
  v31 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v53, L"registryKeysType", L"number");
  v9 = v31;
  if ( v31 < 0 )
  {
    v51 = 0;
    v50 = v31;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v66, 0x4000000000000800uLL);
    v32 = -1;
    do
      ++v32;
    while ( v66[v32] );
    goto LABEL_23;
  }
  v33 = PlaiAddDataToReportHeader(*((struct IXMLDOMDocument **)this + 32), v53, L"registryKeysLookupResult", L"number");
  v9 = v33;
  if ( v33 < 0 )
  {
    v51 = 0;
    v50 = v33;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v67, 0x4000000000000800uLL);
    v34 = -1;
    do
      ++v34;
    while ( v67[v34] );
    goto LABEL_23;
  }
  v35 = SafeArrayAccessData(*((SAFEARRAY **)this + 24), &ppvData);
  v9 = v35;
  if ( v35 < 0 )
  {
    v51 = 0;
    v50 = v35;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_125;
    }
    PlaiWhoAmI(v68, 0x4000000000000800uLL);
    v36 = -1;
    do
      ++v36;
    while ( v68[v36] );
    goto LABEL_23;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(*((_QWORD *)this + 24) + 24LL) )
      goto LABEL_124;
    v38 = (_WORD *)*((_QWORD *)ppvData + i);
    if ( !v38 || !*v38 )
      continue;
    v39 = PlaiAddItemToReport(*((struct IXMLDOMDocument **)this + 32), v56, &v55);
    v9 = v39;
    if ( v39 < 0 )
    {
      v50 = v39;
      v51 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v72, 0x4000000000000800uLL);
        v47 = -1;
        do
          ++v47;
        while ( v72[v47] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v50, 4, byte_180147320, 1, &v51, 4);
      }
      v6 = v55;
      goto LABEL_124;
    }
    v6 = v55;
    v40 = PlaiAddDataToReportItem(
            *((struct IXMLDOMDocument **)this + 32),
            v55,
            L"registryKeysQuery",
            *((const unsigned __int16 **)ppvData + i));
    v9 = v40;
    if ( v40 < 0 )
    {
      v50 = v40;
      v51 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v71, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v71[v46] );
        goto LABEL_103;
      }
      goto LABEL_124;
    }
    v41 = WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 16LL), 0) == 258
        ? HConfigurationDataCollector::QueryRegistryKey(this, *((unsigned __int16 **)ppvData + i), v6)
        : PlaiHResultFromWin32(0x4D3u);
    v42 = StringCchPrintfW(v8, 0x400u, L"0x%x", v41);
    v9 = v42;
    if ( v42 < 0 )
      break;
    v43 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)this + 32), v6, L"registryKeysOpenResult", v8);
    v9 = v43;
    if ( v43 < 0 )
    {
      v51 = 0;
      v50 = v43;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v69, 0x4000000000000800uLL);
        v44 = -1;
        do
          ++v44;
        while ( v69[v44] );
LABEL_103:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v50, 4, byte_180147320, 1, &v51, 4);
        goto LABEL_124;
      }
      goto LABEL_124;
    }
  }
  v51 = 0;
  v50 = v42;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v70, 0x4000000000000800uLL);
    v45 = -1;
    do
      ++v45;
    while ( v70[v45] );
    goto LABEL_103;
  }
LABEL_124:
  v4 = v52;
LABEL_125:
  if ( ppvData )
  {
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 24));
    ppvData = 0;
  }
  if ( v56 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v56->lpVtbl->Release)(v56);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v53 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v53->lpVtbl->Release)(v53);
    v53 = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  PlaiFreeString((BSTR)v4);
  if ( v8 )
    PlaiFree(v8, 1);
  return v9;
}

```

## disassembly

```asm
0x1800ab454  mov     [rsp-8+arg_10], rbx
0x1800ab459  push    rbp
0x1800ab45a  push    rsi
0x1800ab45b  push    rdi
0x1800ab45c  push    r12
0x1800ab45e  push    r13
0x1800ab460  push    r14
0x1800ab462  push    r15
0x1800ab464  lea     rbp, [rsp-7C0h]
0x1800ab46c  sub     rsp, 8C0h
0x1800ab473  mov     rax, cs:__security_cookie
0x1800ab47a  xor     rax, rsp
0x1800ab47d  mov     [rbp+7F0h+var_40], rax
0x1800ab484  xor     esi, esi
0x1800ab486  lea     r9, byte_180147320; char *
0x1800ab48d  mov     rbx, rdx
0x1800ab490  mov     [rbp+7F0h+ppvData], rsi
0x1800ab494  mov     r14, rcx
0x1800ab497  mov     [rbp+7F0h+var_850], rsi
0x1800ab49b  xor     r8d, r8d; int
0x1800ab49e  mov     [rbp+7F0h+var_870], rsi
0x1800ab4a2  lea     edx, [rsi+1]; int
0x1800ab4a5  mov     [rbp+7F0h+var_868], rsi
0x1800ab4a9  mov     ecx, 800h; dwBytes
0x1800ab4ae  mov     [rbp+7F0h+var_858], rsi
0x1800ab4b2  mov     edi, esi
0x1800ab4b4  mov     r15d, esi
0x1800ab4b7  mov     r12d, esi
0x1800ab4ba  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800ab4bf  mov     r13, rax
0x1800ab4c2  test    rax, rax
0x1800ab4c5  jnz     loc_1800AB5A7
0x1800ab4cb  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab4d1  mov     eax, 8007000Eh
0x1800ab4d6  mov     ebx, eax
0x1800ab4d8  mov     [rsp+8F0h+var_878], eax
0x1800ab4dc  mov     [rsp+8F0h+var_880], esi
0x1800ab4e0  jz      loc_1800AC039
0x1800ab4e6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab4f0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab4f7  jz      loc_1800AC039
0x1800ab4fd  mov     rax, cs:qword_180169748
0x1800ab504  and     rax, rdx
0x1800ab507  cmp     cs:qword_180169748, rax
0x1800ab50e  jnz     loc_1800AC039
0x1800ab514  lea     rcx, [rbp+7F0h+var_840]; unsigned __int16 *
0x1800ab518  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab51d  lea     rcx, [rbp+7F0h+var_840]
0x1800ab521  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab525  inc     rax
0x1800ab528  cmp     [rcx+rax*2], si
0x1800ab52c  jnz     short loc_1800AB525
0x1800ab52e  lea     ecx, [rax+rax]
0x1800ab531  add     rcx, 2
0x1800ab535  lea     rax, [rbp+7F0h+var_840]
0x1800ab539  mov     [rsp+8F0h+var_890], rcx
0x1800ab53e  lea     r9, [rsp+8F0h+var_878]
0x1800ab543  lea     rcx, [rsp+8F0h+var_880]
0x1800ab548  mov     [rsp+8F0h+var_898], rax
0x1800ab54d  lea     rdx, PLA_EVENT_ERROR
0x1800ab554  mov     [rsp+8F0h+var_8A0], 2Fh ; '/'
0x1800ab55d  lea     rax, aHconfiguration_5; "HConfigurationDataCollector::QueryRegis"...
0x1800ab564  mov     [rsp+8F0h+var_8A8], rax
0x1800ab569  mov     eax, 4
0x1800ab56e  mov     [rsp+8F0h+var_8B0], rax
0x1800ab573  mov     [rsp+8F0h+var_8B8], rcx
0x1800ab578  lea     rcx, byte_180147320
0x1800ab57f  mov     [rsp+8F0h+var_8C0], 1
0x1800ab588  mov     [rsp+8F0h+var_8C8], rcx
0x1800ab58d  lea     r8d, [rax+1]
0x1800ab591  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ab598  mov     [rsp+8F0h+var_8D0], rax
0x1800ab59d  call    EventingWriteEvent
0x1800ab5a2  jmp     loc_1800AC039
0x1800ab5a7  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x1800ab5ae  lea     rax, [rbp+7F0h+var_870]
0x1800ab5b2  mov     [rsp+8F0h+var_8C0], rax; struct IXMLDOMElement **
0x1800ab5b7  lea     r8, aRegistrykeys; "registryKeys"
0x1800ab5be  lea     rax, [rbp+7F0h+var_850]
0x1800ab5c2  mov     rdx, rbx; struct IXMLDOMElement *
0x1800ab5c5  mov     [rsp+8F0h+var_8C8], rax; struct IXMLDOMElement **
0x1800ab5ca  mov     [rsp+8F0h+var_8D0], rsi; unsigned __int16 *
0x1800ab5cf  call    ?PlaiCreateReportTable@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG22PEAPEAU2@3@Z; PlaiCreateReportTable(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *,IXMLDOMElement * *)
0x1800ab5d4  mov     ebx, eax
0x1800ab5d6  test    eax, eax
0x1800ab5d8  jns     loc_1800AB6B7
0x1800ab5de  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab5e4  mov     [rsp+8F0h+var_878], esi
0x1800ab5e8  mov     [rsp+8F0h+var_880], eax
0x1800ab5ec  jz      loc_1800AB6AE
0x1800ab5f2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab5fc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab603  jz      loc_1800AB6AE
0x1800ab609  mov     rax, cs:qword_180169748
0x1800ab610  and     rax, rdx
0x1800ab613  cmp     cs:qword_180169748, rax
0x1800ab61a  jnz     loc_1800AB6AE
0x1800ab620  lea     rcx, [rbp+7F0h+var_7C0]; unsigned __int16 *
0x1800ab624  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab629  lea     rcx, [rbp+7F0h+var_7C0]
0x1800ab62d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab631  inc     rax
0x1800ab634  cmp     [rcx+rax*2], si
0x1800ab638  jnz     short loc_1800AB631
0x1800ab63a  lea     ecx, [rax+rax]
0x1800ab63d  add     rcx, 2
0x1800ab641  lea     rax, [rbp+7F0h+var_7C0]
0x1800ab645  mov     [rsp+8F0h+var_890], rcx
0x1800ab64a  lea     r9, [rsp+8F0h+var_880]
0x1800ab64f  mov     [rsp+8F0h+var_898], rax
0x1800ab654  lea     rcx, [rsp+8F0h+var_878]
0x1800ab659  mov     [rsp+8F0h+var_8A0], 2Fh ; '/'
0x1800ab662  lea     rax, aHconfiguration_5; "HConfigurationDataCollector::QueryRegis"...
0x1800ab669  mov     [rsp+8F0h+var_8A8], rax
0x1800ab66e  lea     rdx, PLA_EVENT_ERROR
0x1800ab675  mov     eax, 4
0x1800ab67a  mov     [rsp+8F0h+var_8B0], rax
0x1800ab67f  mov     [rsp+8F0h+var_8B8], rcx
0x1800ab684  lea     rcx, byte_180147320
0x1800ab68b  mov     [rsp+8F0h+var_8C0], 1
0x1800ab694  mov     [rsp+8F0h+var_8C8], rcx
0x1800ab699  lea     r8d, [rax+1]
0x1800ab69d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ab6a4  mov     [rsp+8F0h+var_8D0], rax
0x1800ab6a9  call    EventingWriteEvent
0x1800ab6ae  mov     r15, [rbp+7F0h+var_870]
0x1800ab6b2  jmp     loc_1800AC039
0x1800ab6b7  mov     r15, [rbp+7F0h+var_870]
0x1800ab6bb  lea     r9, aString; "string"
0x1800ab6c2  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x1800ab6c9  lea     r8, aRegistrykeysqu; "registryKeysQuery"
0x1800ab6d0  mov     rdx, r15; struct IXMLDOMElement *
0x1800ab6d3  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800ab6d8  mov     ebx, eax
0x1800ab6da  test    eax, eax
0x1800ab6dc  jns     loc_1800AB766
0x1800ab6e2  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab6e8  mov     [rsp+8F0h+var_878], esi
0x1800ab6ec  mov     [rsp+8F0h+var_880], eax
0x1800ab6f0  jz      loc_1800AC039
0x1800ab6f6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab700  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab707  jz      loc_1800AC039
0x1800ab70d  mov     rax, cs:qword_180169748
0x1800ab714  and     rax, rdx
0x1800ab717  cmp     cs:qword_180169748, rax
0x1800ab71e  jnz     loc_1800AC039
0x1800ab724  lea     rcx, [rbp+7F0h+var_740]; unsigned __int16 *
0x1800ab72b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab730  lea     rcx, [rbp+7F0h+var_740]
0x1800ab737  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab73b  inc     rax
0x1800ab73e  cmp     [rcx+rax*2], si
0x1800ab742  jnz     short loc_1800AB73B
0x1800ab744  lea     ecx, [rax+rax]
0x1800ab747  lea     rax, [rbp+7F0h+var_740]
0x1800ab74e  add     rcx, 2
0x1800ab752  lea     r9, [rsp+8F0h+var_880]
0x1800ab757  mov     [rsp+8F0h+var_890], rcx
0x1800ab75c  lea     rcx, [rsp+8F0h+var_878]
0x1800ab761  jmp     loc_1800AB548
0x1800ab766  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x1800ab76d  lea     r9, aNumber; "number"
0x1800ab774  lea     r8, aRegistrykeysop; "registryKeysOpenResult"
0x1800ab77b  mov     rdx, r15; struct IXMLDOMElement *
0x1800ab77e  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800ab783  mov     ebx, eax
0x1800ab785  test    eax, eax
0x1800ab787  jns     short loc_1800AB7FA
0x1800ab789  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab78f  mov     [rsp+8F0h+var_878], esi
0x1800ab793  mov     [rsp+8F0h+var_880], eax
0x1800ab797  jz      loc_1800AC039
0x1800ab79d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab7a7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab7ae  jz      loc_1800AC039
0x1800ab7b4  mov     rax, cs:qword_180169748
0x1800ab7bb  and     rax, rdx
0x1800ab7be  cmp     cs:qword_180169748, rax
0x1800ab7c5  jnz     loc_1800AC039
0x1800ab7cb  lea     rcx, [rbp+7F0h+var_6C0]; unsigned __int16 *
0x1800ab7d2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab7d7  lea     rcx, [rbp+7F0h+var_6C0]
0x1800ab7de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab7e2  inc     rax
0x1800ab7e5  cmp     [rcx+rax*2], si
0x1800ab7e9  jnz     short loc_1800AB7E2
0x1800ab7eb  lea     ecx, [rax+rax]
0x1800ab7ee  lea     rax, [rbp+7F0h+var_6C0]
0x1800ab7f5  jmp     loc_1800AB74E
0x1800ab7fa  xor     ecx, ecx; bstrString
0x1800ab7fc  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800ab801  lea     rcx, aHeader; "Header"
0x1800ab808  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800ab80d  mov     [rbp+7F0h+var_870], rax
0x1800ab811  mov     rdi, rax
0x1800ab814  test    rax, rax
0x1800ab817  jnz     short loc_1800AB891
0x1800ab819  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab81f  mov     eax, 8007000Eh
0x1800ab824  mov     ebx, eax
0x1800ab826  mov     [rsp+8F0h+var_880], eax
0x1800ab82a  mov     [rsp+8F0h+var_878], esi
0x1800ab82e  jz      loc_1800AC039
0x1800ab834  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab83e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab845  jz      loc_1800AC039
0x1800ab84b  mov     rax, cs:qword_180169748
0x1800ab852  and     rax, rdx
0x1800ab855  cmp     cs:qword_180169748, rax
0x1800ab85c  jnz     loc_1800AC039
0x1800ab862  lea     rcx, [rbp+7F0h+var_640]; unsigned __int16 *
0x1800ab869  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab86e  lea     rcx, [rbp+7F0h+var_640]
0x1800ab875  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab879  inc     rax
0x1800ab87c  cmp     [rcx+rax*2], si
0x1800ab880  jnz     short loc_1800AB879
0x1800ab882  lea     ecx, [rax+rax]
0x1800ab885  lea     rax, [rbp+7F0h+var_640]
0x1800ab88c  jmp     loc_1800AB74E
0x1800ab891  mov     rcx, [r14+100h]
0x1800ab898  lea     r8, [rbp+7F0h+var_868]
0x1800ab89c  mov     rdx, rdi
0x1800ab89f  mov     rax, [rcx]
0x1800ab8a2  mov     rax, [rax+178h]
0x1800ab8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab8ae  mov     ebx, eax
0x1800ab8b0  test    eax, eax
0x1800ab8b2  jns     short loc_1800AB925
0x1800ab8b4  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab8ba  mov     [rsp+8F0h+var_878], esi
0x1800ab8be  mov     [rsp+8F0h+var_880], eax
0x1800ab8c2  jz      loc_1800AC039
0x1800ab8c8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab8d2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab8d9  jz      loc_1800AC039
0x1800ab8df  mov     rax, cs:qword_180169748
0x1800ab8e6  and     rax, rdx
0x1800ab8e9  cmp     cs:qword_180169748, rax
0x1800ab8f0  jnz     loc_1800AC039
0x1800ab8f6  lea     rcx, [rbp+7F0h+var_5C0]; unsigned __int16 *
0x1800ab8fd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab902  lea     rcx, [rbp+7F0h+var_5C0]
0x1800ab909  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab90d  inc     rax
0x1800ab910  cmp     [rcx+rax*2], si
0x1800ab914  jnz     short loc_1800AB90D
0x1800ab916  lea     ecx, [rax+rax]
0x1800ab919  lea     rax, [rbp+7F0h+var_5C0]
0x1800ab920  jmp     loc_1800AB74E
0x1800ab925  mov     rax, [r15]
0x1800ab928  xor     r8d, r8d
0x1800ab92b  mov     rdx, [rbp+7F0h+var_868]
0x1800ab92f  mov     rcx, r15
0x1800ab932  mov     rax, [rax+0A8h]
0x1800ab939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab93e  mov     ebx, eax
0x1800ab940  test    eax, eax
0x1800ab942  jns     short loc_1800AB9B5
0x1800ab944  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab94a  mov     [rsp+8F0h+var_878], esi
0x1800ab94e  mov     [rsp+8F0h+var_880], eax
0x1800ab952  jz      loc_1800AC039
0x1800ab958  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab962  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab969  jz      loc_1800AC039
0x1800ab96f  mov     rax, cs:qword_180169748
0x1800ab976  and     rax, rdx
0x1800ab979  cmp     cs:qword_180169748, rax
0x1800ab980  jnz     loc_1800AC039
0x1800ab986  lea     rcx, [rbp+7F0h+var_540]; unsigned __int16 *
0x1800ab98d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ab992  lea     rcx, [rbp+7F0h+var_540]
0x1800ab999  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab99d  inc     rax
0x1800ab9a0  cmp     [rcx+rax*2], si
0x1800ab9a4  jnz     short loc_1800AB99D
0x1800ab9a6  lea     ecx, [rax+rax]
0x1800ab9a9  lea     rax, [rbp+7F0h+var_540]
0x1800ab9b0  jmp     loc_1800AB74E
0x1800ab9b5  mov     rdx, [rbp+7F0h+var_868]; struct IXMLDOMElement *
0x1800ab9b9  lea     r9, aString; "string"
0x1800ab9c0  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x1800ab9c7  lea     r8, aRegistrykeyske; "registryKeysKey"
0x1800ab9ce  call    ?PlaiAddDataToReportHeader@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportHeader(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800ab9d3  mov     ebx, eax
0x1800ab9d5  test    eax, eax
0x1800ab9d7  jns     short loc_1800ABA4A
0x1800ab9d9  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ab9df  mov     [rsp+8F0h+var_878], esi
0x1800ab9e3  mov     [rsp+8F0h+var_880], eax
0x1800ab9e7  jz      loc_1800AC039
0x1800ab9ed  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ab9f7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ab9fe  jz      loc_1800AC039
0x1800aba04  mov     rax, cs:qword_180169748
0x1800aba0b  and     rax, rdx
0x1800aba0e  cmp     cs:qword_180169748, rax
0x1800aba15  jnz     loc_1800AC039
  ... truncated ...
```
