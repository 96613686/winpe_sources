# CSAMIMediaSource::OnSamplesNeeded(CBytewiseMediaStream *)

- ea: `0x180087d40`
- end: `0x180088fa9`
- name: `?OnSamplesNeeded@CSAMIMediaSource@@EEAAJPEAVCBytewiseMediaStream@@@Z`
- size: `4713`
- prototype: `__int64 __fastcall(DWORD *this, struct CBytewiseMediaStream *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1800090fc`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x1800404e0`
- `0x18004689c`
- `0x180073b14`
- `0x18007450c`
- `0x180087d40`
- `0x180093b3c`
- `0x1801099f0`
- `0x18011b1e4`
- `0x180131e94`
- `0x180131f44`
- `0x180153d0c`
- `0x180153dc8`
- `0x180153fb0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800883ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088441`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800884d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800885fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088690`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088727`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800887b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088850`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800888e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008897b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088a1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088b77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088cd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ecc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800883ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088441`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800884d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800885fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088690`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088727`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800887b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088850`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800888e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008897b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088a1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ae5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088b77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088cd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ecc`
- `MFPlat!MFCreateMemoryBuffer` at `0x180087e6f`
- `MFPlat!MFCreateMemoryBuffer` at `0x180087e6f`

## pseudocode

```c
__int64 __fastcall CSAMIMediaSource::OnSamplesNeeded(DWORD *this, struct CBytewiseMediaStream *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // r15
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int64 v12; // rax
  char v13; // cl
  IMFMediaBuffer *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  HRESULT v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r13
  DWORD v23; // eax
  wchar_t *v24; // rbx
  CallStackTracing *v25; // rax
  __int64 v26; // rcx
  char *v27; // r10
  size_t v28; // r11
  __int64 v29; // r15
  const char *v30; // r8
  const char *v31; // rdx
  const char *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rax
  int *v35; // r13
  void *v36; // rcx
  size_t v37; // r11
  char *v38; // r15
  unsigned __int64 v39; // r9
  const char *v40; // r8
  __int64 v41; // rcx
  __int64 v42; // r11
  __int64 v43; // rax
  __int64 v44; // rcx
  const char *v45; // rcx
  const char *v46; // r8
  const char *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  const char **v50; // r11
  void *v51; // rcx
  char *v52; // r10
  size_t v53; // r13
  int v54; // eax
  CVPtrList *v55; // rcx
  __int64 v56; // r11
  __int64 v57; // rax
  unsigned __int64 v58; // r15
  __int64 v59; // r15
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // r13
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  wchar_t *v70; // rbx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  wchar_t *v74; // rbx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  wchar_t *v77; // rbx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  wchar_t *v80; // rbx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 v83; // rdx
  wchar_t *v84; // rbx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  wchar_t *v87; // rbx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  wchar_t *v90; // rbx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  wchar_t *v93; // rbx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  wchar_t *v96; // rbx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  wchar_t *v99; // rbx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  wchar_t *v102; // rcx
  CallStackTracing *v103; // rax
  struct CallStackContext *v104; // rax
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 v107; // rcx
  wchar_t *v108; // rbx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  wchar_t *v111; // rbx
  CallStackTracing *v112; // rax
  struct CallStackContext *v113; // rax
  wchar_t *v114; // rbx
  CallStackTracing *v115; // rax
  struct CallStackContext *v116; // rax
  wchar_t *v117; // rbx
  CallStackTracing *v118; // rax
  struct CallStackContext *v119; // rax
  wchar_t *v120; // rbx
  CallStackTracing *v121; // rax
  struct CallStackContext *v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rcx
  wchar_t *v125; // rbx
  CallStackTracing *v126; // rax
  struct CallStackContext *v127; // rax
  wchar_t *v128; // rbx
  CallStackTracing *v129; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v132[8]; // [rsp+50h] [rbp-49h] BYREF
  void *v133; // [rsp+58h] [rbp-41h] BYREF
  char *v134; // [rsp+60h] [rbp-39h] BYREF
  size_t Size; // [rsp+68h] [rbp-31h] BYREF
  void *v136; // [rsp+70h] [rbp-29h] BYREF
  __int64 v137; // [rsp+78h] [rbp-21h]
  char *v138; // [rsp+80h] [rbp-19h]
  __int64 v139; // [rsp+88h] [rbp-11h]
  __int64 v140; // [rsp+90h] [rbp-9h]
  char *Buffer; // [rsp+98h] [rbp-1h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+A0h] [rbp+7h] BYREF
  unsigned __int64 v143; // [rsp+A8h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v132, "CSAMIMediaSource::OnSamplesNeeded", 802);
  ppBuffer = 0;
  if ( !a2 )
  {
    v128 = (wchar_t *)CallStackTracing::s_wpInstance;
    v17 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v129 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4);
      CallStackTracing::s_wpInstance = v129;
      if ( v129 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v129 + 8LL))(v129, 2032) )
      {
        v128 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v128 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v128 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v128);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSAMIMediaSource::OnSamplesNeeded", 812, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
        this,
        -2147467261);
    goto LABEL_282;
  }
  while ( 2 )
  {
    v6 = this[189];
    v7 = *((_QWORD *)a2 + 29);
    v8 = *((unsigned int *)a2 + 60);
    if ( 10000 * v6 > v7 )
      *((_QWORD *)a2 + 29) = 10000 * v6;
    v9 = *(_QWORD *)this;
    v143 = 0;
    if ( (*(int (__fastcall **)(DWORD *, unsigned __int64 *))(v9 + 120))(this, &v143) >= 0 )
    {
      v12 = v143;
    }
    else
    {
      v12 = 0;
      v143 = 0;
    }
    v13 = byte_1801B110B;
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    {
      WPP_SF_qiI(*((_QWORD *)WPP_GLOBAL_Control + 17), v10, v11, this, v7, v12);
      v12 = v143;
      v13 = byte_1801B110B;
    }
    if ( v7 == 0x7FFFFFFFFFFFFFFFLL || v7 > v12 )
    {
      if ( (unsigned __int8)v13 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 100, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this);
      v17 = CMediaSourceBase::SetEndOfStream((CMediaSourceBase *)this, a2);
      if ( v17 >= 0 )
        break;
      v125 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v126 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v124, v123);
        CallStackTracing::s_wpInstance = v126;
        if ( v126 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v126 + 8LL))(v126, 2032) )
        {
          v125 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v125 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v125 + 8) )
      {
        v127 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v125);
        if ( *((_DWORD *)v127 + 499) != v17 )
          CallStackContext::TraceFailure(v127, "CSAMIMediaSource::OnSamplesNeeded", 863, v17);
      }
      if ( !g_wppLevels )
        break;
      v83 = 101;
