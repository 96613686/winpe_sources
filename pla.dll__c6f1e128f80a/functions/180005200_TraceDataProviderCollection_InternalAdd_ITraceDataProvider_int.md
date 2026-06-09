# TraceDataProviderCollection::InternalAdd(ITraceDataProvider *,int)

- ea: `0x180005200`
- end: `0x180005d5f`
- name: `?InternalAdd@TraceDataProviderCollection@@QEAAJPEAUITraceDataProvider@@H@Z`
- size: `2911`
- prototype: `__int64 __fastcall(TraceDataProviderCollection *__hidden this, struct ITraceDataProvider *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180005010`
- `0x1800c1ab0`
- `0x1800fa2a0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180005200`
- `0x180006170`
- `0x1800067b0`
- `0x18013ae76`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000544a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000554f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000544a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000554f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000526b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005383`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000526b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005383`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053c6`
- `OLEAUT32!__imp_VariantInit` at `0x180005285`
- `OLEAUT32!__imp_VariantInit` at `0x180005293`
- `OLEAUT32!__imp_VariantInit` at `0x180005285`
- `OLEAUT32!__imp_VariantInit` at `0x180005293`
- `OLEAUT32!__imp_VariantClear` at `0x180005559`
- `OLEAUT32!__imp_VariantClear` at `0x180005567`
- `OLEAUT32!__imp_VariantClear` at `0x180005559`
- `OLEAUT32!__imp_VariantClear` at `0x180005567`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800053ff`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800053ff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000545a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000545a`

## pseudocode

```c
__int64 __fastcall TraceDataProviderCollection::InternalAdd(
        TraceDataProviderCollection *this,
        struct ITraceDataProvider *a2,
        int a3)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // rsi
  int v8; // eax
  unsigned __int64 v9; // rdx
  int v10; // edi
  unsigned int v11; // r14d
  unsigned int i; // eax
  __int64 v13; // rbx
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  int v16; // eax
  unsigned __int64 v17; // rdx
  SAFEARRAY **v18; // rsi
  HRESULT v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  int v21; // eax
  int v22; // eax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  int v25; // eax
  unsigned __int64 v26; // rdx
  Enumerator *v27; // rcx
  int v28; // eax
  unsigned __int64 v29; // rdx
  __int64 v31; // rax
  bool v32; // zf
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // [rsp+50h] [rbp-B8h]
  __int64 v40; // [rsp+58h] [rbp-B0h]
  int v41; // [rsp+78h] [rbp-90h] BYREF
  int v42; // [rsp+80h] [rbp-88h] BYREF
  __int64 v43; // [rsp+88h] [rbp-80h] BYREF
  void *ppvData; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v45; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v48; // [rsp+D8h] [rbp-30h] BYREF
  __int128 Buf2; // [rsp+F8h] [rbp-10h] BYREF
  __int128 Buf1; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 v51[64]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v52[64]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v53[64]; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int16 v54[64]; // [rsp+298h] [rbp+190h] BYREF
  unsigned __int16 v55[64]; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int16 v56[64]; // [rsp+398h] [rbp+290h] BYREF
  unsigned __int16 v57[64]; // [rsp+418h] [rbp+310h] BYREF
  unsigned __int16 v58[64]; // [rsp+498h] [rbp+390h] BYREF
  unsigned __int16 v59[64]; // [rsp+518h] [rbp+410h] BYREF
  unsigned __int16 v60[64]; // [rsp+598h] [rbp+490h] BYREF

  v43 = 0;
  Buf2 = 0;
  Buf1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v45, 0, sizeof(v45));
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantInit(&v45);
  v45.llVal = 0;
  if ( *((_QWORD *)this + 9) )
  {
    v7 = -1;
    if ( a3 )
    {
LABEL_31:
      v25 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, GUID *, ULONG *))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IDispatch,
              &pvarg.decVal.Lo32);
      v10 = v25;
      if ( v25 < 0 )
      {
        v41 = 0;
        v42 = v25;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_33;
        }
        PlaiWhoAmI(v59, v26);
        do
          v32 = v59[++v7] == 0;
        while ( !v32 );
      }
      else
      {
        v27 = (Enumerator *)*((_QWORD *)this + 9);
        pvarg.vt = 9;
        v28 = Enumerator::Add(v27, &pvarg, 0);
        v10 = v28;
        if ( v28 >= 0 )
          goto LABEL_33;
        v41 = 0;
        v42 = v28;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_33;
        }
        PlaiWhoAmI(v60, v29);
        do
          v32 = v60[++v7] == 0;
        while ( !v32 );
      }
