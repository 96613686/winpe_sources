# CFLACMetadataWriter::InsertPropertiesIntoVorbisComment(FLAC::Metadata::VorbisComment *)

- ea: `0x180031ca4`
- end: `0x180032764`
- name: `?InsertPropertiesIntoVorbisComment@CFLACMetadataWriter@@AEAAJPEAVVorbisComment@Metadata@FLAC@@@Z`
- size: `2752`
- prototype: `__int64 __fastcall(CFLACMetadataWriter *__hidden this, struct FLAC::Metadata::VorbisComment *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033730`

## callees

- `0x1800018a4`
- `0x1800018e4`
- `0x1800018f0`
- `0x180001e80`
- `0x180001ea4`
- `0x1800028ac`
- `0x180003180`
- `0x180003490`
- `0x180003a60`
- `0x180003a70`
- `0x180003a80`
- `0x180020398`
- `0x180020484`
- `0x1800234fc`
- `0x18002fce8`
- `0x18002ff68`
- `0x18002fff0`
- `0x1800300e0`
- `0x18003051c`
- `0x180030f28`
- `0x180031bdc`
- `0x180031ca4`
- `0x180032900`
- `0x1800340c4`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f56`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f6a`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f7b`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f56`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f6a`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180031f7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032054`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800320ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003217f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003221c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032402`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003249c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003252f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003269c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032054`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800320ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003217f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003221c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032402`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003249c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003252f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003269c`

## string_xrefs

- `0x180031d52`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x1800320b1`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x18003214a`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x1800321dc`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x180032279`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x18003235a`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x18003245f`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x1800324f9`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x18003258c`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x180032645`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`
- `0x1800326f6`: `CFLACMetadataWriter::InsertPropertiesIntoVorbisComment`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFLACMetadataWriter::InsertPropertiesIntoVorbisComment(
        CFLACMetadataWriter *this,
        struct FLAC::Metadata::VorbisComment *a2)
{
  int CommentField; // ebx
  unsigned int i; // r12d
  void *v5; // rdi
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rdi
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned __int64 v12; // r15
  struct VORBIS_COMMENT_FIELD *v13; // r13
  unsigned int v14; // r14d
  _QWORD *v15; // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  void *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned __int64 v22; // rdi
  char *v23; // rax
  __int64 v24; // rdx
  FLAC::Metadata::VorbisComment::Entry *v25; // rax
  __int64 v26; // rdx
  struct VORBIS_COMMENT_FIELD *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  void *v44; // rdi
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  unsigned int v55; // edi
  FLAC::Metadata::VorbisComment *v56; // r15
  __int64 v57; // rdx
  const char *v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v63[8]; // [rsp+30h] [rbp-59h] BYREF
  FLAC::Metadata::VorbisComment *v64; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v65; // [rsp+40h] [rbp-49h]
  void **p_Block; // [rsp+48h] [rbp-41h]
  char v67; // [rsp+50h] [rbp-39h]
  FLAC::Metadata::VorbisComment::Entry *v68; // [rsp+58h] [rbp-31h]
  void **v69; // [rsp+60h] [rbp-29h]
  char **p_Src; // [rsp+68h] [rbp-21h]
  struct VORBIS_COMMENT_FIELD **v71; // [rsp+70h] [rbp-19h]
  char v72; // [rsp+78h] [rbp-11h]
  char *Src; // [rsp+80h] [rbp-9h] BYREF
  void *v74; // [rsp+88h] [rbp-1h] BYREF
  struct VORBIS_COMMENT_FIELD *v75; // [rsp+90h] [rbp+7h] BYREF
  void *Block; // [rsp+98h] [rbp+Fh] BYREF

