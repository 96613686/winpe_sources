# ValueMap::AddFlagOrIndex(tagVARIANT)

- ea: `0x180007940`
- end: `0x18000922f`
- name: `?AddFlagOrIndex@ValueMap@@IEAAJUtagVARIANT@@@Z`
- size: `6383`
- prototype: `__int64 __fastcall(ValueMap *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006ca0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180007940`
- `0x180009240`
- `0x1800198b0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000920e`
- `msvcrt!_wcsicmp` at `0x18000920e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ec8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e68`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d1a`
- `OLEAUT32!__imp_VariantInit` at `0x180007995`
- `OLEAUT32!__imp_VariantInit` at `0x180007d50`
- `OLEAUT32!__imp_VariantInit` at `0x180007995`
- `OLEAUT32!__imp_VariantInit` at `0x180007d50`
- `OLEAUT32!__imp_VariantClear` at `0x180007a06`
- `OLEAUT32!__imp_VariantClear` at `0x180007b10`
- `OLEAUT32!__imp_VariantClear` at `0x180007b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180007d73`
- `OLEAUT32!__imp_VariantClear` at `0x180007eeb`
- `OLEAUT32!__imp_VariantClear` at `0x180007f34`
- `OLEAUT32!__imp_VariantClear` at `0x180007fea`
- `OLEAUT32!__imp_VariantClear` at `0x180008180`
- `OLEAUT32!__imp_VariantClear` at `0x180008329`
- `OLEAUT32!__imp_VariantClear` at `0x1800091c1`
- `OLEAUT32!__imp_VariantClear` at `0x180007a06`
- `OLEAUT32!__imp_VariantClear` at `0x180007b10`
- `OLEAUT32!__imp_VariantClear` at `0x180007b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180007d73`
- `OLEAUT32!__imp_VariantClear` at `0x180007eeb`
- `OLEAUT32!__imp_VariantClear` at `0x180007f34`
- `OLEAUT32!__imp_VariantClear` at `0x180007fea`
- `OLEAUT32!__imp_VariantClear` at `0x180008180`
- `OLEAUT32!__imp_VariantClear` at `0x180008329`
- `OLEAUT32!__imp_VariantClear` at `0x1800091c1`
- `OLEAUT32!__imp_VariantCopy` at `0x180007eaa`
- `OLEAUT32!__imp_VariantCopy` at `0x180007eaa`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007de0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800083fb`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007de0`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800083fb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800083d0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800083d0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180007e86`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180007e86`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007ed8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007ed8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800085d5`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800085d5`

## string_xrefs

- `0x1800088d1`: `ValueMap::CreateItem`
- `0x18000898f`: `ValueMap::CreateItem`

## pseudocode

```c
__int64 __fastcall ValueMap::AddFlagOrIndex(ValueMap *this, struct tagVARIANT *a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned __int64 v6; // rdx
  int v7; // ebx
  int v8; // eax
  unsigned __int64 v9; // rdx
  int v10; // eax
  unsigned __int64 v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // rdx
  BOOL v14; // r15d
  int v15; // r13d
  __int64 v16; // rdi
  int v17; // eax
  unsigned __int64 v18; // rdx
  VARTYPE vt; // ax
  __int64 *v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  int v23; // edi
  LONGLONG llVal; // rbx
  bool v25; // zf
  OLECHAR *v26; // rdi
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned __int64 v31; // rdx
  LONGLONG Class; // rsi
  int v33; // eax
  unsigned __int64 v34; // rdx
  int v35; // eax
  unsigned __int64 v36; // rdx
  HRESULT v37; // eax
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  __int64 (__fastcall *v40)(LONGLONG, __int128 *); // rax
  int v41; // eax
  unsigned __int64 v42; // rdx
  __int64 v43; // rdi
  unsigned int v44; // eax
  SAFEARRAY **v45; // r15
  HRESULT v46; // eax
  unsigned __int64 v47; // rdx
  int v48; // r14d
  HRESULT v49; // eax
  unsigned __int64 v50; // rdx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 (__fastcall *v55)(__int64 *, __int64); // rax
  int v56; // eax
  unsigned __int64 v57; // rdx
  __int64 v58; // rax
  SAFEARRAY *v59; // rcx
  SAFEARRAY *v60; // rax
  HRESULT v61; // eax
  unsigned __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rdi
  int v65; // eax
  unsigned __int64 v66; // rdx
  __int64 v67; // rdi
  int v68; // eax
  unsigned __int64 v69; // rdx
  HRESULT v70; // eax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // [rsp+78h] [rbp-90h] BYREF
  __int64 v90; // [rsp+80h] [rbp-88h] BYREF
  VARIANTARG pvargSrc; // [rsp+88h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v93; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-58h] BYREF
  void *ppvData; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v97; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvargDest; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v99; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v100; // [rsp+118h] [rbp+10h]
  unsigned __int16 v101[64]; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 v102[64]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v103[64]; // [rsp+228h] [rbp+120h] BYREF
  unsigned __int16 v104[64]; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned __int16 v105[64]; // [rsp+328h] [rbp+220h] BYREF
  unsigned __int16 v106[64]; // [rsp+3A8h] [rbp+2A0h] BYREF
  unsigned __int16 v107[64]; // [rsp+428h] [rbp+320h] BYREF
  unsigned __int16 v108[64]; // [rsp+4A8h] [rbp+3A0h] BYREF
  unsigned __int16 v109[64]; // [rsp+528h] [rbp+420h] BYREF
  unsigned __int16 v110[64]; // [rsp+5A8h] [rbp+4A0h] BYREF
  unsigned __int16 v111[64]; // [rsp+628h] [rbp+520h] BYREF
  unsigned __int16 v112[64]; // [rsp+6A8h] [rbp+5A0h] BYREF
  unsigned __int16 v113[64]; // [rsp+728h] [rbp+620h] BYREF
  unsigned __int16 v114[64]; // [rsp+7A8h] [rbp+6A0h] BYREF
  unsigned __int16 v115[64]; // [rsp+828h] [rbp+720h] BYREF
  unsigned __int16 v116[64]; // [rsp+8A8h] [rbp+7A0h] BYREF
  unsigned __int16 v117[64]; // [rsp+928h] [rbp+820h] BYREF
  unsigned __int16 v118[64]; // [rsp+9A8h] [rbp+8A0h] BYREF
  unsigned __int16 v119[64]; // [rsp+A28h] [rbp+920h] BYREF
  unsigned __int16 v120[64]; // [rsp+AA8h] [rbp+9A0h] BYREF
  unsigned __int16 v121[64]; // [rsp+B28h] [rbp+A20h] BYREF
  unsigned __int16 v122[64]; // [rsp+BA8h] [rbp+AA0h] BYREF
  unsigned __int16 v123[64]; // [rsp+C28h] [rbp+B20h] BYREF
  unsigned __int16 v124[64]; // [rsp+CA8h] [rbp+BA0h] BYREF
  unsigned __int16 v125[64]; // [rsp+D28h] [rbp+C20h] BYREF
  unsigned __int16 v126[64]; // [rsp+DA8h] [rbp+CA0h] BYREF
  unsigned __int16 v127[64]; // [rsp+E28h] [rbp+D20h] BYREF
  unsigned __int16 v128[64]; // [rsp+EA8h] [rbp+DA0h] BYREF

  v97 = 0;
  v94 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v93 = 0;
  VariantInit(&pvarg);
  v4 = *(_QWORD *)this;
  pvarg.llVal = 0;
  v5 = (*(__int64 (__fastcall **)(ValueMap *, __int64 *))(v4 + 72))(this, &v97);
  v7 = v5;
  if ( v5 < 0 )
  {
    LODWORD(v90) = 0;
    LODWORD(v89) = v5;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v101, v6);
      v53 = -1;
      do
        v25 = v101[++v53] == 0;
      while ( !v25 );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v90, 4);
    }
    goto LABEL_60;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v97)(v97, &IID_IEnumVARIANT, &v94);
  v7 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v90) = v8;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_60;
    }
    PlaiWhoAmI(v102, v9);
    v77 = -1;
    do
      v25 = v102[++v77] == 0;
    while ( !v25 );
