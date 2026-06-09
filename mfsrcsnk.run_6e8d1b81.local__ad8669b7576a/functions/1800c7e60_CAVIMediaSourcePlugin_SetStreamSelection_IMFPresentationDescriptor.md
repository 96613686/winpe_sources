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
  unsigned int v5; // r14d
  char *v6; // rdi
  wchar_t *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned int i; // esi
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v24; // r15d
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  unsigned int v26; // esi
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  int v57; // [rsp+30h] [rbp-28h] BYREF
  int v58; // [rsp+34h] [rbp-24h] BYREF
  __int64 v59; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v60[3]; // [rsp+40h] [rbp-18h] BYREF
  int v61; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v62; // [rsp+A8h] [rbp+50h] BYREF
  unsigned int v63; // [rsp+B0h] [rbp+58h] BYREF
  int v64; // [rsp+B8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v61,
    "CAVIMediaSourcePlugin::SetStreamSelection",
    1318);
  v5 = 0;
  v6 = (char *)this - 16;
  v64 = 0;
  v62 = 0;
  v63 = 0;
  v58 = 0;
  v57 = 0;
  if ( a2 )
  {
    if ( *((_QWORD *)v6 + 9) )
    {
      v8 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))a2->lpVtbl->GetStreamDescriptorCount)(
             a2,
             &v63);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v6 + 9) + 264LL))(
               *((_QWORD *)v6 + 9),
               &v62);
        if ( v8 >= 0 )
        {
          for ( i = 0; i < v62; ++i )
          {
            v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 288LL))(*((_QWORD *)this + 7), i);
            if ( v8 < 0 )
            {
              v21 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
                CallStackTracing::s_wpInstance = v22;
                if ( v22
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
                {
                  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v21 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v21 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CAVIMediaSourcePlugin::SetStreamSelection",
                    1353,
                    v8);
              }
              if ( g_wppLevels )
              {
                v11 = 138;
                goto LABEL_139;
              }
              goto LABEL_140;
            }
          }
          v24 = 0;
          while ( v5 < v63 )
          {
            lpVtbl = a2->lpVtbl;
            v26 = 0;
            v59 = 0;
            v8 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))lpVtbl->GetStreamDescriptorByIndex)(
                   a2,
                   v5,
                   &v64,
                   &v59);
            if ( v8 < 0 )
            {
              v47 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                CallStackTracing::s_wpInstance = v48;
                if ( v48
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                {
                  v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v47 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v47 + 8) )
              {
                v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                if ( *((_DWORD *)v49 + 499) != v8 )
                  CallStackContext::TraceFailure(v49, "CAVIMediaSourcePlugin::SetStreamSelection", 1359, v8);
              }
              if ( g_wppLevels )
              {
                v46 = 139;
LABEL_114:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v46,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  (char *)this - 16,
                  v8);
              }
LABEL_115:
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v59);
              goto LABEL_140;
            }
            if ( v64 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v59 + 264LL))(v59, &v58);
              if ( v8 >= 0 )
              {
                while ( 1 )
                {
                  if ( v26 >= v62 )
                    goto LABEL_61;
                  v29 = *((_QWORD *)this + 7);
                  v60[0] = 0;
                  v61 = 0;
                  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, _QWORD *))(*(_QWORD *)v29 + 272LL))(
                         v29,
                         v26,
                         &v61,
                         v60);
                  if ( v8 < 0 )
                    break;
                  v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v60[0] + 264LL))(v60[0], &v57);
                  if ( v8 < 0 )
                  {
                    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                      CallStackTracing::s_wpInstance = v38;
                      if ( v38
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(
                             v38,
                             2032) )
                      {
                        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v37 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v37 + 8) )
                    {
                      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                      if ( *((_DWORD *)v39 + 499) != v8 )
                        CallStackContext::TraceFailure(v39, "CAVIMediaSourcePlugin::SetStreamSelection", 1369, v8);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_93;
                    v36 = 142;
                    goto LABEL_92;
                  }
                  if ( v58 == v57 )
                  {
                    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 280LL))(
                           *((_QWORD *)this + 7),
                           v26);
                    if ( v8 >= 0 )
                    {
                      ++v24;
                      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v60);
                      goto LABEL_61;
                    }
                    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                      CallStackTracing::s_wpInstance = v34;
                      if ( v34
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(
                             v34,
                             2032) )
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
                      if ( *((_DWORD *)v35 + 499) != v8 )
                        CallStackContext::TraceFailure(v35, "CAVIMediaSourcePlugin::SetStreamSelection", 1372, v8);
                    }
                    if ( g_wppLevels )
                    {
                      v36 = 143;
                      goto LABEL_92;
                    }