LABEL_121:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v83, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this, v17);
      break;
    }
    v14 = ppBuffer;
    v137 = *((_QWORD *)a2 + 29);
    if ( ppBuffer )
    {
      ppBuffer = 0;
      ((void (__fastcall *)(IMFMediaBuffer *))v14->lpVtbl->Release)(v14);
    }
    v17 = MFCreateMemoryBuffer(this[649], &ppBuffer);
    if ( v17 < 0 )
    {
      v120 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v121 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
        CallStackTracing::s_wpInstance = v121;
        if ( v121 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v121 + 8LL))(v121, 2032) )
        {
          v120 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v120 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v120 + 8) )
      {
        v122 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v120);
        if ( *((_DWORD *)v122 + 499) != v17 )
          CallStackContext::TraceFailure(v122, "CSAMIMediaSource::OnSamplesNeeded", 878, v17);
      }
      if ( !g_wppLevels )
        break;
      v83 = 102;
      goto LABEL_121;
    }
    Buffer = 0;
    v17 = ((__int64 (__fastcall *)(IMFMediaBuffer *, char **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &Buffer,
            0,
            0);
    if ( v17 < 0 )
    {
      v117 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v118 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
        CallStackTracing::s_wpInstance = v118;
        if ( v118 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v118 + 8LL))(v118, 2032) )
        {
          v117 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v117 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v117 + 8) )
      {
        v119 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v117);
        if ( *((_DWORD *)v119 + 499) != v17 )
          CallStackContext::TraceFailure(v119, "CSAMIMediaSource::OnSamplesNeeded", 885, v17);
      }
      if ( !g_wppLevels )
        break;
      v83 = 103;
      goto LABEL_121;
    }
    v21 = 0;
    v22 = *((_QWORD *)this + 325) + 8 * v8;
    v139 = v22;
    if ( !v22 )
    {
      v114 = (wchar_t *)CallStackTracing::s_wpInstance;
      v17 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v115 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
        CallStackTracing::s_wpInstance = v115;
        if ( v115 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v115 + 8LL))(v115, 2032) )
        {
          v114 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v114 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v114 + 8) )
      {
        v116 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v114);
        if ( *((_DWORD *)v116 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v116, "CSAMIMediaSource::OnSamplesNeeded", 892, -2147467261);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v69 = 104;
LABEL_236:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v69,
        &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
        this,
        -2147467261);