LABEL_173:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
    goto LABEL_60;
  }
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 40LL))(v94);
  v7 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v90) = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_60;
    }
    PlaiWhoAmI(v103, v11);
    v78 = -1;
    do
      v25 = v103[++v78] == 0;
    while ( !v25 );
    goto LABEL_173;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v94 + 24LL))(v94, 1, &pvarg, 0);
  v7 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v90) = v12;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_60;
    }
    PlaiWhoAmI(v104, v13);
    v79 = -1;
    do
      v25 = v104[++v79] == 0;
    while ( !v25 );
    goto LABEL_173;
  }
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    v16 = -1;
    if ( v7 == 1 )
    {
      if ( v15 )
      {
LABEL_59:
        v7 = 0;
        goto LABEL_60;
      }
      pRecInfo = a2->pRecInfo;
      *(_OWORD *)&pvargDest.vt = *(_OWORD *)&a2->vt;
      memset(&pvargSrc, 0, sizeof(pvargSrc));
      pvargDest.pRecInfo = pRecInfo;
      VariantInit(&pvargSrc);
      pvargSrc.llVal = 0;
      Class = CreateClassObject<ValueMapItem>();
      if ( !Class )
      {
        v7 = -2147024882;
        LODWORD(v90) = -2147024882;
        LODWORD(v89) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v118, v31);
          v75 = -1;
          do
            v25 = v118[++v75] == 0;
          while ( !v25 );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
        }
        VariantClear(&pvargSrc);
        pvargSrc.llVal = 0;
