# CADTSBufferParser::GetNextSample(IMFSample * *,uint *,uint *)

- ea: `0x18002d034`
- end: `0x18002ddd9`
- name: `?GetNextSample@CADTSBufferParser@@QEAAJPEAPEAUIMFSample@@PEAI1@Z`
- size: `3493`
- prototype: `__int64 __fastcall(CADTSBufferParser *__hidden this, struct IMFSample **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800c15f0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18002d034`
- `0x18002dde0`
- `0x18002e4d0`
- `0x18002e544`
- `0x18002e6d0`
- `0x180079680`
- `0x180079f34`
- `0x180110a88`
- `0x180110ed0`
- `0x18011190c`
- `0x180121750`
- `0x18013abf8`
- `0x18013b2cc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d0e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d1b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d270`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d327`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d3eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d5e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d71c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d7b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d902`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002db12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d0e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d1b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d270`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d327`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d3eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d5e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d71c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d7b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d902`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002db12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc86`
- `MFPlat!MFCreateMemoryBuffer` at `0x18002d196`
- `MFPlat!MFCreateMemoryBuffer` at `0x18002d196`
- `MFPlat!MFCreateSample` at `0x18002d989`
- `MFPlat!MFCreateSample` at `0x18002d989`

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
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v30 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v51 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        if ( (unsigned __int8)byte_1801BA10B >= 4u )
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
            v42 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v57 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v54 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v61 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v65 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v70 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v74 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v78 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
      v81 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18002d034  push    rbp