LABEL_237:
      if ( ppBuffer )
        ((void (__fastcall *)(IMFMediaBuffer *, __int64, __int64, __int64))ppBuffer->lpVtbl->Unlock)(
          ppBuffer,
          v18,
          v20,
          v21);
      break;
    }
    v23 = this[653];
    if ( v23 == -1 )
    {
      v138 = 0;
    }
    else
    {
      v138 = (char *)(*((_QWORD *)this + 327) + 8LL * v23);
      if ( !v138 )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        v17 = -2147467261;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v68 + 499) != -2147467261 )
            CallStackContext::TraceFailure(v68, "CSAMIMediaSource::OnSamplesNeeded", 898, -2147467261);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v69 = 105;
        goto LABEL_236;
      }
    }
    v26 = *(_QWORD *)v22;
    v27 = Buffer;
    v28 = this[649];
    v134 = Buffer;
    v29 = v137 / 10000;
    Size = v28;
    v140 = v137 / 10000;
    v137 = 0x7FFFFFFFFFFFFFFFLL;
    if ( *(_DWORD *)(v26 + 904) )
    {
      v30 = (const char *)&byte_180185A40;
      v31 = (const char *)&byte_180185A40;
      if ( *((_QWORD *)this + 322) )
        v30 = (const char *)*((_QWORD *)this + 322);
      if ( *(_QWORD *)(v26 + 8) )
        v31 = *(const char **)(v26 + 8);
      v32 = (const char *)&byte_180185A40;
      if ( *((_QWORD *)this + 323) )
        v32 = (const char *)*((_QWORD *)this + 323);
      v17 = StringCchPrintfExA(Buffer, (unsigned int)v28, &v134, &Size, 0, "<P STYLE=\"%s %s %s\">", v32, v31, v30);
      if ( v17 < 0 )
      {
        v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v33, v18);
          CallStackTracing::s_wpInstance = v78;
          if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
          {
            v77 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v77 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v77 + 8) )
        {
          v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
          if ( *((_DWORD *)v79 + 499) != v17 )
            CallStackContext::TraceFailure(v79, "CSAMIMediaSource::OnSamplesNeeded", 967, v17);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v73 = 112;
      }
      else
      {
        v34 = *(_QWORD *)v22;
        v35 = 0;
        v36 = *(void **)(v34 + 888);
        v133 = v36;
        while ( v36 )
        {
          v136 = 0;
          CVPtrList::GetNext((CVPtrList *)v36, &v133, &v136);
          if ( *(unsigned int *)v136 > v29 )
            break;
          v36 = v133;
          v35 = (int *)v136;
        }
        v37 = Size;
        v38 = v134;
        if ( v35 )
        {
          v39 = v35[4];
          v40 = (const char *)*((_QWORD *)v35 + 1);
          LODWORD(v133) = *v35;
          v17 = StringCbCopyNA(v134, Size, v40, v39);
          if ( v17 < 0 )
          {
            v70 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v41, v18);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
              {
                v70 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v70 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v70 + 8) )
            {
              v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
              if ( *((_DWORD *)v72 + 499) != v17 )
                CallStackContext::TraceFailure(v72, "CSAMIMediaSource::OnSamplesNeeded", 1001, v17);
            }
            if ( !g_wppLevels )
              goto LABEL_237;
            v73 = 113;
            goto LABEL_90;
          }
          v137 = (unsigned int)v133;
          v43 = v35[4];
          v38 += v43;
          v37 = v42 - v43;
          v134 = v38;
          Size = v37;
        }
        v17 = StringCchPrintfExA(v38, v37, &v134, &Size, 0, "%s", "</P>");
        if ( v17 >= 0 )
        {
          v27 = v134;
          v28 = Size;
          v29 = v140;
          v22 = v139;
          goto LABEL_40;
        }
        v74 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, v18);
          CallStackTracing::s_wpInstance = v75;
          if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
          {
            v74 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v74 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v74 + 8) )
        {
          v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
          if ( *((_DWORD *)v76 + 499) != v17 )
            CallStackContext::TraceFailure(v76, "CSAMIMediaSource::OnSamplesNeeded", 1013, v17);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v73 = 114;
      }
LABEL_90:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v73, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this, v17);
      goto LABEL_237;
    }
