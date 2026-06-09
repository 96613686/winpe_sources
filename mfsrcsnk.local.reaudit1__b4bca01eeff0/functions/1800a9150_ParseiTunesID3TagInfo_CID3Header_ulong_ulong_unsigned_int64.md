# ParseiTunesID3TagInfo(CID3Header *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x1800a9150`
- end: `0x1800a9c15`
- name: `?ParseiTunesID3TagInfo@@YAJPEAVCID3Header@@PEAK1PEA_K@Z`
- size: `2757`
- prototype: `__int64 __fastcall(struct CID3Header *this, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006a124`
- `0x1800ae6e0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18002c080`
- `0x18002c21c`
- `0x18002c24c`
- `0x180047630`
- `0x180058da4`
- `0x180079680`
- `0x180079f34`
- `0x1800828cc`
- `0x1800a9150`
- `0x180129248`
- `0x1801394d4`
- `0x180169fcc`
- `0x18017b734`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a93d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a948c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a95a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a965a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a972e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a97e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a987b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9910`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a99c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9af2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a93d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a948c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a95a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a965a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a972e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a97e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a987b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9910`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a99c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9af2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a91e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a91f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a937d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a93a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a91e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a91f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a937d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a93a6`

## string_xrefs

- `0x1800a9186`: `ParseiTunesID3TagInfo`
- `0x1800a942e`: `ParseiTunesID3TagInfo`
- `0x1800a94e9`: `ParseiTunesID3TagInfo`
- `0x1800a9606`: `ParseiTunesID3TagInfo`
- `0x1800a96b7`: `ParseiTunesID3TagInfo`
- `0x1800a978b`: `ParseiTunesID3TagInfo`
- `0x1800a9843`: `ParseiTunesID3TagInfo`
- `0x1800a98d8`: `ParseiTunesID3TagInfo`
- `0x1800a996d`: `ParseiTunesID3TagInfo`
- `0x1800a9a20`: `ParseiTunesID3TagInfo`
- `0x1800a9aba`: `ParseiTunesID3TagInfo`
- `0x1800a9b4f`: `ParseiTunesID3TagInfo`
- `0x1800a9be9`: `ParseiTunesID3TagInfo`

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
            v72 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v69 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v66 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v63 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v59 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v56 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v53 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v32 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v50 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v46 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v42 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800a9150  mov     [rsp-40h+arg_18], r9
0x1800a9155  mov     [rsp-40h+arg_10], r8
0x1800a915a  mov     [rsp-40h+arg_8], rdx
0x1800a915f  push    rbp
0x1800a9160  push    rbx
0x1800a9161  push    rsi
0x1800a9162  push    rdi
0x1800a9163  push    r12
0x1800a9165  push    r13
0x1800a9167  push    r14
0x1800a9169  push    r15
0x1800a916b  mov     rbp, rsp
0x1800a916e  sub     rsp, 58h
0x1800a9172  xor     esi, esi
0x1800a9174  mov     r15, rcx
0x1800a9177  or      ecx, 0FFFFFFFFh
0x1800a917a  mov     [rbp+pv], rsi
0x1800a917e  mov     [rdx], ecx
0x1800a9180  mov     r12d, esi
0x1800a9183  mov     [r8], ecx
0x1800a9186  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a918d  lea     r8d, [rsi+48h]; int
0x1800a9191  mov     [rbp+var_28], esi
0x1800a9194  lea     rcx, [rbp+arg_0]; this
0x1800a9198  mov     [rbp+Buf1], rsi
0x1800a919c  mov     [rbp+var_18], rsi
0x1800a91a0  mov     [r9], rsi
0x1800a91a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a91a8  test    r15, r15
0x1800a91ab  jnz     loc_1800A9231
0x1800a91b1  mov     edi, 0C00D36D5h
0x1800a91b6  mov     ebx, edi
0x1800a91b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800a91bf  jb      short loc_1800A91E2
0x1800a91c1  lea     edx, [rsi+0Ah]
0x1800a91c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a91cb  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a91d2  xor     r9d, r9d
0x1800a91d5  mov     dword ptr [rsp+58h+var_38], edi
0x1800a91d9  mov     rcx, [rcx+10h]
0x1800a91dd  call    WPP_SF_qD
0x1800a91e2  mov     r15, [rbp+pv]
0x1800a91e6  mov     rcx, r15; pv
0x1800a91e9  call    cs:__imp_CoTaskMemFree
0x1800a91f0  nop     dword ptr [rax+rax+00h]
0x1800a91f5  mov     rcx, [rbp+Buf1]; pv
0x1800a91f9  call    cs:__imp_CoTaskMemFree
0x1800a9200  nop     dword ptr [rax+rax+00h]
0x1800a9205  mov     rcx, r12; pv
0x1800a9208  call    cs:__imp_CoTaskMemFree
0x1800a920f  nop     dword ptr [rax+rax+00h]
0x1800a9214  lea     rcx, [rbp+arg_0]; this
0x1800a9218  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a921d  mov     eax, ebx
0x1800a921f  add     rsp, 58h
0x1800a9223  pop     r15
0x1800a9225  pop     r14
0x1800a9227  pop     r13
0x1800a9229  pop     r12
0x1800a922b  pop     rdi
0x1800a922c  pop     rsi
0x1800a922d  pop     rbx
0x1800a922e  pop     rbp
0x1800a922f  retn
0x1800a9231  mov     r14d, esi
0x1800a9234  mov     r8d, r14d; unsigned int
0x1800a9237  lea     rdx, Str1; "COMM"
0x1800a923e  mov     rcx, r15; this
0x1800a9241  call    ?FindFrame@CID3Header@@QEAAPEAVCID3Frame@@PEBDI@Z; CID3Header::FindFrame(char const *,uint)
0x1800a9246  mov     r13, rax
0x1800a9249  test    rax, rax
0x1800a924c  jnz     short loc_1800A926C
0x1800a924e  mov     r8d, r14d; unsigned int
0x1800a9251  lea     rdx, aCom; "COM"
0x1800a9258  mov     rcx, r15; this
0x1800a925b  call    ?FindFrame@CID3Header@@QEAAPEAVCID3Frame@@PEBDI@Z; CID3Header::FindFrame(char const *,uint)
0x1800a9260  mov     r13, rax
0x1800a9263  test    rax, rax
0x1800a9266  jz      loc_1800A93BE
0x1800a926c  mov     esi, [r13+78h]
0x1800a9270  lea     edi, [rsi+1]
0x1800a9273  cmp     edi, esi
0x1800a9275  jb      loc_1800A9B7B
0x1800a927b  mov     r8d, edi; unsigned __int64
0x1800a927e  lea     r9, [rbp+var_18]; void **
0x1800a9282  xor     edx, edx; unsigned int
0x1800a9284  mov     [rbp+arg_0], edi
0x1800a9287  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800a928c  mov     ebx, eax
0x1800a928e  test    eax, eax
0x1800a9290  js      loc_1800A9AE6
0x1800a9296  mov     r12, [rbp+var_18]
0x1800a929a  mov     r8d, esi; Size
0x1800a929d  mov     rdx, [r13+70h]; Src
0x1800a92a1  mov     rcx, r12; void *
0x1800a92a4  call    memcpy_0
0x1800a92a9  mov     byte ptr [rsi+r12], 0
0x1800a92ae  movsx   esi, byte ptr [r12]
0x1800a92b3  mov     ecx, esi
0x1800a92b5  call    ?ID3TextEncodingNULSize@@YAKW4ID3_TEXTENC@@@Z; ID3TextEncodingNULSize(ID3_TEXTENC)
0x1800a92ba  add     eax, 4
0x1800a92bd  cmp     eax, [r13+44h]
0x1800a92c1  ja      loc_1800A9A4C
0x1800a92c7  lea     r8, [rbp+arg_0]; unsigned int *
0x1800a92cb  mov     edx, 4; unsigned int
0x1800a92d0  mov     ecx, edi; unsigned int
0x1800a92d2  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800a92d7  mov     ebx, eax
0x1800a92d9  test    eax, eax
0x1800a92db  js      loc_1800A99B7
0x1800a92e1  mov     ecx, esi
0x1800a92e3  call    ?IsID3TextStringEncodingSupported@@YAJW4ID3_TEXTENC@@@Z; IsID3TextStringEncodingSupported(ID3_TEXTENC)
0x1800a92e8  mov     ebx, eax
0x1800a92ea  test    eax, eax
0x1800a92ec  js      loc_1800A9904
0x1800a92f2  mov     r8d, [rbp+arg_0]
0x1800a92f6  lea     rdx, [r12+4]
0x1800a92fb  call    ?ID3EncodedTextStringSize@@YAHW4ID3_TEXTENC@@PEBDK@Z; ID3EncodedTextStringSize(ID3_TEXTENC,char const *,ulong)
0x1800a9300  mov     edx, 1; unsigned int
0x1800a9305  mov     edi, eax
0x1800a9307  lea     r9, [rbp+Buf1]; void **
0x1800a930b  lea     r8d, [rdx+13h]; unsigned __int64
0x1800a930f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800a9314  mov     ebx, eax
0x1800a9316  test    eax, eax
0x1800a9318  js      loc_1800A986F
0x1800a931e  mov     rbx, [rbp+Buf1]
0x1800a9322  lea     r8, ?s_szITunSMPBTag@@3QBGB; "iTunSMPB"
0x1800a9329  mov     r9d, 9
0x1800a932f  mov     [rsp+58h+var_30], 14h
0x1800a9337  mov     ecx, esi
0x1800a9339  mov     [rsp+58h+var_38], rbx
0x1800a933e  lea     edx, [r9-8]
0x1800a9342  call    ?WideCharToID3EncodedTextString@@YAHW4ID3_TEXTENC@@HPEBGHPEADH@Z; WideCharToID3EncodedTextString(ID3_TEXTENC,int,ushort const *,int,char *,int)
0x1800a9347  cmp     edi, eax
0x1800a9349  jnz     short loc_1800A9368
0x1800a934b  test    rbx, rbx
0x1800a934e  jz      short loc_1800A9368
0x1800a9350  mov     r8d, edi; Size
0x1800a9353  lea     rdx, [r12+4]; Buf2
0x1800a9358  mov     rcx, rbx; Buf1
0x1800a935b  call    memcmp_0
0x1800a9360  test    eax, eax
0x1800a9362  jz      loc_1800A945A
0x1800a9368  mov     rax, [r13+0]
0x1800a936c  mov     rcx, r13
0x1800a936f  inc     r14d
0x1800a9372  mov     rax, [rax+10h]
0x1800a9376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a937b  xor     ecx, ecx; pv
0x1800a937d  call    cs:__imp_CoTaskMemFree
0x1800a9384  nop     dword ptr [rax+rax+00h]
0x1800a9389  xor     esi, esi
0x1800a938b  mov     rcx, rbx; pv
0x1800a938e  mov     [rbp+pv], rsi
0x1800a9392  call    cs:__imp_CoTaskMemFree
0x1800a9399  nop     dword ptr [rax+rax+00h]
0x1800a939e  mov     rcx, [rbp+var_18]; pv
0x1800a93a2  mov     [rbp+Buf1], rsi
0x1800a93a6  call    cs:__imp_CoTaskMemFree
0x1800a93ad  nop     dword ptr [rax+rax+00h]
0x1800a93b2  mov     r12d, esi
0x1800a93b5  mov     [rbp+var_18], rsi
0x1800a93b9  jmp     loc_1800A9234
0x1800a93be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a93c5  mov     edi, 0C00D36D5h
0x1800a93ca  mov     ebx, edi
0x1800a93cc  test    rcx, rcx
0x1800a93cf  jnz     short loc_1800A9418
0x1800a93d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a93d8  nop     dword ptr [rax+rax+00h]
0x1800a93dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a93e4  mov     rcx, rax
0x1800a93e7  test    rax, rax
0x1800a93ea  jz      short loc_1800A940A
0x1800a93ec  mov     rax, [rax]
0x1800a93ef  mov     edx, 7F0h
0x1800a93f4  mov     rax, [rax+8]
0x1800a93f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93fd  test    eax, eax
0x1800a93ff  jz      short loc_1800A940A
0x1800a9401  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9408  jmp     short loc_1800A9418
0x1800a940a  lea     rcx, qword_1801B97E0; this
0x1800a9411  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9418  cmp     [rcx+8], sil
0x1800a941c  jz      short loc_1800A9443
0x1800a941e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9423  cmp     [rax+7CCh], edi
0x1800a9429  jz      short loc_1800A9443
0x1800a942b  mov     r9d, edi; int
0x1800a942e  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a9435  mov     r8d, 8Ah; int
0x1800a943b  mov     rcx, rax; this
0x1800a943e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9443  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a944a  jb      loc_1800A91E2
0x1800a9450  mov     edx, 17h
0x1800a9455  jmp     loc_1800A91C4
0x1800a945a  lea     r10d, [rdi+4]
0x1800a945e  cmp     r10d, 4
0x1800a9462  jb      loc_1800A97D5
0x1800a9468  mov     ecx, [rbp+arg_0]; unsigned int
0x1800a946b  lea     r8, [rbp+arg_0]; unsigned int *
0x1800a946f  mov     edx, edi; unsigned int
0x1800a9471  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800a9476  mov     ebx, eax
0x1800a9478  test    eax, eax
0x1800a947a  jns     loc_1800A9550
0x1800a9480  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9487  test    rcx, rcx
0x1800a948a  jnz     short loc_1800A94D3
0x1800a948c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9493  nop     dword ptr [rax+rax+00h]
0x1800a9498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a949f  mov     rcx, rax
0x1800a94a2  test    rax, rax
0x1800a94a5  jz      short loc_1800A94C5
0x1800a94a7  mov     rax, [rax]
0x1800a94aa  mov     edx, 7F0h
0x1800a94af  mov     rax, [rax+8]
0x1800a94b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a94b8  test    eax, eax
0x1800a94ba  jz      short loc_1800A94C5
0x1800a94bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a94c3  jmp     short loc_1800A94D3
0x1800a94c5  lea     rcx, qword_1801B97E0; this
0x1800a94cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a94d3  cmp     byte ptr [rcx+8], 0
0x1800a94d7  jz      short loc_1800A94FE
0x1800a94d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a94de  cmp     [rax+7CCh], ebx
0x1800a94e4  jz      short loc_1800A94FE
0x1800a94e6  mov     r9d, ebx; int
0x1800a94e9  lea     rdx, aParseitunesid3; "ParseiTunesID3TagInfo"
0x1800a94f0  mov     r8d, 7Ch ; '|'; int
0x1800a94f6  mov     rcx, rax; this
0x1800a94f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a94fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9505  jb      short loc_1800A952A
0x1800a9507  mov     edx, 13h
0x1800a950c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9513  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a951a  xor     r9d, r9d
0x1800a951d  mov     dword ptr [rsp+58h+var_38], ebx
0x1800a9521  mov     rcx, [rcx+10h]
0x1800a9525  call    WPP_SF_qD
0x1800a952a  mov     r12, [rbp+var_18]
0x1800a952e  mov     r15, [rbp+pv]
0x1800a9532  test    r13, r13
0x1800a9535  jz      loc_1800A91E6
0x1800a953b  mov     rax, [r13+0]
0x1800a953f  mov     rcx, r13
0x1800a9542  mov     rax, [rax+10h]
0x1800a9546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a954b  jmp     loc_1800A91E6
0x1800a9550  mov     r8d, [rbp+arg_0]
0x1800a9554  mov     ecx, esi
0x1800a9556  mov     edi, r10d
0x1800a9559  add     rdi, [rbp+var_18]
0x1800a955d  mov     rdx, rdi
0x1800a9560  call    ?ID3EncodedTextStringSize@@YAHW4ID3_TEXTENC@@PEBDK@Z; ID3EncodedTextStringSize(ID3_TEXTENC,char const *,ulong)
0x1800a9565  mov     r8d, eax
0x1800a9568  mov     dword ptr [rsp+58h+var_38], 0
0x1800a9570  mov     rdx, rdi
0x1800a9573  mov     ecx, esi
0x1800a9575  xor     r9d, r9d
0x1800a9578  mov     r14d, eax
0x1800a957b  call    ?ID3EncodedTextStringToWideChar@@YAHW4ID3_TEXTENC@@PEBDHPEAGH@Z; ID3EncodedTextStringToWideChar(ID3_TEXTENC,char const *,int,ushort *,int)
0x1800a9580  mov     r15d, eax
0x1800a9583  lea     rdx, [rbp+var_28]; unsigned int *
0x1800a9587  mov     r12d, eax
0x1800a958a  lea     rcx, [r15+r15]; unsigned __int64
0x1800a958e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800a9593  mov     ebx, eax
0x1800a9595  test    eax, eax
0x1800a9597  jns     loc_1800A9632
0x1800a959d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95a4  test    rcx, rcx
0x1800a95a7  jnz     short loc_1800A95F0
0x1800a95a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a95b0  nop     dword ptr [rax+rax+00h]
0x1800a95b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95bc  mov     rcx, rax
0x1800a95bf  test    rax, rax
0x1800a95c2  jz      short loc_1800A95E2
0x1800a95c4  mov     rax, [rax]
0x1800a95c7  mov     edx, 7F0h
0x1800a95cc  mov     rax, [rax+8]
0x1800a95d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a95d5  test    eax, eax
0x1800a95d7  jz      short loc_1800A95E2
0x1800a95d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95e0  jmp     short loc_1800A95F0
0x1800a95e2  lea     rcx, qword_1801B97E0; this
0x1800a95e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95f0  cmp     byte ptr [rcx+8], 0
0x1800a95f4  jz      short loc_1800A961B
0x1800a95f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a95fb  cmp     [rax+7CCh], ebx
  ... truncated ...
```
