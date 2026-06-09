# CFLACMetadataWriter::WriteEditedMetadataFromPropHandler(IStream *,IStream *)

- ea: `0x180033730`
- end: `0x18003404f`
- name: `?WriteEditedMetadataFromPropHandler@CFLACMetadataWriter@@QEAAJPEAUIStream@@0@Z`
- size: `2335`
- prototype: `__int64 __fastcall(CFLACMetadataWriter *__hidden this, struct IStream *, struct IStream *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002d340`

## callees

- `0x1800018a4`
- `0x180001e80`
- `0x180001ea4`
- `0x180002e50`
- `0x180003150`
- `0x1800031f0`
- `0x180003260`
- `0x1800032a0`
- `0x1800032e0`
- `0x1800034d0`
- `0x180003600`
- `0x1800037e0`
- `0x1800037f0`
- `0x180003810`
- `0x180003880`
- `0x180003a00`
- `0x180003ba0`
- `0x180003c20`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x1800313d4`
- `0x180031bdc`
- `0x180031ca4`
- `0x180033730`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800337bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003386d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033935`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800339e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033ad2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033b82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033c87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033d3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033df5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033f49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800337bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003386d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033935`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800339e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033ad2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033b82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033c87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033d3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033df5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033f49`

## string_xrefs

- `0x180033769`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033818`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x1800338ca`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033992`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033a46`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033b2f`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033bdf`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033ce4`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033d9b`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033e52`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033efc`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`
- `0x180033fa6`: `CFLACMetadataWriter::WriteEditedMetadataFromPropHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFLACMetadataWriter::WriteEditedMetadataFromPropHandler(
        CFLACMetadataWriter *this,
        struct IStream *a2,
        struct IStream *a3)
{
  struct FLAC::Metadata::VorbisComment *block; // r12
  __int64 v7; // rdx
  struct FLAC__IOCallbacks *v8; // r15
  int v9; // ebx
  int inserted; // edi
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  struct FLAC__IOCallbacks *Callbacks; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  FLAC::Metadata::VorbisComment *v28; // rax
  struct FLAC::Metadata::Prototype *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  bool v39; // al
  __int128 v40; // xmm1
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  _BYTE v63[16]; // [rsp+30h] [rbp-79h] BYREF
  __int128 v64; // [rsp+40h] [rbp-69h] BYREF
  __int128 v65; // [rsp+50h] [rbp-59h]
  __int128 v66; // [rsp+60h] [rbp-49h]
  __int128 v67; // [rsp+70h] [rbp-39h] BYREF
  __int128 v68; // [rsp+80h] [rbp-29h]
  __int128 v69; // [rsp+90h] [rbp-19h]
  FLAC::Metadata::VorbisComment *v70; // [rsp+A0h] [rbp-9h]
  _BYTE v71[16]; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v72[16]; // [rsp+B8h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v63,
    "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
    527);
  FLAC::Metadata::Chain::Chain((FLAC::Metadata::Chain *)v72);
  FLAC::Metadata::Iterator::Iterator((FLAC::Metadata::Iterator *)v71);
  block = 0;
  if ( FLAC::Metadata::Iterator::is_valid((FLAC::Metadata::Iterator *)v72) )
  {
    CFLACMetadataCallbackFactory::m_fStreamIsIMFBytestream = 0;
    Callbacks = CFLACMetadataCallbackFactory::GetCallbacks();
    v8 = Callbacks;
    if ( Callbacks )
    {
      v64 = *(_OWORD *)Callbacks;
      v65 = *((_OWORD *)Callbacks + 1);
      v66 = *((_OWORD *)Callbacks + 2);
      if ( (unsigned __int8)FLAC::Metadata::Chain::read(v72, a2, &v64, 0) )
      {
        FLAC::Metadata::Iterator::init((FLAC::Metadata::Iterator *)v71, (struct FLAC::Metadata::Chain *)v72);
        if ( FLAC::Metadata::Iterator::is_valid((FLAC::Metadata::Iterator *)v71) )
        {
          do
          {
            if ( (unsigned int)FLAC::Metadata::Iterator::get_block_type(v71) == 4 )
              goto LABEL_62;
          }
          while ( FLAC::Metadata::Iterator::next((FLAC::Metadata::Iterator *)v71) );
          v28 = (FLAC::Metadata::VorbisComment *)operator new(0x18u);
          v70 = v28;
          if ( v28 )
            v29 = (struct FLAC::Metadata::Prototype *)FLAC::Metadata::VorbisComment::VorbisComment(v28);
          else
            v29 = 0;
          if ( !FLAC::Metadata::Iterator::insert_block_after((FLAC::Metadata::Iterator *)v71, v29) )
          {
            v9 = -2147467259;
            inserted = -2147467259;
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
              {
                v31 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v31 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                  569,
                  -2147467259);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v14 = 58;
              goto LABEL_12;
            }
            goto LABEL_130;
          }
LABEL_62:
          block = FLAC::Metadata::Iterator::get_block((FLAC::Metadata::Iterator *)v71);
          inserted = CFLACMetadataWriter::InsertPropertiesIntoVorbisComment(this, block);
          if ( inserted >= 0 )
          {
            v39 = FLAC::Metadata::Chain::check_if_tempfile_needed((FLAC::Metadata::Chain *)v72, 1);
            v40 = *((_OWORD *)v8 + 1);
            LOBYTE(v41) = 1;
            if ( v39 )
            {
              v64 = *(_OWORD *)v8;
              v65 = v40;
              v66 = *((_OWORD *)v8 + 2);
              v67 = *(_OWORD *)v8;
              v68 = *((_OWORD *)v8 + 1);
              v69 = *((_OWORD *)v8 + 2);
              if ( !(unsigned __int8)FLAC::Metadata::Chain::write(v72, v41, a2, &v67, a3, &v64) )
              {
                v9 = -2147467259;
                inserted = -2147467259;
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
                  CallStackTracing::s_wpInstance = v44;
                  if ( v44
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                  {
                    v43 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v43 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v43 + 8) )
                {
                  v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                  if ( *((_DWORD *)v45 + 499) != -2147467259 )
                    CallStackContext::TraceFailure(
                      v45,
                      "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                      584,
                      -2147467259);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v14 = 60;
                  goto LABEL_12;
                }
                goto LABEL_130;
              }
            }
            else
            {
              v67 = *(_OWORD *)v8;
              v68 = v40;
              v69 = *((_OWORD *)v8 + 2);
              if ( !(unsigned __int8)FLAC::Metadata::Chain::write(v72, v41, a3, &v67) )
              {
                v9 = -2147467259;
                inserted = -2147467259;
                v47 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != -2147467259 )
                    CallStackContext::TraceFailure(
                      v49,
                      "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                      591,
                      -2147467259);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v14 = 61;
                  goto LABEL_12;
                }
                goto LABEL_130;
              }
            }
            inserted = ((__int64 (__fastcall *)(struct IStream *, struct IStream *, __int64, _QWORD, _QWORD))a2->lpVtbl->CopyTo)(
                         a2,
                         a3,
                         -1,
                         0,
                         0);
            if ( inserted >= 0 )
            {
              inserted = ((__int64 (__fastcall *)(struct IStream *, _QWORD))a3->lpVtbl->Commit)(a3, 0);
              if ( inserted >= 0 )
              {
                inserted = ((__int64 (__fastcall *)(struct IStream *, _QWORD))a2->lpVtbl->Commit)(a2, 0);
                if ( inserted >= 0 )
                  goto LABEL_130;
                v59 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
                  CallStackTracing::s_wpInstance = v60;
                  if ( v60
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                  {
                    v59 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v59 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v59 + 8) )
                {
                  v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                  if ( *((_DWORD *)v61 + 499) != inserted )
                    CallStackContext::TraceFailure(
                      v61,
                      "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                      607,
                      inserted);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_130;
                v38 = 64;
              }
              else
              {
                v55 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                  CallStackTracing::s_wpInstance = v56;
                  if ( v56
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
                  {
                    v55 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v55 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v55 + 8) )
                {
                  v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                  if ( *((_DWORD *)v57 + 499) != inserted )
                    CallStackContext::TraceFailure(
                      v57,
                      "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                      605,
                      inserted);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_130;
                v38 = 63;
              }
            }
            else
            {
              v51 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
                CallStackTracing::s_wpInstance = v52;
                if ( v52
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                {
                  v51 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v51 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v51 + 8) )
              {
                v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                if ( *((_DWORD *)v53 + 499) != inserted )
                  CallStackContext::TraceFailure(
                    v53,
                    "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                    600,
                    inserted);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_130;
              v38 = 62;
            }
          }
          else
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != inserted )
                CallStackContext::TraceFailure(
                  v37,
                  "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
                  577,
                  inserted);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_130;
            v38 = 59;
          }
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v38,
            &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
            this,
            inserted);
          goto LABEL_130;
        }
        v9 = -2147467259;
        inserted = -2147467259;
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != -2147467259 )
            CallStackContext::TraceFailure(
              v27,
              "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
              557,
              -2147467259);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 57;
          goto LABEL_12;
        }
      }
      else
      {
        v9 = -2147467259;
        inserted = -2147467259;
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != -2147467259 )
            CallStackContext::TraceFailure(
              v23,
              "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
              551,
              -2147467259);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 56;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v9 = -2147024882;
      inserted = -2147024882;
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v19,
            "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler",
            546,
            -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 55;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v8 = 0;
    v9 = -2147024882;
    inserted = -2147024882;
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v13, "CFLACMetadataWriter::WriteEditedMetadataFromPropHandler", 538, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 54;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids, this, v9);
    }
  }