LABEL_57:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v42,
        4,
        qword_180147320,
        1,
        &v41,
        4,
        "TraceDataProviderCollection::InternalAdd",
        41);
      goto LABEL_33;
    }
    v8 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int128 *))a2->lpVtbl->get_Guid)(a2, &Buf1);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v11 = *(_DWORD *)(*((_QWORD *)this + 9) + 76LL);
      v45.vt = 19;
      for ( i = 0; ; i = v45.lVal + 1 )
      {
        v45.lVal = i;
        if ( i >= v11 )
          goto LABEL_31;
        if ( v43 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 16LL))(v43, 0x4000000000000400LL);
          v43 = 0;
        }
        v13 = *((_QWORD *)this + 9);
        v14 = *(_OWORD *)&v45.vt;
        ppvData = (void *)v13;
        pRecInfo = v45.pRecInfo;
        v41 = *(_DWORD *)(v13 + 56);
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
        {
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_METHOD,
            3,
            "Enumerator::GetItem",
            20,
            &ppvData,
            8,
            &v41,
            4,
            v39,
            v40);
        }
        if ( *(_DWORD *)(v13 + 8) )
          EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
        v41 = *(_DWORD *)(v13 + 56);
        v42 = 0;
        ppvData = 0;
        v47 = v13;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
        {
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_METHOD,
            3,
            "Enumerator::GetNamedItem",
            25,
            &v47,
            8,
            &v41,
            4,
            v39,
            v40);
        }
        if ( *(_DWORD *)(v13 + 8) )
          EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
        *(_OWORD *)&v48.vt = v14;
        v48.pRecInfo = pRecInfo;
        v16 = Enumerator::GetIndex<ITraceDataProvider>(v13, &v48, 0, (unsigned int *)&v42);
        v10 = v16;
        if ( v16 < 0 )
        {
          v41 = 0;
          v42 = v16;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v53, v17);
            v35 = -1;
            do
              v32 = v53[++v35] == 0;
            while ( !v32 );
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v42,
              4,
              qword_180147320,
              1,
              &v41,
              4,
              "Enumerator::GetNamedItem",
              25);
          }
          v18 = (SAFEARRAY **)(v13 + 64);
        }
        else
        {
          v18 = (SAFEARRAY **)(v13 + 64);
          v19 = SafeArrayAccessData(*(SAFEARRAY **)(v13 + 64), &ppvData);
          v10 = v19;
          if ( v19 < 0 )
          {
            v41 = 0;
            v42 = v19;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v54, v17);
              v36 = -1;
              do
                v32 = v54[++v36] == 0;
              while ( !v32 );
              goto LABEL_70;
            }
          }
          else
          {
            v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)ppvData + 3 * (unsigned int)v42 + 1);
            v21 = (**v20)(v20, &GUID_03837512_098b_11d8_9414_505054503030, &v43);
            v10 = v21;
            if ( v21 < 0 )
            {
              v41 = 0;
              v42 = v21;
              if ( (_DWORD)xmmword_180169738 )
              {
                if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v55, v17);
                  v37 = -1;
                  do
                    v32 = v55[++v37] == 0;
                  while ( !v32 );
LABEL_70:
                  EventingWriteEvent(
                    &g_Eventing,
                    PLA_EVENT_ERROR,
                    5,
                    &v42,
                    4,
                    qword_180147320,
                    1,
                    &v41,
                    4,
                    "Enumerator::GetNamedItem",
                    25);
                }
              }
            }
          }
        }
        if ( *(_DWORD *)(v13 + 8) )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
        if ( ppvData )
          SafeArrayUnaccessData(*v18);
        if ( *(_DWORD *)(v13 + 8) )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
        if ( v10 < 0 )
        {
          v42 = v10;
          v41 = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v58, v17);
            v33 = -1;
            do
              v32 = v58[++v33] == 0;
            while ( !v32 );
            goto LABEL_57;
          }
          goto LABEL_33;
        }
        v22 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v43 + 72LL))(v43, &Buf2);
        v10 = v22;
        if ( v22 < 0 )
        {
          v42 = v22;
          v41 = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v57, v23);
            v38 = -1;
            do
              v32 = v57[++v38] == 0;
            while ( !v32 );
            goto LABEL_57;
          }
          goto LABEL_33;
        }
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          v10 = -2144337651;
          v41 = 0;
          v42 = -2144337651;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v56, v24);
            v34 = -1;
            do
              v32 = v56[++v34] == 0;
            while ( !v32 );
            goto LABEL_57;
          }
          goto LABEL_33;
        }
        v7 = -1;
      }
    }
    v41 = 0;
    v42 = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v52, v9);
      do
        v32 = v52[++v7] == 0;
      while ( !v32 );
      goto LABEL_57;
    }
  }
  else
  {
    v10 = -2147024882;
    v41 = -2147024882;
    v42 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v51, v6);
      v31 = -1;
      do
        v32 = v51[++v31] == 0;
      while ( !v32 );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v41,
        4,
        qword_180147320,
        1,
        &v42,
        4,
        "TraceDataProviderCollection::InternalAdd",
        41);
    }
  }
