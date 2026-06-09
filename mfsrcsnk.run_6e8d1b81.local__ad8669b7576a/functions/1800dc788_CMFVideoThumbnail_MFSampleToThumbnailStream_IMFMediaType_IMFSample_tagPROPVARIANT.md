# CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)

- ea: `0x1800dc788`
- end: `0x1800dd324`
- name: `?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z`
- size: `2972`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaType *, struct IMFSample *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18015a8dc`
- `0x18015ad04`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180056e38`
- `0x1800734a8`
- `0x180073b14`
- `0x180073e00`
- `0x1800ca5e0`
- `0x1800dc788`
- `0x1801099f0`
- `0x18015bc0c`
- `0x18015beac`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc8c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc99c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dca62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcb1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcc0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dccfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcde3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcea0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf4b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd000`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd0b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd21c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc8c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc99c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dca62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcb1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcc0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dccfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcde3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcea0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf4b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd000`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd0b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd21c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dcf2f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dcf2f`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::MFSampleToThumbnailStream(
        CMFVideoThumbnail *this,
        struct IMFMediaType *a2,
        struct IMFSample *a3,
        struct tagPROPVARIANT *a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  __int64 v11; // rdx
  HRESULT v12; // ebx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct IMFSample *v21; // rdi
  HRESULT (__stdcall *GetBufferByIndex)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  unsigned int v31; // r14d
  unsigned int v32; // r15d
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // ecx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  int v43; // ebx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  unsigned int v47; // r14d
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  _BYTE v67[8]; // [rsp+40h] [rbp-99h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-91h] BYREF
  struct IMFMediaType *v69; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v70; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v71; // [rsp+5Ch] [rbp-7Dh] BYREF
  unsigned int v72; // [rsp+60h] [rbp-79h] BYREF
  __int64 v73; // [rsp+68h] [rbp-71h] BYREF
  struct IMFSample *v74; // [rsp+70h] [rbp-69h] BYREF
  int v75; // [rsp+78h] [rbp-61h] BYREF
  __int64 v76; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v77[2]; // [rsp+88h] [rbp-51h] BYREF
  int v78; // [rsp+98h] [rbp-41h] BYREF
  __int128 v79; // [rsp+9Ch] [rbp-3Dh]
  __int128 v80; // [rsp+ACh] [rbp-2Dh] BYREF
  __int64 v81; // [rsp+BCh] [rbp-1Dh]
  __int128 Buf2; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v83[16]; // [rsp+D8h] [rbp-1h] BYREF

  memset(v77, 0, 14);
  v78 = 0;
  v81 = 0;
  v69 = 0;
  v74 = 0;
  v79 = 0;
  v73 = 0;
  v80 = 0;
  ppstm = 0;
  Buf2 = 0;
  v70 = 0;
  v72 = 0;
  v76 = 0;
  v75 = 0;
  v71 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v67,
    "CMFVideoThumbnail::MFSampleToThumbnailStream",
    1654);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v83);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
  v12 = CMFVideoThumbnail::ConvertYUVtoRGB32(this, a3, a2, &v74, &v69);
  if ( v12 < 0 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v12 )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1657, v12);
    }
    if ( g_wppLevels )
    {
      v16 = 145;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
      goto LABEL_157;
    }
    goto LABEL_157;
  }
  v12 = MFGetAttribute2UINT32asUINT64(v69, &MF_MT_FRAME_SIZE, &v70, &v72);
  if ( v12 >= 0 )
  {
    v21 = v74;
    GetBufferByIndex = v74->lpVtbl->GetBufferByIndex;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    v12 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))GetBufferByIndex)(v21, 0, &v73);
    if ( v12 < 0 )
    {
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v12 )
          CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1661, v12);
      }
      if ( g_wppLevels )
      {
        v16 = 147;
        goto LABEL_15;
      }
      goto LABEL_157;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *, unsigned int *))(*(_QWORD *)v73 + 24LL))(
            v73,
            &v76,
            &v75,
            &v71);
    if ( v12 < 0 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != v12 )
          CallStackContext::TraceFailure(v30, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1663, v12);
      }
      if ( g_wppLevels )
      {
        v16 = 148;
        goto LABEL_15;
      }
      goto LABEL_157;
    }
    v31 = v72;
    v32 = v70;
    v33 = v71 % v72;
    v34 = 4 * v70;
    v35 = -(int)(v71 / v72);
    if ( (int)(v71 / v72) > 0 )
      v35 = v71 / v72;
    if ( v35 >= (unsigned int)v34 )
    {
      v78 = 40;
      DWORD2(v79) = 2097153;
      LODWORD(v79) = v70;
      v12 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))v69->lpVtbl->GetGUID)(
              v69,
              &MF_MT_SUBTYPE,
              &Buf2);
      if ( v12 >= 0 )
      {
        v43 = 1;
        if ( !memcmp_0(&MFVideoFormat_RGB32, &Buf2, 0x10u) )
          v43 = MFGetAttributeUINT32(v69, &MF_MT_DEFAULT_STRIDE, v32);
        DWORD1(v79) = v31 * (((v43 >> 31) & 2) - 1);
        v12 = SAFE_DIBSIZE(&v78, &v80);
        if ( v12 >= 0 )
        {
          strcpy((char *)v77, "BM");
          BYTE3(v77[0]) = 0;
          WORD2(v77[0]) = 0;
          *(_QWORD *)((char *)v77 + 6) = 0x3A00000000LL;
          v47 = 4 * v32 * v31;
          if ( v47 < 0xFFFFFFC6 )
          {
            *(_DWORD *)((char *)v77 + 2) = v47 + 58;
            v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v12 >= 0 )
            {
              v12 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD *, __int64))ppstm->lpVtbl->Write)(ppstm, v77, 14);
              if ( v12 >= 0 )
              {
                v12 = ((__int64 (__fastcall *)(LPSTREAM, int *, __int64))ppstm->lpVtbl->Write)(ppstm, &v78, 44);
                if ( v12 >= 0 )
                {
                  v12 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
                          ppstm,
                          v76,
                          v47,
                          0);
                  if ( v12 >= 0 )
                  {
                    v12 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(
                            ppstm,
                            0,
                            0,
                            0);
                    if ( v12 >= 0 )
                    {
                      a4->hVal.QuadPart = (LONGLONG)ppstm;
                      a4->vt = 66;
                      ppstm = 0;
                      goto LABEL_156;
                    }
                    v63 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                      CallStackTracing::s_wpInstance = v64;
                      if ( v64
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(
                             v64,
                             2032) )
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
                      if ( *((_DWORD *)v65 + 499) != v12 )
                        CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1731, v12);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_156;
                    v39 = 158;
                  }
                  else
                  {
                    v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                      CallStackTracing::s_wpInstance = v61;
                      if ( v61
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(
                             v61,
                             2032) )
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
                      if ( *((_DWORD *)v62 + 499) != v12 )
                        CallStackContext::TraceFailure(v62, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1730, v12);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_156;
                    v39 = 157;
                  }
                }
                else
                {
                  v57 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                    CallStackTracing::s_wpInstance = v58;
                    if ( v58
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
                    {
                      v57 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v57 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v57 + 8) )
                  {
                    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
                    if ( *((_DWORD *)v59 + 499) != v12 )
                      CallStackContext::TraceFailure(v59, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1726, v12);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_156;
                  v39 = 156;
                }
              }
              else
              {
                v54 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                  CallStackTracing::s_wpInstance = v55;
                  if ( v55
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
                  {
                    v54 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v54 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v54 + 8) )
                {
                  v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
                  if ( *((_DWORD *)v56 + 499) != v12 )
                    CallStackContext::TraceFailure(v56, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1725, v12);
                }
                if ( !g_wppLevels )
                  goto LABEL_156;
                v39 = 155;
              }
            }
            else
            {
              v51 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                CallStackTracing::s_wpInstance = v52;
                if ( v52
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                {
                  v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v51 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v51 + 8) )
              {
                v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                if ( *((_DWORD *)v53 + 499) != v12 )
                  CallStackContext::TraceFailure(v53, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1722, v12);
              }
              if ( !g_wppLevels )
                goto LABEL_156;
              v39 = 154;
            }
          }
          else
          {
            v48 = (wchar_t *)CallStackTracing::s_wpInstance;
            v12 = -2147024362;
            if ( !CallStackTracing::s_wpInstance )
            {
              v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
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
              if ( *((_DWORD *)v50 + 499) != -2147024362 )
                CallStackContext::TraceFailure(v50, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1719, -2147024362);
            }
            if ( !g_wppLevels )
              goto LABEL_156;
            v39 = 153;
          }
        }
        else
        {
          v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v44 + 8) )
          {
            v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v46 + 499) != v12 )
              CallStackContext::TraceFailure(v46, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1705, v12);
          }
          if ( !g_wppLevels )
            goto LABEL_156;
          v39 = 152;
        }
      }
      else
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != v12 )
            CallStackContext::TraceFailure(v42, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1696, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_156;
        v39 = 151;
      }
    }
    else
    {
      if ( (unsigned __int8)byte_1801B110B >= 0x20u )
        WPP_SF_qlPD(*((_QWORD *)WPP_GLOBAL_Control + 17), v33, v34, this, v35, (unsigned int)v34);
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      v12 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v38, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1672, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_156;
      v39 = 150;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
LABEL_156:
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 32LL))(v73, v33);
    goto LABEL_157;
  }
  v18 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v12 )
      CallStackContext::TraceFailure(v20, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1659, v12);
  }
  if ( g_wppLevels )
  {
    v16 = 146;
    goto LABEL_15;
  }
LABEL_157:
  if ( ppstm )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    ppstm = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800dc788  push    rbp
0x1800dc78a  push    rbx
0x1800dc78b  push    rsi
0x1800dc78c  push    rdi
0x1800dc78d  push    r12
0x1800dc78f  push    r13
0x1800dc791  push    r14
0x1800dc793  push    r15
0x1800dc795  lea     rbp, [rsp-1Fh]
0x1800dc79a  sub     rsp, 0F8h
0x1800dc7a1  mov     rax, cs:__security_cookie
0x1800dc7a8  xor     rax, rsp
0x1800dc7ab  mov     [rbp+57h+var_48], rax
0x1800dc7af  xor     r13d, r13d
0x1800dc7b2  xor     eax, eax
0x1800dc7b4  xorps   xmm0, xmm0
0x1800dc7b7  mov     [rbp+57h+var_A8], rax
0x1800dc7bb  mov     r15, r8
0x1800dc7be  mov     [rbp+57h+var_A0], eax
0x1800dc7c1  mov     r14, rdx
0x1800dc7c4  mov     [rbp+57h+var_9C], ax
0x1800dc7c8  mov     rsi, rcx
0x1800dc7cb  mov     [rbp+57h+var_98], r13d
0x1800dc7cf  mov     r8d, 676h; int
0x1800dc7d5  mov     [rbp+57h+var_74], rax
0x1800dc7d9  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dc7e0  mov     [rsp+130h+var_E0], r13
0x1800dc7e5  lea     rcx, [rsp+130h+var_F0]; this
0x1800dc7ea  mov     [rbp+57h+var_C0], r13
0x1800dc7ee  movups  [rbp+57h+var_94], xmm0
0x1800dc7f2  mov     [rbp+57h+var_C8], r13
0x1800dc7f6  mov     r12, r9
0x1800dc7f9  movups  [rbp+57h+var_84], xmm0
0x1800dc7fd  mov     [rsp+130h+ppstm], r13
0x1800dc802  movups  [rbp+57h+Buf2], xmm0
0x1800dc806  mov     [rsp+130h+var_D8], r13d
0x1800dc80b  mov     [rbp+57h+var_D0], r13d
0x1800dc80f  mov     [rbp+57h+var_B0], r13
0x1800dc813  mov     [rbp+57h+var_B8], r13d
0x1800dc817  mov     [rbp+57h+var_D4], r13d
0x1800dc81b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dc820  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800dc827  cmp     [rcx+8], r13b
0x1800dc82b  jz      short loc_1800DC881
0x1800dc82d  cmp     [rsi+190h], r13
0x1800dc834  jz      short loc_1800DC881
0x1800dc836  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc83b  mov     rcx, [rsi+190h]
0x1800dc842  mov     rdi, rax
0x1800dc845  mov     rdx, [rcx]
0x1800dc848  mov     rax, [rdx+128h]
0x1800dc84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc854  mov     rcx, [rsi+190h]
0x1800dc85b  mov     ebx, eax
0x1800dc85d  mov     rdx, [rcx]
0x1800dc860  mov     rax, [rdx+118h]
0x1800dc867  lea     rdx, [rbp+57h+var_58]
0x1800dc86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc870  movups  xmm0, xmmword ptr [rax]
0x1800dc873  mov     [rdi+7E0h], ebx
0x1800dc879  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800dc881  lea     rcx, [rsp+130h+var_E0]
0x1800dc886  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc88b  lea     rcx, [rbp+57h+var_C0]
0x1800dc88f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc894  lea     rax, [rsp+130h+var_E0]
0x1800dc899  mov     r8, r14; struct IMFMediaType *
0x1800dc89c  lea     r9, [rbp+57h+var_C0]; struct IMFSample **
0x1800dc8a0  mov     [rsp+130h+var_110], rax; struct IMFMediaType **
0x1800dc8a5  mov     rdx, r15; struct IMFSample *
0x1800dc8a8  mov     rcx, rsi; this
0x1800dc8ab  call    ?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z; CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)
0x1800dc8b0  mov     ebx, eax
0x1800dc8b2  test    eax, eax
0x1800dc8b4  jns     loc_1800DC96C
0x1800dc8ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc8c1  test    rcx, rcx
0x1800dc8c4  jnz     short loc_1800DC907
0x1800dc8c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc8cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc8d3  mov     rcx, rax
0x1800dc8d6  test    rax, rax
0x1800dc8d9  jz      short loc_1800DC8F9
0x1800dc8db  mov     rax, [rax]
0x1800dc8de  mov     edx, 7F0h
0x1800dc8e3  mov     rax, [rax+8]
0x1800dc8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc8ec  test    eax, eax
0x1800dc8ee  jz      short loc_1800DC8F9
0x1800dc8f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc8f7  jmp     short loc_1800DC907
0x1800dc8f9  lea     rcx, qword_1801B07E0; this
0x1800dc900  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc907  cmp     [rcx+8], r13b
0x1800dc90b  jz      short loc_1800DC932
0x1800dc90d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc912  cmp     [rax+7CCh], ebx
0x1800dc918  jz      short loc_1800DC932
0x1800dc91a  mov     r9d, ebx; int
0x1800dc91d  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dc924  mov     r8d, 679h; int
0x1800dc92a  mov     rcx, rax; this
0x1800dc92d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dc932  mov     edi, 1
0x1800dc937  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800dc93e  jb      loc_1800DD2C1
0x1800dc944  mov     edx, 91h
0x1800dc949  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc950  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800dc957  mov     r9, rsi
0x1800dc95a  mov     dword ptr [rsp+130h+var_110], ebx
0x1800dc95e  mov     rcx, [rcx+10h]
0x1800dc962  call    WPP_SF_qD
0x1800dc967  jmp     loc_1800DD2C1
0x1800dc96c  mov     rcx, [rsp+130h+var_E0]
0x1800dc971  lea     r9, [rbp+57h+var_D0]
0x1800dc975  lea     r8, [rsp+130h+var_D8]
0x1800dc97a  lea     rdx, MF_MT_FRAME_SIZE
0x1800dc981  call    MFGetAttribute2UINT32asUINT64
0x1800dc986  mov     ebx, eax
0x1800dc988  test    eax, eax
0x1800dc98a  jns     loc_1800DCA24
0x1800dc990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc997  test    rcx, rcx
0x1800dc99a  jnz     short loc_1800DC9DD
0x1800dc99c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dc9a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc9a9  mov     rcx, rax
0x1800dc9ac  test    rax, rax
0x1800dc9af  jz      short loc_1800DC9CF
0x1800dc9b1  mov     rax, [rax]
0x1800dc9b4  mov     edx, 7F0h
0x1800dc9b9  mov     rax, [rax+8]
0x1800dc9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc9c2  test    eax, eax
0x1800dc9c4  jz      short loc_1800DC9CF
0x1800dc9c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc9cd  jmp     short loc_1800DC9DD
0x1800dc9cf  lea     rcx, qword_1801B07E0; this
0x1800dc9d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dc9dd  cmp     [rcx+8], r13b
0x1800dc9e1  jz      short loc_1800DCA08
0x1800dc9e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dc9e8  cmp     [rax+7CCh], ebx
0x1800dc9ee  jz      short loc_1800DCA08
0x1800dc9f0  mov     r9d, ebx; int
0x1800dc9f3  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dc9fa  mov     r8d, 67Bh; int
0x1800dca00  mov     rcx, rax; this
0x1800dca03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dca08  mov     edi, 1
0x1800dca0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800dca14  jb      loc_1800DD2C1
0x1800dca1a  mov     edx, 92h
0x1800dca1f  jmp     loc_1800DC949
0x1800dca24  mov     rdi, [rbp+57h+var_C0]
0x1800dca28  lea     rcx, [rbp+57h+var_C8]
0x1800dca2c  mov     rax, [rdi]
0x1800dca2f  mov     rbx, [rax+140h]
0x1800dca36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dca3b  lea     r8, [rbp+57h+var_C8]
0x1800dca3f  xor     edx, edx
0x1800dca41  mov     rcx, rdi
0x1800dca44  mov     rax, rbx
0x1800dca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dca4c  mov     ebx, eax
0x1800dca4e  test    eax, eax
0x1800dca50  jns     loc_1800DCAEA
0x1800dca56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dca5d  test    rcx, rcx
0x1800dca60  jnz     short loc_1800DCAA3
0x1800dca62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dca68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dca6f  mov     rcx, rax
0x1800dca72  test    rax, rax
0x1800dca75  jz      short loc_1800DCA95
0x1800dca77  mov     rax, [rax]
0x1800dca7a  mov     edx, 7F0h
0x1800dca7f  mov     rax, [rax+8]
0x1800dca83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dca88  test    eax, eax
0x1800dca8a  jz      short loc_1800DCA95
0x1800dca8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dca93  jmp     short loc_1800DCAA3
0x1800dca95  lea     rcx, qword_1801B07E0; this
0x1800dca9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcaa3  cmp     [rcx+8], r13b
0x1800dcaa7  jz      short loc_1800DCACE
0x1800dcaa9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcaae  cmp     [rax+7CCh], ebx
0x1800dcab4  jz      short loc_1800DCACE
0x1800dcab6  mov     r9d, ebx; int
0x1800dcab9  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dcac0  mov     r8d, 67Dh; int
0x1800dcac6  mov     rcx, rax; this
0x1800dcac9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcace  mov     edi, 1
0x1800dcad3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800dcada  jb      loc_1800DD2C1
0x1800dcae0  mov     edx, 93h
0x1800dcae5  jmp     loc_1800DC949
0x1800dcaea  mov     rcx, [rbp+57h+var_C8]
0x1800dcaee  lea     r9, [rbp+57h+var_D4]
0x1800dcaf2  lea     r8, [rbp+57h+var_B8]
0x1800dcaf6  lea     rdx, [rbp+57h+var_B0]
0x1800dcafa  mov     rax, [rcx]
0x1800dcafd  mov     rax, [rax+18h]
0x1800dcb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcb06  mov     ebx, eax
0x1800dcb08  test    eax, eax
0x1800dcb0a  jns     loc_1800DCBA4
0x1800dcb10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb17  test    rcx, rcx
0x1800dcb1a  jnz     short loc_1800DCB5D
0x1800dcb1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dcb22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb29  mov     rcx, rax
0x1800dcb2c  test    rax, rax
0x1800dcb2f  jz      short loc_1800DCB4F
0x1800dcb31  mov     rax, [rax]
0x1800dcb34  mov     edx, 7F0h
0x1800dcb39  mov     rax, [rax+8]
0x1800dcb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcb42  test    eax, eax
0x1800dcb44  jz      short loc_1800DCB4F
0x1800dcb46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb4d  jmp     short loc_1800DCB5D
0x1800dcb4f  lea     rcx, qword_1801B07E0; this
0x1800dcb56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb5d  cmp     [rcx+8], r13b
0x1800dcb61  jz      short loc_1800DCB88
0x1800dcb63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcb68  cmp     [rax+7CCh], ebx
0x1800dcb6e  jz      short loc_1800DCB88
0x1800dcb70  mov     r9d, ebx; int
0x1800dcb73  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dcb7a  mov     r8d, 67Fh; int
0x1800dcb80  mov     rcx, rax; this
0x1800dcb83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcb88  mov     edi, 1
0x1800dcb8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800dcb94  jb      loc_1800DD2C1
0x1800dcb9a  mov     edx, 94h
0x1800dcb9f  jmp     loc_1800DC949
0x1800dcba4  mov     eax, [rbp+57h+var_D4]
0x1800dcba7  xor     edx, edx
0x1800dcba9  mov     r14d, [rbp+57h+var_D0]
0x1800dcbad  mov     r15d, [rsp+130h+var_D8]
0x1800dcbb2  div     r14d
0x1800dcbb5  lea     r8d, ds:0[r15*4]
0x1800dcbbd  mov     ecx, eax
0x1800dcbbf  neg     ecx
0x1800dcbc1  cmovs   ecx, eax
0x1800dcbc4  cmp     ecx, r8d
0x1800dcbc7  jnb     loc_1800DCCB3
0x1800dcbcd  mov     eax, 20h ; ' '
0x1800dcbd2  cmp     cs:byte_1801B110B, al
0x1800dcbd8  jb      short loc_1800DCBFC
0x1800dcbda  mov     eax, r8d
0x1800dcbdd  mov     r9, rsi
0x1800dcbe0  mov     [rsp+130h+var_108], rax
0x1800dcbe5  mov     dword ptr [rsp+130h+var_110], ecx
0x1800dcbe9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcbf0  mov     rcx, [rcx+88h]
0x1800dcbf7  call    WPP_SF_qlPD
0x1800dcbfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc03  mov     ebx, 80070057h
0x1800dcc08  test    rcx, rcx
0x1800dcc0b  jnz     short loc_1800DCC4E
0x1800dcc0d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dcc13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc1a  mov     rcx, rax
0x1800dcc1d  test    rax, rax
0x1800dcc20  jz      short loc_1800DCC40
0x1800dcc22  mov     rax, [rax]
0x1800dcc25  mov     edx, 7F0h
0x1800dcc2a  mov     rax, [rax+8]
0x1800dcc2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcc33  test    eax, eax
0x1800dcc35  jz      short loc_1800DCC40
0x1800dcc37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc3e  jmp     short loc_1800DCC4E
0x1800dcc40  lea     rcx, qword_1801B07E0; this
0x1800dcc47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc4e  cmp     [rcx+8], r13b
0x1800dcc52  jz      short loc_1800DCC79
0x1800dcc54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcc59  cmp     [rax+7CCh], ebx
0x1800dcc5f  jz      short loc_1800DCC79
0x1800dcc61  mov     r9d, ebx; int
0x1800dcc64  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800dcc6b  mov     r8d, 688h; int
0x1800dcc71  mov     rcx, rax; this
0x1800dcc74  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcc79  mov     edi, 1
0x1800dcc7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800dcc85  jb      loc_1800DD2B1
0x1800dcc8b  mov     edx, 96h
0x1800dcc90  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcc97  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
  ... truncated ...
```