  v64 = a2;
  CommentField = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 8) )
    {
      if ( CFLACMetadataCallbackFactory::m_fStreamIsIMFBytestream )
        return (unsigned int)CommentField;
      v55 = 0;
      v56 = v64;
      while ( 1 )
      {
        if ( v55 >= *((_DWORD *)this + 14) )
          return (unsigned int)CommentField;
        v64 = 0;
        CommentField = CFLACMetadataWriter::FindCommentField(
                         this,
                         *(const unsigned __int16 **)(*((_QWORD *)this + 6) + 8LL * v55),
                         &v64);
        if ( CommentField == -1072875819 )
        {
          CommentField = 0;
        }
        else
        {
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)v63,
            "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
            827);
          if ( CommentField < 0 )
          {
            v59 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57);
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != CommentField )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
                  827,
                  CommentField);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
                this,
                CommentField);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
            return (unsigned int)CommentField;
          }
          CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 48, v55);
          v58 = (const char *)*((_QWORD *)v64 + 1);
          if ( *((_BYTE *)v64 + 16) )
            FLAC::Metadata::VorbisComment::remove_entries_matching(v56, v58);
          else
            FLAC::Metadata::VorbisComment::remove_entry_matching(v56, v58);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
        }
        ++v55;
      }
    }
    v75 = 0;
    Block = 0;
    p_Block = &Block;
    v67 = 1;
    CommentField = CFLACMetadataWriter::FindCommentField(
                     this,
                     *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 8LL * i),
                     &v75);
    if ( CommentField == -1072875819 )
    {
      CommentField = 0;
      goto LABEL_5;
    }
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v63,
      "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
      730);
    if ( CommentField < 0 )
    {
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != CommentField )
          CallStackContext::TraceFailure(
            v54,
            "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
            730,
            CommentField);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v48 = 71;
LABEL_135:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v48,
          &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
          this,
          CommentField);
      }
LABEL_136:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
      v44 = Block;
      if ( Block )
        goto LABEL_137;
      return (unsigned int)CommentField;
    }
    v7 = operator new(0x20u);
    v9 = v7;
    Block = v7;
    if ( !v7 )
    {
      Block = 0;
      CommentField = -2147024882;
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v51,
            "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
            733,
            -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
          this,
          -2147024882);
      goto LABEL_136;
    }
    *v7 = *((_QWORD *)this + 12) + 24LL * i;
    *((_DWORD *)v7 + 2) = 0;
    v7[2] = 0;
    v7[3] = 0;
    Block = v7;
    CommentField = CPropVariantConversionHelper::CalcStringSizes((CPropVariantConversionHelper *)v7);
    if ( CommentField >= 0 )
      break;
    if ( CommentField != -2147024809 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != CommentField )
          CallStackContext::TraceFailure(
            v47,
            "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
            742,
            CommentField);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v48 = 73;
        goto LABEL_135;
      }
      goto LABEL_136;
    }
    CommentField = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
LABEL_5:
    v67 = 0;
    v5 = Block;
    if ( Block )
    {
LABEL_6:
      CPropVariantConversionHelper::~CPropVariantConversionHelper((CPropVariantConversionHelper *)Block);
      operator delete(v5);
    }
LABEL_45:
    ;
  }
  v11 = *((_DWORD *)v9 + 2);
  v65 = v11;
  v12 = 0;
  v13 = v75;
  if ( *((_BYTE *)v75 + 16) )
  {
    FLAC::Metadata::VorbisComment::remove_entries_matching(v64, *((const char **)v75 + 1));
    v11 = v65;
  }
  v14 = 0;
  while ( 2 )
  {
    if ( v14 >= v11 )
    {
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
      v67 = 0;
      v5 = Block;
      if ( !Block )
        goto LABEL_45;
      goto LABEL_6;
    }
    v74 = 0;
    Src = 0;
    v75 = 0;
    v69 = &v74;
    p_Src = &Src;
    v71 = &v75;
    v72 = 1;
    v15 = Block;
    v16 = CPropVariantConversionHelper::CalcStringSizes((CPropVariantConversionHelper *)Block);
    CommentField = v16;
    if ( v14 < *((_DWORD *)v15 + 2) )
    {
      if ( v16 >= 0 )
        v12 = *(_QWORD *)(v15[2] + 8LL * v14);
    }
    else
    {
      CommentField = -2147024809;
    }
    if ( v12 == 1 || CommentField == -2147024809 )
    {
LABEL_27:
      CommentField = 0;
      goto LABEL_28;
    }
    if ( CommentField >= 0 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_BYTE *)(*((_QWORD *)v13 + 1) + v18) );
      v19 = operator new[](v12);
      v74 = v19;
      if ( !v19 )
      {
        CommentField = -2147024882;
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              v40,
              "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
              780,
              -2147024882);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_87;
        v31 = 75;
