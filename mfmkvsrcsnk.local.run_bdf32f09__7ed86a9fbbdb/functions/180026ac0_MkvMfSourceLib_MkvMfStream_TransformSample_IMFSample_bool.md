# MkvMfSourceLib::MkvMfStream::TransformSample(IMFSample * *,bool)

- ea: `0x180026ac0`
- end: `0x180027ecc`
- name: `?TransformSample@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `5132`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *this, struct IMFSample **)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800376e0`
- `0x1800383d0`

## callees

- `0x180002e14`
- `0x1800036c5`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000a3e0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18002110c`
- `0x18002148c`
- `0x180023adc`
- `0x180026ac0`
- `0x180071330`
- `0x1800796dc`
- `0x18007ac54`
- `0x18007acc4`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026c77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026de5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ebe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002703e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027117`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027215`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002731a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800273fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027714`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027761`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027a50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027b3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027c26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027d11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026c77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026de5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ebe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002703e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027117`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027215`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002731a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800273fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027714`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027761`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027a50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027b3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027c26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027d11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e0f`
- `MFPlat!MFCreateMemoryBuffer` at `0x180026b81`
- `MFPlat!MFCreateMemoryBuffer` at `0x180027625`
- `MFPlat!MFCreateMemoryBuffer` at `0x180026b81`
- `MFPlat!MFCreateMemoryBuffer` at `0x180027625`

## string_xrefs

- `0x180026b34`: `m_pFrameCompression->settings_len > DWORD_MAX`

## pseudocode