LABEL_101:
        LODWORD(v89) = 0;
        LODWORD(v90) = v7;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_60;
        }
        PlaiWhoAmI(v128, v50);
        do
          v25 = v128[++v16] == 0;
        while ( !v25 );
        goto LABEL_173;
      }
      VariantClear(&pvargSrc);
      pvargSrc.llVal = Class;
      pvargSrc.vt = 9;
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)Class + 8LL))(Class);
      v33 = (*(__int64 (__fastcall **)(LONGLONG, _QWORD))(*(_QWORD *)Class + 128LL))(
              Class,
              *((unsigned int *)this + 22));
      v7 = v33;
      if ( v33 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v33;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v119, v34);
        v72 = -1;
        do
          v25 = v119[++v72] == 0;
        while ( !v25 );
        goto LABEL_153;
      }
      v35 = (*(__int64 (__fastcall **)(LONGLONG, __int64))(*(_QWORD *)Class + 80LL))(Class, 0xFFFFFFFFLL);
      v7 = v35;
      if ( v35 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v120, v36);
        v74 = -1;
        do
          v25 = v120[++v74] == 0;
        while ( !v25 );
        goto LABEL_153;
      }
      v37 = VariantChangeType(&pvargDest, &pvargDest, 0, *((_WORD *)this + 36));
      v7 = v37;
      if ( v37 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v37;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v121, v38);
        v83 = -1;
        do
          v25 = v121[++v83] == 0;
        while ( !v25 );
        goto LABEL_153;
      }
      v39 = *(_QWORD *)Class;
      v99 = *(_OWORD *)&pvargDest.vt;
      v40 = *(__int64 (__fastcall **)(LONGLONG, __int128 *))(v39 + 112);
      v100 = pvargDest.pRecInfo;
      v41 = v40(Class, &v99);
      v7 = v41;
      if ( v41 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v41;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v122, v42);
        v84 = -1;
        do
          v25 = v122[++v84] == 0;
        while ( !v25 );
LABEL_153:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
LABEL_83:
        VariantClear(&pvargSrc);
        pvargSrc.llVal = 0;
LABEL_58:
        (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)Class + 16LL))(Class);
        if ( v7 >= 0 )
          goto LABEL_59;
        goto LABEL_101;
      }
      v43 = *((_QWORD *)this + 12);
      v90 = v43;
      ppvData = 0;
      LODWORD(v89) = *(_DWORD *)(v43 + 56);
      bstrString = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
      {
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::Add", 16, &v90, 8, &v89, 4);
      }
      if ( *(_DWORD *)(v43 + 8) )
        EnterCriticalSection((LPCRITICAL_SECTION)(v43 + 16));
      v44 = *(_DWORD *)(v43 + 80);
      if ( *(_DWORD *)(v43 + 76) >= v44 )
      {
        v59 = *(SAFEARRAY **)(v43 + 64);
        v45 = (SAFEARRAY **)(v43 + 64);
        bstrString = (BSTR)(v44 + 16);
        if ( v59 )
        {
          v70 = SafeArrayRedim(v59, (SAFEARRAYBOUND *)&bstrString);
          v48 = v70;
          if ( v70 < 0 )
          {
            LODWORD(v89) = 0;
            LODWORD(v90) = v70;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_51;
            }
            PlaiWhoAmI(v123, v47);
            v71 = -1;
            do
              v25 = v123[++v71] == 0;
            while ( !v25 );
            goto LABEL_161;
          }
        }
        else
        {
          v60 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&bstrString);
          *v45 = v60;
          if ( !v60 )
          {
            v48 = -2147024882;
            LODWORD(v90) = -2147024882;
            LODWORD(v89) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_51;
            }
            PlaiWhoAmI(v124, v47);
            v76 = -1;
            do
              v25 = v124[++v76] == 0;
            while ( !v25 );
            goto LABEL_161;
          }
        }
        *(_DWORD *)(v43 + 80) = (_DWORD)bstrString;
      }
      v45 = (SAFEARRAY **)(v43 + 64);
      v46 = SafeArrayAccessData(*(SAFEARRAY **)(v43 + 64), &ppvData);
      v48 = v46;
      if ( v46 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v46;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_51;
        }
        PlaiWhoAmI(v125, v47);
        v85 = -1;
        do
          v25 = v125[++v85] == 0;
        while ( !v25 );
      }
      else
      {
        v49 = VariantCopy((VARIANTARG *)ppvData + *(unsigned int *)(v43 + 76), &pvargSrc);
        v48 = v49;
        if ( v49 >= 0 )
        {
          ++*(_DWORD *)(v43 + 76);
LABEL_51:
          if ( *(_DWORD *)(v43 + 8) )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v43 + 16));
          if ( ppvData )
            SafeArrayUnaccessData(*v45);
          if ( v48 >= 0 )
          {
            VariantClear(&pvargSrc);
            pvargSrc.llVal = 0;
            v7 = v48;
LABEL_57:
            v16 = -1;
            goto LABEL_58;
          }
          LODWORD(v90) = v48;
          v7 = v48;
          LODWORD(v89) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            VariantClear(&pvargSrc);
            pvargSrc.llVal = 0;
            goto LABEL_57;
          }
          PlaiWhoAmI(v127, v47);
          v16 = -1;
          v86 = -1;
          do
            v25 = v127[++v86] == 0;
          while ( !v25 );
          goto LABEL_153;
        }
        LODWORD(v89) = 0;
        LODWORD(v90) = v49;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_51;
        }
        PlaiWhoAmI(v126, v47);
        v54 = -1;
        do
          v25 = v126[++v54] == 0;
        while ( !v25 );
      }
