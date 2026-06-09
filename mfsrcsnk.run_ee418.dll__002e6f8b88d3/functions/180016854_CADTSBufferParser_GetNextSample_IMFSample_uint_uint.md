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
  __int64 v9; // r8
  __int64 v10; // r9
  wchar_t *v11; // rdi
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rdi
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  wchar_t *v26; // rdi
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rdi
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rdi
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  unsigned int v43; // r12d
  unsigned int v44; // r13d
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  unsigned int v48; // eax
  unsigned __int8 *v49; // r12
  unsigned int v50; // edx
  unsigned int v51; // ecx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // r13d
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  unsigned int v68; // edx
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  wchar_t *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  wchar_t *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // r9
  wchar_t *v99; // rcx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r9
  wchar_t *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  __int64 v108; // r9
  wchar_t *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  IMFSample *v112; // rcx
  bool v114; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v115[3]; // [rsp+41h] [rbp-68h] BYREF
  unsigned int v116; // [rsp+44h] [rbp-65h] BYREF
  unsigned int v117; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v118; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned int v119; // [rsp+50h] [rbp-59h]
  unsigned int v120; // [rsp+54h] [rbp-55h]
  int v121; // [rsp+58h] [rbp-51h]
  int v122; // [rsp+60h] [rbp-49h] BYREF
  int v123; // [rsp+64h] [rbp-45h]
  unsigned int *v124; // [rsp+68h] [rbp-41h]
  struct IMFSample **v125; // [rsp+70h] [rbp-39h]
  IMFSample *ppIMFSample; // [rsp+78h] [rbp-31h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 *v128; // [rsp+88h] [rbp-21h] BYREF
  __int64 v129; // [rsp+90h] [rbp-19h] BYREF
  unsigned int v130; // [rsp+98h] [rbp-11h] BYREF
  void *Block; // [rsp+A0h] [rbp-9h]
  unsigned int v132; // [rsp+A8h] [rbp-1h]
  __int64 v133; // [rsp+ACh] [rbp+3h]

  v125 = a2;
  *a2 = 0;
  *a3 = 0;
  v124 = a4;
  v128 = 0;
  v129 = 0;
  v5 = a4;
  ppBuffer = 0;
  ppIMFSample = 0;
  Block = 0;
  v133 = 0;
  v132 = 0;
  *a4 = 0;
  v114 = 0;
  v117 = 0;
  v116 = 7;
  v130 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v115, "CADTSBufferParser::GetNextSample", 411);
  NextValidADTSHeader = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)this + 40LL))(
                          *(_QWORD *)this,
                          &v130);
  if ( NextValidADTSHeader < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v7, v6, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CADTSBufferParser::GetNextSample",
          411,
          NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v14 = 42;
    goto LABEL_12;
  }
  NextValidADTSHeader = MFCreateMemoryBuffer(v130 - *((_DWORD *)this + 2), &ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v21, "CADTSBufferParser::GetNextSample", 417, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v14 = 43;
    goto LABEL_12;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                          ppBuffer,
                          &v129,
                          0,
                          0);
  if ( NextValidADTSHeader < 0 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22, v24, v25);
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
      if ( *((_DWORD *)v28 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v28, "CADTSBufferParser::GetNextSample", 418, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v14 = 44;
    goto LABEL_12;
  }
  NextValidADTSHeader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, _QWORD, _QWORD))(**(_QWORD **)this + 24LL))(
                          *(_QWORD *)this,
                          &v128,
                          0,
                          0);
  if ( NextValidADTSHeader < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v30, v29, v31, v32);
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
      if ( *((_DWORD *)v35 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v35, "CADTSBufferParser::GetNextSample", 419, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v14 = 45;
    goto LABEL_12;
  }
  NextValidADTSHeader = CADTSBufferParser::FindNextValidADTSHeader(this, v128, v130, &v114, &v117, &v116);
  if ( NextValidADTSHeader < 0 )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v37, v36, v38, v39);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
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
      if ( *((_DWORD *)v42 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v42, "CADTSBufferParser::GetNextSample", 421, NextValidADTSHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_199;
    v14 = 46;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
      this,
      NextValidADTSHeader);
    goto LABEL_199;
  }
  v43 = v117;
  v119 = 0;
  v117 = v116;
  while ( 1 )
  {
    if ( !v114 )
      goto LABEL_129;
    v44 = v130;
    v121 = *((_DWORD *)this + 2);
    v120 = v43 + v121;
    if ( v43 + v121 > v130 )
      break;
    if ( *((_BYTE *)this + 16) )
    {
      NextValidADTSHeader = anonymous_namespace_::UpdateSubSampleMappingForFrame(v43);
      if ( NextValidADTSHeader < 0 )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
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
          if ( *((_DWORD *)v71 + 499) != NextValidADTSHeader )
            CallStackContext::TraceFailure(v71, "CADTSBufferParser::GetNextSample", 441, NextValidADTSHeader);
        }
        if ( g_wppLevels )
        {
          v14 = 47;
          goto LABEL_12;
        }
        goto LABEL_199;
      }
      v44 = v130;
    }
    v48 = v43;
    v116 = 0;
    *((_DWORD *)this + 2) += v43;
    v49 = v128;
    v118 = v48;
    v114 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v115,
      "CADTSBufferParser::FindNextValidADTSHeader",
      341);
    v50 = *((_DWORD *)this + 2);
    if ( v50 < v44 - 1 )
    {
      v51 = *((_DWORD *)this + 2);
      do
      {
        if ( v49[v51] == 0xFF )
        {
          if ( (v49[v51 + 1] & 0xF6) == 0xF0 )
            break;
          ++v50;
        }
        *((_DWORD *)this + 2) = ++v50;
        v51 = v50;
      }
      while ( v50 < v44 - 1 );
    }
    NextValidADTSHeader = 0;
    while ( 1 )
    {
      v52 = *((unsigned int *)this + 2);
      if ( (int)v52 + 7 > v44 )
        goto LABEL_87;
      CADTSFrameHeader::CADTSFrameHeader((CADTSFrameHeader *)&v122, &v49[v52]);
      v117 = 2 * ((v122 & 0x8000) == 0) + 7;
      if ( v117 > v44 )
      {
        if ( (unsigned __int8)byte_1801B110B >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 40, &WPP_82f9222a817a345a00b3f046417f5137_Traceguids, this);
        v117 = 7;
      }
      if ( CADTSFrameHeader::IsValidFrameHeader((CADTSFrameHeader *)&v122) )
        break;
      ++*((_DWORD *)this + 2);
      NextValidADTSHeader = CADTSBufferParser::FindNextSyncPoint(this, v49, v44);
      if ( NextValidADTSHeader < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54, v55);
          CallStackTracing::s_wpInstance = v57;
          if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
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
          if ( *((_DWORD *)v58 + 499) != NextValidADTSHeader )
            CallStackContext::TraceFailure(v58, "CADTSBufferParser::FindNextValidADTSHeader", 357, NextValidADTSHeader);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
            this,
            NextValidADTSHeader);