LABEL_33:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&v45);
  v45.llVal = 0;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005200  mov     r11, rsp
0x180005203  push    rbp
0x180005204  lea     rbp, [r11-578h]
0x18000520b  sub     rsp, 670h
0x180005212  mov     rax, cs:__security_cookie
0x180005219  xor     rax, rsp
0x18000521c  mov     [rbp+570h+var_60], rax
0x180005223  mov     [r11+18h], rbx
0x180005227  xor     eax, eax
0x180005229  mov     [r11-10h], rsi
0x18000522d  xorps   xmm0, xmm0
0x180005230  xor     esi, esi
0x180005232  mov     [r11-20h], r12
0x180005236  xorps   xmm1, xmm1
0x180005239  mov     [r11-38h], r15
0x18000523d  mov     ebx, r8d
0x180005240  mov     r12, rdx
0x180005243  mov     r15, rcx
0x180005246  mov     [rbp+570h+var_5F0], rsi
0x18000524a  movups  [rbp+570h+Buf2], xmm0
0x18000524e  mov     qword ptr [rbp+570h+pvarg+10h], rax
0x180005252  movups  [rbp+570h+Buf1], xmm1
0x180005256  mov     qword ptr [rbp+570h+var_5E0+10h], rax
0x18000525a  movups  xmmword ptr [rbp+570h+pvarg], xmm0
0x18000525e  movups  xmmword ptr [rbp+570h+var_5E0], xmm1
0x180005262  cmp     [rcx+8], eax
0x180005265  jz      short loc_180005271
0x180005267  add     rcx, 10h; lpCriticalSection
0x18000526b  call    cs:__imp_EnterCriticalSection
0x180005271  mov     [rsp+670h+var_10], rdi
0x180005279  lea     rcx, [rbp+570h+pvarg]; pvarg
0x18000527d  mov     [rsp+670h+var_20], r13
0x180005285  call    cs:__imp_VariantInit
0x18000528b  lea     rcx, [rbp+570h+var_5E0]; pvarg
0x18000528f  mov     qword ptr [rbp+570h+pvarg+8], rsi
0x180005293  call    cs:__imp_VariantInit
0x180005299  mov     qword ptr [rbp+570h+var_5E0+8], rsi
0x18000529d  cmp     [r15+48h], rsi
0x1800052a1  jz      loc_1800055B8
0x1800052a7  mov     [rsp+670h+var_28], r14
0x1800052af  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800052b6  movaps  [rsp+670h+var_48+8], xmm6
0x1800052be  mov     r13, 4000000000000800h
0x1800052c8  movaps  [rsp+670h+var_58+8], xmm7
0x1800052d0  lea     r14, qword_180147320
0x1800052d7  test    ebx, ebx
0x1800052d9  jnz     loc_1800054CB
0x1800052df  mov     rax, [r12]
0x1800052e3  lea     rdx, [rbp+570h+Buf1]
0x1800052e7  mov     rcx, r12
0x1800052ea  mov     rax, [rax+48h]
0x1800052ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f3  mov     edi, eax
0x1800052f5  test    eax, eax
0x1800052f7  js      loc_180005C08
0x1800052fd  mov     rax, [r15+48h]
0x180005301  xor     edi, edi
0x180005303  mov     r14d, [rax+4Ch]
0x180005307  mov     eax, 13h
0x18000530c  mov     word ptr [rbp+570h+var_5E0], ax
0x180005310  mov     eax, edi
0x180005312  mov     dword ptr [rbp+570h+var_5E0+8], eax
0x180005315  mov     rdx, 4000000000000400h
0x18000531f  cmp     eax, r14d
0x180005322  jnb     loc_1800054C4
0x180005328  mov     rcx, [rbp+570h+var_5F0]
0x18000532c  test    rcx, rcx
0x18000532f  jz      short loc_18000534B
0x180005331  mov     rax, [rcx]
0x180005334  mov     rax, [rax+10h]
0x180005338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533d  mov     rdx, 4000000000000400h
0x180005347  mov     [rbp+570h+var_5F0], rdi
0x18000534b  cmp     dword ptr cs:xmmword_180169738, 0
0x180005352  mov     rbx, [r15+48h]
0x180005356  movups  xmm6, xmmword ptr [rbp+570h+var_5E0]
0x18000535a  mov     [rbp+570h+ppvData], rbx
0x18000535e  movsd   xmm7, qword ptr [rbp+570h+var_5E0+10h]
0x180005363  mov     eax, [rbx+38h]
0x180005366  mov     [rsp+670h+var_600], eax
0x18000536a  jz      short loc_180005379
0x18000536c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180005373  jnz     loc_18000569C
0x180005379  cmp     dword ptr [rbx+8], 0
0x18000537d  jz      short loc_180005389
0x18000537f  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005383  call    cs:__imp_EnterCriticalSection
0x180005389  cmp     dword ptr cs:xmmword_180169738, 0
0x180005390  mov     eax, [rbx+38h]
0x180005393  mov     [rsp+670h+var_600], eax
0x180005397  mov     [rsp+670h+var_5F8], edi
0x18000539b  mov     [rbp+570h+ppvData], rdi
0x18000539f  mov     [rbp+570h+var_5B0], rbx
0x1800053a3  jz      short loc_1800053BC
0x1800053a5  mov     rdx, 4000000000000400h
0x1800053af  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800053b6  jnz     loc_180005706
0x1800053bc  cmp     dword ptr [rbx+8], 0
0x1800053c0  jz      short loc_1800053CC
0x1800053c2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800053c6  call    cs:__imp_EnterCriticalSection
0x1800053cc  lea     r9, [rsp+670h+var_5F8]
0x1800053d1  movaps  [rbp+570h+var_5A0], xmm6
0x1800053d5  xor     r8d, r8d
0x1800053d8  movsd   [rbp+570h+var_590], xmm7
0x1800053dd  lea     rdx, [rbp+570h+var_5A0]
0x1800053e1  mov     rcx, rbx
0x1800053e4  call    ??$GetIndex@UITraceDataProvider@@@Enumerator@@IEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *),ulong *)
0x1800053e9  mov     edi, eax
0x1800053eb  test    eax, eax
0x1800053ed  js      loc_180005C33
0x1800053f3  mov     rcx, [rbx+40h]; psa
0x1800053f7  lea     rsi, [rbx+40h]
0x1800053fb  lea     rdx, [rbp+570h+ppvData]; ppvData
0x1800053ff  call    cs:__imp_SafeArrayAccessData
0x180005405  mov     edi, eax
0x180005407  test    eax, eax
0x180005409  js      loc_180005C5E
0x18000540f  mov     eax, [rsp+670h+var_5F8]
0x180005413  lea     r8, [rbp+570h+var_5F0]
0x180005417  lea     rdx, _GUID_03837512_098b_11d8_9414_505054503030
0x18000541e  lea     rcx, [rax+rax*2]
0x180005422  mov     rax, [rbp+570h+ppvData]
0x180005426  mov     rcx, [rax+rcx*8+8]
0x18000542b  mov     rax, [rcx]
0x18000542e  mov     rax, [rax]
0x180005431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005436  mov     edi, eax
0x180005438  test    eax, eax
0x18000543a  js      loc_180005C89
0x180005440  cmp     dword ptr [rbx+8], 0
0x180005444  jz      short loc_180005450
0x180005446  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000544a  call    cs:__imp_LeaveCriticalSection
0x180005450  cmp     [rbp+570h+ppvData], 0
0x180005455  jz      short loc_180005460
0x180005457  mov     rcx, [rsi]; psa
0x18000545a  call    cs:__imp_SafeArrayUnaccessData
0x180005460  cmp     dword ptr [rbx+8], 0
0x180005464  jz      short loc_180005470
0x180005466  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000546a  call    cs:__imp_LeaveCriticalSection
0x180005470  test    edi, edi
0x180005472  js      loc_180005770
0x180005478  mov     rcx, [rbp+570h+var_5F0]
0x18000547c  lea     rdx, [rbp+570h+Buf2]
0x180005480  mov     rax, [rcx]
0x180005483  mov     rax, [rax+48h]
0x180005487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000548c  mov     edi, eax
0x18000548e  test    eax, eax
0x180005490  js      loc_180005CE1
0x180005496  mov     r8d, 10h; Size
0x18000549c  lea     rdx, [rbp+570h+Buf2]; Buf2
0x1800054a0  lea     rcx, [rbp+570h+Buf1]; Buf1
0x1800054a4  call    memcmp_0
0x1800054a9  test    eax, eax
0x1800054ab  jz      loc_180005CB4
0x1800054b1  mov     eax, dword ptr [rbp+570h+var_5E0+8]
0x1800054b4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800054bb  inc     eax
0x1800054bd  xor     edi, edi
0x1800054bf  jmp     loc_180005312
0x1800054c4  lea     r14, qword_180147320
0x1800054cb  mov     rax, [r12]
0x1800054cf  lea     r8, [rbp+570h+pvarg+8]
0x1800054d3  lea     rdx, IID_IDispatch
0x1800054da  mov     rcx, r12
0x1800054dd  mov     rax, [rax]
0x1800054e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e5  mov     edi, eax
0x1800054e7  test    eax, eax
0x1800054e9  js      loc_180005D09
0x1800054ef  mov     rcx, [r15+48h]; this
0x1800054f3  lea     rdx, [rbp+570h+pvarg]; struct tagVARIANT *
0x1800054f7  mov     eax, 9
0x1800054fc  xor     r8d, r8d; int *
0x1800054ff  mov     word ptr [rbp+570h+pvarg], ax
0x180005503  call    ?Add@Enumerator@@QEAAJPEAUtagVARIANT@@PEAJ@Z; Enumerator::Add(tagVARIANT *,long *)
0x180005508  mov     edi, eax
0x18000550a  test    eax, eax
0x18000550c  js      loc_180005D34
0x180005512  xor     esi, esi
0x180005514  movaps  xmm6, [rsp+670h+var_48+8]
0x18000551c  mov     r14, [rsp+670h+var_28]
0x180005524  movaps  xmm7, [rsp+670h+var_58+8]
0x18000552c  cmp     dword ptr [r15+8], 0
0x180005531  mov     r13, [rsp+670h+var_20]
0x180005539  mov     r12, [rsp+670h+var_18]
0x180005541  mov     rbx, [rsp+670h+arg_10]
0x180005549  jz      short loc_180005555
0x18000554b  lea     rcx, [r15+10h]; lpCriticalSection
0x18000554f  call    cs:__imp_LeaveCriticalSection
0x180005555  lea     rcx, [rbp+570h+pvarg]; pvarg
0x180005559  call    cs:__imp_VariantClear
0x18000555f  lea     rcx, [rbp+570h+var_5E0]; pvarg
0x180005563  mov     qword ptr [rbp+570h+pvarg+8], rsi
0x180005567  call    cs:__imp_VariantClear
0x18000556d  mov     rcx, [rbp+570h+var_5F0]
0x180005571  mov     r15, [rsp+670h+var_30]
0x180005579  mov     qword ptr [rbp+570h+var_5E0+8], rsi
0x18000557d  mov     rsi, [rsp+668h]
0x180005585  test    rcx, rcx
0x180005588  jz      short loc_180005596
0x18000558a  mov     rax, [rcx]
0x18000558d  mov     rax, [rax+10h]
0x180005591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005596  mov     eax, edi
0x180005598  mov     rdi, [rsp+670h+var_10]
0x1800055a0  mov     rcx, [rbp+570h+var_60]
0x1800055a7  xor     rcx, rsp; StackCookie
0x1800055aa  call    __security_check_cookie
0x1800055af  add     rsp, 670h
0x1800055b6  pop     rbp
0x1800055b7  retn
0x1800055b8  cmp     dword ptr cs:xmmword_180169738, esi
0x1800055be  mov     edi, 8007000Eh
0x1800055c3  mov     [rsp+670h+var_600], edi
0x1800055c7  mov     [rsp+670h+var_5F8], esi
0x1800055cb  jz      loc_18000552C
0x1800055d1  mov     r13, 4000000000000800h
0x1800055db  test    qword ptr cs:xmmword_180169738+8, r13
0x1800055e2  jz      loc_18000552C
0x1800055e8  mov     rax, cs:qword_180169748
0x1800055ef  and     rax, r13
0x1800055f2  cmp     cs:qword_180169748, rax
0x1800055f9  jnz     loc_18000552C
0x1800055ff  lea     rcx, [rbp+570h+var_560]; unsigned __int16 *
0x180005603  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180005608  lea     rcx, [rbp+570h+var_560]
0x18000560c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005613  cmp     [rcx+rax*2+2], si
0x180005618  lea     rax, [rax+1]
0x18000561c  jnz     short loc_180005613
0x18000561e  lea     ecx, [rax+rax]
0x180005621  mov     r8d, 5
0x180005627  add     rcx, 2
0x18000562b  lea     rax, [rbp+570h+var_560]
0x18000562f  mov     [rsp+60h], rcx
0x180005634  lea     r9, [rsp+670h+var_600]
0x180005639  mov     [rsp+670h+var_618], rax
0x18000563e  lea     rdx, PLA_EVENT_ERROR
0x180005645  mov     [rsp+670h+var_620], 29h ; ')'
0x18000564e  lea     rax, aTracedataprovi_3; "TraceDataProviderCollection::InternalAd"...
0x180005655  mov     [rsp+670h+var_628], rax
0x18000565a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180005661  mov     [rsp+670h+var_630], 4
0x18000566a  lea     rax, [rsp+670h+var_5F8]
0x18000566f  mov     [rsp+670h+var_638], rax
0x180005674  lea     rax, qword_180147320
0x18000567b  mov     [rsp+670h+var_640], 1
0x180005684  mov     [rsp+670h+var_648], rax
0x180005689  mov     [rsp+670h+var_650], 4
0x180005692  call    EventingWriteEvent
0x180005697  jmp     loc_18000552C
0x18000569c  mov     rax, cs:qword_180169748
0x1800056a3  and     rax, rdx
0x1800056a6  cmp     cs:qword_180169748, rax
0x1800056ad  jnz     loc_180005379
0x1800056b3  mov     [rsp+670h+var_630], 4
0x1800056bc  lea     rax, [rsp+670h+var_600]
0x1800056c1  mov     [rsp+670h+var_638], rax
0x1800056c6  lea     r9, aEnumeratorGeti; "Enumerator::GetItem"
0x1800056cd  lea     rax, [rbp+570h+ppvData]
0x1800056d1  mov     [rsp+670h+var_640], 8
0x1800056da  mov     [rsp+670h+var_648], rax
0x1800056df  lea     rdx, PLA_EVENT_METHOD
0x1800056e6  mov     r8d, 3
0x1800056ec  mov     [rsp+670h+var_650], 14h
0x1800056f5  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800056fc  call    EventingWriteEvent
0x180005701  jmp     loc_180005379
0x180005706  mov     rax, cs:qword_180169748
0x18000570d  and     rax, rdx
0x180005710  cmp     cs:qword_180169748, rax
0x180005717  jnz     loc_1800053BC
0x18000571d  mov     [rsp+670h+var_630], 4
0x180005726  lea     rax, [rsp+670h+var_600]
0x18000572b  mov     [rsp+670h+var_638], rax
0x180005730  lea     r9, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180005737  lea     rax, [rbp+570h+var_5B0]
0x18000573b  mov     [rsp+670h+var_640], 8
0x180005744  mov     [rsp+670h+var_648], rax
0x180005749  lea     rdx, PLA_EVENT_METHOD
0x180005750  mov     r8d, 3
0x180005756  mov     [rsp+670h+var_650], 19h
0x18000575f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180005766  call    EventingWriteEvent
0x18000576b  jmp     loc_1800053BC
0x180005770  xor     esi, esi
0x180005772  mov     [rsp+670h+var_5F8], edi
0x180005776  cmp     dword ptr cs:xmmword_180169738, esi
0x18000577c  mov     [rsp+670h+var_600], esi
0x180005780  jz      loc_180005514
0x180005786  test    qword ptr cs:xmmword_180169738+8, r13
0x18000578d  jz      loc_180005514
0x180005793  mov     rax, cs:qword_180169748
0x18000579a  and     rax, r13
0x18000579d  cmp     cs:qword_180169748, rax
0x1800057a4  jnz     loc_180005514
  ... truncated ...
```