LABEL_86:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
          this,
          -2147024882);
LABEL_87:
        operator delete(v74);
        v74 = 0;
        operator delete(Src);
        Src = 0;
        if ( v75 )
          (**(void (__fastcall ***)(struct VORBIS_COMMENT_FIELD *, __int64))v75)(v75, 1);
        v75 = 0;
        goto LABEL_103;
      }
      CommentField = CPropVariantConversionHelper::CopyStringToBuffer(
                       (CPropVariantConversionHelper *)Block,
                       v14,
                       (unsigned __int8 *)v19,
                       v12);
      if ( CommentField == -2147024809 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
          WPP_SF_qSD(*((_QWORD *)WPP_GLOBAL_Control + 27), *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * i), 87);
        goto LABEL_27;
      }
      if ( CommentField < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
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
          if ( *((_DWORD *)v37 + 499) != CommentField )
            CallStackContext::TraceFailure(
              v37,
              "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
              791,
              CommentField);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
            this,
            CommentField);
        goto LABEL_87;
      }
      v22 = v12 + v18 + 2;
      v23 = (char *)operator new[](v22);
      Src = v23;
      if ( !v23 )
      {
        CommentField = -2147024882;
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              v34,
              "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
              794,
              -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v31 = 78;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      memset_0(v23, 0, v22);
      _o_strcat_s(Src, v22, *((_QWORD *)v13 + 1));
      _o_strcat_s(Src, v22, "=");
      _o_strcat_s(Src, v22, v74);
      v25 = (FLAC::Metadata::VorbisComment::Entry *)operator new(0x40u);
      v68 = v25;
      if ( v25 )
        v27 = (struct VORBIS_COMMENT_FIELD *)FLAC::Metadata::VorbisComment::Entry::Entry(v25, Src);
      else
        v27 = 0;
      v75 = v27;
      if ( !v27 )
      {
        CommentField = -2147024882;
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              v30,
              "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment",
              801,
              -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v31 = 79;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( CFLACMetadataCallbackFactory::m_fStreamIsIMFBytestream || *((_BYTE *)v13 + 16) )
        FLAC::Metadata::VorbisComment::append_comment(v64, v27);
      else
        FLAC::Metadata::VorbisComment::replace_comment(v64, v27, 0);
LABEL_28:
      operator delete(v74);
      v74 = 0;
      operator delete(Src);
      Src = 0;
      if ( v75 )
        (**(void (__fastcall ***)(struct VORBIS_COMMENT_FIELD *, __int64))v75)(v75, 1);
      ++v14;
      v11 = v65;
      continue;
    }
    break;
  }
  v41 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
    CallStackTracing::s_wpInstance = v42;
    if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v41 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v41 + 8) )
  {
    v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
    if ( *((_DWORD *)v43 + 499) != CommentField )
      CallStackContext::TraceFailure(v43, "CFLACMetadataWriter::InsertPropertiesIntoVorbisComment", 775, CommentField);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
      this,
      CommentField);
  operator delete(v74);
  v74 = 0;
  operator delete(Src);
  Src = 0;
  if ( v75 )
    (**(void (__fastcall ***)(struct VORBIS_COMMENT_FIELD *, __int64))v75)(v75, 1);
  v75 = 0;
LABEL_103:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  v44 = Block;
  if ( !Block )
    return (unsigned int)CommentField;
LABEL_137:
  CPropVariantConversionHelper::~CPropVariantConversionHelper((CPropVariantConversionHelper *)Block);
  operator delete(v44);
  return (unsigned int)CommentField;
}

