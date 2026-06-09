# ParseiTunesID3TagInfo(CID3Header *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x1800a41d4`
- end: `0x1800a4c28`
- name: `?ParseiTunesID3TagInfo@@YAJPEAVCID3Header@@PEAK1PEA_K@Z`
- size: `2644`
- prototype: `__int64 __fastcall(struct CID3Header *this, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180069118`
- `0x1800a94e0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180016700`
- `0x180018b90`
- `0x180021010`
- `0x1800211a0`
- `0x1800211cc`
- `0x180044080`
- `0x180073b14`
- `0x18007450c`
- `0x18007ca70`
- `0x1800a41d4`
- `0x180122434`
- `0x180131e94`
- `0x1801611d4`
- `0x1801723d4`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a442c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a44e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a45f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a46a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4771`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4823`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4941`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a49ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a442c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a44e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a45f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a46a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4771`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4823`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4941`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a49ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a427c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a43ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a43f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a427c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a43ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a43f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4407`

## string_xrefs

- `0x1800a420a`: `ParseiTunesID3TagInfo`
- `0x1800a4483`: `ParseiTunesID3TagInfo`
- `0x1800a4538`: `ParseiTunesID3TagInfo`
- `0x1800a464f`: `ParseiTunesID3TagInfo`
- `0x1800a46fa`: `ParseiTunesID3TagInfo`
- `0x1800a47c8`: `ParseiTunesID3TagInfo`
- `0x1800a487a`: `ParseiTunesID3TagInfo`
- `0x1800a4909`: `ParseiTunesID3TagInfo`
- `0x1800a4998`: `ParseiTunesID3TagInfo`
- `0x1800a4a45`: `ParseiTunesID3TagInfo`
- `0x1800a4ad9`: `ParseiTunesID3TagInfo`
- `0x1800a4b68`: `ParseiTunesID3TagInfo`
- `0x1800a4bfc`: `ParseiTunesID3TagInfo`

## pseudocode

```c
__int64 __fastcall ParseiTunesID3TagInfo(
        struct CID3Header *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  char *v5; // r12
  int EncoderDelayFromiTuneSMPBTag; // ebx
  __int64 v7; // rdx
  void *v8; // r15
  unsigned int v10; // r14d
  __int64 v11; // rdx
  void *v12; // rcx
  struct CID3Frame *Frame; // r13
  __int64 v14; // rsi
  unsigned int v15; // edi
  __int64 v16; // rdx
  unsigned int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // edi
  void *v23; // rcx
  __int64 v24; // rdx
  void *v25; // rbx
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // r10d
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  char *v36; // rdi
  __int64 v37; // r14
  __int64 v38; // r15
  int v39; // r12d
  __int64 v40; // rdx
  void *v41; // rcx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v75; // [rsp+20h] [rbp-38h]
  unsigned int v76; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  void *v78; // [rsp+40h] [rbp-18h] BYREF
  LPVOID Buf1; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v80; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int *v81; // [rsp+A8h] [rbp+50h]
  unsigned int *v82; // [rsp+B0h] [rbp+58h]
  unsigned __int64 *v83; // [rsp+B8h] [rbp+60h]

  v83 = a4;
  v82 = a3;
  v81 = a2;
  pv = 0;
  *a2 = -1;
  v5 = 0;
  *a3 = -1;
  v76 = 0;
  Buf1 = 0;
  v78 = 0;
  *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v80, "ParseiTunesID3TagInfo", 72);
  if ( this )
  {
    v10 = 0;
    while ( 1 )
    {
      Frame = CID3Header::FindFrame(this, "COMM", v10);
      if ( !Frame )
      {
        Frame = CID3Header::FindFrame(this, "COM", v10);
        if ( !Frame )
          break;
      }
      v14 = *((unsigned int *)Frame + 30);
      v15 = v14 + 1;
      if ( (int)v14 + 1 < (unsigned int)v14 )
      {
        v72 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v73;
          if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
          {
            v72 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v72 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        EncoderDelayFromiTuneSMPBTag = -2147024362;
        if ( *((_BYTE *)v72 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "ParseiTunesID3TagInfo", 85, -2147024362);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v62 = 11;
LABEL_110:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v62,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          0,
          EncoderDelayFromiTuneSMPBTag);
        goto LABEL_44;
      }
      v80 = v14 + 1;
      EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v12, 0, v15, &v78);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v71, "ParseiTunesID3TagInfo", 86, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_43;
        v35 = 12;
        goto LABEL_42;
      }
      v5 = (char *)v78;
      memcpy_0(v78, *((const void **)Frame + 14), (unsigned int)v14);
      v5[v14] = 0;
      v17 = *v5;
      if ( (unsigned int)ID3TextEncodingNULSize(v17) + 4 > *((_DWORD *)Frame + 17) )
      {
        v66 = (wchar_t *)CallStackTracing::s_wpInstance;
        EncoderDelayFromiTuneSMPBTag = -1072875829;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v67;
          if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
          {
            v66 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v66 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
          if ( *((_DWORD *)v68 + 499) != -1072875829 )
            CallStackContext::TraceFailure(v68, "ParseiTunesID3TagInfo", 99, -1072875829);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v62 = 13;
        goto LABEL_110;
      }
      EncoderDelayFromiTuneSMPBTag = ULongSub(v15, 4u, &v80);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v65, "ParseiTunesID3TagInfo", 103, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v62 = 15;
        goto LABEL_110;
      }
      EncoderDelayFromiTuneSMPBTag = IsID3TextStringEncodingSupported(v17);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          {
            v59 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v59 + 8) )
        {
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
          if ( *((_DWORD *)v61 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v61, "ParseiTunesID3TagInfo", 108, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v62 = 16;
        goto LABEL_110;
      }
      v22 = ID3EncodedTextStringSize(v21, v5 + 4, v80);
      EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v23, 1u, 0x14u, &Buf1);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v57;
          if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
          {
            v56 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v56 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v56 + 8) )
        {
          v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
          if ( *((_DWORD *)v58 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v58, "ParseiTunesID3TagInfo", 116, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_43;
        v35 = 17;
        goto LABEL_42;
      }
      v25 = Buf1;
      if ( v22 == (unsigned int)WideCharToID3EncodedTextString(v17, 1, L"iTunSMPB")
        && v25
        && !memcmp_0(v25, v5 + 4, v22) )
      {
        if ( v22 >= 0xFFFFFFFC )
        {
          v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          EncoderDelayFromiTuneSMPBTag = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v55, "ParseiTunesID3TagInfo", 123, -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_43;
          v35 = 18;
        }
        else
        {
          EncoderDelayFromiTuneSMPBTag = ULongSub(v80, v22, &v80);
          if ( EncoderDelayFromiTuneSMPBTag < 0 )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
              CallStackTracing::s_wpInstance = v33;
              if ( v33
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
              {
                v32 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v32 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v32 + 8) )
            {
              v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
              if ( *((_DWORD *)v34 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v34, "ParseiTunesID3TagInfo", 124, EncoderDelayFromiTuneSMPBTag);
            }
            if ( g_wppLevels )
            {
              v35 = 19;
              goto LABEL_42;
            }
LABEL_43:
            v5 = (char *)v78;
LABEL_44:
            v8 = pv;
LABEL_45:
            (*(void (__fastcall **)(struct CID3Frame *))(*(_QWORD *)Frame + 16LL))(Frame);
            goto LABEL_6;
          }
          v36 = (char *)v78 + v31;
          v37 = (unsigned int)ID3EncodedTextStringSize(v17, v36, v80);
          v38 = (unsigned int)ID3EncodedTextStringToWideChar(v17, v36, v37, 0, 0);
          v39 = v38;
          EncoderDelayFromiTuneSMPBTag = ULongLongToULong(2 * v38, &v76);
          if ( EncoderDelayFromiTuneSMPBTag >= 0 )
          {
            EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v41, 1u, v76, &pv);
            if ( EncoderDelayFromiTuneSMPBTag >= 0 )
            {
              v75 = v38;
              v8 = pv;
              ID3EncodedTextStringToWideChar(v17, v36, (unsigned int)v37, pv, v75);
              EncoderDelayFromiTuneSMPBTag = FindEncoderDelayFromiTuneSMPBTag(
                                               (_DWORD)v8,
                                               v39,
                                               (_DWORD)v81,
                                               (_DWORD)v82,
                                               (__int64)v83);
              if ( EncoderDelayFromiTuneSMPBTag < 0 )
              {
                v50 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
                  CallStackTracing::s_wpInstance = v51;
                  if ( v51
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                  {
                    v50 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v50 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v50 + 8) )
                {
                  v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                  if ( *((_DWORD *)v52 + 499) != EncoderDelayFromiTuneSMPBTag )
                    CallStackContext::TraceFailure(v52, "ParseiTunesID3TagInfo", 131, EncoderDelayFromiTuneSMPBTag);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    22,
                    &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
                    0,
                    EncoderDelayFromiTuneSMPBTag);
              }
              v5 = (char *)v78;
              goto LABEL_45;
            }
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v46 + 8) )
            {
              v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
              if ( *((_DWORD *)v48 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v48, "ParseiTunesID3TagInfo", 129, EncoderDelayFromiTuneSMPBTag);
            }
            if ( !g_wppLevels )
              goto LABEL_43;
            v35 = 21;
          }
          else
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
              CallStackTracing::s_wpInstance = v43;
              if ( v43
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
              {
                v42 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v42 + 8) )
            {
              v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
              if ( *((_DWORD *)v44 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v44, "ParseiTunesID3TagInfo", 128, EncoderDelayFromiTuneSMPBTag);
            }
            if ( !g_wppLevels )
              goto LABEL_43;
            v35 = 20;
          }
        }
LABEL_42:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v35,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          0,
          EncoderDelayFromiTuneSMPBTag);
        goto LABEL_43;
      }
      ++v10;
      (*(void (__fastcall **)(struct CID3Frame *))(*(_QWORD *)Frame + 16LL))(Frame);
      CoTaskMemFree(0);
      pv = 0;
      CoTaskMemFree(v25);
      Buf1 = 0;
      CoTaskMemFree(v78);
      v5 = 0;
      v78 = 0;
    }
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    EncoderDelayFromiTuneSMPBTag = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != -1072875819 )
        CallStackContext::TraceFailure(v29, "ParseiTunesID3TagInfo", 138, -1072875819);
    }
    if ( g_wppLevels )
    {
      v7 = 23;
      goto LABEL_4;
    }
  }
  else
  {
    EncoderDelayFromiTuneSMPBTag = -1072875819;
    if ( g_wppLevels >= 8u )
    {
      v7 = 10;
LABEL_4:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
        0,
        -1072875819);
    }
  }
  v8 = pv;