LABEL_40:
    if ( !v138 || !*(_QWORD *)v138 || (v45 = *(const char **)(*(_QWORD *)v138 + 8LL)) == 0 )
      v45 = (const char *)&byte_180185A40;
    v46 = (const char *)&byte_180185A40;
    v47 = (const char *)&byte_180185A40;
    if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) )
      v46 = *(const char **)(*(_QWORD *)v22 + 8LL);
    if ( *((_QWORD *)this + 323) )
      v47 = (const char *)*((_QWORD *)this + 323);
    v17 = StringCchPrintfExA(v27, v28, &v134, &Size, 0, "<P STYLE=\"%s %s %s\">", v47, v46, v45);
    if ( v17 < 0 )
    {
      v111 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v112 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v48, v18);
        CallStackTracing::s_wpInstance = v112;
        if ( v112 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v112 + 8LL))(v112, 2032) )
        {
          v111 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v111 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v111 + 8) )
      {
        v113 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v111);
        if ( *((_DWORD *)v113 + 499) != v17 )
          CallStackContext::TraceFailure(v113, "CSAMIMediaSource::OnSamplesNeeded", 1033, v17);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v73 = 116;
      goto LABEL_90;
    }
    v49 = *(_QWORD *)v22;
    v50 = 0;
    v136 = 0;
    v51 = *(void **)(v49 + 440);
    v133 = v51;
    while ( v133 )
    {
      CVPtrList::GetNext((CVPtrList *)v51, &v133, &v136);
      v50 = (const char **)v136;
      if ( *(unsigned int *)v136 >= v29 )
      {
        v137 = *(unsigned int *)v136;
        break;
      }
    }
    if ( !v50 )
    {
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 117, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this);
      v17 = CMediaSourceBase::SetEndOfStream((CMediaSourceBase *)this, a2);
      if ( v17 >= 0 )
        goto LABEL_237;
      v108 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v107, v18);
        CallStackTracing::s_wpInstance = v109;
        if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
        {
          v108 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v108 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v108 + 8) )
      {
        v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
        if ( *((_DWORD *)v110 + 499) != v17 )
          CallStackContext::TraceFailure(v110, "CSAMIMediaSource::OnSamplesNeeded", 1070, v17);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v73 = 118;
      goto LABEL_90;
    }
    v52 = v134;
    v53 = Size;
    v138 = v134;
    while ( 1 )
    {
      v54 = StringCbCopyNA(v52, v53, v50[1], *((int *)v50 + 4));
      v21 = 0;
      v17 = v54;
      if ( v54 < 0 )
      {
        v102 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v103 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v103;
          if ( v103 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v103 + 8LL))(v103, 2032) )
          {
            v102 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v102 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v102 + 8) )
        {
          v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v102);
          if ( *((_DWORD *)v104 + 499) != v17 )
            CallStackContext::TraceFailure(v104, "CSAMIMediaSource::OnSamplesNeeded", 1083, v17);
          v102 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        if ( g_wppLevels )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
            this,
            v17);
          v102 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        if ( !v102 )
        {
          v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v105;
          if ( v105 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(v105, 2032) )
          {
            v102 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v102 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v102 + 8) )
        {
          v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v102);
          if ( *((_DWORD *)v106 + 499) != v17 )
            CallStackContext::TraceFailure(v106, "CSAMIMediaSource::OnSamplesNeeded", 1111, v17);
        }
        if ( g_wppLevels )
        {
          v73 = 120;
          goto LABEL_90;
        }
        goto LABEL_237;
      }
      v57 = *(int *)(v56 + 16);
      v53 -= v57;
      v138 += v57;
      if ( !v133 )
        break;
      CVPtrList::GetNext(v55, &v133, &v136);
      v50 = (const char **)v136;
      v58 = *(unsigned int *)v136;
      if ( v58 > v137 )
      {
        v59 = v58 - v137;
        goto LABEL_60;
      }
    }
    v59 = 0x7FFFFFFFFFFFFFFFLL;
