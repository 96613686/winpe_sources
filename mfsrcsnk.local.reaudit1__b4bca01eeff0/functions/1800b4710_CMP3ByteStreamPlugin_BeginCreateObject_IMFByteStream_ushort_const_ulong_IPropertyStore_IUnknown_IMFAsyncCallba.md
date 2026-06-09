# CMP3ByteStreamPlugin::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x1800b4710`
- end: `0x1800b4f07`
- name: `?BeginCreateObject@CMP3ByteStreamPlugin@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU4@@Z`
- size: `2039`
- prototype: `__int64 __fastcall(CMP3ByteStreamPlugin *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x18009faa0`
- `0x1800b4710`
- `0x1800eaac8`
- `0x180110ed0`
- `0x180154abc`
- `0x1801581e0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b47e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4893`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4957`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4a1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4afc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4ca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4dc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b47e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4893`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4957`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4a1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4afc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4ca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4dc5`
- `MFPlat!CreatePropertyStore` at `0x1800b4ad3`
- `MFPlat!CreatePropertyStore` at `0x1800b4ad3`

## string_xrefs

- `0x1800b475d`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4847`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b48f3`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b49b7`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4a7d`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4b55`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4c3d`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4d01`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800b4e1e`: `CMP3ByteStreamPlugin::BeginCreateObject`

## pseudocode

