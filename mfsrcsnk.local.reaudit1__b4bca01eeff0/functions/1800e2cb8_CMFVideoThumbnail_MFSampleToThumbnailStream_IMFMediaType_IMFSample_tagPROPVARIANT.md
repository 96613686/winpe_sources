# CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)

- ea: `0x1800e2cb8`
- end: `0x1800e38a9`
- name: `?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z`
- size: `3057`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaType *, struct IMFSample *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18016339c`
- `0x1801637dc`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18005a094`
- `0x1800790a8`
- `0x180079680`
- `0x180079a9c`
- `0x1800d01ec`
- `0x1800e2cb8`
- `0x180110ed0`
- `0x18016475c`
- `0x180164a18`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2ed2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2f9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e305e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3155`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e324a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3337`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e33fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e34b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e356c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3627`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e36e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e379a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2ed2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2f9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e305e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3155`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e324a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3337`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e33fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e34b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e356c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3627`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e36e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e379a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e348f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e348f`

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
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v24 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v28 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v63 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v60 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v57 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v54 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v51 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v48 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v44 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v40 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
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
          v36 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v18 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800e2cb8  push    rbp
0x1800e2cba  push    rbx
0x1800e2cbb  push    rsi
0x1800e2cbc  push    rdi
0x1800e2cbd  push    r12
0x1800e2cbf  push    r13
0x1800e2cc1  push    r14
0x1800e2cc3  push    r15
0x1800e2cc5  lea     rbp, [rsp-1Fh]
0x1800e2cca  sub     rsp, 0F8h
0x1800e2cd1  mov     rax, cs:__security_cookie
0x1800e2cd8  xor     rax, rsp
0x1800e2cdb  mov     [rbp+57h+var_48], rax
0x1800e2cdf  xor     r13d, r13d
0x1800e2ce2  xor     eax, eax
0x1800e2ce4  xorps   xmm0, xmm0
0x1800e2ce7  mov     [rbp+57h+var_A8], rax
0x1800e2ceb  mov     r15, r8
0x1800e2cee  mov     [rbp+57h+var_A0], eax
0x1800e2cf1  mov     r14, rdx
0x1800e2cf4  mov     [rbp+57h+var_9C], ax
0x1800e2cf8  mov     rsi, rcx
0x1800e2cfb  mov     [rbp+57h+var_98], r13d
0x1800e2cff  mov     r8d, 676h; int
0x1800e2d05  mov     [rbp+57h+var_74], rax
0x1800e2d09  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e2d10  mov     [rsp+130h+var_E0], r13
0x1800e2d15  lea     rcx, [rsp+130h+var_F0]; this
0x1800e2d1a  mov     [rbp+57h+var_C0], r13
0x1800e2d1e  movups  [rbp+57h+var_94], xmm0
0x1800e2d22  mov     [rbp+57h+var_C8], r13
0x1800e2d26  mov     r12, r9
0x1800e2d29  movups  [rbp+57h+var_84], xmm0
0x1800e2d2d  mov     [rsp+130h+ppstm], r13
0x1800e2d32  movups  [rbp+57h+Buf2], xmm0
0x1800e2d36  mov     [rsp+130h+var_D8], r13d
0x1800e2d3b  mov     [rbp+57h+var_D0], r13d
0x1800e2d3f  mov     [rbp+57h+var_B0], r13
0x1800e2d43  mov     [rbp+57h+var_B8], r13d
0x1800e2d47  mov     [rbp+57h+var_D4], r13d
0x1800e2d4b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e2d50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e2d57  cmp     [rcx+8], r13b
0x1800e2d5b  jz      short loc_1800E2DB1
0x1800e2d5d  cmp     [rsi+190h], r13
0x1800e2d64  jz      short loc_1800E2DB1
0x1800e2d66  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2d6b  mov     rcx, [rsi+190h]
0x1800e2d72  mov     rdi, rax
0x1800e2d75  mov     rdx, [rcx]
0x1800e2d78  mov     rax, [rdx+128h]
0x1800e2d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2d84  mov     rcx, [rsi+190h]
0x1800e2d8b  mov     ebx, eax
0x1800e2d8d  mov     rdx, [rcx]
0x1800e2d90  mov     rax, [rdx+118h]
0x1800e2d97  lea     rdx, [rbp+57h+var_58]
0x1800e2d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2da0  movups  xmm0, xmmword ptr [rax]
0x1800e2da3  mov     [rdi+7E0h], ebx
0x1800e2da9  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800e2db1  lea     rcx, [rsp+130h+var_E0]
0x1800e2db6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e2dbb  lea     rcx, [rbp+57h+var_C0]
0x1800e2dbf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e2dc4  lea     rax, [rsp+130h+var_E0]
0x1800e2dc9  mov     r8, r14; struct IMFMediaType *
0x1800e2dcc  lea     r9, [rbp+57h+var_C0]; struct IMFSample **
0x1800e2dd0  mov     [rsp+130h+var_110], rax; struct IMFMediaType **
0x1800e2dd5  mov     rdx, r15; struct IMFSample *
0x1800e2dd8  mov     rcx, rsi; this
0x1800e2ddb  call    ?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z; CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)
0x1800e2de0  mov     ebx, eax
0x1800e2de2  test    eax, eax
0x1800e2de4  jns     loc_1800E2EA2
0x1800e2dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2df1  test    rcx, rcx
0x1800e2df4  jnz     short loc_1800E2E3D
0x1800e2df6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2dfd  nop     dword ptr [rax+rax+00h]
0x1800e2e02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2e09  mov     rcx, rax
0x1800e2e0c  test    rax, rax
0x1800e2e0f  jz      short loc_1800E2E2F
0x1800e2e11  mov     rax, [rax]
0x1800e2e14  mov     edx, 7F0h
0x1800e2e19  mov     rax, [rax+8]
0x1800e2e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e22  test    eax, eax
0x1800e2e24  jz      short loc_1800E2E2F
0x1800e2e26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2e2d  jmp     short loc_1800E2E3D
0x1800e2e2f  lea     rcx, qword_1801B97E0; this
0x1800e2e36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2e3d  cmp     [rcx+8], r13b
0x1800e2e41  jz      short loc_1800E2E68
0x1800e2e43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2e48  cmp     [rax+7CCh], ebx
0x1800e2e4e  jz      short loc_1800E2E68
0x1800e2e50  mov     r9d, ebx; int
0x1800e2e53  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e2e5a  mov     r8d, 679h; int
0x1800e2e60  mov     rcx, rax; this
0x1800e2e63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2e68  mov     edi, 1
0x1800e2e6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800e2e74  jb      loc_1800E3845
0x1800e2e7a  mov     edx, 91h
0x1800e2e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2e86  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800e2e8d  mov     r9, rsi
0x1800e2e90  mov     dword ptr [rsp+130h+var_110], ebx
0x1800e2e94  mov     rcx, [rcx+10h]
0x1800e2e98  call    WPP_SF_qD
0x1800e2e9d  jmp     loc_1800E3845
0x1800e2ea2  mov     rcx, [rsp+130h+var_E0]
0x1800e2ea7  lea     r9, [rbp+57h+var_D0]
0x1800e2eab  lea     r8, [rsp+130h+var_D8]
0x1800e2eb0  lea     rdx, MF_MT_FRAME_SIZE
0x1800e2eb7  call    MFGetAttribute2UINT32asUINT64
0x1800e2ebc  mov     ebx, eax
0x1800e2ebe  test    eax, eax
0x1800e2ec0  jns     loc_1800E2F60
0x1800e2ec6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2ecd  test    rcx, rcx
0x1800e2ed0  jnz     short loc_1800E2F19
0x1800e2ed2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2ed9  nop     dword ptr [rax+rax+00h]
0x1800e2ede  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2ee5  mov     rcx, rax
0x1800e2ee8  test    rax, rax
0x1800e2eeb  jz      short loc_1800E2F0B
0x1800e2eed  mov     rax, [rax]
0x1800e2ef0  mov     edx, 7F0h
0x1800e2ef5  mov     rax, [rax+8]
0x1800e2ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2efe  test    eax, eax
0x1800e2f00  jz      short loc_1800E2F0B
0x1800e2f02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2f09  jmp     short loc_1800E2F19
0x1800e2f0b  lea     rcx, qword_1801B97E0; this
0x1800e2f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2f19  cmp     [rcx+8], r13b
0x1800e2f1d  jz      short loc_1800E2F44
0x1800e2f1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2f24  cmp     [rax+7CCh], ebx
0x1800e2f2a  jz      short loc_1800E2F44
0x1800e2f2c  mov     r9d, ebx; int
0x1800e2f2f  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e2f36  mov     r8d, 67Bh; int
0x1800e2f3c  mov     rcx, rax; this
0x1800e2f3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2f44  mov     edi, 1
0x1800e2f49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800e2f50  jb      loc_1800E3845
0x1800e2f56  mov     edx, 92h
0x1800e2f5b  jmp     loc_1800E2E7F
0x1800e2f60  mov     rdi, [rbp+57h+var_C0]
0x1800e2f64  lea     rcx, [rbp+57h+var_C8]
0x1800e2f68  mov     rax, [rdi]
0x1800e2f6b  mov     rbx, [rax+140h]
0x1800e2f72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e2f77  lea     r8, [rbp+57h+var_C8]
0x1800e2f7b  xor     edx, edx
0x1800e2f7d  mov     rcx, rdi
0x1800e2f80  mov     rax, rbx
0x1800e2f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f88  mov     ebx, eax
0x1800e2f8a  test    eax, eax
0x1800e2f8c  jns     loc_1800E302C
0x1800e2f92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2f99  test    rcx, rcx
0x1800e2f9c  jnz     short loc_1800E2FE5
0x1800e2f9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2fa5  nop     dword ptr [rax+rax+00h]
0x1800e2faa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2fb1  mov     rcx, rax
0x1800e2fb4  test    rax, rax
0x1800e2fb7  jz      short loc_1800E2FD7
0x1800e2fb9  mov     rax, [rax]
0x1800e2fbc  mov     edx, 7F0h
0x1800e2fc1  mov     rax, [rax+8]
0x1800e2fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fca  test    eax, eax
0x1800e2fcc  jz      short loc_1800E2FD7
0x1800e2fce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2fd5  jmp     short loc_1800E2FE5
0x1800e2fd7  lea     rcx, qword_1801B97E0; this
0x1800e2fde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2fe5  cmp     [rcx+8], r13b
0x1800e2fe9  jz      short loc_1800E3010
0x1800e2feb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2ff0  cmp     [rax+7CCh], ebx
0x1800e2ff6  jz      short loc_1800E3010
0x1800e2ff8  mov     r9d, ebx; int
0x1800e2ffb  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e3002  mov     r8d, 67Dh; int
0x1800e3008  mov     rcx, rax; this
0x1800e300b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e3010  mov     edi, 1
0x1800e3015  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800e301c  jb      loc_1800E3845
0x1800e3022  mov     edx, 93h
0x1800e3027  jmp     loc_1800E2E7F
0x1800e302c  mov     rcx, [rbp+57h+var_C8]
0x1800e3030  lea     r9, [rbp+57h+var_D4]
0x1800e3034  lea     r8, [rbp+57h+var_B8]
0x1800e3038  lea     rdx, [rbp+57h+var_B0]
0x1800e303c  mov     rax, [rcx]
0x1800e303f  mov     rax, [rax+18h]
0x1800e3043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3048  mov     ebx, eax
0x1800e304a  test    eax, eax
0x1800e304c  jns     loc_1800E30EC
0x1800e3052  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3059  test    rcx, rcx
0x1800e305c  jnz     short loc_1800E30A5
0x1800e305e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e3065  nop     dword ptr [rax+rax+00h]
0x1800e306a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3071  mov     rcx, rax
0x1800e3074  test    rax, rax
0x1800e3077  jz      short loc_1800E3097
0x1800e3079  mov     rax, [rax]
0x1800e307c  mov     edx, 7F0h
0x1800e3081  mov     rax, [rax+8]
0x1800e3085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e308a  test    eax, eax
0x1800e308c  jz      short loc_1800E3097
0x1800e308e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3095  jmp     short loc_1800E30A5
0x1800e3097  lea     rcx, qword_1801B97E0; this
0x1800e309e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e30a5  cmp     [rcx+8], r13b
0x1800e30a9  jz      short loc_1800E30D0
0x1800e30ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e30b0  cmp     [rax+7CCh], ebx
0x1800e30b6  jz      short loc_1800E30D0
0x1800e30b8  mov     r9d, ebx; int
0x1800e30bb  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e30c2  mov     r8d, 67Fh; int
0x1800e30c8  mov     rcx, rax; this
0x1800e30cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e30d0  mov     edi, 1
0x1800e30d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800e30dc  jb      loc_1800E3845
0x1800e30e2  mov     edx, 94h
0x1800e30e7  jmp     loc_1800E2E7F
0x1800e30ec  mov     eax, [rbp+57h+var_D4]
0x1800e30ef  xor     edx, edx
0x1800e30f1  mov     r14d, [rbp+57h+var_D0]
0x1800e30f5  mov     r15d, [rsp+130h+var_D8]
0x1800e30fa  div     r14d
0x1800e30fd  lea     r8d, ds:0[r15*4]
0x1800e3105  mov     ecx, eax
0x1800e3107  neg     ecx
0x1800e3109  cmovs   ecx, eax
0x1800e310c  cmp     ecx, r8d
0x1800e310f  jnb     loc_1800E3201
0x1800e3115  mov     eax, 20h ; ' '
0x1800e311a  cmp     cs:byte_1801BA10B, al
0x1800e3120  jb      short loc_1800E3144
0x1800e3122  mov     eax, r8d
0x1800e3125  mov     r9, rsi
0x1800e3128  mov     [rsp+130h+var_108], rax
0x1800e312d  mov     dword ptr [rsp+130h+var_110], ecx
0x1800e3131  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3138  mov     rcx, [rcx+88h]
0x1800e313f  call    WPP_SF_qlPD
0x1800e3144  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e314b  mov     ebx, 80070057h
0x1800e3150  test    rcx, rcx
0x1800e3153  jnz     short loc_1800E319C
0x1800e3155  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e315c  nop     dword ptr [rax+rax+00h]
0x1800e3161  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e3168  mov     rcx, rax
0x1800e316b  test    rax, rax
0x1800e316e  jz      short loc_1800E318E
0x1800e3170  mov     rax, [rax]
0x1800e3173  mov     edx, 7F0h
0x1800e3178  mov     rax, [rax+8]
0x1800e317c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3181  test    eax, eax
0x1800e3183  jz      short loc_1800E318E
0x1800e3185  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e318c  jmp     short loc_1800E319C
0x1800e318e  lea     rcx, qword_1801B97E0; this
0x1800e3195  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e319c  cmp     [rcx+8], r13b
0x1800e31a0  jz      short loc_1800E31C7
0x1800e31a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e31a7  cmp     [rax+7CCh], ebx
0x1800e31ad  jz      short loc_1800E31C7
0x1800e31af  mov     r9d, ebx; int
0x1800e31b2  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x1800e31b9  mov     r8d, 688h; int
0x1800e31bf  mov     rcx, rax; this
0x1800e31c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e31c7  mov     edi, 1
  ... truncated ...
```