LABEL_161:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
      goto LABEL_51;
    }
    if ( pvarg.vt != 9 )
    {
      v7 = -2147023267;
      LODWORD(v90) = -2147023267;
      LODWORD(v89) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_60;
      }
      PlaiWhoAmI(v117, v13);
      do
        v25 = v117[++v16] == 0;
      while ( !v25 );
      goto LABEL_173;
    }
    if ( v93 )
    {
      (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
      v93 = 0;
    }
    v17 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 **))pvarg.llVal)(pvarg.llVal, &IID_IValueMapItem, &v93);
    v7 = v17;
    if ( v17 < 0 )
      break;
    vt = a2->vt;
    v20 = v93;
    bstrString = 0;
    if ( vt == 21 )
    {
      v21 = *v93;
      memset(&pvargSrc, 0, sizeof(pvargSrc));
      v23 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v21 + 104))(v93, &pvargSrc);
      if ( v23 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v90) = v23;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v106, v22);
          v73 = -1;
          do
            v25 = v106[++v73] == 0;
          while ( !v25 );
          goto LABEL_147;
        }
      }
      else
      {
        if ( pvargSrc.vt == 21 || (v61 = VariantChangeType(&pvargSrc, &pvargSrc, 0, 0x15u), v23 = v61, v61 >= 0) )
        {
          llVal = pvargSrc.llVal;
          VariantClear(&pvargSrc);
          v25 = llVal == a2->llVal;
          v7 = v23;
          v14 = v25;
          goto LABEL_15;
        }
        LODWORD(v89) = 0;
        LODWORD(v90) = v61;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v107, v62);
          v63 = -1;
          do
            v25 = v107[++v63] == 0;
          while ( !v25 );
LABEL_147:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
        }
      }
      VariantClear(&pvargSrc);
      LODWORD(v90) = v23;
      v7 = v23;
      LODWORD(v89) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v108, v18);
        v52 = -1;
        do
          v25 = v108[++v52] == 0;
        while ( !v25 );
LABEL_33:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v90, 4, byte_180147320, 1, &v89, 4);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
    if ( vt == 8 )
    {
      PlaiFreeString(0);
      v87 = *v20;
      bstrString = 0;
      v88 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v87 + 88))(v20, &bstrString);
      v7 = v88;
      if ( v88 < 0 )
      {
        LODWORD(v90) = v88;
        LODWORD(v89) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v109, v18);
          v80 = -1;
          do
            v25 = v109[++v80] == 0;
          while ( !v25 );
          goto LABEL_33;
        }
      }
      else
      {
        v14 = bstrString && a2->llVal && !_wcsicmp(bstrString, a2->bstrVal);
      }
    }
    else
    {
      v7 = -2147023267;
      LODWORD(v90) = -2147023267;
      LODWORD(v89) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v105, v18);
        v29 = -1;
        do
          v25 = v105[++v29] == 0;
        while ( !v25 );
        goto LABEL_33;
      }
    }
