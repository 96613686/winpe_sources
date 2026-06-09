# MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample(IMFSample * *,bool)

- ea: `0x1800383d0`
- end: `0x180039ebd`
- name: `?TransformSample@MkvMfStreamVideoAVC@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `6893`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAVC *__hidden this, struct IMFSample **, bool)`
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
// Hidden C++ exception states: #wind=10
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample(
        const void **this,
        struct IMFSample **a2,
        char a3)
{
  unsigned int v4; // r15d
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  struct IMFSample *v26; // rcx
  const char *v27; // r9
  __int64 result; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct IMFSample *v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFSample *v39; // rcx
  unsigned int v40; // r13d
  __int64 size_of; // rax
  __int64 v42; // rbx
  unsigned int v43; // ebx
  __int64 v44; // r9
  const void *v45; // rdx
  int NextNALUnitLength; // ebx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rcx
  DWORD v53; // r12d
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct IMFSample *v57; // rdx
  struct IMFSample *v58; // rcx
  __int64 v59; // rdx
  HRESULT v60; // ebx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // rcx
  int v85; // ebx
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  struct IMFSample *v89; // rcx
  unsigned int v90; // ebx
  unsigned int v91; // eax
  unsigned int v92; // ecx
  unsigned int v93; // r13d
  __int64 v94; // rdx
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  __int64 *v98; // rcx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  struct IMFSample *v101; // rdx
  __int64 *v102; // rcx
  CallStackTracing *v103; // rax
  struct CallStackContext *v104; // rax
  __int64 *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  struct IMFSample *v111; // rcx
  bool v112; // cf
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 *v116; // rcx
  CallStackTracing *v117; // rax
  struct CallStackContext *v118; // rax
  __int64 v119; // rdx
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 *v122; // rcx
  CallStackTracing *v123; // rax
  struct CallStackContext *v124; // rax
  struct IMFSample *v125; // rcx
  __int64 v126; // rdx
  __int64 v127; // r8
  __int64 v128; // r9
  __int64 *v129; // rcx
  CallStackTracing *v130; // rax
  struct CallStackContext *v131; // rax
  struct IMFSample *v132; // rcx
  __int64 v133; // rdx
  int v134; // ebx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 *v137; // rcx
  CallStackTracing *v138; // rax
  struct CallStackContext *v139; // rax
  struct IMFSample *v140; // rcx
  struct IMFSample *v141; // rcx
  __int64 v142; // rdx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 *v145; // rcx
  CallStackTracing *v146; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFSample *v148; // [rsp+30h] [rbp-B8h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v150; // [rsp+40h] [rbp-A8h] BYREF
  DWORD v151; // [rsp+44h] [rbp-A4h]
  __int128 v152; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v153; // [rsp+58h] [rbp-90h]
  unsigned int v154; // [rsp+60h] [rbp-88h]
  _BYTE v155[12]; // [rsp+64h] [rbp-84h] BYREF
  char v156; // [rsp+70h] [rbp-78h]
  DWORD dwLength; // [rsp+78h] [rbp-70h] BYREF
  const unsigned __int8 *v158; // [rsp+80h] [rbp-68h] BYREF
  _QWORD v159[3]; // [rsp+88h] [rbp-60h] BYREF
  char v160; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  struct IMFSample **v162; // [rsp+F8h] [rbp+10h] BYREF
  char v163; // [rsp+100h] [rbp+18h]
  __int64 v164; // [rsp+108h] [rbp+20h] BYREF

  v163 = a3;
  v162 = a2;
  v4 = 0;
  if ( !a2 || !*a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v164,
      "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
      621);
    v145 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v146 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v142, v143, v144);
      CallStackTracing::s_wpInstance = v146;
      if ( v146 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v146 + 8LL))(v146, 2032) )
      {
        v145 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v145 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v145 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v145);
      v9 = -2147467261;
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
          621,
          -2147467261);
    }
    else
    {
      v9 = -2147467261;
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
    (CallStackScopeTrace *)&v164,
    "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample",
    624);
  v5 = MkvMfSourceLib::MkvMfStream::TransformSample((MkvMfSourceLib::MkvMfStream *)this, v162);
  v9 = v5;
  if ( v5 < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 624, v9);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v9);
