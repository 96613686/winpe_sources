# MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType(IMFMediaType * *)

- ea: `0x1800357a0`
- end: `0x180036b58`
- name: `?GetMFMediaType@MkvMfStreamVideoHEVC@MkvMfSourceLib@@UEAAJPEAPEAUIMFMediaType@@@Z`
- size: `5048`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoHEVC *__hidden this, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001fd0`
- `0x180001fdc`
- `0x1800036c5`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180031648`
- `0x1800327d0`
- `0x1800357a0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003580a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003590f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035aee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035beb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035ca6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800360db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003616c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800361fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036348`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800363d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003649a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036532`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800365ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003669a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036732`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800367ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800368b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003697e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036a77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003580a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003590f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035aee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035beb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035ca6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800360db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003616c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800361fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036348`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800363d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003649a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036532`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800365ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003669a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036732`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800367ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800368b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003697e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036a77`
- `MFPlat!MFCreateSample` at `0x180035d33`
- `MFPlat!MFCreateSample` at `0x180035d33`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180035fc9`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180035fc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType(void **this, struct IMFMediaType **a2)
{
  struct IMFMediaType **v2; // r12
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  _QWORD *v24; // r15
  unsigned __int64 v25; // r14
  __int64 v26; // r15
  unsigned __int16 v27; // dx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
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
  void *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // r10
  __int64 v62; // r9
  unsigned int v63; // r13d
  unsigned int v64; // eax
  __int64 v65; // r8
  __int64 v66; // rdx
  unsigned int v67; // ecx
  unsigned int v68; // eax
  unsigned int v69; // r15d
  DWORD v70; // r12d
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  __int64 v93; // rdx
  __int64 *v94; // rcx
  CallStackTracing *v95; // rax
  struct CallStackContext *v96; // rax
  __int64 *v97; // rcx
  CallStackTracing *v98; // rax
  struct CallStackContext *v99; // rax
  __int64 *v100; // rcx
  CallStackTracing *v101; // rax
  struct CallStackContext *v102; // rax
  __int64 v103; // rdx
  __int64 *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 *v107; // rcx
  CallStackTracing *v108; // rax
  struct CallStackContext *v109; // rax
  __int64 *v110; // rcx
  CallStackTracing *v111; // rax
  struct CallStackContext *v112; // rax
  __int64 v113; // rdx
  __int64 *v114; // rcx
  CallStackTracing *v115; // rax
  struct CallStackContext *v116; // rax
  __int64 *v117; // rcx
  CallStackTracing *v118; // rax
  struct CallStackContext *v119; // rax
  __int64 *v120; // rcx
  CallStackTracing *v121; // rax
  struct CallStackContext *v122; // rax
  __int64 *v123; // rcx
  CallStackTracing *v124; // rax
  struct CallStackContext *v125; // rax
  _QWORD *v126; // r14
  __int64 v127; // rdx
  __int64 v128; // r8
  __int64 v129; // r9
  __int64 *v130; // rcx
  CallStackTracing *v131; // rax
  struct CallStackContext *v132; // rax
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // r9
  __int64 *v136; // rcx
  CallStackTracing *v137; // rax
  struct CallStackContext *v138; // rax
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // r9
  __int64 *v142; // rcx
  CallStackTracing *v143; // rax
  struct CallStackContext *v144; // rax
  __int64 v145; // rdx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 *v148; // rcx
  CallStackTracing *v149; // rax
  struct CallStackContext *v150; // rax
  struct IMFMediaType *v151; // rax
  IMFSample *ppIMFSample; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v154[2]; // [rsp+38h] [rbp-41h] BYREF
  char v155; // [rsp+48h] [rbp-31h]
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v157; // [rsp+58h] [rbp-21h] BYREF
  struct IMFMediaType *v158; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v159; // [rsp+68h] [rbp-11h]
  __int64 v160; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v161; // [rsp+78h] [rbp-1h]
  unsigned int i; // [rsp+7Ch] [rbp+3h]
  unsigned int v163; // [rsp+80h] [rbp+7h]
  void *v164[2]; // [rsp+88h] [rbp+Fh] BYREF
  char v165; // [rsp+98h] [rbp+1Fh]
  struct IMFMediaType **v166; // [rsp+E8h] [rbp+6Fh] BYREF
  char v167; // [rsp+F0h] [rbp+77h] BYREF
  int MFMediaType; // [rsp+F8h] [rbp+7Fh] BYREF

  v166 = a2;
  v2 = a2;
  MFMediaType = 0;
  v158 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v154[0] = &MFMediaType;
    v154[1] = this;
    v155 = 1;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v167,
      "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
      785);
    MFMediaType = MkvMfSourceLib::MkvMfStreamVideo::GetMFMediaType((MkvMfSourceLib::MkvMfStreamVideo *)this, &v158);
    if ( MFMediaType < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( MFMediaType < 0 && *((_DWORD *)ThreadRelativeContext + 499) != MFMediaType )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
            785,
            MFMediaType);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v17 = 109;
LABEL_26:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
        this,
        MFMediaType);
LABEL_27:
      v10 = MFMediaType;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v167);
      v155 = 0;
LABEL_28:
      lambda_942c5f5086b0201557cb4d5dce8d0238_::operator()(v154);
      goto LABEL_313;
    }
    MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v158->lpVtbl->SetGUID)(
                    v158,
                    &MF_MT_SUBTYPE,
                    &MFVideoFormat_HEVC);
    if ( MFMediaType < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( MFMediaType < 0 && *((_DWORD *)v23 + 499) != MFMediaType )
          CallStackContext::TraceFailure(v23, "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType", 787, MFMediaType);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v17 = 110;
      goto LABEL_26;
    }
    v24 = this[9];
    v25 = v24[14];
    if ( v25 > 0x17 )
    {
      v26 = v24[13];
      v27 = __ROR2__(*(_WORD *)(v26 + 19), 8);
      if ( v27 )
      {
        MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v158->lpVtbl->SetUINT64)(
                        v158,
                        &MF_MT_FRAME_RATE,
                        ((unsigned __int64)v27 << 32) | 0x100);
        if ( MFMediaType < 0 )
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
            if ( MFMediaType < 0 && *((_DWORD *)v33 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v33,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                797,
                MFMediaType);
          }
          if ( !g_wppLevels )
            goto LABEL_56;
          v34 = 111;
LABEL_55:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            MFMediaType);
LABEL_56:
          v10 = MFMediaType;
LABEL_57:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v167);
          v155 = 0;
          goto LABEL_28;
        }
      }
      *((_DWORD *)this + 114) = (*(_BYTE *)(v26 + 21) & 3) + 1;
      MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, _QWORD))v158->lpVtbl->SetUINT32)(
                      v158,
                      &MF_MT_VIDEO_PROFILE,
                      *(_BYTE *)(v26 + 1) & 0x1F);
      if ( MFMediaType < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( MFMediaType < 0 && *((_DWORD *)v40 + 499) != MFMediaType )
            CallStackContext::TraceFailure(
              v40,
              "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
              803,
              MFMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_56;
        v34 = 112;
        goto LABEL_55;
      }
      MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, _QWORD))v158->lpVtbl->SetUINT32)(
                      v158,
                      &MF_MT_VIDEO_LEVEL,
                      *(unsigned __int8 *)(v26 + 12));
      if ( MFMediaType < 0 )
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
          if ( MFMediaType < 0 && *((_DWORD *)v46 + 499) != MFMediaType )
            CallStackContext::TraceFailure(
              v46,
              "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
              804,
              MFMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_56;
        v34 = 113;
        goto LABEL_55;
      }
      ppIMFSample = 0;
      MFMediaType = MFCreateSample(&ppIMFSample);
      if ( MFMediaType < 0 )
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
          if ( MFMediaType < 0 && *((_DWORD *)v52 + 499) != MFMediaType )
            CallStackContext::TraceFailure(
              v52,
              "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
              810,
              MFMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v53 = 114;
LABEL_94:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v53,
          &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
          this,
          MFMediaType);
LABEL_95:
        v10 = MFMediaType;
LABEL_96:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
        goto LABEL_57;
      }
      operator delete(this[60]);
      v54 = operator new[](0x800u);
      this[60] = v54;
      if ( !v54 )
      {
        MFMediaType = -2147024882;
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( MFMediaType < 0 && *((_DWORD *)v60 + 499) != MFMediaType )
            CallStackContext::TraceFailure(
              v60,
              "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
              816,
              MFMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v53 = 115;
        goto LABEL_94;
      }
      v61 = v26 + 23;
      v160 = v26 + 23;
      v62 = (unsigned int)(v25 - 23);
      v161 = v25 - 23;
      v63 = 0;
      LODWORD(v25) = 0;
      v64 = *(unsigned __int8 *)(v26 + 22);
      v163 = v64;
      v65 = 0;
LABEL_110:
      v157 = v65;
      if ( (unsigned int)v65 < v64 && (int)v25 + 3 < (unsigned int)v62 && (unsigned int)v25 < (int)v25 + 3 )
      {
        v66 = (unsigned int)(v25 + 1);
        if ( (unsigned int)v66 < (unsigned int)v25 )
        {
          MFMediaType = -2147024362;
          v123 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v124 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v65, v62);
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
            if ( MFMediaType < 0 && *((_DWORD *)v125 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v125,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                824,
                MFMediaType);
          }
          if ( !g_wppLevels )
            goto LABEL_95;
          v53 = 116;
        }
        else
        {
          LOBYTE(v65) = *(_BYTE *)((unsigned int)v25 + v61);
          MFMediaType = 0;
          LOWORD(v67) = __ROR2__(*(_WORD *)(v66 + v61), 8);
          v25 = (unsigned int)(v25 + 3);
          if ( (unsigned int)v25 >= (unsigned int)v66 )
          {
            LOBYTE(v65) = v65 & 0x3F;
            v167 = v65;
            v68 = 0;
            v67 = (unsigned __int16)v67;
            for ( i = (unsigned __int16)v67; ; v67 = i )
            {
              v159 = v68;
              if ( v68 >= v67 || (v69 = v25 + 2, (int)v25 + 2 >= (unsigned int)v62) || (unsigned int)v25 >= v69 )
              {
                v65 = v157 + 1;
                v64 = v163;
                goto LABEL_110;
              }
              v70 = (unsigned __int16)__ROR2__(*(_WORD *)(v25 + v61), 8);
              v25 = v70 + v69;
              if ( (unsigned int)v25 < v69 )
              {
                MFMediaType = -2147024362;
                v117 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v118 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v65, v62);
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
                  if ( MFMediaType < 0 && *((_DWORD *)v119 + 499) != MFMediaType )
                    CallStackContext::TraceFailure(
                      v119,
                      "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                      835,
                      MFMediaType);
                }
                if ( g_wppLevels )
                {
                  v113 = 119;
                  goto LABEL_235;
                }
                goto LABEL_236;
              }
              MFMediaType = 0;
              if ( (unsigned int)v25 > (unsigned int)v62 )
                break;
              if ( (unsigned __int8)(v65 - 32) <= 2u )
              {
                v71 = v70 + 4;
                *((_DWORD *)this[60] + v63++) = v71;
                if ( v63 > 0x200 )
                {
                  MFMediaType = -1072875842;
                  v110 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v111 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71, v65, v62);
                    CallStackTracing::s_wpInstance = v111;
                    if ( v111
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v111 + 8LL))(
                           v111,
                           2032) )
                    {
                      v110 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v110 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v110 + 8) )
                  {
                    v112 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v110);
                    if ( MFMediaType < 0 && *((_DWORD *)v112 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v112,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        848,
                        MFMediaType);
                  }
                  if ( g_wppLevels )
                  {
                    v113 = 121;
LABEL_235:
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v113,
                      &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                      this,
                      MFMediaType);
                    goto LABEL_236;
                  }
                  goto LABEL_236;
                }
                ppBuffer = 0;
                MFMediaType = MFCreateAlignedMemoryBuffer(v70, 0, &ppBuffer);
                if ( MFMediaType < 0 )
                {
                  v107 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
                    CallStackTracing::s_wpInstance = v108;
                    if ( v108
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(
                           v108,
                           2032) )
                    {
                      v107 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v107 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v107 + 8) )
                  {
                    v109 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v107);
                    if ( MFMediaType < 0 && *((_DWORD *)v109 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v109,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        852,
                        MFMediaType);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_201;
                  v103 = 122;
LABEL_200:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v103,
                    &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                    this,
                    MFMediaType);
                  goto LABEL_201;
                }
                MFMediaType = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                                ppBuffer,
                                v70);
                if ( MFMediaType < 0 )
                {
                  v104 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75, v76, v77);
                    CallStackTracing::s_wpInstance = v105;
                    if ( v105
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(
                           v105,
                           2032) )
                    {
                      v104 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v104 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v104 + 8) )
                  {
                    v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
                    if ( MFMediaType < 0 && *((_DWORD *)v106 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v106,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        853,
                        MFMediaType);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_201;
                  v103 = 123;
                  goto LABEL_200;
                }
                v164[0] = 0;
                MFMediaType = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                                ppBuffer,
                                v164,
                                0,
                                0);
                if ( MFMediaType < 0 )
                {
                  v100 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79, v80);
                    CallStackTracing::s_wpInstance = v101;
                    if ( v101
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v101 + 8LL))(
                           v101,
                           2032) )
                    {
                      v100 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v100 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v100 + 8) )
                  {
                    v102 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v100);
                    if ( MFMediaType < 0 && *((_DWORD *)v102 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v102,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        855,
                        MFMediaType);
                  }
                  if ( g_wppLevels )
                  {
                    v103 = 124;
                    goto LABEL_200;
                  }
LABEL_201:
                  v10 = MFMediaType;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                  goto LABEL_237;
                }
                memcpy_0(v164[0], (const void *)(v160 + v69), v70);
                MFMediaType = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                if ( MFMediaType < 0 )
                {
                  v97 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v98 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v81, v82, v83);
                    CallStackTracing::s_wpInstance = v98;
                    if ( v98
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v98 + 8LL))(v98, 2032) )
                    {
                      v97 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v97 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v97 + 8) )
                  {
                    v99 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v97);
                    if ( MFMediaType < 0 && *((_DWORD *)v99 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v99,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        857,
                        MFMediaType);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_166;
                  v93 = 125;
LABEL_165:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v93,
                    &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                    this,
                    MFMediaType);
                  goto LABEL_166;
                }
                MFMediaType = ((__int64 (__fastcall *)(IMFSample *, void *))ppIMFSample->lpVtbl->AddBuffer)(
                                ppIMFSample,
                                this[63]);
                if ( MFMediaType < 0 )
                {
                  v94 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v95 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85, v86);
                    CallStackTracing::s_wpInstance = v95;
                    if ( v95
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v95 + 8LL))(v95, 2032) )
                    {
                      v94 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v94 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v94 + 8) )
                  {
                    v96 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v94);
                    if ( MFMediaType < 0 && *((_DWORD *)v96 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v96,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        859,
                        MFMediaType);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_166;
                  v93 = 126;
                  goto LABEL_165;
                }
                MFMediaType = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                                ppIMFSample,
                                ppBuffer);
                if ( MFMediaType < 0 )
                {
                  v90 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v87, v88, v89);
                    CallStackTracing::s_wpInstance = v91;
                    if ( v91
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
                    {
                      v90 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v90 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v90 + 8) )
                  {
                    v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
                    if ( MFMediaType < 0 && *((_DWORD *)v92 + 499) != MFMediaType )
                      CallStackContext::TraceFailure(
                        v92,
                        "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                        860,
                        MFMediaType);
                  }
                  if ( g_wppLevels )
                  {
                    v93 = 127;
                    goto LABEL_165;
                  }
LABEL_166:
                  v10 = MFMediaType;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                  goto LABEL_96;
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                v62 = v161;
                LOBYTE(v65) = v167;
                v61 = v160;
              }
              v68 = v159 + 1;
            }
            MFMediaType = -1072875842;
            v114 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v115 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v65, v62);
              CallStackTracing::s_wpInstance = v115;
              if ( v115
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v115 + 8LL))(v115, 2032) )
              {
                v114 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v114 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v114 + 8) )
            {
              v116 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v114);
              if ( MFMediaType < 0 && *((_DWORD *)v116 + 499) != MFMediaType )
                CallStackContext::TraceFailure(
                  v116,
                  "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                  839,
                  MFMediaType);
            }
            if ( g_wppLevels )
            {
              v113 = 120;
              goto LABEL_235;
            }
LABEL_236:
            v10 = MFMediaType;
LABEL_237:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v167);
            v155 = 0;
            goto LABEL_28;
          }
          MFMediaType = -2147024362;
          v120 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v121 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v65, v62);
            CallStackTracing::s_wpInstance = v121;
            if ( v121
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v121 + 8LL))(v121, 2032) )
            {
              v120 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v120 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v120 + 8) )
          {
            v122 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v120);
            if ( MFMediaType < 0 && *((_DWORD *)v122 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v122,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                827,
                MFMediaType);
          }
          if ( !g_wppLevels )
            goto LABEL_95;
          v53 = 117;
        }
        goto LABEL_94;
      }
      *((_DWORD *)this + 122) = v63;
      if ( v63 )
      {
        v160 = 0;
        v126 = this + 62;
        MFMediaType = ((__int64 (__fastcall *)(IMFSample *, void **))ppIMFSample->lpVtbl->ConvertToContiguousBuffer)(
                        ppIMFSample,
                        this + 62);
        if ( MFMediaType < 0 )
        {
          v130 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v131 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v127, v128, v129);
            CallStackTracing::s_wpInstance = v131;
            if ( v131
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v131 + 8LL))(v131, 2032) )
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
            if ( MFMediaType < 0 && *((_DWORD *)v132 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v132,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                872,
                MFMediaType);
          }
          if ( !g_wppLevels )
            goto LABEL_95;
          v53 = 128;
          goto LABEL_94;
        }
        v157 = 0;
        MFMediaType = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *, _QWORD))(*(_QWORD *)*v126 + 24LL))(
                        *v126,
                        &v160,
                        &v157,
                        0);
        if ( MFMediaType < 0 )
        {
          v136 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v137 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v133, v134, v135);
            CallStackTracing::s_wpInstance = v137;
            if ( v137
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v137 + 8LL))(v137, 2032) )
            {
              v136 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v136 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v136 + 8) )
          {
            v138 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v136);
            if ( MFMediaType < 0 && *((_DWORD *)v138 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v138,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                874,
                MFMediaType);
          }
          if ( !g_wppLevels )
            goto LABEL_95;
          v53 = 129;
          goto LABEL_94;
        }
        v164[1] = this;
        v165 = 1;
        MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64, _QWORD))v158->lpVtbl->SetBlob)(
                        v158,
                        &MF_MT_MPEG_SEQUENCE_HEADER,
                        v160,
                        v157);
        if ( MFMediaType < 0 )
        {
          v142 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v143 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v139, v140, v141);
            CallStackTracing::s_wpInstance = v143;
            if ( v143
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v143 + 8LL))(v143, 2032) )
            {
              v142 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v142 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v142 + 8) )
          {
            v144 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v142);
            if ( MFMediaType < 0 && *((_DWORD *)v144 + 499) != MFMediaType )
              CallStackContext::TraceFailure(
                v144,
                "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
                880,
                MFMediaType);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              130,
              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
              this,
              MFMediaType);
          v10 = MFMediaType;
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v126 + 32LL))(*v126);
          goto LABEL_96;
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v126 + 32LL))(*v126);
      }
      MFMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const IID *, __int64))v158->lpVtbl->SetUINT32)(
                      v158,
                      &MF_NALU_LENGTH_SET,
                      1);
      if ( MFMediaType < 0 )
      {
        v148 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v149 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v145, v146, v147);
          CallStackTracing::s_wpInstance = v149;
          if ( v149 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v149 + 8LL))(v149, 2032) )
          {
            v148 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v148 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v148 + 8) )
        {
          v150 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v148);
          if ( MFMediaType < 0 && *((_DWORD *)v150 + 499) != MFMediaType )
            CallStackContext::TraceFailure(
              v150,
              "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
              882,
              MFMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v53 = 131;
        goto LABEL_94;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
      v2 = v166;
    }
    v151 = v158;
    v158 = 0;
    *v2 = v151;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v167);
    v155 = 0;
    lambda_942c5f5086b0201557cb4d5dce8d0238_::operator()(v154);
    v10 = 0;
    goto LABEL_313;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v166,
    "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType",
    765);
  MFMediaType = -2147467261;
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
    CallStackTracing::s_wpInstance = v8;
    if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v7 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v7 + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
    if ( MFMediaType < 0 && *((_DWORD *)v9 + 499) != MFMediaType )
      CallStackContext::TraceFailure(v9, "MkvMfSourceLib::MkvMfStreamVideoHEVC::GetMFMediaType", 765, MFMediaType);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      108,
      &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
      this,
      MFMediaType);
  v10 = MFMediaType;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v166);
LABEL_313:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v158);
  return v10;
}

```