0x18002d036  push    rbx
0x18002d037  push    rsi
0x18002d038  push    rdi
0x18002d039  push    r12
0x18002d03b  push    r13
0x18002d03d  push    r14
0x18002d03f  push    r15
0x18002d041  lea     rbp, [rsp-1Fh]
0x18002d046  sub     rsp, 0C8h
0x18002d04d  mov     rax, cs:__security_cookie
0x18002d054  xor     rax, rsp
0x18002d057  mov     [rbp+57h+var_48], rax
0x18002d05b  xor     r12d, r12d
0x18002d05e  mov     [rbp+57h+var_90], rdx
0x18002d062  mov     [rdx], r12
0x18002d065  lea     r14, aCadtsbufferpar_2; "CADTSBufferParser::GetNextSample"
0x18002d06c  mov     [r8], r12d
0x18002d06f  mov     rsi, rcx
0x18002d072  mov     r8d, 19Bh; int
0x18002d078  mov     [rbp+57h+var_98], r9
0x18002d07c  mov     rdx, r14; char *
0x18002d07f  mov     [rbp+57h+var_78], r12
0x18002d083  lea     rcx, [rbp+57h+var_BF]; this
0x18002d087  mov     [rbp+57h+var_70], r12
0x18002d08b  mov     r13, r9
0x18002d08e  mov     [rbp+57h+ppBuffer], r12
0x18002d092  mov     [rbp+57h+ppIMFSample], r12
0x18002d096  mov     [rbp+57h+Block], r12
0x18002d09a  mov     [rbp+57h+var_54], r12
0x18002d09e  mov     [rbp+57h+var_58], r12d
0x18002d0a2  mov     [r9], r12d
0x18002d0a5  mov     [rbp+57h+var_C0], r12b
0x18002d0a9  mov     [rbp+57h+var_B8], r12d
0x18002d0ad  mov     [rbp+57h+var_BC], 7
0x18002d0b4  mov     [rbp+57h+var_68], r12d
0x18002d0b8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002d0bd  mov     rcx, [rsi]
0x18002d0c0  lea     rdx, [rbp+57h+var_68]
0x18002d0c4  mov     rax, [rcx]
0x18002d0c7  mov     rax, [rax+28h]
0x18002d0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0d0  mov     ebx, eax
0x18002d0d2  test    eax, eax
0x18002d0d4  jns     loc_18002D18C
0x18002d0da  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d0e1  test    rdi, rdi
0x18002d0e4  jnz     short loc_18002D12D
0x18002d0e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d0ed  nop     dword ptr [rax+rax+00h]
0x18002d0f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d0f9  mov     rcx, rax
0x18002d0fc  test    rax, rax
0x18002d0ff  jz      short loc_18002D11F
0x18002d101  mov     rax, [rax]
0x18002d104  mov     edx, 7F0h
0x18002d109  mov     rax, [rax+8]
0x18002d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d112  test    eax, eax
0x18002d114  jz      short loc_18002D11F
0x18002d116  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d11d  jmp     short loc_18002D12D
0x18002d11f  lea     rdi, qword_1801B97E0
0x18002d126  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d12d  cmp     [rdi+8], r12b
0x18002d131  jz      short loc_18002D157
0x18002d133  mov     rcx, rdi; this
0x18002d136  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d13b  cmp     [rax+7CCh], ebx
0x18002d141  jz      short loc_18002D157
0x18002d143  mov     r9d, ebx; int
0x18002d146  mov     r8d, 19Bh; int
0x18002d14c  mov     rdx, r14; char *
0x18002d14f  mov     rcx, rax; this
0x18002d152  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d157  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d15e  jb      loc_18002DD47
0x18002d164  mov     edx, 2Ah ; '*'
0x18002d169  lea     r8, WPP_82f9222a817a345a00b3f046417f5137_Traceguids
0x18002d170  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d177  mov     r9, rsi
0x18002d17a  mov     dword ptr [rsp+100h+var_E0], ebx
0x18002d17e  mov     rcx, [rcx+10h]
0x18002d182  call    WPP_SF_qD
0x18002d187  jmp     loc_18002DD47
0x18002d18c  mov     ecx, [rbp+57h+var_68]
0x18002d18f  lea     rdx, [rbp+57h+ppBuffer]; ppBuffer
0x18002d193  sub     ecx, [rsi+8]; cbMaxLength
0x18002d196  call    cs:__imp_MFCreateMemoryBuffer
0x18002d19d  nop     dword ptr [rax+rax+00h]
0x18002d1a2  mov     ebx, eax
0x18002d1a4  test    eax, eax
0x18002d1a6  jns     loc_18002D240
0x18002d1ac  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1b3  test    rdi, rdi
0x18002d1b6  jnz     short loc_18002D1FF
0x18002d1b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d1bf  nop     dword ptr [rax+rax+00h]
0x18002d1c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1cb  mov     rcx, rax
0x18002d1ce  test    rax, rax
0x18002d1d1  jz      short loc_18002D1F1
0x18002d1d3  mov     rax, [rax]
0x18002d1d6  mov     edx, 7F0h
0x18002d1db  mov     rax, [rax+8]
0x18002d1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1e4  test    eax, eax
0x18002d1e6  jz      short loc_18002D1F1
0x18002d1e8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1ef  jmp     short loc_18002D1FF
0x18002d1f1  lea     rdi, qword_1801B97E0
0x18002d1f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1ff  cmp     [rdi+8], r12b
0x18002d203  jz      short loc_18002D229
0x18002d205  mov     rcx, rdi; this
0x18002d208  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d20d  cmp     [rax+7CCh], ebx
0x18002d213  jz      short loc_18002D229
0x18002d215  mov     r9d, ebx; int
0x18002d218  mov     r8d, 1A1h; int
0x18002d21e  mov     rdx, r14; char *
0x18002d221  mov     rcx, rax; this
0x18002d224  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d229  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d230  jb      loc_18002DD47
0x18002d236  mov     edx, 2Bh ; '+'
0x18002d23b  jmp     loc_18002D169
0x18002d240  mov     rcx, [rbp+57h+ppBuffer]
0x18002d244  lea     rdx, [rbp+57h+var_70]
0x18002d248  xor     r9d, r9d
0x18002d24b  xor     r8d, r8d
0x18002d24e  mov     rax, [rcx]
0x18002d251  mov     rax, [rax+18h]
0x18002d255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d25a  mov     ebx, eax
0x18002d25c  test    eax, eax
0x18002d25e  jns     loc_18002D2F8
0x18002d264  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d26b  test    rdi, rdi
0x18002d26e  jnz     short loc_18002D2B7
0x18002d270  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d277  nop     dword ptr [rax+rax+00h]
0x18002d27c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d283  mov     rcx, rax
0x18002d286  test    rax, rax
0x18002d289  jz      short loc_18002D2A9
0x18002d28b  mov     rax, [rax]
0x18002d28e  mov     edx, 7F0h
0x18002d293  mov     rax, [rax+8]
0x18002d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29c  test    eax, eax
0x18002d29e  jz      short loc_18002D2A9
0x18002d2a0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d2a7  jmp     short loc_18002D2B7
0x18002d2a9  lea     rdi, qword_1801B97E0
0x18002d2b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d2b7  cmp     [rdi+8], r12b
0x18002d2bb  jz      short loc_18002D2E1
0x18002d2bd  mov     rcx, rdi; this
0x18002d2c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d2c5  cmp     [rax+7CCh], ebx
0x18002d2cb  jz      short loc_18002D2E1
0x18002d2cd  mov     r9d, ebx; int
0x18002d2d0  mov     r8d, 1A2h; int
0x18002d2d6  mov     rdx, r14; char *
0x18002d2d9  mov     rcx, rax; this
0x18002d2dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d2e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d2e8  jb      loc_18002DD47
0x18002d2ee  mov     edx, 2Ch ; ','
0x18002d2f3  jmp     loc_18002D169
0x18002d2f8  mov     rcx, [rsi]
0x18002d2fb  lea     rdx, [rbp+57h+var_78]
0x18002d2ff  xor     r9d, r9d
0x18002d302  xor     r8d, r8d
0x18002d305  mov     rax, [rcx]
0x18002d308  mov     rax, [rax+18h]
0x18002d30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d311  mov     ebx, eax
0x18002d313  test    eax, eax
0x18002d315  jns     loc_18002D3AF
0x18002d31b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d322  test    rdi, rdi
0x18002d325  jnz     short loc_18002D36E
0x18002d327  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d32e  nop     dword ptr [rax+rax+00h]
0x18002d333  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d33a  mov     rcx, rax
0x18002d33d  test    rax, rax
0x18002d340  jz      short loc_18002D360
0x18002d342  mov     rax, [rax]
0x18002d345  mov     edx, 7F0h
0x18002d34a  mov     rax, [rax+8]
0x18002d34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d353  test    eax, eax
0x18002d355  jz      short loc_18002D360
0x18002d357  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d35e  jmp     short loc_18002D36E
0x18002d360  lea     rdi, qword_1801B97E0
0x18002d367  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d36e  cmp     [rdi+8], r12b
0x18002d372  jz      short loc_18002D398
0x18002d374  mov     rcx, rdi; this
0x18002d377  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d37c  cmp     [rax+7CCh], ebx
0x18002d382  jz      short loc_18002D398
0x18002d384  mov     r9d, ebx; int
0x18002d387  mov     r8d, 1A3h; int
0x18002d38d  mov     rdx, r14; char *
0x18002d390  mov     rcx, rax; this
0x18002d393  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d398  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d39f  jb      loc_18002DD47
0x18002d3a5  mov     edx, 2Dh ; '-'
0x18002d3aa  jmp     loc_18002D169
0x18002d3af  mov     r8d, [rbp+57h+var_68]; unsigned int
0x18002d3b3  lea     rax, [rbp+57h+var_BC]
0x18002d3b7  mov     rdx, [rbp+57h+var_78]; unsigned __int8 *
0x18002d3bb  lea     r9, [rbp+57h+var_C0]; bool *
0x18002d3bf  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18002d3c4  mov     rcx, rsi; this
0x18002d3c7  lea     rax, [rbp+57h+var_B8]
0x18002d3cb  mov     [rsp+100h+var_E0], rax; unsigned int *
0x18002d3d0  call    ?FindNextValidADTSHeader@CADTSBufferParser@@AEAAJPEAEKPEA_NPEAK2@Z; CADTSBufferParser::FindNextValidADTSHeader(uchar *,ulong,bool *,ulong *,ulong *)
0x18002d3d5  mov     ebx, eax
0x18002d3d7  test    eax, eax
0x18002d3d9  jns     loc_18002D473
0x18002d3df  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d3e6  test    rdi, rdi
0x18002d3e9  jnz     short loc_18002D432
0x18002d3eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d3f2  nop     dword ptr [rax+rax+00h]
0x18002d3f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d3fe  mov     rcx, rax
0x18002d401  test    rax, rax
0x18002d404  jz      short loc_18002D424
0x18002d406  mov     rax, [rax]
0x18002d409  mov     edx, 7F0h
0x18002d40e  mov     rax, [rax+8]
0x18002d412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d417  test    eax, eax
0x18002d419  jz      short loc_18002D424
0x18002d41b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d422  jmp     short loc_18002D432
0x18002d424  lea     rdi, qword_1801B97E0
0x18002d42b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d432  cmp     [rdi+8], r12b
0x18002d436  jz      short loc_18002D45C
0x18002d438  mov     rcx, rdi; this
0x18002d43b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d440  cmp     [rax+7CCh], ebx
0x18002d446  jz      short loc_18002D45C
0x18002d448  mov     r9d, ebx; int
0x18002d44b  mov     r8d, 1A5h; int
0x18002d451  mov     rdx, r14; char *
0x18002d454  mov     rcx, rax; this
0x18002d457  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d45c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d463  jb      loc_18002DD47
0x18002d469  mov     edx, 2Eh ; '.'
0x18002d46e  jmp     loc_18002D169
0x18002d473  mov     ecx, [rbp+57h+var_BC]
0x18002d476  lea     rdi, qword_1801B97E0
0x18002d47d  mov     edx, r12d
0x18002d480  lea     r14, WPP_82f9222a817a345a00b3f046417f5137_Traceguids
0x18002d487  mov     r12d, [rbp+57h+var_B8]
0x18002d48b  mov     r15d, 7F0h
0x18002d491  mov     [rbp+57h+var_B0], edx
0x18002d494  mov     [rbp+57h+var_B8], ecx
0x18002d497  mov     al, [rbp+57h+var_C0]
0x18002d49a  test    al, al
0x18002d49c  jz      loc_18002D8CF
0x18002d4a2  mov     eax, [rsi+8]
0x18002d4a5  mov     r13d, [rbp+57h+var_68]
0x18002d4a9  mov     [rbp+57h+var_A8], eax
0x18002d4ac  add     eax, r12d
0x18002d4af  mov     [rbp+57h+var_AC], eax
0x18002d4b2  cmp     eax, r13d
0x18002d4b5  ja      loc_18002D8CB
0x18002d4bb  cmp     byte ptr [rsi+10h], 0
0x18002d4bf  jz      short loc_18002D4DD
0x18002d4c1  mov     edx, ecx
0x18002d4c3  lea     r8, [rbp+57h+Block]
0x18002d4c7  mov     ecx, r12d; unsigned int
0x18002d4ca  call    _anonymous_namespace___UpdateSubSampleMappingForFrame
0x18002d4cf  mov     ebx, eax
0x18002d4d1  test    eax, eax
0x18002d4d3  js      loc_18002D70D
0x18002d4d9  mov     r13d, [rbp+57h+var_68]
0x18002d4dd  mov     eax, r12d
0x18002d4e0  mov     [rbp+57h+var_BC], 0
0x18002d4e7  add     [rsi+8], eax
0x18002d4ea  lea     rdx, aCadtsbufferpar_1; "CADTSBufferParser::FindNextValidADTSHea"...
0x18002d4f1  mov     r12, [rbp+57h+var_78]
0x18002d4f5  lea     rcx, [rbp+57h+var_BF]; this
0x18002d4f9  mov     [rbp+57h+var_B4], eax
0x18002d4fc  mov     r8d, 155h; int
0x18002d502  xor     al, al
0x18002d504  mov     [rbp+57h+var_C0], al
0x18002d507  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
  ... truncated ...
```
