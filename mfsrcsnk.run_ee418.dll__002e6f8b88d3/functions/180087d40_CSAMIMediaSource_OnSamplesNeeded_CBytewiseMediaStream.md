# CSAMIMediaSource::OnSamplesNeeded(CBytewiseMediaStream *)

- ea: `0x180087d40`
- end: `0x180088fa9`
- name: `?OnSamplesNeeded@CSAMIMediaSource@@EEAAJPEAVCBytewiseMediaStream@@@Z`
- size: `4713`
- prototype: `__int64 __fastcall(CSAMIMediaSource *__hidden this, struct CBytewiseMediaStream *)`
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
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  char v15; // cl
  IMFMediaBuffer *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  HRESULT v19; // edi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v27; // r13
  DWORD v28; // eax
  wchar_t *v29; // rbx
  CallStackTracing *v30; // rax
  __int64 v31; // rcx
  char *v32; // r10
  size_t v33; // r11
  __int64 v34; // r15
  const char *v35; // r8
  const char *v36; // rdx
  const char *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  int *v40; // r13
  void *v41; // rcx
  size_t v42; // r11
  char *v43; // r15
  unsigned __int64 v44; // r9
  const char *v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r11
  __int64 v48; // rax
  __int64 v49; // rcx
  const char *v50; // rcx
  const char *v51; // r8
  const char *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  const char **v55; // r11
  void *v56; // rcx
  char *v57; // r10
  size_t v58; // r13
  int v59; // eax
  CVPtrList *v60; // rcx
  __int64 v61; // r11
  __int64 v62; // rax
  unsigned __int64 v63; // r15
  __int64 v64; // r15
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // r13
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // rcx
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  wchar_t *v77; // rbx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  wchar_t *v81; // rbx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  wchar_t *v84; // rbx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  wchar_t *v87; // rbx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 v90; // rdx
  wchar_t *v91; // rbx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  wchar_t *v94; // rbx
  CallStackTracing *v95; // rax
  struct CallStackContext *v96; // rax
  wchar_t *v97; // rbx
  CallStackTracing *v98; // rax
  struct CallStackContext *v99; // rax
  wchar_t *v100; // rbx
  CallStackTracing *v101; // rax
  struct CallStackContext *v102; // rax
  wchar_t *v103; // rbx
  CallStackTracing *v104; // rax
  struct CallStackContext *v105; // rax
  wchar_t *v106; // rbx
  CallStackTracing *v107; // rax
  struct CallStackContext *v108; // rax
  wchar_t *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  CallStackTracing *v112; // rax
  struct CallStackContext *v113; // rax
  __int64 v114; // rcx
  wchar_t *v115; // rbx
  CallStackTracing *v116; // rax
  struct CallStackContext *v117; // rax
  wchar_t *v118; // rbx
  CallStackTracing *v119; // rax
  struct CallStackContext *v120; // rax
  wchar_t *v121; // rbx
  CallStackTracing *v122; // rax
  struct CallStackContext *v123; // rax
  wchar_t *v124; // rbx
  CallStackTracing *v125; // rax
  struct CallStackContext *v126; // rax
  wchar_t *v127; // rbx
  CallStackTracing *v128; // rax
  struct CallStackContext *v129; // rax
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // r8
  __int64 v133; // r9
  wchar_t *v134; // rbx
  CallStackTracing *v135; // rax
  struct CallStackContext *v136; // rax
  wchar_t *v137; // rbx
  CallStackTracing *v138; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v141[8]; // [rsp+50h] [rbp-49h] BYREF
  void *v142; // [rsp+58h] [rbp-41h] BYREF
  char *v143; // [rsp+60h] [rbp-39h] BYREF
  size_t Size; // [rsp+68h] [rbp-31h] BYREF
  void *v145; // [rsp+70h] [rbp-29h] BYREF
  __int64 v146; // [rsp+78h] [rbp-21h]
  char *v147; // [rsp+80h] [rbp-19h]
  __int64 v148; // [rsp+88h] [rbp-11h]
  __int64 v149; // [rsp+90h] [rbp-9h]
  char *Buffer; // [rsp+98h] [rbp-1h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+A0h] [rbp+7h] BYREF
  unsigned __int64 v152; // [rsp+A8h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v141, "CSAMIMediaSource::OnSamplesNeeded", 802);
  ppBuffer = 0;
  if ( !a2 )
  {
    v137 = (wchar_t *)CallStackTracing::s_wpInstance;
    v19 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4, v6, v7);
      CallStackTracing::s_wpInstance = v138;
      if ( v138 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(v138, 2032) )
      {
        v137 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v137 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v137 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v137);
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
    v8 = this[189];
    v9 = *((_QWORD *)a2 + 29);
    v10 = *((unsigned int *)a2 + 60);
    if ( 10000 * v8 > v9 )
      *((_QWORD *)a2 + 29) = 10000 * v8;
    v11 = *(_QWORD *)this;
    v152 = 0;
    if ( (*(int (__fastcall **)(DWORD *, unsigned __int64 *))(v11 + 120))(this, &v152) >= 0 )
    {
      v14 = v152;
    }
    else
    {
      v14 = 0;
      v152 = 0;
    }
    v15 = byte_1801B110B;
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    {
      WPP_SF_qiI(*((_QWORD *)WPP_GLOBAL_Control + 17), v12, v13, this, v9, v14);
      v14 = v152;
      v15 = byte_1801B110B;
    }
    if ( v9 == 0x7FFFFFFFFFFFFFFFLL || v9 > v14 )
    {
      if ( (unsigned __int8)v15 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 100, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this);
      v19 = CMediaSourceBase::SetEndOfStream((CMediaSourceBase *)this, a2);
      if ( v19 >= 0 )
        break;
      v134 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v135 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v131, v130, v132, v133);
        CallStackTracing::s_wpInstance = v135;
        if ( v135 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v135 + 8LL))(v135, 2032) )
        {
          v134 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v134 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v134 + 8) )
      {
        v136 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v134);
        if ( *((_DWORD *)v136 + 499) != v19 )
          CallStackContext::TraceFailure(v136, "CSAMIMediaSource::OnSamplesNeeded", 863, v19);
      }
      if ( !g_wppLevels )
        break;
      v90 = 101;