LABEL_60:
    LODWORD(v133) = v21;
    LODWORD(v134) = v21;
    v17 = ULongLongToULong(v53, (unsigned int *)&v134);
    if ( v17 < 0 )
    {
      v99 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v60, v18);
        CallStackTracing::s_wpInstance = v100;
        if ( v100 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
        {
          v99 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v99 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v99 + 8) )
      {
        v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
        if ( *((_DWORD *)v101 + 499) != v17 )
          CallStackContext::TraceFailure(v101, "CSAMIMediaSource::OnSamplesNeeded", 1120, v17);
      }
      if ( g_wppLevels )
      {
        v73 = 121;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v17 = ULongSub(this[649], (unsigned int)v134, (unsigned int *)&v133);
    if ( v17 < 0 )
    {
      v96 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v61, v18);
        CallStackTracing::s_wpInstance = v97;
        if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
        {
          v96 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v96 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v96 + 8) )
      {
        v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
        if ( *((_DWORD *)v98 + 499) != v17 )
          CallStackContext::TraceFailure(v98, "CSAMIMediaSource::OnSamplesNeeded", 1122, v17);
      }
      if ( g_wppLevels )
      {
        v73 = 122;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v18 = (unsigned int)((_DWORD)v133 + 1);
    if ( (unsigned int)v18 < (unsigned int)v133 )
    {
      v93 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v61, v18);
        CallStackTracing::s_wpInstance = v94;
        if ( v94 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
        {
          v93 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v93 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      v17 = -2147024362;
      if ( *((_BYTE *)v93 + 8) )
      {
        v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
        if ( *((_DWORD *)v95 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v95, "CSAMIMediaSource::OnSamplesNeeded", 1124, -2147024362);
      }
      if ( g_wppLevels )
      {
        v73 = 123;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    if ( (unsigned int)v18 <= 1 )
    {
      v90 = (wchar_t *)CallStackTracing::s_wpInstance;
      v17 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v61, v18);
        CallStackTracing::s_wpInstance = v91;
        if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
        {
          v90 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v90 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v90 + 8) )
      {
        v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
        if ( *((_DWORD *)v92 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v92, "CSAMIMediaSource::OnSamplesNeeded", 1134, -1072875845);
      }
      if ( g_wppLevels )
      {
        v73 = 124;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    Buffer[(unsigned int)v133] = 0;
    v17 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
    if ( v17 < 0 )
    {
      v87 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v62, v18);
        CallStackTracing::s_wpInstance = v88;
        if ( v88 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
        {
          v87 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v87 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v87 + 8) )
      {
        v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
        if ( *((_DWORD *)v89 + 499) != v17 )
          CallStackContext::TraceFailure(v89, "CSAMIMediaSource::OnSamplesNeeded", 1141, v17);
      }
      if ( g_wppLevels )
      {
        v73 = 125;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v17 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    if ( v17 < 0 )
    {
      v84 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v63, v18);
        CallStackTracing::s_wpInstance = v85;
        if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
        {
          v84 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v84 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v84 + 8) )
      {
        v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
        if ( *((_DWORD *)v86 + 499) != v17 )
          CallStackContext::TraceFailure(v86, "CSAMIMediaSource::OnSamplesNeeded", 1147, v17);
      }
      if ( g_wppLevels )
      {
        v73 = 126;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v64 = 10000 * v137;
    v139 = 10000 * v59;
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      WPP_SF_qii(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        127,
        &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
        this,
        10000 * v137,
        10000 * v59);
    v17 = CMediaSourceBase::CreateAndAddSampleToQueue((CMediaSourceBase *)this, a2, ppBuffer, v64, 10000 * v59);
    if ( v17 < 0 )
    {
      v80 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v65);
        CallStackTracing::s_wpInstance = v81;
        if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
        {
          v80 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v80 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v80 + 8) )
      {
        v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
        if ( *((_DWORD *)v82 + 499) != v17 )
          CallStackContext::TraceFailure(v82, "CSAMIMediaSource::OnSamplesNeeded", 1158, v17);
      }
      if ( g_wppLevels )
      {
        v83 = 128;
        goto LABEL_121;
      }
    }
    else
    {
      if ( v59 == 0x7FFFFFFFFFFFFFFFLL )
        v67 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v67 = v64 + v139;
      *((_QWORD *)a2 + 29) = v67;
      if ( !CMediaSourceBase::IsSampleNeeded((CMediaSourceBase *)this, a2) )
        continue;
    }
    break;
  }
LABEL_282:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v132);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180087d40  mov     [rsp-8+arg_10], rbx
0x180087d45  push    rbp
0x180087d46  push    rsi
0x180087d47  push    rdi
0x180087d48  push    r12
0x180087d4a  push    r13
0x180087d4c  push    r14
0x180087d4e  push    r15
0x180087d50  lea     rbp, [rsp-27h]
0x180087d55  sub     rsp, 0C0h
0x180087d5c  mov     rax, cs:__security_cookie
0x180087d63  xor     rax, rsp
0x180087d66  mov     [rbp+57h+var_40], rax
0x180087d6a  mov     rbx, rdx
0x180087d6d  mov     rsi, rcx
0x180087d70  lea     rdx, aCsamimediasour_7; "CSAMIMediaSource::OnSamplesNeeded"
0x180087d77  mov     r8d, 322h; int
0x180087d7d  lea     rcx, [rbp+57h+var_A0]; this
0x180087d81  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180087d86  xor     r13d, r13d
0x180087d89  mov     [rbp+57h+ppBuffer], r13
0x180087d8d  test    rbx, rbx
0x180087d90  jz      loc_180088EB7
0x180087d96  lea     r14d, [r13+1]
0x180087d9a  lea     r12, WPP_0776a4c2c75433e71492a25261740b6d_Traceguids
0x180087da1  mov     eax, [rsi+2F4h]
0x180087da7  mov     rdi, [rbx+0E8h]
0x180087dae  mov     r15d, [rbx+0F0h]
0x180087db5  imul    rcx, rax, 2710h
0x180087dbc  cmp     rcx, rdi
0x180087dbf  jle     short loc_180087DC8
0x180087dc1  mov     [rbx+0E8h], rcx
0x180087dc8  mov     rax, [rsi]
0x180087dcb  lea     rdx, [rbp+57h+var_48]
0x180087dcf  mov     rcx, rsi
0x180087dd2  mov     [rbp+57h+var_48], r13
0x180087dd6  mov     rax, [rax+78h]
0x180087dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ddf  test    eax, eax
0x180087de1  jns     short loc_180087DEC
0x180087de3  mov     rax, r13
0x180087de6  mov     [rbp+57h+var_48], rax
0x180087dea  jmp     short loc_180087DF0
0x180087dec  mov     rax, [rbp+57h+var_48]
0x180087df0  mov     cl, cs:byte_1801B110B
0x180087df6  cmp     cl, 10h
0x180087df9  jb      short loc_180087E25
0x180087dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e02  mov     r9, rsi
0x180087e05  mov     [rsp+0F0h+var_C8], rax
0x180087e0a  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x180087e0f  mov     rcx, [rcx+88h]
0x180087e16  call    WPP_SF_qiI
0x180087e1b  mov     rax, [rbp+57h+var_48]
0x180087e1f  mov     cl, cs:byte_1801B110B
0x180087e25  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180087e2f  cmp     rdi, rdx
0x180087e32  jz      loc_180088DED
0x180087e38  cmp     rdi, rax
0x180087e3b  ja      loc_180088DED
0x180087e41  mov     rcx, [rbp+57h+ppBuffer]
0x180087e45  mov     rax, [rbx+0E8h]
0x180087e4c  mov     [rbp+57h+var_78], rax
0x180087e50  test    rcx, rcx
0x180087e53  jz      short loc_180087E65
0x180087e55  mov     [rbp+57h+ppBuffer], r13
0x180087e59  mov     rax, [rcx]
0x180087e5c  mov     rax, [rax+10h]
0x180087e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e65  mov     ecx, [rsi+0A24h]; cbMaxLength
0x180087e6b  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x180087e6f  call    cs:__imp_MFCreateMemoryBuffer
0x180087e75  mov     edi, eax
0x180087e77  test    eax, eax
0x180087e79  js      loc_180088D5B
0x180087e7f  mov     rcx, [rbp+57h+ppBuffer]
0x180087e83  lea     rdx, [rbp+57h+Buffer]
0x180087e87  mov     [rbp+57h+Buffer], r13
0x180087e8b  xor     r9d, r9d
0x180087e8e  xor     r8d, r8d
0x180087e91  mov     rax, [rcx]
0x180087e94  mov     rax, [rax+18h]
0x180087e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e9d  mov     edi, eax
0x180087e9f  test    eax, eax
0x180087ea1  js      loc_180088CC9
0x180087ea7  mov     rax, [rsi+0A28h]
0x180087eae  xor     r9d, r9d
0x180087eb1  lea     r13, [rax+r15*8]
0x180087eb5  mov     [rbp+57h+var_68], r13
0x180087eb9  test    r13, r13
0x180087ebc  jz      loc_180088BFD
0x180087ec2  mov     eax, [rsi+0A34h]
0x180087ec8  cmp     eax, 0FFFFFFFFh
0x180087ecb  jz      short loc_180087F3A
0x180087ecd  mov     ecx, eax
0x180087ecf  mov     rax, [rsi+0A38h]
0x180087ed6  lea     rcx, [rax+rcx*8]
0x180087eda  mov     [rbp+57h+var_70], rcx
0x180087ede  test    rcx, rcx
0x180087ee1  jnz     short loc_180087F3E
0x180087ee3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087eea  mov     r15d, 80004003h
0x180087ef0  mov     edi, r15d
0x180087ef3  test    rbx, rbx
0x180087ef6  jnz     loc_180088359
0x180087efc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180087f02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180087f09  mov     rcx, rax
0x180087f0c  test    rax, rax
0x180087f0f  jz      loc_18008834B
0x180087f15  mov     rax, [rax]
0x180087f18  mov     edx, 7F0h
0x180087f1d  mov     rax, [rax+8]
0x180087f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f26  test    eax, eax
0x180087f28  jz      loc_18008834B
0x180087f2e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087f35  jmp     loc_180088359
0x180087f3a  mov     [rbp+57h+var_70], r9
0x180087f3e  mov     rcx, [r13+0]
0x180087f42  mov     rax, 346DC5D63886594Bh
0x180087f4c  imul    [rbp+57h+var_78]
0x180087f50  mov     r10, [rbp+57h+Buffer]
0x180087f54  mov     r11d, [rsi+0A24h]
0x180087f5b  mov     r15, rdx
0x180087f5e  sar     r15, 0Bh
0x180087f62  mov     rax, r15
0x180087f65  mov     [rbp+57h+var_90], r10
0x180087f69  shr     rax, 3Fh
0x180087f6d  add     r15, rax
0x180087f70  mov     [rbp+57h+Size], r11
0x180087f74  mov     rax, 7FFFFFFFFFFFFFFFh
0x180087f7e  mov     [rbp+57h+var_60], r15
0x180087f82  mov     [rbp+57h+var_78], rax
0x180087f86  cmp     [rcx+388h], r9d
0x180087f8d  jbe     loc_1800880E0
0x180087f93  mov     rax, [rsi+0A10h]
0x180087f9a  lea     rdi, byte_180185A40
0x180087fa1  test    rax, rax
0x180087fa4  mov     r8, rdi
0x180087fa7  mov     rdx, rdi
0x180087faa  cmovnz  r8, rax
0x180087fae  cmp     [rcx+8], r9
0x180087fb2  mov     rax, [rsi+0A18h]
0x180087fb9  cmovnz  rdx, [rcx+8]
0x180087fbe  mov     rcx, rdi
0x180087fc1  mov     [rsp+0F0h+var_B0], r8
0x180087fc6  test    rax, rax
0x180087fc9  mov     [rsp+0F0h+var_B8], rdx
0x180087fce  lea     r8, [rbp+57h+var_90]; char **
0x180087fd2  cmovnz  rcx, rax
0x180087fd6  mov     edx, r11d; Size
0x180087fd9  mov     [rsp+0F0h+var_C0], rcx
0x180087fde  lea     rax, aPStyleSSS; "<P STYLE=\"%s %s %s\">"
0x180087fe5  mov     [rsp+0F0h+var_C8], rax; char *
0x180087fea  mov     rcx, r10; Buffer
0x180087fed  mov     qword ptr [rsp+0F0h+var_D0], r9; unsigned int
0x180087ff2  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x180087ff6  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180087ffb  mov     edi, eax
0x180087ffd  test    eax, eax
0x180087fff  js      loc_1800884C7
0x180088005  mov     rax, [r13+0]
0x180088009  xor     r13d, r13d
0x18008800c  mov     rcx, [rax+378h]; this
0x180088013  mov     [rbp+57h+var_98], rcx
0x180088017  test    rcx, rcx
0x18008801a  jz      short loc_180088045
0x18008801c  lea     r8, [rbp+57h+var_80]; void **
0x180088020  mov     [rbp+57h+var_80], 0
0x180088028  lea     rdx, [rbp+57h+var_98]; void **
0x18008802c  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x180088031  mov     rdx, [rbp+57h+var_80]
0x180088035  mov     eax, [rdx]
0x180088037  cmp     rax, r15
0x18008803a  jg      short loc_180088045
0x18008803c  mov     rcx, [rbp+57h+var_98]
0x180088040  mov     r13, rdx
0x180088043  jmp     short loc_180088017
0x180088045  mov     r11, [rbp+57h+Size]
0x180088049  mov     r15, [rbp+57h+var_90]
0x18008804d  test    r13, r13
0x180088050  jz      short loc_18008808F
0x180088052  mov     eax, [r13+0]
0x180088056  mov     rdx, r11; unsigned __int64
0x180088059  movsxd  r9, dword ptr [r13+10h]; unsigned __int64
0x18008805d  mov     rcx, r15; char *
0x180088060  mov     r8, [r13+8]; char *
0x180088064  mov     dword ptr [rbp+57h+var_98], eax
0x180088067  call    ?StringCbCopyNA@@YAJPEAD_KPEBD1@Z; StringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18008806c  mov     edi, eax
0x18008806e  test    eax, eax
0x180088070  js      loc_18008839F
0x180088076  mov     eax, dword ptr [rbp+57h+var_98]
0x180088079  mov     [rbp+57h+var_78], rax
0x18008807d  movsxd  rax, dword ptr [r13+10h]
0x180088081  add     r15, rax
0x180088084  sub     r11, rax
0x180088087  mov     [rbp+57h+var_90], r15
0x18008808b  mov     [rbp+57h+Size], r11
0x18008808f  lea     rax, aP; "</P>"
0x180088096  mov     rdx, r11; Size
0x180088099  mov     [rsp+0F0h+var_C0], rax
0x18008809e  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x1800880a2  lea     rax, aS_0; "%s"
0x1800880a9  mov     rcx, r15; Buffer
0x1800880ac  mov     [rsp+0F0h+var_C8], rax; char *
0x1800880b1  lea     r8, [rbp+57h+var_90]; char **
0x1800880b5  mov     qword ptr [rsp+0F0h+var_D0], 0; unsigned int
0x1800880be  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800880c3  mov     edi, eax
0x1800880c5  test    eax, eax
0x1800880c7  js      loc_180088435
0x1800880cd  mov     r10, [rbp+57h+var_90]
0x1800880d1  xor     r9d, r9d
0x1800880d4  mov     r11, [rbp+57h+Size]
0x1800880d8  mov     r15, [rbp+57h+var_60]
0x1800880dc  mov     r13, [rbp+57h+var_68]
0x1800880e0  mov     rax, [rbp+57h+var_70]
0x1800880e4  test    rax, rax
0x1800880e7  jz      short loc_1800880FA
0x1800880e9  mov     rcx, [rax]
0x1800880ec  test    rcx, rcx
0x1800880ef  jz      short loc_1800880FA
0x1800880f1  mov     rcx, [rcx+8]
0x1800880f5  test    rcx, rcx
0x1800880f8  jnz     short loc_180088101
0x1800880fa  lea     rcx, byte_180185A40
0x180088101  mov     rax, [r13+0]
0x180088105  lea     r8, byte_180185A40
0x18008810c  mov     [rsp+0F0h+var_B0], rcx
0x180088111  lea     rdx, byte_180185A40
0x180088118  mov     rcx, r10; Buffer
0x18008811b  cmp     [rax+8], r9
0x18008811f  cmovnz  r8, [rax+8]
0x180088124  mov     rax, [rsi+0A18h]
0x18008812b  mov     [rsp+0F0h+var_B8], r8
0x180088130  test    rax, rax
0x180088133  lea     r8, [rbp+57h+var_90]; char **
0x180088137  cmovnz  rdx, rax
0x18008813b  lea     rax, aPStyleSSS; "<P STYLE=\"%s %s %s\">"
0x180088142  mov     [rsp+0F0h+var_C0], rdx
0x180088147  mov     rdx, r11; Size
0x18008814a  mov     [rsp+0F0h+var_C8], rax; char *
0x18008814f  mov     qword ptr [rsp+0F0h+var_D0], r9; unsigned int
0x180088154  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x180088158  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18008815d  mov     edi, eax
0x18008815f  test    eax, eax
0x180088161  js      loc_180088B6B
0x180088167  mov     rax, [r13+0]
0x18008816b  xor     r11d, r11d
0x18008816e  mov     [rbp+57h+var_80], r11
0x180088172  mov     rcx, [rax+1B8h]; this
0x180088179  mov     [rbp+57h+var_98], rcx
0x18008817d  cmp     [rbp+57h+var_98], 0
0x180088182  jz      short loc_1800881A1
0x180088184  lea     r8, [rbp+57h+var_80]; void **
0x180088188  lea     rdx, [rbp+57h+var_98]; void **
0x18008818c  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x180088191  mov     r11, [rbp+57h+var_80]
0x180088195  mov     eax, [r11]
0x180088198  cmp     rax, r15
0x18008819b  jl      short loc_18008817D
0x18008819d  mov     [rbp+57h+var_78], rax
0x1800881a1  test    r11, r11
0x1800881a4  jz      loc_180088A9D
0x1800881aa  mov     r10, [rbp+57h+var_90]
0x1800881ae  mov     r13, [rbp+57h+Size]
0x1800881b2  mov     [rbp+57h+var_70], r10
0x1800881b6  movsxd  r9, dword ptr [r11+10h]; unsigned __int64
0x1800881ba  mov     rdx, r13; unsigned __int64
0x1800881bd  mov     r8, [r11+8]; char *
0x1800881c1  mov     rcx, r10; char *
0x1800881c4  call    ?StringCbCopyNA@@YAJPEAD_KPEBD1@Z; StringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800881c9  xor     r9d, r9d
0x1800881cc  mov     edi, eax
0x1800881ce  test    eax, eax
0x1800881d0  js      loc_180088968
0x1800881d6  movsxd  rax, dword ptr [r11+10h]
0x1800881da  mov     r10, [rbp+57h+var_70]
0x1800881de  sub     r13, rax
0x1800881e1  add     r10, rax
0x1800881e4  mov     [rbp+57h+var_70], r10
0x1800881e8  cmp     [rbp+57h+var_98], r9
0x1800881ec  jz      short loc_180088210
0x1800881ee  lea     r8, [rbp+57h+var_80]; void **
0x1800881f2  lea     rdx, [rbp+57h+var_98]; void **
0x1800881f6  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x1800881fb  mov     r11, [rbp+57h+var_80]
0x1800881ff  mov     rax, [rbp+57h+var_78]
0x180088203  mov     r15d, [r11]
0x180088206  cmp     r15, rax
0x180088209  jbe     short loc_1800881B6
0x18008820b  sub     r15, rax
0x18008820e  jmp     short loc_18008821A
0x180088210  mov     r15, 7FFFFFFFFFFFFFFFh
0x18008821a  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x18008821e  mov     dword ptr [rbp+57h+var_98], r9d
  ... truncated ...
```
