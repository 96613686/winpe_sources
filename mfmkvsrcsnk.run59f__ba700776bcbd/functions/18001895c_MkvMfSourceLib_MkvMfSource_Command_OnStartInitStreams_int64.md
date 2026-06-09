# MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)

- ea: `0x18001895c`
- end: `0x180019319`
- name: `?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z`
- size: `2493`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001789c`
- `0x180017f48`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000cd1c`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x18001895c`
- `0x18001bca0`
- `0x180021b9c`
- `0x180022640`
- `0x1800242ec`
- `0x18002436c`
- `0x180026e34`
- `0x180046bc4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018cbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018ed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800191f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018cbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018ed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800191f6`

## string_xrefs

- `0x1800189b0`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018ac7`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018d29`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018f3b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x18001901c`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x1800190f0`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x1800191c4`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180019261`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(
        MkvMfSourceLib::MkvMfSource::Command *this,
        __int64 a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // r12
  _QWORD *v14; // rdi
  __int128 v15; // xmm7
  __int64 v16; // r14
  _QWORD *v17; // rbx
  __int64 v18; // xmm8_8
  __int128 v19; // xmm6
  __int128 v20; // xmm9
  _QWORD *v21; // rbx
  __int64 v22; // rax
  __int128 *v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned int i; // r15d
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rax
  MkvMfSourceLib::MkvMfStream *v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  int v48; // edi
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  MkvReader *v62; // rcx
  int v64[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v65; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v66; // [rsp+48h] [rbp-C0h] BYREF
  int v67; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v68; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v69[2]; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v70[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v71; // [rsp+88h] [rbp-80h]
  __int64 v72; // [rsp+98h] [rbp-70h]
  MkvMfSourceLib::MkvMfStream *v73; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v75; // [rsp+C8h] [rbp-40h]
  __int128 v76; // [rsp+D8h] [rbp-30h]
  __int64 v77; // [rsp+E8h] [rbp-20h]
  __int128 v78; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v79; // [rsp+108h] [rbp+0h]
  __int128 v80; // [rsp+118h] [rbp+10h]
  __int64 v81; // [rsp+128h] [rbp+20h]
  _QWORD v82[2]; // [rsp+130h] [rbp+28h] BYREF

  v64[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v64[1],
    "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
    3787);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v82);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v82[0] = this;
  v82[1] = v64;
  v66 = 0;
  v64[0] = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 3) + 264LL))(
             *((_QWORD *)this + 3),
             &v66);
  if ( v64[0] >= 0 )
  {
    v13 = *((_QWORD *)this + 1);
    v14 = *(_QWORD **)(v13 + 576);
    v72 = 0;
    v15 = 0;
    v16 = 0;
    v71 = 0u;
    v70[0] = 0xFFFFFFFF;
    v17 = (_QWORD *)*v14;
    v65 = (_QWORD *)*v14;
    v18 = 0;
    v19 = 0u;
    v20 = 0xFFFFFFFF;
    while ( v17 != v14 )
    {
      v21 = (_QWORD *)v17[5];
      *(_QWORD *)v69 = v21;
      Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v69);
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*v21 + 120LL))(v21) )
      {
        MkvMfSourceLib::MkvMfStream::GetSeekInfoForTime(v21, &v78, a2);
        if ( (_QWORD)v80 )
        {
          if ( !v16
            || (v22 = *(_QWORD *)(v80 + 8), v22 < *(_QWORD *)(v16 + 8))
            || v22 == *(_QWORD *)(v16 + 8) && *(_QWORD *)(v80 + 16) < *(_QWORD *)(v16 + 16) )
          {
            v20 = v78;
            v15 = v79;
            v19 = v80;
            v18 = v81;
            v16 = v80;
          }
          v70[0] = v78;
          v70[1] = v79;
          v71 = v80;
          v72 = v81;
          v23 = v70;
        }
        else
        {
          v72 = 0;
          v71 = 0u;
          v70[0] = 0xFFFFFFFF;
          v74 = 0xFFFFFFFF;
          v75 = 0;
          v76 = 0u;
          v77 = 0;
          v23 = &v74;
        }
        (*(void (__fastcall **)(_QWORD *, __int128 *))(*v21 + 152LL))(v21, v23);
        v21[34] = 5000000;
      }
      if ( v21 )
        (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v65);
      v17 = v65;
    }
    if ( v16 )
    {
      for ( i = 0; i < v66; ++i )
      {
        LODWORD(v68) = 0;
        v65 = 0;
        v64[0] = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD **))(**((_QWORD **)this + 3) + 272LL))(
                   *((_QWORD *)this + 3),
                   i,
                   &v68,
                   &v65);
        if ( v64[0] < 0 )
        {
          v59 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
            CallStackTracing::s_wpInstance = v60;
            if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
            {
              v59 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v59 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v59 + 8) )
          {
            v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
            if ( v64[0] < 0 && *((_DWORD *)v61 + 499) != v64[0] )
              CallStackContext::TraceFailure(
                v61,
                "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
                3845,
                v64[0]);
          }
          if ( g_wppLevels )
          {
            v58 = 246;
LABEL_124:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v58,
              &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
              this,
              v64[0]);
          }
LABEL_125:
          v12 = v64[0];
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
          goto LABEL_127;
        }
        v67 = 0;
        v64[0] = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v65 + 264LL))(v65, &v67);
        if ( v64[0] < 0 )
        {
          v55 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
            CallStackTracing::s_wpInstance = v56;
            if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
            {
              v55 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v55 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v55 + 8) )
          {
            v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
            if ( v64[0] < 0 && *((_DWORD *)v57 + 499) != v64[0] )
              CallStackContext::TraceFailure(
                v57,
                "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
                3849,
                v64[0]);
          }
          if ( g_wppLevels )
          {
            v58 = 247;
            goto LABEL_124;
          }
          goto LABEL_125;
        }
        v34 = std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::_Find<unsigned long>(
                v13 + 576,
                &v67);
        if ( (_QWORD *)v34 != v14 )
        {
          v73 = *(MkvMfSourceLib::MkvMfStream **)(v34 + 40);
          v35 = v73;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v73);
          if ( (_DWORD)v68 )
          {
            v69[0] = 0;
            v64[0] = MkvMfSourceLib::MkvMfStream::Select(v35, v69);
            if ( v64[0] < 0 )
            {
              v52 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                {
                  v52 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v52 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v52 + 8) )
              {
                v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                if ( v64[0] < 0 && *((_DWORD *)v54 + 499) != v64[0] )
                  CallStackContext::TraceFailure(
                    v54,
                    "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
                    3873,
                    v64[0]);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  249,
                  &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
                  this,
                  v64[0]);
              v48 = v64[0];
              if ( v35 )
                (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v35 + 16LL))(v35);
              goto LABEL_73;
            }
            v64[0] = MkvMfSourceLib::MkvMfSource::QueueStreamEvent(
                       *((MkvMfSourceLib::MkvMfSource **)this + 1),
                       v69[0],
                       v35);
            if ( v64[0] < 0 )
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
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
                if ( v64[0] < 0 && *((_DWORD *)v51 + 499) != v64[0] )
                  CallStackContext::TraceFailure(
                    v51,
                    "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
                    3875,
                    v64[0]);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  250,
                  &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
                  this,
                  v64[0]);
              v48 = v64[0];
              if ( v35 )
                (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v35 + 16LL))(v35);
              goto LABEL_73;
            }
            MkvMfSourceLib::MkvMfStream::GetSeekInfo(v35, &v74);
            if ( !(_QWORD)v76 )
            {
              v74 = v20;
              v75 = v15;
              v76 = v19;
              v77 = v18;
              (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *, __int128 *))(*(_QWORD *)v35 + 152LL))(v35, &v74);
            }
          }
          else
          {
            v64[0] = MkvMfSourceLib::MkvMfStream::Deselect(v35);
            if ( v64[0] < 0 )
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
                CallStackTracing::s_wpInstance = v46;
                if ( v46
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                {
                  v45 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v45 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v45 + 8) )
              {
                v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                if ( v64[0] < 0 && *((_DWORD *)v47 + 499) != v64[0] )
                  CallStackContext::TraceFailure(
                    v47,
                    "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams",
                    3868,
                    v64[0]);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  248,
                  &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
                  this,
                  v64[0]);
              v48 = v64[0];
              if ( v35 )
                (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_73:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
              v12 = v48;
              goto LABEL_127;
            }
          }
          if ( v35 )
            (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v35 + 16LL))(v35);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
      }
      v62 = (MkvReader *)(*((_QWORD *)this + 1) + 184LL);
      *((_QWORD *)v62 + 26) = *(_QWORD *)(v16 + 8);
      MkvReader::Seek(v62, *(_QWORD *)(v16 + 8));
      v12 = 0;
    }
    else
    {
      v64[0] = -1072873844;
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( v64[0] < 0 && *((_DWORD *)v26 + 499) != v64[0] )
          CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams", 3838, v64[0]);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          245,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          v64[0]);
      v12 = v64[0];
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( v64[0] < 0 && *((_DWORD *)v11 + 499) != v64[0] )
        CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams", 3794, v64[0]);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        244,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        v64[0]);
    v12 = v64[0];
  }
LABEL_127:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v64[1]);
  return v12;
}

```