LABEL_121:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v90, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this, v19);
      break;
    }
    v16 = ppBuffer;
    v146 = *((_QWORD *)a2 + 29);
    if ( ppBuffer )
    {
      ppBuffer = 0;
      ((void (__fastcall *)(IMFMediaBuffer *))v16->lpVtbl->Release)(v16);
    }
    v19 = MFCreateMemoryBuffer(this[649], &ppBuffer);
    if ( v19 < 0 )
    {
      v127 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v128 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17, v20, v21);
        CallStackTracing::s_wpInstance = v128;
        if ( v128 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v128 + 8LL))(v128, 2032) )
        {
          v127 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v127 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v127 + 8) )
      {
        v129 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v127);
        if ( *((_DWORD *)v129 + 499) != v19 )
          CallStackContext::TraceFailure(v129, "CSAMIMediaSource::OnSamplesNeeded", 878, v19);
      }
      if ( !g_wppLevels )
        break;
      v90 = 102;
      goto LABEL_121;
    }
    Buffer = 0;
    v19 = ((__int64 (__fastcall *)(IMFMediaBuffer *, char **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &Buffer,
            0,
            0);
    if ( v19 < 0 )
    {
      v124 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v125 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22, v24, v25);
        CallStackTracing::s_wpInstance = v125;
        if ( v125 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v125 + 8LL))(v125, 2032) )
        {
          v124 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v124 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v124 + 8) )
      {
        v126 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v124);
        if ( *((_DWORD *)v126 + 499) != v19 )
          CallStackContext::TraceFailure(v126, "CSAMIMediaSource::OnSamplesNeeded", 885, v19);
      }
      if ( !g_wppLevels )
        break;
      v90 = 103;
      goto LABEL_121;
    }
    v26 = 0;
    v27 = *((_QWORD *)this + 325) + 8 * v10;
    v148 = v27;
    if ( !v27 )
    {
      v121 = (wchar_t *)CallStackTracing::s_wpInstance;
      v19 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v122 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22, v24, 0);
        CallStackTracing::s_wpInstance = v122;
        if ( v122 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v122 + 8LL))(v122, 2032) )
        {
          v121 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v121 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v121 + 8) )
      {
        v123 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v121);
        if ( *((_DWORD *)v123 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v123, "CSAMIMediaSource::OnSamplesNeeded", 892, -2147467261);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v76 = 104;
LABEL_236:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v76,
        &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
        this,
        -2147467261);