LABEL_130:
  operator delete(v8);
  if ( block )
    (*(void (__fastcall **)(struct FLAC::Metadata::VorbisComment *, __int64))(*(_QWORD *)block + 8LL))(block, 1);
  FLAC::Metadata::Iterator::~Iterator((FLAC::Metadata::Iterator *)v71);
  FLAC::Metadata::Chain::~Chain((FLAC::Metadata::Chain *)v72);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180033730  mov     [rsp-8+arg_18], rbx
0x180033735  push    rbp
0x180033736  push    rsi
0x180033737  push    rdi
0x180033738  push    r12
0x18003373a  push    r13
0x18003373c  push    r14
0x18003373e  push    r15
0x180033740  lea     rbp, [rsp-27h]
0x180033745  sub     rsp, 0D0h
0x18003374c  mov     rax, cs:__security_cookie
0x180033753  xor     rax, rsp
0x180033756  mov     [rbp+57h+var_38], rax
0x18003375a  mov     rsi, r8
0x18003375d  mov     rbx, rdx
0x180033760  mov     r14, rcx
0x180033763  mov     r8d, 20Fh; int
0x180033769  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x180033770  lea     rcx, [rbp+57h+var_D0]; this
0x180033774  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180033779  nop
0x18003377a  lea     rcx, [rbp+57h+var_48]; this
0x18003377e  call    ??0Chain@Metadata@FLAC@@QEAA@XZ; FLAC::Metadata::Chain::Chain(void)
0x180033783  nop
0x180033784  lea     rcx, [rbp+57h+var_58]; this
0x180033788  call    ??0Iterator@Metadata@FLAC@@QEAA@XZ; FLAC::Metadata::Iterator::Iterator(void)
0x18003378d  nop
0x18003378e  xor     r13d, r13d
0x180033791  mov     r12d, r13d
0x180033794  lea     rcx, [rbp+57h+var_48]; this
0x180033798  call    ?is_valid@Iterator@Metadata@FLAC@@QEBA_NXZ; FLAC::Metadata::Iterator::is_valid(void)
0x18003379d  test    al, al
0x18003379f  jnz     loc_180033842
0x1800337a5  mov     r15d, r13d
0x1800337a8  mov     ebx, 8007000Eh
0x1800337ad  mov     edi, ebx
0x1800337af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800337b6  test    rcx, rcx
0x1800337b9  jnz     short loc_1800337FC
0x1800337bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800337c1  mov     rcx, rax
0x1800337c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800337cb  test    rax, rax
0x1800337ce  jz      short loc_1800337EE
0x1800337d0  mov     rax, [rax]
0x1800337d3  mov     edx, 7F0h
0x1800337d8  mov     rax, [rax+8]
0x1800337dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337e1  test    eax, eax
0x1800337e3  jz      short loc_1800337EE
0x1800337e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800337ec  jmp     short loc_1800337FC
0x1800337ee  lea     rcx, qword_18006EB20; this
0x1800337f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800337fc  cmp     [rcx+8], r13b
0x180033800  jz      short loc_180033827
0x180033802  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033807  cmp     [rax+7CCh], ebx
0x18003380d  jz      short loc_180033827
0x18003380f  mov     r9d, ebx; int
0x180033812  mov     r8d, 21Ah; int
0x180033818  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x18003381f  mov     rcx, rax; this
0x180033822  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033827  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003382c  cmp     al, 1
0x18003382e  jb      loc_180033FE1
0x180033834  mov     edx, 36h ; '6'
0x180033839  mov     dword ptr [rsp+100h+var_E0], ebx
0x18003383d  jmp     loc_180033FC7
0x180033842  mov     cs:?m_fStreamIsIMFBytestream@CFLACMetadataCallbackFactory@@2_NA, r13b; bool CFLACMetadataCallbackFactory::m_fStreamIsIMFBytestream
0x180033849  call    ?GetCallbacks@CFLACMetadataCallbackFactory@@SAPEAUFLAC__IOCallbacks@@XZ; CFLACMetadataCallbackFactory::GetCallbacks(void)
0x18003384e  mov     r15, rax
0x180033851  test    rax, rax
0x180033854  jnz     loc_1800338F0
0x18003385a  mov     ebx, 8007000Eh
0x18003385f  mov     edi, ebx
0x180033861  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033868  test    rcx, rcx
0x18003386b  jnz     short loc_1800338AE
0x18003386d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033873  mov     rcx, rax
0x180033876  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003387d  test    rax, rax
0x180033880  jz      short loc_1800338A0
0x180033882  mov     rax, [rax]
0x180033885  mov     edx, 7F0h
0x18003388a  mov     rax, [rax+8]
0x18003388e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033893  test    eax, eax
0x180033895  jz      short loc_1800338A0
0x180033897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003389e  jmp     short loc_1800338AE
0x1800338a0  lea     rcx, qword_18006EB20; this
0x1800338a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800338ae  cmp     [rcx+8], r13b
0x1800338b2  jz      short loc_1800338D9
0x1800338b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800338b9  cmp     [rax+7CCh], ebx
0x1800338bf  jz      short loc_1800338D9
0x1800338c1  mov     r9d, ebx; int
0x1800338c4  mov     r8d, 222h; int
0x1800338ca  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x1800338d1  mov     rcx, rax; this
0x1800338d4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800338d9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800338de  cmp     al, 1
0x1800338e0  jb      loc_180033FE1
0x1800338e6  mov     edx, 37h ; '7'
0x1800338eb  jmp     loc_180033839
0x1800338f0  movups  xmm0, xmmword ptr [rax]
0x1800338f3  movaps  [rbp+57h+var_C0], xmm0
0x1800338f7  movups  xmm1, xmmword ptr [rax+10h]
0x1800338fb  movaps  [rbp+57h+var_B0], xmm1
0x1800338ff  movups  xmm0, xmmword ptr [rax+20h]
0x180033903  movaps  [rbp+57h+var_A0], xmm0
0x180033907  xor     r9d, r9d
0x18003390a  lea     r8, [rbp+57h+var_C0]
0x18003390e  mov     rdx, rbx
0x180033911  lea     rcx, [rbp+57h+var_48]
0x180033915  call    ?read@Chain@Metadata@FLAC@@QEAA_NPEAXUFLAC__IOCallbacks@@_N@Z; FLAC::Metadata::Chain::read(void *,FLAC__IOCallbacks,bool)
0x18003391a  test    al, al
0x18003391c  jnz     loc_1800339B8
0x180033922  mov     ebx, 80004005h
0x180033927  mov     edi, ebx
0x180033929  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033930  test    rcx, rcx
0x180033933  jnz     short loc_180033976
0x180033935  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003393b  mov     rcx, rax
0x18003393e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033945  test    rax, rax
0x180033948  jz      short loc_180033968
0x18003394a  mov     rax, [rax]
0x18003394d  mov     edx, 7F0h
0x180033952  mov     rax, [rax+8]
0x180033956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003395b  test    eax, eax
0x18003395d  jz      short loc_180033968
0x18003395f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033966  jmp     short loc_180033976
0x180033968  lea     rcx, qword_18006EB20; this
0x18003396f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033976  cmp     [rcx+8], r13b
0x18003397a  jz      short loc_1800339A1
0x18003397c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033981  cmp     [rax+7CCh], ebx
0x180033987  jz      short loc_1800339A1
0x180033989  mov     r9d, ebx; int
0x18003398c  mov     r8d, 227h; int
0x180033992  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x180033999  mov     rcx, rax; this
0x18003399c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800339a1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800339a6  cmp     al, 1
0x1800339a8  jb      loc_180033FE1
0x1800339ae  mov     edx, 38h ; '8'
0x1800339b3  jmp     loc_180033839
0x1800339b8  lea     rdx, [rbp+57h+var_48]; struct FLAC::Metadata::Chain *
0x1800339bc  lea     rcx, [rbp+57h+var_58]; this
0x1800339c0  call    ?init@Iterator@Metadata@FLAC@@QEAAXAEAVChain@23@@Z; FLAC::Metadata::Iterator::init(FLAC::Metadata::Chain &)
0x1800339c5  lea     rcx, [rbp+57h+var_58]; this
0x1800339c9  call    ?is_valid@Iterator@Metadata@FLAC@@QEBA_NXZ; FLAC::Metadata::Iterator::is_valid(void)
0x1800339ce  test    al, al
0x1800339d0  jnz     loc_180033A6C
0x1800339d6  mov     ebx, 80004005h
0x1800339db  mov     edi, ebx
0x1800339dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800339e4  test    rcx, rcx
0x1800339e7  jnz     short loc_180033A2A
0x1800339e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800339ef  mov     rcx, rax
0x1800339f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800339f9  test    rax, rax
0x1800339fc  jz      short loc_180033A1C
0x1800339fe  mov     rax, [rax]
0x180033a01  mov     edx, 7F0h
0x180033a06  mov     rax, [rax+8]
0x180033a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a0f  test    eax, eax
0x180033a11  jz      short loc_180033A1C
0x180033a13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033a1a  jmp     short loc_180033A2A
0x180033a1c  lea     rcx, qword_18006EB20; this
0x180033a23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033a2a  cmp     [rcx+8], r13b
0x180033a2e  jz      short loc_180033A55
0x180033a30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033a35  cmp     [rax+7CCh], ebx
0x180033a3b  jz      short loc_180033A55
0x180033a3d  mov     r9d, ebx; int
0x180033a40  mov     r8d, 22Dh; int
0x180033a46  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x180033a4d  mov     rcx, rax; this
0x180033a50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033a55  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180033a5a  cmp     al, 1
0x180033a5c  jb      loc_180033FE1
0x180033a62  mov     edx, 39h ; '9'
0x180033a67  jmp     loc_180033839
0x180033a6c  lea     rcx, [rbp+57h+var_58]
0x180033a70  call    ?get_block_type@Iterator@Metadata@FLAC@@QEBA?AW4FLAC__MetadataType@@XZ; FLAC::Metadata::Iterator::get_block_type(void)
0x180033a75  cmp     eax, 4
0x180033a78  jz      loc_180033B55
0x180033a7e  lea     rcx, [rbp+57h+var_58]; this
0x180033a82  call    ?next@Iterator@Metadata@FLAC@@QEAA_NXZ; FLAC::Metadata::Iterator::next(void)
0x180033a87  test    al, al
0x180033a89  jnz     short loc_180033A6C
0x180033a8b  mov     ecx, 18h; Size
0x180033a90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033a95  mov     [rbp+57h+var_60], rax
0x180033a99  test    rax, rax
0x180033a9c  jz      short loc_180033AA8
0x180033a9e  mov     rcx, rax; this
0x180033aa1  call    ??0VorbisComment@Metadata@FLAC@@QEAA@XZ; FLAC::Metadata::VorbisComment::VorbisComment(void)
0x180033aa6  jmp     short loc_180033AAB
0x180033aa8  mov     rax, r13
0x180033aab  mov     rdx, rax; struct FLAC::Metadata::Prototype *
0x180033aae  lea     rcx, [rbp+57h+var_58]; this
0x180033ab2  call    ?insert_block_after@Iterator@Metadata@FLAC@@QEAA_NPEAVPrototype@23@@Z; FLAC::Metadata::Iterator::insert_block_after(FLAC::Metadata::Prototype *)
0x180033ab7  test    al, al
0x180033ab9  jnz     loc_180033B55
0x180033abf  mov     ebx, 80004005h
0x180033ac4  mov     edi, ebx
0x180033ac6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033acd  test    rcx, rcx
0x180033ad0  jnz     short loc_180033B13
0x180033ad2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033ad8  mov     rcx, rax
0x180033adb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033ae2  test    rax, rax
0x180033ae5  jz      short loc_180033B05
0x180033ae7  mov     rax, [rax]
0x180033aea  mov     edx, 7F0h
0x180033aef  mov     rax, [rax+8]
0x180033af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af8  test    eax, eax
0x180033afa  jz      short loc_180033B05
0x180033afc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033b03  jmp     short loc_180033B13
0x180033b05  lea     rcx, qword_18006EB20; this
0x180033b0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033b13  cmp     [rcx+8], r13b
0x180033b17  jz      short loc_180033B3E
0x180033b19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033b1e  cmp     [rax+7CCh], ebx
0x180033b24  jz      short loc_180033B3E
0x180033b26  mov     r9d, ebx; int
0x180033b29  mov     r8d, 239h; int
0x180033b2f  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x180033b36  mov     rcx, rax; this
0x180033b39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033b3e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180033b43  cmp     al, 1
0x180033b45  jb      loc_180033FE1
0x180033b4b  mov     edx, 3Ah ; ':'
0x180033b50  jmp     loc_180033839
0x180033b55  lea     rcx, [rbp+57h+var_58]; this
0x180033b59  call    ?get_block@Iterator@Metadata@FLAC@@QEAAPEAVPrototype@23@XZ; FLAC::Metadata::Iterator::get_block(void)
0x180033b5e  mov     r12, rax
0x180033b61  mov     rdx, rax; struct FLAC::Metadata::VorbisComment *
0x180033b64  mov     rcx, r14; this
0x180033b67  call    ?InsertPropertiesIntoVorbisComment@CFLACMetadataWriter@@AEAAJPEAVVorbisComment@Metadata@FLAC@@@Z; CFLACMetadataWriter::InsertPropertiesIntoVorbisComment(FLAC::Metadata::VorbisComment *)
0x180033b6c  mov     edi, eax
0x180033b6e  test    eax, eax
0x180033b70  jns     loc_180033C05
0x180033b76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033b7d  test    rcx, rcx
0x180033b80  jnz     short loc_180033BC3
0x180033b82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033b88  mov     rcx, rax
0x180033b8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033b92  test    rax, rax
0x180033b95  jz      short loc_180033BB5
0x180033b97  mov     rax, [rax]
0x180033b9a  mov     edx, 7F0h
0x180033b9f  mov     rax, [rax+8]
0x180033ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ba8  test    eax, eax
0x180033baa  jz      short loc_180033BB5
0x180033bac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033bb3  jmp     short loc_180033BC3
0x180033bb5  lea     rcx, qword_18006EB20; this
0x180033bbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033bc3  cmp     [rcx+8], r13b
0x180033bc7  jz      short loc_180033BEE
0x180033bc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033bce  cmp     [rax+7CCh], edi
0x180033bd4  jz      short loc_180033BEE
0x180033bd6  mov     r9d, edi; int
0x180033bd9  mov     r8d, 241h; int
0x180033bdf  lea     rdx, aCflacmetadataw_5; "CFLACMetadataWriter::WriteEditedMetadat"...
0x180033be6  mov     rcx, rax; this
0x180033be9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033bee  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180033bf3  cmp     al, 1
0x180033bf5  jb      loc_180033FE1
0x180033bfb  mov     edx, 3Bh ; ';'
0x180033c00  jmp     loc_180033FC3
0x180033c05  mov     dl, 1; bool
  ... truncated ...
```