LABEL_6:
  CoTaskMemFree(v8);
  CoTaskMemFree(Buf1);
  CoTaskMemFree(v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v80);
  return (unsigned int)EncoderDelayFromiTuneSMPBTag;
}

```

## disassembly

```asm
0x1800a41d4  mov     [rsp-40h+arg_18], r9
0x1800a41d9  mov     [rsp-40h+arg_10], r8
0x1800a41de  mov     [rsp-40h+arg_8], rdx
0x1800a41e3  push    rbp
0x1800a41e4  push    rbx
0x1800a41e5  push    rsi
0x1800a41e6  push    rdi
0x1800a41e7  push    r12
0x1800a41e9  push    r13
0x1800a41eb  push    r14
0x1800a41ed  push    r15
0x1800a41ef  mov     rbp, rsp
0x1800a41f2  sub     rsp, 58h
0x1800a41f6  xor     esi, esi
0x1800a41f8  mov     r15, rcx
0x1800a41fb  or      ecx, 0FFFFFFFFh
0x1800a41fe  mov     [rbp+pv], rsi
0x1800a4202  mov     [rdx], ecx
0x1800a4204  mov     r12d, esi
0x1800a4207  mov     [r8], ecx
0x1800a420a  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a4211  lea     r8d, [rsi+48h]; int
0x1800a4215  mov     [rbp+var_28], esi
0x1800a4218  lea     rcx, [rbp+arg_0]; this
0x1800a421c  mov     [rbp+Buf1], rsi
0x1800a4220  mov     [rbp+var_18], rsi
0x1800a4224  mov     [r9], rsi
0x1800a4227  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a422c  test    r15, r15
0x1800a422f  jnz     short loc_1800A429E
0x1800a4231  mov     edi, 0C00D36D5h
0x1800a4236  mov     ebx, edi
0x1800a4238  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800a423f  jb      short loc_1800A4262
0x1800a4241  lea     edx, [rsi+0Ah]
0x1800a4244  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a424b  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a4252  xor     r9d, r9d
0x1800a4255  mov     dword ptr [rsp+58h+var_38], edi
0x1800a4259  mov     rcx, [rcx+10h]
0x1800a425d  call    WPP_SF_qD
0x1800a4262  mov     r15, [rbp+pv]
0x1800a4266  mov     rcx, r15; pv
0x1800a4269  call    cs:__imp_CoTaskMemFree
0x1800a426f  mov     rcx, [rbp+Buf1]; pv
0x1800a4273  call    cs:__imp_CoTaskMemFree
0x1800a4279  mov     rcx, r12; pv
0x1800a427c  call    cs:__imp_CoTaskMemFree
0x1800a4282  lea     rcx, [rbp+arg_0]; this
0x1800a4286  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a428b  mov     eax, ebx
0x1800a428d  add     rsp, 58h
0x1800a4291  pop     r15
0x1800a4293  pop     r14
0x1800a4295  pop     r13
0x1800a4297  pop     r12
0x1800a4299  pop     rdi
0x1800a429a  pop     rsi
0x1800a429b  pop     rbx
0x1800a429c  pop     rbp
0x1800a429d  retn
0x1800a429e  mov     r14d, esi
0x1800a42a1  mov     r8d, r14d; unsigned int
0x1800a42a4  lea     rdx, Str1; "COMM"
0x1800a42ab  mov     rcx, r15; this
0x1800a42ae  call    ?FindFrame@CID3Header@@QEAAPEAVCID3Frame@@PEBDI@Z; CID3Header::FindFrame(char const *,uint)
0x1800a42b3  mov     r13, rax
0x1800a42b6  test    rax, rax
0x1800a42b9  jnz     short loc_1800A42D9
0x1800a42bb  mov     r8d, r14d; unsigned int
0x1800a42be  lea     rdx, aCom; "COM"
0x1800a42c5  mov     rcx, r15; this
0x1800a42c8  call    ?FindFrame@CID3Header@@QEAAPEAVCID3Frame@@PEBDI@Z; CID3Header::FindFrame(char const *,uint)
0x1800a42cd  mov     r13, rax
0x1800a42d0  test    rax, rax
0x1800a42d3  jz      loc_1800A4419
0x1800a42d9  mov     esi, [r13+78h]
0x1800a42dd  lea     edi, [rsi+1]
0x1800a42e0  cmp     edi, esi
0x1800a42e2  jb      loc_1800A4B94
0x1800a42e8  mov     r8d, edi; unsigned __int64
0x1800a42eb  lea     r9, [rbp+var_18]; void **
0x1800a42ef  xor     edx, edx; unsigned int
0x1800a42f1  mov     [rbp+arg_0], edi
0x1800a42f4  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800a42f9  mov     ebx, eax
0x1800a42fb  test    eax, eax
0x1800a42fd  js      loc_1800A4B05
0x1800a4303  mov     r12, [rbp+var_18]
0x1800a4307  mov     r8d, esi; Size
0x1800a430a  mov     rdx, [r13+70h]; Src
0x1800a430e  mov     rcx, r12; void *
0x1800a4311  call    memcpy_0
0x1800a4316  mov     byte ptr [rsi+r12], 0
0x1800a431b  movsx   esi, byte ptr [r12]
0x1800a4320  mov     ecx, esi
0x1800a4322  call    ?ID3TextEncodingNULSize@@YAKW4ID3_TEXTENC@@@Z; ID3TextEncodingNULSize(ID3_TEXTENC)
0x1800a4327  add     eax, 4
0x1800a432a  cmp     eax, [r13+44h]
0x1800a432e  ja      loc_1800A4A71
0x1800a4334  lea     r8, [rbp+arg_0]; unsigned int *
0x1800a4338  mov     edx, 4; unsigned int
0x1800a433d  mov     ecx, edi; unsigned int
0x1800a433f  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800a4344  mov     ebx, eax
0x1800a4346  test    eax, eax
0x1800a4348  js      loc_1800A49E2
0x1800a434e  mov     ecx, esi
0x1800a4350  call    ?IsID3TextStringEncodingSupported@@YAJW4ID3_TEXTENC@@@Z; IsID3TextStringEncodingSupported(ID3_TEXTENC)
0x1800a4355  mov     ebx, eax
0x1800a4357  test    eax, eax
0x1800a4359  js      loc_1800A4935
0x1800a435f  mov     r8d, [rbp+arg_0]
0x1800a4363  lea     rdx, [r12+4]
0x1800a4368  call    ?ID3EncodedTextStringSize@@YAHW4ID3_TEXTENC@@PEBDK@Z; ID3EncodedTextStringSize(ID3_TEXTENC,char const *,ulong)
0x1800a436d  mov     edx, 1; unsigned int
0x1800a4372  mov     edi, eax
0x1800a4374  lea     r9, [rbp+Buf1]; void **
0x1800a4378  lea     r8d, [rdx+13h]; unsigned __int64
0x1800a437c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800a4381  mov     ebx, eax
0x1800a4383  test    eax, eax
0x1800a4385  js      loc_1800A48A6
0x1800a438b  mov     rbx, [rbp+Buf1]
0x1800a438f  lea     r8, ?s_szITunSMPBTag@@3QBGB; "iTunSMPB"
0x1800a4396  mov     r9d, 9
0x1800a439c  mov     [rsp+58h+var_30], 14h
0x1800a43a4  mov     ecx, esi
0x1800a43a6  mov     [rsp+58h+var_38], rbx
0x1800a43ab  lea     edx, [r9-8]
0x1800a43af  call    ?WideCharToID3EncodedTextString@@YAHW4ID3_TEXTENC@@HPEBGHPEADH@Z; WideCharToID3EncodedTextString(ID3_TEXTENC,int,ushort const *,int,char *,int)
0x1800a43b4  cmp     edi, eax
0x1800a43b6  jnz     short loc_1800A43D5
0x1800a43b8  test    rbx, rbx
0x1800a43bb  jz      short loc_1800A43D5
0x1800a43bd  mov     r8d, edi; Size
0x1800a43c0  lea     rdx, [r12+4]; Buf2
0x1800a43c5  mov     rcx, rbx; Buf1
0x1800a43c8  call    memcmp_0
0x1800a43cd  test    eax, eax
0x1800a43cf  jz      loc_1800A44AF
0x1800a43d5  mov     rax, [r13+0]
0x1800a43d9  mov     rcx, r13
0x1800a43dc  inc     r14d
0x1800a43df  mov     rax, [rax+10h]
0x1800a43e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a43e8  xor     ecx, ecx; pv
0x1800a43ea  call    cs:__imp_CoTaskMemFree
0x1800a43f0  xor     esi, esi
0x1800a43f2  mov     rcx, rbx; pv
0x1800a43f5  mov     [rbp+pv], rsi
0x1800a43f9  call    cs:__imp_CoTaskMemFree
0x1800a43ff  mov     rcx, [rbp+var_18]; pv
0x1800a4403  mov     [rbp+Buf1], rsi
0x1800a4407  call    cs:__imp_CoTaskMemFree
0x1800a440d  mov     r12d, esi
0x1800a4410  mov     [rbp+var_18], rsi
0x1800a4414  jmp     loc_1800A42A1
0x1800a4419  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4420  mov     edi, 0C00D36D5h
0x1800a4425  mov     ebx, edi
0x1800a4427  test    rcx, rcx
0x1800a442a  jnz     short loc_1800A446D
0x1800a442c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a4432  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4439  mov     rcx, rax
0x1800a443c  test    rax, rax
0x1800a443f  jz      short loc_1800A445F
0x1800a4441  mov     rax, [rax]
0x1800a4444  mov     edx, 7F0h
0x1800a4449  mov     rax, [rax+8]
0x1800a444d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4452  test    eax, eax
0x1800a4454  jz      short loc_1800A445F
0x1800a4456  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a445d  jmp     short loc_1800A446D
0x1800a445f  lea     rcx, qword_1801B07E0; this
0x1800a4466  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a446d  cmp     [rcx+8], sil
0x1800a4471  jz      short loc_1800A4498
0x1800a4473  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4478  cmp     [rax+7CCh], edi
0x1800a447e  jz      short loc_1800A4498
0x1800a4480  mov     r9d, edi; int
0x1800a4483  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a448a  mov     r8d, 8Ah; int
0x1800a4490  mov     rcx, rax; this
0x1800a4493  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4498  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a449f  jb      loc_1800A4262
0x1800a44a5  mov     edx, 17h
0x1800a44aa  jmp     loc_1800A4244
0x1800a44af  lea     r10d, [rdi+4]
0x1800a44b3  cmp     r10d, 4
0x1800a44b7  jb      loc_1800A4812
0x1800a44bd  mov     ecx, [rbp+arg_0]; unsigned int
0x1800a44c0  lea     r8, [rbp+arg_0]; unsigned int *
0x1800a44c4  mov     edx, edi; unsigned int
0x1800a44c6  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800a44cb  mov     ebx, eax
0x1800a44cd  test    eax, eax
0x1800a44cf  jns     loc_1800A459F
0x1800a44d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a44dc  test    rcx, rcx
0x1800a44df  jnz     short loc_1800A4522
0x1800a44e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a44e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a44ee  mov     rcx, rax
0x1800a44f1  test    rax, rax
0x1800a44f4  jz      short loc_1800A4514
0x1800a44f6  mov     rax, [rax]
0x1800a44f9  mov     edx, 7F0h
0x1800a44fe  mov     rax, [rax+8]
0x1800a4502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4507  test    eax, eax
0x1800a4509  jz      short loc_1800A4514
0x1800a450b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4512  jmp     short loc_1800A4522
0x1800a4514  lea     rcx, qword_1801B07E0; this
0x1800a451b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4522  cmp     byte ptr [rcx+8], 0
0x1800a4526  jz      short loc_1800A454D
0x1800a4528  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a452d  cmp     [rax+7CCh], ebx
0x1800a4533  jz      short loc_1800A454D
0x1800a4535  mov     r9d, ebx; int
0x1800a4538  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a453f  mov     r8d, 7Ch ; '|'; int
0x1800a4545  mov     rcx, rax; this
0x1800a4548  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a454d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4554  jb      short loc_1800A4579
0x1800a4556  mov     edx, 13h
0x1800a455b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4562  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a4569  xor     r9d, r9d
0x1800a456c  mov     dword ptr [rsp+58h+var_38], ebx
0x1800a4570  mov     rcx, [rcx+10h]
0x1800a4574  call    WPP_SF_qD
0x1800a4579  mov     r12, [rbp+var_18]
0x1800a457d  mov     r15, [rbp+pv]
0x1800a4581  test    r13, r13
0x1800a4584  jz      loc_1800A4266
0x1800a458a  mov     rax, [r13+0]
0x1800a458e  mov     rcx, r13
0x1800a4591  mov     rax, [rax+10h]
0x1800a4595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a459a  jmp     loc_1800A4266
0x1800a459f  mov     r8d, [rbp+arg_0]
0x1800a45a3  mov     ecx, esi
0x1800a45a5  mov     edi, r10d
0x1800a45a8  add     rdi, [rbp+var_18]
0x1800a45ac  mov     rdx, rdi
0x1800a45af  call    ?ID3EncodedTextStringSize@@YAHW4ID3_TEXTENC@@PEBDK@Z; ID3EncodedTextStringSize(ID3_TEXTENC,char const *,ulong)
0x1800a45b4  mov     r8d, eax
0x1800a45b7  mov     dword ptr [rsp+58h+var_38], 0
0x1800a45bf  mov     rdx, rdi
0x1800a45c2  mov     ecx, esi
0x1800a45c4  xor     r9d, r9d
0x1800a45c7  mov     r14d, eax
0x1800a45ca  call    ?ID3EncodedTextStringToWideChar@@YAHW4ID3_TEXTENC@@PEBDHPEAGH@Z; ID3EncodedTextStringToWideChar(ID3_TEXTENC,char const *,int,ushort *,int)
0x1800a45cf  mov     r15d, eax
0x1800a45d2  lea     rdx, [rbp+var_28]; unsigned int *
0x1800a45d6  mov     r12d, eax
0x1800a45d9  lea     rcx, [r15+r15]; unsigned __int64
0x1800a45dd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800a45e2  mov     ebx, eax
0x1800a45e4  test    eax, eax
0x1800a45e6  jns     loc_1800A467B
0x1800a45ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a45f3  test    rcx, rcx
0x1800a45f6  jnz     short loc_1800A4639
0x1800a45f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a45fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4605  mov     rcx, rax
0x1800a4608  test    rax, rax
0x1800a460b  jz      short loc_1800A462B
0x1800a460d  mov     rax, [rax]
0x1800a4610  mov     edx, 7F0h
0x1800a4615  mov     rax, [rax+8]
0x1800a4619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a461e  test    eax, eax
0x1800a4620  jz      short loc_1800A462B
0x1800a4622  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4629  jmp     short loc_1800A4639
0x1800a462b  lea     rcx, qword_1801B07E0; this
0x1800a4632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4639  cmp     byte ptr [rcx+8], 0
0x1800a463d  jz      short loc_1800A4664
0x1800a463f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4644  cmp     [rax+7CCh], ebx
0x1800a464a  jz      short loc_1800A4664
0x1800a464c  mov     r9d, ebx; int
0x1800a464f  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a4656  mov     r8d, 80h; int
0x1800a465c  mov     rcx, rax; this
0x1800a465f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4664  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a466b  jb      loc_1800A4579
0x1800a4671  mov     edx, 14h
  ... truncated ...
```