LABEL_15:
    v26 = bstrString;
    if ( bstrString )
    {
      ppvData = bstrString;
      LODWORD(v89) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
      {
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_FREE_STRING, 3, byte_180147320, 1, &v89, 4, &ppvData, 8);
      }
      SysFreeString(v26);
    }
    if ( v7 < 0 )
    {
      LODWORD(v89) = 0;
      LODWORD(v90) = v7;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v115, v18);
        v82 = -1;
        do
          v25 = v115[++v82] == 0;
        while ( !v25 );
        goto LABEL_173;
      }
      goto LABEL_60;
    }
    if ( *((_DWORD *)this + 22) == 1 )
    {
      v55 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 80);
      if ( v14 )
      {
        v64 = -1;
        v65 = v55(v93, 0xFFFFFFFFLL);
        v7 = v65;
        if ( v65 < 0 )
        {
          LODWORD(v89) = 0;
          LODWORD(v90) = v65;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v114, v66);
            do
              v25 = v114[++v64] == 0;
            while ( !v25 );
            goto LABEL_173;
          }
          goto LABEL_60;
        }
        v15 = 1;
      }
      else
      {
        v56 = v55(v93, 0);
        v7 = v56;
        if ( v56 < 0 )
        {
          LODWORD(v89) = 0;
          LODWORD(v90) = v56;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v112, v57);
            v58 = -1;
            do
              v25 = v112[++v58] == 0;
            while ( !v25 );
            goto LABEL_173;
          }
          goto LABEL_60;
        }
      }
    }
    else
    {
      if ( *((_DWORD *)this + 22) != 2 )
      {
        v7 = -2147467259;
        LODWORD(v90) = -2147467259;
        LODWORD(v89) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v111, v18);
          v81 = -1;
          do
            v25 = v111[++v81] == 0;
          while ( !v25 );
          goto LABEL_173;
        }
        goto LABEL_60;
      }
      if ( v14 )
      {
        v67 = -1;
        v68 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v93 + 80))(v93, 0xFFFFFFFFLL);
        v7 = v68;
        if ( v68 < 0 )
        {
          LODWORD(v89) = 0;
          LODWORD(v90) = v68;
          if ( (_DWORD)xmmword_180169738 )
          {
            if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v110, v69);
              do
                v25 = v110[++v67] == 0;
              while ( !v25 );
              goto LABEL_173;
            }
          }
        }
        goto LABEL_60;
      }
    }
    VariantClear(&pvarg);
    pvarg.llVal = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v94 + 24LL))(v94, 1, &pvarg, 0);
    v7 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v89) = 0;
      LODWORD(v90) = v27;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v113, v13);
        v28 = -1;
        do
          v25 = v113[++v28] == 0;
        while ( !v25 );
        goto LABEL_173;
      }
      goto LABEL_60;
    }
  }
  LODWORD(v89) = 0;
  LODWORD(v90) = v17;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v116, v18);
    do
      v25 = v116[++v16] == 0;
    while ( !v25 );
    goto LABEL_173;
  }
