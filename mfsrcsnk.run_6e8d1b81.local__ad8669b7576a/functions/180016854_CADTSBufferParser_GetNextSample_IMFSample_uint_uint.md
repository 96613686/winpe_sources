# CADTSBufferParser::GetNextSample(IMFSample * *,uint *,uint *)

- ea: `0x180016854`
- end: `0x180017592`
- name: `?GetNextSample@CADTSBufferParser@@QEAAJPEAPEAUIMFSample@@PEAI1@Z`
- size: `3390`
- prototype: `__int64 __fastcall(CADTSBufferParser *__hidden this, struct IMFSample **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800bbaf0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x1800152d0`
- `0x180015dec`
- `0x180016504`
- `0x180016578`
- `0x180016854`
- `0x180018b90`
- `0x180073b14`
- `0x18007450c`
- `0x18010959c`
- `0x1801099f0`
- `0x18010a3fc`
- `0x18011b1e4`
- `0x180133510`
- `0x180133ba8`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016906`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800169cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016a7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016b2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016bed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016dde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016f12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016fa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800170e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017183`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001722d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800172de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017446`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016906`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800169cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016a7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016b2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016bed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016dde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016f12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016fa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800170e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017183`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001722d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800172de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017446`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800169b0`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800169b0`
- `MFPlat!MFCreateSample` at `0x180017167`
- `MFPlat!MFCreateSample` at `0x180017167`

## pseudocode