LABEL_93:
                    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v60);
                    goto LABEL_115;
                  }
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v60);
                  ++v26;
                }
                v40 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                  CallStackTracing::s_wpInstance = v41;
                  if ( v41
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                  {
                    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v40 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v40 + 8) )
                {
                  v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                  if ( *((_DWORD *)v42 + 499) != v8 )
                    CallStackContext::TraceFailure(v42, "CAVIMediaSourcePlugin::SetStreamSelection", 1368, v8);
                }
                if ( !g_wppLevels )
                  goto LABEL_93;
                v36 = 141;
LABEL_92:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v36,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  (char *)this - 16,
                  v8);
                goto LABEL_93;
              }
              v43 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
                CallStackTracing::s_wpInstance = v44;
                if ( v44
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  v43 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v43 + 8) )
              {
                v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                if ( *((_DWORD *)v45 + 499) != v8 )
                  CallStackContext::TraceFailure(v45, "CAVIMediaSourcePlugin::SetStreamSelection", 1362, v8);
              }
              if ( g_wppLevels )
              {
                v46 = 140;
                goto LABEL_114;
              }
              goto LABEL_115;
            }
LABEL_61:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v59);
            ++v5;
          }
          if ( !v24 )
          {
            if ( byte_1801B1109 )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                144,
                &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                (char *)this - 16);
            v50 = (wchar_t *)CallStackTracing::s_wpInstance;
            v8 = -2147024809;
            if ( !CallStackTracing::s_wpInstance )
            {
              v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
              CallStackTracing::s_wpInstance = v51;
              if ( v51
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
              {
                v50 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v50 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v50 + 8) )
            {
              v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
              if ( *((_DWORD *)v52 + 499) != -2147024809 )
                CallStackContext::TraceFailure(v52, "CAVIMediaSourcePlugin::SetStreamSelection", 1386, -2147024809);
            }
            if ( g_wppLevels )
            {
              v11 = 145;
              goto LABEL_139;
            }
          }
        }
        else
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
            if ( *((_DWORD *)v19 + 499) != v8 )
              CallStackContext::TraceFailure(v19, "CAVIMediaSourcePlugin::SetStreamSelection", 1345, v8);
          }
          if ( g_wppLevels )
          {
            v11 = 137;
            goto LABEL_139;
          }
        }
      }
      else
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != v8 )
            CallStackContext::TraceFailure(v15, "CAVIMediaSourcePlugin::SetStreamSelection", 1339, v8);
        }
        if ( g_wppLevels )
        {
          v11 = 136;
          goto LABEL_139;
        }
      }
    }
    else
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      v8 = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
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
        if ( *((_DWORD *)v55 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v55, "CAVIMediaSourcePlugin::SetStreamSelection", 1333, -1072875854);
      }
      if ( g_wppLevels )
      {
        v11 = 135;
        goto LABEL_139;
      }
    }
  }
  else
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CAVIMediaSourcePlugin::SetStreamSelection", 1329, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 134;
LABEL_139:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        (char *)this - 16,
        v8);
    }
  }
LABEL_140:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v61);
  return (unsigned int)v8;
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