```

## disassembly

```asm
0x180031ca4  mov     [rsp-8+arg_10], rbx
0x180031ca9  push    rbp
0x180031caa  push    rsi
0x180031cab  push    rdi
0x180031cac  push    r12
0x180031cae  push    r13
0x180031cb0  push    r14
0x180031cb2  push    r15
0x180031cb4  lea     rbp, [rsp-27h]
0x180031cb9  sub     rsp, 0B0h
0x180031cc0  mov     rax, cs:__security_cookie
0x180031cc7  xor     rax, rsp
0x180031cca  mov     [rbp+57h+var_40], rax
0x180031cce  mov     [rbp+57h+var_A8], rdx
0x180031cd2  mov     rsi, rcx
0x180031cd5  xor     r13d, r13d
0x180031cd8  mov     ebx, r13d
0x180031cdb  mov     r12d, r13d
0x180031cde  lea     r15d, [r13+20h]
0x180031ce2  cmp     r12d, [rsi+20h]
0x180031ce6  jnb     loc_1800325F7
0x180031cec  mov     [rbp+57h+var_50], r13
0x180031cf0  mov     [rbp+57h+Block], r13
0x180031cf4  lea     rax, [rbp+57h+Block]
0x180031cf8  mov     [rbp+57h+var_98], rax
0x180031cfc  mov     [rbp+57h+var_90], 1
0x180031d00  mov     r14d, r12d
0x180031d03  mov     rdx, [rsi+18h]
0x180031d07  lea     r8, [rbp+57h+var_50]; struct VORBIS_COMMENT_FIELD **
0x180031d0b  mov     rdx, [rdx+r14*8]; unsigned __int16 *
0x180031d0f  mov     rcx, rsi; this
0x180031d12  call    ?FindCommentField@CFLACMetadataWriter@@AEAAJPEBGPEAPEBUVORBIS_COMMENT_FIELD@@@Z; CFLACMetadataWriter::FindCommentField(ushort const *,VORBIS_COMMENT_FIELD const * *)
0x180031d17  mov     ebx, eax
0x180031d19  cmp     eax, 0C00D36D5h
0x180031d1e  jnz     short loc_180031D4C
0x180031d20  mov     ebx, r13d
0x180031d23  mov     [rbp+57h+var_90], r13b
0x180031d27  mov     rdi, [rbp+57h+Block]
0x180031d2b  test    rdi, rdi
0x180031d2e  jz      loc_180032036
0x180031d34  mov     rcx, rdi; this
0x180031d37  call    ??1CPropVariantConversionHelper@@QEAA@XZ; CPropVariantConversionHelper::~CPropVariantConversionHelper(void)
0x180031d3c  mov     rdx, r15
0x180031d3f  mov     rcx, rdi; Block
0x180031d42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031d47  jmp     loc_180032036
0x180031d4c  mov     r8d, 2DAh; int
0x180031d52  lea     rdx, aCflacmetadataw_2; "CFLACMetadataWriter::InsertPropertiesIn"...
0x180031d59  lea     rcx, [rbp+57h+var_B0]; this
0x180031d5d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180031d62  nop
0x180031d63  test    ebx, ebx
0x180031d65  js      loc_180032523
0x180031d6b  mov     rcx, r15; Size
0x180031d6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031d73  mov     rdi, rax
0x180031d76  mov     [rbp+57h+Block], rax
0x180031d7a  test    rax, rax
0x180031d7d  jz      loc_180032485
0x180031d83  lea     rdx, [r14+r14*2]
0x180031d87  mov     rcx, [rsi+60h]
0x180031d8b  lea     rdx, [rcx+rdx*8]
0x180031d8f  mov     [rax], rdx
0x180031d92  mov     [rax+8], r13d
0x180031d96  mov     [rax+10h], r13
0x180031d9a  mov     [rax+18h], r13
0x180031d9e  mov     [rbp+57h+Block], rax
0x180031da2  test    rax, rax
0x180031da5  jz      loc_180032489
0x180031dab  mov     rcx, rax; this
0x180031dae  call    ?CalcStringSizes@CPropVariantConversionHelper@@IEAAJXZ; CPropVariantConversionHelper::CalcStringSizes(void)
0x180031db3  mov     ebx, eax
0x180031db5  test    eax, eax
0x180031db7  js      loc_180032013
0x180031dbd  mov     eax, [rdi+8]
0x180031dc0  mov     [rbp+57h+var_A0], eax
0x180031dc3  mov     r15, r13
0x180031dc6  mov     r13, [rbp+57h+var_50]
0x180031dca  xor     edi, edi
0x180031dcc  cmp     [r13+10h], dil
0x180031dd0  jz      short loc_180031DE2
0x180031dd2  mov     rdx, [r13+8]; char *
0x180031dd6  mov     rcx, [rbp+57h+var_A8]; this
0x180031dda  call    ?remove_entries_matching@VorbisComment@Metadata@FLAC@@QEAAHPEBD@Z; FLAC::Metadata::VorbisComment::remove_entries_matching(char const *)
0x180031ddf  mov     eax, [rbp+57h+var_A0]
0x180031de2  mov     r14d, edi
0x180031de5  cmp     r14d, eax
0x180031de8  jnb     loc_180031FE8
0x180031dee  mov     [rbp+57h+var_58], rdi
0x180031df2  mov     [rbp+57h+Src], rdi
0x180031df6  mov     [rbp+57h+var_50], rdi
0x180031dfa  lea     rax, [rbp+57h+var_58]
0x180031dfe  mov     [rbp+57h+var_80], rax
0x180031e02  lea     rax, [rbp+57h+Src]
0x180031e06  mov     [rbp+57h+var_78], rax
0x180031e0a  lea     rax, [rbp+57h+var_50]
0x180031e0e  mov     [rbp+57h+var_70], rax
0x180031e12  mov     [rbp+57h+var_68], 1
0x180031e16  mov     rdi, [rbp+57h+Block]
0x180031e1a  mov     rcx, rdi; this
0x180031e1d  call    ?CalcStringSizes@CPropVariantConversionHelper@@IEAAJXZ; CPropVariantConversionHelper::CalcStringSizes(void)
0x180031e22  mov     ebx, eax
0x180031e24  cmp     r14d, [rdi+8]
0x180031e28  jb      short loc_180031E31
0x180031e2a  mov     ebx, 80070057h
0x180031e2f  jmp     short loc_180031E40
0x180031e31  test    eax, eax
0x180031e33  js      short loc_180031E40
0x180031e35  mov     ecx, r14d
0x180031e38  mov     rax, [rdi+10h]
0x180031e3c  mov     r15, [rax+rcx*8]
0x180031e40  cmp     r15, 1
0x180031e44  jz      loc_180031ED8
0x180031e4a  cmp     ebx, 80070057h
0x180031e50  jz      loc_180031ED8
0x180031e56  xor     edi, edi
0x180031e58  test    ebx, ebx
0x180031e5a  js      loc_1800322F1
0x180031e60  mov     rax, [r13+8]
0x180031e64  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031e68  inc     rdi
0x180031e6b  cmp     byte ptr [rax+rdi], 0
0x180031e6f  jnz     short loc_180031E68
0x180031e71  mov     rcx, r15; unsigned __int64
0x180031e74  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031e79  mov     [rbp+57h+var_58], rax
0x180031e7d  test    rax, rax
0x180031e80  jz      loc_180032206
0x180031e86  mov     r9, r15; unsigned __int64
0x180031e89  mov     r8, rax; unsigned __int8 *
0x180031e8c  mov     edx, r14d; unsigned int
0x180031e8f  mov     rcx, [rbp+57h+Block]; this
0x180031e93  call    ?CopyStringToBuffer@CPropVariantConversionHelper@@QEAAJKPEAE_K@Z; CPropVariantConversionHelper::CopyStringToBuffer(ulong,uchar *,unsigned __int64)
0x180031e98  mov     ebx, eax
0x180031e9a  cmp     eax, 80070057h
0x180031e9f  jnz     short loc_180031F1A
0x180031ea1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180031ea6  cmp     al, 20h ; ' '
0x180031ea8  jb      short loc_180031ED8
0x180031eaa  mov     rax, [rsi+18h]
0x180031eae  mov     dword ptr [rsp+0E0h+var_B8], 80070057h; char
0x180031eb6  mov     ecx, r12d
0x180031eb9  mov     rax, [rax+rcx*8]
0x180031ebd  mov     [rsp+0E0h+var_C0], rax; __int64
0x180031ec2  mov     r9, rsi
0x180031ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ecc  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180031ed3  call    WPP_SF_qSD
0x180031ed8  xor     edi, edi
0x180031eda  mov     ebx, edi
0x180031edc  mov     rcx, [rbp+57h+var_58]; Block
0x180031ee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031ee5  mov     [rbp+57h+var_58], rdi
0x180031ee9  mov     rcx, [rbp+57h+Src]; Block
0x180031eed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031ef2  mov     rcx, [rbp+57h+var_50]
0x180031ef6  mov     [rbp+57h+Src], rdi
0x180031efa  test    rcx, rcx
0x180031efd  jz      short loc_180031F0F
0x180031eff  mov     rax, [rcx]
0x180031f02  mov     edx, 1
0x180031f07  mov     rax, [rax]
0x180031f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f0f  inc     r14d
0x180031f12  mov     eax, [rbp+57h+var_A0]
0x180031f15  jmp     loc_180031DE5
0x180031f1a  test    ebx, ebx
0x180031f1c  js      loc_180032170
0x180031f22  add     rdi, 2
0x180031f26  add     rdi, r15
0x180031f29  mov     rcx, rdi; unsigned __int64
0x180031f2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031f31  mov     [rbp+57h+Src], rax
0x180031f35  test    rax, rax
0x180031f38  jz      loc_1800320D7
0x180031f3e  mov     r8, rdi; Size
0x180031f41  xor     edx, edx; Val
0x180031f43  mov     rcx, rax; void *
0x180031f46  call    memset_0
0x180031f4b  mov     r8, [r13+8]
0x180031f4f  mov     rdx, rdi
0x180031f52  mov     rcx, [rbp+57h+Src]
0x180031f56  call    cs:__imp__o_strcat_s
0x180031f5c  lea     r8, asc_180064838; "="
0x180031f63  mov     rdx, rdi
0x180031f66  mov     rcx, [rbp+57h+Src]
0x180031f6a  call    cs:__imp__o_strcat_s
0x180031f70  mov     r8, [rbp+57h+var_58]
0x180031f74  mov     rdx, rdi
0x180031f77  mov     rcx, [rbp+57h+Src]
0x180031f7b  call    cs:__imp__o_strcat_s
0x180031f81  mov     ecx, 40h ; '@'; Size
0x180031f86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031f8b  mov     [rbp+57h+var_88], rax
0x180031f8f  xor     edi, edi
0x180031f91  test    rax, rax
0x180031f94  jz      short loc_180031FA4
0x180031f96  mov     rdx, [rbp+57h+Src]; Src
0x180031f9a  mov     rcx, rax; this
0x180031f9d  call    ??0Entry@VorbisComment@Metadata@FLAC@@QEAA@PEBD@Z; FLAC::Metadata::VorbisComment::Entry::Entry(char const *)
0x180031fa2  jmp     short loc_180031FA7
0x180031fa4  mov     rax, rdi
0x180031fa7  mov     [rbp+57h+var_50], rax
0x180031fab  test    rax, rax
0x180031fae  jz      loc_18003203E
0x180031fb4  cmp     cs:?m_fStreamIsIMFBytestream@CFLACMetadataCallbackFactory@@2_NA, dil; bool CFLACMetadataCallbackFactory::m_fStreamIsIMFBytestream
0x180031fbb  jnz     short loc_180031FD7
0x180031fbd  cmp     [r13+10h], dil
0x180031fc1  jnz     short loc_180031FD7
0x180031fc3  xor     r8d, r8d; bool
0x180031fc6  mov     rdx, rax; struct FLAC::Metadata::VorbisComment::Entry *
0x180031fc9  mov     rcx, [rbp+57h+var_A8]; this
0x180031fcd  call    ?replace_comment@VorbisComment@Metadata@FLAC@@QEAA_NAEBVEntry@123@_N@Z; FLAC::Metadata::VorbisComment::replace_comment(FLAC::Metadata::VorbisComment::Entry const &,bool)
0x180031fd2  jmp     loc_180031EDC
0x180031fd7  mov     rdx, rax; struct FLAC::Metadata::VorbisComment::Entry *
0x180031fda  mov     rcx, [rbp+57h+var_A8]; this
0x180031fde  call    ?append_comment@VorbisComment@Metadata@FLAC@@QEAA_NAEBVEntry@123@@Z; FLAC::Metadata::VorbisComment::append_comment(FLAC::Metadata::VorbisComment::Entry const &)
0x180031fe3  jmp     loc_180031EDC
0x180031fe8  lea     rcx, [rbp+57h+var_B0]; this
0x180031fec  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180031ff1  nop
0x180031ff2  xor     r13d, r13d
0x180031ff5  mov     [rbp+57h+var_90], r13b
0x180031ff9  mov     rdi, [rbp+57h+Block]
0x180031ffd  test    rdi, rdi
0x180032000  jz      short loc_180032030
0x180032002  mov     rcx, rdi; this
0x180032005  call    ??1CPropVariantConversionHelper@@QEAA@XZ; CPropVariantConversionHelper::~CPropVariantConversionHelper(void)
0x18003200a  lea     r15d, [r13+20h]
0x18003200e  jmp     loc_180031D3C
0x180032013  cmp     ebx, 80070057h
0x180032019  jnz     loc_1800323F6
0x18003201f  mov     ebx, r13d
0x180032022  lea     rcx, [rbp+57h+var_B0]; this
0x180032026  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003202b  jmp     loc_180031D23
0x180032030  mov     r15d, 20h ; ' '
0x180032036  inc     r12d
0x180032039  jmp     loc_180031CE2
0x18003203e  mov     edi, 8007000Eh
0x180032043  mov     ebx, edi
0x180032045  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003204c  xor     r14d, r14d
0x18003204f  test    rcx, rcx
0x180032052  jnz     short loc_180032095
0x180032054  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003205a  mov     rcx, rax
0x18003205d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032064  test    rax, rax
0x180032067  jz      short loc_180032087
0x180032069  mov     rax, [rax]
0x18003206c  mov     edx, 7F0h
0x180032071  mov     rax, [rax+8]
0x180032075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003207a  test    eax, eax
0x18003207c  jz      short loc_180032087
0x18003207e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032085  jmp     short loc_180032095
0x180032087  lea     rcx, qword_18006EB20; this
0x18003208e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032095  cmp     [rcx+8], r14b
0x180032099  jz      short loc_1800320C0
0x18003209b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800320a0  cmp     [rax+7CCh], edi
0x1800320a6  jz      short loc_1800320C0
0x1800320a8  mov     r9d, edi; int
0x1800320ab  mov     r8d, 321h; int
0x1800320b1  lea     rdx, aCflacmetadataw_2; "CFLACMetadataWriter::InsertPropertiesIn"...
0x1800320b8  mov     rcx, rax; this
0x1800320bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800320c0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800320c5  cmp     al, 1
0x1800320c7  jb      loc_1800322B5
0x1800320cd  mov     edx, 4Fh ; 'O'
0x1800320d2  jmp     loc_180032296
0x1800320d7  mov     edi, 8007000Eh
0x1800320dc  mov     ebx, edi
0x1800320de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800320e5  xor     r14d, r14d
0x1800320e8  test    rcx, rcx
0x1800320eb  jnz     short loc_18003212E
0x1800320ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800320f3  mov     rcx, rax
0x1800320f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800320fd  test    rax, rax
0x180032100  jz      short loc_180032120
0x180032102  mov     rax, [rax]
0x180032105  mov     edx, 7F0h
0x18003210a  mov     rax, [rax+8]
0x18003210e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032113  test    eax, eax
0x180032115  jz      short loc_180032120
0x180032117  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003211e  jmp     short loc_18003212E
0x180032120  lea     rcx, qword_18006EB20; this
0x180032127  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003212e  cmp     [rcx+8], r14b
0x180032132  jz      short loc_180032159
0x180032134  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032139  cmp     [rax+7CCh], edi
  ... truncated ...
```