LABEL_237:
      if ( ppBuffer )
        ((void (__fastcall *)(IMFMediaBuffer *, __int64, __int64, __int64))ppBuffer->lpVtbl->Unlock)(
          ppBuffer,
          v22,
          v24,
          v26);
      break;
    }
    v28 = this[653];
    if ( v28 == -1 )
    {
      v147 = 0;
    }
    else
    {
      v147 = (char *)(*((_QWORD *)this + 327) + 8LL * v28);
      if ( !v147 )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        v19 = -2147467261;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v24, 0);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)v75 + 499) != -2147467261 )
            CallStackContext::TraceFailure(v75, "CSAMIMediaSource::OnSamplesNeeded", 898, -2147467261);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v76 = 105;
        goto LABEL_236;
      }
    }
    v31 = *(_QWORD *)v27;
    v32 = Buffer;
    v33 = this[649];
    v143 = Buffer;
    v34 = v146 / 10000;
    Size = v33;
    v149 = v146 / 10000;
    v146 = 0x7FFFFFFFFFFFFFFFLL;
    if ( *(_DWORD *)(v31 + 904) )
    {
      v35 = (const char *)&word_180185A40;
      v36 = (const char *)&word_180185A40;
      if ( *((_QWORD *)this + 322) )
        v35 = (const char *)*((_QWORD *)this + 322);
      if ( *(_QWORD *)(v31 + 8) )
        v36 = *(const char **)(v31 + 8);
      v37 = (const char *)&word_180185A40;
      if ( *((_QWORD *)this + 323) )
        v37 = (const char *)*((_QWORD *)this + 323);
      v19 = StringCchPrintfExA(Buffer, (unsigned int)v33, &v143, &Size, 0, "<P STYLE=\"%s %s %s\">", v37, v36, v35);
      if ( v19 < 0 )
      {
        v84 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v22, v24, v26);
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
          if ( *((_DWORD *)v86 + 499) != v19 )
            CallStackContext::TraceFailure(v86, "CSAMIMediaSource::OnSamplesNeeded", 967, v19);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v80 = 112;
      }
      else
      {
        v39 = *(_QWORD *)v27;
        v40 = 0;
        v41 = *(void **)(v39 + 888);
        v142 = v41;
        while ( v41 )
        {
          v145 = 0;
          CVPtrList::GetNext((CVPtrList *)v41, &v142, &v145);
          if ( *(unsigned int *)v145 > v34 )
            break;
          v41 = v142;
          v40 = (int *)v145;
        }
        v42 = Size;
        v43 = v143;
        if ( v40 )
        {
          v44 = v40[4];
          v45 = (const char *)*((_QWORD *)v40 + 1);
          LODWORD(v142) = *v40;
          v19 = StringCbCopyNA(v143, Size, v45, v44);
          if ( v19 < 0 )
          {
            v77 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v46, v22, v24, v26);
              CallStackTracing::s_wpInstance = v78;
              if ( v78
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
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
              if ( *((_DWORD *)v79 + 499) != v19 )
                CallStackContext::TraceFailure(v79, "CSAMIMediaSource::OnSamplesNeeded", 1001, v19);
            }
            if ( !g_wppLevels )
              goto LABEL_237;
            v80 = 113;
            goto LABEL_90;
          }
          v146 = (unsigned int)v142;
          v48 = v40[4];
          v43 += v48;
          v42 = v47 - v48;
          v143 = v43;
          Size = v42;
        }
        v19 = StringCchPrintfExA(v43, v42, &v143, &Size, 0, "%s", "</P>");
        if ( v19 >= 0 )
        {
          v32 = v143;
          v33 = Size;
          v34 = v149;
          v27 = v148;
          goto LABEL_40;
        }
        v81 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v49, v22, v24, v26);
          CallStackTracing::s_wpInstance = v82;
          if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
          {
            v81 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v81 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v81 + 8) )
        {
          v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
          if ( *((_DWORD *)v83 + 499) != v19 )
            CallStackContext::TraceFailure(v83, "CSAMIMediaSource::OnSamplesNeeded", 1013, v19);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v80 = 114;
      }
LABEL_90:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v80, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this, v19);
      goto LABEL_237;
    }