## disassembly

```asm
0x18001895c  mov     rax, rsp
0x18001895f  push    rbp
0x180018960  push    rbx
0x180018961  push    rsi
0x180018962  push    rdi
0x180018963  push    r12
0x180018965  push    r13
0x180018967  push    r14
0x180018969  push    r15
0x18001896b  lea     rbp, [rax-0C8h]
0x180018972  sub     rsp, 188h
0x180018979  movaps  xmmword ptr [rax-58h], xmm6
0x18001897d  movaps  xmmword ptr [rax-68h], xmm7
0x180018981  movaps  xmmword ptr [rax-78h], xmm8
0x180018986  movaps  xmmword ptr [rax-88h], xmm9
0x18001898e  mov     rax, cs:__security_cookie
0x180018995  xor     rax, rsp
0x180018998  mov     [rbp+0C0h+var_88], rax
0x18001899c  mov     r15, rdx
0x18001899f  mov     rsi, rcx
0x1800189a2  xor     r13d, r13d
0x1800189a5  mov     [rsp+1C0h+var_190], r13d
0x1800189aa  mov     r8d, 0ECBh; int
0x1800189b0  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800189b7  lea     rcx, [rsp+1C0h+var_190+4]; this
0x1800189bc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800189c1  nop
0x1800189c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800189c9  cmp     [rcx+8], r13b
0x1800189cd  jz      short loc_180018A1A
0x1800189cf  cmp     [rsi+10h], r13
0x1800189d3  jz      short loc_180018A1A
0x1800189d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800189da  mov     rdi, rax
0x1800189dd  mov     rcx, [rsi+10h]
0x1800189e1  mov     rdx, [rcx]
0x1800189e4  mov     rax, [rdx+128h]
0x1800189eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189f0  mov     ebx, eax
0x1800189f2  mov     rcx, [rsi+10h]
0x1800189f6  mov     rdx, [rcx]
0x1800189f9  mov     rax, [rdx+118h]
0x180018a00  lea     rdx, [rbp+0C0h+var_98]
0x180018a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a09  movups  xmm0, xmmword ptr [rax]
0x180018a0c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180018a14  mov     [rdi+7E0h], ebx
0x180018a1a  mov     [rbp+0C0h+var_98], rsi
0x180018a1e  lea     rax, [rsp+1C0h+var_190]
0x180018a23  mov     [rbp+0C0h+var_90], rax
0x180018a27  mov     [rsp+1C0h+var_180], r13d
0x180018a2c  mov     rcx, [rsi+18h]
0x180018a30  mov     rax, [rcx]
0x180018a33  lea     rdx, [rsp+1C0h+var_180]
0x180018a38  mov     rax, [rax+108h]
0x180018a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a44  mov     [rsp+1C0h+var_190], eax
0x180018a48  test    eax, eax
0x180018a4a  jns     loc_180018B0F
0x180018a50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018a57  test    rcx, rcx
0x180018a5a  jnz     short loc_180018AA3
0x180018a5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018a63  nop     dword ptr [rax+rax+00h]
0x180018a68  mov     rcx, rax
0x180018a6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018a72  test    rax, rax
0x180018a75  jz      short loc_180018A95
0x180018a77  mov     rax, [rax]
0x180018a7a  mov     edx, 7F0h
0x180018a7f  mov     rax, [rax+8]
0x180018a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a88  test    eax, eax
0x180018a8a  jz      short loc_180018A95
0x180018a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018a93  jmp     short loc_180018AA3
0x180018a95  lea     rcx, qword_1800DBF70; this
0x180018a9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018aa3  cmp     [rcx+8], r13b
0x180018aa7  jz      short loc_180018AD6
0x180018aa9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018aae  mov     r9d, [rsp+1C0h+var_190]; int
0x180018ab3  test    r9d, r9d
0x180018ab6  jns     short loc_180018AD6
0x180018ab8  cmp     [rax+7CCh], r9d
0x180018abf  jz      short loc_180018AD6
0x180018ac1  mov     r8d, 0ED2h; int
0x180018ac7  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018ace  mov     rcx, rax; this
0x180018ad1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018ad6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018add  jb      short loc_180018B06
0x180018adf  mov     edx, 0F4h
0x180018ae4  mov     eax, [rsp+1C0h+var_190]
0x180018ae8  mov     [rsp+1C0h+var_1A0], eax
0x180018aec  mov     r9, rsi
0x180018aef  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180018afd  mov     rcx, [rcx+10h]
0x180018b01  call    WPP_SF_qD
0x180018b06  mov     ebx, [rsp+1C0h+var_190]
0x180018b0a  jmp     loc_1800192AF
0x180018b0f  mov     r12, [rsi+8]
0x180018b13  mov     rdi, [r12+240h]
0x180018b1b  mov     dword ptr [rsp+1C0h+var_168+0Ch], r13d
0x180018b20  mov     dword ptr [rbp+0C0h+var_130+1], r13d
0x180018b24  mov     word ptr [rbp+0C0h+var_130+5], r13w
0x180018b29  mov     byte ptr [rbp+0C0h+var_130+7], r13b
0x180018b2d  xorps   xmm7, xmm7
0x180018b30  mov     r14, r13
0x180018b33  mov     qword ptr [rbp+0C0h+var_140], r13
0x180018b37  mov     dword ptr [rsp+1C0h+var_168+8], 0FFFFFFFFh
0x180018b3f  mov     qword ptr [rsp+1C0h+var_158], r13
0x180018b44  mov     byte ptr [rbp+0C0h+var_130], r13b
0x180018b48  mov     qword ptr [rbp+0C0h+var_140+8], r13
0x180018b4c  mov     rbx, [rdi]
0x180018b4f  mov     [rsp+1C0h+var_188], rbx
0x180018b54  movsd   xmm8, [rbp+0C0h+var_130]
0x180018b5a  movups  xmm6, [rbp+0C0h+var_140]
0x180018b5e  movups  xmm9, [rsp+1C0h+var_168+8]
0x180018b64  cmp     rbx, rdi
0x180018b67  jz      loc_180018CA1
0x180018b6d  mov     rbx, [rbx+28h]
0x180018b71  mov     qword ptr [rsp+1C0h+var_170], rbx
0x180018b76  lea     rcx, [rsp+1C0h+var_170]
0x180018b7b  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180018b80  nop
0x180018b81  mov     rax, [rbx]
0x180018b84  mov     rcx, rbx
0x180018b87  mov     rax, [rax+78h]
0x180018b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b90  test    al, al
0x180018b92  jz      short loc_180018B99
0x180018b94  jmp     loc_180018C78
0x180018b99  mov     r8, r15
0x180018b9c  lea     rdx, [rbp+0C0h+var_D0]
0x180018ba0  mov     rcx, rbx
0x180018ba3  call    ?GetSeekInfoForTime@MkvMfStream@MkvMfSourceLib@@QEAA?BVSeekInfo@2@_J@Z; MkvMfSourceLib::MkvMfStream::GetSeekInfoForTime(__int64)
0x180018ba8  mov     rcx, qword ptr [rbp+0C0h+var_B0]
0x180018bac  test    rcx, rcx
0x180018baf  jz      short loc_180018C0A
0x180018bb1  movsd   xmm0, [rbp+0C0h+var_A0]
0x180018bb6  movups  xmm1, [rbp+0C0h+var_B0]
0x180018bba  movups  xmm2, [rbp+0C0h+var_C0]
0x180018bbe  movups  xmm3, [rbp+0C0h+var_D0]
0x180018bc2  test    r14, r14
0x180018bc5  jz      short loc_180018BDD
0x180018bc7  mov     rax, [rcx+8]
0x180018bcb  cmp     rax, [r14+8]
0x180018bcf  jl      short loc_180018BDD
0x180018bd1  jnz     short loc_180018BF0
0x180018bd3  mov     rax, [r14+10h]
0x180018bd7  cmp     [rcx+10h], rax
0x180018bdb  jge     short loc_180018BF0
0x180018bdd  movups  xmm9, xmm3
0x180018be1  movups  xmm7, xmm2
0x180018be4  movups  xmm6, xmm1
0x180018be7  movaps  xmm8, xmm0
0x180018beb  movq    r14, xmm1
0x180018bf0  movaps  [rsp+1C0h+var_168+8], xmm3
0x180018bf5  movaps  [rsp+1C0h+var_158+8], xmm2
0x180018bfa  movaps  [rbp+0C0h+var_140], xmm1
0x180018bfe  movsd   [rbp+0C0h+var_130], xmm0
0x180018c03  lea     rdx, [rsp+1C0h+var_168+8]
0x180018c08  jmp     short loc_180018C5B
0x180018c0a  mov     dword ptr [rsp+1C0h+var_168+0Ch], r13d
0x180018c0f  mov     dword ptr [rbp+0C0h+var_130+1], r13d
0x180018c13  mov     word ptr [rbp+0C0h+var_130+5], r13w
0x180018c18  mov     byte ptr [rbp+0C0h+var_130+7], r13b
0x180018c1c  xorps   xmm1, xmm1
0x180018c1f  mov     qword ptr [rbp+0C0h+var_140], r13
0x180018c23  mov     dword ptr [rsp+1C0h+var_168+8], 0FFFFFFFFh
0x180018c2b  mov     qword ptr [rsp+1C0h+var_158], r13
0x180018c30  mov     byte ptr [rbp+0C0h+var_130], r13b
0x180018c34  mov     qword ptr [rbp+0C0h+var_140+8], r13
0x180018c38  movups  xmm0, [rsp+1C0h+var_168+8]
0x180018c3d  movaps  [rbp+0C0h+var_110], xmm0
0x180018c41  movaps  [rbp+0C0h+var_100], xmm1
0x180018c45  movups  xmm0, [rbp+0C0h+var_140]
0x180018c49  movaps  [rbp+0C0h+var_F0], xmm0
0x180018c4d  movsd   xmm1, [rbp+0C0h+var_130]
0x180018c52  movsd   [rbp+0C0h+var_E0], xmm1
0x180018c57  lea     rdx, [rbp+0C0h+var_110]
0x180018c5b  mov     rax, [rbx]
0x180018c5e  mov     rcx, rbx
0x180018c61  mov     rax, [rax+98h]
0x180018c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c6d  mov     qword ptr [rbx+110h], 4C4B40h
0x180018c78  test    rbx, rbx
0x180018c7b  jz      short loc_180018C8D
0x180018c7d  mov     rax, [rbx]
0x180018c80  mov     rcx, rbx
0x180018c83  mov     rax, [rax+10h]
0x180018c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c8c  nop
0x180018c8d  lea     rcx, [rsp+1C0h+var_188]
0x180018c92  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180018c97  mov     rbx, [rsp+1C0h+var_188]
0x180018c9c  jmp     loc_180018B64
0x180018ca1  test    r14, r14
0x180018ca4  jnz     loc_180018D72
0x180018caa  mov     [rsp+1C0h+var_190], 0C00D3E8Ch
0x180018cb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018cb9  test    rcx, rcx
0x180018cbc  jnz     short loc_180018D05
0x180018cbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018cc5  nop     dword ptr [rax+rax+00h]
0x180018cca  mov     rcx, rax
0x180018ccd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018cd4  test    rax, rax
0x180018cd7  jz      short loc_180018CF7
0x180018cd9  mov     rax, [rax]
0x180018cdc  mov     edx, 7F0h
0x180018ce1  mov     rax, [rax+8]
0x180018ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cea  test    eax, eax
0x180018cec  jz      short loc_180018CF7
0x180018cee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018cf5  jmp     short loc_180018D05
0x180018cf7  lea     rcx, qword_1800DBF70; this
0x180018cfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018d05  cmp     [rcx+8], r13b
0x180018d09  jz      short loc_180018D38
0x180018d0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018d10  mov     r9d, [rsp+1C0h+var_190]; int
0x180018d15  test    r9d, r9d
0x180018d18  jns     short loc_180018D38
0x180018d1a  cmp     [rax+7CCh], r9d
0x180018d21  jz      short loc_180018D38
0x180018d23  mov     r8d, 0EFEh; int
0x180018d29  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018d30  mov     rcx, rax; this
0x180018d33  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018d38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018d3f  jb      short loc_180018D69
0x180018d41  mov     edx, 0F5h
0x180018d46  mov     eax, [rsp+1C0h+var_190]
0x180018d4a  mov     [rsp+1C0h+var_1A0], eax
0x180018d4e  mov     r9, rsi
0x180018d51  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d5f  mov     rcx, [rcx+10h]
0x180018d63  call    WPP_SF_qD
0x180018d68  nop
0x180018d69  mov     ebx, [rsp+1C0h+var_190]
0x180018d6d  jmp     loc_1800192D4
0x180018d72  mov     r15d, r13d
0x180018d75  cmp     r15d, [rsp+1C0h+var_180]
0x180018d7a  jnb     loc_1800192B1
0x180018d80  mov     dword ptr [rsp+1C0h+var_178], r13d
0x180018d85  mov     [rsp+1C0h+var_188], r13
0x180018d8a  mov     rcx, [rsi+18h]
0x180018d8e  mov     rax, [rcx]
0x180018d91  lea     r9, [rsp+1C0h+var_188]
0x180018d96  lea     r8, [rsp+1C0h+var_178]
0x180018d9b  mov     edx, r15d
0x180018d9e  mov     rax, [rax+110h]
0x180018da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018daa  mov     [rsp+1C0h+var_190], eax
0x180018dae  test    eax, eax
0x180018db0  js      loc_1800191EA
0x180018db6  mov     [rsp+1C0h+var_17C], r13d
0x180018dbb  mov     rcx, [rsp+1C0h+var_188]
0x180018dc0  mov     rax, [rcx]
0x180018dc3  lea     rdx, [rsp+1C0h+var_17C]
0x180018dc8  mov     rax, [rax+108h]
0x180018dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dd4  mov     [rsp+1C0h+var_190], eax
0x180018dd8  test    eax, eax
0x180018dda  js      loc_18001914D
0x180018de0  lea     rdx, [rsp+1C0h+var_17C]
0x180018de5  lea     rcx, [r12+240h]
0x180018ded  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::_Find<ulong>(ulong const &)
0x180018df2  cmp     rax, rdi
0x180018df5  jz      loc_180018EB2
0x180018dfb  mov     rbx, [rax+28h]
0x180018dff  mov     [rbp+0C0h+var_120], rbx
0x180018e03  lea     rcx, [rbp+0C0h+var_120]
0x180018e07  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180018e0c  nop
0x180018e0d  mov     rcx, rbx; this
0x180018e10  cmp     dword ptr [rsp+1C0h+var_178], r13d
0x180018e15  jnz     short loc_180018E2A
0x180018e17  call    ?Deselect@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Deselect(void)
0x180018e1c  mov     [rsp+1C0h+var_190], eax
0x180018e20  test    eax, eax
0x180018e22  js      loc_180018EC4
0x180018e28  jmp     short loc_180018E9D
0x180018e2a  mov     [rsp+1C0h+var_170], r13d
0x180018e2f  lea     rdx, [rsp+1C0h+var_170]; unsigned int *
0x180018e34  call    ?Select@MkvMfStream@MkvMfSourceLib@@QEAAJPEAK@Z; MkvMfSourceLib::MkvMfStream::Select(ulong *)
0x180018e39  mov     [rsp+1C0h+var_190], eax
0x180018e3d  test    eax, eax
0x180018e3f  js      loc_180019079
0x180018e45  mov     r8, rbx; struct MkvMfSourceLib::MkvMfStream *
0x180018e48  mov     edx, [rsp+1C0h+var_170]; unsigned int
0x180018e4c  mov     rcx, [rsi+8]; this
0x180018e50  call    ?QueueStreamEvent@MkvMfSource@MkvMfSourceLib@@AEBAJKPEAVMkvMfStream@2@@Z; MkvMfSourceLib::MkvMfSource::QueueStreamEvent(ulong,MkvMfSourceLib::MkvMfStream *)
0x180018e55  mov     [rsp+1C0h+var_190], eax
0x180018e59  test    eax, eax
  ... truncated ...
```