```c
__int64 __fastcall CADTSBufferParser::GetNextSample(
        CADTSBufferParser *this,
        struct IMFSample **a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int *v5; // r13
  __int64 v6; // rdx
  __int64 v7; // rcx
  HRESULT NextValidADTSHeader; // ebx
  wchar_t *v9; // rdi
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  wchar_t *v15; // rdi
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  wchar_t *v20; // rdi
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  wchar_t *v25; // rdi
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  wchar_t *v30; // rdi
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int v33; // r12d
  unsigned int v34; // r13d
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned __int8 *v37; // r12
  unsigned int v38; // edx
  unsigned int v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // r13d
  __int64 v49; // rdx
  unsigned int v50; // edx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rdx
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  int v69; // r8d
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  wchar_t *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  wchar_t *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  IMFSample *v84; // rcx
  bool v86; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v87[3]; // [rsp+41h] [rbp-68h] BYREF
  unsigned int v88; // [rsp+44h] [rbp-65h] BYREF
  unsigned int v89; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v90; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned int v91; // [rsp+50h] [rbp-59h]
  unsigned int v92; // [rsp+54h] [rbp-55h]
  int v93; // [rsp+58h] [rbp-51h]
  int v94; // [rsp+60h] [rbp-49h] BYREF
  int v95; // [rsp+64h] [rbp-45h]
  unsigned int *v96; // [rsp+68h] [rbp-41h]
  struct IMFSample **v97; // [rsp+70h] [rbp-39h]
  IMFSample *ppIMFSample; // [rsp+78h] [rbp-31h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 *v100; // [rsp+88h] [rbp-21h] BYREF
  __int64 v101; // [rsp+90h] [rbp-19h] BYREF
  unsigned int v102; // [rsp+98h] [rbp-11h] BYREF
  void *Block; // [rsp+A0h] [rbp-9h]
  unsigned int v104; // [rsp+A8h] [rbp-1h]
  __int64 v105; // [rsp+ACh] [rbp+3h]

  v97 = a2;
  *a2 = 0;
  *a3 = 0;
  v96 = a4;
  v100 = 0;
  v101 = 0;
  v5 = a4;
  ppBuffer = 0;
  ppIMFSample = 0;
  Block = 0;
  v105 = 0;
  v104 = 0;
  *a4 = 0;
  v86 = 0;
  v89 = 0;
  v88 = 7;
  v102 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v87, "CADTSBufferParser::GetNextSample", 411);
  NextValidADTSHeader = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)this + 40LL))(
                          *(_QWORD *)this,
                          &v102);
  if ( NextValidADTSHeader < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v7, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CADTSBufferParser::GetNextSample",
          411,
          NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v12 = 42;
    goto LABEL_12;
  }
  NextValidADTSHeader = MFCreateMemoryBuffer(v102 - *((_DWORD *)this + 2), &ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v17, "CADTSBufferParser::GetNextSample", 417, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v12 = 43;
    goto LABEL_12;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                          ppBuffer,
                          &v101,
                          0,
                          0);
  if ( NextValidADTSHeader < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v22, "CADTSBufferParser::GetNextSample", 418, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v12 = 44;
    goto LABEL_12;
  }
  NextValidADTSHeader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, _QWORD, _QWORD))(**(_QWORD **)this + 24LL))(
                          *(_QWORD *)this,
                          &v100,
                          0,
                          0);
  if ( NextValidADTSHeader < 0 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v27, "CADTSBufferParser::GetNextSample", 419, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v12 = 45;
    goto LABEL_12;
  }
  NextValidADTSHeader = CADTSBufferParser::FindNextValidADTSHeader(this, v100, v102, &v86, &v89, &v88);
  if ( NextValidADTSHeader < 0 )
  {
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v29, v28);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v32, "CADTSBufferParser::GetNextSample", 421, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v12 = 46;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
      this,
      NextValidADTSHeader);
    goto LABEL_199;
  }
  v33 = v89;
  v91 = 0;
  v89 = v88;
  while ( 1 )
  {
    if ( !v86 )
      goto LABEL_129;
    v34 = v102;
    v93 = *((_DWORD *)this + 2);
    v92 = v33 + v93;
    if ( v33 + v93 > v102 )
      break;
    if ( *((_BYTE *)this + 16) )
    {
      NextValidADTSHeader = anonymous_namespace_::UpdateSubSampleMappingForFrame(v33);
      if ( NextValidADTSHeader < 0 )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)v53 + 499) != NextValidADTSHeader )
            CallStackContext::TraceFailure(v53, "CADTSBufferParser::GetNextSample", 441, NextValidADTSHeader);
        }
        if ( g_wppLevels )
        {
          v12 = 47;
          goto LABEL_12;
        }
        goto LABEL_199;
      }
      v34 = v102;
    }
    v36 = v33;
    v88 = 0;
    *((_DWORD *)this + 2) += v33;
    v37 = v100;
    v90 = v36;
    v86 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v87,
      "CADTSBufferParser::FindNextValidADTSHeader",
      341);
    v38 = *((_DWORD *)this + 2);
    if ( v38 < v34 - 1 )
    {
      v39 = *((_DWORD *)this + 2);
      do
      {
        if ( v37[v39] == 0xFF )
        {
          if ( (v37[v39 + 1] & 0xF6) == 0xF0 )
            break;
          ++v38;
        }
        *((_DWORD *)this + 2) = ++v38;
        v39 = v38;
      }
      while ( v38 < v34 - 1 );
    }
    NextValidADTSHeader = 0;
    while ( 1 )
    {
      v40 = *((unsigned int *)this + 2);
      if ( (int)v40 + 7 > v34 )
        goto LABEL_87;
      CADTSFrameHeader::CADTSFrameHeader((CADTSFrameHeader *)&v94, &v37[v40]);
      v89 = 2 * ((v94 & 0x8000) == 0) + 7;
      if ( v89 > v34 )
      {
        if ( (unsigned __int8)byte_1801B110B >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 40, &WPP_82f9222a817a345a00b3f046417f5137_Traceguids, this);
        v89 = 7;
      }
      if ( CADTSFrameHeader::IsValidFrameHeader((CADTSFrameHeader *)&v94) )
        break;
      ++*((_DWORD *)this + 2);
      NextValidADTSHeader = CADTSBufferParser::FindNextSyncPoint(this, v37, v34);
      if ( NextValidADTSHeader < 0 )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != NextValidADTSHeader )
            CallStackContext::TraceFailure(v44, "CADTSBufferParser::FindNextValidADTSHeader", 357, NextValidADTSHeader);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
            this,
            NextValidADTSHeader);
LABEL_87:
        v33 = v88;
        goto LABEL_88;
      }
    }
    v86 = 1;
    v33 = v95 & 0x1FFF;
LABEL_88:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v87);
    if ( NextValidADTSHeader < 0 )
    {
      v57 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != NextValidADTSHeader )
          CallStackContext::TraceFailure(v59, "CADTSBufferParser::GetNextSample", 450, NextValidADTSHeader);
      }
      if ( g_wppLevels )
      {
        v12 = 48;
        goto LABEL_12;
      }
      goto LABEL_199;
    }
    v46 = *((_DWORD *)this + 2);
    if ( v46 <= v92 )
    {
      v48 = v90;
    }
    else
    {
      v47 = v46 - v92;
      if ( v47 > 0x1FFF )
        v47 = 0x1FFF;
      v48 = v47 + v90;
    }
    if ( memcpy_s((void *const)(v101 + v91), v48, &v100[v93], v48) )
    {
      v54 = (wchar_t *)CallStackTracing::s_wpInstance;
      NextValidADTSHeader = -1072875855;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
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
        if ( *((_DWORD *)v56 + 499) != -1072875855 )
          CallStackContext::TraceFailure(v56, "CADTSBufferParser::GetNextSample", 466, -1072875855);
      }
      if ( g_wppLevels )
      {
        v12 = 49;
        goto LABEL_12;
      }
      goto LABEL_199;
    }
    v50 = v48 + v91;
    v5 = v96;
    v91 = v50;
    ++*v96;
    if ( *v5 >= *((_DWORD *)this + 3) )
      goto LABEL_129;
  }
  v5 = v96;
LABEL_129:
  if ( !*v5 )
    goto LABEL_199;
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v61 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
      CallStackTracing::s_wpInstance = v62;
      if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
      {
        v61 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v61 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v61 + 8) )
    {
      v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
      if ( *((_DWORD *)v63 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v63, "CADTSBufferParser::GetNextSample", 475, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v12 = 50;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = MFCreateSample(&ppIMFSample);
  if ( NextValidADTSHeader < 0 )
  {
    v65 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64);
      CallStackTracing::s_wpInstance = v66;
      if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
      {
        v65 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v65 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v65 + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
      if ( *((_DWORD *)v67 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v67, "CADTSBufferParser::GetNextSample", 476, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v12 = 51;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                          ppIMFSample,
                          ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v70 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68);
      CallStackTracing::s_wpInstance = v71;
      if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
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
      if ( *((_DWORD *)v72 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v72, "CADTSBufferParser::GetNextSample", 477, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v12 = 52;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  if ( !*((_BYTE *)this + 16) )
    goto LABEL_197;
  v90 = 0;
  NextValidADTSHeader = ULongLongToULong(8LL * v104, &v90);
  if ( NextValidADTSHeader < 0 )
  {
    v74 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73);
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
      if ( *((_DWORD *)v76 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v76, "CADTSBufferParser::GetNextSample", 483, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v12 = 53;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFSample *, const GUID *, void *, _QWORD))ppIMFSample->lpVtbl->SetBlob)(
                          ppIMFSample,
                          &MFSampleExtension_Encryption_SubSample_Mapping,
                          Block,
                          v90);
  if ( NextValidADTSHeader < 0 )
  {
    v78 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77);
      CallStackTracing::s_wpInstance = v79;
      if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
      {
        v78 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v78 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v78 + 8) )
    {
      v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
      if ( *((_DWORD *)v80 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v80, "CADTSBufferParser::GetNextSample", 489, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v12 = 54;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                          ppIMFSample,
                          &MFSampleExtension_Encryption_ProtectionScheme,
                          2);
  if ( NextValidADTSHeader >= 0 )
  {
LABEL_197:
    v84 = ppIMFSample;
    ppIMFSample = 0;
    *v97 = v84;
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_qqdd(*((_QWORD *)WPP_GLOBAL_Control + 17), v68, v69, (_DWORD)this, (__int64)v84);
    goto LABEL_199;
  }
  v81 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68);
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
    if ( *((_DWORD *)v83 + 499) != NextValidADTSHeader )
      CallStackContext::TraceFailure(v83, "CADTSBufferParser::GetNextSample", 491, NextValidADTSHeader);
  }
  if ( g_wppLevels )
  {
    v12 = 55;
    goto LABEL_12;
  }
LABEL_199:
  if ( v100 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this);
  if ( v101 )
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  if ( ppBuffer )
  {
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
    ppBuffer = 0;
  }
  if ( ppIMFSample )
  {
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
    ppIMFSample = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v87);
  operator delete(Block);
  return (unsigned int)NextValidADTSHeader;
}

```

