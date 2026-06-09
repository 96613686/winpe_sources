# DataCollectorCollection::Add(IDataCollector *)

- ea: `0x18002df20`
- end: `0x18002eaa6`
- name: `?Add@DataCollectorCollection@@UEAAJPEAUIDataCollector@@@Z`
- size: `2950`
- prototype: `__int64 __fastcall(DataCollectorCollection *__hidden this, struct IDataCollector *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002df20`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e12c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e196`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e12c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dfb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e0bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dfb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e0bc`
- `OLEAUT32!__imp_VariantInit` at `0x18002dfc8`
- `OLEAUT32!__imp_VariantInit` at `0x18002dfc8`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfe0`
- `OLEAUT32!__imp_VariantClear` at `0x18002e026`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1a0`
- `OLEAUT32!__imp_VariantClear` at `0x18002dfe0`
- `OLEAUT32!__imp_VariantClear` at `0x18002e026`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1a0`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e108`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e108`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e35c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e35c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002e0e4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002e0e4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002e13c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002e13c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18002e431`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18002e431`

## pseudocode

```c
__int64 __fastcall DataCollectorCollection::Add(DataCollectorCollection *this, struct IDataCollector *a2)
{
  int v4; // eax
  unsigned __int64 v5; // rdx
  struct IDataCollectorVtbl *lpVtbl; // rax
  int v7; // eax
  unsigned __int64 v8; // rdx
  unsigned int v9; // edi
  struct IDataCollectorVtbl *v10; // rax
  int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned int v16; // edi
  __int64 v17; // rsi
  unsigned int v18; // eax
  SAFEARRAY **v19; // r15
  HRESULT v20; // eax
  unsigned __int64 v21; // rdx
  int v22; // r12d
  HRESULT v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rdx
  __int64 v27; // rax
  bool v28; // zf
  __int64 v29; // rax
  SAFEARRAY *v30; // rcx
  SAFEARRAY *v31; // rax
  __int64 v32; // rax
  HRESULT v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  int (__fastcall *v42)(DataCollectorCollection *, VARIANTARG *, __int64 *); // rax
  unsigned __int64 v43; // rdx
  __int64 v44; // [rsp+50h] [rbp-B8h]
  __int64 v45; // [rsp+58h] [rbp-B0h]
  int v46; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v47; // [rsp+80h] [rbp-88h] BYREF
  __int64 v48; // [rsp+88h] [rbp-80h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+90h] [rbp-78h] BYREF
  void *ppvData; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v53; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 v54[64]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 v55[64]; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int16 v56[64]; // [rsp+1E8h] [rbp+E0h] BYREF
  unsigned __int16 v57[64]; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int16 v58[64]; // [rsp+2E8h] [rbp+1E0h] BYREF
  unsigned __int16 v59[64]; // [rsp+368h] [rbp+260h] BYREF
  unsigned __int16 v60[64]; // [rsp+3E8h] [rbp+2E0h] BYREF
  unsigned __int16 v61[64]; // [rsp+468h] [rbp+360h] BYREF
  unsigned __int16 v62[64]; // [rsp+4E8h] [rbp+3E0h] BYREF
  unsigned __int16 v63[64]; // [rsp+568h] [rbp+460h] BYREF
  unsigned __int16 v64[64]; // [rsp+5E8h] [rbp+4E0h] BYREF

  v4 = *((_DWORD *)this + 14);
  memset(&pvarg, 0, sizeof(pvarg));
  v52 = 0;
  LODWORD(v48) = v4;
  ppvData = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "DataCollectorCollection::Add",
      29,
      &ppvData,
      8,
      &v48,
      4,
      v44,
      v45);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v9 = -2147024882;
    v46 = -2147024882;
    LODWORD(v48) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v54, v5);
      v35 = -1;
      do
        v28 = v54[++v35] == 0;
      while ( !v28 );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v46,
        4,
        qword_180147320,
        1,
        &v48,
        4,
        "DataCollectorCollection::Add",
        29);
    }
    goto LABEL_26;
  }
  VariantClear(&pvarg);
  lpVtbl = a2->lpVtbl;
  pvarg.llVal = 0;
  v7 = ((__int64 (__fastcall *)(struct IDataCollector *, CY *))lpVtbl->get_Name)(a2, &pvarg.cyVal);
  v9 = v7;
  if ( v7 < 0 )
  {
    v46 = 0;
    LODWORD(v48) = v7;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v55, v8);
      v29 = -1;
      do
        v28 = v55[++v29] == 0;
      while ( !v28 );
      goto LABEL_42;
    }
    goto LABEL_26;
  }
  pvarg.vt = 8;
  if ( !pvarg.llVal
    || !*pvarg.bstrVal
    || (v42 = *(int (__fastcall **)(DataCollectorCollection *, VARIANTARG *, __int64 *))(*(_QWORD *)this + 64LL),
        v53 = pvarg,
        v42(this, &v53, &v52) < 0) )
  {
    VariantClear(&pvarg);
    v10 = a2->lpVtbl;
    pvarg.llVal = 0;
    v11 = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, CY *))v10->QueryInterface)(
            a2,
            &IID_IDispatch,
            &pvarg.cyVal);
    v9 = v11;
    if ( v11 < 0 )
    {
      v46 = 0;
      LODWORD(v48) = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_26;
      }
      PlaiWhoAmI(v57, v12);
      v32 = -1;
      do
        v28 = v57[++v32] == 0;
      while ( !v28 );
    }
    else
    {
      v13 = *((_QWORD *)this + 10);
      pvarg.vt = 9;
      if ( !v13
        || (v14 = ((__int64 (__fastcall *)(struct IDataCollector *))a2->lpVtbl->put_DataCollectorSet)(a2),
            v9 = v14,
            v14 >= 0) )
      {
        v16 = 0;
        v17 = *((_QWORD *)this + 9);
        v47 = 0;
        ppvData = 0;
        rgsabound = 0;
        v46 = *(_DWORD *)(v17 + 56);
        v48 = v17;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
        {
          EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::Add", 16, &v48, 8, &v46, 4, v44, v45);
        }
        if ( *(_DWORD *)(v17 + 8) )
          EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
        v18 = *(_DWORD *)(v17 + 80);
        if ( *(_DWORD *)(v17 + 76) >= v18 )
        {
          v30 = *(SAFEARRAY **)(v17 + 64);
          rgsabound.lLbound = 0;
          v19 = (SAFEARRAY **)(v17 + 64);
          rgsabound.cElements = v18 + 16;
          if ( v30 )
          {
            v33 = SafeArrayRedim(v30, &rgsabound);
            v22 = v33;
            if ( v33 < 0 )
            {
              v46 = 0;
              LODWORD(v48) = v33;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v59, v21);
                v34 = -1;
                do
                  v28 = v59[++v34] == 0;
                while ( !v28 );
                EventingWriteEvent(
                  &g_Eventing,
                  PLA_EVENT_ERROR,
                  5,
                  &v48,
                  4,
                  qword_180147320,
                  1,
                  &v46,
                  4,
                  "Enumerator::Add",
                  16);
              }
              goto LABEL_20;
            }
          }
          else
          {
            v31 = SafeArrayCreate(0xCu, 1u, &rgsabound);
            *v19 = v31;
            if ( !v31 )
            {
              v22 = -2147024882;
              LODWORD(v48) = -2147024882;
              v46 = 0;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v60, v21);
                v37 = -1;
                do
                  v28 = v60[++v37] == 0;
                while ( !v28 );
                EventingWriteEvent(
                  &g_Eventing,
                  PLA_EVENT_ERROR,
                  5,
                  &v48,
                  4,
                  qword_180147320,
                  1,
                  &v46,
                  4,
                  "Enumerator::Add",
                  16);
              }
              v16 = v47;
              goto LABEL_20;
            }
          }
          *(_DWORD *)(v17 + 80) = rgsabound.cElements;
        }
        v19 = (SAFEARRAY **)(v17 + 64);
        v20 = SafeArrayAccessData(*(SAFEARRAY **)(v17 + 64), &ppvData);
        v22 = v20;
        if ( v20 < 0 )
        {
          v47 = 0;
          v46 = v20;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v61, v21);
            v38 = -1;
            do
              v28 = v61[++v38] == 0;
            while ( !v28 );
            goto LABEL_83;
          }
        }
        else
        {
          v23 = VariantCopy((VARIANTARG *)ppvData + *(unsigned int *)(v17 + 76), &pvarg);
          v22 = v23;
          if ( v23 >= 0 )
          {
            v16 = *(_DWORD *)(v17 + 76);
            *(_DWORD *)(v17 + 76) = v16 + 1;
            goto LABEL_20;
          }
          v47 = 0;
          v46 = v23;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v62, v21);
            v27 = -1;
            do
              v28 = v62[++v27] == 0;
            while ( !v28 );
