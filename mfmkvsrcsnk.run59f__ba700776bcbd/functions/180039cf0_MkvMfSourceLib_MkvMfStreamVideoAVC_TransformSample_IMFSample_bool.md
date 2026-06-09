# MkvMfSourceLib::MkvMfStreamVideoAVC::TransformSample(IMFSample * *,bool)

- ea: `0x180039cf0`
- end: `0x18003b86e`
- name: `?TransformSample@MkvMfStreamVideoAVC@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `7038`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAVC *__hidden this, struct IMFSample **, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002e54`
- `0x180003705`
- `0x180005c68`
- `0x1800080f4`
- `0x1800089b8`
- `0x180009048`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b58`
- `0x180021b9c`
- `0x180027af0`
- `0x180032bcc`
- `0x180038768`
- `0x180039cf0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a130`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a252`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a50f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a6ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aa74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b040`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b145`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b286`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b3a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b4ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b60f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a130`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a252`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a50f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a6ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aa74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b040`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b145`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b286`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b3a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b4ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b60f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7a4`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18003a7d8`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18003b264`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18003a7d8`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18003b264`

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
        v145 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v17 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v23 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
            v29 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v116 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v122 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v137 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v129 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v49 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v54 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v63 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v69 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v75 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v81 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v86 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v108 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v105 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v102 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v98 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v95 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180039cf0  mov     rax, rsp
0x180039cf3  mov     [rax+18h], r8b
0x180039cf7  mov     [rax+10h], rdx
0x180039cfb  push    rbx
0x180039cfc  push    rsi
0x180039cfd  push    rdi
0x180039cfe  push    r12
0x180039d00  push    r13
0x180039d02  push    r14
0x180039d04  push    r15
0x180039d06  sub     rsp, 0B0h
0x180039d0d  mov     bl, r8b
0x180039d10  mov     rsi, rcx
0x180039d13  xor     r15d, r15d
0x180039d16  test    rdx, rdx
0x180039d19  jz      loc_18003B778
0x180039d1f  cmp     [rdx], r15
0x180039d22  jz      loc_18003B778
0x180039d28  mov     edi, 270h
0x180039d2d  mov     r8d, edi; int
0x180039d30  lea     r14, aMkvmfsourcelib_9; "MkvMfSourceLib::MkvMfStreamVideoAVC::Tr"...
0x180039d37  mov     rdx, r14; char *
0x180039d3a  lea     rcx, [rax+20h]; this
0x180039d3e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180039d43  nop
0x180039d44  mov     r8b, bl; bool
0x180039d47  mov     rdx, [rsp+0E8h+arg_8]; struct IMFSample **
0x180039d4f  mov     rcx, rsi; this
0x180039d52  call    ?TransformSample@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z; MkvMfSourceLib::MkvMfStream::TransformSample(IMFSample * *,bool)
0x180039d57  mov     ebx, eax
0x180039d59  test    eax, eax
0x180039d5b  jns     loc_180039E0D
0x180039d61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d68  test    rcx, rcx
0x180039d6b  jnz     short loc_180039DB4
0x180039d6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039d74  nop     dword ptr [rax+rax+00h]
0x180039d79  mov     rcx, rax
0x180039d7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d83  test    rax, rax
0x180039d86  jz      short loc_180039DA6
0x180039d88  mov     rax, [rax]
0x180039d8b  mov     edx, 7F0h
0x180039d90  mov     rax, [rax+8]
0x180039d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d99  test    eax, eax
0x180039d9b  jz      short loc_180039DA6
0x180039d9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039da4  jmp     short loc_180039DB4
0x180039da6  lea     rcx, qword_1800DBF70; this
0x180039dad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039db4  cmp     [rcx+8], r15b
0x180039db8  jz      short loc_180039DD8
0x180039dba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039dbf  cmp     [rax+7CCh], ebx
0x180039dc5  jz      short loc_180039DD8
0x180039dc7  mov     r9d, ebx; int
0x180039dca  mov     r8d, edi; int
0x180039dcd  mov     rdx, r14; char *
0x180039dd0  mov     rcx, rax; this
0x180039dd3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039dd8  mov     edi, 1
0x180039ddd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180039de4  jb      short loc_180039E08
0x180039de6  lea     edx, [rdi+55h]
0x180039de9  mov     [rsp+0E8h+var_C8], ebx
0x180039ded  mov     r9, rsi
0x180039df0  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180039df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dfe  mov     rcx, [rcx+10h]
0x180039e02  call    WPP_SF_qD
0x180039e07  nop
0x180039e08  jmp     loc_18003B84B
0x180039e0d  mov     [rsp+0E8h+var_B8], r15
0x180039e12  mov     rax, [rsp+0E8h+arg_8]
0x180039e1a  mov     rcx, [rax]
0x180039e1d  mov     [rsp+0E8h+var_B8], rcx
0x180039e22  lea     rax, [rsp+0E8h+arg_8]
0x180039e2a  mov     [rsp+0E8h+var_58], rax
0x180039e32  lea     rax, [rsp+0E8h+var_B8]
0x180039e37  mov     [rsp+0E8h+var_50], rax
0x180039e3f  mov     edi, 1
0x180039e44  mov     [rsp+0E8h+var_48], dil
0x180039e4c  mov     [rsp+0E8h+pBuffer], r15
0x180039e51  mov     [rsp+0E8h+var_68], r15
0x180039e59  mov     [rsp+0E8h+var_A8], r15d
0x180039e5e  mov     rax, [rcx]
0x180039e61  lea     rdx, [rsp+0E8h+pBuffer]
0x180039e66  mov     rax, [rax+148h]
0x180039e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e72  mov     ebx, eax
0x180039e74  test    eax, eax
0x180039e76  jns     loc_180039F62
0x180039e7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e83  test    rcx, rcx
0x180039e86  jnz     short loc_180039ECF
0x180039e88  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039e8f  nop     dword ptr [rax+rax+00h]
0x180039e94  mov     rcx, rax
0x180039e97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e9e  test    rax, rax
0x180039ea1  jz      short loc_180039EC1
0x180039ea3  mov     rax, [rax]
0x180039ea6  mov     edx, 7F0h
0x180039eab  mov     rax, [rax+8]
0x180039eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039eb4  test    eax, eax
0x180039eb6  jz      short loc_180039EC1
0x180039eb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ebf  jmp     short loc_180039ECF
0x180039ec1  lea     rcx, qword_1800DBF70; this
0x180039ec8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ecf  cmp     [rcx+8], r15b
0x180039ed3  jz      short loc_180039EF6
0x180039ed5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039eda  cmp     [rax+7CCh], ebx
0x180039ee0  jz      short loc_180039EF6
0x180039ee2  mov     r9d, ebx; int
0x180039ee5  mov     r8d, 280h; int
0x180039eeb  mov     rdx, r14; char *
0x180039eee  mov     rcx, rax; this
0x180039ef1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039ef6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180039efd  jb      short loc_180039F23
0x180039eff  mov     edx, 57h ; 'W'
0x180039f04  mov     [rsp+0E8h+var_C8], ebx
0x180039f08  mov     r9, rsi
0x180039f0b  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180039f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f19  mov     rcx, [rcx+10h]
0x180039f1d  call    WPP_SF_qD
0x180039f22  nop
0x180039f23  lea     rcx, [rsp+0E8h+pBuffer]
0x180039f28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039f2d  nop
0x180039f2e  mov     rcx, [rsp+0E8h+var_B8]
0x180039f33  mov     [rsp+0E8h+var_B8], r15
0x180039f38  mov     rax, [rsp+0E8h+arg_8]
0x180039f40  mov     [rax], rcx
0x180039f43  lea     rcx, [rsp+0E8h+var_B8]
0x180039f48  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039f4d  nop
0x180039f4e  lea     rcx, [rsp+0E8h+arg_18]; this
0x180039f56  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180039f5b  mov     eax, ebx
0x180039f5d  jmp     loc_18003B85A
0x180039f62  mov     rcx, [rsp+0E8h+pBuffer]
0x180039f67  mov     rax, [rcx]
0x180039f6a  lea     r9, [rsp+0E8h+var_A8]
0x180039f6f  xor     r8d, r8d
0x180039f72  lea     rdx, [rsp+0E8h+var_68]
0x180039f7a  mov     rax, [rax+18h]
0x180039f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f83  mov     ebx, eax
0x180039f85  test    eax, eax
0x180039f87  jns     loc_18003A073
0x180039f8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039f94  test    rcx, rcx
0x180039f97  jnz     short loc_180039FE0
0x180039f99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039fa0  nop     dword ptr [rax+rax+00h]
0x180039fa5  mov     rcx, rax
0x180039fa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039faf  test    rax, rax
0x180039fb2  jz      short loc_180039FD2
0x180039fb4  mov     rax, [rax]
0x180039fb7  mov     edx, 7F0h
0x180039fbc  mov     rax, [rax+8]
0x180039fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fc5  test    eax, eax
0x180039fc7  jz      short loc_180039FD2
0x180039fc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039fd0  jmp     short loc_180039FE0
0x180039fd2  lea     rcx, qword_1800DBF70; this
0x180039fd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039fe0  cmp     [rcx+8], r15b
0x180039fe4  jz      short loc_18003A007
0x180039fe6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039feb  cmp     [rax+7CCh], ebx
0x180039ff1  jz      short loc_18003A007
0x180039ff3  mov     r9d, ebx; int
0x180039ff6  mov     r8d, 281h; int
0x180039ffc  mov     rdx, r14; char *
0x180039fff  mov     rcx, rax; this
0x18003a002  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003a007  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18003a00e  jb      short loc_18003A034
0x18003a010  mov     edx, 58h ; 'X'
0x18003a015  mov     [rsp+0E8h+var_C8], ebx
0x18003a019  mov     r9, rsi
0x18003a01c  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x18003a023  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a02a  mov     rcx, [rcx+10h]
0x18003a02e  call    WPP_SF_qD
0x18003a033  nop
0x18003a034  lea     rcx, [rsp+0E8h+pBuffer]
0x18003a039  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a03e  nop
0x18003a03f  mov     rcx, [rsp+0E8h+var_B8]
0x18003a044  mov     [rsp+0E8h+var_B8], r15
0x18003a049  mov     rax, [rsp+0E8h+arg_8]
0x18003a051  mov     [rax], rcx
0x18003a054  lea     rcx, [rsp+0E8h+var_B8]
0x18003a059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a05e  nop
0x18003a05f  lea     rcx, [rsp+0E8h+arg_18]; this
0x18003a067  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003a06c  mov     eax, ebx
0x18003a06e  jmp     loc_18003B85A
0x18003a073  cmp     [rsi+1C8h], r15d
0x18003a07a  jnz     loc_18003A228
0x18003a080  lea     rax, [rsp+0E8h+pBuffer]
0x18003a085  mov     [rsp+0E8h+ppBuffer], rax
0x18003a08a  mov     [rsp+0E8h+var_78], dil
0x18003a08f  cmp     [rsp+0E8h+var_A8], 4
0x18003a094  jb      short loc_18003A0F9
0x18003a096  mov     rax, [rsp+0E8h+var_68]
0x18003a09e  mov     ecx, [rax]
0x18003a0a0  cmp     ecx, cs:?kNaluStartCode@MkvMfStreamVideoAVC@MkvMfSourceLib@@2QBEB; uchar const near * const MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode
0x18003a0a6  jnz     short loc_18003A0F9
0x18003a0a8  mov     rcx, [rsp+0E8h+pBuffer]
0x18003a0ad  mov     rax, [rcx]
0x18003a0b0  mov     rax, [rax+20h]
0x18003a0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0b9  nop
0x18003a0ba  lea     rcx, [rsp+0E8h+pBuffer]
0x18003a0bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a0c4  nop
0x18003a0c5  mov     rcx, [rsp+0E8h+var_B8]
0x18003a0ca  mov     [rsp+0E8h+var_B8], r15
0x18003a0cf  mov     rax, [rsp+0E8h+arg_8]
0x18003a0d7  mov     [rax], rcx
0x18003a0da  lea     rcx, [rsp+0E8h+var_B8]
0x18003a0df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a0e4  nop
0x18003a0e5  lea     rcx, [rsp+0E8h+arg_18]; this
0x18003a0ed  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003a0f2  xor     eax, eax
0x18003a0f4  jmp     loc_18003B85A
0x18003a0f9  cmp     cs:byte_1800DC8D3, 4
0x18003a100  jb      short loc_18003A124
0x18003a102  mov     edx, 59h ; 'Y'
0x18003a107  mov     r9, rsi
0x18003a10a  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x18003a111  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a118  mov     rcx, [rcx+88h]
0x18003a11f  call    WPP_SF_q
0x18003a124  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003a12b  test    rcx, rcx
0x18003a12e  jnz     short loc_18003A177
0x18003a130  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003a137  nop     dword ptr [rax+rax+00h]
0x18003a13c  mov     rcx, rax
0x18003a13f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003a146  test    rax, rax
0x18003a149  jz      short loc_18003A169
0x18003a14b  mov     rax, [rax]
0x18003a14e  mov     edx, 7F0h
0x18003a153  mov     rax, [rax+8]
0x18003a157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a15c  test    eax, eax
0x18003a15e  jz      short loc_18003A169
0x18003a160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003a167  jmp     short loc_18003A177
0x18003a169  lea     rcx, qword_1800DBF70; this
0x18003a170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003a177  cmp     [rcx+8], r15b
0x18003a17b  jz      short loc_18003A1A5
0x18003a17d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003a182  mov     ebx, 0C00D36BBh
0x18003a187  cmp     [rax+7CCh], ebx
0x18003a18d  jz      short loc_18003A1AA
0x18003a18f  mov     r9d, ebx; int
0x18003a192  mov     r8d, 28Eh; int
0x18003a198  mov     rdx, r14; char *
0x18003a19b  mov     rcx, rax; this
0x18003a19e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003a1a3  jmp     short loc_18003A1AA
0x18003a1a5  mov     ebx, 0C00D36BBh
0x18003a1aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18003a1b1  jb      short loc_18003A1D7
0x18003a1b3  mov     edx, 5Ah ; 'Z'
0x18003a1b8  mov     [rsp+0E8h+var_C8], ebx
0x18003a1bc  mov     r9, rsi
0x18003a1bf  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x18003a1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1cd  mov     rcx, [rcx+10h]
0x18003a1d1  call    WPP_SF_qD
0x18003a1d6  nop
0x18003a1d7  mov     rcx, [rsp+0E8h+pBuffer]
0x18003a1dc  mov     rax, [rcx]
0x18003a1df  mov     rax, [rax+20h]
0x18003a1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1e8  nop
0x18003a1e9  lea     rcx, [rsp+0E8h+pBuffer]
0x18003a1ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a1f3  nop
0x18003a1f4  mov     rdx, [rsp+0E8h+var_B8]
0x18003a1f9  mov     [rsp+0E8h+var_B8], r15
0x18003a1fe  mov     rcx, [rsp+0E8h+arg_8]
  ... truncated ...
```
