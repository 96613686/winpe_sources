# MkvMfSourceLib::MkvMfStream::ReadBlock(mkvparser::BlockEntry const *)

- ea: `0x180024440`
- end: `0x180024de4`
- name: `?ReadBlock@MkvMfStream@MkvMfSourceLib@@UEAAJPEBVBlockEntry@mkvparser@@@Z`
- size: `2468`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, const struct mkvparser::BlockEntry *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800225b4`
- `0x1800240f0`
- `0x180024440`
- `0x180071330`
- `0x18008bef4`
- `0x1800a8de8`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800245af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800247ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024879`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024997`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024a26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024c8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024d1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800245af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800247ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024879`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024997`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024a26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024c8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024d1a`
- `MFPlat!MFCreateSample` at `0x180024648`
- `MFPlat!MFCreateSample` at `0x180024648`
- `MFPlat!MFCreateMemoryBuffer` at `0x180024524`
- `MFPlat!MFCreateMemoryBuffer` at `0x180024524`

## string_xrefs

- `0x18002450c`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x1800247b8`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024847`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x1800248d6`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024965`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x1800249f4`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024a83`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024b12`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024bca`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024c59`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024ce8`: `MkvMfSourceLib::MkvMfStream::ReadBlock`
- `0x180024d77`: `MkvMfSourceLib::MkvMfStream::ReadBlock`

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
            v78 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v13);
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
            v75 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v23 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v72 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v69 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v66 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
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
              v50 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v54 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v63 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v60 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v57 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180024440  mov     [rsp-38h+arg_0], rbx
