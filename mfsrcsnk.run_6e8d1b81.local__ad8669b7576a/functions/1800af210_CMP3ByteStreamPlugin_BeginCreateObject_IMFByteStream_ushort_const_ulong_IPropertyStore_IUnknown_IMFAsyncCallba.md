# CMP3ByteStreamPlugin::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x1800af210`
- end: `0x1800af9d0`
- name: `?BeginCreateObject@CMP3ByteStreamPlugin@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU4@@Z`
- size: `1984`
- prototype: `__int64 __fastcall(CMP3ByteStreamPlugin *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x180034d10`
- `0x180073b14`
- `0x18009a448`
- `0x1800af210`
- `0x1800e41ec`
- `0x1801099f0`
- `0x18014c6cc`
- `0x18014fc94`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af2e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af38d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af44b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af50b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af5de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af6c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af77e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af895`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af2e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af38d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af44b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af50b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af5de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af6c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af77e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800af895`
- `MFPlat!CreatePropertyStore` at `0x1800af5bb`
- `MFPlat!CreatePropertyStore` at `0x1800af5bb`

## string_xrefs

- `0x1800af25d`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af341`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af3e7`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af4a5`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af565`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af631`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af713`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af7d1`: `CMP3ByteStreamPlugin::BeginCreateObject`
- `0x1800af8e8`: `CMP3ByteStreamPlugin::BeginCreateObject`

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
  __int128 v65; // [rsp+48h] [rbp-38h] BYREF
  __int64 v66; // [rsp+58h] [rbp-28h]
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
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v33 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v39 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    v66 = 0;
    v65 = 0;
    v43 = ((__int64 (__fastcall *)(IPropertyStore *, __int64 *, __int128 *))v36->lpVtbl->GetValue)(
            v36,
            MFPKEY_TELEMETRY_SESSION,
            &v65);
    if ( v43 >= 0 )
    {
      if ( (_WORD)v65 != 13 )
      {
LABEL_90:
        CMFPropVariant::Clear((CMFPropVariant *)&v65);
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
            v54 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v43 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))&v65 + 1))(
              *((_QWORD *)&v65 + 1),
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
          v49 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v44 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v13 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800af210  mov     [rsp-38h+arg_10], rbx
0x1800af215  push    rbp
0x1800af216  push    rsi
0x1800af217  push    rdi
0x1800af218  push    r12
0x1800af21a  push    r13
0x1800af21c  push    r14
0x1800af21e  push    r15
0x1800af220  mov     rbp, rsp
0x1800af223  sub     rsp, 80h
0x1800af22a  mov     rax, cs:__security_cookie
0x1800af231  xor     rax, rsp
0x1800af234  mov     [rbp+var_10], rax
0x1800af238  mov     rax, [rbp+arg_28]
0x1800af23c  xor     r15d, r15d
0x1800af23f  mov     r12, [rbp+arg_30]
0x1800af243  mov     rsi, rdx
0x1800af246  mov     r13, [rbp+arg_38]
0x1800af24a  mov     r14, rcx
0x1800af24d  mov     [rbp+var_48], rdx
0x1800af251  lea     rcx, [rbp+var_50]; this
0x1800af255  lea     r8d, [r15+52h]; int
0x1800af259  mov     [rbp+var_40], rax
0x1800af25d  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af264  mov     [rbp+var_4C], r15d
0x1800af268  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800af26d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af274  cmp     [rbx+8], r15b
0x1800af278  jz      short loc_1800AF2CF
0x1800af27a  cmp     [r14+30h], r15
0x1800af27e  jz      short loc_1800AF2CF
0x1800af280  mov     rcx, rbx; this
0x1800af283  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af288  mov     rcx, [r14+30h]
0x1800af28c  mov     rdi, rax
0x1800af28f  mov     rdx, [rcx]
0x1800af292  mov     rax, [rdx+128h]
0x1800af299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af29e  mov     rcx, [r14+30h]
0x1800af2a2  mov     ebx, eax
0x1800af2a4  mov     rdx, [rcx]
0x1800af2a7  mov     rax, [rdx+118h]
0x1800af2ae  lea     rdx, [rbp+ppStore]
0x1800af2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af2b7  movups  xmm0, xmmword ptr [rax]
0x1800af2ba  mov     [rdi+7E0h], ebx
0x1800af2c0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af2c7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800af2cf  test    rsi, rsi
0x1800af2d2  jnz     loc_1800AF375
0x1800af2d8  xor     r13d, r13d
0x1800af2db  mov     esi, 80004003h
0x1800af2e0  mov     edi, esi
0x1800af2e2  test    rbx, rbx
0x1800af2e5  jnz     short loc_1800AF328
0x1800af2e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af2ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af2f4  mov     rcx, rax
0x1800af2f7  test    rax, rax
0x1800af2fa  jz      short loc_1800AF31A
0x1800af2fc  mov     rax, [rax]
0x1800af2ff  mov     edx, 7F0h
0x1800af304  mov     rax, [rax+8]
0x1800af308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af30d  test    eax, eax
0x1800af30f  jz      short loc_1800AF31A
0x1800af311  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af318  jmp     short loc_1800AF328
0x1800af31a  lea     rbx, qword_1801B07E0
0x1800af321  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af328  cmp     [rbx+8], r13b
0x1800af32c  jz      short loc_1800AF356
0x1800af32e  mov     rcx, rbx; this
0x1800af331  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af336  cmp     [rax+7CCh], esi
0x1800af33c  jz      short loc_1800AF356
0x1800af33e  mov     r9d, esi; int
0x1800af341  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af348  mov     r8d, 52h ; 'R'; int
0x1800af34e  mov     rcx, rax; this
0x1800af351  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af356  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800af35d  jb      loc_1800AF929
0x1800af363  mov     edx, 0Bh
0x1800af368  lea     r9, [r14-48h]
0x1800af36c  mov     [rsp+80h+var_60], esi
0x1800af370  jmp     loc_1800AF912
0x1800af375  test    r12, r12
0x1800af378  jnz     loc_1800AF413
0x1800af37e  xor     r13d, r13d
0x1800af381  mov     esi, 80004003h
0x1800af386  mov     edi, esi
0x1800af388  test    rbx, rbx
0x1800af38b  jnz     short loc_1800AF3CE
0x1800af38d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af393  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af39a  mov     rcx, rax
0x1800af39d  test    rax, rax
0x1800af3a0  jz      short loc_1800AF3C0
0x1800af3a2  mov     rax, [rax]
0x1800af3a5  mov     edx, 7F0h
0x1800af3aa  mov     rax, [rax+8]
0x1800af3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af3b3  test    eax, eax
0x1800af3b5  jz      short loc_1800AF3C0
0x1800af3b7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af3be  jmp     short loc_1800AF3CE
0x1800af3c0  lea     rbx, qword_1801B07E0
0x1800af3c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af3ce  cmp     [rbx+8], r13b
0x1800af3d2  jz      short loc_1800AF3FC
0x1800af3d4  mov     rcx, rbx; this
0x1800af3d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af3dc  cmp     [rax+7CCh], esi
0x1800af3e2  jz      short loc_1800AF3FC
0x1800af3e4  mov     r9d, esi; int
0x1800af3e7  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af3ee  mov     r8d, 53h ; 'S'; int
0x1800af3f4  mov     rcx, rax; this
0x1800af3f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af3fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800af403  jb      loc_1800AF929
0x1800af409  mov     edx, 0Ch
0x1800af40e  jmp     loc_1800AF368
0x1800af413  lea     rsi, [r14-48h]
0x1800af417  mov     r8, r13; struct IUnknown *
0x1800af41a  mov     rax, rsi
0x1800af41d  lea     r9, [r14+20h]; struct CMP3ByteStreamPluginResult **
0x1800af421  neg     rax
0x1800af424  mov     rdx, r12; struct IMFAsyncCallback *
0x1800af427  sbb     rcx, rcx
0x1800af42a  and     rcx, r14; struct IUnknown *
0x1800af42d  call    ?CreateInstance@CMP3ByteStreamPluginResult@@SAJPEAUIUnknown@@PEAUIMFAsyncCallback@@0PEAPEAV1@@Z; CMP3ByteStreamPluginResult::CreateInstance(IUnknown *,IMFAsyncCallback *,IUnknown *,CMP3ByteStreamPluginResult * *)
0x1800af432  xor     r13d, r13d
0x1800af435  mov     edi, eax
0x1800af437  test    eax, eax
0x1800af439  jns     loc_1800AF4D1
0x1800af43f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af446  test    rbx, rbx
0x1800af449  jnz     short loc_1800AF48C
0x1800af44b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af451  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af458  mov     rcx, rax
0x1800af45b  test    rax, rax
0x1800af45e  jz      short loc_1800AF47E
0x1800af460  mov     rax, [rax]
0x1800af463  mov     edx, 7F0h
0x1800af468  mov     rax, [rax+8]
0x1800af46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af471  test    eax, eax
0x1800af473  jz      short loc_1800AF47E
0x1800af475  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af47c  jmp     short loc_1800AF48C
0x1800af47e  lea     rbx, qword_1801B07E0
0x1800af485  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af48c  cmp     [rbx+8], r13b
0x1800af490  jz      short loc_1800AF4BA
0x1800af492  mov     rcx, rbx; this
0x1800af495  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af49a  cmp     [rax+7CCh], edi
0x1800af4a0  jz      short loc_1800AF4BA
0x1800af4a2  mov     r9d, edi; int
0x1800af4a5  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af4ac  mov     r8d, 56h ; 'V'; int
0x1800af4b2  mov     rcx, rax; this
0x1800af4b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af4ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800af4c1  jb      loc_1800AF929
0x1800af4c7  mov     edx, 0Dh
0x1800af4cc  jmp     loc_1800AF90B
0x1800af4d1  mov     r15, [rsi+68h]
0x1800af4d5  test    r15, r15
0x1800af4d8  jz      short loc_1800AF4E9
0x1800af4da  mov     rax, [r15]
0x1800af4dd  mov     rcx, r15
0x1800af4e0  mov     rax, [rax+8]
0x1800af4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4e9  lea     r12, [r14+28h]
0x1800af4ed  mov     rcx, r12; struct CMP3BytewiseMediaSource **
0x1800af4f0  call    ?Create@CMP3BytewiseMediaSource@@SAJPEAPEAV1@@Z; CMP3BytewiseMediaSource::Create(CMP3BytewiseMediaSource * *)
0x1800af4f5  mov     edi, eax
0x1800af4f7  test    eax, eax
0x1800af4f9  jns     loc_1800AF591
0x1800af4ff  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af506  test    rbx, rbx
0x1800af509  jnz     short loc_1800AF54C
0x1800af50b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af511  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af518  mov     rcx, rax
0x1800af51b  test    rax, rax
0x1800af51e  jz      short loc_1800AF53E
0x1800af520  mov     rax, [rax]
0x1800af523  mov     edx, 7F0h
0x1800af528  mov     rax, [rax+8]
0x1800af52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af531  test    eax, eax
0x1800af533  jz      short loc_1800AF53E
0x1800af535  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af53c  jmp     short loc_1800AF54C
0x1800af53e  lea     rbx, qword_1801B07E0
0x1800af545  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af54c  cmp     [rbx+8], r13b
0x1800af550  jz      short loc_1800AF57A
0x1800af552  mov     rcx, rbx; this
0x1800af555  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af55a  cmp     [rax+7CCh], edi
0x1800af560  jz      short loc_1800AF57A
0x1800af562  mov     r9d, edi; int
0x1800af565  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af56c  mov     r8d, 5Bh ; '['; int
0x1800af572  mov     rcx, rax; this
0x1800af575  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af57a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800af581  jb      loc_1800AF929
0x1800af587  mov     edx, 0Eh
0x1800af58c  jmp     loc_1800AF90B
0x1800af591  mov     rcx, [rbp+arg_20]
0x1800af595  mov     [rbp+ppStore], rcx
0x1800af599  test    rcx, rcx
0x1800af59c  jz      short loc_1800AF5B7
0x1800af59e  mov     rax, [rcx]
0x1800af5a1  mov     rax, [rax+8]
0x1800af5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af5aa  mov     rcx, [rbp+ppStore]
0x1800af5ae  test    rcx, rcx
0x1800af5b1  jnz     loc_1800AF67F
0x1800af5b7  lea     rcx, [rbp+ppStore]; ppStore
0x1800af5bb  call    cs:__imp_CreatePropertyStore
0x1800af5c1  mov     edi, eax
0x1800af5c3  test    eax, eax
0x1800af5c5  jns     loc_1800AF67B
0x1800af5cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af5d2  lea     rbx, qword_1801B07E0
0x1800af5d9  test    rcx, rcx
0x1800af5dc  jnz     short loc_1800AF61B
0x1800af5de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af5e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af5eb  mov     rcx, rax
0x1800af5ee  test    rax, rax
0x1800af5f1  jz      short loc_1800AF611
0x1800af5f3  mov     rax, [rax]
0x1800af5f6  mov     edx, 7F0h
0x1800af5fb  mov     rax, [rax+8]
0x1800af5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af604  test    eax, eax
0x1800af606  jz      short loc_1800AF611
0x1800af608  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af60f  jmp     short loc_1800AF61B
0x1800af611  mov     rcx, rbx; this
0x1800af614  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af61b  cmp     [rcx+8], r13b
0x1800af61f  jz      short loc_1800AF646
0x1800af621  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af626  cmp     [rax+7CCh], edi
0x1800af62c  jz      short loc_1800AF646
0x1800af62e  mov     r9d, edi; int
0x1800af631  lea     rdx, aCmp3bytestream_4; "CMP3ByteStreamPlugin::BeginCreateObject"
0x1800af638  mov     r8d, 65h ; 'e'; int
0x1800af63e  mov     rcx, rax; this
0x1800af641  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af646  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800af64d  jb      loc_1800AF838
0x1800af653  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af65a  lea     r8, WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids
0x1800af661  mov     edx, 0Fh
0x1800af666  mov     [rsp+80h+var_60], edi
0x1800af66a  mov     r9, rsi
0x1800af66d  mov     rcx, [rcx+10h]
0x1800af671  call    WPP_SF_qD
0x1800af676  jmp     loc_1800AF838
0x1800af67b  mov     rcx, [rbp+ppStore]
0x1800af67f  xor     eax, eax
0x1800af681  lea     r8, [rbp+var_38]
0x1800af685  mov     [rbp+var_28], rax
0x1800af689  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x1800af690  xorps   xmm0, xmm0
0x1800af693  movups  [rbp+var_38], xmm0
0x1800af697  mov     rax, [rcx]
0x1800af69a  mov     rax, [rax+28h]
0x1800af69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af6a3  lea     rbx, qword_1801B07E0
0x1800af6aa  mov     edi, eax
0x1800af6ac  test    eax, eax
0x1800af6ae  jns     loc_1800AF73F
0x1800af6b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af6bb  test    rcx, rcx
0x1800af6be  jnz     short loc_1800AF6FD
0x1800af6c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800af6c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af6cd  mov     rcx, rax
0x1800af6d0  test    rax, rax
0x1800af6d3  jz      short loc_1800AF6F3
0x1800af6d5  mov     rax, [rax]
0x1800af6d8  mov     edx, 7F0h
0x1800af6dd  mov     rax, [rax+8]
0x1800af6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af6e6  test    eax, eax
0x1800af6e8  jz      short loc_1800AF6F3
0x1800af6ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af6f1  jmp     short loc_1800AF6FD
  ... truncated ...
```
