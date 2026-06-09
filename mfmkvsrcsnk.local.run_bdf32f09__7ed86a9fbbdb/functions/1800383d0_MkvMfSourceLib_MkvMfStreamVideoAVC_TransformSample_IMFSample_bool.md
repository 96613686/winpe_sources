# MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample(IMFSample * *,bool)

- ea: `0x1800383d0`
- end: `0x180039ebd`
- name: `?TransformSample@MkvMfStreamVideoAVC@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `6893`
- prototype: `__int64 __fastcall(const void **this, struct IMFSample **, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002e14`
- `0x1800036c5`
- `0x180005ab8`
- `0x180007dbc`
- `0x180008710`
- `0x180008d18`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d44`
- `0x180020d84`
- `0x180026ac0`
- `0x1800315c0`
- `0x180036ecc`
- `0x1800383d0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003844d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038562`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003866d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800387fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003891a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038d80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ea4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038fc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039112`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039220`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800393c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800394c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800395c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800398f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039a11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039b4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039dfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003844d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038562`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003866d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800387fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003891a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038d80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ea4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038fc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039112`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039220`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800393c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800394c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800395c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800398f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039a11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039b4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039dfa`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180038e88`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800398d8`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180038e88`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800398d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample(
        const void **this,
        struct IMFSample **a2,
        bool a3)
{
  unsigned int v5; // r15d
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct IMFSample *v27; // rcx
  const char *v28; // r9
  __int64 result; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  struct IMFSample *v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct IMFSample *v40; // rcx
  unsigned int v41; // r13d
  __int64 size_of; // rax
  __int64 v43; // rbx
  unsigned int v44; // ebx
  __int64 v45; // r9
  const void *v46; // rdx
  int NextNALUnitLength; // ebx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rcx
  DWORD v54; // r12d
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  struct IMFSample *v58; // rdx
  struct IMFSample *v59; // rcx
  __int64 v60; // rdx
  HRESULT v61; // ebx
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
  __int64 v85; // rcx
  int v86; // ebx
  __int64 *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  struct IMFSample *v90; // rcx
  unsigned int v91; // ebx
  unsigned int v92; // eax
  unsigned int v93; // ecx
  unsigned int v94; // r13d
  __int64 v95; // rdx
  __int64 *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  __int64 *v99; // rcx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  struct IMFSample *v102; // rdx
  __int64 *v103; // rcx
  CallStackTracing *v104; // rax
  struct CallStackContext *v105; // rax
  __int64 *v106; // rcx
  CallStackTracing *v107; // rax
  struct CallStackContext *v108; // rax
  __int64 *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  struct IMFSample *v112; // rcx
  bool v113; // cf
  __int64 v114; // rdx
  __int64 v115; // r8
  __int64 v116; // r9
  __int64 *v117; // rcx
  CallStackTracing *v118; // rax
  struct CallStackContext *v119; // rax
  __int64 v120; // rdx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 *v123; // rcx
  CallStackTracing *v124; // rax
  struct CallStackContext *v125; // rax
  struct IMFSample *v126; // rcx
  __int64 v127; // rdx
  __int64 v128; // r8
  __int64 v129; // r9
  __int64 *v130; // rcx
  CallStackTracing *v131; // rax
  struct CallStackContext *v132; // rax
  struct IMFSample *v133; // rcx
  __int64 v134; // rdx
  int v135; // ebx
  __int64 v136; // r8
  __int64 v137; // r9
  __int64 *v138; // rcx
  CallStackTracing *v139; // rax
  struct CallStackContext *v140; // rax
  struct IMFSample *v141; // rcx
  struct IMFSample *v142; // rcx
  __int64 v143; // rdx
  __int64 v144; // r8
  __int64 v145; // r9
  __int64 *v146; // rcx
  CallStackTracing *v147; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFSample *v149; // [rsp+30h] [rbp-B8h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v151; // [rsp+40h] [rbp-A8h] BYREF
  DWORD v152; // [rsp+44h] [rbp-A4h]
  __int128 v153; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v154; // [rsp+58h] [rbp-90h]
  unsigned int v155; // [rsp+60h] [rbp-88h]
  _BYTE v156[12]; // [rsp+64h] [rbp-84h] BYREF
  char v157; // [rsp+70h] [rbp-78h]
  DWORD dwLength; // [rsp+78h] [rbp-70h] BYREF
  const unsigned __int8 *v159; // [rsp+80h] [rbp-68h] BYREF
  _QWORD v160[3]; // [rsp+88h] [rbp-60h] BYREF
  char v161; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  struct IMFSample **v163; // [rsp+F8h] [rbp+10h] BYREF
  bool v164; // [rsp+100h] [rbp+18h]
  __int64 v165; // [rsp+108h] [rbp+20h] BYREF

  v164 = a3;
  v163 = a2;
  v5 = 0;
  if ( !a2 || !*a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v165,
      "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
      621);
    v146 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v147 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v143, v144, v145);
      CallStackTracing::s_wpInstance = v147;
      if ( v147 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v147 + 8LL))(v147, 2032) )
      {
        v146 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v146 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v146 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v146);
      v10 = -2147467261;
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
          621,
          -2147467261);
    }
    else
    {
      v10 = -2147467261;
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
        this,
        -2147467261);
    goto LABEL_292;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v165,
    "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
    624);
  v6 = MkvMfSourceLib::MkvMfStream::TransformSample((MkvMfSourceLib::MkvMfStream *)this, v163, a3);
  v10 = v6;
  if ( v6 < 0 )
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
        CallStackContext::TraceFailure(v13, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 624, v10);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v10);
LABEL_292:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
    return v10;
  }
  try
  {
    v149 = 0;
    v149 = *v163;
    v160[1] = &v163;
    v160[2] = &v149;
    v161 = 1;
    pBuffer = 0;
    v159 = 0;
    v151 = 0;
    v15 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer **))v149->lpVtbl->ConvertToContiguousBuffer)(
            v149,
            &pBuffer);
    if ( v15 < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v15 )
          CallStackContext::TraceFailure(v20, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 640, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v15);
LABEL_67:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
      v40 = v149;
      v149 = 0;
      *v163 = v40;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
      return (unsigned int)v15;
    }
    v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, const unsigned __int8 **, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
            pBuffer,
            &v159,
            0,
            &v151);
    if ( v15 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v15 )
          CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 641, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v15);
      goto LABEL_67;
    }
    if ( !*((_DWORD *)this + 114) )
    {
      *(_QWORD *)&v156[4] = &pBuffer;
      v157 = 1;
      if ( v151 >= 4 && *(_DWORD *)v159 == (_DWORD)MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode )
      {
        ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v27 = v149;
        v149 = 0;
        *v163 = v27;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 0;
      }
      else
      {
        if ( (unsigned __int8)byte_1800D78D3 >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 89, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this);
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != -1072875845 )
            CallStackContext::TraceFailure(
              v32,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              654,
              -1072875845);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            90,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -1072875845);
        ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v33 = v149;
        v149 = 0;
        *v163 = v33;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 3222091451LL;
      }
    }
    v15 = ((__int64 (__fastcall *)(struct IMFSample *))v149->lpVtbl->RemoveAllBuffers)(v149);
    if ( v15 < 0 )
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
        if ( *((_DWORD *)v39 + 499) != v15 )
          CallStackContext::TraceFailure(v39, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 660, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v15);
      goto LABEL_67;
    }
    v155 = *((_DWORD *)this + 114);
    v41 = v151;
    v153 = 0;
    v154 = 0;
    size_of = std::_Get_size_of_n<4>(512);
    *(_QWORD *)&v153 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v43 = v153 + 2048;
    v154 = v153 + 2048;
    memset_0((void *)v153, 0, 0x800u);
    *((_QWORD *)&v153 + 1) = v43;
    v165 = 0;
    std::_Tidy_guard<std::vector<unsigned long>>::~_Tidy_guard<std::vector<unsigned long>>(&v165);
    v44 = 0;
    LODWORD(v165) = 0;
    *(_DWORD *)v156 = 0;
    v152 = 0;
    LODWORD(v45) = v155;
    while ( 1 )
    {
      if ( v5 >= v151 )
      {
        if ( (_DWORD)v45 == 4 )
        {
          *(_DWORD *)&v156[8] = 0;
          v113 = *(_DWORD *)v156 != 0;
          *(_QWORD *)v156 = (unsigned int)-*(_DWORD *)v156;
          v61 = MFCreateMediaBufferWrapper(
                  pBuffer,
                  v113 ? v152 : 0,
                  v151 - (v113 ? v152 : 0),
                  (IMFMediaBuffer **)&v156[4]);
          if ( v61 < 0 )
          {
            v117 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v118 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v114, v115, v116);
              CallStackTracing::s_wpInstance = v118;
              if ( v118
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v118 + 8LL))(v118, 2032) )
              {
                v117 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v117 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v117 + 8) )
            {
              v119 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v117);
              if ( *((_DWORD *)v119 + 499) != v61 )
                CallStackContext::TraceFailure(v119, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 738, v61);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                104,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v61);
            goto LABEL_254;
          }
          v61 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v149->lpVtbl->AddBuffer)(v149, *(_QWORD *)&v156[4]);
          if ( v61 < 0 )
          {
            v123 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v124 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v120, v121, v122);
              CallStackTracing::s_wpInstance = v124;
              if ( v124
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v124 + 8LL))(v124, 2032) )
              {
                v123 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v123 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v123 + 8) )
            {
              v125 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v123);
              if ( *((_DWORD *)v125 + 499) != v61 )
                CallStackContext::TraceFailure(v125, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 739, v61);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v61);
            goto LABEL_254;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v156[4]);
          v44 = v165;
        }
        NextNALUnitLength = ((__int64 (__fastcall *)(struct IMFSample *, const IID *, _QWORD, _QWORD))v149->lpVtbl->SetBlob)(
                              v149,
                              &MF_NALU_LENGTH_INFORMATION,
                              v153,
                              4 * v44);
        if ( NextNALUnitLength >= 0 )
        {
          v160[0] = 0;
          v135 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD *))v149->lpVtbl->ConvertToContiguousBuffer)(
                   v149,
                   v160);
          if ( v135 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v160);
            std::vector<bool>::~vector<bool>(&v153);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
            v142 = v149;
            v149 = 0;
            *v163 = v142;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
            return 0;
          }
          else
          {
            v138 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v139 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v134, v136, v137);
              CallStackTracing::s_wpInstance = v139;
              if ( v139
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v139 + 8LL))(v139, 2032) )
              {
                v138 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v138 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v138 + 8) )
            {
              v140 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v138);
              if ( *((_DWORD *)v140 + 499) != v135 )
                CallStackContext::TraceFailure(v140, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 745, v135);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                107,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v135);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v160);
            std::vector<bool>::~vector<bool>(&v153);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
            v141 = v149;
            v149 = 0;
            *v163 = v141;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
            return (unsigned int)v135;
          }
        }
        v130 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v131 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v127, v128, v129);
          CallStackTracing::s_wpInstance = v131;
          if ( v131 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v131 + 8LL))(v131, 2032) )
          {
            v130 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v130 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v130 + 8) )
        {
          v132 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v130);
          if ( *((_DWORD *)v132 + 499) != NextNALUnitLength )
            CallStackContext::TraceFailure(
              v132,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              742,
              NextNALUnitLength);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            NextNALUnitLength);
LABEL_267:
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v133 = v149;
        v149 = 0;
        *v163 = v133;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return (unsigned int)NextNALUnitLength;
      }
      dwLength = 0;
      NextNALUnitLength = MkvMfSourceLib::MkvMfStreamVideoAVC::GetNextNALUnitLength(
                            (MkvMfSourceLib::MkvMfStreamVideoAVC *)this,
                            &v159[v5],
                            v41,
                            &dwLength);
      if ( NextNALUnitLength < 0 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v49);
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
          if ( *((_DWORD *)v52 + 499) != NextNALUnitLength )
            CallStackContext::TraceFailure(
              v52,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              675,
              NextNALUnitLength);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            NextNALUnitLength);
        goto LABEL_267;
      }
      v53 = *((unsigned int *)this + 114);
      v54 = dwLength;
      if ( v5 + (_DWORD)v53 + dwLength > v151 )
      {
        v55 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v49);
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
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v57 + 499) != -1072875842 )
            CallStackContext::TraceFailure(
              v57,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              679,
              -1072875842);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -1072875842);
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v58 = v149;
        v149 = 0;
        *v163 = v58;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 3222091454LL;
      }
      if ( (_DWORD)v53 == 4 && dwLength == 1 )
      {
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v59 = v149;
        v149 = 0;
        *v163 = v59;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 0;
      }
      if ( !v5 && v159[v53] == 31 )
        goto LABEL_101;
      if ( v155 == 4 )
        goto LABEL_139;
      if ( !v5 )
      {
LABEL_101:
        *(_DWORD *)v156 = 1;
        v152 = dwLength;
      }
      *(_QWORD *)&v156[4] = 0;
      v61 = ((__int64 (__fastcall *)(struct IMFSample *, const void *))v149->lpVtbl->AddBuffer)(v149, this[63]);
      if ( v61 < 0 )
      {
        v64 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v62, v63);
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
          if ( *((_DWORD *)v66 + 499) != v61 )
            CallStackContext::TraceFailure(v66, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 698, v61);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v61);
LABEL_254:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v156[4]);
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v126 = v149;
        v149 = 0;
        *v163 = v126;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return (unsigned int)v61;
      }
      v61 = MFCreateMediaBufferWrapper(pBuffer, v5 + *((_DWORD *)this + 114), v54, (IMFMediaBuffer **)&v156[4]);
      if ( v61 < 0 )
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
          if ( *((_DWORD *)v72 + 499) != v61 )
            CallStackContext::TraceFailure(v72, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 699, v61);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v61);
        goto LABEL_254;
      }
      v61 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v149->lpVtbl->AddBuffer)(v149, *(_QWORD *)&v156[4]);
      if ( v61 < 0 )
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
          if ( *((_DWORD *)v78 + 499) != v61 )
            CallStackContext::TraceFailure(v78, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 700, v61);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v61);
        goto LABEL_254;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v156[4]);
LABEL_139:
      if ( !v5 && v164 && (v46 = this[62]) != 0 )
      {
        NextNALUnitLength = ((__int64 (__fastcall *)(struct IMFSample *))v149->lpVtbl->AddBuffer)(v149);
        if ( NextNALUnitLength < 0 )
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
            if ( *((_DWORD *)v84 + 499) != NextNALUnitLength )
              CallStackContext::TraceFailure(
                v84,
                "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
                706,
                NextNALUnitLength);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              97,
              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
              this,
              NextNALUnitLength);
          goto LABEL_267;
        }
        v85 = *((unsigned int *)this + 122);
        v86 = v165;
        if ( (unsigned int)(v85 + v165) >= 0x200 )
        {
          v87 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79, v80, v81);
            CallStackTracing::s_wpInstance = v88;
            if ( v88 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
            {
              v87 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v87 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v87 + 8) )
          {
            v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
            if ( *((_DWORD *)v89 + 499) != -1072875842 )
              CallStackContext::TraceFailure(
                v89,
                "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
                710,
                -1072875842);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
              this,
              -1072875842);
LABEL_165:
          std::vector<bool>::~vector<bool>(&v153);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
          v90 = v149;
          v149 = 0;
          *v163 = v90;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
          return 3222091454LL;
        }
        memcpy_0((void *)(v153 + 4LL * (unsigned int)v165), this[60], 4 * v85);
        v91 = *((_DWORD *)this + 122) + v86;
      }
      else
      {
        v91 = v165;
      }
      v45 = v155;
      if ( v155 == 4 )
      {
        v46 = (const void *)v5;
        *(_DWORD *)&v159[v5] = (_DWORD)MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode;
      }
      v92 = v54 + v5;
      if ( v54 + v5 < v5 )
      {
        v109 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v45);
          CallStackTracing::s_wpInstance = v110;
          if ( v110 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v110 + 8LL))(v110, 2032) )
          {
            v109 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v109 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v109 + 8) )
        {
          v111 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v109);
          if ( *((_DWORD *)v111 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v111,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              722,
              -2147024362);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -2147024362);
        goto LABEL_229;
      }
      v93 = *((_DWORD *)this + 114);
      v5 = v93 + v92;
      if ( v93 + v92 < v92 )
      {
        v106 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v107 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v45);
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
          v108 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v106);
          if ( *((_DWORD *)v108 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v108,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              723,
              -2147024362);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            100,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -2147024362);
LABEL_229:
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v112 = v149;
        v149 = 0;
        *v163 = v112;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 2147942934LL;
      }
      if ( v41 < v54 )
      {
        v103 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v45);
          CallStackTracing::s_wpInstance = v104;
          if ( v104 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(v104, 2032) )
          {
            v103 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v103 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v103 + 8) )
        {
          v105 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v103);
          if ( *((_DWORD *)v105 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v105,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              724,
              -2147024362);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -2147024362);
        goto LABEL_229;
      }
      v94 = v41 - v54;
      if ( v94 < v93 )
      {
        v99 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v48, v45);
          CallStackTracing::s_wpInstance = v100;
          if ( v100 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
          {
            v99 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v99 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v99 + 8) )
        {
          v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
          if ( *((_DWORD *)v101 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v101,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              725,
              -2147024362);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -2147024362);
        std::vector<bool>::~vector<bool>(&v153);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v102 = v149;
        v149 = 0;
        *v163 = v102;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
        return 2147942934LL;
      }
      v41 = v94 - v93;
      v95 = v91;
      v44 = v91 + 1;
      LODWORD(v165) = v44;
      *(_DWORD *)(v153 + 4 * v95) = v54 + v93;
      if ( v44 >= 0x200 )
      {
        v96 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v95, v48, v45);
          CallStackTracing::s_wpInstance = v97;
          if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
          {
            v96 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v96 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v96 + 8) )
        {
          v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
          if ( *((_DWORD *)v98 + 499) != -1072875842 )
            CallStackContext::TraceFailure(
              v98,
              "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
              730,
              -1072875842);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            103,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            -1072875842);
        goto LABEL_165;
      }
    }
  }
  catch ( ... )
  {
    v152 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x2EB,
             (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfstreamvideo.cpp",
             v28);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v165);
    return v152;
  }
  return result;
}

```

## disassembly

```asm
0x1800383d0  mov     rax, rsp
0x1800383d3  mov     [rax+18h], r8b
0x1800383d7  mov     [rax+10h], rdx
0x1800383db  push    rbx
0x1800383dc  push    rsi
0x1800383dd  push    rdi
0x1800383de  push    r12
0x1800383e0  push    r13
0x1800383e2  push    r14
0x1800383e4  push    r15
0x1800383e6  sub     rsp, 0B0h
0x1800383ed  mov     bl, r8b
0x1800383f0  mov     rsi, rcx
0x1800383f3  xor     r15d, r15d
0x1800383f6  test    rdx, rdx
0x1800383f9  jz      loc_180039DCE
0x1800383ff  cmp     [rdx], r15
0x180038402  jz      loc_180039DCE
0x180038408  mov     edi, 270h
0x18003840d  mov     r8d, edi; int
0x180038410  lea     r14, aMkvmfsourcelib_9; "MkvMfSourceLib::MkvMfStreamVideoAVC::Tr"...
0x180038417  mov     rdx, r14; char *
0x18003841a  lea     rcx, [rax+20h]; this
0x18003841e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038423  nop
0x180038424  mov     r8b, bl; bool
0x180038427  mov     rdx, [rsp+0E8h+arg_8]; struct IMFSample **
0x18003842f  mov     rcx, rsi; this
0x180038432  call    ?TransformSample@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z; MkvMfSourceLib::MkvMfStream::TransformSample(IMFSample * *,bool)
0x180038437  mov     ebx, eax
0x180038439  test    eax, eax
0x18003843b  jns     loc_1800384E7
0x180038441  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038448  test    rcx, rcx
0x18003844b  jnz     short loc_18003848E
0x18003844d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038453  mov     rcx, rax
0x180038456  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003845d  test    rax, rax
0x180038460  jz      short loc_180038480
0x180038462  mov     rax, [rax]
0x180038465  mov     edx, 7F0h
0x18003846a  mov     rax, [rax+8]
0x18003846e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038473  test    eax, eax
0x180038475  jz      short loc_180038480
0x180038477  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003847e  jmp     short loc_18003848E
0x180038480  lea     rcx, qword_1800D6F70; this
0x180038487  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003848e  cmp     [rcx+8], r15b
0x180038492  jz      short loc_1800384B2
0x180038494  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038499  cmp     [rax+7CCh], ebx
0x18003849f  jz      short loc_1800384B2
0x1800384a1  mov     r9d, ebx; int
0x1800384a4  mov     r8d, edi; int
0x1800384a7  mov     rdx, r14; char *
0x1800384aa  mov     rcx, rax; this
0x1800384ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800384b2  mov     edi, 1
0x1800384b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800384be  jb      short loc_1800384E2
0x1800384c0  lea     edx, [rdi+55h]
0x1800384c3  mov     [rsp+0E8h+var_C8], ebx
0x1800384c7  mov     r9, rsi
0x1800384ca  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800384d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384d8  mov     rcx, [rcx+10h]
0x1800384dc  call    WPP_SF_qD
0x1800384e1  nop
0x1800384e2  jmp     loc_180039E9B
0x1800384e7  mov     [rsp+0E8h+var_B8], r15
0x1800384ec  mov     rax, [rsp+0E8h+arg_8]
0x1800384f4  mov     rcx, [rax]
0x1800384f7  mov     [rsp+0E8h+var_B8], rcx
0x1800384fc  lea     rax, [rsp+0E8h+arg_8]
0x180038504  mov     [rsp+0E8h+var_58], rax
0x18003850c  lea     rax, [rsp+0E8h+var_B8]
0x180038511  mov     [rsp+0E8h+var_50], rax
0x180038519  mov     edi, 1
0x18003851e  mov     [rsp+0E8h+var_48], dil
0x180038526  mov     [rsp+0E8h+pBuffer], r15
0x18003852b  mov     [rsp+0E8h+var_68], r15
0x180038533  mov     [rsp+0E8h+var_A8], r15d
0x180038538  mov     rax, [rcx]
0x18003853b  lea     rdx, [rsp+0E8h+pBuffer]
0x180038540  mov     rax, [rax+148h]
0x180038547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003854c  mov     ebx, eax
0x18003854e  test    eax, eax
0x180038550  jns     loc_180038636
0x180038556  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003855d  test    rcx, rcx
0x180038560  jnz     short loc_1800385A3
0x180038562  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038568  mov     rcx, rax
0x18003856b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038572  test    rax, rax
0x180038575  jz      short loc_180038595
0x180038577  mov     rax, [rax]
0x18003857a  mov     edx, 7F0h
0x18003857f  mov     rax, [rax+8]
0x180038583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038588  test    eax, eax
0x18003858a  jz      short loc_180038595
0x18003858c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038593  jmp     short loc_1800385A3
0x180038595  lea     rcx, qword_1800D6F70; this
0x18003859c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800385a3  cmp     [rcx+8], r15b
0x1800385a7  jz      short loc_1800385CA
0x1800385a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800385ae  cmp     [rax+7CCh], ebx
0x1800385b4  jz      short loc_1800385CA
0x1800385b6  mov     r9d, ebx; int
0x1800385b9  mov     r8d, 280h; int
0x1800385bf  mov     rdx, r14; char *
0x1800385c2  mov     rcx, rax; this
0x1800385c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800385ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800385d1  jb      short loc_1800385F7
0x1800385d3  mov     edx, 57h ; 'W'
0x1800385d8  mov     [rsp+0E8h+var_C8], ebx
0x1800385dc  mov     r9, rsi
0x1800385df  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800385e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385ed  mov     rcx, [rcx+10h]
0x1800385f1  call    WPP_SF_qD
0x1800385f6  nop
0x1800385f7  lea     rcx, [rsp+0E8h+pBuffer]
0x1800385fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038601  nop
0x180038602  mov     rcx, [rsp+0E8h+var_B8]
0x180038607  mov     [rsp+0E8h+var_B8], r15
0x18003860c  mov     rax, [rsp+0E8h+arg_8]
0x180038614  mov     [rax], rcx
0x180038617  lea     rcx, [rsp+0E8h+var_B8]
0x18003861c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038621  nop
0x180038622  lea     rcx, [rsp+0E8h+arg_18]; this
0x18003862a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003862f  mov     eax, ebx
0x180038631  jmp     loc_180039EAA
0x180038636  mov     rcx, [rsp+0E8h+pBuffer]
0x18003863b  mov     rax, [rcx]
0x18003863e  lea     r9, [rsp+0E8h+var_A8]
0x180038643  xor     r8d, r8d
0x180038646  lea     rdx, [rsp+0E8h+var_68]
0x18003864e  mov     rax, [rax+18h]
0x180038652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038657  mov     ebx, eax
0x180038659  test    eax, eax
0x18003865b  jns     loc_180038741
0x180038661  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038668  test    rcx, rcx
0x18003866b  jnz     short loc_1800386AE
0x18003866d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038673  mov     rcx, rax
0x180038676  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003867d  test    rax, rax
0x180038680  jz      short loc_1800386A0
0x180038682  mov     rax, [rax]
0x180038685  mov     edx, 7F0h
0x18003868a  mov     rax, [rax+8]
0x18003868e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038693  test    eax, eax
0x180038695  jz      short loc_1800386A0
0x180038697  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003869e  jmp     short loc_1800386AE
0x1800386a0  lea     rcx, qword_1800D6F70; this
0x1800386a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800386ae  cmp     [rcx+8], r15b
0x1800386b2  jz      short loc_1800386D5
0x1800386b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800386b9  cmp     [rax+7CCh], ebx
0x1800386bf  jz      short loc_1800386D5
0x1800386c1  mov     r9d, ebx; int
0x1800386c4  mov     r8d, 281h; int
0x1800386ca  mov     rdx, r14; char *
0x1800386cd  mov     rcx, rax; this
0x1800386d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800386d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800386dc  jb      short loc_180038702
0x1800386de  mov     edx, 58h ; 'X'
0x1800386e3  mov     [rsp+0E8h+var_C8], ebx
0x1800386e7  mov     r9, rsi
0x1800386ea  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800386f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386f8  mov     rcx, [rcx+10h]
0x1800386fc  call    WPP_SF_qD
0x180038701  nop
0x180038702  lea     rcx, [rsp+0E8h+pBuffer]
0x180038707  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003870c  nop
0x18003870d  mov     rcx, [rsp+0E8h+var_B8]
0x180038712  mov     [rsp+0E8h+var_B8], r15
0x180038717  mov     rax, [rsp+0E8h+arg_8]
0x18003871f  mov     [rax], rcx
0x180038722  lea     rcx, [rsp+0E8h+var_B8]
0x180038727  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003872c  nop
0x18003872d  lea     rcx, [rsp+0E8h+arg_18]; this
0x180038735  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003873a  mov     eax, ebx
0x18003873c  jmp     loc_180039EAA
0x180038741  cmp     [rsi+1C8h], r15d
0x180038748  jnz     loc_1800388F0
0x18003874e  lea     rax, [rsp+0E8h+pBuffer]
0x180038753  mov     [rsp+0E8h+ppBuffer], rax
0x180038758  mov     [rsp+0E8h+var_78], dil
0x18003875d  cmp     [rsp+0E8h+var_A8], 4
0x180038762  jb      short loc_1800387C7
0x180038764  mov     rax, [rsp+0E8h+var_68]
0x18003876c  mov     ecx, [rax]
0x18003876e  cmp     ecx, cs:?kNaluStartCode@MkvMfStreamVideoAVC@MkvMfSourceLib@@2QBEB; uchar const near * const MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode
0x180038774  jnz     short loc_1800387C7
0x180038776  mov     rcx, [rsp+0E8h+pBuffer]
0x18003877b  mov     rax, [rcx]
0x18003877e  mov     rax, [rax+20h]
0x180038782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038787  nop
0x180038788  lea     rcx, [rsp+0E8h+pBuffer]
0x18003878d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038792  nop
0x180038793  mov     rcx, [rsp+0E8h+var_B8]
0x180038798  mov     [rsp+0E8h+var_B8], r15
0x18003879d  mov     rax, [rsp+0E8h+arg_8]
0x1800387a5  mov     [rax], rcx
0x1800387a8  lea     rcx, [rsp+0E8h+var_B8]
0x1800387ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800387b2  nop
0x1800387b3  lea     rcx, [rsp+0E8h+arg_18]; this
0x1800387bb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800387c0  xor     eax, eax
0x1800387c2  jmp     loc_180039EAA
0x1800387c7  cmp     cs:byte_1800D78D3, 4
0x1800387ce  jb      short loc_1800387F2
0x1800387d0  mov     edx, 59h ; 'Y'
0x1800387d5  mov     r9, rsi
0x1800387d8  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800387df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387e6  mov     rcx, [rcx+88h]
0x1800387ed  call    WPP_SF_q
0x1800387f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800387f9  test    rcx, rcx
0x1800387fc  jnz     short loc_18003883F
0x1800387fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038804  mov     rcx, rax
0x180038807  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003880e  test    rax, rax
0x180038811  jz      short loc_180038831
0x180038813  mov     rax, [rax]
0x180038816  mov     edx, 7F0h
0x18003881b  mov     rax, [rax+8]
0x18003881f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038824  test    eax, eax
0x180038826  jz      short loc_180038831
0x180038828  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003882f  jmp     short loc_18003883F
0x180038831  lea     rcx, qword_1800D6F70; this
0x180038838  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003883f  cmp     [rcx+8], r15b
0x180038843  jz      short loc_18003886D
0x180038845  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003884a  mov     ebx, 0C00D36BBh
0x18003884f  cmp     [rax+7CCh], ebx
0x180038855  jz      short loc_180038872
0x180038857  mov     r9d, ebx; int
0x18003885a  mov     r8d, 28Eh; int
0x180038860  mov     rdx, r14; char *
0x180038863  mov     rcx, rax; this
0x180038866  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003886b  jmp     short loc_180038872
0x18003886d  mov     ebx, 0C00D36BBh
0x180038872  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180038879  jb      short loc_18003889F
0x18003887b  mov     edx, 5Ah ; 'Z'
0x180038880  mov     [rsp+0E8h+var_C8], ebx
0x180038884  mov     r9, rsi
0x180038887  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x18003888e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038895  mov     rcx, [rcx+10h]
0x180038899  call    WPP_SF_qD
0x18003889e  nop
0x18003889f  mov     rcx, [rsp+0E8h+pBuffer]
0x1800388a4  mov     rax, [rcx]
0x1800388a7  mov     rax, [rax+20h]
0x1800388ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388b0  nop
0x1800388b1  lea     rcx, [rsp+0E8h+pBuffer]
0x1800388b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800388bb  nop
0x1800388bc  mov     rdx, [rsp+0E8h+var_B8]
0x1800388c1  mov     [rsp+0E8h+var_B8], r15
0x1800388c6  mov     rcx, [rsp+0E8h+arg_8]
0x1800388ce  mov     [rcx], rdx
0x1800388d1  lea     rcx, [rsp+0E8h+var_B8]
0x1800388d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800388db  nop
  ... truncated ...
```
