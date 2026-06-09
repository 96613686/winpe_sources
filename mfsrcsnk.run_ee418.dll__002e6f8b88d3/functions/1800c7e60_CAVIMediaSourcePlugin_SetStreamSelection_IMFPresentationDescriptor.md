# CAVIMediaSourcePlugin::SetStreamSelection(IMFPresentationDescriptor *)

- ea: `0x1800c7e60`
- end: `0x1800c870a`
- name: `?SetStreamSelection@CAVIMediaSourcePlugin@@UEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2218`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800c7e60`
- `0x18011b1e4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c7ec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c7f7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c802a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c80e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c827f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c830e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c839d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c844f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c84de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c85c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c865a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c7ec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c7f7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c802a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c80e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c827f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c830e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c839d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c844f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c84de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c85c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c865a`

## string_xrefs

- `0x1800c7e77`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c82d6`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c8365`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c83f4`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c84a6`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c8535`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800c861d`: `CAVIMediaSourcePlugin::SetStreamSelection`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::SetStreamSelection(
        CAVIMediaSourcePlugin *this,
        struct IMFPresentationDescriptor *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // r14d
  char *v8; // rdi
  wchar_t *v9; // rcx
  int v10; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int i; // esi
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v30; // r15d
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  unsigned int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  int v73; // [rsp+30h] [rbp-28h] BYREF
  int v74; // [rsp+34h] [rbp-24h] BYREF
  __int64 v75; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v76[3]; // [rsp+40h] [rbp-18h] BYREF
  int v77; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v78; // [rsp+A8h] [rbp+50h] BYREF
  unsigned int v79; // [rsp+B0h] [rbp+58h] BYREF
  int v80; // [rsp+B8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v77,
    "CAVIMediaSourcePlugin::SetStreamSelection",
    1318);
  v7 = 0;
  v8 = (char *)this - 16;
  v80 = 0;
  v78 = 0;
  v79 = 0;
  v74 = 0;
  v73 = 0;
  if ( a2 )
  {
    if ( *((_QWORD *)v8 + 9) )
    {
      v10 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))a2->lpVtbl->GetStreamDescriptorCount)(
              a2,
              &v79);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v8 + 9) + 264LL))(
                *((_QWORD *)v8 + 9),
                &v78);
        if ( v10 >= 0 )
        {
          for ( i = 0; i < v78; ++i )
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 288LL))(
                    *((_QWORD *)this + 7),
                    i);
            if ( v10 < 0 )
            {
              v27 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
                CallStackTracing::s_wpInstance = v28;
                if ( v28
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                {
                  v27 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v27 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v27 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CAVIMediaSourcePlugin::SetStreamSelection",
                    1353,
                    v10);
              }
              if ( g_wppLevels )
              {
                v13 = 138;
                goto LABEL_139;
              }
              goto LABEL_140;
            }
          }
          v30 = 0;
          while ( v7 < v79 )
          {
            lpVtbl = a2->lpVtbl;
            v32 = 0;
            v75 = 0;
            v10 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))lpVtbl->GetStreamDescriptorByIndex)(
                    a2,
                    v7,
                    &v80,
                    &v75);
            if ( v10 < 0 )
            {
              v63 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
                CallStackTracing::s_wpInstance = v64;
                if ( v64
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
                {
                  v63 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v63 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v63 + 8) )
              {
                v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                if ( *((_DWORD *)v65 + 499) != v10 )
                  CallStackContext::TraceFailure(v65, "CAVIMediaSourcePlugin::SetStreamSelection", 1359, v10);
              }
              if ( g_wppLevels )
              {
                v62 = 139;
LABEL_114:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v62,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  (char *)this - 16,
                  v10);
              }
LABEL_115:
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v75);
              goto LABEL_140;
            }
            if ( v80 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v75 + 264LL))(v75, &v74);
              if ( v10 >= 0 )
              {
                while ( 1 )
                {
                  if ( v32 >= v78 )
                    goto LABEL_61;
                  v39 = *((_QWORD *)this + 7);
                  v76[0] = 0;
                  v77 = 0;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, _QWORD *))(*(_QWORD *)v39 + 272LL))(
                          v39,
                          v32,
                          &v77,
                          v76);
                  if ( v10 < 0 )
                    break;
                  v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v76[0] + 264LL))(v76[0], &v73);
                  if ( v10 < 0 )
                  {
                    v53 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
                      CallStackTracing::s_wpInstance = v54;
                      if ( v54
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(
                             v54,
                             2032) )
                      {
                        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v53 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v53 + 8) )
                    {
                      v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                      if ( *((_DWORD *)v55 + 499) != v10 )
                        CallStackContext::TraceFailure(v55, "CAVIMediaSourcePlugin::SetStreamSelection", 1369, v10);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_93;
                    v52 = 142;
                    goto LABEL_92;
                  }
                  if ( v74 == v73 )
                  {
                    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 280LL))(
                            *((_QWORD *)this + 7),
                            v32);
                    if ( v10 >= 0 )
                    {
                      ++v30;
                      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v76);
                      goto LABEL_61;
                    }
                    v49 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
                      CallStackTracing::s_wpInstance = v50;
                      if ( v50
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(
                             v50,
                             2032) )
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
                      if ( *((_DWORD *)v51 + 499) != v10 )
                        CallStackContext::TraceFailure(v51, "CAVIMediaSourcePlugin::SetStreamSelection", 1372, v10);
                    }
                    if ( g_wppLevels )
                    {
                      v52 = 143;
                      goto LABEL_92;
                    }
LABEL_93:
                    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v76);
                    goto LABEL_115;
                  }
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v76);
                  ++v32;
                }
                v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                  CallStackTracing::s_wpInstance = v57;
                  if ( v57
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
                  {
                    v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v56 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v56 + 8) )
                {
                  v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                  if ( *((_DWORD *)v58 + 499) != v10 )
                    CallStackContext::TraceFailure(v58, "CAVIMediaSourcePlugin::SetStreamSelection", 1368, v10);
                }
                if ( !g_wppLevels )
                  goto LABEL_93;
                v52 = 141;
LABEL_92:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v52,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  (char *)this - 16,
                  v10);
                goto LABEL_93;
              }
              v59 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
                CallStackTracing::s_wpInstance = v60;
                if ( v60
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                {
                  v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v59 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v59 + 8) )
              {
                v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                if ( *((_DWORD *)v61 + 499) != v10 )
                  CallStackContext::TraceFailure(v61, "CAVIMediaSourcePlugin::SetStreamSelection", 1362, v10);
              }
              if ( g_wppLevels )
              {
                v62 = 140;
                goto LABEL_114;
              }
              goto LABEL_115;
            }
LABEL_61:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v75);
            ++v7;
          }
          if ( !v30 )
          {
            if ( byte_1801B1109 )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                144,
                &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                (char *)this - 16);
            v66 = (wchar_t *)CallStackTracing::s_wpInstance;
            v10 = -2147024809;
            if ( !CallStackTracing::s_wpInstance )
            {
              v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
              CallStackTracing::s_wpInstance = v67;
              if ( v67
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
              {
                v66 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v66 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v66 + 8) )
            {
              v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
              if ( *((_DWORD *)v68 + 499) != -2147024809 )
                CallStackContext::TraceFailure(v68, "CAVIMediaSourcePlugin::SetStreamSelection", 1386, -2147024809);
            }
            if ( g_wppLevels )
            {
              v13 = 145;
              goto LABEL_139;
            }
          }
        }
        else
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v10 )
              CallStackContext::TraceFailure(v25, "CAVIMediaSourcePlugin::SetStreamSelection", 1345, v10);
          }
          if ( g_wppLevels )
          {
            v13 = 137;
            goto LABEL_139;
          }
        }
      }
      else
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != v10 )
            CallStackContext::TraceFailure(v19, "CAVIMediaSourcePlugin::SetStreamSelection", 1339, v10);
        }
        if ( g_wppLevels )
        {
          v13 = 136;
          goto LABEL_139;
        }
      }
    }
    else
    {
      v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      v10 = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
        CallStackTracing::s_wpInstance = v70;
        if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
        {
          v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v69 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v69 + 8) )
      {
        v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
        if ( *((_DWORD *)v71 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v71, "CAVIMediaSourcePlugin::SetStreamSelection", 1333, -1072875854);
      }
      if ( g_wppLevels )
      {
        v13 = 135;
        goto LABEL_139;
      }
    }
  }
  else
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "CAVIMediaSourcePlugin::SetStreamSelection", 1329, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 134;
LABEL_139:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        (char *)this - 16,
        v10);
    }
  }
LABEL_140:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v77);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800c7e60  push    rbp
0x1800c7e62  push    rbx
0x1800c7e63  push    rsi
0x1800c7e64  push    rdi
0x1800c7e65  push    r12
0x1800c7e67  push    r13
0x1800c7e69  push    r14
0x1800c7e6b  push    r15
0x1800c7e6d  mov     rbp, rsp
0x1800c7e70  sub     rsp, 58h
0x1800c7e74  mov     r12, rdx
0x1800c7e77  lea     r15, aCavimediasourc_9; "CAVIMediaSourcePlugin::SetStreamSelecti"...
0x1800c7e7e  mov     r13, rcx
0x1800c7e81  mov     rdx, r15; char *
0x1800c7e84  mov     r8d, 526h; int
0x1800c7e8a  lea     rcx, [rbp+arg_0]; this
0x1800c7e8e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c7e93  xor     r14d, r14d
0x1800c7e96  lea     rdi, [r13-10h]
0x1800c7e9a  mov     [rbp+arg_18], r14d
0x1800c7e9e  mov     [rbp+arg_8], r14d
0x1800c7ea2  mov     [rbp+arg_10], r14d
0x1800c7ea6  mov     [rbp+var_24], r14d
0x1800c7eaa  mov     [rbp+var_28], r14d
0x1800c7eae  test    r12, r12
0x1800c7eb1  jnz     loc_1800C7F47
0x1800c7eb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7ebe  mov     ebx, 80004003h
0x1800c7ec3  test    rcx, rcx
0x1800c7ec6  jnz     short loc_1800C7F09
0x1800c7ec8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c7ece  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7ed5  mov     rcx, rax
0x1800c7ed8  test    rax, rax
0x1800c7edb  jz      short loc_1800C7EFB
0x1800c7edd  mov     rax, [rax]
0x1800c7ee0  mov     edx, 7F0h
0x1800c7ee5  mov     rax, [rax+8]
0x1800c7ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7eee  test    eax, eax
0x1800c7ef0  jz      short loc_1800C7EFB
0x1800c7ef2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7ef9  jmp     short loc_1800C7F09
0x1800c7efb  lea     rcx, qword_1801B07E0; this
0x1800c7f02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7f09  cmp     [rcx+8], r14b
0x1800c7f0d  jz      short loc_1800C7F30
0x1800c7f0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c7f14  cmp     [rax+7CCh], ebx
0x1800c7f1a  jz      short loc_1800C7F30
0x1800c7f1c  mov     r9d, ebx; int
0x1800c7f1f  mov     r8d, 531h; int
0x1800c7f25  mov     rdx, r15; char *
0x1800c7f28  mov     rcx, rax; this
0x1800c7f2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c7f30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c7f37  jb      loc_1800C86EE
0x1800c7f3d  mov     edx, 86h
0x1800c7f42  jmp     loc_1800C86D0
0x1800c7f47  cmp     [rdi+48h], r14
0x1800c7f4b  jz      loc_1800C8649
0x1800c7f51  mov     rax, [r12]
0x1800c7f55  lea     rdx, [rbp+arg_10]
0x1800c7f59  mov     rcx, r12
0x1800c7f5c  mov     rax, [rax+108h]
0x1800c7f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f68  mov     ebx, eax
0x1800c7f6a  test    eax, eax
0x1800c7f6c  jns     loc_1800C7FFD
0x1800c7f72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7f79  test    rcx, rcx
0x1800c7f7c  jnz     short loc_1800C7FBF
0x1800c7f7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c7f84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7f8b  mov     rcx, rax
0x1800c7f8e  test    rax, rax
0x1800c7f91  jz      short loc_1800C7FB1
0x1800c7f93  mov     rax, [rax]
0x1800c7f96  mov     edx, 7F0h
0x1800c7f9b  mov     rax, [rax+8]
0x1800c7f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7fa4  test    eax, eax
0x1800c7fa6  jz      short loc_1800C7FB1
0x1800c7fa8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7faf  jmp     short loc_1800C7FBF
0x1800c7fb1  lea     rcx, qword_1801B07E0; this
0x1800c7fb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c7fbf  cmp     [rcx+8], r14b
0x1800c7fc3  jz      short loc_1800C7FE6
0x1800c7fc5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c7fca  cmp     [rax+7CCh], ebx
0x1800c7fd0  jz      short loc_1800C7FE6
0x1800c7fd2  mov     r9d, ebx; int
0x1800c7fd5  mov     r8d, 53Bh; int
0x1800c7fdb  mov     rdx, r15; char *
0x1800c7fde  mov     rcx, rax; this
0x1800c7fe1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c7fe6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c7fed  jb      loc_1800C86EE
0x1800c7ff3  mov     edx, 88h
0x1800c7ff8  jmp     loc_1800C86D0
0x1800c7ffd  mov     rcx, [rdi+48h]
0x1800c8001  lea     rdx, [rbp+arg_8]
0x1800c8005  mov     rax, [rcx]
0x1800c8008  mov     rax, [rax+108h]
0x1800c800f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8014  mov     ebx, eax
0x1800c8016  test    eax, eax
0x1800c8018  jns     loc_1800C80A9
0x1800c801e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8025  test    rcx, rcx
0x1800c8028  jnz     short loc_1800C806B
0x1800c802a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8030  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8037  mov     rcx, rax
0x1800c803a  test    rax, rax
0x1800c803d  jz      short loc_1800C805D
0x1800c803f  mov     rax, [rax]
0x1800c8042  mov     edx, 7F0h
0x1800c8047  mov     rax, [rax+8]
0x1800c804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8050  test    eax, eax
0x1800c8052  jz      short loc_1800C805D
0x1800c8054  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c805b  jmp     short loc_1800C806B
0x1800c805d  lea     rcx, qword_1801B07E0; this
0x1800c8064  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c806b  cmp     [rcx+8], r14b
0x1800c806f  jz      short loc_1800C8092
0x1800c8071  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c8076  cmp     [rax+7CCh], ebx
0x1800c807c  jz      short loc_1800C8092
0x1800c807e  mov     r9d, ebx; int
0x1800c8081  mov     r8d, 541h; int
0x1800c8087  mov     rdx, r15; char *
0x1800c808a  mov     rcx, rax; this
0x1800c808d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8092  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c8099  jb      loc_1800C86EE
0x1800c809f  mov     edx, 89h
0x1800c80a4  jmp     loc_1800C86D0
0x1800c80a9  mov     esi, r14d
0x1800c80ac  cmp     esi, [rbp+arg_8]
0x1800c80af  jnb     loc_1800C815F
0x1800c80b5  mov     rcx, [r13+38h]
0x1800c80b9  mov     edx, esi
0x1800c80bb  mov     rax, [rcx]
0x1800c80be  mov     rax, [rax+120h]
0x1800c80c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c80ca  mov     ebx, eax
0x1800c80cc  test    eax, eax
0x1800c80ce  js      short loc_1800C80D4
0x1800c80d0  inc     esi
0x1800c80d2  jmp     short loc_1800C80AC
0x1800c80d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c80db  test    rcx, rcx
0x1800c80de  jnz     short loc_1800C8121
0x1800c80e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c80e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c80ed  mov     rcx, rax
0x1800c80f0  test    rax, rax
0x1800c80f3  jz      short loc_1800C8113
0x1800c80f5  mov     rax, [rax]
0x1800c80f8  mov     edx, 7F0h
0x1800c80fd  mov     rax, [rax+8]
0x1800c8101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8106  test    eax, eax
0x1800c8108  jz      short loc_1800C8113
0x1800c810a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8111  jmp     short loc_1800C8121
0x1800c8113  lea     rcx, qword_1801B07E0; this
0x1800c811a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8121  cmp     [rcx+8], r14b
0x1800c8125  jz      short loc_1800C8148
0x1800c8127  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c812c  cmp     [rax+7CCh], ebx
0x1800c8132  jz      short loc_1800C8148
0x1800c8134  mov     r9d, ebx; int
0x1800c8137  mov     r8d, 549h; int
0x1800c813d  mov     rdx, r15; char *
0x1800c8140  mov     rcx, rax; this
0x1800c8143  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c8148  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c814f  jb      loc_1800C86EE
0x1800c8155  mov     edx, 8Ah
0x1800c815a  jmp     loc_1800C86D0
0x1800c815f  mov     r15d, r14d
0x1800c8162  cmp     r14d, [rbp+arg_10]
0x1800c8166  jnb     loc_1800C8584
0x1800c816c  mov     rax, [r12]
0x1800c8170  lea     r9, [rbp+var_20]
0x1800c8174  xor     esi, esi
0x1800c8176  lea     r8, [rbp+arg_18]
0x1800c817a  mov     edx, r14d
0x1800c817d  mov     [rbp+var_20], rsi
0x1800c8181  mov     rcx, r12
0x1800c8184  mov     rax, [rax+110h]
0x1800c818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8190  mov     ebx, eax
0x1800c8192  test    eax, eax
0x1800c8194  js      loc_1800C84D2
0x1800c819a  cmp     [rbp+arg_18], esi
0x1800c819d  jz      loc_1800C8262
0x1800c81a3  mov     rcx, [rbp+var_20]
0x1800c81a7  lea     rdx, [rbp+var_24]
0x1800c81ab  mov     rax, [rcx]
0x1800c81ae  mov     rax, [rax+108h]
0x1800c81b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c81ba  mov     ebx, eax
0x1800c81bc  test    eax, eax
0x1800c81be  js      loc_1800C8443
0x1800c81c4  cmp     esi, [rbp+arg_8]
0x1800c81c7  jnb     loc_1800C8262
0x1800c81cd  mov     rcx, [r13+38h]
0x1800c81d1  lea     r9, [rbp+var_18]
0x1800c81d5  mov     [rbp+var_18], 0
0x1800c81dd  lea     r8, [rbp+arg_0]
0x1800c81e1  mov     [rbp+arg_0], 0
0x1800c81e8  mov     edx, esi
0x1800c81ea  mov     rax, [rcx]
0x1800c81ed  mov     rax, [rax+110h]
0x1800c81f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c81f9  mov     ebx, eax
0x1800c81fb  test    eax, eax
0x1800c81fd  js      loc_1800C8391
0x1800c8203  mov     rcx, [rbp+var_18]
0x1800c8207  lea     rdx, [rbp+var_28]
0x1800c820b  mov     rax, [rcx]
0x1800c820e  mov     rax, [rax+108h]
0x1800c8215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c821a  mov     ebx, eax
0x1800c821c  test    eax, eax
0x1800c821e  js      loc_1800C8302
0x1800c8224  mov     eax, [rbp+var_28]
0x1800c8227  cmp     [rbp+var_24], eax
0x1800c822a  jz      short loc_1800C8239
0x1800c822c  lea     rcx, [rbp+var_18]; void *
0x1800c8230  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800c8235  inc     esi
0x1800c8237  jmp     short loc_1800C81C4
0x1800c8239  mov     rcx, [r13+38h]
0x1800c823d  mov     edx, esi
0x1800c823f  mov     rax, [rcx]
0x1800c8242  mov     rax, [rax+118h]
0x1800c8249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c824e  xor     esi, esi
0x1800c8250  mov     ebx, eax
0x1800c8252  test    eax, eax
0x1800c8254  js      short loc_1800C8273
0x1800c8256  inc     r15d
0x1800c8259  lea     rcx, [rbp+var_18]; void *
0x1800c825d  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800c8262  lea     rcx, [rbp+var_20]; void *
0x1800c8266  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800c826b  inc     r14d
0x1800c826e  jmp     loc_1800C8162
0x1800c8273  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c827a  test    rcx, rcx
0x1800c827d  jnz     short loc_1800C82C0
0x1800c827f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8285  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c828c  mov     rcx, rax
0x1800c828f  test    rax, rax
0x1800c8292  jz      short loc_1800C82B2
0x1800c8294  mov     rax, [rax]
0x1800c8297  mov     edx, 7F0h
0x1800c829c  mov     rax, [rax+8]
0x1800c82a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c82a5  test    eax, eax
0x1800c82a7  jz      short loc_1800C82B2
0x1800c82a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c82b0  jmp     short loc_1800C82C0
0x1800c82b2  lea     rcx, qword_1801B07E0; this
0x1800c82b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c82c0  cmp     [rcx+8], sil
0x1800c82c4  jz      short loc_1800C82EB
0x1800c82c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c82cb  cmp     [rax+7CCh], ebx
0x1800c82d1  jz      short loc_1800C82EB
0x1800c82d3  mov     r9d, ebx; int
0x1800c82d6  lea     rdx, aCavimediasourc_9; "CAVIMediaSourcePlugin::SetStreamSelecti"...
0x1800c82dd  mov     r8d, 55Ch; int
0x1800c82e3  mov     rcx, rax; this
0x1800c82e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c82eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c82f2  jb      loc_1800C8435
0x1800c82f8  mov     edx, 8Fh
0x1800c82fd  jmp     loc_1800C8417
0x1800c8302  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c8309  test    rcx, rcx
0x1800c830c  jnz     short loc_1800C834F
0x1800c830e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c8314  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c831b  mov     rcx, rax
0x1800c831e  test    rax, rax
0x1800c8321  jz      short loc_1800C8341
0x1800c8323  mov     rax, [rax]
0x1800c8326  mov     edx, 7F0h
0x1800c832b  mov     rax, [rax+8]
0x1800c832f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
