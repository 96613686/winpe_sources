# CAVIMediaSourcePlugin::SetStreamSelection(IMFPresentationDescriptor *)

- ea: `0x1800cd930`
- end: `0x1800ce21d`
- name: `?SetStreamSelection@CAVIMediaSourcePlugin@@UEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2285`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x1800cd930`
- `0x180121750`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd998`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cda54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdb06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdbc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdd67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cddfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cde91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdf49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdfde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce0cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cd998`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cda54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdb06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdbc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdd67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cddfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cde91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdf49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cdfde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce0cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce166`

## string_xrefs

- `0x1800cd947`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800cddc4`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800cde59`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800cdeee`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800cdfa6`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800ce03b`: `CAVIMediaSourcePlugin::SetStreamSelection`
- `0x1800ce129`: `CAVIMediaSourcePlugin::SetStreamSelection`

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
                  v21 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v47 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v37 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v33 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v40 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v43 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            if ( byte_1801BA109 )
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
                v50 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v17 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v13 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v53 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800cd930  push    rbp
0x1800cd932  push    rbx
0x1800cd933  push    rsi
0x1800cd934  push    rdi
0x1800cd935  push    r12
0x1800cd937  push    r13
0x1800cd939  push    r14
0x1800cd93b  push    r15
0x1800cd93d  mov     rbp, rsp
0x1800cd940  sub     rsp, 58h
0x1800cd944  mov     r12, rdx
0x1800cd947  lea     r15, aCavimediasourc_9; "CAVIMediaSourcePlugin::SetStreamSelecti"...
0x1800cd94e  mov     r13, rcx
0x1800cd951  mov     rdx, r15; char *
0x1800cd954  mov     r8d, 526h; int
0x1800cd95a  lea     rcx, [rbp+arg_0]; this
0x1800cd95e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cd963  xor     r14d, r14d
0x1800cd966  lea     rdi, [r13-10h]
0x1800cd96a  mov     [rbp+arg_18], r14d
0x1800cd96e  mov     [rbp+arg_8], r14d
0x1800cd972  mov     [rbp+arg_10], r14d
0x1800cd976  mov     [rbp+var_24], r14d
0x1800cd97a  mov     [rbp+var_28], r14d
0x1800cd97e  test    r12, r12
0x1800cd981  jnz     loc_1800CDA1D
0x1800cd987  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd98e  mov     ebx, 80004003h
0x1800cd993  test    rcx, rcx
0x1800cd996  jnz     short loc_1800CD9DF
0x1800cd998  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cd99f  nop     dword ptr [rax+rax+00h]
0x1800cd9a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd9ab  mov     rcx, rax
0x1800cd9ae  test    rax, rax
0x1800cd9b1  jz      short loc_1800CD9D1
0x1800cd9b3  mov     rax, [rax]
0x1800cd9b6  mov     edx, 7F0h
0x1800cd9bb  mov     rax, [rax+8]
0x1800cd9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd9c4  test    eax, eax
0x1800cd9c6  jz      short loc_1800CD9D1
0x1800cd9c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd9cf  jmp     short loc_1800CD9DF
0x1800cd9d1  lea     rcx, qword_1801B97E0; this
0x1800cd9d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd9df  cmp     [rcx+8], r14b
0x1800cd9e3  jz      short loc_1800CDA06
0x1800cd9e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd9ea  cmp     [rax+7CCh], ebx
0x1800cd9f0  jz      short loc_1800CDA06
0x1800cd9f2  mov     r9d, ebx; int
0x1800cd9f5  mov     r8d, 531h; int
0x1800cd9fb  mov     rdx, r15; char *
0x1800cd9fe  mov     rcx, rax; this
0x1800cda01  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cda06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cda0d  jb      loc_1800CE200
0x1800cda13  mov     edx, 86h
0x1800cda18  jmp     loc_1800CE1E2
0x1800cda1d  cmp     [rdi+48h], r14
0x1800cda21  jz      loc_1800CE155
0x1800cda27  mov     rax, [r12]
0x1800cda2b  lea     rdx, [rbp+arg_10]
0x1800cda2f  mov     rcx, r12
0x1800cda32  mov     rax, [rax+108h]
0x1800cda39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cda3e  mov     ebx, eax
0x1800cda40  test    eax, eax
0x1800cda42  jns     loc_1800CDAD9
0x1800cda48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda4f  test    rcx, rcx
0x1800cda52  jnz     short loc_1800CDA9B
0x1800cda54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cda5b  nop     dword ptr [rax+rax+00h]
0x1800cda60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda67  mov     rcx, rax
0x1800cda6a  test    rax, rax
0x1800cda6d  jz      short loc_1800CDA8D
0x1800cda6f  mov     rax, [rax]
0x1800cda72  mov     edx, 7F0h
0x1800cda77  mov     rax, [rax+8]
0x1800cda7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cda80  test    eax, eax
0x1800cda82  jz      short loc_1800CDA8D
0x1800cda84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda8b  jmp     short loc_1800CDA9B
0x1800cda8d  lea     rcx, qword_1801B97E0; this
0x1800cda94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cda9b  cmp     [rcx+8], r14b
0x1800cda9f  jz      short loc_1800CDAC2
0x1800cdaa1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cdaa6  cmp     [rax+7CCh], ebx
0x1800cdaac  jz      short loc_1800CDAC2
0x1800cdaae  mov     r9d, ebx; int
0x1800cdab1  mov     r8d, 53Bh; int
0x1800cdab7  mov     rdx, r15; char *
0x1800cdaba  mov     rcx, rax; this
0x1800cdabd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cdac2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdac9  jb      loc_1800CE200
0x1800cdacf  mov     edx, 88h
0x1800cdad4  jmp     loc_1800CE1E2
0x1800cdad9  mov     rcx, [rdi+48h]
0x1800cdadd  lea     rdx, [rbp+arg_8]
0x1800cdae1  mov     rax, [rcx]
0x1800cdae4  mov     rax, [rax+108h]
0x1800cdaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdaf0  mov     ebx, eax
0x1800cdaf2  test    eax, eax
0x1800cdaf4  jns     loc_1800CDB8B
0x1800cdafa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdb01  test    rcx, rcx
0x1800cdb04  jnz     short loc_1800CDB4D
0x1800cdb06  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cdb0d  nop     dword ptr [rax+rax+00h]
0x1800cdb12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdb19  mov     rcx, rax
0x1800cdb1c  test    rax, rax
0x1800cdb1f  jz      short loc_1800CDB3F
0x1800cdb21  mov     rax, [rax]
0x1800cdb24  mov     edx, 7F0h
0x1800cdb29  mov     rax, [rax+8]
0x1800cdb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb32  test    eax, eax
0x1800cdb34  jz      short loc_1800CDB3F
0x1800cdb36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdb3d  jmp     short loc_1800CDB4D
0x1800cdb3f  lea     rcx, qword_1801B97E0; this
0x1800cdb46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdb4d  cmp     [rcx+8], r14b
0x1800cdb51  jz      short loc_1800CDB74
0x1800cdb53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cdb58  cmp     [rax+7CCh], ebx
0x1800cdb5e  jz      short loc_1800CDB74
0x1800cdb60  mov     r9d, ebx; int
0x1800cdb63  mov     r8d, 541h; int
0x1800cdb69  mov     rdx, r15; char *
0x1800cdb6c  mov     rcx, rax; this
0x1800cdb6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cdb74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdb7b  jb      loc_1800CE200
0x1800cdb81  mov     edx, 89h
0x1800cdb86  jmp     loc_1800CE1E2
0x1800cdb8b  mov     esi, r14d
0x1800cdb8e  cmp     esi, [rbp+arg_8]
0x1800cdb91  jnb     loc_1800CDC47
0x1800cdb97  mov     rcx, [r13+38h]
0x1800cdb9b  mov     edx, esi
0x1800cdb9d  mov     rax, [rcx]
0x1800cdba0  mov     rax, [rax+120h]
0x1800cdba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdbac  mov     ebx, eax
0x1800cdbae  test    eax, eax
0x1800cdbb0  js      short loc_1800CDBB6
0x1800cdbb2  inc     esi
0x1800cdbb4  jmp     short loc_1800CDB8E
0x1800cdbb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdbbd  test    rcx, rcx
0x1800cdbc0  jnz     short loc_1800CDC09
0x1800cdbc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cdbc9  nop     dword ptr [rax+rax+00h]
0x1800cdbce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdbd5  mov     rcx, rax
0x1800cdbd8  test    rax, rax
0x1800cdbdb  jz      short loc_1800CDBFB
0x1800cdbdd  mov     rax, [rax]
0x1800cdbe0  mov     edx, 7F0h
0x1800cdbe5  mov     rax, [rax+8]
0x1800cdbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdbee  test    eax, eax
0x1800cdbf0  jz      short loc_1800CDBFB
0x1800cdbf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdbf9  jmp     short loc_1800CDC09
0x1800cdbfb  lea     rcx, qword_1801B97E0; this
0x1800cdc02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdc09  cmp     [rcx+8], r14b
0x1800cdc0d  jz      short loc_1800CDC30
0x1800cdc0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cdc14  cmp     [rax+7CCh], ebx
0x1800cdc1a  jz      short loc_1800CDC30
0x1800cdc1c  mov     r9d, ebx; int
0x1800cdc1f  mov     r8d, 549h; int
0x1800cdc25  mov     rdx, r15; char *
0x1800cdc28  mov     rcx, rax; this
0x1800cdc2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cdc30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdc37  jb      loc_1800CE200
0x1800cdc3d  mov     edx, 8Ah
0x1800cdc42  jmp     loc_1800CE1E2
0x1800cdc47  mov     r15d, r14d
0x1800cdc4a  cmp     r14d, [rbp+arg_10]
0x1800cdc4e  jnb     loc_1800CE08A
0x1800cdc54  mov     rax, [r12]
0x1800cdc58  lea     r9, [rbp+var_20]
0x1800cdc5c  xor     esi, esi
0x1800cdc5e  lea     r8, [rbp+arg_18]
0x1800cdc62  mov     edx, r14d
0x1800cdc65  mov     [rbp+var_20], rsi
0x1800cdc69  mov     rcx, r12
0x1800cdc6c  mov     rax, [rax+110h]
0x1800cdc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdc78  mov     ebx, eax
0x1800cdc7a  test    eax, eax
0x1800cdc7c  js      loc_1800CDFD2
0x1800cdc82  cmp     [rbp+arg_18], esi
0x1800cdc85  jz      loc_1800CDD4A
0x1800cdc8b  mov     rcx, [rbp+var_20]
0x1800cdc8f  lea     rdx, [rbp+var_24]
0x1800cdc93  mov     rax, [rcx]
0x1800cdc96  mov     rax, [rax+108h]
0x1800cdc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdca2  mov     ebx, eax
0x1800cdca4  test    eax, eax
0x1800cdca6  js      loc_1800CDF3D
0x1800cdcac  cmp     esi, [rbp+arg_8]
0x1800cdcaf  jnb     loc_1800CDD4A
0x1800cdcb5  mov     rcx, [r13+38h]
0x1800cdcb9  lea     r9, [rbp+var_18]
0x1800cdcbd  mov     [rbp+var_18], 0
0x1800cdcc5  lea     r8, [rbp+arg_0]
0x1800cdcc9  mov     [rbp+arg_0], 0
0x1800cdcd0  mov     edx, esi
0x1800cdcd2  mov     rax, [rcx]
0x1800cdcd5  mov     rax, [rax+110h]
0x1800cdcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdce1  mov     ebx, eax
0x1800cdce3  test    eax, eax
0x1800cdce5  js      loc_1800CDE85
0x1800cdceb  mov     rcx, [rbp+var_18]
0x1800cdcef  lea     rdx, [rbp+var_28]
0x1800cdcf3  mov     rax, [rcx]
0x1800cdcf6  mov     rax, [rax+108h]
0x1800cdcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd02  mov     ebx, eax
0x1800cdd04  test    eax, eax
0x1800cdd06  js      loc_1800CDDF0
0x1800cdd0c  mov     eax, [rbp+var_28]
0x1800cdd0f  cmp     [rbp+var_24], eax
0x1800cdd12  jz      short loc_1800CDD21
0x1800cdd14  lea     rcx, [rbp+var_18]; void *
0x1800cdd18  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cdd1d  inc     esi
0x1800cdd1f  jmp     short loc_1800CDCAC
0x1800cdd21  mov     rcx, [r13+38h]
0x1800cdd25  mov     edx, esi
0x1800cdd27  mov     rax, [rcx]
0x1800cdd2a  mov     rax, [rax+118h]
0x1800cdd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd36  xor     esi, esi
0x1800cdd38  mov     ebx, eax
0x1800cdd3a  test    eax, eax
0x1800cdd3c  js      short loc_1800CDD5B
0x1800cdd3e  inc     r15d
0x1800cdd41  lea     rcx, [rbp+var_18]; void *
0x1800cdd45  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cdd4a  lea     rcx, [rbp+var_20]; void *
0x1800cdd4e  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cdd53  inc     r14d
0x1800cdd56  jmp     loc_1800CDC4A
0x1800cdd5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd62  test    rcx, rcx
0x1800cdd65  jnz     short loc_1800CDDAE
0x1800cdd67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cdd6e  nop     dword ptr [rax+rax+00h]
0x1800cdd73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd7a  mov     rcx, rax
0x1800cdd7d  test    rax, rax
0x1800cdd80  jz      short loc_1800CDDA0
0x1800cdd82  mov     rax, [rax]
0x1800cdd85  mov     edx, 7F0h
0x1800cdd8a  mov     rax, [rax+8]
0x1800cdd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd93  test    eax, eax
0x1800cdd95  jz      short loc_1800CDDA0
0x1800cdd97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdd9e  jmp     short loc_1800CDDAE
0x1800cdda0  lea     rcx, qword_1801B97E0; this
0x1800cdda7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cddae  cmp     [rcx+8], sil
0x1800cddb2  jz      short loc_1800CDDD9
0x1800cddb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cddb9  cmp     [rax+7CCh], ebx
0x1800cddbf  jz      short loc_1800CDDD9
0x1800cddc1  mov     r9d, ebx; int
0x1800cddc4  lea     rdx, aCavimediasourc_9; "CAVIMediaSourcePlugin::SetStreamSelecti"...
0x1800cddcb  mov     r8d, 55Ch; int
0x1800cddd1  mov     rcx, rax; this
0x1800cddd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cddd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdde0  jb      loc_1800CDF2F
0x1800cdde6  mov     edx, 8Fh
0x1800cddeb  jmp     loc_1800CDF11
0x1800cddf0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cddf7  test    rcx, rcx
0x1800cddfa  jnz     short loc_1800CDE43
0x1800cddfc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cde03  nop     dword ptr [rax+rax+00h]
0x1800cde08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cde0f  mov     rcx, rax
  ... truncated ...
```
