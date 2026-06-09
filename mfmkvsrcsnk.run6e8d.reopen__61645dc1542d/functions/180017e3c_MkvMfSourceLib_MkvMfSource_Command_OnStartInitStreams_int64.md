# MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)

- ea: `0x180017e3c`
- end: `0x1800187ce`
- name: `?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z`
- size: `2450`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180016dd8`
- `0x180017460`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000c790`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x180017e3c`
- `0x18001b044`
- `0x180020d84`
- `0x1800217b0`
- `0x1800233b4`
- `0x180023428`
- `0x180025e34`
- `0x180044d58`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017f3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800183a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001847f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001854d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001861b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800186b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017f3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800183a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001847f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001854d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001861b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800186b2`

## string_xrefs

- `0x180017e90`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180017fa1`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x1800181fd`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018409`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x1800184e4`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x1800185b2`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018680`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`
- `0x180018717`: `MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams`

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
              v59 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v55 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v52 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v49 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v45 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180017e3c  mov     rax, rsp
0x180017e3f  push    rbp
0x180017e40  push    rbx
0x180017e41  push    rsi
0x180017e42  push    rdi
0x180017e43  push    r12
0x180017e45  push    r13
0x180017e47  push    r14
0x180017e49  push    r15
0x180017e4b  lea     rbp, [rax-0C8h]
0x180017e52  sub     rsp, 188h
0x180017e59  movaps  xmmword ptr [rax-58h], xmm6
0x180017e5d  movaps  xmmword ptr [rax-68h], xmm7
0x180017e61  movaps  xmmword ptr [rax-78h], xmm8
0x180017e66  movaps  xmmword ptr [rax-88h], xmm9
0x180017e6e  mov     rax, cs:__security_cookie
0x180017e75  xor     rax, rsp
0x180017e78  mov     [rbp+0C0h+var_88], rax
0x180017e7c  mov     r15, rdx
0x180017e7f  mov     rsi, rcx
0x180017e82  xor     r13d, r13d
0x180017e85  mov     [rsp+1C0h+var_190], r13d
0x180017e8a  mov     r8d, 0ECBh; int
0x180017e90  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017e97  lea     rcx, [rsp+1C0h+var_190+4]; this
0x180017e9c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180017ea1  nop
0x180017ea2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180017ea9  cmp     [rcx+8], r13b
0x180017ead  jz      short loc_180017EFA
0x180017eaf  cmp     [rsi+10h], r13
0x180017eb3  jz      short loc_180017EFA
0x180017eb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017eba  mov     rdi, rax
0x180017ebd  mov     rcx, [rsi+10h]
0x180017ec1  mov     rdx, [rcx]
0x180017ec4  mov     rax, [rdx+128h]
0x180017ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ed0  mov     ebx, eax
0x180017ed2  mov     rcx, [rsi+10h]
0x180017ed6  mov     rdx, [rcx]
0x180017ed9  mov     rax, [rdx+118h]
0x180017ee0  lea     rdx, [rbp+0C0h+var_98]
0x180017ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ee9  movups  xmm0, xmmword ptr [rax]
0x180017eec  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180017ef4  mov     [rdi+7E0h], ebx
0x180017efa  mov     [rbp+0C0h+var_98], rsi
0x180017efe  lea     rax, [rsp+1C0h+var_190]
0x180017f03  mov     [rbp+0C0h+var_90], rax
0x180017f07  mov     [rsp+1C0h+var_180], r13d
0x180017f0c  mov     rcx, [rsi+18h]
0x180017f10  mov     rax, [rcx]
0x180017f13  lea     rdx, [rsp+1C0h+var_180]
0x180017f18  mov     rax, [rax+108h]
0x180017f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f24  mov     [rsp+1C0h+var_190], eax
0x180017f28  test    eax, eax
0x180017f2a  jns     loc_180017FE9
0x180017f30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017f37  test    rcx, rcx
0x180017f3a  jnz     short loc_180017F7D
0x180017f3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017f42  mov     rcx, rax
0x180017f45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017f4c  test    rax, rax
0x180017f4f  jz      short loc_180017F6F
0x180017f51  mov     rax, [rax]
0x180017f54  mov     edx, 7F0h
0x180017f59  mov     rax, [rax+8]
0x180017f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f62  test    eax, eax
0x180017f64  jz      short loc_180017F6F
0x180017f66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017f6d  jmp     short loc_180017F7D
0x180017f6f  lea     rcx, qword_1800D6F70; this
0x180017f76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017f7d  cmp     [rcx+8], r13b
0x180017f81  jz      short loc_180017FB0
0x180017f83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017f88  mov     r9d, [rsp+1C0h+var_190]; int
0x180017f8d  test    r9d, r9d
0x180017f90  jns     short loc_180017FB0
0x180017f92  cmp     [rax+7CCh], r9d
0x180017f99  jz      short loc_180017FB0
0x180017f9b  mov     r8d, 0ED2h; int
0x180017fa1  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017fa8  mov     rcx, rax; this
0x180017fab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017fb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017fb7  jb      short loc_180017FE0
0x180017fb9  mov     edx, 0F4h
0x180017fbe  mov     eax, [rsp+1C0h+var_190]
0x180017fc2  mov     [rsp+1C0h+var_1A0], eax
0x180017fc6  mov     r9, rsi
0x180017fc9  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fd7  mov     rcx, [rcx+10h]
0x180017fdb  call    WPP_SF_qD
0x180017fe0  mov     ebx, [rsp+1C0h+var_190]
0x180017fe4  jmp     loc_180018765
0x180017fe9  mov     r12, [rsi+8]
0x180017fed  mov     rdi, [r12+240h]
0x180017ff5  mov     dword ptr [rsp+1C0h+var_168+0Ch], r13d
0x180017ffa  mov     dword ptr [rbp+0C0h+var_130+1], r13d
0x180017ffe  mov     word ptr [rbp+0C0h+var_130+5], r13w
0x180018003  mov     byte ptr [rbp+0C0h+var_130+7], r13b
0x180018007  xorps   xmm7, xmm7
0x18001800a  mov     r14, r13
0x18001800d  mov     qword ptr [rbp+0C0h+var_140], r13
0x180018011  mov     dword ptr [rsp+1C0h+var_168+8], 0FFFFFFFFh
0x180018019  mov     qword ptr [rsp+1C0h+var_158], r13
0x18001801e  mov     byte ptr [rbp+0C0h+var_130], r13b
0x180018022  mov     qword ptr [rbp+0C0h+var_140+8], r13
0x180018026  mov     rbx, [rdi]
0x180018029  mov     [rsp+1C0h+var_188], rbx
0x18001802e  movsd   xmm8, [rbp+0C0h+var_130]
0x180018034  movups  xmm6, [rbp+0C0h+var_140]
0x180018038  movups  xmm9, [rsp+1C0h+var_168+8]
0x18001803e  cmp     rbx, rdi
0x180018041  jz      loc_18001817B
0x180018047  mov     rbx, [rbx+28h]
0x18001804b  mov     qword ptr [rsp+1C0h+var_170], rbx
0x180018050  lea     rcx, [rsp+1C0h+var_170]
0x180018055  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18001805a  nop
0x18001805b  mov     rax, [rbx]
0x18001805e  mov     rcx, rbx
0x180018061  mov     rax, [rax+78h]
0x180018065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001806a  test    al, al
0x18001806c  jz      short loc_180018073
0x18001806e  jmp     loc_180018152
0x180018073  mov     r8, r15
0x180018076  lea     rdx, [rbp+0C0h+var_D0]
0x18001807a  mov     rcx, rbx
0x18001807d  call    ?GetSeekInfoForTime@MkvMfStream@MkvMfSourceLib@@QEAA?BVSeekInfo@2@_J@Z; MkvMfSourceLib::MkvMfStream::GetSeekInfoForTime(__int64)
0x180018082  mov     rcx, qword ptr [rbp+0C0h+var_B0]
0x180018086  test    rcx, rcx
0x180018089  jz      short loc_1800180E4
0x18001808b  movsd   xmm0, [rbp+0C0h+var_A0]
0x180018090  movups  xmm1, [rbp+0C0h+var_B0]
0x180018094  movups  xmm2, [rbp+0C0h+var_C0]
0x180018098  movups  xmm3, [rbp+0C0h+var_D0]
0x18001809c  test    r14, r14
0x18001809f  jz      short loc_1800180B7
0x1800180a1  mov     rax, [rcx+8]
0x1800180a5  cmp     rax, [r14+8]
0x1800180a9  jl      short loc_1800180B7
0x1800180ab  jnz     short loc_1800180CA
0x1800180ad  mov     rax, [r14+10h]
0x1800180b1  cmp     [rcx+10h], rax
0x1800180b5  jge     short loc_1800180CA
0x1800180b7  movups  xmm9, xmm3
0x1800180bb  movups  xmm7, xmm2
0x1800180be  movups  xmm6, xmm1
0x1800180c1  movaps  xmm8, xmm0
0x1800180c5  movq    r14, xmm1
0x1800180ca  movaps  [rsp+1C0h+var_168+8], xmm3
0x1800180cf  movaps  [rsp+1C0h+var_158+8], xmm2
0x1800180d4  movaps  [rbp+0C0h+var_140], xmm1
0x1800180d8  movsd   [rbp+0C0h+var_130], xmm0
0x1800180dd  lea     rdx, [rsp+1C0h+var_168+8]
0x1800180e2  jmp     short loc_180018135
0x1800180e4  mov     dword ptr [rsp+1C0h+var_168+0Ch], r13d
0x1800180e9  mov     dword ptr [rbp+0C0h+var_130+1], r13d
0x1800180ed  mov     word ptr [rbp+0C0h+var_130+5], r13w
0x1800180f2  mov     byte ptr [rbp+0C0h+var_130+7], r13b
0x1800180f6  xorps   xmm1, xmm1
0x1800180f9  mov     qword ptr [rbp+0C0h+var_140], r13
0x1800180fd  mov     dword ptr [rsp+1C0h+var_168+8], 0FFFFFFFFh
0x180018105  mov     qword ptr [rsp+1C0h+var_158], r13
0x18001810a  mov     byte ptr [rbp+0C0h+var_130], r13b
0x18001810e  mov     qword ptr [rbp+0C0h+var_140+8], r13
0x180018112  movups  xmm0, [rsp+1C0h+var_168+8]
0x180018117  movaps  [rbp+0C0h+var_110], xmm0
0x18001811b  movaps  [rbp+0C0h+var_100], xmm1
0x18001811f  movups  xmm0, [rbp+0C0h+var_140]
0x180018123  movaps  [rbp+0C0h+var_F0], xmm0
0x180018127  movsd   xmm1, [rbp+0C0h+var_130]
0x18001812c  movsd   [rbp+0C0h+var_E0], xmm1
0x180018131  lea     rdx, [rbp+0C0h+var_110]
0x180018135  mov     rax, [rbx]
0x180018138  mov     rcx, rbx
0x18001813b  mov     rax, [rax+98h]
0x180018142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018147  mov     qword ptr [rbx+110h], 4C4B40h
0x180018152  test    rbx, rbx
0x180018155  jz      short loc_180018167
0x180018157  mov     rax, [rbx]
0x18001815a  mov     rcx, rbx
0x18001815d  mov     rax, [rax+10h]
0x180018161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018166  nop
0x180018167  lea     rcx, [rsp+1C0h+var_188]
0x18001816c  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180018171  mov     rbx, [rsp+1C0h+var_188]
0x180018176  jmp     loc_18001803E
0x18001817b  test    r14, r14
0x18001817e  jnz     loc_180018246
0x180018184  mov     [rsp+1C0h+var_190], 0C00D3E8Ch
0x18001818c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018193  test    rcx, rcx
0x180018196  jnz     short loc_1800181D9
0x180018198  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001819e  mov     rcx, rax
0x1800181a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181a8  test    rax, rax
0x1800181ab  jz      short loc_1800181CB
0x1800181ad  mov     rax, [rax]
0x1800181b0  mov     edx, 7F0h
0x1800181b5  mov     rax, [rax+8]
0x1800181b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181be  test    eax, eax
0x1800181c0  jz      short loc_1800181CB
0x1800181c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181c9  jmp     short loc_1800181D9
0x1800181cb  lea     rcx, qword_1800D6F70; this
0x1800181d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181d9  cmp     [rcx+8], r13b
0x1800181dd  jz      short loc_18001820C
0x1800181df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800181e4  mov     r9d, [rsp+1C0h+var_190]; int
0x1800181e9  test    r9d, r9d
0x1800181ec  jns     short loc_18001820C
0x1800181ee  cmp     [rax+7CCh], r9d
0x1800181f5  jz      short loc_18001820C
0x1800181f7  mov     r8d, 0EFEh; int
0x1800181fd  lea     rdx, aMkvmfsourcelib_122; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018204  mov     rcx, rax; this
0x180018207  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001820c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018213  jb      short loc_18001823D
0x180018215  mov     edx, 0F5h
0x18001821a  mov     eax, [rsp+1C0h+var_190]
0x18001821e  mov     [rsp+1C0h+var_1A0], eax
0x180018222  mov     r9, rsi
0x180018225  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001822c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018233  mov     rcx, [rcx+10h]
0x180018237  call    WPP_SF_qD
0x18001823c  nop
0x18001823d  mov     ebx, [rsp+1C0h+var_190]
0x180018241  jmp     loc_18001878A
0x180018246  mov     r15d, r13d
0x180018249  cmp     r15d, [rsp+1C0h+var_180]
0x18001824e  jnb     loc_180018767
0x180018254  mov     dword ptr [rsp+1C0h+var_178], r13d
0x180018259  mov     [rsp+1C0h+var_188], r13
0x18001825e  mov     rcx, [rsi+18h]
0x180018262  mov     rax, [rcx]
0x180018265  lea     r9, [rsp+1C0h+var_188]
0x18001826a  lea     r8, [rsp+1C0h+var_178]
0x18001826f  mov     edx, r15d
0x180018272  mov     rax, [rax+110h]
0x180018279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001827e  mov     [rsp+1C0h+var_190], eax
0x180018282  test    eax, eax
0x180018284  js      loc_1800186A6
0x18001828a  mov     [rsp+1C0h+var_17C], r13d
0x18001828f  mov     rcx, [rsp+1C0h+var_188]
0x180018294  mov     rax, [rcx]
0x180018297  lea     rdx, [rsp+1C0h+var_17C]
0x18001829c  mov     rax, [rax+108h]
0x1800182a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182a8  mov     [rsp+1C0h+var_190], eax
0x1800182ac  test    eax, eax
0x1800182ae  js      loc_18001860F
0x1800182b4  lea     rdx, [rsp+1C0h+var_17C]
0x1800182b9  lea     rcx, [r12+240h]
0x1800182c1  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::_Find<ulong>(ulong const &)
0x1800182c6  cmp     rax, rdi
0x1800182c9  jz      loc_180018386
0x1800182cf  mov     rbx, [rax+28h]
0x1800182d3  mov     [rbp+0C0h+var_120], rbx
0x1800182d7  lea     rcx, [rbp+0C0h+var_120]
0x1800182db  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x1800182e0  nop
0x1800182e1  mov     rcx, rbx; this
0x1800182e4  cmp     dword ptr [rsp+1C0h+var_178], r13d
0x1800182e9  jnz     short loc_1800182FE
0x1800182eb  call    ?Deselect@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Deselect(void)
0x1800182f0  mov     [rsp+1C0h+var_190], eax
0x1800182f4  test    eax, eax
0x1800182f6  js      loc_180018398
0x1800182fc  jmp     short loc_180018371
0x1800182fe  mov     [rsp+1C0h+var_170], r13d
0x180018303  lea     rdx, [rsp+1C0h+var_170]; unsigned int *
0x180018308  call    ?Select@MkvMfStream@MkvMfSourceLib@@QEAAJPEAK@Z; MkvMfSourceLib::MkvMfStream::Select(ulong *)
0x18001830d  mov     [rsp+1C0h+var_190], eax
0x180018311  test    eax, eax
0x180018313  js      loc_180018541
0x180018319  mov     r8, rbx; struct MkvMfSourceLib::MkvMfStream *
0x18001831c  mov     edx, [rsp+1C0h+var_170]; unsigned int
0x180018320  mov     rcx, [rsi+8]; this
0x180018324  call    ?QueueStreamEvent@MkvMfSource@MkvMfSourceLib@@AEBAJKPEAVMkvMfStream@2@@Z; MkvMfSourceLib::MkvMfSource::QueueStreamEvent(ulong,MkvMfSourceLib::MkvMfStream *)
0x180018329  mov     [rsp+1C0h+var_190], eax
0x18001832d  test    eax, eax
0x18001832f  js      loc_180018473
0x180018335  lea     rdx, [rbp+0C0h+var_110]
  ... truncated ...
```
