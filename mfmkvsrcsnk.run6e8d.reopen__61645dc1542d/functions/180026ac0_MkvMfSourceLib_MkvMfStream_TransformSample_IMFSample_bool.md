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
  HRESULT v7; // r15d
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  int v36; // eax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // r12
  unsigned int v50; // ebx
  DWORD *v51; // r15
  unsigned __int64 v52; // rcx
  int v53; // ebx
  int v54; // r12d
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFMediaBuffer *v79; // [rsp+30h] [rbp-A9h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v81; // [rsp+40h] [rbp-99h] BYREF
  _BYTE v82[8]; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v83; // [rsp+50h] [rbp-89h]
  __int64 v84; // [rsp+58h] [rbp-81h]
  _BYTE v85[8]; // [rsp+60h] [rbp-79h] BYREF
  int v86; // [rsp+68h] [rbp-71h]
  __int64 v87; // [rsp+70h] [rbp-69h]
  __int64 v88; // [rsp+80h] [rbp-59h] BYREF
  unsigned int v89; // [rsp+88h] [rbp-51h]
  __int64 v90; // [rsp+90h] [rbp-49h]
  int v91; // [rsp+98h] [rbp-41h]
  char *v92; // [rsp+E0h] [rbp+7h]
  __int64 *v93; // [rsp+E8h] [rbp+Fh]
  char v94; // [rsp+F0h] [rbp+17h]
  char v95; // [rsp+148h] [rbp+6Fh] BYREF
  void *v96; // [rsp+158h] [rbp+7Fh] BYREF

  if ( !a2 || !*a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v95,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      332);
    v76 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
    v6 = -2147467261;
    if ( *((_BYTE *)v76 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
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
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
    return (unsigned int)v6;
  }
  v4 = *((_QWORD *)this + 39);
  if ( !v4 )
    return 0;
  if ( *(_DWORD *)v4 != 3 )
  {
    if ( !*(_DWORD *)v4 )
    {
      memset_0(&v88, 0, 0x58u);
      v95 = 0;
      v36 = inflateInit2_(&v88);
      v92 = &v95;
      v93 = &v88;
      v94 = 1;
      if ( v36 )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v96,
          "MkvMfSourceLib::MkvMfStream::TransformSample",
          386);
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
        v6 = -2147220907;
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != -2147220907 )
            CallStackContext::TraceFailure(v39, "MkvMfSourceLib::MkvMfStream::TransformSample", 386, -2147220907);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147220907);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      v79 = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v96,
        "MkvMfSourceLib::MkvMfStream::TransformSample",
        390);
      v6 = ((__int64 (__fastcall *)(_QWORD, struct IMFMediaBuffer **))(*a2)->lpVtbl->ConvertToContiguousBuffer)(
             *a2,
             &v79);
      if ( v6 < 0 )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != v6 )
            CallStackContext::TraceFailure(v42, "MkvMfSourceLib::MkvMfStream::TransformSample", 390, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      v6 = ((__int64 (__fastcall *)(_QWORD))(*a2)->lpVtbl->RemoveAllBuffers)(*a2);
      if ( v6 < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != v6 )
            CallStackContext::TraceFailure(v45, "MkvMfSourceLib::MkvMfStream::TransformSample", 391, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      CSmartMFBufferLock::CSmartMFBufferLock((CSmartMFBufferLock *)v82, v79);
      v6 = CSmartMFBufferLock::Lock((CSmartMFBufferLock *)v82);
      if ( v6 < 0 )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != v6 )
            CallStackContext::TraceFailure(v48, "MkvMfSourceLib::MkvMfStream::TransformSample", 394, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      v49 = v84;
      v50 = v83;
      v51 = (DWORD *)((char *)this + 440);
      if ( !*((_DWORD *)this + 110) )
      {
        v52 = 2LL * v83;
        if ( v52 > 0xFFFFFFFF )
        {
          *v51 = -1;
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          v6 = -2147024362;
          if ( *((_BYTE *)v57 + 8) )
          {
            v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
            if ( *((_DWORD *)v59 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v59, "MkvMfSourceLib::MkvMfStream::TransformSample", 401, -2147024362);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              -2147024362);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          if ( !v95 )
            inflateEnd(&v88);
          return (unsigned int)v6;
        }
        *v51 = v52;
        if ( (unsigned __int8)byte_1800D78D3 >= 4u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            48,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            v52);
      }
      v88 = v49;
      v89 = v50;
      do
      {
        ppBuffer = 0;
        v6 = MFCreateMemoryBuffer(*v51, &ppBuffer);
        if ( v6 < 0 )
        {
          v73 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v74;
            if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
            {
              v73 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v73 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v73 + 8) )
          {
            v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
            if ( *((_DWORD *)v75 + 499) != v6 )
              CallStackContext::TraceFailure(v75, "MkvMfSourceLib::MkvMfStream::TransformSample", 412, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          if ( !v95 )
            inflateEnd(&v88);
          return (unsigned int)v6;
        }
        CSmartMFBufferLock::CSmartMFBufferLock((CSmartMFBufferLock *)v85, ppBuffer);
        v6 = CSmartMFBufferLock::Lock((CSmartMFBufferLock *)v85);
        if ( v6 < 0 )
        {
          v70 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
              CallStackContext::TraceFailure(v72, "MkvMfSourceLib::MkvMfStream::TransformSample", 415, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v85);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          if ( !v95 )
            inflateEnd(&v88);
          return (unsigned int)v6;
        }
        v53 = v86;
        v90 = v87;
        v91 = v86;
        v54 = inflate(&v88, 0);
        v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
               ppBuffer,
               (unsigned int)(v53 - v91));
        if ( v6 < 0 )
        {
          v67 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v68;
            if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
            {
              v67 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v67 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v67 + 8) )
          {
            v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
            if ( *((_DWORD *)v69 + 499) != v6 )
              CallStackContext::TraceFailure(v69, "MkvMfSourceLib::MkvMfStream::TransformSample", 424, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v85);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          if ( !v95 )
            inflateEnd(&v88);
          return (unsigned int)v6;
        }
        v6 = ((__int64 (__fastcall *)(_QWORD, IMFMediaBuffer *))(*a2)->lpVtbl->AddBuffer)(*a2, ppBuffer);
        if ( v6 < 0 )
        {
          v64 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          if ( *((_BYTE *)v64 + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
            if ( *((_DWORD *)v66 + 499) != v6 )
              CallStackContext::TraceFailure(v66, "MkvMfSourceLib::MkvMfStream::TransformSample", 425, v6);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
              this,
              v6);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v85);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          if ( !v95 )
            inflateEnd(&v88);
          return (unsigned int)v6;
        }
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v85);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
      }
      while ( !v54 );
      inflateEnd(&v88);
      v95 = 1;
      v81 = 0;
      v6 = ((__int64 (__fastcall *)(_QWORD, __int64 *))(*a2)->lpVtbl->ConvertToContiguousBuffer)(*a2, &v81);
      if ( v6 < 0 )
      {
        v55 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          {
            v55 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v55 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v55 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v60 + 499) != v6 )
            CallStackContext::TraceFailure(v60, "MkvMfSourceLib::MkvMfStream::TransformSample", 437, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v81 + 40LL))(v81, (char *)this + 440);
      if ( v6 < 0 )
      {
        v61 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
          if ( *((_DWORD *)v63 + 499) != v6 )
            CallStackContext::TraceFailure(v63, "MkvMfSourceLib::MkvMfStream::TransformSample", 438, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
        CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        if ( !v95 )
          inflateEnd(&v88);
        return (unsigned int)v6;
      }
      if ( (unsigned __int8)byte_1800D78D3 >= 4u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 55, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, *v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v82);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      if ( !v95 )
        inflateEnd(&v88);
    }
    return 0;
  }
  v5 = (_QWORD *)((char *)this + 320);
  if ( *((_QWORD *)this + 40) )
  {
LABEL_56:
    v96 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v95,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      362);
    v7 = ((__int64 (__fastcall *)(_QWORD, void **))(*a2)->lpVtbl->ConvertToContiguousBuffer)(*a2, &v96);
    if ( v7 < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != v7 )
          CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfStream::TransformSample", 362, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_68;
      v25 = 39;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v7);