## disassembly

```asm
0x180016854  push    rbp
0x180016856  push    rbx
0x180016857  push    rsi
0x180016858  push    rdi
0x180016859  push    r12
0x18001685b  push    r13
0x18001685d  push    r14
0x18001685f  push    r15
0x180016861  lea     rbp, [rsp-1Fh]
0x180016866  sub     rsp, 0C8h
0x18001686d  mov     rax, cs:__security_cookie
0x180016874  xor     rax, rsp
0x180016877  mov     [rbp+57h+var_48], rax
0x18001687b  xor     r12d, r12d
0x18001687e  mov     [rbp+57h+var_90], rdx
0x180016882  mov     [rdx], r12
0x180016885  lea     r14, aCadtsbufferpar_2; "CADTSBufferParser::GetNextSample"
0x18001688c  mov     [r8], r12d
0x18001688f  mov     rsi, rcx
0x180016892  mov     r8d, 19Bh; int
0x180016898  mov     [rbp+57h+var_98], r9
0x18001689c  mov     rdx, r14; char *
0x18001689f  mov     [rbp+57h+var_78], r12
0x1800168a3  lea     rcx, [rbp+57h+var_BF]; this
0x1800168a7  mov     [rbp+57h+var_70], r12
0x1800168ab  mov     r13, r9
0x1800168ae  mov     [rbp+57h+ppBuffer], r12
0x1800168b2  mov     [rbp+57h+ppIMFSample], r12
0x1800168b6  mov     [rbp+57h+Block], r12
0x1800168ba  mov     [rbp+57h+var_54], r12
0x1800168be  mov     [rbp+57h+var_58], r12d
0x1800168c2  mov     [r9], r12d
0x1800168c5  mov     [rbp+57h+var_C0], r12b
0x1800168c9  mov     [rbp+57h+var_B8], r12d
0x1800168cd  mov     [rbp+57h+var_BC], 7
0x1800168d4  mov     [rbp+57h+var_68], r12d
0x1800168d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800168dd  mov     rcx, [rsi]
0x1800168e0  lea     rdx, [rbp+57h+var_68]
0x1800168e4  mov     rax, [rcx]
0x1800168e7  mov     rax, [rax+28h]
0x1800168eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f0  mov     ebx, eax
0x1800168f2  test    eax, eax
0x1800168f4  jns     loc_1800169A6
0x1800168fa  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016901  test    rdi, rdi
0x180016904  jnz     short loc_180016947
0x180016906  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001690c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016913  mov     rcx, rax
0x180016916  test    rax, rax
0x180016919  jz      short loc_180016939
0x18001691b  mov     rax, [rax]
0x18001691e  mov     edx, 7F0h
0x180016923  mov     rax, [rax+8]
0x180016927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001692c  test    eax, eax
0x18001692e  jz      short loc_180016939
0x180016930  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016937  jmp     short loc_180016947
0x180016939  lea     rdi, qword_1801B07E0
0x180016940  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180016947  cmp     [rdi+8], r12b
0x18001694b  jz      short loc_180016971
0x18001694d  mov     rcx, rdi; this
0x180016950  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016955  cmp     [rax+7CCh], ebx
0x18001695b  jz      short loc_180016971
0x18001695d  mov     r9d, ebx; int
0x180016960  mov     r8d, 19Bh; int
0x180016966  mov     rdx, r14; char *
0x180016969  mov     rcx, rax; this
0x18001696c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016971  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016978  jb      loc_180017501
0x18001697e  mov     edx, 2Ah ; '*'
0x180016983  lea     r8, WPP_82f9222a817a345a00b3f046417f5137_Traceguids
0x18001698a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016991  mov     r9, rsi
0x180016994  mov     dword ptr [rsp+100h+var_E0], ebx
0x180016998  mov     rcx, [rcx+10h]
0x18001699c  call    WPP_SF_qD
0x1800169a1  jmp     loc_180017501
0x1800169a6  mov     ecx, [rbp+57h+var_68]
0x1800169a9  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x1800169ad  sub     ecx, [rsi+8]; cbMaxLength
0x1800169b0  call    cs:__imp_MFCreateMemoryBuffer
0x1800169b6  mov     ebx, eax
0x1800169b8  test    eax, eax
0x1800169ba  jns     loc_180016A4E
0x1800169c0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800169c7  test    rdi, rdi
0x1800169ca  jnz     short loc_180016A0D
0x1800169cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800169d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800169d9  mov     rcx, rax
0x1800169dc  test    rax, rax
0x1800169df  jz      short loc_1800169FF
0x1800169e1  mov     rax, [rax]
0x1800169e4  mov     edx, 7F0h
0x1800169e9  mov     rax, [rax+8]
0x1800169ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f2  test    eax, eax
0x1800169f4  jz      short loc_1800169FF
0x1800169f6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800169fd  jmp     short loc_180016A0D
0x1800169ff  lea     rdi, qword_1801B07E0
0x180016a06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a0d  cmp     [rdi+8], r12b
0x180016a11  jz      short loc_180016A37
0x180016a13  mov     rcx, rdi; this
0x180016a16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016a1b  cmp     [rax+7CCh], ebx
0x180016a21  jz      short loc_180016A37
0x180016a23  mov     r9d, ebx; int
0x180016a26  mov     r8d, 1A1h; int
0x180016a2c  mov     rdx, r14; char *
0x180016a2f  mov     rcx, rax; this
0x180016a32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016a37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016a3e  jb      loc_180017501
0x180016a44  mov     edx, 2Bh ; '+'
0x180016a49  jmp     loc_180016983
0x180016a4e  mov     rcx, [rbp+57h+ppBuffer]
0x180016a52  lea     rdx, [rbp+57h+var_70]
0x180016a56  xor     r9d, r9d
0x180016a59  xor     r8d, r8d
0x180016a5c  mov     rax, [rcx]
0x180016a5f  mov     rax, [rax+18h]
0x180016a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a68  mov     ebx, eax
0x180016a6a  test    eax, eax
0x180016a6c  jns     loc_180016B00
0x180016a72  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a79  test    rdi, rdi
0x180016a7c  jnz     short loc_180016ABF
0x180016a7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016a84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016a8b  mov     rcx, rax
0x180016a8e  test    rax, rax
0x180016a91  jz      short loc_180016AB1
0x180016a93  mov     rax, [rax]
0x180016a96  mov     edx, 7F0h
0x180016a9b  mov     rax, [rax+8]
0x180016a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aa4  test    eax, eax
0x180016aa6  jz      short loc_180016AB1
0x180016aa8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016aaf  jmp     short loc_180016ABF
0x180016ab1  lea     rdi, qword_1801B07E0
0x180016ab8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180016abf  cmp     [rdi+8], r12b
0x180016ac3  jz      short loc_180016AE9
0x180016ac5  mov     rcx, rdi; this
0x180016ac8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016acd  cmp     [rax+7CCh], ebx
0x180016ad3  jz      short loc_180016AE9
0x180016ad5  mov     r9d, ebx; int
0x180016ad8  mov     r8d, 1A2h; int
0x180016ade  mov     rdx, r14; char *
0x180016ae1  mov     rcx, rax; this
0x180016ae4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016ae9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016af0  jb      loc_180017501
0x180016af6  mov     edx, 2Ch ; ','
0x180016afb  jmp     loc_180016983
0x180016b00  mov     rcx, [rsi]
0x180016b03  lea     rdx, [rbp+57h+var_78]
0x180016b07  xor     r9d, r9d
0x180016b0a  xor     r8d, r8d
0x180016b0d  mov     rax, [rcx]
0x180016b10  mov     rax, [rax+18h]
0x180016b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b19  mov     ebx, eax
0x180016b1b  test    eax, eax
0x180016b1d  jns     loc_180016BB1
0x180016b23  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b2a  test    rdi, rdi
0x180016b2d  jnz     short loc_180016B70
0x180016b2f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016b35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b3c  mov     rcx, rax
0x180016b3f  test    rax, rax
0x180016b42  jz      short loc_180016B62
0x180016b44  mov     rax, [rax]
0x180016b47  mov     edx, 7F0h
0x180016b4c  mov     rax, [rax+8]
0x180016b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b55  test    eax, eax
0x180016b57  jz      short loc_180016B62
0x180016b59  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b60  jmp     short loc_180016B70
0x180016b62  lea     rdi, qword_1801B07E0
0x180016b69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180016b70  cmp     [rdi+8], r12b
0x180016b74  jz      short loc_180016B9A
0x180016b76  mov     rcx, rdi; this
0x180016b79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016b7e  cmp     [rax+7CCh], ebx
0x180016b84  jz      short loc_180016B9A
0x180016b86  mov     r9d, ebx; int
0x180016b89  mov     r8d, 1A3h; int
0x180016b8f  mov     rdx, r14; char *
0x180016b92  mov     rcx, rax; this
0x180016b95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016b9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016ba1  jb      loc_180017501
0x180016ba7  mov     edx, 2Dh ; '-'
0x180016bac  jmp     loc_180016983
0x180016bb1  mov     r8d, [rbp+57h+var_68]; unsigned int
0x180016bb5  lea     rax, [rbp+57h+var_BC]
0x180016bb9  mov     rdx, [rbp+57h+var_78]; unsigned __int8 *
0x180016bbd  lea     r9, [rbp+57h+var_C0]; bool *
0x180016bc1  mov     [rsp+100h+var_D8], rax; unsigned int *
0x180016bc6  mov     rcx, rsi; this
0x180016bc9  lea     rax, [rbp+57h+var_B8]
0x180016bcd  mov     [rsp+100h+var_E0], rax; unsigned int *
0x180016bd2  call    ?FindNextValidADTSHeader@CADTSBufferParser@@AEAAJPEAEKPEA_NPEAK2@Z; CADTSBufferParser::FindNextValidADTSHeader(uchar *,ulong,bool *,ulong *,ulong *)
0x180016bd7  mov     ebx, eax
0x180016bd9  test    eax, eax
0x180016bdb  jns     loc_180016C6F
0x180016be1  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016be8  test    rdi, rdi
0x180016beb  jnz     short loc_180016C2E
0x180016bed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016bf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016bfa  mov     rcx, rax
0x180016bfd  test    rax, rax
0x180016c00  jz      short loc_180016C20
0x180016c02  mov     rax, [rax]
0x180016c05  mov     edx, 7F0h
0x180016c0a  mov     rax, [rax+8]
0x180016c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c13  test    eax, eax
0x180016c15  jz      short loc_180016C20
0x180016c17  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c1e  jmp     short loc_180016C2E
0x180016c20  lea     rdi, qword_1801B07E0
0x180016c27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c2e  cmp     [rdi+8], r12b
0x180016c32  jz      short loc_180016C58
0x180016c34  mov     rcx, rdi; this
0x180016c37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016c3c  cmp     [rax+7CCh], ebx
0x180016c42  jz      short loc_180016C58
0x180016c44  mov     r9d, ebx; int
0x180016c47  mov     r8d, 1A5h; int
0x180016c4d  mov     rdx, r14; char *
0x180016c50  mov     rcx, rax; this
0x180016c53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016c58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016c5f  jb      loc_180017501
0x180016c65  mov     edx, 2Eh ; '.'
0x180016c6a  jmp     loc_180016983
0x180016c6f  mov     ecx, [rbp+57h+var_BC]
0x180016c72  lea     rdi, qword_1801B07E0
0x180016c79  mov     edx, r12d
0x180016c7c  lea     r14, WPP_82f9222a817a345a00b3f046417f5137_Traceguids
0x180016c83  mov     r12d, [rbp+57h+var_B8]
0x180016c87  mov     r15d, 7F0h
0x180016c8d  mov     [rbp+57h+var_B0], edx
0x180016c90  mov     [rbp+57h+var_B8], ecx
0x180016c93  mov     al, [rbp+57h+var_C0]
0x180016c96  test    al, al
0x180016c98  jz      loc_1800170B3
0x180016c9e  mov     eax, [rsi+8]
0x180016ca1  mov     r13d, [rbp+57h+var_68]
0x180016ca5  mov     [rbp+57h+var_A8], eax
0x180016ca8  add     eax, r12d
0x180016cab  mov     [rbp+57h+var_AC], eax
0x180016cae  cmp     eax, r13d
0x180016cb1  ja      loc_1800170AF
0x180016cb7  cmp     byte ptr [rsi+10h], 0
0x180016cbb  jz      short loc_180016CD9
0x180016cbd  mov     edx, ecx
0x180016cbf  lea     r8, [rbp+57h+Block]
0x180016cc3  mov     ecx, r12d; unsigned int
0x180016cc6  call    _anonymous_namespace___UpdateSubSampleMappingForFrame
0x180016ccb  mov     ebx, eax
0x180016ccd  test    eax, eax
0x180016ccf  js      loc_180016F03
0x180016cd5  mov     r13d, [rbp+57h+var_68]
0x180016cd9  mov     eax, r12d
0x180016cdc  mov     [rbp+57h+var_BC], 0
0x180016ce3  add     [rsi+8], eax
0x180016ce6  lea     rdx, aCadtsbufferpar_1; "CADTSBufferParser::FindNextValidADTSHea"...
0x180016ced  mov     r12, [rbp+57h+var_78]
0x180016cf1  lea     rcx, [rbp+57h+var_BF]; this
0x180016cf5  mov     [rbp+57h+var_B4], eax
0x180016cf8  mov     r8d, 155h; int
0x180016cfe  xor     al, al
0x180016d00  mov     [rbp+57h+var_C0], al
0x180016d03  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016d08  mov     edx, [rsi+8]
0x180016d0b  lea     r8d, [r13-1]
0x180016d0f  cmp     edx, r8d
0x180016d12  jnb     short loc_180016D3A
0x180016d14  mov     ecx, edx
0x180016d16  mov     eax, ecx
  ... truncated ...
```