LABEL_83:
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v46,
              4,
              qword_180147320,
              1,
              &v47,
              4,
              "Enumerator::Add",
              16);
          }
        }
LABEL_20:
        if ( *(_DWORD *)(v17 + 8) )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
        if ( ppvData )
          SafeArrayUnaccessData(*v19);
        if ( v22 < 0 )
        {
          v46 = v22;
          v9 = v22;
          v47 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_26;
          }
          PlaiWhoAmI(v63, v21);
          v36 = -1;
          do
            v28 = v63[++v36] == 0;
          while ( !v28 );
        }
        else
        {
          v24 = ((__int64 (__fastcall *)(struct IDataCollector *, _QWORD))a2->lpVtbl->put_Index)(a2, v16);
          v9 = v24;
          if ( v24 >= 0 )
            goto LABEL_26;
          v47 = 0;
          v46 = v24;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_26;
          }
          PlaiWhoAmI(v64, v25);
          v41 = -1;
          do
            v28 = v64[++v41] == 0;
          while ( !v28 );
        }
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v46,
          4,
          qword_180147320,
          1,
          &v47,
          4,
          "DataCollectorCollection::Add",
          29);
        goto LABEL_26;
      }
      v46 = 0;
      LODWORD(v48) = v14;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_26;
      }
      PlaiWhoAmI(v58, v15);
      v40 = -1;
      do
        v28 = v58[++v40] == 0;
      while ( !v28 );
    }