LABEL_40:
    if ( !v147 || !*(_QWORD *)v147 || (v50 = *(const char **)(*(_QWORD *)v147 + 8LL)) == 0 )
      v50 = (const char *)&word_180185A40;
    v51 = (const char *)&word_180185A40;
    v52 = (const char *)&word_180185A40;
    if ( *(_QWORD *)(*(_QWORD *)v27 + 8LL) )
      v51 = *(const char **)(*(_QWORD *)v27 + 8LL);
    if ( *((_QWORD *)this + 323) )
      v52 = (const char *)*((_QWORD *)this + 323);
    v19 = StringCchPrintfExA(v32, v33, &v143, &Size, 0, "<P STYLE=\"%s %s %s\">", v52, v51, v50);
    if ( v19 < 0 )
    {
      v118 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v119 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v53, v22, v24, v26);
        CallStackTracing::s_wpInstance = v119;
        if ( v119 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v119 + 8LL))(v119, 2032) )
        {
          v118 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v118 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v118 + 8) )
      {
        v120 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v118);
        if ( *((_DWORD *)v120 + 499) != v19 )
          CallStackContext::TraceFailure(v120, "CSAMIMediaSource::OnSamplesNeeded", 1033, v19);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v80 = 116;
      goto LABEL_90;
    }
    v54 = *(_QWORD *)v27;
    v55 = 0;
    v145 = 0;
    v56 = *(void **)(v54 + 440);
    v142 = v56;
    while ( v142 )
    {
      CVPtrList::GetNext((CVPtrList *)v56, &v142, &v145);
      v55 = (const char **)v145;
      if ( *(unsigned int *)v145 >= v34 )
      {
        v146 = *(unsigned int *)v145;
        break;
      }
    }
    if ( !v55 )
    {
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 117, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this);
      v19 = CMediaSourceBase::SetEndOfStream((CMediaSourceBase *)this, a2);
      if ( v19 >= 0 )
        goto LABEL_237;
      v115 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v114, v22, v24, v26);
        CallStackTracing::s_wpInstance = v116;
        if ( v116 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(v116, 2032) )
        {
          v115 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v115 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v115 + 8) )
      {
        v117 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v115);
        if ( *((_DWORD *)v117 + 499) != v19 )
          CallStackContext::TraceFailure(v117, "CSAMIMediaSource::OnSamplesNeeded", 1070, v19);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v80 = 118;
      goto LABEL_90;
    }
    v57 = v143;
    v58 = Size;
    v147 = v143;
    while ( 1 )
    {
      v59 = StringCbCopyNA(v57, v58, v55[1], *((int *)v55 + 4));
      v26 = 0;
      v19 = v59;
      if ( v59 < 0 )
      {
        v109 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v24, 0);
          CallStackTracing::s_wpInstance = v110;
          if ( v110 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v110 + 8LL))(v110, 2032) )
          {
            v109 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v109 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v109 + 8) )
        {
          v111 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v109);
          if ( *((_DWORD *)v111 + 499) != v19 )
            CallStackContext::TraceFailure(v111, "CSAMIMediaSource::OnSamplesNeeded", 1083, v19);
          v109 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        if ( g_wppLevels )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
            this,
            v19);
          v109 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        if ( !v109 )
        {
          v112 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v24, v26);
          CallStackTracing::s_wpInstance = v112;
          if ( v112 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v112 + 8LL))(v112, 2032) )
          {
            v109 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v109 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v109 + 8) )
        {
          v113 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v109);
          if ( *((_DWORD *)v113 + 499) != v19 )
            CallStackContext::TraceFailure(v113, "CSAMIMediaSource::OnSamplesNeeded", 1111, v19);
        }
        if ( g_wppLevels )
        {
          v80 = 120;
          goto LABEL_90;
        }
        goto LABEL_237;
      }
      v62 = *(int *)(v61 + 16);
      v58 -= v62;
      v147 += v62;
      if ( !v142 )
        break;
      CVPtrList::GetNext(v60, &v142, &v145);
      v55 = (const char **)v145;
      v63 = *(unsigned int *)v145;
      if ( v63 > v146 )
      {
        v64 = v63 - v146;
        goto LABEL_60;
      }
    }
    v64 = 0x7FFFFFFFFFFFFFFFLL;
