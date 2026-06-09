# MkvMfSourceLib::MkvMfStream::ReadBlock(mkvparser::BlockEntry const *)

- ea: `0x180024440`
- end: `0x180024de4`
- name: `?ReadBlock@MkvMfStream@MkvMfSourceLib@@UEAAJPEBVBlockEntry@mkvparser@@@Z`
- size: `2468`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *this, struct mkvparser::IMkvReader ****)`
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
// Hidden C++ exception states: #wind=7
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
  HRESULT v12; // ebx
  int v13; // r15d
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
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
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v52; // [rsp+30h] [rbp-40h]
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v55; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int8 *v56; // [rsp+50h] [rbp-20h] BYREF
  struct mkvparser::IMkvReader *v57; // [rsp+58h] [rbp-18h]
  __int64 v58; // [rsp+60h] [rbp-10h]
  __int64 v60; // [rsp+C0h] [rbp+50h] BYREF
  int v61; // [rsp+C8h] [rbp+58h] BYREF

  v4 = ((__int64 (__fastcall *)(struct mkvparser::IMkvReader ****))(*a2)[1])(a2);
  v58 = v4;
  v5 = a2[1];
  v6 = *(_DWORD *)(v4 + 40);
  v52 = v6;
  v57 = **v5;
  v60 = 0;
  mkvparser::Block::GetTime((mkvparser::Block *)v4, (const struct Cluster *)v5, &v60);
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
  v8 = v60 / 100;
  for ( i = 0; i < v6; ++i )
  {
    v55 = 0;
    v10 = (mkvparser::Block::Frame *)(*(_QWORD *)(v4 + 32) + 16LL * i);
    v11 = *((_DWORD *)v10 + 2);
    if ( v11 > 0 )
    {
      ppBuffer = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v60,
        "MkvMfSourceLib::MkvMfStream::ReadBlock",
        1272);
      v12 = MFCreateMemoryBuffer(v11, &ppBuffer);
      if ( v12 < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1272, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v20 = 101;
LABEL_140:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v12);
        goto LABEL_141;
      }
      v56 = 0;
      v61 = 0;
      v12 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, _QWORD))ppBuffer->lpVtbl->Lock)(
              ppBuffer,
              &v56,
              &v61,
              0);
      if ( v12 < 0 )
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
          if ( *((_DWORD *)v48 + 499) != v12 )
            CallStackContext::TraceFailure(v48, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1278, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v20 = 102;
        goto LABEL_140;
      }
      v13 = mkvparser::Block::Frame::Read(v10, v57, v56);
      if ( v13 >= 0 )
      {
        v12 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                ppBuffer,
                (unsigned int)v11);
        if ( v12 < 0 )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
            if ( *((_DWORD *)v19 + 499) != v12 )
              CallStackContext::TraceFailure(v19, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1286, v12);
          }
          if ( g_wppLevels )
          {
            v20 = 103;
            goto LABEL_140;
          }
LABEL_141:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          return (unsigned int)v12;
        }
      }
      MkvMfSourceLib::MkvMfStream::GetBlockStartAndDuration(this, (const struct mkvparser::BlockEntry *)a2, 0, &v55);
      v12 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v12 < 0 )
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
          if ( *((_DWORD *)v45 + 499) != v12 )
            CallStackContext::TraceFailure(v45, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1334, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v20 = 104;
        goto LABEL_140;
      }
      if ( v13 < 0 )
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
        v12 = -1072875818;
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != -1072875818 )
            CallStackContext::TraceFailure(v42, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1338, -1072875818);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v20 = 105;
        goto LABEL_140;
      }
      ppIMFSample = 0;
      v12 = MFCreateSample(&ppIMFSample);
      if ( v12 < 0 )
      {
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
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != v12 )
            CallStackContext::TraceFailure(v39, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1343, v12);
        }
        if ( g_wppLevels )
        {
          v24 = 106;
LABEL_98:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v24,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            v12);
        }
LABEL_99:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
        goto LABEL_141;
      }
      if ( v7 )
      {
        v12 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                ppIMFSample,
                &MFSampleExtension_CleanPoint,
                1);
        if ( v12 < 0 )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            if ( *((_DWORD *)v23 + 499) != v12 )
              CallStackContext::TraceFailure(v23, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1348, v12);
          }
          if ( g_wppLevels )
          {
            v24 = 107;
            goto LABEL_98;
          }
          goto LABEL_99;
        }
      }
      if ( *((_BYTE *)this + 248) )
      {
        v12 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                ppIMFSample,
                &MFSampleExtension_Discontinuity,
                1);
        if ( v12 < 0 )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            if ( *((_DWORD *)v27 + 499) != v12 )
              CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1353, v12);
          }
          if ( g_wppLevels )
          {
            v24 = 108;
            goto LABEL_98;
          }
          goto LABEL_99;
        }
        *((_BYTE *)this + 248) = 0;
      }
      v12 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, v8);
      if ( v12 < 0 )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != v12 )
            CallStackContext::TraceFailure(v36, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1368, v12);
        }
        if ( g_wppLevels )
        {
          v24 = 110;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      v12 = ((__int64 (__fastcall *)(IMFSample *, unsigned __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
              ppIMFSample,
              v55);
      if ( v12 < 0 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          if ( *((_DWORD *)v33 + 499) != v12 )
            CallStackContext::TraceFailure(v33, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1369, v12);
        }
        if ( g_wppLevels )
        {
          v24 = 111;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      v12 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
              ppIMFSample,
              ppBuffer);
      if ( v12 < 0 )
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v12 )
            CallStackContext::TraceFailure(v30, "MkvMfSourceLib::MkvMfStream::ReadBlock", 1370, v12);
        }
        if ( g_wppLevels )
        {
          v24 = 112;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      LOBYTE(v17) = v7;
      if ( (*(int (__fastcall **)(MkvMfSourceLib::MkvMfStream *, IMFSample **, __int64))(*(_QWORD *)this + 112LL))(
             this,
             &ppIMFSample,
             v17) < 0 )
      {
        v18 = *((_QWORD *)this + 52);
        if ( v18 )
          ++*(_QWORD *)(v18 + 608);
      }
      v8 += v55;
      MkvMfSourceLib::MkvMfStream::QueueSample(this, ppIMFSample);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
      v4 = v58;
    }
    v6 = v52;
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