LABEL_42:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v48,
      4,
      qword_180147320,
      1,
      &v46,
      4,
      "DataCollectorCollection::Add",
      29);
    goto LABEL_26;
  }
  v9 = -2144337655;
  LODWORD(v48) = -2144337655;
  v46 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v56, v43);
    v39 = -1;
    do
      v28 = v56[++v39] == 0;
    while ( !v28 );
    goto LABEL_42;
  }
LABEL_26:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  return v9;
}

```

## disassembly

```asm
0x18002df20  mov     r11, rsp
0x18002df23  push    rbp
0x18002df24  lea     rbp, [r11-5A8h]
0x18002df2b  sub     rsp, 6A0h
0x18002df32  mov     rax, cs:__security_cookie
0x18002df39  xor     rax, rsp
0x18002df3c  mov     [rbp+5A0h+var_40], rax
0x18002df43  mov     [r11+18h], rbx
0x18002df47  xor     eax, eax
0x18002df49  mov     [r11-10h], rsi
0x18002df4d  xorps   xmm0, xmm0
0x18002df50  mov     [r11-20h], r12
0x18002df54  lea     rsi, aDatacollectorc_10; "DataCollectorCollection::Add"
0x18002df5b  mov     [r11-28h], r13
0x18002df5f  mov     rbx, rcx
0x18002df62  mov     [r11-30h], r14
0x18002df66  mov     r12, 4000000000000400h
0x18002df70  mov     [r11-38h], r15
0x18002df74  mov     r14, rdx
0x18002df77  xor     r15d, r15d
0x18002df7a  mov     qword ptr [rbp+5A0h+pvarg+10h], rax
0x18002df7e  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002df85  mov     r13d, 8
0x18002df8b  mov     eax, [rcx+38h]
0x18002df8e  movups  xmmword ptr [rbp+5A0h+pvarg], xmm0
0x18002df92  mov     [rbp+5A0h+var_5F0], r15
0x18002df96  mov     dword ptr [rbp+5A0h+var_620], eax
0x18002df99  mov     [rbp+5A0h+ppvData], rcx
0x18002df9d  jz      short loc_18002DFAC
0x18002df9f  test    qword ptr cs:xmmword_180169738+8, r12
0x18002dfa6  jnz     loc_18002E5BD
0x18002dfac  cmp     [rbx+8], r15d
0x18002dfb0  jz      short loc_18002DFBC
0x18002dfb2  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002dfb6  call    cs:__imp_EnterCriticalSection
0x18002dfbc  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x18002dfc0  mov     [rsp+6A0h+var_10], rdi
0x18002dfc8  call    cs:__imp_VariantInit
0x18002dfce  mov     qword ptr [rbp+5A0h+pvarg+8], r15
0x18002dfd2  cmp     [rbx+48h], r15
0x18002dfd6  jz      loc_18002E51E
0x18002dfdc  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x18002dfe0  call    cs:__imp_VariantClear
0x18002dfe6  mov     rax, [r14]
0x18002dfe9  lea     rdx, [rbp+5A0h+pvarg+8]
0x18002dfed  mov     rcx, r14
0x18002dff0  mov     qword ptr [rbp+5A0h+pvarg+8], r15
0x18002dff4  mov     rax, [rax+0C0h]
0x18002dffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e000  mov     edi, eax
0x18002e002  test    eax, eax
0x18002e004  js      loc_18002E25A
0x18002e00a  mov     rcx, qword ptr [rbp+5A0h+pvarg+8]
0x18002e00e  mov     word ptr [rbp+5A0h+pvarg], r13w
0x18002e013  test    rcx, rcx
0x18002e016  jz      short loc_18002E022
0x18002e018  cmp     r15w, [rcx]
0x18002e01c  jnz     loc_18002EA5F
0x18002e022  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x18002e026  call    cs:__imp_VariantClear
0x18002e02c  mov     rax, [r14]
0x18002e02f  lea     r8, [rbp+5A0h+pvarg+8]
0x18002e033  lea     rdx, IID_IDispatch
0x18002e03a  mov     qword ptr [rbp+5A0h+pvarg+8], r15
0x18002e03e  mov     rcx, r14
0x18002e041  mov     rax, [rax]
0x18002e044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e049  mov     edi, eax
0x18002e04b  test    eax, eax
0x18002e04d  js      loc_18002E379
0x18002e053  mov     rdx, [rbx+50h]
0x18002e057  mov     eax, 9
0x18002e05c  mov     word ptr [rbp+5A0h+pvarg], ax
0x18002e060  test    rdx, rdx
0x18002e063  jz      short loc_18002E07E
0x18002e065  mov     rax, [r14]
0x18002e068  mov     rcx, r14
0x18002e06b  mov     rax, [rax+40h]
0x18002e06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e074  mov     edi, eax
0x18002e076  test    eax, eax
0x18002e078  js      loc_18002E9B1
0x18002e07e  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002e085  mov     edi, r15d
0x18002e088  mov     rsi, [rbx+48h]
0x18002e08c  mov     [rsp+6A0h+var_628], r15d
0x18002e091  mov     [rbp+5A0h+ppvData], r15
0x18002e095  mov     qword ptr [rbp+5A0h+rgsabound.cElements], r15
0x18002e099  mov     eax, [rsi+38h]
0x18002e09c  mov     [rsp+6A0h+var_630], eax
0x18002e0a0  mov     [rbp+5A0h+var_620], rsi
0x18002e0a4  jz      short loc_18002E0B3
0x18002e0a6  test    qword ptr cs:xmmword_180169738+8, r12
0x18002e0ad  jnz     loc_18002E61E
0x18002e0b3  cmp     [rsi+8], edi
0x18002e0b6  jz      short loc_18002E0C2
0x18002e0b8  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002e0bc  call    cs:__imp_EnterCriticalSection
0x18002e0c2  mov     eax, [rsi+50h]
0x18002e0c5  mov     r13, 4000000000000800h
0x18002e0cf  cmp     [rsi+4Ch], eax
0x18002e0d2  jnb     loc_18002E333
0x18002e0d8  mov     rcx, [rsi+40h]; psa
0x18002e0dc  lea     r15, [rsi+40h]
0x18002e0e0  lea     rdx, [rbp+5A0h+ppvData]; ppvData
0x18002e0e4  call    cs:__imp_SafeArrayAccessData
0x18002e0ea  mov     r12d, eax
0x18002e0ed  test    eax, eax
0x18002e0ef  js      loc_18002E9E2
0x18002e0f5  mov     eax, [rsi+4Ch]
0x18002e0f8  lea     rdx, [rbp+5A0h+pvarg]; pvargSrc
0x18002e0fc  lea     rcx, [rax+rax*2]
0x18002e100  mov     rax, [rbp+5A0h+ppvData]
0x18002e104  lea     rcx, [rax+rcx*8]; pvargDest
0x18002e108  call    cs:__imp_VariantCopy
0x18002e10e  mov     r12d, eax
0x18002e111  test    eax, eax
0x18002e113  js      loc_18002E1E9
0x18002e119  mov     edi, [rsi+4Ch]
0x18002e11c  lea     eax, [rdi+1]
0x18002e11f  mov     [rsi+4Ch], eax
0x18002e122  cmp     dword ptr [rsi+8], 0
0x18002e126  jz      short loc_18002E132
0x18002e128  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002e12c  call    cs:__imp_LeaveCriticalSection
0x18002e132  cmp     [rbp+5A0h+ppvData], 0
0x18002e137  jz      short loc_18002E142
0x18002e139  mov     rcx, [r15]; psa
0x18002e13c  call    cs:__imp_SafeArrayUnaccessData
0x18002e142  test    r12d, r12d
0x18002e145  js      loc_18002EA08
0x18002e14b  mov     rax, [r14]
0x18002e14e  mov     edx, edi
0x18002e150  mov     rcx, r14
0x18002e153  mov     rax, [rax+0E0h]
0x18002e15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e15f  xor     r15d, r15d
0x18002e162  mov     edi, eax
0x18002e164  test    eax, eax
0x18002e166  js      loc_18002EA37
0x18002e16c  cmp     dword ptr [rbx+8], 0
0x18002e170  mov     r14, [rsp+6A0h+var_28]
0x18002e178  mov     r13, [rsp+6A0h+var_20]
0x18002e180  mov     r12, [rsp+6A0h+var_18]
0x18002e188  mov     rsi, [rsp+698h]
0x18002e190  jz      short loc_18002E19C
0x18002e192  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002e196  call    cs:__imp_LeaveCriticalSection
0x18002e19c  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x18002e1a0  call    cs:__imp_VariantClear
0x18002e1a6  mov     rcx, [rbp+5A0h+var_5F0]
0x18002e1aa  mov     rbx, [rsp+6A0h+arg_10]
0x18002e1b2  mov     qword ptr [rbp+5A0h+pvarg+8], r15
0x18002e1b6  mov     r15, [rsp+6A0h+var_30]
0x18002e1be  test    rcx, rcx
0x18002e1c1  jnz     loc_18002EA95
0x18002e1c7  mov     eax, edi
0x18002e1c9  mov     rdi, [rsp+6A0h+var_10]
0x18002e1d1  mov     rcx, [rbp+5A0h+var_40]
0x18002e1d8  xor     rcx, rsp; StackCookie
0x18002e1db  call    __security_check_cookie
0x18002e1e0  add     rsp, 6A0h
0x18002e1e7  pop     rbp
0x18002e1e8  retn
0x18002e1e9  cmp     dword ptr cs:xmmword_180169738, edi
0x18002e1ef  mov     [rsp+6A0h+var_628], edi
0x18002e1f3  mov     [rsp+6A0h+var_630], eax
0x18002e1f7  jz      loc_18002E122
0x18002e1fd  test    qword ptr cs:xmmword_180169738+8, r13
0x18002e204  jz      loc_18002E122
0x18002e20a  mov     rax, cs:qword_180169748
0x18002e211  and     rax, r13
0x18002e214  cmp     cs:qword_180169748, rax
0x18002e21b  jnz     loc_18002E122
0x18002e221  lea     rcx, [rbp+5A0h+var_1C0]; unsigned __int16 *
0x18002e228  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002e22d  lea     rcx, [rbp+5A0h+var_1C0]
0x18002e234  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e23b  nop     dword ptr [rax+rax+00h]
0x18002e240  cmp     [rcx+rax*2+2], di
0x18002e245  lea     rax, [rax+1]
0x18002e249  jnz     short loc_18002E240
0x18002e24b  lea     ecx, [rax+rax]
0x18002e24e  lea     rax, [rbp+5A0h+var_1C0]
0x18002e255  jmp     loc_18002E815
0x18002e25a  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002e261  mov     [rsp+6A0h+var_630], r15d
0x18002e266  mov     dword ptr [rbp+5A0h+var_620], eax
0x18002e269  jz      loc_18002E16C
0x18002e26f  mov     r13, 4000000000000800h
0x18002e279  test    qword ptr cs:xmmword_180169738+8, r13
0x18002e280  jz      loc_18002E16C
0x18002e286  mov     rax, cs:qword_180169748
0x18002e28d  and     rax, r13
0x18002e290  cmp     cs:qword_180169748, rax
0x18002e297  jnz     loc_18002E16C
0x18002e29d  lea     rcx, [rbp+5A0h+var_540]; unsigned __int16 *
0x18002e2a1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002e2a6  lea     rcx, [rbp+5A0h+var_540]
0x18002e2aa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e2b1  cmp     [rcx+rax*2+2], r15w
0x18002e2b7  lea     rax, [rax+1]
0x18002e2bb  jnz     short loc_18002E2B1
0x18002e2bd  lea     ecx, [rax+rax]
0x18002e2c0  lea     rax, [rbp+5A0h+var_540]
0x18002e2c4  add     rcx, 2
0x18002e2c8  lea     r9, [rbp+5A0h+var_620]
0x18002e2cc  mov     [rsp+60h], rcx
0x18002e2d1  mov     [rsp+6A0h+var_648], rax
0x18002e2d6  lea     rax, [rsp+6A0h+var_630]
0x18002e2db  mov     [rsp+6A0h+var_650], 1Dh
0x18002e2e4  mov     [rsp+6A0h+var_658], rsi
0x18002e2e9  mov     [rsp+6A0h+var_660], 4
0x18002e2f2  lea     rdx, PLA_EVENT_ERROR
0x18002e2f9  mov     [rsp+6A0h+var_668], rax
0x18002e2fe  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002e305  lea     rax, qword_180147320
0x18002e30c  mov     [rsp+6A0h+var_670], 1
0x18002e315  mov     [rsp+6A0h+var_678], rax
0x18002e31a  mov     r8d, 5
0x18002e320  mov     [rsp+6A0h+var_680], 4
0x18002e329  call    EventingWriteEvent
0x18002e32e  jmp     loc_18002E16C
0x18002e333  mov     rcx, [rsi+40h]; psa
0x18002e337  add     eax, 10h
0x18002e33a  mov     [rbp+5A0h+rgsabound.lLbound], r15d
0x18002e33e  lea     r15, [rsi+40h]
0x18002e342  mov     [rbp+5A0h+rgsabound.cElements], eax
0x18002e345  test    rcx, rcx
0x18002e348  jnz     loc_18002E42D
0x18002e34e  mov     ecx, 0Ch; vt
0x18002e353  lea     r8, [rbp+5A0h+rgsabound]; rgsabound
0x18002e357  mov     edx, 1; cDims
0x18002e35c  call    cs:__imp_SafeArrayCreate
0x18002e362  mov     [r15], rax
0x18002e365  test    rax, rax
0x18002e368  jz      loc_18002E3FB
0x18002e36e  mov     eax, [rbp+5A0h+rgsabound.cElements]
0x18002e371  mov     [rsi+50h], eax
0x18002e374  jmp     loc_18002E0D8
0x18002e379  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002e380  mov     [rsp+6A0h+var_630], r15d
0x18002e385  mov     dword ptr [rbp+5A0h+var_620], eax
0x18002e388  jz      loc_18002E16C
0x18002e38e  mov     r13, 4000000000000800h
0x18002e398  test    qword ptr cs:xmmword_180169738+8, r13
0x18002e39f  jz      loc_18002E16C
0x18002e3a5  mov     rax, cs:qword_180169748
0x18002e3ac  and     rax, r13
0x18002e3af  cmp     cs:qword_180169748, rax
0x18002e3b6  jnz     loc_18002E16C
0x18002e3bc  lea     rcx, [rbp+5A0h+var_440]; unsigned __int16 *
0x18002e3c3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002e3c8  lea     rcx, [rbp+5A0h+var_440]
0x18002e3cf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e3d6  nop     word ptr [rax+rax+00000000h]
0x18002e3e0  cmp     [rcx+rax*2+2], r15w
0x18002e3e6  lea     rax, [rax+1]
0x18002e3ea  jnz     short loc_18002E3E0
0x18002e3ec  lea     ecx, [rax+rax]
0x18002e3ef  lea     rax, [rbp+5A0h+var_440]
0x18002e3f6  jmp     loc_18002E2C4
0x18002e3fb  cmp     dword ptr cs:xmmword_180169738, 0
0x18002e402  mov     edi, 8007000Eh
0x18002e407  mov     r12d, edi
0x18002e40a  mov     dword ptr [rbp+5A0h+var_620], edi
0x18002e40d  mov     [rsp+6A0h+var_630], 0
0x18002e415  jz      short loc_18002E424
0x18002e417  test    qword ptr cs:xmmword_180169738+8, r13
0x18002e41e  jnz     loc_18002E708
0x18002e424  mov     edi, [rsp+6A0h+var_628]
0x18002e428  jmp     loc_18002E122
0x18002e42d  lea     rdx, [rbp+5A0h+rgsabound]; psaboundNew
0x18002e431  call    cs:__imp_SafeArrayRedim
0x18002e437  mov     r12d, eax
0x18002e43a  test    eax, eax
0x18002e43c  jns     loc_18002E36E
0x18002e442  cmp     dword ptr cs:xmmword_180169738, edi
0x18002e448  mov     [rsp+6A0h+var_630], edi
0x18002e44c  mov     dword ptr [rbp+5A0h+var_620], eax
0x18002e44f  jz      loc_18002E122
0x18002e455  test    qword ptr cs:xmmword_180169738+8, r13
0x18002e45c  jz      loc_18002E122
0x18002e462  mov     rax, cs:qword_180169748
0x18002e469  and     rax, r13
0x18002e46c  cmp     cs:qword_180169748, rax
0x18002e473  jnz     loc_18002E122
0x18002e479  lea     rcx, [rbp+5A0h+var_340]; unsigned __int16 *
0x18002e480  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002e485  lea     rcx, [rbp+5A0h+var_340]
0x18002e48c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e493  cmp     [rcx+rax*2+2], di
0x18002e498  lea     rax, [rax+1]
0x18002e49c  jnz     short loc_18002E493
0x18002e49e  lea     ecx, [rax+rax]
0x18002e4a1  mov     r8d, 5
0x18002e4a7  add     rcx, 2
0x18002e4ab  lea     rax, [rbp+5A0h+var_340]
0x18002e4b2  mov     [rsp+60h], rcx
0x18002e4b7  lea     r9, [rbp+5A0h+var_620]
  ... truncated ...
```
