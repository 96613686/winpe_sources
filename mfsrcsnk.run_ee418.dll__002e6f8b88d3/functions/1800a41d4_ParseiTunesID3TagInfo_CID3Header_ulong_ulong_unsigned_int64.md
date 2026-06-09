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
  __int64 v13; // r8
  __int64 v14; // r9
  struct CID3Frame *Frame; // r13
  __int64 v16; // rsi
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned int v32; // edi
  void *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  void *v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  unsigned int v47; // r10d
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  char *v52; // rdi
  __int64 v53; // r14
  __int64 v54; // r15
  int v55; // r12d
  __int64 v56; // rdx
  void *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  wchar_t *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // rdx
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  wchar_t *v88; // rcx
  CallStackTracing *v89; // rax
  struct CallStackContext *v90; // rax
  wchar_t *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  wchar_t *v94; // rcx
  CallStackTracing *v95; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v97; // [rsp+20h] [rbp-38h]
  __int64 v98; // [rsp+20h] [rbp-38h]
  unsigned int v99; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  void *v101; // [rsp+40h] [rbp-18h] BYREF
  LPVOID Buf1; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v103; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int *v104; // [rsp+A8h] [rbp+50h]
  unsigned int *v105; // [rsp+B0h] [rbp+58h]
  unsigned __int64 *v106; // [rsp+B8h] [rbp+60h]

  v106 = a4;
  v105 = a3;
  v104 = a2;
  pv = 0;
  *a2 = -1;
  v5 = 0;
  *a3 = -1;
  v99 = 0;
  Buf1 = 0;
  v101 = 0;
  *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v103, "ParseiTunesID3TagInfo", 72);
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
      v16 = *((unsigned int *)Frame + 30);
      v17 = v16 + 1;
      if ( (int)v16 + 1 < (unsigned int)v16 )
      {
        v94 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v95 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
          CallStackTracing::s_wpInstance = v95;
          if ( v95 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v95 + 8LL))(v95, 2032) )
          {
            v94 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v94 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        EncoderDelayFromiTuneSMPBTag = -2147024362;
        if ( *((_BYTE *)v94 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v94);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "ParseiTunesID3TagInfo", 85, -2147024362);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v84 = 11;
LABEL_110:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v84,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          0,
          EncoderDelayFromiTuneSMPBTag);
        goto LABEL_44;
      }
      v103 = v16 + 1;
      EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v12, 0, v17, &v101);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v91 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v92;
          if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
          {
            v91 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v91 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v91 + 8) )
        {
          v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
          if ( *((_DWORD *)v93 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v93, "ParseiTunesID3TagInfo", 86, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_43;
        v51 = 12;
        goto LABEL_42;
      }
      v5 = (char *)v101;
      memcpy_0(v101, *((const void **)Frame + 14), (unsigned int)v16);
      v5[v16] = 0;
      v21 = *v5;
      if ( (unsigned int)ID3TextEncodingNULSize(v21) + 4 > *((_DWORD *)Frame + 17) )
      {
        v88 = (wchar_t *)CallStackTracing::s_wpInstance;
        EncoderDelayFromiTuneSMPBTag = -1072875829;
        if ( !CallStackTracing::s_wpInstance )
        {
          v89 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v89;
          if ( v89 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v89 + 8LL))(v89, 2032) )
          {
            v88 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v88 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v88 + 8) )
        {
          v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v88);
          if ( *((_DWORD *)v90 + 499) != -1072875829 )
            CallStackContext::TraceFailure(v90, "ParseiTunesID3TagInfo", 99, -1072875829);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v84 = 13;
        goto LABEL_110;
      }
      EncoderDelayFromiTuneSMPBTag = ULongSub(v17, 4u, &v103);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v86;
          if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
          {
            v85 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v85 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v85 + 8) )
        {
          v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
          if ( *((_DWORD *)v87 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v87, "ParseiTunesID3TagInfo", 103, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v84 = 15;
        goto LABEL_110;
      }
      EncoderDelayFromiTuneSMPBTag = IsID3TextStringEncodingSupported(v21);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v81 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v30, v31);
          CallStackTracing::s_wpInstance = v82;
          if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
          {
            v81 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v81 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v81 + 8) )
        {
          v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
          if ( *((_DWORD *)v83 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v83, "ParseiTunesID3TagInfo", 108, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_44;
        v84 = 16;
        goto LABEL_110;
      }
      v32 = ID3EncodedTextStringSize(v29, v5 + 4, v103);
      EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v33, 1u, 0x14u, &Buf1);
      if ( EncoderDelayFromiTuneSMPBTag < 0 )
      {
        v78 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
          CallStackTracing::s_wpInstance = v79;
          if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
          {
            v78 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v78 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v78 + 8) )
        {
          v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
          if ( *((_DWORD *)v80 + 499) != EncoderDelayFromiTuneSMPBTag )
            CallStackContext::TraceFailure(v80, "ParseiTunesID3TagInfo", 116, EncoderDelayFromiTuneSMPBTag);
        }
        if ( !g_wppLevels )
          goto LABEL_43;
        v51 = 17;
        goto LABEL_42;
      }
      v37 = Buf1;
      HIDWORD(v97) = HIDWORD(Buf1);
      if ( v32 == (unsigned int)WideCharToID3EncodedTextString(v21, 1, L"iTunSMPB")
        && v37
        && !memcmp_0(v37, v5 + 4, v32) )
      {
        if ( v32 >= 0xFFFFFFFC )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
          EncoderDelayFromiTuneSMPBTag = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
            CallStackTracing::s_wpInstance = v76;
            if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
            {
              v75 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v75 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v75 + 8) )
          {
            v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
            if ( *((_DWORD *)v77 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v77, "ParseiTunesID3TagInfo", 123, -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_43;
          v51 = 18;
        }
        else
        {
          EncoderDelayFromiTuneSMPBTag = ULongSub(v103, v32, &v103);
          if ( EncoderDelayFromiTuneSMPBTag < 0 )
          {
            v48 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
              CallStackTracing::s_wpInstance = v49;
              if ( v49
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
              {
                v48 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v48 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v48 + 8) )
            {
              v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
              if ( *((_DWORD *)v50 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v50, "ParseiTunesID3TagInfo", 124, EncoderDelayFromiTuneSMPBTag);
            }
            if ( g_wppLevels )
            {
              v51 = 19;
              goto LABEL_42;
            }
LABEL_43:
            v5 = (char *)v101;
LABEL_44:
            v8 = pv;
LABEL_45:
            (*(void (__fastcall **)(struct CID3Frame *))(*(_QWORD *)Frame + 16LL))(Frame);
            goto LABEL_6;
          }
          v52 = (char *)v101 + v47;
          LODWORD(v97) = 0;
          v53 = (unsigned int)ID3EncodedTextStringSize(v21, v52, v103);
          v54 = (unsigned int)ID3EncodedTextStringToWideChar(v21, v52, v53, 0, v97);
          v55 = v54;
          EncoderDelayFromiTuneSMPBTag = ULongLongToULong(2 * v54, &v99);
          if ( EncoderDelayFromiTuneSMPBTag >= 0 )
          {
            EncoderDelayFromiTuneSMPBTag = CTCoAllocPolicy::Alloc(v57, 1u, v99, &pv);
            if ( EncoderDelayFromiTuneSMPBTag >= 0 )
            {
              LODWORD(v98) = v54;
              v8 = pv;
              ID3EncodedTextStringToWideChar(v21, v52, (unsigned int)v53, pv, v98);
              EncoderDelayFromiTuneSMPBTag = FindEncoderDelayFromiTuneSMPBTag(
                                               (_DWORD)v8,
                                               v55,
                                               (_DWORD)v104,
                                               (_DWORD)v105,
                                               (__int64)v106);
              if ( EncoderDelayFromiTuneSMPBTag < 0 )
              {
                v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v69, v70, v71);
                  CallStackTracing::s_wpInstance = v73;
                  if ( v73
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
                  {
                    v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v72 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v72 + 8) )
                {
                  v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
                  if ( *((_DWORD *)v74 + 499) != EncoderDelayFromiTuneSMPBTag )
                    CallStackContext::TraceFailure(v74, "ParseiTunesID3TagInfo", 131, EncoderDelayFromiTuneSMPBTag);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    22,
                    &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
                    0,
                    EncoderDelayFromiTuneSMPBTag);
              }
              v5 = (char *)v101;
              goto LABEL_45;
            }
            v66 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
              CallStackTracing::s_wpInstance = v67;
              if ( v67
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
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
              if ( *((_DWORD *)v68 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v68, "ParseiTunesID3TagInfo", 129, EncoderDelayFromiTuneSMPBTag);
            }
            if ( !g_wppLevels )
              goto LABEL_43;
            v51 = 21;
          }
          else
          {
            v60 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v58, v59);
              CallStackTracing::s_wpInstance = v61;
              if ( v61
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
              {
                v60 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v60 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v60 + 8) )
            {
              v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
              if ( *((_DWORD *)v62 + 499) != EncoderDelayFromiTuneSMPBTag )
                CallStackContext::TraceFailure(v62, "ParseiTunesID3TagInfo", 128, EncoderDelayFromiTuneSMPBTag);
            }
            if ( !g_wppLevels )
              goto LABEL_43;
            v51 = 20;
          }
        }
LABEL_42:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v51,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          0,
          EncoderDelayFromiTuneSMPBTag);
        goto LABEL_43;
      }
      ++v10;
      (*(void (__fastcall **)(struct CID3Frame *))(*(_QWORD *)Frame + 16LL))(Frame);
      CoTaskMemFree(0);
      pv = 0;
      CoTaskMemFree(v37);
      Buf1 = 0;
      CoTaskMemFree(v101);
      v5 = 0;
      v101 = 0;
    }
    v41 = (wchar_t *)CallStackTracing::s_wpInstance;
    EncoderDelayFromiTuneSMPBTag = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)v43 + 499) != -1072875819 )
        CallStackContext::TraceFailure(v43, "ParseiTunesID3TagInfo", 138, -1072875819);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v103);
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