LABEL_87:
        v43 = v116;
        goto LABEL_88;
      }
    }
    v114 = 1;
    v43 = v123 & 0x1FFF;
LABEL_88:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v115);
    if ( NextValidADTSHeader < 0 )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v60, v61);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v77 + 499) != NextValidADTSHeader )
          CallStackContext::TraceFailure(v77, "CADTSBufferParser::GetNextSample", 450, NextValidADTSHeader);
      }
      if ( g_wppLevels )
      {
        v14 = 48;
        goto LABEL_12;
      }
      goto LABEL_199;
    }
    v62 = *((_DWORD *)this + 2);
    if ( v62 <= v120 )
    {
      v64 = v118;
    }
    else
    {
      v63 = v62 - v120;
      if ( v63 > 0x1FFF )
        v63 = 0x1FFF;
      v64 = v63 + v118;
    }
    if ( memcpy_s((void *const)(v129 + v119), v64, &v128[v121], v64) )
    {
      v72 = (wchar_t *)CallStackTracing::s_wpInstance;
      NextValidADTSHeader = -1072875855;
      if ( !CallStackTracing::s_wpInstance )
      {
        v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
        CallStackTracing::s_wpInstance = v73;
        if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
        {
          v72 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v72 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v72 + 8) )
      {
        v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
        if ( *((_DWORD *)v74 + 499) != -1072875855 )
          CallStackContext::TraceFailure(v74, "CADTSBufferParser::GetNextSample", 466, -1072875855);
      }
      if ( g_wppLevels )
      {
        v14 = 49;
        goto LABEL_12;
      }
      goto LABEL_199;
    }
    v68 = v64 + v119;
    v5 = v124;
    v119 = v68;
    ++*v124;
    if ( *v5 >= *((_DWORD *)this + 3) )
      goto LABEL_129;
  }
  v5 = v124;