LABEL_60:
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( v93 )
  {
    (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
    v93 = 0;
  }
  if ( v94 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    v94 = 0;
  }
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007940  mov     r11, rsp
0x180007943  push    rbp
0x180007944  push    rbx
0x180007945  lea     rbp, [r11-0E68h]
0x18000794c  sub     rsp, 0F58h
0x180007953  mov     rax, cs:__security_cookie
0x18000795a  xor     rax, rsp
0x18000795d  mov     [rbp+0E60h+var_40], rax
0x180007964  mov     [r11+18h], rsi
0x180007968  xor     ebx, ebx
0x18000796a  mov     [r11-20h], r12
0x18000796e  xorps   xmm0, xmm0
0x180007971  mov     [r11-30h], r14
0x180007975  xor     eax, eax
0x180007977  mov     r14, rcx
0x18000797a  mov     qword ptr [rbp+0E60h+pvarg+10h], rax
0x18000797e  lea     rcx, [rbp+0E60h+pvarg]; pvarg
0x180007982  mov     [rbp+0E60h+var_E90], rbx
0x180007986  mov     rsi, rdx
0x180007989  mov     [rbp+0E60h+var_EB8], rbx
0x18000798d  movups  xmmword ptr [rbp+0E60h+pvarg], xmm0
0x180007991  mov     [rbp+0E60h+var_EC0], rbx
0x180007995  call    cs:__imp_VariantInit
0x18000799b  mov     rax, [r14]
0x18000799e  lea     rdx, [rbp+0E60h+var_E90]
0x1800079a2  mov     rcx, r14
0x1800079a5  mov     qword ptr [rbp+0E60h+pvarg+8], rbx
0x1800079a9  mov     rax, [rax+48h]
0x1800079ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b2  mov     ebx, eax
0x1800079b4  test    eax, eax
0x1800079b6  js      loc_18000806B
0x1800079bc  mov     rcx, [rbp+0E60h+var_E90]
0x1800079c0  lea     r8, [rbp+0E60h+var_EB8]
0x1800079c4  lea     rdx, IID_IEnumVARIANT
0x1800079cb  mov     rax, [rcx]
0x1800079ce  mov     rax, [rax]
0x1800079d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d6  mov     ebx, eax
0x1800079d8  test    eax, eax
0x1800079da  js      loc_180008F7B
0x1800079e0  mov     rcx, [rbp+0E60h+var_EB8]
0x1800079e4  mov     rax, [rcx]
0x1800079e7  mov     rax, [rax+28h]
0x1800079eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f0  mov     ebx, eax
0x1800079f2  test    eax, eax
0x1800079f4  js      loc_180008FB0
0x1800079fa  lea     rcx, [rbp+0E60h+pvarg]; pvarg
0x1800079fe  mov     [rsp+0F50h], rdi
0x180007a06  call    cs:__imp_VariantClear
0x180007a0c  mov     rcx, [rbp+0E60h+var_EB8]
0x180007a10  lea     r8, [rbp+0E60h+pvarg]
0x180007a14  xor     edi, edi
0x180007a16  xor     r9d, r9d
0x180007a19  mov     qword ptr [rbp+0E60h+pvarg+8], rdi
0x180007a1d  mov     edx, 1
0x180007a22  mov     rax, [rcx]
0x180007a25  mov     rax, [rax+18h]
0x180007a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a2e  mov     ebx, eax
0x180007a30  test    eax, eax
0x180007a32  js      loc_180008FE5
0x180007a38  mov     [rsp+0F60h+var_20], r13
0x180007a40  mov     r12, 4000000000000800h
0x180007a4a  mov     [rsp+0F60h+var_30], r15
0x180007a52  xor     r15d, r15d
0x180007a55  xor     r13d, r13d
0x180007a58  mov     eax, 9
0x180007a5d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007a64  cmp     ebx, 1
0x180007a67  jz      loc_180007D25
0x180007a6d  cmp     ax, word ptr [rbp+0E60h+pvarg]
0x180007a71  jnz     loc_1800090EE
0x180007a77  mov     rcx, [rbp+0E60h+var_EC0]
0x180007a7b  test    rcx, rcx
0x180007a7e  jz      short loc_180007A94
0x180007a80  mov     rax, [rcx]
0x180007a83  mov     rax, [rax+10h]
0x180007a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8c  mov     [rbp+0E60h+var_EC0], 0
0x180007a94  mov     rcx, qword ptr [rbp+0E60h+pvarg+8]
0x180007a98  lea     r8, [rbp+0E60h+var_EC0]
0x180007a9c  lea     rdx, IID_IValueMapItem
0x180007aa3  mov     rax, [rcx]
0x180007aa6  mov     rax, [rax]
0x180007aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aae  mov     ebx, eax
0x180007ab0  test    eax, eax
0x180007ab2  js      loc_1800090C3
0x180007ab8  movzx   eax, word ptr [rsi]
0x180007abb  xor     ecx, ecx; bstrString
0x180007abd  mov     rbx, [rbp+0E60h+var_EC0]
0x180007ac1  mov     [rbp+0E60h+bstrString], rcx
0x180007ac5  cmp     ax, 15h
0x180007ac9  jnz     loc_180007BFB
0x180007acf  xor     eax, eax
0x180007ad1  lea     rdx, [rbp+0E60h+pvargSrc]
0x180007ad5  mov     qword ptr [rbp+0E60h+pvargSrc+10h], rax
0x180007ad9  xorps   xmm0, xmm0
0x180007adc  mov     rax, [rbx]
0x180007adf  mov     rcx, rbx
0x180007ae2  movups  xmmword ptr [rbp+0E60h+pvargSrc], xmm0
0x180007ae6  mov     rax, [rax+68h]
0x180007aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aef  mov     edi, eax
0x180007af1  test    eax, eax
0x180007af3  js      loc_180007FC4
0x180007af9  mov     eax, 15h
0x180007afe  cmp     ax, word ptr [rbp+0E60h+pvargSrc]
0x180007b02  jnz     loc_1800083ED
0x180007b08  mov     rbx, qword ptr [rbp+0E60h+pvargSrc+8]
0x180007b0c  lea     rcx, [rbp+0E60h+pvargSrc]; pvarg
0x180007b10  call    cs:__imp_VariantClear
0x180007b16  xor     ecx, ecx
0x180007b18  cmp     rbx, [rsi+8]
0x180007b1c  mov     r15d, ecx
0x180007b1f  mov     ebx, edi
0x180007b21  setz    r15b
0x180007b25  mov     rdi, [rbp+0E60h+bstrString]
0x180007b29  test    rdi, rdi
0x180007b2c  jnz     loc_180007CEF
0x180007b32  test    ebx, ebx
0x180007b34  js      loc_180009098
0x180007b3a  mov     ecx, [r14+58h]
0x180007b3e  sub     ecx, 1
0x180007b41  jz      loc_18000826A
0x180007b47  cmp     ecx, 1
0x180007b4a  jnz     loc_18000903D
0x180007b50  test    r15d, r15d
0x180007b53  jnz     loc_1800084A0
0x180007b59  lea     rcx, [rbp+0E60h+pvarg]; pvarg
0x180007b5d  call    cs:__imp_VariantClear
0x180007b63  mov     rcx, [rbp+0E60h+var_EB8]
0x180007b67  lea     r8, [rbp+0E60h+pvarg]
0x180007b6b  xor     edi, edi
0x180007b6d  xor     r9d, r9d
0x180007b70  mov     qword ptr [rbp+0E60h+pvarg+8], rdi
0x180007b74  mov     edx, 1
0x180007b79  mov     rax, [rcx]
0x180007b7c  mov     rax, [rax+18h]
0x180007b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b85  mov     ebx, eax
0x180007b87  test    eax, eax
0x180007b89  jns     loc_180007A58
0x180007b8f  cmp     dword ptr cs:xmmword_180169738, edi
0x180007b95  mov     dword ptr [rsp+0F60h+var_EF0], edi
0x180007b99  mov     dword ptr [rsp+0F60h+var_EE8], eax
0x180007b9d  jz      loc_180007F18
0x180007ba3  test    qword ptr cs:xmmword_180169738+8, r12
0x180007baa  jz      loc_180007F18
0x180007bb0  mov     rax, cs:qword_180169748
0x180007bb7  and     rax, r12
0x180007bba  cmp     cs:qword_180169748, rax
0x180007bc1  jnz     loc_180007F18
0x180007bc7  lea     rcx, [rbp+0E60h+var_840]; unsigned __int16 *
0x180007bce  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180007bd3  lea     rcx, [rbp+0E60h+var_840]
0x180007bda  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007be1  cmp     [rcx+rax*2+2], di
0x180007be6  lea     rax, [rax+1]
0x180007bea  jnz     short loc_180007BE1
0x180007bec  lea     ecx, [rax+rax]
0x180007bef  lea     rax, [rbp+0E60h+var_840]
0x180007bf6  jmp     loc_180008529
0x180007bfb  cmp     ax, 8
0x180007bff  jz      loc_1800091D0
0x180007c05  cmp     dword ptr cs:xmmword_180169738, ecx
0x180007c0b  mov     ebx, 8007065Dh
0x180007c10  mov     dword ptr [rsp+0F60h+var_EE8], ebx
0x180007c14  mov     dword ptr [rsp+0F60h+var_EF0], ecx
0x180007c18  jz      loc_180007B25
0x180007c1e  test    qword ptr cs:xmmword_180169738+8, r12
0x180007c25  jz      loc_180007B25
0x180007c2b  mov     rax, cs:qword_180169748
0x180007c32  and     rax, r12
0x180007c35  cmp     cs:qword_180169748, rax
0x180007c3c  jnz     loc_180007B25
0x180007c42  lea     rcx, [rbp+0E60h+var_C40]; unsigned __int16 *
0x180007c49  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180007c4e  lea     rcx, [rbp+0E60h+var_C40]
0x180007c55  mov     rax, rdi
0x180007c58  nop     dword ptr [rax+rax+00000000h]
0x180007c60  cmp     word ptr [rcx+rax*2+2], 0
0x180007c66  lea     rax, [rax+1]
0x180007c6a  jnz     short loc_180007C60
0x180007c6c  lea     ecx, [rax+rax]
0x180007c6f  lea     rax, [rbp+0E60h+var_C40]
0x180007c76  add     rcx, 2
0x180007c7a  lea     r9, [rsp+0F60h+var_EE8]
0x180007c7f  mov     [rsp+60h], rcx
0x180007c84  lea     rdx, PLA_EVENT_ERROR
0x180007c8b  mov     [rsp+0F60h+var_F08], rax
0x180007c90  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180007c97  mov     [rsp+0F60h+var_F10], 17h
0x180007ca0  lea     rax, aValuemapIsvalu; "ValueMap::IsValueEqual"
0x180007ca7  mov     [rsp+0F60h+var_F18], rax
0x180007cac  mov     r8d, 5
0x180007cb2  mov     [rsp+0F60h+var_F20], 4
0x180007cbb  lea     rax, [rsp+0F60h+var_EF0]
0x180007cc0  mov     [rsp+0F60h+var_F28], rax
0x180007cc5  lea     rax, byte_180147320
0x180007ccc  mov     [rsp+0F60h+var_F30], 1
0x180007cd5  mov     [rsp+0F60h+var_F38], rax
0x180007cda  mov     [rsp+0F60h+var_F40], 4
0x180007ce3  call    EventingWriteEvent
0x180007ce8  xor     ecx, ecx
0x180007cea  jmp     loc_180007B25
0x180007cef  cmp     dword ptr cs:xmmword_180169738, 0
0x180007cf6  mov     [rbp+0E60h+ppvData], rdi
0x180007cfa  mov     dword ptr [rsp+0F60h+var_EF0], ecx
0x180007cfe  jz      short loc_180007D17
0x180007d00  mov     rdx, 4000000000000200h
0x180007d0a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180007d11  jnz     loc_1800086CB
0x180007d17  mov     rcx, rdi; bstrString
0x180007d1a  call    cs:__imp_SysFreeString
0x180007d20  jmp     loc_180007B32
0x180007d25  test    r13d, r13d
0x180007d28  jnz     loc_180007F16
0x180007d2e  movaps  xmm0, xmmword ptr [rsi]
0x180007d31  lea     rcx, [rbp+0E60h+pvargSrc]; pvarg
0x180007d35  movsd   xmm1, qword ptr [rsi+10h]
0x180007d3a  xor     eax, eax
0x180007d3c  movaps  xmmword ptr [rbp+0E60h+pvargDest], xmm0
0x180007d40  xorps   xmm0, xmm0
0x180007d43  movups  xmmword ptr [rbp+0E60h+pvargSrc], xmm0
0x180007d47  mov     qword ptr [rbp+0E60h+pvargSrc+10h], rax
0x180007d4b  movsd   qword ptr [rbp+0E60h+pvargDest+10h], xmm1
0x180007d50  call    cs:__imp_VariantInit
0x180007d56  mov     qword ptr [rbp+0E60h+pvargSrc+8], 0
0x180007d5e  call    ??$CreateClassObject@VValueMapItem@@@@YAPEAVValueMapItem@@PEBDH@Z; CreateClassObject<ValueMapItem>(char const *,int)
0x180007d63  mov     rsi, rax
0x180007d66  test    rax, rax
0x180007d69  jz      loc_1800082FE
0x180007d6f  lea     rcx, [rbp+0E60h+pvargSrc]; pvarg
0x180007d73  call    cs:__imp_VariantClear
0x180007d79  mov     eax, 9
0x180007d7e  mov     qword ptr [rbp+0E60h+pvargSrc+8], rsi
0x180007d82  mov     word ptr [rbp+0E60h+pvargSrc], ax
0x180007d86  mov     rcx, rsi
0x180007d89  mov     rax, [rsi]
0x180007d8c  mov     rax, [rax+8]
0x180007d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d95  mov     rax, [rsi]
0x180007d98  mov     rcx, rsi
0x180007d9b  mov     edx, [r14+58h]
0x180007d9f  mov     rax, [rax+80h]
0x180007da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dab  mov     ebx, eax
0x180007dad  test    eax, eax
0x180007daf  js      loc_18000865A
0x180007db5  mov     rax, [rsi]
0x180007db8  mov     edx, edi
0x180007dba  mov     rcx, rsi
0x180007dbd  mov     rax, [rax+50h]
0x180007dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc6  mov     ebx, eax
0x180007dc8  test    eax, eax
0x180007dca  js      loc_18000815A
0x180007dd0  movzx   r9d, word ptr [r14+48h]; vt
0x180007dd5  lea     rdx, [rbp+0E60h+pvargDest]; pvarSrc
0x180007dd9  xor     r8d, r8d; wFlags
0x180007ddc  lea     rcx, [rbp+0E60h+pvargDest]; pvargDest
0x180007de0  call    cs:__imp_VariantChangeType
0x180007de6  mov     ebx, eax
0x180007de8  test    eax, eax
0x180007dea  js      loc_18000911E
0x180007df0  mov     rax, [rsi]
0x180007df3  lea     rdx, [rbp+0E60h+var_E60]
0x180007df7  movaps  xmm0, xmmword ptr [rbp+0E60h+pvargDest]
0x180007dfb  mov     rcx, rsi
0x180007dfe  movsd   xmm1, qword ptr [rbp+0E60h+pvargDest+10h]
0x180007e03  movaps  [rbp+0E60h+var_E60], xmm0
0x180007e07  mov     rax, [rax+70h]
0x180007e0b  movsd   [rbp+0E60h+var_E50], xmm1
0x180007e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e15  mov     ebx, eax
0x180007e17  test    eax, eax
0x180007e19  js      loc_180009149
0x180007e1f  mov     rdi, [r14+60h]
0x180007e23  lea     r13, aEnumeratorAdd; "Enumerator::Add"
0x180007e2a  xor     ebx, ebx
0x180007e2c  mov     [rsp+0F60h+var_EE8], rdi
0x180007e31  cmp     dword ptr cs:xmmword_180169738, ebx
0x180007e37  mov     [rbp+0E60h+ppvData], rbx
0x180007e3b  mov     eax, [rdi+38h]
0x180007e3e  mov     dword ptr [rsp+0F60h+var_EF0], eax
0x180007e42  mov     [rbp+0E60h+bstrString], rbx
0x180007e46  jz      short loc_180007E5F
0x180007e48  mov     rdx, 4000000000000400h
0x180007e52  test    qword ptr cs:xmmword_180169738+8, rdx
0x180007e59  jnz     loc_1800087FD
0x180007e5f  cmp     [rdi+8], ebx
0x180007e62  jz      short loc_180007E6E
0x180007e64  lea     rcx, [rdi+10h]; lpCriticalSection
0x180007e68  call    cs:__imp_EnterCriticalSection
0x180007e6e  mov     eax, [rdi+50h]
0x180007e71  cmp     [rdi+4Ch], eax
0x180007e74  jnb     loc_1800083A8
  ... truncated ...
```