```c
__int64 __fastcall MkvMfSourceLib::MkvMfStream::TransformSample(
        MkvMfSourceLib::MkvMfStream *this,
        struct IMFSample **a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  HRESULT v10; // r15d
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  __int64 v85; // r12
  unsigned int v86; // ebx
  DWORD *v87; // r15
  unsigned __int64 v88; // rcx
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  int v95; // ebx
  int v96; // r12d
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 *v106; // rcx
  CallStackTracing *v107; // rax
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  struct CallStackContext *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 *v115; // rcx
  CallStackTracing *v116; // rax
  struct CallStackContext *v117; // rax
  __int64 *v118; // rcx
  CallStackTracing *v119; // rax
  struct CallStackContext *v120; // rax
  __int64 *v121; // rcx
  CallStackTracing *v122; // rax
  struct CallStackContext *v123; // rax
  __int64 *v124; // rcx
  CallStackTracing *v125; // rax
  struct CallStackContext *v126; // rax
  __int64 *v127; // rcx
  CallStackTracing *v128; // rax
  struct CallStackContext *v129; // rax
  __int64 v130; // rdx
  __int64 v131; // r8
  __int64 v132; // r9
  __int64 *v133; // rcx
  CallStackTracing *v134; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFMediaBuffer *v136; // [rsp+30h] [rbp-A9h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v138; // [rsp+40h] [rbp-99h] BYREF
  _BYTE v139[8]; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v140; // [rsp+50h] [rbp-89h]
  __int64 v141; // [rsp+58h] [rbp-81h]
  _BYTE v142[8]; // [rsp+60h] [rbp-79h] BYREF
  int v143; // [rsp+68h] [rbp-71h]
  __int64 v144; // [rsp+70h] [rbp-69h]
  __int64 v145; // [rsp+80h] [rbp-59h] BYREF
  unsigned int v146; // [rsp+88h] [rbp-51h]
  __int64 v147; // [rsp+90h] [rbp-49h]
  int v148; // [rsp+98h] [rbp-41h]
  char *v149; // [rsp+E0h] [rbp+7h]
  __int64 *v150; // [rsp+E8h] [rbp+Fh]
  char v151; // [rsp+F0h] [rbp+17h]
  char v152; // [rsp+148h] [rbp+6Fh] BYREF
  void *v153; // [rsp+158h] [rbp+7Fh] BYREF

  if ( !a2 || !*a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v152,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      332);
    v133 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v134 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v130, v131, v132);
      CallStackTracing::s_wpInstance = v134;
      if ( v134 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v134 + 8LL))(v134, 2032) )
      {
        v133 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v133 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v6 = -2147467261;
    if ( *((_BYTE *)v133 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v133);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfStream::TransformSample",
          332,
          -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
        this,
        -2147467261);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
    return (unsigned int)v6;
  }
  v4 = *((_QWORD *)this + 39);
  if ( !v4 )
    return 0;
  if ( *(_DWORD *)v4 != 3 )
  {
    if ( !*(_DWORD *)v4 )
    {
      memset_0(&v145, 0, 0x58u);
      v152 = 0;
      v60 = inflateInit2_(&v145);
      v149 = &v152;
      v150 = &v145;
      v151 = 1;
      if ( v60 )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v153,
          "MkvMfSourceLib::MkvMfStream::TransformSample",
          386);
        v64 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v64 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v6 = -2147220907;
        if ( *((_BYTE *)v64 + 8) )
        {
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
          if ( *((_DWORD *)v66 + 499) != -2147220907 )
            CallStackContext::TraceFailure(v66, "MkvMfSourceLib::MkvMfStream::TransformSample", 386, -2147220907);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147220907);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      v136 = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v153,
        "MkvMfSourceLib::MkvMfStream::TransformSample",
        390);
      v6 = ((__int64 (__fastcall *)(_QWORD, struct IMFMediaBuffer **))(*a2)->lpVtbl->ConvertToContiguousBuffer)(
             *a2,
             &v136);
      if ( v6 < 0 )
      {
        v70 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v70 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
          if ( *((_DWORD *)v72 + 499) != v6 )
            CallStackContext::TraceFailure(v72, "MkvMfSourceLib::MkvMfStream::TransformSample", 390, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      v6 = ((__int64 (__fastcall *)(_QWORD))(*a2)->lpVtbl->RemoveAllBuffers)(*a2);
      if ( v6 < 0 )
      {
        v76 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73, v74, v75);
          CallStackTracing::s_wpInstance = v77;
          if ( v77 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
          {
            v76 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v76 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v76 + 8) )
        {
          v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
          if ( *((_DWORD *)v78 + 499) != v6 )
            CallStackContext::TraceFailure(v78, "MkvMfSourceLib::MkvMfStream::TransformSample", 391, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      CSmartMFBufferLock::CSmartMFBufferLock((CSmartMFBufferLock *)v139, v136);
      v6 = CSmartMFBufferLock::Lock((CSmartMFBufferLock *)v139);
      if ( v6 < 0 )
      {
        v82 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79, v80, v81);
          CallStackTracing::s_wpInstance = v83;
          if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
          {
            v82 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v82 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v82 + 8) )
        {
          v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
          if ( *((_DWORD *)v84 + 499) != v6 )
            CallStackContext::TraceFailure(v84, "MkvMfSourceLib::MkvMfStream::TransformSample", 394, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      v85 = v141;
      v86 = v140;
      v87 = (DWORD *)((char *)this + 440);
      if ( !*((_DWORD *)this + 110) )
      {
        v88 = 2LL * v140;
        if ( v88 > 0xFFFFFFFF )
        {
          *v87 = -1;
          v108 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79, v80, v81);
            CallStackTracing::s_wpInstance = v109;
            if ( v109
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
            {
              v108 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v108 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          v6 = -2147024362;
          if ( *((_BYTE *)v108 + 8) )
          {
            v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
            if ( *((_DWORD *)v110 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v110, "MkvMfSourceLib::MkvMfStream::TransformSample", 401, -2147024362);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              -2147024362);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          if ( !v152 )
            inflateEnd(&v145);
          return (unsigned int)v6;
        }
        *v87 = v88;
        if ( (unsigned __int8)byte_1800D78D3 >= 4u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            48,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            v88);
      }
      v145 = v85;
      v146 = v86;
      do
      {
        ppBuffer = 0;
        v6 = MFCreateMemoryBuffer(*v87, &ppBuffer);
        if ( v6 < 0 )
        {
          v127 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v128 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
            CallStackTracing::s_wpInstance = v128;
            if ( v128
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v128 + 8LL))(v128, 2032) )
            {
              v127 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v127 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v127 + 8) )
          {
            v129 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v127);
            if ( *((_DWORD *)v129 + 499) != v6 )
              CallStackContext::TraceFailure(v129, "MkvMfSourceLib::MkvMfStream::TransformSample", 412, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          if ( !v152 )
            inflateEnd(&v145);
          return (unsigned int)v6;
        }
        CSmartMFBufferLock::CSmartMFBufferLock((CSmartMFBufferLock *)v142, ppBuffer);
        v6 = CSmartMFBufferLock::Lock((CSmartMFBufferLock *)v142);
        if ( v6 < 0 )
        {
          v124 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v125 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v92, v93, v94);
            CallStackTracing::s_wpInstance = v125;
            if ( v125
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v125 + 8LL))(v125, 2032) )
            {
              v124 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v124 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v124 + 8) )
          {
            v126 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v124);
            if ( *((_DWORD *)v126 + 499) != v6 )
              CallStackContext::TraceFailure(v126, "MkvMfSourceLib::MkvMfStream::TransformSample", 415, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v142);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          if ( !v152 )
            inflateEnd(&v145);
          return (unsigned int)v6;
        }
        v95 = v143;
        v147 = v144;
        v148 = v143;
        v96 = inflate(&v145, 0);
        v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
               ppBuffer,
               (unsigned int)(v95 - v148));
        if ( v6 < 0 )
        {
          v121 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v122 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v97, v98, v99);
            CallStackTracing::s_wpInstance = v122;
            if ( v122
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v122 + 8LL))(v122, 2032) )
            {
              v121 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v121 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v121 + 8) )
          {
            v123 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v121);
            if ( *((_DWORD *)v123 + 499) != v6 )
              CallStackContext::TraceFailure(v123, "MkvMfSourceLib::MkvMfStream::TransformSample", 424, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v142);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          if ( !v152 )
            inflateEnd(&v145);
          return (unsigned int)v6;
        }
        v6 = ((__int64 (__fastcall *)(_QWORD, IMFMediaBuffer *))(*a2)->lpVtbl->AddBuffer)(*a2, ppBuffer);
        if ( v6 < 0 )
        {
          v118 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v119 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v100, v101, v102);
            CallStackTracing::s_wpInstance = v119;
            if ( v119
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v119 + 8LL))(v119, 2032) )
            {
              v118 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v118 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v118 + 8) )
          {
            v120 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v118);
            if ( *((_DWORD *)v120 + 499) != v6 )
              CallStackContext::TraceFailure(v120, "MkvMfSourceLib::MkvMfStream::TransformSample", 425, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v142);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          if ( !v152 )
            inflateEnd(&v145);
          return (unsigned int)v6;
        }
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v142);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
      }
      while ( !v96 );
      inflateEnd(&v145);
      v152 = 1;
      v138 = 0;
      v6 = ((__int64 (__fastcall *)(_QWORD, __int64 *))(*a2)->lpVtbl->ConvertToContiguousBuffer)(*a2, &v138);
      if ( v6 < 0 )
      {
        v106 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v107 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v103, v104, v105);
          CallStackTracing::s_wpInstance = v107;
          if ( v107 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v107 + 8LL))(v107, 2032) )
          {
            v106 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v106 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v106 + 8) )
        {
          v111 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v106);
          if ( *((_DWORD *)v111 + 499) != v6 )
            CallStackContext::TraceFailure(v111, "MkvMfSourceLib::MkvMfStream::TransformSample", 437, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v138 + 40LL))(v138, (char *)this + 440);
      if ( v6 < 0 )
      {
        v115 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
          CallStackTracing::s_wpInstance = v116;
          if ( v116 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(v116, 2032) )
          {
            v115 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v115 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v115 + 8) )
        {
          v117 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v115);
          if ( *((_DWORD *)v117 + 499) != v6 )
            CallStackContext::TraceFailure(v117, "MkvMfSourceLib::MkvMfStream::TransformSample", 438, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        if ( !v152 )
          inflateEnd(&v145);
        return (unsigned int)v6;
      }
      if ( (unsigned __int8)byte_1800D78D3 >= 4u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 55, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, *v87);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
      CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v139);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v153);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
      if ( !v152 )
        inflateEnd(&v145);
    }
    return 0;
  }
  v5 = (_QWORD *)((char *)this + 320);
  if ( *((_QWORD *)this + 40) )
  {
LABEL_56:
    v153 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v152,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      362);
    v10 = ((__int64 (__fastcall *)(_QWORD, void **))(*a2)->lpVtbl->ConvertToContiguousBuffer)(*a2, &v153);
    if ( v10 < 0 )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != v10 )
          CallStackContext::TraceFailure(v39, "MkvMfSourceLib::MkvMfStream::TransformSample", 362, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_68;
      v40 = 39;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v10);
LABEL_68:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v153);
      return (unsigned int)v10;
    }
    v10 = ((__int64 (__fastcall *)(_QWORD))(*a2)->lpVtbl->RemoveAllBuffers)(*a2);
    if ( v10 < 0 )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v10 )
          CallStackContext::TraceFailure(v46, "MkvMfSourceLib::MkvMfStream::TransformSample", 363, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_68;
      v40 = 40;
      goto LABEL_67;
    }
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*a2)->lpVtbl->AddBuffer)(*a2, *v5);
    if ( v6 < 0 )
    {
      v50 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v6 )
          CallStackContext::TraceFailure(v52, "MkvMfSourceLib::MkvMfStream::TransformSample", 364, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_92;
      v53 = 41;
LABEL_91:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
LABEL_92:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v153);
      return (unsigned int)v6;
    }
    v6 = ((__int64 (__fastcall *)(_QWORD, void *))(*a2)->lpVtbl->AddBuffer)(*a2, v153);
    if ( v6 < 0 )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != v6 )
          CallStackContext::TraceFailure(v59, "MkvMfSourceLib::MkvMfStream::TransformSample", 365, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_92;
      v53 = 42;
      goto LABEL_91;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v153);
    return 0;
  }
  if ( *(__int64 *)(v4 + 16) <= 0xFFFFFFFFLL )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v152,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      349);
    v10 = MFCreateMemoryBuffer(*(_DWORD *)(*((_QWORD *)this + 39) + 16LL), (IMFMediaBuffer **)this + 40);
    if ( v10 < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v10 )
          CallStackContext::TraceFailure(v13, "MkvMfSourceLib::MkvMfStream::TransformSample", 349, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v14 = 35;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v10);
LABEL_20:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
      return (unsigned int)v10;
    }
    v153 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD, _QWORD))(*(_QWORD *)*v5 + 24LL))(*v5, &v153, 0, 0);
    if ( v10 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v10 )
          CallStackContext::TraceFailure(v21, "MkvMfSourceLib::MkvMfStream::TransformSample", 352, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v14 = 36;
      goto LABEL_19;
    }
    memcpy_0(v153, *(const void **)(*((_QWORD *)this + 39) + 8LL), *(unsigned int *)(*((_QWORD *)this + 39) + 16LL));
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v5 + 48LL))(
            *v5,
            *(unsigned int *)(*((_QWORD *)this + 39) + 16LL));
    if ( v10 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v10 )
          CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfStream::TransformSample", 354, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v14 = 37;
      goto LABEL_19;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
    if ( v10 < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != v10 )
          CallStackContext::TraceFailure(v33, "MkvMfSourceLib::MkvMfStream::TransformSample", 355, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v14 = 38;
      goto LABEL_19;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v152);
    if ( !*v5 )
      return 0;
    goto LABEL_56;
  }
  v6 = -1072875829;
  MkvSourceTelemetryLogger::SetFailed(
    *((_QWORD *)this + 52),
    3222091467LL,
    0,
    "MkvMfSourceLib::MkvMfStream::TransformSample",
    "m_pFrameCompression->settings_len > DWORD_MAX");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026ac0  mov     [rsp-8+arg_0], rbx
0x180026ac5  push    rbp
0x180026ac6  push    rsi
0x180026ac7  push    rdi
0x180026ac8  push    r12
0x180026aca  push    r13
0x180026acc  push    r14
0x180026ace  push    r15
0x180026ad0  lea     rbp, [rsp-27h]
0x180026ad5  sub     rsp, 100h
0x180026adc  mov     r14, rdx
0x180026adf  mov     rsi, rcx
0x180026ae2  xor     r13d, r13d
0x180026ae5  test    rdx, rdx
0x180026ae8  jz      loc_180027DE6
0x180026aee  cmp     [rdx], r13
0x180026af1  jz      loc_180027DE6
0x180026af7  mov     rcx, [rcx+138h]
0x180026afe  test    rcx, rcx
0x180026b01  jz      loc_1800271A9
0x180026b07  mov     eax, [rcx]
0x180026b09  cmp     eax, 3
0x180026b0c  jnz     loc_1800271B0
0x180026b12  lea     rbx, [rsi+140h]
0x180026b19  lea     rdi, aMkvmfsourcelib_58; "MkvMfSourceLib::MkvMfStream::TransformS"...
0x180026b20  cmp     [rbx], r13
0x180026b23  jnz     loc_180026E77
0x180026b29  mov     eax, 0FFFFFFFFh
0x180026b2e  cmp     [rcx+10h], rax
0x180026b32  jle     short loc_180026B5E
0x180026b34  lea     rax, aMPframecompres; "m_pFrameCompression->settings_len > DWO"...
0x180026b3b  mov     [rsp+130h+var_110], rax
0x180026b40  mov     r9, rdi
0x180026b43  xor     r8d, r8d
0x180026b46  mov     ebx, 0C00D36CBh
0x180026b4b  mov     edx, ebx
0x180026b4d  mov     rcx, [rsi+1A0h]
0x180026b54  call    ?SetFailed@MkvSourceTelemetryLogger@@UEAAJJ_JPEIADPEBD@Z; MkvSourceTelemetryLogger::SetFailed(long,__int64,char restrict *,char const *)
0x180026b59  jmp     loc_180027EAF
0x180026b5e  mov     r12d, 15Dh
0x180026b64  mov     r8d, r12d; int
0x180026b67  mov     rdx, rdi; char *
0x180026b6a  lea     rcx, [rbp+57h+arg_8]; this
0x180026b6e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180026b73  nop
0x180026b74  mov     rcx, [rsi+138h]
0x180026b7b  mov     rdx, rbx; ppBuffer
0x180026b7e  mov     ecx, [rcx+10h]; cbMaxLength
0x180026b81  call    cs:__imp_MFCreateMemoryBuffer
0x180026b87  mov     r15d, eax
0x180026b8a  test    eax, eax
0x180026b8c  jns     loc_180026C43
0x180026b92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b99  test    rcx, rcx
0x180026b9c  jnz     short loc_180026BDF
0x180026b9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026ba4  mov     rcx, rax
0x180026ba7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026bae  test    rax, rax
0x180026bb1  jz      short loc_180026BD1
0x180026bb3  mov     rax, [rax]
0x180026bb6  mov     edx, 7F0h
0x180026bbb  mov     rax, [rax+8]
0x180026bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bc4  test    eax, eax
0x180026bc6  jz      short loc_180026BD1
0x180026bc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026bcf  jmp     short loc_180026BDF
0x180026bd1  lea     rcx, qword_1800D6F70; this
0x180026bd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026bdf  cmp     [rcx+8], r13b
0x180026be3  jz      short loc_180026C04
0x180026be5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026bea  cmp     [rax+7CCh], r15d
0x180026bf1  jz      short loc_180026C04
0x180026bf3  mov     r9d, r15d; int
0x180026bf6  mov     r8d, r12d; int
0x180026bf9  mov     rdx, rdi; char *
0x180026bfc  mov     rcx, rax; this
0x180026bff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026c04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026c0b  jb      short loc_180026C32
0x180026c0d  mov     edx, 23h ; '#'
0x180026c12  mov     dword ptr [rsp+130h+var_110], r15d
0x180026c17  mov     r9, rsi
0x180026c1a  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180026c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c28  mov     rcx, [rcx+10h]
0x180026c2c  call    WPP_SF_qD
0x180026c31  nop
0x180026c32  lea     rcx, [rbp+57h+arg_8]; this
0x180026c36  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026c3b  mov     eax, r15d
0x180026c3e  jmp     loc_180027EB1
0x180026c43  mov     [rbp+57h+arg_18], r13
0x180026c47  mov     rcx, [rbx]
0x180026c4a  mov     rax, [rcx]
0x180026c4d  xor     r9d, r9d
0x180026c50  xor     r8d, r8d
0x180026c53  lea     rdx, [rbp+57h+arg_18]
0x180026c57  mov     rax, [rax+18h]
0x180026c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c60  mov     r15d, eax
0x180026c63  test    eax, eax
0x180026c65  jns     loc_180026CF7
0x180026c6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026c72  test    rcx, rcx
0x180026c75  jnz     short loc_180026CB8
0x180026c77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026c7d  mov     rcx, rax
0x180026c80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026c87  test    rax, rax
0x180026c8a  jz      short loc_180026CAA
0x180026c8c  mov     rax, [rax]
0x180026c8f  mov     edx, 7F0h
0x180026c94  mov     rax, [rax+8]
0x180026c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c9d  test    eax, eax
0x180026c9f  jz      short loc_180026CAA
0x180026ca1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ca8  jmp     short loc_180026CB8
0x180026caa  lea     rcx, qword_1800D6F70; this
0x180026cb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026cb8  cmp     [rcx+8], r13b
0x180026cbc  jz      short loc_180026CE0
0x180026cbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026cc3  cmp     [rax+7CCh], r15d
0x180026cca  jz      short loc_180026CE0
0x180026ccc  mov     r9d, r15d; int
0x180026ccf  mov     r8d, 160h; int
0x180026cd5  mov     rdx, rdi; char *
0x180026cd8  mov     rcx, rax; this
0x180026cdb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026ce0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026ce7  jb      loc_180026C32
0x180026ced  mov     edx, 24h ; '$'
0x180026cf2  jmp     loc_180026C12
0x180026cf7  mov     rdx, [rsi+138h]
0x180026cfe  mov     r8d, [rdx+10h]; Size
0x180026d02  mov     rdx, [rdx+8]; Src
0x180026d06  mov     rcx, [rbp+57h+arg_18]; void *
0x180026d0a  call    memcpy_0
0x180026d0f  mov     rcx, [rbx]
0x180026d12  mov     rax, [rcx]
0x180026d15  mov     rdx, [rsi+138h]
0x180026d1c  mov     edx, [rdx+10h]
0x180026d1f  mov     rax, [rax+30h]
0x180026d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d28  mov     r15d, eax
0x180026d2b  test    eax, eax
0x180026d2d  jns     loc_180026DBF
0x180026d33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d3a  test    rcx, rcx
0x180026d3d  jnz     short loc_180026D80
0x180026d3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026d45  mov     rcx, rax
0x180026d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d4f  test    rax, rax
0x180026d52  jz      short loc_180026D72
0x180026d54  mov     rax, [rax]
0x180026d57  mov     edx, 7F0h
0x180026d5c  mov     rax, [rax+8]
0x180026d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d65  test    eax, eax
0x180026d67  jz      short loc_180026D72
0x180026d69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d70  jmp     short loc_180026D80
0x180026d72  lea     rcx, qword_1800D6F70; this
0x180026d79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d80  cmp     [rcx+8], r13b
0x180026d84  jz      short loc_180026DA8
0x180026d86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026d8b  cmp     [rax+7CCh], r15d
0x180026d92  jz      short loc_180026DA8
0x180026d94  mov     r9d, r15d; int
0x180026d97  mov     r8d, 162h; int
0x180026d9d  mov     rdx, rdi; char *
0x180026da0  mov     rcx, rax; this
0x180026da3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026da8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026daf  jb      loc_180026C32
0x180026db5  mov     edx, 25h ; '%'
0x180026dba  jmp     loc_180026C12
0x180026dbf  mov     rcx, [rbx]
0x180026dc2  mov     rax, [rcx]
0x180026dc5  mov     rax, [rax+20h]
0x180026dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dce  mov     r15d, eax
0x180026dd1  test    eax, eax
0x180026dd3  jns     loc_180026E65
0x180026dd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026de0  test    rcx, rcx
0x180026de3  jnz     short loc_180026E26
0x180026de5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026deb  mov     rcx, rax
0x180026dee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026df5  test    rax, rax
0x180026df8  jz      short loc_180026E18
0x180026dfa  mov     rax, [rax]
0x180026dfd  mov     edx, 7F0h
0x180026e02  mov     rax, [rax+8]
0x180026e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e0b  test    eax, eax
0x180026e0d  jz      short loc_180026E18
0x180026e0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026e16  jmp     short loc_180026E26
0x180026e18  lea     rcx, qword_1800D6F70; this
0x180026e1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026e26  cmp     [rcx+8], r13b
0x180026e2a  jz      short loc_180026E4E
0x180026e2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026e31  cmp     [rax+7CCh], r15d
0x180026e38  jz      short loc_180026E4E
0x180026e3a  mov     r9d, r15d; int
0x180026e3d  mov     r8d, 163h; int
0x180026e43  mov     rdx, rdi; char *
0x180026e46  mov     rcx, rax; this
0x180026e49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026e4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026e55  jb      loc_180026C32
0x180026e5b  mov     edx, 26h ; '&'
0x180026e60  jmp     loc_180026C12
0x180026e65  lea     rcx, [rbp+57h+arg_8]; this
0x180026e69  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026e6e  cmp     [rbx], r13
0x180026e71  jz      loc_1800271A9
0x180026e77  mov     [rbp+57h+arg_18], r13
0x180026e7b  mov     r12d, 16Ah
0x180026e81  mov     r8d, r12d; int
0x180026e84  mov     rdx, rdi; char *
0x180026e87  lea     rcx, [rbp+57h+arg_8]; this
0x180026e8b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180026e90  nop
0x180026e91  mov     rcx, [r14]
0x180026e94  mov     rax, [rcx]
0x180026e97  lea     rdx, [rbp+57h+arg_18]
0x180026e9b  mov     rax, [rax+148h]
0x180026ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea7  mov     r15d, eax
0x180026eaa  test    eax, eax
0x180026eac  jns     loc_180026F6A
0x180026eb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026eb9  test    rcx, rcx
0x180026ebc  jnz     short loc_180026EFF
0x180026ebe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026ec4  mov     rcx, rax
0x180026ec7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ece  test    rax, rax
0x180026ed1  jz      short loc_180026EF1
0x180026ed3  mov     rax, [rax]
0x180026ed6  mov     edx, 7F0h
0x180026edb  mov     rax, [rax+8]
0x180026edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ee4  test    eax, eax
0x180026ee6  jz      short loc_180026EF1
0x180026ee8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026eef  jmp     short loc_180026EFF
0x180026ef1  lea     rcx, qword_1800D6F70; this
0x180026ef8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026eff  cmp     [rcx+8], r13b
0x180026f03  jz      short loc_180026F24
0x180026f05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026f0a  cmp     [rax+7CCh], r15d
0x180026f11  jz      short loc_180026F24
0x180026f13  mov     r9d, r15d; int
0x180026f16  mov     r8d, r12d; int
0x180026f19  mov     rdx, rdi; char *
0x180026f1c  mov     rcx, rax; this
0x180026f1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026f24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026f2b  jb      short loc_180026F52
0x180026f2d  mov     edx, 27h ; '''
0x180026f32  mov     dword ptr [rsp+130h+var_110], r15d
0x180026f37  mov     r9, rsi
0x180026f3a  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180026f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f48  mov     rcx, [rcx+10h]
0x180026f4c  call    WPP_SF_qD
0x180026f51  nop
0x180026f52  lea     rcx, [rbp+57h+arg_8]; this
0x180026f56  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026f5b  nop
0x180026f5c  lea     rcx, [rbp+57h+arg_18]
0x180026f60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f65  jmp     loc_180026C3B
0x180026f6a  mov     rcx, [r14]
0x180026f6d  mov     rax, [rcx]
0x180026f70  mov     rax, [rax+160h]
0x180026f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f7c  mov     r15d, eax
0x180026f7f  test    eax, eax
0x180026f81  jns     loc_180027013
0x180026f87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026f8e  test    rcx, rcx
0x180026f91  jnz     short loc_180026FD4
0x180026f93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026f99  mov     rcx, rax
0x180026f9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026fa3  test    rax, rax
0x180026fa6  jz      short loc_180026FC6
  ... truncated ...
```