LABEL_129:
  if ( !*v5 )
    goto LABEL_199;
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v81 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79, v80);
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
        CallStackContext::TraceFailure(v83, "CADTSBufferParser::GetNextSample", 475, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v14 = 50;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = MFCreateSample(&ppIMFSample);
  if ( NextValidADTSHeader < 0 )
  {
    v87 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85, v86);
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
      if ( *((_DWORD *)v89 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v89, "CADTSBufferParser::GetNextSample", 476, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v14 = 51;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                          ppIMFSample,
                          ppBuffer);
  if ( NextValidADTSHeader < 0 )
  {
    v93 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90, v91, v92);
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
    if ( *((_BYTE *)v93 + 8) )
    {
      v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
      if ( *((_DWORD *)v95 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v95, "CADTSBufferParser::GetNextSample", 477, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v14 = 52;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  if ( !*((_BYTE *)this + 16) )
    goto LABEL_197;
  v118 = 0;
  NextValidADTSHeader = ULongLongToULong(8LL * v132, &v118);
  if ( NextValidADTSHeader < 0 )
  {
    v99 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v96, v97, v98);
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
      if ( *((_DWORD *)v101 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v101, "CADTSBufferParser::GetNextSample", 483, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v14 = 53;
      goto LABEL_12;
    }
    goto LABEL_199;
  }
  NextValidADTSHeader = ((__int64 (__fastcall *)(IMFSample *, const GUID *, void *, _QWORD))ppIMFSample->lpVtbl->SetBlob)(
                          ppIMFSample,
                          &MFSampleExtension_Encryption_SubSample_Mapping,
                          Block,
                          v118);
  if ( NextValidADTSHeader < 0 )
  {
    v105 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v102, v103, v104);
      CallStackTracing::s_wpInstance = v106;
      if ( v106 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
      {
        v105 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v105 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v105 + 8) )
    {
      v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
      if ( *((_DWORD *)v107 + 499) != NextValidADTSHeader )
        CallStackContext::TraceFailure(v107, "CADTSBufferParser::GetNextSample", 489, NextValidADTSHeader);
    }
    if ( g_wppLevels )
    {
      v14 = 54;
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
    v112 = ppIMFSample;
    ppIMFSample = 0;
    *v125 = v112;
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_qqdd(*((_QWORD *)WPP_GLOBAL_Control + 17), v90, v91, (_DWORD)this, (__int64)v112);
    goto LABEL_199;
  }
  v109 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90, v91, v108);
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
    if ( *((_DWORD *)v111 + 499) != NextValidADTSHeader )
      CallStackContext::TraceFailure(v111, "CADTSBufferParser::GetNextSample", 491, NextValidADTSHeader);
  }
  if ( g_wppLevels )
  {
    v14 = 55;
    goto LABEL_12;
  }
LABEL_199:
  if ( v128 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this);
  if ( v129 )
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v115);
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