LABEL_68:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      return (unsigned int)v7;
    }
    v7 = ((__int64 (__fastcall *)(_QWORD))(*a2)->lpVtbl->RemoveAllBuffers)(*a2);
    if ( v7 < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v7 )
          CallStackContext::TraceFailure(v28, "MkvMfSourceLib::MkvMfStream::TransformSample", 363, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_68;
      v25 = 40;
      goto LABEL_67;
    }
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*a2)->lpVtbl->AddBuffer)(*a2, *v5);
    if ( v6 < 0 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != v6 )
          CallStackContext::TraceFailure(v31, "MkvMfSourceLib::MkvMfStream::TransformSample", 364, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_92;
      v32 = 41;
LABEL_91:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v6);
LABEL_92:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      return (unsigned int)v6;
    }
    v6 = ((__int64 (__fastcall *)(_QWORD, void *))(*a2)->lpVtbl->AddBuffer)(*a2, v96);
    if ( v6 < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != v6 )
          CallStackContext::TraceFailure(v35, "MkvMfSourceLib::MkvMfStream::TransformSample", 365, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_92;
      v32 = 42;
      goto LABEL_91;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    return 0;
  }
  if ( *(__int64 *)(v4 + 16) <= 0xFFFFFFFFLL )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v95,
      "MkvMfSourceLib::MkvMfStream::TransformSample",
      349);
    v7 = MFCreateMemoryBuffer(*(_DWORD *)(*((_QWORD *)this + 39) + 16LL), (IMFMediaBuffer **)this + 40);
    if ( v7 < 0 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v7 )
          CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfStream::TransformSample", 349, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 35;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v7);
LABEL_20:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
      return (unsigned int)v7;
    }
    v96 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD, _QWORD))(*(_QWORD *)*v5 + 24LL))(*v5, &v96, 0, 0);
    if ( v7 < 0 )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v7 )
          CallStackContext::TraceFailure(v15, "MkvMfSourceLib::MkvMfStream::TransformSample", 352, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 36;
      goto LABEL_19;
    }
    memcpy_0(v96, *(const void **)(*((_QWORD *)this + 39) + 8LL), *(unsigned int *)(*((_QWORD *)this + 39) + 16LL));
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v5 + 48LL))(
           *v5,
           *(unsigned int *)(*((_QWORD *)this + 39) + 16LL));
    if ( v7 < 0 )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v7 )
          CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfStream::TransformSample", 354, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 37;
      goto LABEL_19;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
    if ( v7 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
        if ( *((_DWORD *)v21 + 499) != v7 )
          CallStackContext::TraceFailure(v21, "MkvMfSourceLib::MkvMfStream::TransformSample", 355, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 38;
      goto LABEL_19;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v95);
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