## disassembly

```asm
0x1800357a0  mov     [rsp-8+arg_0], rbx
0x1800357a5  mov     [rsp-8+arg_8], rdx
0x1800357aa  push    rbp
0x1800357ab  push    rsi
0x1800357ac  push    rdi
0x1800357ad  push    r12
0x1800357af  push    r13
0x1800357b1  push    r14
0x1800357b3  push    r15
0x1800357b5  lea     rbp, [rsp-27h]
0x1800357ba  sub     rsp, 0A0h
0x1800357c1  mov     r12, rdx
0x1800357c4  mov     rdi, rcx
0x1800357c7  xor     r13d, r13d
0x1800357ca  mov     [rbp+57h+arg_18], r13d
0x1800357ce  mov     [rbp+57h+var_70], r13
0x1800357d2  test    rdx, rdx
0x1800357d5  jnz     loc_1800358B8
0x1800357db  mov     ebx, 2FDh
0x1800357e0  mov     r8d, ebx; int
0x1800357e3  lea     rsi, aMkvmfsourcelib_13; "MkvMfSourceLib::MkvMfStreamVideoHEVC::G"...
0x1800357ea  mov     rdx, rsi; char *
0x1800357ed  lea     rcx, [rbp+57h+arg_8]; this
0x1800357f1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800357f6  nop
0x1800357f7  mov     [rbp+57h+arg_18], 80004003h
0x1800357fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035805  test    rcx, rcx
0x180035808  jnz     short loc_18003584B
0x18003580a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035810  mov     rcx, rax
0x180035813  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003581a  test    rax, rax
0x18003581d  jz      short loc_18003583D
0x18003581f  mov     rax, [rax]
0x180035822  mov     edx, 7F0h
0x180035827  mov     rax, [rax+8]
0x18003582b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035830  test    eax, eax
0x180035832  jz      short loc_18003583D
0x180035834  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003583b  jmp     short loc_18003584B
0x18003583d  lea     rcx, qword_1800D6F70; this
0x180035844  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003584b  cmp     [rcx+8], r13b
0x18003584f  jz      short loc_180035876
0x180035851  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035856  mov     r9d, [rbp+57h+arg_18]; int
0x18003585a  test    r9d, r9d
0x18003585d  jns     short loc_180035876
0x18003585f  cmp     [rax+7CCh], r9d
0x180035866  jz      short loc_180035876
0x180035868  mov     r8d, ebx; int
0x18003586b  mov     rdx, rsi; char *
0x18003586e  mov     rcx, rax; this
0x180035871  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035876  mov     ebx, 1
0x18003587b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180035881  jb      short loc_1800358A7
0x180035883  lea     edx, [rbx+6Bh]
0x180035886  mov     eax, [rbp+57h+arg_18]
0x180035889  mov     [rsp+0D0h+var_B0], eax
0x18003588d  mov     r9, rdi
0x180035890  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180035897  mov     rcx, cs:WPP_GLOBAL_Control
0x18003589e  mov     rcx, [rcx+10h]
0x1800358a2  call    WPP_SF_qD
0x1800358a7  mov     ebx, [rbp+57h+arg_18]
0x1800358aa  lea     rcx, [rbp+57h+arg_8]; this
0x1800358ae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800358b3  jmp     loc_180036B32
0x1800358b8  mov     [rdx], r13
0x1800358bb  lea     rax, [rbp+57h+arg_18]
0x1800358bf  mov     [rbp+57h+var_98], rax
0x1800358c3  mov     [rbp+57h+var_90], rdi
0x1800358c7  mov     ebx, 1
0x1800358cc  mov     [rbp+57h+var_88], bl
0x1800358cf  mov     r14d, 311h
0x1800358d5  mov     r8d, r14d; int
0x1800358d8  lea     rsi, aMkvmfsourcelib_13; "MkvMfSourceLib::MkvMfStreamVideoHEVC::G"...
0x1800358df  mov     rdx, rsi; char *
0x1800358e2  lea     rcx, [rbp+57h+arg_10]; this
0x1800358e6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800358eb  nop
0x1800358ec  lea     rdx, [rbp+57h+var_70]; struct IMFMediaType **
0x1800358f0  mov     rcx, rdi; this
0x1800358f3  call    ?GetMFMediaType@MkvMfStreamVideo@MkvMfSourceLib@@UEAAJPEAPEAUIMFMediaType@@@Z; MkvMfSourceLib::MkvMfStreamVideo::GetMFMediaType(IMFMediaType * *)
0x1800358f8  mov     [rbp+57h+arg_18], eax
0x1800358fb  test    eax, eax
0x1800358fd  jns     loc_1800359C8
0x180035903  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003590a  test    rcx, rcx
0x18003590d  jnz     short loc_180035950
0x18003590f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035915  mov     rcx, rax
0x180035918  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003591f  test    rax, rax
0x180035922  jz      short loc_180035942
0x180035924  mov     rax, [rax]
0x180035927  mov     edx, 7F0h
0x18003592c  mov     rax, [rax+8]
0x180035930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035935  test    eax, eax
0x180035937  jz      short loc_180035942
0x180035939  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035940  jmp     short loc_180035950
0x180035942  lea     rcx, qword_1800D6F70; this
0x180035949  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035950  cmp     [rcx+8], r13b
0x180035954  jz      short loc_18003597B
0x180035956  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003595b  mov     r9d, [rbp+57h+arg_18]; int
0x18003595f  test    r9d, r9d
0x180035962  jns     short loc_18003597B
0x180035964  cmp     [rax+7CCh], r9d
0x18003596b  jz      short loc_18003597B
0x18003596d  mov     r8d, r14d; int
0x180035970  mov     rdx, rsi; char *
0x180035973  mov     rcx, rax; this
0x180035976  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003597b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180035981  jb      short loc_1800359A9
0x180035983  mov     edx, 6Dh ; 'm'
0x180035988  mov     eax, [rbp+57h+arg_18]
0x18003598b  mov     [rsp+0D0h+var_B0], eax
0x18003598f  mov     r9, rdi
0x180035992  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180035999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359a0  mov     rcx, [rcx+10h]
0x1800359a4  call    WPP_SF_qD
0x1800359a9  mov     ebx, [rbp+57h+arg_18]
0x1800359ac  lea     rcx, [rbp+57h+arg_10]; this
0x1800359b0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800359b5  nop
0x1800359b6  mov     [rbp+57h+var_88], r13b
0x1800359ba  lea     rcx, [rbp+57h+var_98]
0x1800359be  call    _lambda_942c5f5086b0201557cb4d5dce8d0238___operator__
0x1800359c3  jmp     loc_180036B32
0x1800359c8  mov     rcx, [rbp+57h+var_70]
0x1800359cc  mov     rax, [rcx]
0x1800359cf  lea     r8, MFVideoFormat_HEVC
0x1800359d6  lea     rdx, MF_MT_SUBTYPE
0x1800359dd  mov     rax, [rax+0C0h]
0x1800359e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359e9  mov     [rbp+57h+arg_18], eax
0x1800359ec  test    eax, eax
0x1800359ee  jns     loc_180035A85
0x1800359f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800359fb  test    rcx, rcx
0x1800359fe  jnz     short loc_180035A41
0x180035a00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035a06  mov     rcx, rax
0x180035a09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035a10  test    rax, rax
0x180035a13  jz      short loc_180035A33
0x180035a15  mov     rax, [rax]
0x180035a18  mov     edx, 7F0h
0x180035a1d  mov     rax, [rax+8]
0x180035a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a26  test    eax, eax
0x180035a28  jz      short loc_180035A33
0x180035a2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035a31  jmp     short loc_180035A41
0x180035a33  lea     rcx, qword_1800D6F70; this
0x180035a3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035a41  cmp     [rcx+8], r13b
0x180035a45  jz      short loc_180035A6F
0x180035a47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035a4c  mov     r9d, [rbp+57h+arg_18]; int
0x180035a50  test    r9d, r9d
0x180035a53  jns     short loc_180035A6F
0x180035a55  cmp     [rax+7CCh], r9d
0x180035a5c  jz      short loc_180035A6F
0x180035a5e  mov     r8d, 313h; int
0x180035a64  mov     rdx, rsi; char *
0x180035a67  mov     rcx, rax; this
0x180035a6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035a6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180035a75  jb      loc_1800359A9
0x180035a7b  mov     edx, 6Eh ; 'n'
0x180035a80  jmp     loc_180035988
0x180035a85  mov     r15, [rdi+48h]
0x180035a89  mov     r14, [r15+70h]
0x180035a8d  cmp     r14, 17h
0x180035a91  jbe     loc_180036B0C
0x180035a97  mov     r15, [r15+68h]
0x180035a9b  movzx   edx, word ptr [r15+13h]
0x180035aa0  ror     dx, 8
0x180035aa4  xor     r12d, r12d
0x180035aa7  test    dx, dx
0x180035aaa  jz      loc_180035BA1
0x180035ab0  mov     rcx, [rbp+57h+var_70]
0x180035ab4  mov     rax, [rcx]
0x180035ab7  movzx   r8d, dx
0x180035abb  shl     r8, 20h
0x180035abf  bts     r8, 8
0x180035ac4  lea     rdx, MF_MT_FRAME_RATE
0x180035acb  mov     rax, [rax+0B0h]
0x180035ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ad7  mov     [rbp+57h+arg_18], eax
0x180035ada  test    eax, eax
0x180035adc  jns     loc_180035BA1
0x180035ae2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ae9  test    rcx, rcx
0x180035aec  jnz     short loc_180035B2F
0x180035aee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035af4  mov     rcx, rax
0x180035af7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035afe  test    rax, rax
0x180035b01  jz      short loc_180035B21
0x180035b03  mov     rax, [rax]
0x180035b06  mov     edx, 7F0h
0x180035b0b  mov     rax, [rax+8]
0x180035b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b14  test    eax, eax
0x180035b16  jz      short loc_180035B21
0x180035b18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035b1f  jmp     short loc_180035B2F
0x180035b21  lea     rcx, qword_1800D6F70; this
0x180035b28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035b2f  cmp     [rcx+8], r12b
0x180035b33  jz      short loc_180035B5D
0x180035b35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035b3a  mov     r9d, [rbp+57h+arg_18]; int
0x180035b3e  test    r9d, r9d
0x180035b41  jns     short loc_180035B5D
0x180035b43  cmp     [rax+7CCh], r9d
0x180035b4a  jz      short loc_180035B5D
0x180035b4c  mov     r8d, 31Dh; int
0x180035b52  mov     rdx, rsi; char *
0x180035b55  mov     rcx, rax; this
0x180035b58  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035b5d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180035b63  jb      short loc_180035B8B
0x180035b65  mov     edx, 6Fh ; 'o'
0x180035b6a  mov     eax, [rbp+57h+arg_18]
0x180035b6d  mov     [rsp+0D0h+var_B0], eax
0x180035b71  mov     r9, rdi
0x180035b74  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180035b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b82  mov     rcx, [rcx+10h]
0x180035b86  call    WPP_SF_qD
0x180035b8b  mov     ebx, [rbp+57h+arg_18]
0x180035b8e  lea     rcx, [rbp+57h+arg_10]; this
0x180035b92  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180035b97  nop
0x180035b98  mov     [rbp+57h+var_88], r12b
0x180035b9c  jmp     loc_1800359BA
0x180035ba1  movzx   eax, byte ptr [r15+15h]
0x180035ba6  and     eax, 3
0x180035ba9  add     eax, ebx
0x180035bab  mov     [rdi+1C8h], eax
0x180035bb1  mov     rcx, [rbp+57h+var_70]
0x180035bb5  mov     rax, [rcx]
0x180035bb8  movzx   r8d, byte ptr [r15+1]
0x180035bbd  and     r8d, 1Fh
0x180035bc1  lea     rdx, MF_MT_VIDEO_PROFILE
0x180035bc8  mov     rax, [rax+0A8h]
0x180035bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bd4  mov     [rbp+57h+arg_18], eax
0x180035bd7  test    eax, eax
0x180035bd9  jns     loc_180035C70
0x180035bdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035be6  test    rcx, rcx
0x180035be9  jnz     short loc_180035C2C
0x180035beb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035bf1  mov     rcx, rax
0x180035bf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035bfb  test    rax, rax
0x180035bfe  jz      short loc_180035C1E
0x180035c00  mov     rax, [rax]
0x180035c03  mov     edx, 7F0h
0x180035c08  mov     rax, [rax+8]
0x180035c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c11  test    eax, eax
0x180035c13  jz      short loc_180035C1E
0x180035c15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035c1c  jmp     short loc_180035C2C
0x180035c1e  lea     rcx, qword_1800D6F70; this
0x180035c25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035c2c  cmp     [rcx+8], r12b
0x180035c30  jz      short loc_180035C5A
0x180035c32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035c37  mov     r9d, [rbp+57h+arg_18]; int
0x180035c3b  test    r9d, r9d
0x180035c3e  jns     short loc_180035C5A
0x180035c40  cmp     [rax+7CCh], r9d
0x180035c47  jz      short loc_180035C5A
0x180035c49  mov     r8d, 323h; int
0x180035c4f  mov     rdx, rsi; char *
0x180035c52  mov     rcx, rax; this
0x180035c55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035c5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180035c60  jb      loc_180035B8B
0x180035c66  mov     edx, 70h ; 'p'
0x180035c6b  jmp     loc_180035B6A
0x180035c70  mov     rcx, [rbp+57h+var_70]
0x180035c74  mov     rax, [rcx]
0x180035c77  movzx   r8d, byte ptr [r15+0Ch]
0x180035c7c  lea     rdx, MF_MT_VIDEO_LEVEL
  ... truncated ...
```