LABEL_292:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
    return v9;
  }
  try
  {
    v148 = 0;
    v148 = *v162;
    v159[1] = &v162;
    v159[2] = &v148;
    v160 = 1;
    pBuffer = 0;
    v158 = 0;
    v150 = 0;
    v14 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer **))v148->lpVtbl->ConvertToContiguousBuffer)(
            v148,
            &pBuffer);
    if ( v14 < 0 )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v15, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v14 )
          CallStackContext::TraceFailure(v19, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 640, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v14);
LABEL_67:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
      v39 = v148;
      v148 = 0;
      *v162 = v39;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
      return (unsigned int)v14;
    }
    v14 = ((__int64 (__fastcall *)(IMFMediaBuffer *, const unsigned __int8 **, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
            pBuffer,
            &v158,
            0,
            &v150);
    if ( v14 < 0 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v14 )
          CallStackContext::TraceFailure(v25, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 641, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v14);
      goto LABEL_67;
    }
    if ( !*((_DWORD *)this + 114) )
    {
      *(_QWORD *)&v155[4] = &pBuffer;
      v156 = 1;
      if ( v150 >= 4 && *(_DWORD *)v158 == (_DWORD)MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode )
      {
        ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v26 = v148;
        v148 = 0;
        *v162 = v26;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 0;
      }
      else
      {
        if ( (unsigned __int8)byte_1800D78D3 >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 89, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this);
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
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
          if ( *((_DWORD *)v31 + 499) != -1072875845 )
            CallStackContext::TraceFailure(
              v31,
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
        v32 = v148;
        v148 = 0;
        *v162 = v32;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 3222091451LL;
      }
    }
    v14 = ((__int64 (__fastcall *)(struct IMFSample *))v148->lpVtbl->RemoveAllBuffers)(v148);
    if ( v14 < 0 )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v14 )
          CallStackContext::TraceFailure(v38, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 660, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v14);
      goto LABEL_67;
    }
    v154 = *((_DWORD *)this + 114);
    v40 = v150;
    v152 = 0;
    v153 = 0;
    size_of = std::_Get_size_of_n<4>(512);
    *(_QWORD *)&v152 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v42 = v152 + 2048;
    v153 = v152 + 2048;
    memset_0((void *)v152, 0, 0x800u);
    *((_QWORD *)&v152 + 1) = v42;
    v164 = 0;
    std::_Tidy_guard<std::vector<unsigned long>>::~_Tidy_guard<std::vector<unsigned long>>(&v164);
    v43 = 0;
    LODWORD(v164) = 0;
    *(_DWORD *)v155 = 0;
    v151 = 0;
    LODWORD(v44) = v154;
    while ( 1 )
    {
      if ( v4 >= v150 )
      {
        if ( (_DWORD)v44 == 4 )
        {
          *(_DWORD *)&v155[8] = 0;
          v112 = *(_DWORD *)v155 != 0;
          *(_QWORD *)v155 = (unsigned int)-*(_DWORD *)v155;
          v60 = MFCreateMediaBufferWrapper(
                  pBuffer,
                  v112 ? v151 : 0,
                  v150 - (v112 ? v151 : 0),
                  (IMFMediaBuffer **)&v155[4]);
          if ( v60 < 0 )
          {
            v116 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v117 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v113, v114, v115);
              CallStackTracing::s_wpInstance = v117;
              if ( v117
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v117 + 8LL))(v117, 2032) )
              {
                v116 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v116 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v116 + 8) )
            {
              v118 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v116);
              if ( *((_DWORD *)v118 + 499) != v60 )
                CallStackContext::TraceFailure(v118, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 738, v60);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                104,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v60);
            goto LABEL_254;
          }
          v60 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v148->lpVtbl->AddBuffer)(v148, *(_QWORD *)&v155[4]);
          if ( v60 < 0 )
          {
            v122 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v123 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v119, v120, v121);
              CallStackTracing::s_wpInstance = v123;
              if ( v123
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v123 + 8LL))(v123, 2032) )
              {
                v122 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v122 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v122 + 8) )
            {
              v124 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v122);
              if ( *((_DWORD *)v124 + 499) != v60 )
                CallStackContext::TraceFailure(v124, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 739, v60);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v60);
            goto LABEL_254;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v155[4]);
          v43 = v164;
        }
        NextNALUnitLength = ((__int64 (__fastcall *)(struct IMFSample *, const IID *, _QWORD, _QWORD))v148->lpVtbl->SetBlob)(
                              v148,
                              &MF_NALU_LENGTH_INFORMATION,
                              v152,
                              4 * v43);
        if ( NextNALUnitLength >= 0 )
        {
          v159[0] = 0;
          v134 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD *))v148->lpVtbl->ConvertToContiguousBuffer)(
                   v148,
                   v159);
          if ( v134 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v159);
            std::vector<bool>::~vector<bool>(&v152);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
            v141 = v148;
            v148 = 0;
            *v162 = v141;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
            return 0;
          }
          else
          {
            v137 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v133, v135, v136);
              CallStackTracing::s_wpInstance = v138;
              if ( v138
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(v138, 2032) )
              {
                v137 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v137 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v137 + 8) )
            {
              v139 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v137);
              if ( *((_DWORD *)v139 + 499) != v134 )
                CallStackContext::TraceFailure(v139, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 745, v134);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                107,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v134);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v159);
            std::vector<bool>::~vector<bool>(&v152);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
            v140 = v148;
            v148 = 0;
            *v162 = v140;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
            return (unsigned int)v134;
          }
        }
        v129 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v130 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v126, v127, v128);
          CallStackTracing::s_wpInstance = v130;
          if ( v130 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v130 + 8LL))(v130, 2032) )
          {
            v129 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v129 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v129 + 8) )
        {
          v131 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v129);
          if ( *((_DWORD *)v131 + 499) != NextNALUnitLength )
            CallStackContext::TraceFailure(
              v131,
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
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v132 = v148;
        v148 = 0;
        *v162 = v132;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return (unsigned int)NextNALUnitLength;
      }
      dwLength = 0;
      NextNALUnitLength = MkvMfSourceLib::MkvMfStreamVideoAVC::GetNextNALUnitLength(
                            (MkvMfSourceLib::MkvMfStreamVideoAVC *)this,
                            &v158[v4],
                            v40,
                            &dwLength);
      if ( NextNALUnitLength < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != NextNALUnitLength )
            CallStackContext::TraceFailure(
              v51,
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
      v52 = *((unsigned int *)this + 114);
      v53 = dwLength;
      if ( v4 + (_DWORD)v52 + dwLength > v150 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v48);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != -1072875842 )
            CallStackContext::TraceFailure(
              v56,
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
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v57 = v148;
        v148 = 0;
        *v162 = v57;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 3222091454LL;
      }
      if ( (_DWORD)v52 == 4 && dwLength == 1 )
      {
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v58 = v148;
        v148 = 0;
        *v162 = v58;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 0;
      }
      if ( !v4 && v158[v52] == 31 )
        goto LABEL_101;
      if ( v154 == 4 )
        goto LABEL_139;
      if ( !v4 )
      {
LABEL_101:
        *(_DWORD *)v155 = 1;
        v151 = dwLength;
      }
      *(_QWORD *)&v155[4] = 0;
      v60 = ((__int64 (__fastcall *)(struct IMFSample *, const void *))v148->lpVtbl->AddBuffer)(v148, this[63]);
      if ( v60 < 0 )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v61, v62);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != v60 )
            CallStackContext::TraceFailure(v65, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 698, v60);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v60);