0x180024445  mov     [rsp-38h+arg_8], rdx
0x18002444a  push    rbp
0x18002444b  push    rsi
0x18002444c  push    rdi
0x18002444d  push    r12
0x18002444f  push    r13
0x180024451  push    r14
0x180024453  push    r15
0x180024455  mov     rbp, rsp
0x180024458  sub     rsp, 70h
0x18002445c  mov     rsi, rdx
0x18002445f  mov     rdi, rcx
0x180024462  mov     rax, [rdx]
0x180024465  mov     rcx, rdx
0x180024468  mov     rax, [rax+8]
0x18002446c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024471  mov     rbx, rax
0x180024474  mov     [rbp+var_10], rax
0x180024478  mov     rdx, [rsi+8]; struct Cluster *
0x18002447c  mov     r14d, [rax+28h]
0x180024480  mov     [rbp+var_40], r14d
0x180024484  mov     r8, [rdx]
0x180024487  mov     rax, [r8]
0x18002448a  mov     [rbp+var_18], rax
0x18002448e  mov     [rbp+arg_10], 0
0x180024496  lea     r8, [rbp+arg_10]; __int64 *
0x18002449a  mov     rcx, rbx; this
0x18002449d  call    ?GetTime@Block@mkvparser@@QEBAJPEBVCluster@2@AEA_J@Z; mkvparser::Block::GetTime(mkvparser::Cluster const *,__int64 &)
0x1800244a2  cmp     byte ptr [rbx+1Ah], 0
0x1800244a6  jge     loc_1800245ED
0x1800244ac  mov     r13b, 1
0x1800244af  mov     rax, 0A3D70A3D70A3D70Bh
0x1800244b9  imul    [rbp+arg_10]
0x1800244bd  mov     rsi, rdx
0x1800244c0  add     rsi, [rbp+arg_10]
0x1800244c4  sar     rsi, 6
0x1800244c8  mov     rax, rsi
0x1800244cb  shr     rax, 3Fh
0x1800244cf  add     rsi, rax
0x1800244d2  xor     r12d, r12d
0x1800244d5  cmp     r12d, r14d
0x1800244d8  jge     loc_180024DCA
0x1800244de  mov     [rbp+var_28], 0
0x1800244e6  movsxd  r15, r12d
0x1800244e9  shl     r15, 4
0x1800244ed  add     r15, [rbx+20h]
0x1800244f1  mov     r14d, [r15+8]
0x1800244f5  test    r14d, r14d
0x1800244f8  jle     loc_180024782
0x1800244fe  mov     [rbp+ppBuffer], 0
0x180024506  mov     r8d, 4F8h; int
0x18002450c  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x180024513  lea     rcx, [rbp+arg_10]; this
0x180024517  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002451c  nop
0x18002451d  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180024521  mov     ecx, r14d; cbMaxLength
0x180024524  call    cs:__imp_MFCreateMemoryBuffer
0x18002452a  mov     ebx, eax
0x18002452c  test    eax, eax
0x18002452e  js      loc_180024D0E
0x180024534  mov     [rbp+var_20], 0
0x18002453c  mov     [rbp+arg_18], 0
0x180024543  mov     rcx, [rbp+ppBuffer]
0x180024547  mov     rax, [rcx]
0x18002454a  xor     r9d, r9d
0x18002454d  lea     r8, [rbp+arg_18]
0x180024551  lea     rdx, [rbp+var_20]
0x180024555  mov     rax, [rax+18h]
0x180024559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002455e  mov     ebx, eax
0x180024560  test    eax, eax
0x180024562  js      loc_180024C7F
0x180024568  mov     r8, [rbp+var_20]; unsigned __int8 *
0x18002456c  mov     rdx, [rbp+var_18]; struct mkvparser::IMkvReader *
0x180024570  mov     rcx, r15; this
0x180024573  call    ?Read@Frame@Block@mkvparser@@QEBAJPEAUIMkvReader@3@PEAE@Z; mkvparser::Block::Frame::Read(mkvparser::IMkvReader *,uchar *)
0x180024578  mov     r15d, eax
0x18002457b  test    eax, eax
0x18002457d  js      loc_180024607
0x180024583  mov     rcx, [rbp+ppBuffer]
0x180024587  mov     r8, [rcx]
0x18002458a  mov     edx, r14d
0x18002458d  mov     rax, [r8+30h]
0x180024591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024596  mov     ebx, eax
0x180024598  xor     r14d, r14d
0x18002459b  test    eax, eax
0x18002459d  jns     short loc_18002460A
0x18002459f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245a6  test    rcx, rcx
0x1800245a9  jnz     loc_18002479C
0x1800245af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800245b5  mov     rcx, rax
0x1800245b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245bf  test    rax, rax
0x1800245c2  jz      loc_18002478E
0x1800245c8  mov     rax, [rax]
0x1800245cb  mov     edx, 7F0h
0x1800245d0  mov     rax, [rax+8]
0x1800245d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245d9  test    eax, eax
0x1800245db  jz      loc_18002478E
0x1800245e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245e8  jmp     loc_18002479C
0x1800245ed  xor     r13b, r13b
0x1800245f0  cmp     [rdi+120h], r13b
0x1800245f7  jz      loc_1800244AF
0x1800245fd  mov     eax, 1
0x180024602  jmp     loc_180024DCC
0x180024607  xor     r14d, r14d
0x18002460a  lea     r9, [rbp+var_28]; unsigned __int64 *
0x18002460e  xor     r8d, r8d; unsigned __int64 *
0x180024611  mov     rdx, [rbp+arg_8]; struct mkvparser::BlockEntry *
0x180024615  mov     rcx, rdi; this
0x180024618  call    ?GetBlockStartAndDuration@MkvMfStream@MkvMfSourceLib@@IEAAXPEBVBlockEntry@mkvparser@@PEA_K1@Z; MkvMfSourceLib::MkvMfStream::GetBlockStartAndDuration(mkvparser::BlockEntry const *,unsigned __int64 *,unsigned __int64 *)
0x18002461d  mov     rcx, [rbp+ppBuffer]
0x180024621  mov     rax, [rcx]
0x180024624  mov     rax, [rax+20h]
0x180024628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002462d  mov     ebx, eax
0x18002462f  test    eax, eax
0x180024631  js      loc_180024BF0
0x180024637  test    r15d, r15d
0x18002463a  js      loc_180024B5C
0x180024640  mov     [rbp+ppIMFSample], r14
0x180024644  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180024648  call    cs:__imp_MFCreateSample
0x18002464e  mov     ebx, eax
0x180024650  test    eax, eax
0x180024652  js      loc_180024AA9
0x180024658  test    r13b, r13b
0x18002465b  jz      short loc_180024687
0x18002465d  mov     rcx, [rbp+ppIMFSample]
0x180024661  mov     rax, [rcx]
0x180024664  mov     r8d, 1
0x18002466a  lea     rdx, MFSampleExtension_CleanPoint
0x180024671  mov     rax, [rax+0A8h]
0x180024678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002467d  mov     ebx, eax
0x18002467f  test    eax, eax
0x180024681  js      loc_1800247DE
0x180024687  cmp     [rdi+0F8h], r14b
0x18002468e  jz      short loc_1800246C1
0x180024690  mov     rcx, [rbp+ppIMFSample]
0x180024694  mov     rax, [rcx]
0x180024697  mov     r8d, 1
0x18002469d  lea     rdx, MFSampleExtension_Discontinuity
0x1800246a4  mov     rax, [rax+0A8h]
0x1800246ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246b0  mov     ebx, eax
0x1800246b2  test    eax, eax
0x1800246b4  js      loc_18002486D
0x1800246ba  mov     [rdi+0F8h], r14b
0x1800246c1  mov     rcx, [rbp+ppIMFSample]
0x1800246c5  mov     rax, [rcx]
0x1800246c8  mov     rdx, rsi
0x1800246cb  mov     rax, [rax+120h]
0x1800246d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246d7  mov     ebx, eax
0x1800246d9  test    eax, eax
0x1800246db  js      loc_180024A1A
0x1800246e1  mov     rcx, [rbp+ppIMFSample]
0x1800246e5  mov     rax, [rcx]
0x1800246e8  mov     rdx, [rbp+var_28]
0x1800246ec  mov     rax, [rax+130h]
0x1800246f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246f8  mov     ebx, eax
0x1800246fa  test    eax, eax
0x1800246fc  js      loc_18002498B
0x180024702  mov     rcx, [rbp+ppIMFSample]
0x180024706  mov     rax, [rcx]
0x180024709  mov     rdx, [rbp+ppBuffer]
0x18002470d  mov     rax, [rax+150h]
0x180024714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024719  mov     ebx, eax
0x18002471b  test    eax, eax
0x18002471d  js      loc_1800248FC
0x180024723  mov     rax, [rdi]
0x180024726  mov     r8b, r13b
0x180024729  lea     rdx, [rbp+ppIMFSample]
0x18002472d  mov     rcx, rdi
0x180024730  mov     rax, [rax+70h]
0x180024734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024739  test    eax, eax
0x18002473b  jns     short loc_180024750
0x18002473d  mov     rax, [rdi+1A0h]
0x180024744  test    rax, rax
0x180024747  jz      short loc_180024750
0x180024749  inc     qword ptr [rax+260h]
0x180024750  add     rsi, [rbp+var_28]
0x180024754  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x180024758  mov     rcx, rdi; this
0x18002475b  call    ?QueueSample@MkvMfStream@MkvMfSourceLib@@IEAAJPEAUIMFSample@@@Z; MkvMfSourceLib::MkvMfStream::QueueSample(IMFSample *)
0x180024760  nop
0x180024761  lea     rcx, [rbp+ppIMFSample]
0x180024765  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002476a  nop
0x18002476b  lea     rcx, [rbp+arg_10]; this
0x18002476f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180024774  nop
0x180024775  lea     rcx, [rbp+ppBuffer]
0x180024779  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002477e  mov     rbx, [rbp+var_10]
0x180024782  inc     r12d
0x180024785  mov     r14d, [rbp+var_40]
0x180024789  jmp     loc_1800244D5
0x18002478e  lea     rcx, qword_1800D6F70; this
0x180024795  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002479c  cmp     [rcx+8], r14b
0x1800247a0  jz      short loc_1800247C7
0x1800247a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800247a7  cmp     [rax+7CCh], ebx
0x1800247ad  jz      short loc_1800247C7
0x1800247af  mov     r9d, ebx; int
0x1800247b2  mov     r8d, 506h; int
0x1800247b8  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x1800247bf  mov     rcx, rax; this
0x1800247c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800247c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800247ce  jb      loc_180024DB3
0x1800247d4  mov     edx, 67h ; 'g'
0x1800247d9  jmp     loc_180024D94
0x1800247de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800247e5  test    rcx, rcx
0x1800247e8  jnz     short loc_18002482B
0x1800247ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800247f0  mov     rcx, rax
0x1800247f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800247fa  test    rax, rax
0x1800247fd  jz      short loc_18002481D
0x1800247ff  mov     rax, [rax]
0x180024802  mov     edx, 7F0h
0x180024807  mov     rax, [rax+8]
0x18002480b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024810  test    eax, eax
0x180024812  jz      short loc_18002481D
0x180024814  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002481b  jmp     short loc_18002482B
0x18002481d  lea     rcx, qword_1800D6F70; this
0x180024824  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002482b  cmp     [rcx+8], r14b
0x18002482f  jz      short loc_180024856
0x180024831  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024836  cmp     [rax+7CCh], ebx
0x18002483c  jz      short loc_180024856
0x18002483e  mov     r9d, ebx; int
0x180024841  mov     r8d, 544h; int
0x180024847  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x18002484e  mov     rcx, rax; this
0x180024851  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180024856  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002485d  jb      loc_180024B4E
0x180024863  mov     edx, 6Bh ; 'k'
0x180024868  jmp     loc_180024B2F
0x18002486d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024874  test    rcx, rcx
0x180024877  jnz     short loc_1800248BA
0x180024879  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002487f  mov     rcx, rax
0x180024882  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024889  test    rax, rax
0x18002488c  jz      short loc_1800248AC
0x18002488e  mov     rax, [rax]
0x180024891  mov     edx, 7F0h
0x180024896  mov     rax, [rax+8]
0x18002489a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002489f  test    eax, eax
0x1800248a1  jz      short loc_1800248AC
0x1800248a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800248aa  jmp     short loc_1800248BA
0x1800248ac  lea     rcx, qword_1800D6F70; this
0x1800248b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800248ba  cmp     [rcx+8], r14b
0x1800248be  jz      short loc_1800248E5
0x1800248c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800248c5  cmp     [rax+7CCh], ebx
0x1800248cb  jz      short loc_1800248E5
0x1800248cd  mov     r9d, ebx; int
0x1800248d0  mov     r8d, 549h; int
0x1800248d6  lea     rdx, aMkvmfsourcelib_5; "MkvMfSourceLib::MkvMfStream::ReadBlock"
0x1800248dd  mov     rcx, rax; this
0x1800248e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800248e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800248ec  jb      loc_180024B4E
0x1800248f2  mov     edx, 6Ch ; 'l'
0x1800248f7  jmp     loc_180024B2F
0x1800248fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024903  test    rcx, rcx
0x180024906  jnz     short loc_180024949
0x180024908  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002490e  mov     rcx, rax
0x180024911  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024918  test    rax, rax
0x18002491b  jz      short loc_18002493B
0x18002491d  mov     rax, [rax]
0x180024920  mov     edx, 7F0h
0x180024925  mov     rax, [rax+8]
0x180024929  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