```c
__int64 __fastcall CMP3ByteStreamPlugin::BeginCreateObject(
        unsigned __int64 this,
        struct IMFByteStream *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct IPropertyStore *a5,
        struct IUnknown **a6,
        struct IMFAsyncCallback *a7,
        struct IUnknown *a8)
{
  __int64 v8; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  wchar_t *v13; // rbx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v15; // ebx
  __int128 v16; // xmm0
  int Instance; // edi
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  _QWORD *v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // rcx
  wchar_t *v26; // rbx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  CMP3BytewiseMediaSource **v30; // r12
  __int64 v31; // rdx
  __int64 v32; // rcx
  wchar_t *v33; // rbx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  IPropertyStore *v36; // rcx
  __int64 v37; // rdx
  HRESULT PropertyStore; // edi
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  int v43; // edi
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  unsigned int v52; // edx
  __int64 v53; // rdx
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct IUnknown **v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  _BYTE v61[4]; // [rsp+30h] [rbp-50h] BYREF
  int v62; // [rsp+34h] [rbp-4Ch] BYREF
  struct IMFByteStream *v63; // [rsp+38h] [rbp-48h]
  struct IUnknown **v64; // [rsp+40h] [rbp-40h]
  PROPVARIANT pvar; // [rsp+48h] [rbp-38h] BYREF
  IPropertyStore *ppStore[2]; // [rsp+60h] [rbp-20h] BYREF

  v8 = 0;
  v63 = a2;
  v64 = a6;
  v62 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMP3ByteStreamPlugin::BeginCreateObject", 82);
  v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(this + 48) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(this + 48) + 296LL))(*(_QWORD *)(this + 48));
    v16 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, IPropertyStore **))(**(_QWORD **)(this + 48) + 280LL))(
                       *(_QWORD *)(this + 48),
                       ppStore);
    *((_DWORD *)ThreadRelativeContext + 504) = v15;
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    *((_OWORD *)ThreadRelativeContext + 125) = v16;
  }
  if ( !a2 )
  {
    Instance = -2147467261;
    if ( !v13 )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v19 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v19, "CMP3ByteStreamPlugin::BeginCreateObject", 82, -2147467261);
    }
    if ( g_wppLevels )
    {
      v20 = 11;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids,
        this - 72,
        -2147467261);
      goto LABEL_106;
    }
    goto LABEL_106;
  }
  if ( a7 )
  {
    v23 = (_QWORD *)(this - 72);
    Instance = CMP3ByteStreamPluginResult::CreateInstance(
                 (struct IUnknown *)(this & -(__int64)(this != 72)),
                 a7,
                 a8,
                 (struct CMP3ByteStreamPluginResult **)(this + 32));
    if ( Instance < 0 )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != Instance )
          CallStackContext::TraceFailure(v28, "CMP3ByteStreamPlugin::BeginCreateObject", 86, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_106;
      v29 = 13;
      goto LABEL_105;
    }
    v8 = v23[13];
    if ( v8 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(v23[13]);
    v30 = (CMP3BytewiseMediaSource **)(this + 40);
    Instance = CMP3BytewiseMediaSource::Create((struct CMP3BytewiseMediaSource **)(this + 40));
    if ( Instance < 0 )
    {
      v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v32, v31);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != Instance )
          CallStackContext::TraceFailure(v35, "CMP3ByteStreamPlugin::BeginCreateObject", 91, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_106;
      v29 = 14;
      goto LABEL_105;
    }
    ppStore[0] = a5;
    if ( !a5 || (((void (__fastcall *)(struct IPropertyStore *))a5->lpVtbl->AddRef)(a5), (v36 = ppStore[0]) == 0) )
    {
      PropertyStore = CreatePropertyStore(ppStore);
      if ( PropertyStore < 0 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v41 + 499) != PropertyStore )
            CallStackContext::TraceFailure(v41, "CMP3ByteStreamPlugin::BeginCreateObject", 101, PropertyStore);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids,
            this - 72,
            PropertyStore);
        goto LABEL_91;
      }
      v36 = ppStore[0];
    }
    memset(&pvar, 0, sizeof(pvar));
    v43 = ((__int64 (__fastcall *)(IPropertyStore *, __int64 *, PROPVARIANT *))v36->lpVtbl->GetValue)(
            v36,
            MFPKEY_TELEMETRY_SESSION,
            &pvar);
    if ( v43 >= 0 )
    {
      if ( pvar.vt != 13 )
      {
LABEL_90:
        CMFPropVariant::Clear(&pvar);
LABEL_91:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(ppStore);
        if ( (*(int (__fastcall **)(unsigned __int64, __int64 *, int *))(*v23 + 56LL))(
               this - 72,
               MF_SOURCERESOLVER_PREFERRED_HANDLER,
               &v62) >= 0
          && v62 )
        {
          CMP3BytewiseMediaSource::SetByteScanLimit(*v30, v52);
        }
        Instance = CMP3BytewiseMediaSource::BeginOpen(*v30, v63, (struct IMFAsyncCallback *)(this + 56));
        if ( Instance >= 0 )
          goto LABEL_106;
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != Instance )
            CallStackContext::TraceFailure(v56, "CMP3ByteStreamPlugin::BeginCreateObject", 132, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_106;
        v29 = 18;
LABEL_105:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids,
          this - 72,
          Instance);
        goto LABEL_106;
      }
      v43 = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, char *))pvar.hVal.QuadPart)(
              pvar.hVal,
              &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
              (char *)(this + 48));
      if ( v43 >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)*v30 + 92) + 32LL))((__int64)*v30 + 736, v23[15]);
        goto LABEL_90;
      }
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != v43 )
          CallStackContext::TraceFailure(v51, "CMP3ByteStreamPlugin::BeginCreateObject", 110, v43);
      }
      if ( !g_wppLevels )
        goto LABEL_90;
      v47 = 17;
    }
    else
    {
      v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v43 )
          CallStackContext::TraceFailure(v46, "CMP3ByteStreamPlugin::BeginCreateObject", 106, v43);
      }
      if ( !g_wppLevels )
        goto LABEL_90;
      v47 = 16;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v47, WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids, this - 72, v43);
    goto LABEL_90;
  }
  Instance = -2147467261;
  if ( !v13 )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
    CallStackTracing::s_wpInstance = v21;
    if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v22 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v22, "CMP3ByteStreamPlugin::BeginCreateObject", 83, -2147467261);
  }
  if ( g_wppLevels )
  {
    v20 = 12;
    goto LABEL_15;
  }
LABEL_106:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
  if ( Instance < 0 )
  {
    v58 = *(_QWORD *)(this + 32);
    if ( v58 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      *(_QWORD *)(this + 32) = 0;
    }
    v59 = *(_QWORD *)(this + 40);
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      *(_QWORD *)(this + 40) = 0;
    }
LABEL_114:
    if ( v8 )
      goto LABEL_115;
    return (unsigned int)Instance;
  }
  v57 = v64;
  if ( !v64 )
    goto LABEL_114;
  if ( v8 )
  {
    *v64 = 0;
    (**(void (__fastcall ***)(__int64, GUID *, struct IUnknown **))v8)(v8, &IID_IUnknown, v57);
LABEL_115:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800b4710  mov     [rsp-38h+arg_10], rbx
0x1800b4715  push    rbp
0x1800b4716  push    rsi
0x1800b4717  push    rdi
0x1800b4718  push    r12
0x1800b471a  push    r13
0x1800b471c  push    r14
0x1800b471e  push    r15
0x1800b4720  mov     rbp, rsp
0x1800b4723  sub     rsp, 80h
0x1800b472a  mov     rax, cs:__security_cookie
0x1800b4731  xor     rax, rsp
0x1800b4734  mov     [rbp+var_10], rax
0x1800b4738  mov     rax, [rbp+arg_28]
0x1800b473c  xor     r15d, r15d
0x1800b473f  mov     r12, [rbp+arg_30]
0x1800b4743  mov     rsi, rdx
0x1800b4746  mov     r13, [rbp+arg_38]
0x1800b474a  mov     r14, rcx
0x1800b474d  mov     [rbp+var_48], rdx
0x1800b4751  lea     rcx, [rbp+var_50]; this
0x1800b4755  lea     r8d, [r15+52h]; int
0x1800b4759  mov     [rbp+var_40], rax
0x1800b475d  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b4764  mov     [rbp+var_4C], r15d
0x1800b4768  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b476d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4774  cmp     [rbx+8], r15b
0x1800b4778  jz      short loc_1800B47CF
0x1800b477a  cmp     [r14+30h], r15
0x1800b477e  jz      short loc_1800B47CF
0x1800b4780  mov     rcx, rbx; this
0x1800b4783  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4788  mov     rcx, [r14+30h]
0x1800b478c  mov     rdi, rax
0x1800b478f  mov     rdx, [rcx]
0x1800b4792  mov     rax, [rdx+128h]
0x1800b4799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b479e  mov     rcx, [r14+30h]
0x1800b47a2  mov     ebx, eax
0x1800b47a4  mov     rdx, [rcx]
0x1800b47a7  mov     rax, [rdx+118h]
0x1800b47ae  lea     rdx, [rbp+ppStore]
0x1800b47b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47b7  movups  xmm0, xmmword ptr [rax]
0x1800b47ba  mov     [rdi+7E0h], ebx
0x1800b47c0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b47c7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b47cf  test    rsi, rsi
0x1800b47d2  jnz     loc_1800B487B
0x1800b47d8  xor     r13d, r13d
0x1800b47db  mov     esi, 80004003h
0x1800b47e0  mov     edi, esi
0x1800b47e2  test    rbx, rbx
0x1800b47e5  jnz     short loc_1800B482E
0x1800b47e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b47ee  nop     dword ptr [rax+rax+00h]
0x1800b47f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b47fa  mov     rcx, rax
0x1800b47fd  test    rax, rax
0x1800b4800  jz      short loc_1800B4820
0x1800b4802  mov     rax, [rax]
0x1800b4805  mov     edx, 7F0h
0x1800b480a  mov     rax, [rax+8]
0x1800b480e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4813  test    eax, eax
0x1800b4815  jz      short loc_1800B4820
0x1800b4817  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b481e  jmp     short loc_1800B482E
0x1800b4820  lea     rbx, qword_1801B97E0
0x1800b4827  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b482e  cmp     [rbx+8], r13b
0x1800b4832  jz      short loc_1800B485C
0x1800b4834  mov     rcx, rbx; this
0x1800b4837  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b483c  cmp     [rax+7CCh], esi
0x1800b4842  jz      short loc_1800B485C
0x1800b4844  mov     r9d, esi; int
0x1800b4847  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b484e  mov     r8d, 52h ; 'R'; int
0x1800b4854  mov     rcx, rax; this
0x1800b4857  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b485c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4863  jb      loc_1800B4E5F
0x1800b4869  mov     edx, 0Bh
0x1800b486e  lea     r9, [r14-48h]
0x1800b4872  mov     [rsp+80h+var_60], esi
0x1800b4876  jmp     loc_1800B4E48
0x1800b487b  test    r12, r12
0x1800b487e  jnz     loc_1800B491F
0x1800b4884  xor     r13d, r13d
0x1800b4887  mov     esi, 80004003h
0x1800b488c  mov     edi, esi
0x1800b488e  test    rbx, rbx
0x1800b4891  jnz     short loc_1800B48DA
0x1800b4893  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b489a  nop     dword ptr [rax+rax+00h]
0x1800b489f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b48a6  mov     rcx, rax
0x1800b48a9  test    rax, rax
0x1800b48ac  jz      short loc_1800B48CC
0x1800b48ae  mov     rax, [rax]
0x1800b48b1  mov     edx, 7F0h
0x1800b48b6  mov     rax, [rax+8]
0x1800b48ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b48bf  test    eax, eax
0x1800b48c1  jz      short loc_1800B48CC
0x1800b48c3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b48ca  jmp     short loc_1800B48DA
0x1800b48cc  lea     rbx, qword_1801B97E0
0x1800b48d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b48da  cmp     [rbx+8], r13b
0x1800b48de  jz      short loc_1800B4908
0x1800b48e0  mov     rcx, rbx; this
0x1800b48e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b48e8  cmp     [rax+7CCh], esi
0x1800b48ee  jz      short loc_1800B4908
0x1800b48f0  mov     r9d, esi; int
0x1800b48f3  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b48fa  mov     r8d, 53h ; 'S'; int
0x1800b4900  mov     rcx, rax; this
0x1800b4903  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4908  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b490f  jb      loc_1800B4E5F
0x1800b4915  mov     edx, 0Ch
0x1800b491a  jmp     loc_1800B486E
0x1800b491f  lea     rsi, [r14-48h]
0x1800b4923  mov     r8, r13; struct IUnknown *
0x1800b4926  mov     rax, rsi
0x1800b4929  lea     r9, [r14+20h]; struct CMP3ByteStreamPluginResult **
0x1800b492d  neg     rax
0x1800b4930  mov     rdx, r12; struct IMFAsyncCallback *
0x1800b4933  sbb     rcx, rcx
0x1800b4936  and     rcx, r14; struct IUnknown *
0x1800b4939  call    ?CreateInstance@CMP3ByteStreamPluginResult@@SAJPEAUIUnknown@@PEAUIMFAsyncCallback@@0PEAPEAV1@@Z; CMP3ByteStreamPluginResult::CreateInstance(IUnknown *,IMFAsyncCallback *,IUnknown *,CMP3ByteStreamPluginResult * *)
0x1800b493e  xor     r13d, r13d
0x1800b4941  mov     edi, eax
0x1800b4943  test    eax, eax
0x1800b4945  jns     loc_1800B49E3
0x1800b494b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4952  test    rbx, rbx
0x1800b4955  jnz     short loc_1800B499E
0x1800b4957  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b495e  nop     dword ptr [rax+rax+00h]
0x1800b4963  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b496a  mov     rcx, rax
0x1800b496d  test    rax, rax
0x1800b4970  jz      short loc_1800B4990
0x1800b4972  mov     rax, [rax]
0x1800b4975  mov     edx, 7F0h
0x1800b497a  mov     rax, [rax+8]
0x1800b497e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4983  test    eax, eax
0x1800b4985  jz      short loc_1800B4990
0x1800b4987  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b498e  jmp     short loc_1800B499E
0x1800b4990  lea     rbx, qword_1801B97E0
0x1800b4997  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b499e  cmp     [rbx+8], r13b
0x1800b49a2  jz      short loc_1800B49CC
0x1800b49a4  mov     rcx, rbx; this
0x1800b49a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b49ac  cmp     [rax+7CCh], edi
0x1800b49b2  jz      short loc_1800B49CC
0x1800b49b4  mov     r9d, edi; int
0x1800b49b7  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b49be  mov     r8d, 56h ; 'V'; int
0x1800b49c4  mov     rcx, rax; this
0x1800b49c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b49cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b49d3  jb      loc_1800B4E5F
0x1800b49d9  mov     edx, 0Dh
0x1800b49de  jmp     loc_1800B4E41
0x1800b49e3  mov     r15, [rsi+68h]
0x1800b49e7  test    r15, r15
0x1800b49ea  jz      short loc_1800B49FB
0x1800b49ec  mov     rax, [r15]
0x1800b49ef  mov     rcx, r15
0x1800b49f2  mov     rax, [rax+8]
0x1800b49f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b49fb  lea     r12, [r14+28h]
0x1800b49ff  mov     rcx, r12; struct CMP3BytewiseMediaSource **
0x1800b4a02  call    ?Create@CMP3BytewiseMediaSource@@SAJPEAPEAV1@@Z; CMP3BytewiseMediaSource::Create(CMP3BytewiseMediaSource * *)
0x1800b4a07  mov     edi, eax
0x1800b4a09  test    eax, eax
0x1800b4a0b  jns     loc_1800B4AA9
0x1800b4a11  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a18  test    rbx, rbx
0x1800b4a1b  jnz     short loc_1800B4A64
0x1800b4a1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4a24  nop     dword ptr [rax+rax+00h]
0x1800b4a29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a30  mov     rcx, rax
0x1800b4a33  test    rax, rax
0x1800b4a36  jz      short loc_1800B4A56
0x1800b4a38  mov     rax, [rax]
0x1800b4a3b  mov     edx, 7F0h
0x1800b4a40  mov     rax, [rax+8]
0x1800b4a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a49  test    eax, eax
0x1800b4a4b  jz      short loc_1800B4A56
0x1800b4a4d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a54  jmp     short loc_1800B4A64
0x1800b4a56  lea     rbx, qword_1801B97E0
0x1800b4a5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4a64  cmp     [rbx+8], r13b
0x1800b4a68  jz      short loc_1800B4A92
0x1800b4a6a  mov     rcx, rbx; this
0x1800b4a6d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4a72  cmp     [rax+7CCh], edi
0x1800b4a78  jz      short loc_1800B4A92
0x1800b4a7a  mov     r9d, edi; int
0x1800b4a7d  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b4a84  mov     r8d, 5Bh ; '['; int
0x1800b4a8a  mov     rcx, rax; this
0x1800b4a8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4a92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4a99  jb      loc_1800B4E5F
0x1800b4a9f  mov     edx, 0Eh
0x1800b4aa4  jmp     loc_1800B4E41
0x1800b4aa9  mov     rcx, [rbp+arg_20]
0x1800b4aad  mov     [rbp+ppStore], rcx
0x1800b4ab1  test    rcx, rcx
0x1800b4ab4  jz      short loc_1800B4ACF
0x1800b4ab6  mov     rax, [rcx]
0x1800b4ab9  mov     rax, [rax+8]
0x1800b4abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ac2  mov     rcx, [rbp+ppStore]
0x1800b4ac6  test    rcx, rcx
0x1800b4ac9  jnz     loc_1800B4BA3
0x1800b4acf  lea     rcx, [rbp+ppStore]; ppStore
0x1800b4ad3  call    cs:__imp_CreatePropertyStore
0x1800b4ada  nop     dword ptr [rax+rax+00h]
0x1800b4adf  mov     edi, eax
0x1800b4ae1  test    eax, eax
0x1800b4ae3  jns     loc_1800B4B9F
0x1800b4ae9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4af0  lea     rbx, qword_1801B97E0
0x1800b4af7  test    rcx, rcx
0x1800b4afa  jnz     short loc_1800B4B3F
0x1800b4afc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4b03  nop     dword ptr [rax+rax+00h]
0x1800b4b08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4b0f  mov     rcx, rax
0x1800b4b12  test    rax, rax
0x1800b4b15  jz      short loc_1800B4B35
0x1800b4b17  mov     rax, [rax]
0x1800b4b1a  mov     edx, 7F0h
0x1800b4b1f  mov     rax, [rax+8]
0x1800b4b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b28  test    eax, eax
0x1800b4b2a  jz      short loc_1800B4B35
0x1800b4b2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4b33  jmp     short loc_1800B4B3F
0x1800b4b35  mov     rcx, rbx; this
0x1800b4b38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4b3f  cmp     [rcx+8], r13b
0x1800b4b43  jz      short loc_1800B4B6A
0x1800b4b45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4b4a  cmp     [rax+7CCh], edi
0x1800b4b50  jz      short loc_1800B4B6A
0x1800b4b52  mov     r9d, edi; int
0x1800b4b55  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800b4b5c  mov     r8d, 65h ; 'e'; int
0x1800b4b62  mov     rcx, rax; this
0x1800b4b65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4b6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4b71  jb      loc_1800B4D68
0x1800b4b77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4b7e  lea     r8, WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids
0x1800b4b85  mov     edx, 0Fh
0x1800b4b8a  mov     [rsp+80h+var_60], edi
0x1800b4b8e  mov     r9, rsi
0x1800b4b91  mov     rcx, [rcx+10h]
0x1800b4b95  call    WPP_SF_qD
0x1800b4b9a  jmp     loc_1800B4D68
0x1800b4b9f  mov     rcx, [rbp+ppStore]
0x1800b4ba3  xor     eax, eax
0x1800b4ba5  lea     r8, [rbp+pvar]
0x1800b4ba9  mov     qword ptr [rbp+pvar+10h], rax
0x1800b4bad  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x1800b4bb4  xorps   xmm0, xmm0
0x1800b4bb7  movups  xmmword ptr [rbp+pvar], xmm0
0x1800b4bbb  mov     rax, [rcx]
0x1800b4bbe  mov     rax, [rax+28h]
0x1800b4bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4bc7  lea     rbx, qword_1801B97E0
0x1800b4bce  mov     edi, eax
0x1800b4bd0  test    eax, eax
0x1800b4bd2  jns     loc_1800B4C69
0x1800b4bd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4bdf  test    rcx, rcx
0x1800b4be2  jnz     short loc_1800B4C27
0x1800b4be4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4beb  nop     dword ptr [rax+rax+00h]
0x1800b4bf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4bf7  mov     rcx, rax
0x1800b4bfa  test    rax, rax
0x1800b4bfd  jz      short loc_1800B4C1D
0x1800b4bff  mov     rax, [rax]
  ... truncated ...
```