LABEL_60:
    LODWORD(v142) = v26;
    LODWORD(v143) = v26;
    v19 = ULongLongToULong(v58, (unsigned int *)&v143);
    if ( v19 < 0 )
    {
      v106 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v107 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v65, v22, v24, v26);
        CallStackTracing::s_wpInstance = v107;
        if ( v107 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v107 + 8LL))(v107, 2032) )
        {
          v106 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v106 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v106 + 8) )
      {
        v108 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v106);
        if ( *((_DWORD *)v108 + 499) != v19 )
          CallStackContext::TraceFailure(v108, "CSAMIMediaSource::OnSamplesNeeded", 1120, v19);
      }
      if ( g_wppLevels )
      {
        v80 = 121;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v19 = ULongSub(this[649], (unsigned int)v143, (unsigned int *)&v142);
    if ( v19 < 0 )
    {
      v103 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v22, v24, v26);
        CallStackTracing::s_wpInstance = v104;
        if ( v104 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(v104, 2032) )
        {
          v103 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v103 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v103 + 8) )
      {
        v105 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v103);
        if ( *((_DWORD *)v105 + 499) != v19 )
          CallStackContext::TraceFailure(v105, "CSAMIMediaSource::OnSamplesNeeded", 1122, v19);
      }
      if ( g_wppLevels )
      {
        v80 = 122;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v22 = (unsigned int)((_DWORD)v142 + 1);
    if ( (unsigned int)v22 < (unsigned int)v142 )
    {
      v100 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v22, v24, v26);
        CallStackTracing::s_wpInstance = v101;
        if ( v101 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v101 + 8LL))(v101, 2032) )
        {
          v100 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v100 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      v19 = -2147024362;
      if ( *((_BYTE *)v100 + 8) )
      {
        v102 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v100);
        if ( *((_DWORD *)v102 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v102, "CSAMIMediaSource::OnSamplesNeeded", 1124, -2147024362);
      }
      if ( g_wppLevels )
      {
        v80 = 123;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    if ( (unsigned int)v22 <= 1 )
    {
      v97 = (wchar_t *)CallStackTracing::s_wpInstance;
      v19 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v98 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v22, v24, v26);
        CallStackTracing::s_wpInstance = v98;
        if ( v98 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v98 + 8LL))(v98, 2032) )
        {
          v97 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v97 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v97 + 8) )
      {
        v99 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v97);
        if ( *((_DWORD *)v99 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v99, "CSAMIMediaSource::OnSamplesNeeded", 1134, -1072875845);
      }
      if ( g_wppLevels )
      {
        v80 = 124;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    Buffer[(unsigned int)v142] = 0;
    v19 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
    if ( v19 < 0 )
    {
      v94 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v95 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v67, v22, v24, v26);
        CallStackTracing::s_wpInstance = v95;
        if ( v95 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v95 + 8LL))(v95, 2032) )
        {
          v94 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v94 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v94 + 8) )
      {
        v96 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v94);
        if ( *((_DWORD *)v96 + 499) != v19 )
          CallStackContext::TraceFailure(v96, "CSAMIMediaSource::OnSamplesNeeded", 1141, v19);
      }
      if ( g_wppLevels )
      {
        v80 = 125;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v19 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    if ( v19 < 0 )
    {
      v91 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v68, v22, v24, v26);
        CallStackTracing::s_wpInstance = v92;
        if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
        {
          v91 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v91 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v91 + 8) )
      {
        v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
        if ( *((_DWORD *)v93 + 499) != v19 )
          CallStackContext::TraceFailure(v93, "CSAMIMediaSource::OnSamplesNeeded", 1147, v19);
      }
      if ( g_wppLevels )
      {
        v80 = 126;
        goto LABEL_90;
      }
      goto LABEL_237;
    }
    v69 = 10000 * v146;
    v148 = 10000 * v64;
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      WPP_SF_qii(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        127,
        &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
        this,
        10000 * v146,
        10000 * v64);
    v19 = CMediaSourceBase::CreateAndAddSampleToQueue((CMediaSourceBase *)this, a2, ppBuffer, v69, 10000 * v64);
    if ( v19 < 0 )
    {
      v87 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v71, v70, v72, v73);
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
        if ( *((_DWORD *)v89 + 499) != v19 )
          CallStackContext::TraceFailure(v89, "CSAMIMediaSource::OnSamplesNeeded", 1158, v19);
      }
      if ( g_wppLevels )
      {
        v90 = 128;
        goto LABEL_121;
      }
    }
    else
    {
      if ( v64 == 0x7FFFFFFFFFFFFFFFLL )
        v74 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v74 = v69 + v148;
      *((_QWORD *)a2 + 29) = v74;
      if ( !CMediaSourceBase::IsSampleNeeded((CMediaSourceBase *)this, a2) )
        continue;
    }
    break;
  }
LABEL_282:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v141);
  return (unsigned int)v19;
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
0x180087f9a  lea     rdi, word_180185A40
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
0x1800880fa  lea     rcx, word_180185A40
0x180088101  mov     rax, [r13+0]
0x180088105  lea     r8, word_180185A40
0x18008810c  mov     [rsp+0F0h+var_B0], rcx
0x180088111  lea     rdx, word_180185A40
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
