# CSAMIMediaSource::OnSamplesNeeded(CBytewiseMediaStream *)

- ea: `0x18008caa0`
- end: `0x18008dd88`
- name: `?OnSamplesNeeded@CSAMIMediaSource@@EEAAJPEAVCBytewiseMediaStream@@@Z`
- size: `4840`
- prototype: `__int64 __fastcall(CSAMIMediaSource *__hidden this, struct CBytewiseMediaStream *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180022758`
- `0x180024890`
- `0x180036c30`
- `0x180042134`
- `0x1800496c4`
- `0x180079680`
- `0x180079f34`
- `0x18008caa0`
- `0x180098e54`
- `0x180110ed0`
- `0x180121750`
- `0x1801394d4`
- `0x180139588`
- `0x18015c4cc`
- `0x18015c590`
- `0x18015c778`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008cc62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d117`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d1b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d2e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d41a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d4b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d54f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d5ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d684`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d7cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d931`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d9d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008da9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008db33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008dc03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008dca4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008cc62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d117`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d1b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d2e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d41a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d4b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d54f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d5ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d684`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d7cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d931`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008d9d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008da9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008db33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008dc03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008dca4`
- `MFPlat!MFCreateMemoryBuffer` at `0x18008cbcf`
- `MFPlat!MFCreateMemoryBuffer` at `0x18008cbcf`

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
  int v17; // edi
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
        v128 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    v13 = byte_1801BA10B;
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
    {
      WPP_SF_qiI(*((_QWORD *)WPP_GLOBAL_Control + 17), v10, v11, this, v7, v12);
      v12 = v143;
      v13 = byte_1801BA10B;
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
          v125 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v120 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v117 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v114 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v24 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v30 = (const char *)&byte_18018FB78;
      v31 = (const char *)&byte_18018FB78;
      if ( *((_QWORD *)this + 322) )
        v30 = (const char *)*((_QWORD *)this + 322);
      if ( *(_QWORD *)(v26 + 8) )
        v31 = *(const char **)(v26 + 8);
      v32 = (const char *)&byte_18018FB78;
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
            v77 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v70 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v74 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v45 = (const char *)&byte_18018FB78;
    v46 = (const char *)&byte_18018FB78;
    v47 = (const char *)&byte_18018FB78;
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
          v111 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
          v108 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v102 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v102 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v99 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v96 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v93 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v90 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v87 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v84 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
          v80 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18008caa0  mov     [rsp-8+arg_10], rbx
0x18008caa5  push    rbp
0x18008caa6  push    rsi
0x18008caa7  push    rdi
0x18008caa8  push    r12
0x18008caaa  push    r13
0x18008caac  push    r14
0x18008caae  push    r15
0x18008cab0  lea     rbp, [rsp-27h]
0x18008cab5  sub     rsp, 0C0h
0x18008cabc  mov     rax, cs:__security_cookie
0x18008cac3  xor     rax, rsp
0x18008cac6  mov     [rbp+57h+var_40], rax
0x18008caca  mov     rbx, rdx
0x18008cacd  mov     rsi, rcx
0x18008cad0  lea     rdx, aCsamimediasour_7; "CSAMIMediaSource::OnSamplesNeeded"
0x18008cad7  mov     r8d, 322h; int
0x18008cadd  lea     rcx, [rbp+57h+var_A0]; this
0x18008cae1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008cae6  xor     r13d, r13d
0x18008cae9  mov     [rbp+57h+ppBuffer], r13
0x18008caed  test    rbx, rbx
0x18008caf0  jz      loc_18008DC8F
0x18008caf6  lea     r14d, [r13+1]
0x18008cafa  lea     r12, WPP_0776a4c2c75433e71492a25261740b6d_Traceguids
0x18008cb01  mov     eax, [rsi+2F4h]
0x18008cb07  mov     rdi, [rbx+0E8h]
0x18008cb0e  mov     r15d, [rbx+0F0h]
0x18008cb15  imul    rcx, rax, 2710h
0x18008cb1c  cmp     rcx, rdi
0x18008cb1f  jle     short loc_18008CB28
0x18008cb21  mov     [rbx+0E8h], rcx
0x18008cb28  mov     rax, [rsi]
0x18008cb2b  lea     rdx, [rbp+57h+var_48]
0x18008cb2f  mov     rcx, rsi
0x18008cb32  mov     [rbp+57h+var_48], r13
0x18008cb36  mov     rax, [rax+78h]
0x18008cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb3f  test    eax, eax
0x18008cb41  jns     short loc_18008CB4C
0x18008cb43  mov     rax, r13
0x18008cb46  mov     [rbp+57h+var_48], rax
0x18008cb4a  jmp     short loc_18008CB50
0x18008cb4c  mov     rax, [rbp+57h+var_48]
0x18008cb50  mov     cl, cs:byte_1801BA10B
0x18008cb56  cmp     cl, 10h
0x18008cb59  jb      short loc_18008CB85
0x18008cb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cb62  mov     r9, rsi
0x18008cb65  mov     [rsp+0F0h+var_C8], rax
0x18008cb6a  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x18008cb6f  mov     rcx, [rcx+88h]
0x18008cb76  call    WPP_SF_qiI
0x18008cb7b  mov     rax, [rbp+57h+var_48]
0x18008cb7f  mov     cl, cs:byte_1801BA10B
0x18008cb85  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18008cb8f  cmp     rdi, rdx
0x18008cb92  jz      loc_18008DBBF
0x18008cb98  cmp     rdi, rax
0x18008cb9b  ja      loc_18008DBBF
0x18008cba1  mov     rcx, [rbp+57h+ppBuffer]
0x18008cba5  mov     rax, [rbx+0E8h]
0x18008cbac  mov     [rbp+57h+var_78], rax
0x18008cbb0  test    rcx, rcx
0x18008cbb3  jz      short loc_18008CBC5
0x18008cbb5  mov     [rbp+57h+ppBuffer], r13
0x18008cbb9  mov     rax, [rcx]
0x18008cbbc  mov     rax, [rax+10h]
0x18008cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cbc5  mov     ecx, [rsi+0A24h]; cbMaxLength
0x18008cbcb  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x18008cbcf  call    cs:__imp_MFCreateMemoryBuffer
0x18008cbd6  nop     dword ptr [rax+rax+00h]
0x18008cbdb  mov     edi, eax
0x18008cbdd  test    eax, eax
0x18008cbdf  js      loc_18008DB27
0x18008cbe5  mov     rcx, [rbp+57h+ppBuffer]
0x18008cbe9  lea     rdx, [rbp+57h+Buffer]
0x18008cbed  mov     [rbp+57h+Buffer], r13
0x18008cbf1  xor     r9d, r9d
0x18008cbf4  xor     r8d, r8d
0x18008cbf7  mov     rax, [rcx]
0x18008cbfa  mov     rax, [rax+18h]
0x18008cbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc03  mov     edi, eax
0x18008cc05  test    eax, eax
0x18008cc07  js      loc_18008DA8F
0x18008cc0d  mov     rax, [rsi+0A28h]
0x18008cc14  xor     r9d, r9d
0x18008cc17  lea     r13, [rax+r15*8]
0x18008cc1b  mov     [rbp+57h+var_68], r13
0x18008cc1f  test    r13, r13
0x18008cc22  jz      loc_18008D9BD
0x18008cc28  mov     eax, [rsi+0A34h]
0x18008cc2e  cmp     eax, 0FFFFFFFFh
0x18008cc31  jz      short loc_18008CCA6
0x18008cc33  mov     ecx, eax
0x18008cc35  mov     rax, [rsi+0A38h]
0x18008cc3c  lea     rcx, [rax+rcx*8]
0x18008cc40  mov     [rbp+57h+var_70], rcx
0x18008cc44  test    rcx, rcx
0x18008cc47  jnz     short loc_18008CCAA
0x18008cc49  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008cc50  mov     r15d, 80004003h
0x18008cc56  mov     edi, r15d
0x18008cc59  test    rbx, rbx
0x18008cc5c  jnz     loc_18008D0C5
0x18008cc62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008cc69  nop     dword ptr [rax+rax+00h]
0x18008cc6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008cc75  mov     rcx, rax
0x18008cc78  test    rax, rax
0x18008cc7b  jz      loc_18008D0B7
0x18008cc81  mov     rax, [rax]
0x18008cc84  mov     edx, 7F0h
0x18008cc89  mov     rax, [rax+8]
0x18008cc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc92  test    eax, eax
0x18008cc94  jz      loc_18008D0B7
0x18008cc9a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008cca1  jmp     loc_18008D0C5
0x18008cca6  mov     [rbp+57h+var_70], r9
0x18008ccaa  mov     rcx, [r13+0]
0x18008ccae  mov     rax, 346DC5D63886594Bh
0x18008ccb8  imul    [rbp+57h+var_78]
0x18008ccbc  mov     r10, [rbp+57h+Buffer]
0x18008ccc0  mov     r11d, [rsi+0A24h]
0x18008ccc7  mov     r15, rdx
0x18008ccca  sar     r15, 0Bh
0x18008ccce  mov     rax, r15
0x18008ccd1  mov     [rbp+57h+var_90], r10
0x18008ccd5  shr     rax, 3Fh
0x18008ccd9  add     r15, rax
0x18008ccdc  mov     [rbp+57h+Size], r11
0x18008cce0  mov     rax, 7FFFFFFFFFFFFFFFh
0x18008ccea  mov     [rbp+57h+var_60], r15
0x18008ccee  mov     [rbp+57h+var_78], rax
0x18008ccf2  cmp     [rcx+388h], r9d
0x18008ccf9  jbe     loc_18008CE4C
0x18008ccff  mov     rax, [rsi+0A10h]
0x18008cd06  lea     rdi, byte_18018FB78
0x18008cd0d  test    rax, rax
0x18008cd10  mov     r8, rdi
0x18008cd13  mov     rdx, rdi
0x18008cd16  cmovnz  r8, rax
0x18008cd1a  cmp     [rcx+8], r9
0x18008cd1e  mov     rax, [rsi+0A18h]
0x18008cd25  cmovnz  rdx, [rcx+8]
0x18008cd2a  mov     rcx, rdi
0x18008cd2d  mov     [rsp+0F0h+var_B0], r8
0x18008cd32  test    rax, rax
0x18008cd35  mov     [rsp+0F0h+var_B8], rdx
0x18008cd3a  lea     r8, [rbp+57h+var_90]; char **
0x18008cd3e  cmovnz  rcx, rax
0x18008cd42  mov     edx, r11d; Size
0x18008cd45  mov     [rsp+0F0h+var_C0], rcx
0x18008cd4a  lea     rax, aPStyleSSS; "<P STYLE=\"%s %s %s\">"
0x18008cd51  mov     [rsp+0F0h+var_C8], rax; char *
0x18008cd56  mov     rcx, r10; Buffer
0x18008cd59  mov     qword ptr [rsp+0F0h+var_D0], r9; unsigned int
0x18008cd5e  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x18008cd62  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18008cd67  mov     edi, eax
0x18008cd69  test    eax, eax
0x18008cd6b  js      loc_18008D23F
0x18008cd71  mov     rax, [r13+0]
0x18008cd75  xor     r13d, r13d
0x18008cd78  mov     rcx, [rax+378h]; this
0x18008cd7f  mov     [rbp+57h+var_98], rcx
0x18008cd83  test    rcx, rcx
0x18008cd86  jz      short loc_18008CDB1
0x18008cd88  lea     r8, [rbp+57h+var_80]; void **
0x18008cd8c  mov     [rbp+57h+var_80], 0
0x18008cd94  lea     rdx, [rbp+57h+var_98]; void **
0x18008cd98  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x18008cd9d  mov     rdx, [rbp+57h+var_80]
0x18008cda1  mov     eax, [rdx]
0x18008cda3  cmp     rax, r15
0x18008cda6  jg      short loc_18008CDB1
0x18008cda8  mov     rcx, [rbp+57h+var_98]
0x18008cdac  mov     r13, rdx
0x18008cdaf  jmp     short loc_18008CD83
0x18008cdb1  mov     r11, [rbp+57h+Size]
0x18008cdb5  mov     r15, [rbp+57h+var_90]
0x18008cdb9  test    r13, r13
0x18008cdbc  jz      short loc_18008CDFB
0x18008cdbe  mov     eax, [r13+0]
0x18008cdc2  mov     rdx, r11; unsigned __int64
0x18008cdc5  movsxd  r9, dword ptr [r13+10h]; unsigned __int64
0x18008cdc9  mov     rcx, r15; char *
0x18008cdcc  mov     r8, [r13+8]; char *
0x18008cdd0  mov     dword ptr [rbp+57h+var_98], eax
0x18008cdd3  call    ?StringCbCopyNA@@YAJPEAD_KPEBD1@Z; StringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18008cdd8  mov     edi, eax
0x18008cdda  test    eax, eax
0x18008cddc  js      loc_18008D10B
0x18008cde2  mov     eax, dword ptr [rbp+57h+var_98]
0x18008cde5  mov     [rbp+57h+var_78], rax
0x18008cde9  movsxd  rax, dword ptr [r13+10h]
0x18008cded  add     r15, rax
0x18008cdf0  sub     r11, rax
0x18008cdf3  mov     [rbp+57h+var_90], r15
0x18008cdf7  mov     [rbp+57h+Size], r11
0x18008cdfb  lea     rax, aP; "</P>"
0x18008ce02  mov     rdx, r11; Size
0x18008ce05  mov     [rsp+0F0h+var_C0], rax
0x18008ce0a  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x18008ce0e  lea     rax, aS_0; "%s"
0x18008ce15  mov     rcx, r15; Buffer
0x18008ce18  mov     [rsp+0F0h+var_C8], rax; char *
0x18008ce1d  lea     r8, [rbp+57h+var_90]; char **
0x18008ce21  mov     qword ptr [rsp+0F0h+var_D0], 0; unsigned int
0x18008ce2a  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18008ce2f  mov     edi, eax
0x18008ce31  test    eax, eax
0x18008ce33  js      loc_18008D1A7
0x18008ce39  mov     r10, [rbp+57h+var_90]
0x18008ce3d  xor     r9d, r9d
0x18008ce40  mov     r11, [rbp+57h+Size]
0x18008ce44  mov     r15, [rbp+57h+var_60]
0x18008ce48  mov     r13, [rbp+57h+var_68]
0x18008ce4c  mov     rax, [rbp+57h+var_70]
0x18008ce50  test    rax, rax
0x18008ce53  jz      short loc_18008CE66
0x18008ce55  mov     rcx, [rax]
0x18008ce58  test    rcx, rcx
0x18008ce5b  jz      short loc_18008CE66
0x18008ce5d  mov     rcx, [rcx+8]
0x18008ce61  test    rcx, rcx
0x18008ce64  jnz     short loc_18008CE6D
0x18008ce66  lea     rcx, byte_18018FB78
0x18008ce6d  mov     rax, [r13+0]
0x18008ce71  lea     r8, byte_18018FB78
0x18008ce78  mov     [rsp+0F0h+var_B0], rcx
0x18008ce7d  lea     rdx, byte_18018FB78
0x18008ce84  mov     rcx, r10; Buffer
0x18008ce87  cmp     [rax+8], r9
0x18008ce8b  cmovnz  r8, [rax+8]
0x18008ce90  mov     rax, [rsi+0A18h]
0x18008ce97  mov     [rsp+0F0h+var_B8], r8
0x18008ce9c  test    rax, rax
0x18008ce9f  lea     r8, [rbp+57h+var_90]; char **
0x18008cea3  cmovnz  rdx, rax
0x18008cea7  lea     rax, aPStyleSSS; "<P STYLE=\"%s %s %s\">"
0x18008ceae  mov     [rsp+0F0h+var_C0], rdx
0x18008ceb3  mov     rdx, r11; Size
0x18008ceb6  mov     [rsp+0F0h+var_C8], rax; char *
0x18008cebb  mov     qword ptr [rsp+0F0h+var_D0], r9; unsigned int
0x18008cec0  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x18008cec4  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x18008cec9  mov     edi, eax
0x18008cecb  test    eax, eax
0x18008cecd  js      loc_18008D925
0x18008ced3  mov     rax, [r13+0]
0x18008ced7  xor     r11d, r11d
0x18008ceda  mov     [rbp+57h+var_80], r11
0x18008cede  mov     rcx, [rax+1B8h]; this
0x18008cee5  mov     [rbp+57h+var_98], rcx
0x18008cee9  cmp     [rbp+57h+var_98], 0
0x18008ceee  jz      short loc_18008CF0D
0x18008cef0  lea     r8, [rbp+57h+var_80]; void **
0x18008cef4  lea     rdx, [rbp+57h+var_98]; void **
0x18008cef8  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x18008cefd  mov     r11, [rbp+57h+var_80]
0x18008cf01  mov     eax, [r11]
0x18008cf04  cmp     rax, r15
0x18008cf07  jl      short loc_18008CEE9
0x18008cf09  mov     [rbp+57h+var_78], rax
0x18008cf0d  test    r11, r11
0x18008cf10  jz      loc_18008D851
0x18008cf16  mov     r10, [rbp+57h+var_90]
0x18008cf1a  mov     r13, [rbp+57h+Size]
0x18008cf1e  mov     [rbp+57h+var_70], r10
0x18008cf22  movsxd  r9, dword ptr [r11+10h]; unsigned __int64
0x18008cf26  mov     rdx, r13; unsigned __int64
0x18008cf29  mov     r8, [r11+8]; char *
0x18008cf2d  mov     rcx, r10; char *
0x18008cf30  call    ?StringCbCopyNA@@YAJPEAD_KPEBD1@Z; StringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18008cf35  xor     r9d, r9d
0x18008cf38  mov     edi, eax
0x18008cf3a  test    eax, eax
0x18008cf3c  js      loc_18008D710
0x18008cf42  movsxd  rax, dword ptr [r11+10h]
0x18008cf46  mov     r10, [rbp+57h+var_70]
0x18008cf4a  sub     r13, rax
0x18008cf4d  add     r10, rax
0x18008cf50  mov     [rbp+57h+var_70], r10
0x18008cf54  cmp     [rbp+57h+var_98], r9
0x18008cf58  jz      short loc_18008CF7C
0x18008cf5a  lea     r8, [rbp+57h+var_80]; void **
0x18008cf5e  lea     rdx, [rbp+57h+var_98]; void **
0x18008cf62  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x18008cf67  mov     r11, [rbp+57h+var_80]
0x18008cf6b  mov     rax, [rbp+57h+var_78]
0x18008cf6f  mov     r15d, [r11]
0x18008cf72  cmp     r15, rax
0x18008cf75  jbe     short loc_18008CF22
0x18008cf77  sub     r15, rax
0x18008cf7a  jmp     short loc_18008CF86
0x18008cf7c  mov     r15, 7FFFFFFFFFFFFFFFh
  ... truncated ...
```
