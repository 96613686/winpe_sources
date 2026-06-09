# MkvMfSourceLib::MkvMfStream::ReadBlock(mkvparser::BlockEntry const *)

- ea: `0x180025380`
- end: `0x180025d73`
- name: `?ReadBlock@MkvMfStream@MkvMfSourceLib@@UEAAJPEBVBlockEntry@mkvparser@@@Z`
- size: `2547`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, const struct mkvparser::BlockEntry *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800234a8`
- `0x180025090`
- `0x180025380`
- `0x1800744d8`
- `0x18008fd7c`
- `0x1800ada50`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800254f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002573c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800257d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025866`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800258fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025a25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ade`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025c0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ca2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800254f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002573c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800257d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025866`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800258fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025a25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ade`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025c0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ca2`
- `MFPlat!MFCreateSample` at `0x180025594`
- `MFPlat!MFCreateSample` at `0x180025594`
- `MFPlat!MFCreateMemoryBuffer` at `0x180025464`
- `MFPlat!MFCreateMemoryBuffer` at `0x180025464`

## string_xrefs

- `0x18002544c`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x18002570a`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x18002579f`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025834`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x1800258c9`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x18002595e`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x1800259f3`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025a88`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025b46`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025bdb`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025c70`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180025d05`: `MkvMfSourceLib::MkvMfStream::ReadBlock`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfStream::ReadBlock(
        MkvMfSourceLib::MkvMfStream *this,
        struct mkvparser::IMkvReader ****a2)
{
  __int64 v4; // rbx
  struct mkvparser::IMkvReader ***v5; // rdx
  int v6; // r14d
  char v7; // r13
  __int64 v8; // rsi
  int i; // r12d
  mkvparser::Block::Frame *v10; // r15
  signed int v11; // r14d
  __int64 v12; // rdx
  HRESULT v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // r15d
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v81; // [rsp+30h] [rbp-40h]
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v84; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int8 *v85; // [rsp+50h] [rbp-20h] BYREF
  struct mkvparser::IMkvReader *v86; // [rsp+58h] [rbp-18h]
  __int64 v87; // [rsp+60h] [rbp-10h]
  __int64 v89; // [rsp+C0h] [rbp+50h] BYREF
  int v90; // [rsp+C8h] [rbp+58h] BYREF

  v4 = ((__int64 (__fastcall *)(struct mkvparser::IMkvReader ****))(*a2)[1])(a2);
  v87 = v4;
  v5 = a2[1];
  v6 = *(_DWORD *)(v4 + 40);
  v81 = v6;
  v86 = **v5;
  v89 = 0;
  mkvparser::Block::GetTime((mkvparser::Block *)v4, (const struct Cluster *)v5, &v89);
  if ( *(char *)(v4 + 26) >= 0 )
  {
    v7 = 0;
    if ( *((_BYTE *)this + 288) )
      return 1;
  }
  else
  {
    v7 = 1;
  }
  v8 = v89 / 100;
  for ( i = 0; i < v6; ++i )
  {
    v84 = 0;
    v10 = (mkvparser::Block::Frame *)(*(_QWORD *)(v4 + 32) + 16LL * i);
    v11 = *((_DWORD *)v10 + 2);
    if ( v11 > 0 )
    {
      ppBuffer = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v89,
        "MkvMfSourceLib::MkvMfStream::ReadBlock",
        1272);
      v13 = MFCreateMemoryBuffer(v11, &ppBuffer);
      if ( v13 < 0 )
      {
        v78 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v14, v15);
          CallStackTracing::s_wpInstance = v79;
          if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
          {
            v78 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v78 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v78 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1272, v13);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v49 = 101;
LABEL_140:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, &WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v13);
        goto LABEL_141;
      }
      v85 = 0;
      v90 = 0;
      v13 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, _QWORD))ppBuffer->lpVtbl->Lock)(
              ppBuffer,
              &v85,
              &v90,
              0);
      if ( v13 < 0 )
      {
        v75 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
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
          if ( *((_DWORD *)v77 + 499) != v13 )
            CallStackContext::TraceFailure(v77, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1278, v13);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v49 = 102;
        goto LABEL_140;
      }
      v19 = mkvparser::Block::Frame::Read(v10, v86, v85);
      if ( v19 >= 0 )
      {
        v13 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                ppBuffer,
                (unsigned int)v11);
        if ( v13 < 0 )
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
            v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v48 + 499) != v13 )
              CallStackContext::TraceFailure(v48, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1286, v13);
          }
          if ( g_wppLevels )
          {
            v49 = 103;
            goto LABEL_140;
          }
LABEL_141:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v89);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          return (unsigned int)v13;
        }
      }
      MkvMfSourceLib::MkvMfStream::GetBlockStartAndDuration(this, (const struct mkvparser::BlockEntry *)a2, 0, &v84);
      v13 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v13 < 0 )
      {
        v72 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v73;
          if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
          {
            v72 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v72 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v72 + 8) )
        {
          v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
          if ( *((_DWORD *)v74 + 499) != v13 )
            CallStackContext::TraceFailure(v74, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1334, v13);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v49 = 104;
        goto LABEL_140;
      }
      if ( v19 < 0 )
      {
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
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
        v13 = -1072875818;
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != -1072875818 )
            CallStackContext::TraceFailure(v71, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1338, -1072875818);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v49 = 105;
        goto LABEL_140;
      }
      ppIMFSample = 0;
      v13 = MFCreateSample(&ppIMFSample);
      if ( v13 < 0 )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
          CallStackTracing::s_wpInstance = v67;
          if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
          {
            v66 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v66 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
          if ( *((_DWORD *)v68 + 499) != v13 )
            CallStackContext::TraceFailure(v68, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1343, v13);
        }
        if ( g_wppLevels )
        {
          v53 = 106;
LABEL_98:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v53,
            &WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            v13);
        }
LABEL_99:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
        goto LABEL_141;
      }
      if ( v7 )
      {
        v13 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                ppIMFSample,
                &MFSampleExtension_CleanPoint,
                1);
        if ( v13 < 0 )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
            CallStackTracing::s_wpInstance = v51;
            if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
            {
              v50 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v50 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v50 + 8) )
          {
            v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
            if ( *((_DWORD *)v52 + 499) != v13 )
              CallStackContext::TraceFailure(v52, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1348, v13);
          }
          if ( g_wppLevels )
          {
            v53 = 107;
            goto LABEL_98;
          }
          goto LABEL_99;
        }
      }
      if ( *((_BYTE *)this + 248) )
      {
        v13 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                ppIMFSample,
                &MFSampleExtension_Discontinuity,
                1);
        if ( v13 < 0 )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
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
            if ( *((_DWORD *)v56 + 499) != v13 )
              CallStackContext::TraceFailure(v56, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1353, v13);
          }
          if ( g_wppLevels )
          {
            v53 = 108;
            goto LABEL_98;
          }
          goto LABEL_99;
        }
        *((_BYTE *)this + 248) = 0;
      }
      v13 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, v8);
      if ( v13 < 0 )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
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
          if ( *((_DWORD *)v65 + 499) != v13 )
            CallStackContext::TraceFailure(v65, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1368, v13);
        }
        if ( g_wppLevels )
        {
          v53 = 110;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      v13 = ((__int64 (__fastcall *)(IMFSample *, unsigned __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
              ppIMFSample,
              v84);
      if ( v13 < 0 )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v61;
          if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
          {
            v60 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v60 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v60 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
          if ( *((_DWORD *)v62 + 499) != v13 )
            CallStackContext::TraceFailure(v62, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1369, v13);
        }
        if ( g_wppLevels )
        {
          v53 = 111;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      v13 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
              ppIMFSample,
              ppBuffer);
      if ( v13 < 0 )
      {
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
          CallStackTracing::s_wpInstance = v58;
          if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
          {
            v57 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v57 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v57 + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
          if ( *((_DWORD *)v59 + 499) != v13 )
            CallStackContext::TraceFailure(v59, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1370, v13);
        }
        if ( g_wppLevels )
        {
          v53 = 112;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      LOBYTE(v45) = v7;
      if ( (*(int (__fastcall **)(MkvMfSourceLib::MkvMfStream *, IMFSample **, __int64))(*(_QWORD *)this + 112LL))(
             this,
             &ppIMFSample,
             v45) < 0 )
      {
        v47 = *((_QWORD *)this + 52);
        if ( v47 )
          ++*(_QWORD *)(v47 + 608);
      }
      v8 += v84;
      MkvMfSourceLib::MkvMfStream::QueueSample(this, ppIMFSample);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v89);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
      v4 = v87;
    }
    v6 = v81;
  }
  return 0;
}

```