LABEL_254:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v155[4]);
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v125 = v148;
        v148 = 0;
        *v162 = v125;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return (unsigned int)v60;
      }
      v60 = MFCreateMediaBufferWrapper(pBuffer, v4 + *((_DWORD *)this + 114), v53, (IMFMediaBuffer **)&v155[4]);
      if ( v60 < 0 )
      {
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != v60 )
            CallStackContext::TraceFailure(v71, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 699, v60);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v60);
        goto LABEL_254;
      }
      v60 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v148->lpVtbl->AddBuffer)(v148, *(_QWORD *)&v155[4]);
      if ( v60 < 0 )
      {
        v75 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
          CallStackTracing::s_wpInstance = v76;
          if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
          {
            v75 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v75 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v75 + 8) )
        {
          v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
          if ( *((_DWORD *)v77 + 499) != v60 )
            CallStackContext::TraceFailure(v77, "MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample", 700, v60);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v60);
        goto LABEL_254;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v155[4]);
LABEL_139:
      if ( !v4 && v163 && (v45 = this[62]) != 0 )
      {
        NextNALUnitLength = ((__int64 (__fastcall *)(struct IMFSample *))v148->lpVtbl->AddBuffer)(v148);
        if ( NextNALUnitLength < 0 )
        {
          v81 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79, v80);
            CallStackTracing::s_wpInstance = v82;
            if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
            {
              v81 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v81 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v81 + 8) )
          {
            v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
            if ( *((_DWORD *)v83 + 499) != NextNALUnitLength )
              CallStackContext::TraceFailure(
                v83,
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
        v84 = *((unsigned int *)this + 122);
        v85 = v164;
        if ( (unsigned int)(v84 + v164) >= 0x200 )
        {
          v86 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79, v80);
            CallStackTracing::s_wpInstance = v87;
            if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
            {
              v86 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v86 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v86 + 8) )
          {
            v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
            if ( *((_DWORD *)v88 + 499) != -1072875842 )
              CallStackContext::TraceFailure(
                v88,
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
          std::vector<bool>::~vector<bool>(&v152);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
          v89 = v148;
          v148 = 0;
          *v162 = v89;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
          return 3222091454LL;
        }
        memcpy_0((void *)(v152 + 4LL * (unsigned int)v164), this[60], 4 * v84);
        v90 = *((_DWORD *)this + 122) + v85;
      }
      else
      {
        v90 = v164;
      }
      v44 = v154;
      if ( v154 == 4 )
      {
        v45 = (const void *)v4;
        *(_DWORD *)&v158[v4] = (_DWORD)MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode;
      }
      v91 = v53 + v4;
      if ( v53 + v4 < v4 )
      {
        v108 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v44);
          CallStackTracing::s_wpInstance = v109;
          if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
          {
            v108 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v108 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v108 + 8) )
        {
          v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
          if ( *((_DWORD *)v110 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v110,
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
      v92 = *((_DWORD *)this + 114);
      v4 = v92 + v91;
      if ( v92 + v91 < v91 )
      {
        v105 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v44);
          CallStackTracing::s_wpInstance = v106;
          if ( v106 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
          {
            v105 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v105 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v105 + 8) )
        {
          v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
          if ( *((_DWORD *)v107 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v107,
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
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v111 = v148;
        v148 = 0;
        *v162 = v111;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 2147942934LL;
      }
      if ( v40 < v53 )
      {
        v102 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v103 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v44);
          CallStackTracing::s_wpInstance = v103;
          if ( v103 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v103 + 8LL))(v103, 2032) )
          {
            v102 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v102 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v102 + 8) )
        {
          v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v102);
          if ( *((_DWORD *)v104 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v104,
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
      v93 = v40 - v53;
      if ( v93 < v92 )
      {
        v98 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v47, v44);
          CallStackTracing::s_wpInstance = v99;
          if ( v99 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
          {
            v98 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v98 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v98 + 8) )
        {
          v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
          if ( *((_DWORD *)v100 + 499) != -2147024362 )
            CallStackContext::TraceFailure(
              v100,
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
        std::vector<bool>::~vector<bool>(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pBuffer);
        v101 = v148;
        v148 = 0;
        *v162 = v101;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
        return 2147942934LL;
      }
      v40 = v93 - v92;
      v94 = v90;
      v43 = v90 + 1;
      LODWORD(v164) = v43;
      *(_DWORD *)(v152 + 4 * v94) = v53 + v92;
      if ( v43 >= 0x200 )
      {
        v95 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v94, v47, v44);
          CallStackTracing::s_wpInstance = v96;
          if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
          {
            v95 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v95 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v95 + 8) )
        {
          v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
          if ( *((_DWORD *)v97 + 499) != -1072875842 )
            CallStackContext::TraceFailure(
              v97,
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
    v151 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x2EB,
             (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfstreamvideo.cpp",
             v27);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v164);
    return v151;
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