## disassembly

```asm
0x180025380  mov     [rsp-38h+arg_0], rbx
0x180025385  mov     [rsp-38h+arg_8], rdx
0x18002538a  push    rbp
0x18002538b  push    rsi
0x18002538c  push    rdi
0x18002538d  push    r12
0x18002538f  push    r13
0x180025391  push    r14
0x180025393  push    r15
0x180025395  mov     rbp, rsp
0x180025398  sub     rsp, 70h
0x18002539c  mov     rsi, rdx
0x18002539f  mov     rdi, rcx
0x1800253a2  mov     rax, [rdx]
0x1800253a5  mov     rcx, rdx
0x1800253a8  mov     rax, [rax+8]
0x1800253ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b1  mov     rbx, rax
0x1800253b4  mov     [rbp+var_10], rax
0x1800253b8  mov     rdx, [rsi+8]; struct Cluster *
0x1800253bc  mov     r14d, [rax+28h]
0x1800253c0  mov     [rbp+var_40], r14d
0x1800253c4  mov     r8, [rdx]
0x1800253c7  mov     rax, [r8]
0x1800253ca  mov     [rbp+var_18], rax
0x1800253ce  mov     [rbp+arg_10], 0
0x1800253d6  lea     r8, [rbp+arg_10]; __int64 *
0x1800253da  mov     rcx, rbx; this
0x1800253dd  call    ?GetTime@Block@mkvparser@@QEBAJPEBVCluster@2@AEA_J@Z; mkvparser::Block::GetTime(mkvparser::Cluster const *,__int64 &)
0x1800253e2  cmp     byte ptr [rbx+1Ah], 0
0x1800253e6  jge     loc_180025539
0x1800253ec  mov     r13b, 1
0x1800253ef  mov     rax, 0A3D70A3D70A3D70Bh
0x1800253f9  imul    [rbp+arg_10]
0x1800253fd  mov     rsi, rdx
0x180025400  add     rsi, [rbp+arg_10]
0x180025404  sar     rsi, 6
0x180025408  mov     rax, rsi
0x18002540b  shr     rax, 3Fh
0x18002540f  add     rsi, rax
0x180025412  xor     r12d, r12d
0x180025415  cmp     r12d, r14d
0x180025418  jge     loc_180025D58
0x18002541e  mov     [rbp+var_28], 0
0x180025426  movsxd  r15, r12d
0x180025429  shl     r15, 4
0x18002542d  add     r15, [rbx+20h]
0x180025431  mov     r14d, [r15+8]
0x180025435  test    r14d, r14d
0x180025438  jle     loc_1800256D4
0x18002543e  mov     [rbp+ppBuffer], 0
0x180025446  mov     r8d, 4F8h; int
0x18002544c  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x180025453  lea     rcx, [rbp+arg_10]; this
0x180025457  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002545c  nop
0x18002545d  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180025461  mov     ecx, r14d; cbMaxLength
0x180025464  call    cs:__imp_MFCreateMemoryBuffer
0x18002546b  nop     dword ptr [rax+rax+00h]
0x180025470  mov     ebx, eax
0x180025472  test    eax, eax
0x180025474  js      loc_180025C96
0x18002547a  mov     [rbp+var_20], 0
0x180025482  mov     [rbp+arg_18], 0
0x180025489  mov     rcx, [rbp+ppBuffer]
0x18002548d  mov     rax, [rcx]
0x180025490  xor     r9d, r9d
0x180025493  lea     r8, [rbp+arg_18]
0x180025497  lea     rdx, [rbp+var_20]
0x18002549b  mov     rax, [rax+18h]
0x18002549f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254a4  mov     ebx, eax
0x1800254a6  test    eax, eax
0x1800254a8  js      loc_180025C01
0x1800254ae  mov     r8, [rbp+var_20]; unsigned __int8 *
0x1800254b2  mov     rdx, [rbp+var_18]; struct mkvparser::IMkvReader *
0x1800254b6  mov     rcx, r15; this
0x1800254b9  call    ?Read@Frame@Block@mkvparser@@QEBAJPEAUIMkvReader@3@PEAE@Z; mkvparser::Block::Frame::Read(mkvparser::IMkvReader *,uchar *)
0x1800254be  mov     r15d, eax
0x1800254c1  test    eax, eax
0x1800254c3  js      loc_180025553
0x1800254c9  mov     rcx, [rbp+ppBuffer]
0x1800254cd  mov     r8, [rcx]
0x1800254d0  mov     edx, r14d
0x1800254d3  mov     rax, [r8+30h]
0x1800254d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254dc  mov     ebx, eax
0x1800254de  xor     r14d, r14d
0x1800254e1  test    eax, eax
0x1800254e3  jns     short loc_180025556
0x1800254e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800254ec  test    rcx, rcx
0x1800254ef  jnz     loc_1800256EE
0x1800254f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800254fc  nop     dword ptr [rax+rax+00h]
0x180025501  mov     rcx, rax
0x180025504  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002550b  test    rax, rax
0x18002550e  jz      loc_1800256E0
0x180025514  mov     rax, [rax]
0x180025517  mov     edx, 7F0h
0x18002551c  mov     rax, [rax+8]
0x180025520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025525  test    eax, eax
0x180025527  jz      loc_1800256E0
0x18002552d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025534  jmp     loc_1800256EE
0x180025539  xor     r13b, r13b
0x18002553c  cmp     [rdi+120h], r13b
0x180025543  jz      loc_1800253EF
0x180025549  mov     eax, 1
0x18002554e  jmp     loc_180025D5A
0x180025553  xor     r14d, r14d
0x180025556  lea     r9, [rbp+var_28]; unsigned __int64 *
0x18002555a  xor     r8d, r8d; unsigned __int64 *
0x18002555d  mov     rdx, [rbp+arg_8]; struct mkvparser::BlockEntry *
0x180025561  mov     rcx, rdi; this
0x180025564  call    ?GetBlockStartAndDuration@MkvMfStream@MkvMfSourceLib@@IEAAXPEBVBlockEntry@mkvparser@@PEA_K1@Z; MkvMfSourceLib::MkvMfStream::GetBlockStartAndDuration(mkvparser::BlockEntry const *,unsigned __int64 *,unsigned __int64 *)
0x180025569  mov     rcx, [rbp+ppBuffer]
0x18002556d  mov     rax, [rcx]
0x180025570  mov     rax, [rax+20h]
0x180025574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025579  mov     ebx, eax
0x18002557b  test    eax, eax
0x18002557d  js      loc_180025B6C
0x180025583  test    r15d, r15d
0x180025586  js      loc_180025AD2
0x18002558c  mov     [rbp+ppIMFSample], r14
0x180025590  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180025594  call    cs:__imp_MFCreateSample
0x18002559b  nop     dword ptr [rax+rax+00h]
0x1800255a0  mov     ebx, eax
0x1800255a2  test    eax, eax
0x1800255a4  js      loc_180025A19
0x1800255aa  test    r13b, r13b
0x1800255ad  jz      short loc_1800255D9
0x1800255af  mov     rcx, [rbp+ppIMFSample]
0x1800255b3  mov     rax, [rcx]
0x1800255b6  mov     r8d, 1
0x1800255bc  lea     rdx, MFSampleExtension_CleanPoint
0x1800255c3  mov     rax, [rax+0A8h]
0x1800255ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255cf  mov     ebx, eax
0x1800255d1  test    eax, eax
0x1800255d3  js      loc_180025730
0x1800255d9  cmp     [rdi+0F8h], r14b
0x1800255e0  jz      short loc_180025613
0x1800255e2  mov     rcx, [rbp+ppIMFSample]
0x1800255e6  mov     rax, [rcx]
0x1800255e9  mov     r8d, 1
0x1800255ef  lea     rdx, MFSampleExtension_Discontinuity
0x1800255f6  mov     rax, [rax+0A8h]
0x1800255fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025602  mov     ebx, eax
0x180025604  test    eax, eax
0x180025606  js      loc_1800257C5
0x18002560c  mov     [rdi+0F8h], r14b
0x180025613  mov     rcx, [rbp+ppIMFSample]
0x180025617  mov     rax, [rcx]
0x18002561a  mov     rdx, rsi
0x18002561d  mov     rax, [rax+120h]
0x180025624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025629  mov     ebx, eax
0x18002562b  test    eax, eax
0x18002562d  js      loc_180025984
0x180025633  mov     rcx, [rbp+ppIMFSample]
0x180025637  mov     rax, [rcx]
0x18002563a  mov     rdx, [rbp+var_28]
0x18002563e  mov     rax, [rax+130h]
0x180025645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002564a  mov     ebx, eax
0x18002564c  test    eax, eax
0x18002564e  js      loc_1800258EF
0x180025654  mov     rcx, [rbp+ppIMFSample]
0x180025658  mov     rax, [rcx]
0x18002565b  mov     rdx, [rbp+ppBuffer]
0x18002565f  mov     rax, [rax+150h]
0x180025666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002566b  mov     ebx, eax
0x18002566d  test    eax, eax
0x18002566f  js      loc_18002585A
0x180025675  mov     rax, [rdi]
0x180025678  mov     r8b, r13b
0x18002567b  lea     rdx, [rbp+ppIMFSample]
0x18002567f  mov     rcx, rdi
0x180025682  mov     rax, [rax+70h]
0x180025686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002568b  test    eax, eax
0x18002568d  jns     short loc_1800256A2
0x18002568f  mov     rax, [rdi+1A0h]
0x180025696  test    rax, rax
0x180025699  jz      short loc_1800256A2
0x18002569b  inc     qword ptr [rax+260h]
0x1800256a2  add     rsi, [rbp+var_28]
0x1800256a6  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x1800256aa  mov     rcx, rdi; this
0x1800256ad  call    ?QueueSample@MkvMfStream@MkvMfSourceLib@@IEAAJPEAUIMFSample@@@Z; MkvMfSourceLib::MkvMfStream::QueueSample(IMFSample *)
0x1800256b2  nop
0x1800256b3  lea     rcx, [rbp+ppIMFSample]
0x1800256b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256bc  nop
0x1800256bd  lea     rcx, [rbp+arg_10]; this
0x1800256c1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800256c6  nop
0x1800256c7  lea     rcx, [rbp+ppBuffer]
0x1800256cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256d0  mov     rbx, [rbp+var_10]
0x1800256d4  inc     r12d
0x1800256d7  mov     r14d, [rbp+var_40]
0x1800256db  jmp     loc_180025415
0x1800256e0  lea     rcx, qword_1800DBF70; this
0x1800256e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800256ee  cmp     [rcx+8], r14b
0x1800256f2  jz      short loc_180025719
0x1800256f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800256f9  cmp     [rax+7CCh], ebx
0x1800256ff  jz      short loc_180025719
0x180025701  mov     r9d, ebx; int
0x180025704  mov     r8d, 506h; int
0x18002570a  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x180025711  mov     rcx, rax; this
0x180025714  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025719  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025720  jb      loc_180025D41
0x180025726  mov     edx, 67h ; 'g'
0x18002572b  jmp     loc_180025D22
0x180025730  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025737  test    rcx, rcx
0x18002573a  jnz     short loc_180025783
0x18002573c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025743  nop     dword ptr [rax+rax+00h]
0x180025748  mov     rcx, rax
0x18002574b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025752  test    rax, rax
0x180025755  jz      short loc_180025775
0x180025757  mov     rax, [rax]
0x18002575a  mov     edx, 7F0h
0x18002575f  mov     rax, [rax+8]
0x180025763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025768  test    eax, eax
0x18002576a  jz      short loc_180025775
0x18002576c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025773  jmp     short loc_180025783
0x180025775  lea     rcx, qword_1800DBF70; this
0x18002577c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025783  cmp     [rcx+8], r14b
0x180025787  jz      short loc_1800257AE
0x180025789  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002578e  cmp     [rax+7CCh], ebx
0x180025794  jz      short loc_1800257AE
0x180025796  mov     r9d, ebx; int
0x180025799  mov     r8d, 544h; int
0x18002579f  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x1800257a6  mov     rcx, rax; this
0x1800257a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800257ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800257b5  jb      loc_180025AC4
0x1800257bb  mov     edx, 6Bh ; 'k'
0x1800257c0  jmp     loc_180025AA5
0x1800257c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800257cc  test    rcx, rcx
0x1800257cf  jnz     short loc_180025818
0x1800257d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800257d8  nop     dword ptr [rax+rax+00h]
0x1800257dd  mov     rcx, rax
0x1800257e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800257e7  test    rax, rax
0x1800257ea  jz      short loc_18002580A
0x1800257ec  mov     rax, [rax]
0x1800257ef  mov     edx, 7F0h
0x1800257f4  mov     rax, [rax+8]
0x1800257f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257fd  test    eax, eax
0x1800257ff  jz      short loc_18002580A
0x180025801  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025808  jmp     short loc_180025818
0x18002580a  lea     rcx, qword_1800DBF70; this
0x180025811  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025818  cmp     [rcx+8], r14b
0x18002581c  jz      short loc_180025843
0x18002581e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025823  cmp     [rax+7CCh], ebx
0x180025829  jz      short loc_180025843
0x18002582b  mov     r9d, ebx; int
0x18002582e  mov     r8d, 549h; int
0x180025834  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x18002583b  mov     rcx, rax; this
0x18002583e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025843  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002584a  jb      loc_180025AC4
0x180025850  mov     edx, 6Ch ; 'l'
0x180025855  jmp     loc_180025AA5
0x18002585a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025861  test    rcx, rcx
0x180025864  jnz     short loc_1800258AD
0x180025866  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002586d  nop     dword ptr [rax+rax+00h]
0x180025872  mov     rcx, rax
0x180025875  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
