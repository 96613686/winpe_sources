# CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)

- ea: `0x18006c8f0`
- end: `0x18006d542`
- name: `?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z`
- size: `3154`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaType *, struct IMFSample *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18006a8cc`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180053ff8`
- `0x18005fed8`
- `0x180067b40`
- `0x18006c8f0`
- `0x18006f08c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006d069`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006d069`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ca2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cb0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cbd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cc96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cd8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ce64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cfd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d2bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ca2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cb0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cbd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cc96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cd8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ce64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cfd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d2bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d430`

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
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  struct IMFSample *v25; // rdi
  HRESULT (__stdcall *GetBufferByIndex)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  unsigned int v39; // r14d
  unsigned int v40; // r15d
  unsigned __int64 v41; // rdx
  __int64 v42; // r8
  unsigned int v43; // ecx
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  int v53; // ebx
  __int64 v54; // r8
  __int64 v55; // r9
  int v56; // ebx
  unsigned __int64 v57; // rcx
  unsigned int v58; // eax
  bool v59; // zf
  unsigned int v60; // ecx
  __int64 v61; // rdx
  unsigned int v62; // r14d
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 *v88; // rcx
  CallStackTracing *v89; // rax
  struct CallStackContext *v90; // rax
  __int64 *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  _BYTE v95[8]; // [rsp+40h] [rbp-99h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-91h] BYREF
  struct IMFMediaType *v97; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v98; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v99; // [rsp+5Ch] [rbp-7Dh] BYREF
  unsigned int v100; // [rsp+60h] [rbp-79h] BYREF
  __int64 v101; // [rsp+68h] [rbp-71h] BYREF
  struct IMFSample *v102; // [rsp+70h] [rbp-69h] BYREF
  int v103; // [rsp+78h] [rbp-61h] BYREF
  __int64 v104; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v105[2]; // [rsp+88h] [rbp-51h] BYREF
  int v106; // [rsp+98h] [rbp-41h] BYREF
  __int128 v107; // [rsp+9Ch] [rbp-3Dh]
  __int128 v108; // [rsp+ACh] [rbp-2Dh]
  __int64 v109; // [rsp+BCh] [rbp-1Dh]
  __int128 Buf2; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v111[16]; // [rsp+D8h] [rbp-1h] BYREF

  memset(v105, 0, 14);
  v106 = 0;
  v109 = 0;
  v97 = 0;
  v102 = 0;
  v107 = 0;
  v101 = 0;
  v108 = 0;
  ppstm = 0;
  Buf2 = 0;
  v98 = 0;
  v100 = 0;
  v104 = 0;
  v103 = 0;
  v99 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v95,
    "CMFVideoThumbnail::MFSampleToThumbnailStream",
    1654);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v111);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  v12 = CMFVideoThumbnail::ConvertYUVtoRGB32(this, a3, a2, &v102, &v97);
  if ( v12 < 0 )
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v12 )
        CallStackContext::TraceFailure(v17, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1657, v12);
    }
    if ( g_wppLevels )
    {
      v18 = 145;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
      goto LABEL_169;
    }
    goto LABEL_169;
  }
  v12 = MFGetAttribute2UINT32asUINT64(v97, &MF_MT_FRAME_SIZE, &v98, &v100);
  if ( v12 >= 0 )
  {
    v25 = v102;
    GetBufferByIndex = v102->lpVtbl->GetBufferByIndex;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v101);
    v12 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))GetBufferByIndex)(v25, 0, &v101);
    if ( v12 < 0 )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v12 )
          CallStackContext::TraceFailure(v32, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1661, v12);
      }
      if ( g_wppLevels )
      {
        v18 = 147;
        goto LABEL_15;
      }
      goto LABEL_169;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *, unsigned int *))(*(_QWORD *)v101 + 24LL))(
            v101,
            &v104,
            &v103,
            &v99);
    if ( v12 < 0 )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v12 )
          CallStackContext::TraceFailure(v38, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1663, v12);
      }
      if ( g_wppLevels )
      {
        v18 = 148;
        goto LABEL_15;
      }
      goto LABEL_169;
    }
    v39 = v100;
    v40 = v98;
    v41 = v99 % v100;
    v42 = 4 * v98;
    v43 = -(int)(v99 / v100);
    if ( (int)(v99 / v100) > 0 )
      v43 = v99 / v100;
    if ( v43 < (unsigned int)v42 )
    {
      if ( (unsigned __int8)byte_1800DC8D3 >= 0x20u )
        WPP_SF_qlPD(*((_QWORD *)WPP_GLOBAL_Control + 17), v41, v42, this, v43, (unsigned int)v42);
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      v12 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v35);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v46, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1672, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_168;
      v47 = 150;
      goto LABEL_167;
    }
    v106 = 40;
    DWORD2(v107) = 2097153;
    LODWORD(v107) = v98;
    v12 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))v97->lpVtbl->GetGUID)(
            v97,
            &MF_MT_SUBTYPE,
            &Buf2);
    if ( v12 < 0 )
    {
      v50 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v48, v49);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v12 )
          CallStackContext::TraceFailure(v52, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1696, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_168;
      v47 = 151;
      goto LABEL_167;
    }
    v53 = 1;
    if ( !memcmp_0(&MFVideoFormat_RGB32, &Buf2, 0x10u) )
      v53 = MFGetAttributeUINT32(v97, &MF_MT_DEFAULT_STRIDE, v40);
    v56 = v39 * (((v53 >> 31) & 2) - 1);
    DWORD1(v107) = v56;
    if ( v56 == 0x80000000 || (int)v107 < 0 || (v41 = WORD5(v107), !WORD5(v107)) )
    {
      v12 = -2147024809;
    }
    else
    {
      v54 = 0xFFFFFFFFLL;
      v57 = WORD5(v107) * (unsigned __int64)(unsigned int)v107;
      if ( v57 <= 0xFFFFFFFF )
      {
        v58 = (unsigned int)v57 >> 3;
        v59 = (v57 & 7) == 0;
        v60 = ((unsigned int)v57 >> 3) + 1;
        if ( v59 )
          v60 = v58;
        if ( (v60 & 3) != 0 )
          v60 = v60 - (v60 & 3) + 4;
        v61 = (unsigned int)-v56;
        if ( v56 > 0 )
          v61 = (unsigned int)v56;
        v41 = v60 * v61;
        if ( v41 <= 0xFFFFFFFF )
        {
          strcpy((char *)v105, "BM");
          LODWORD(v108) = v41;
          BYTE3(v105[0]) = 0;
          WORD2(v105[0]) = 0;
          *(_QWORD *)((char *)v105 + 6) = 0x3A00000000LL;
          v62 = 4 * v40 * v39;
          if ( v62 < 0xFFFFFFC6 )
          {
            *(_DWORD *)((char *)v105 + 2) = v62 + 58;
            v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v12 >= 0 )
            {
              v12 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD *, __int64))ppstm->lpVtbl->Write)(ppstm, v105, 14);
              if ( v12 >= 0 )
              {
                v12 = ((__int64 (__fastcall *)(LPSTREAM, int *, __int64))ppstm->lpVtbl->Write)(ppstm, &v106, 44);
                if ( v12 >= 0 )
                {
                  v12 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
                          ppstm,
                          v104,
                          v62,
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
LABEL_168:
                      (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v101 + 32LL))(v101, v41);
                      goto LABEL_169;
                    }
                    v88 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v89 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v86, v87);
                      CallStackTracing::s_wpInstance = v89;
                      if ( v89
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v89 + 8LL))(
                             v89,
                             2032) )
                      {
                        v88 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v88 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v88 + 8) )
                    {
                      v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v88);
                      if ( *((_DWORD *)v90 + 499) != v12 )
                        CallStackContext::TraceFailure(v90, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1731, v12);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_168;
                    v47 = 158;
                  }
                  else
                  {
                    v83 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v81, v82);
                      CallStackTracing::s_wpInstance = v84;
                      if ( v84
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(
                             v84,
                             2032) )
                      {
                        v83 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v83 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v83 + 8) )
                    {
                      v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
                      if ( *((_DWORD *)v85 + 499) != v12 )
                        CallStackContext::TraceFailure(v85, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1730, v12);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_168;
                    v47 = 157;
                  }
                }
                else
                {
                  v78 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v76, v77);
                    CallStackTracing::s_wpInstance = v79;
                    if ( v79
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
                    {
                      v78 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v78 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                    }
                  }
                  if ( *((_BYTE *)v78 + 8) )
                  {
                    v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
                    if ( *((_DWORD *)v80 + 499) != v12 )
                      CallStackContext::TraceFailure(v80, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1726, v12);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_168;
                  v47 = 156;
                }
              }
              else
              {
                v73 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v71, v72);
                  CallStackTracing::s_wpInstance = v74;
                  if ( v74
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
                  {
                    v73 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v73 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( *((_BYTE *)v73 + 8) )
                {
                  v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                  if ( *((_DWORD *)v75 + 499) != v12 )
                    CallStackContext::TraceFailure(v75, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1725, v12);
                }
                if ( !g_wppLevels )
                  goto LABEL_168;
                v47 = 155;
              }
            }
            else
            {
              v68 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v66, v67);
                CallStackTracing::s_wpInstance = v69;
                if ( v69
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
                {
                  v68 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v68 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v68 + 8) )
              {
                v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                if ( *((_DWORD *)v70 + 499) != v12 )
                  CallStackContext::TraceFailure(v70, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1722, v12);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v47 = 154;
            }
          }
          else
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
            v12 = -2147024362;
            if ( !CallStackTracing::s_wpInstance )
            {
              v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, 0xFFFFFFFFLL, v55);
              CallStackTracing::s_wpInstance = v64;
              if ( v64
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
              {
                v63 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v63 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v63 + 8) )
            {
              v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
              if ( *((_DWORD *)v65 + 499) != -2147024362 )
                CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1719, -2147024362);
            }
            if ( !g_wppLevels )
              goto LABEL_168;
            v47 = 153;
          }
LABEL_167:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v47,
            &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
            this,
            v12);
          goto LABEL_168;
        }
      }
      v12 = -2147024362;
    }
    v91 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v54, v55);
      CallStackTracing::s_wpInstance = v92;
      if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
      {
        v91 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v91 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v91 + 8) )
    {
      v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
      if ( *((_DWORD *)v93 + 499) != v12 )
        CallStackContext::TraceFailure(v93, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1705, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_168;
    v47 = 152;
    goto LABEL_167;
  }
  v22 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
    if ( *((_DWORD *)v24 + 499) != v12 )
      CallStackContext::TraceFailure(v24, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1659, v12);
  }
  if ( g_wppLevels )
  {
    v18 = 146;
    goto LABEL_15;
  }
LABEL_169:
  if ( ppstm )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    ppstm = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v95);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v101);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006c8f0  push    rbp
0x18006c8f2  push    rbx
0x18006c8f3  push    rsi
0x18006c8f4  push    rdi
0x18006c8f5  push    r12
0x18006c8f7  push    r13
0x18006c8f9  push    r14
0x18006c8fb  push    r15
0x18006c8fd  lea     rbp, [rsp-1Fh]
0x18006c902  sub     rsp, 0F8h
0x18006c909  mov     rax, cs:__security_cookie
0x18006c910  xor     rax, rsp
0x18006c913  mov     [rbp+57h+var_48], rax
0x18006c917  xor     r13d, r13d
0x18006c91a  xor     eax, eax
0x18006c91c  xorps   xmm0, xmm0
0x18006c91f  mov     [rbp+57h+var_A8], rax
0x18006c923  mov     r15, r8
0x18006c926  mov     [rbp+57h+var_A0], eax
0x18006c929  mov     r14, rdx
0x18006c92c  mov     [rbp+57h+var_9C], ax
0x18006c930  mov     rsi, rcx
0x18006c933  mov     [rbp+57h+var_98], r13d
0x18006c937  mov     r8d, 676h; int
0x18006c93d  mov     [rbp+57h+var_74], rax
0x18006c941  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006c948  mov     [rsp+130h+var_E0], r13
0x18006c94d  lea     rcx, [rsp+130h+var_F0]; this
0x18006c952  mov     [rbp+57h+var_C0], r13
0x18006c956  movups  [rbp+57h+var_94], xmm0
0x18006c95a  mov     [rbp+57h+var_C8], r13
0x18006c95e  mov     r12, r9
0x18006c961  movups  [rbp+57h+var_84], xmm0
0x18006c965  mov     [rsp+130h+ppstm], r13
0x18006c96a  movups  [rbp+57h+Buf2], xmm0
0x18006c96e  mov     [rsp+130h+var_D8], r13d
0x18006c973  mov     [rbp+57h+var_D0], r13d
0x18006c977  mov     [rbp+57h+var_B0], r13
0x18006c97b  mov     [rbp+57h+var_B8], r13d
0x18006c97f  mov     [rbp+57h+var_D4], r13d
0x18006c983  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006c988  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006c98f  cmp     [rcx+8], r13b
0x18006c993  jz      short loc_18006C9E9
0x18006c995  cmp     [rsi+190h], r13
0x18006c99c  jz      short loc_18006C9E9
0x18006c99e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c9a3  mov     rcx, [rsi+190h]
0x18006c9aa  mov     rdi, rax
0x18006c9ad  mov     rdx, [rcx]
0x18006c9b0  mov     rax, [rdx+128h]
0x18006c9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9bc  mov     rcx, [rsi+190h]
0x18006c9c3  mov     ebx, eax
0x18006c9c5  mov     rdx, [rcx]
0x18006c9c8  mov     rax, [rdx+118h]
0x18006c9cf  lea     rdx, [rbp+57h+var_58]
0x18006c9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9d8  movups  xmm0, xmmword ptr [rax]
0x18006c9db  mov     [rdi+7E0h], ebx
0x18006c9e1  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006c9e9  lea     rcx, [rsp+130h+var_E0]
0x18006c9ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9f3  lea     rcx, [rbp+57h+var_C0]
0x18006c9f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9fc  lea     rax, [rsp+130h+var_E0]
0x18006ca01  mov     r8, r14; struct IMFMediaType *
0x18006ca04  lea     r9, [rbp+57h+var_C0]; struct IMFSample **
0x18006ca08  mov     [rsp+130h+var_110], rax; struct IMFMediaType **
0x18006ca0d  mov     rdx, r15; struct IMFSample *
0x18006ca10  mov     rcx, rsi; this
0x18006ca13  call    ?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z; CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)
0x18006ca18  mov     ebx, eax
0x18006ca1a  test    eax, eax
0x18006ca1c  jns     loc_18006CADA
0x18006ca22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca29  test    rcx, rcx
0x18006ca2c  jnz     short loc_18006CA75
0x18006ca2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ca35  nop     dword ptr [rax+rax+00h]
0x18006ca3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca41  mov     rcx, rax
0x18006ca44  test    rax, rax
0x18006ca47  jz      short loc_18006CA67
0x18006ca49  mov     rax, [rax]
0x18006ca4c  mov     edx, 7F0h
0x18006ca51  mov     rax, [rax+8]
0x18006ca55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca5a  test    eax, eax
0x18006ca5c  jz      short loc_18006CA67
0x18006ca5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca65  jmp     short loc_18006CA75
0x18006ca67  lea     rcx, qword_1800DBF70; this
0x18006ca6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ca75  cmp     [rcx+8], r13b
0x18006ca79  jz      short loc_18006CAA0
0x18006ca7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ca80  cmp     [rax+7CCh], ebx
0x18006ca86  jz      short loc_18006CAA0
0x18006ca88  mov     r9d, ebx; int
0x18006ca8b  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006ca92  mov     r8d, 679h; int
0x18006ca98  mov     rcx, rax; this
0x18006ca9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006caa0  mov     edi, 1
0x18006caa5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006caac  jb      loc_18006D4DE
0x18006cab2  mov     edx, 91h
0x18006cab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cabe  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006cac5  mov     r9, rsi
0x18006cac8  mov     dword ptr [rsp+130h+var_110], ebx
0x18006cacc  mov     rcx, [rcx+10h]
0x18006cad0  call    WPP_SF_qD
0x18006cad5  jmp     loc_18006D4DE
0x18006cada  mov     rcx, [rsp+130h+var_E0]
0x18006cadf  lea     r9, [rbp+57h+var_D0]
0x18006cae3  lea     r8, [rsp+130h+var_D8]
0x18006cae8  lea     rdx, MF_MT_FRAME_SIZE
0x18006caef  call    MFGetAttribute2UINT32asUINT64
0x18006caf4  mov     ebx, eax
0x18006caf6  test    eax, eax
0x18006caf8  jns     loc_18006CB98
0x18006cafe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb05  test    rcx, rcx
0x18006cb08  jnz     short loc_18006CB51
0x18006cb0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006cb11  nop     dword ptr [rax+rax+00h]
0x18006cb16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb1d  mov     rcx, rax
0x18006cb20  test    rax, rax
0x18006cb23  jz      short loc_18006CB43
0x18006cb25  mov     rax, [rax]
0x18006cb28  mov     edx, 7F0h
0x18006cb2d  mov     rax, [rax+8]
0x18006cb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb36  test    eax, eax
0x18006cb38  jz      short loc_18006CB43
0x18006cb3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb41  jmp     short loc_18006CB51
0x18006cb43  lea     rcx, qword_1800DBF70; this
0x18006cb4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cb51  cmp     [rcx+8], r13b
0x18006cb55  jz      short loc_18006CB7C
0x18006cb57  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006cb5c  cmp     [rax+7CCh], ebx
0x18006cb62  jz      short loc_18006CB7C
0x18006cb64  mov     r9d, ebx; int
0x18006cb67  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006cb6e  mov     r8d, 67Bh; int
0x18006cb74  mov     rcx, rax; this
0x18006cb77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cb7c  mov     edi, 1
0x18006cb81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006cb88  jb      loc_18006D4DE
0x18006cb8e  mov     edx, 92h
0x18006cb93  jmp     loc_18006CAB7
0x18006cb98  mov     rdi, [rbp+57h+var_C0]
0x18006cb9c  lea     rcx, [rbp+57h+var_C8]
0x18006cba0  mov     rax, [rdi]
0x18006cba3  mov     rbx, [rax+140h]
0x18006cbaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cbaf  lea     r8, [rbp+57h+var_C8]
0x18006cbb3  xor     edx, edx
0x18006cbb5  mov     rcx, rdi
0x18006cbb8  mov     rax, rbx
0x18006cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbc0  mov     ebx, eax
0x18006cbc2  test    eax, eax
0x18006cbc4  jns     loc_18006CC64
0x18006cbca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cbd1  test    rcx, rcx
0x18006cbd4  jnz     short loc_18006CC1D
0x18006cbd6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006cbdd  nop     dword ptr [rax+rax+00h]
0x18006cbe2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cbe9  mov     rcx, rax
0x18006cbec  test    rax, rax
0x18006cbef  jz      short loc_18006CC0F
0x18006cbf1  mov     rax, [rax]
0x18006cbf4  mov     edx, 7F0h
0x18006cbf9  mov     rax, [rax+8]
0x18006cbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc02  test    eax, eax
0x18006cc04  jz      short loc_18006CC0F
0x18006cc06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cc0d  jmp     short loc_18006CC1D
0x18006cc0f  lea     rcx, qword_1800DBF70; this
0x18006cc16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cc1d  cmp     [rcx+8], r13b
0x18006cc21  jz      short loc_18006CC48
0x18006cc23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006cc28  cmp     [rax+7CCh], ebx
0x18006cc2e  jz      short loc_18006CC48
0x18006cc30  mov     r9d, ebx; int
0x18006cc33  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006cc3a  mov     r8d, 67Dh; int
0x18006cc40  mov     rcx, rax; this
0x18006cc43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cc48  mov     edi, 1
0x18006cc4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006cc54  jb      loc_18006D4DE
0x18006cc5a  mov     edx, 93h
0x18006cc5f  jmp     loc_18006CAB7
0x18006cc64  mov     rcx, [rbp+57h+var_C8]
0x18006cc68  lea     r9, [rbp+57h+var_D4]
0x18006cc6c  lea     r8, [rbp+57h+var_B8]
0x18006cc70  lea     rdx, [rbp+57h+var_B0]
0x18006cc74  mov     rax, [rcx]
0x18006cc77  mov     rax, [rax+18h]
0x18006cc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc80  mov     ebx, eax
0x18006cc82  test    eax, eax
0x18006cc84  jns     loc_18006CD24
0x18006cc8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cc91  test    rcx, rcx
0x18006cc94  jnz     short loc_18006CCDD
0x18006cc96  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006cc9d  nop     dword ptr [rax+rax+00h]
0x18006cca2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cca9  mov     rcx, rax
0x18006ccac  test    rax, rax
0x18006ccaf  jz      short loc_18006CCCF
0x18006ccb1  mov     rax, [rax]
0x18006ccb4  mov     edx, 7F0h
0x18006ccb9  mov     rax, [rax+8]
0x18006ccbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ccc2  test    eax, eax
0x18006ccc4  jz      short loc_18006CCCF
0x18006ccc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cccd  jmp     short loc_18006CCDD
0x18006cccf  lea     rcx, qword_1800DBF70; this
0x18006ccd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ccdd  cmp     [rcx+8], r13b
0x18006cce1  jz      short loc_18006CD08
0x18006cce3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006cce8  cmp     [rax+7CCh], ebx
0x18006ccee  jz      short loc_18006CD08
0x18006ccf0  mov     r9d, ebx; int
0x18006ccf3  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006ccfa  mov     r8d, 67Fh; int
0x18006cd00  mov     rcx, rax; this
0x18006cd03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cd08  mov     edi, 1
0x18006cd0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006cd14  jb      loc_18006D4DE
0x18006cd1a  mov     edx, 94h
0x18006cd1f  jmp     loc_18006CAB7
0x18006cd24  mov     eax, [rbp+57h+var_D4]
0x18006cd27  xor     edx, edx
0x18006cd29  mov     r14d, [rbp+57h+var_D0]
0x18006cd2d  mov     r15d, [rsp+130h+var_D8]
0x18006cd32  div     r14d
0x18006cd35  lea     r8d, ds:0[r15*4]
0x18006cd3d  mov     ecx, eax
0x18006cd3f  neg     ecx
0x18006cd41  cmovs   ecx, eax
0x18006cd44  cmp     ecx, r8d
0x18006cd47  jnb     loc_18006CE1B
0x18006cd4d  mov     eax, 20h ; ' '
0x18006cd52  cmp     cs:byte_1800DC8D3, al
0x18006cd58  jb      short loc_18006CD7C
0x18006cd5a  mov     eax, r8d
0x18006cd5d  mov     r9, rsi
0x18006cd60  mov     [rsp+130h+var_108], rax
0x18006cd65  mov     dword ptr [rsp+130h+var_110], ecx
0x18006cd69  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd70  mov     rcx, [rcx+88h]
0x18006cd77  call    WPP_SF_qlPD
0x18006cd7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cd83  mov     ebx, 80070057h
0x18006cd88  test    rcx, rcx
0x18006cd8b  jnz     short loc_18006CDD4
0x18006cd8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006cd94  nop     dword ptr [rax+rax+00h]
0x18006cd99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cda0  mov     rcx, rax
0x18006cda3  test    rax, rax
0x18006cda6  jz      short loc_18006CDC6
0x18006cda8  mov     rax, [rax]
0x18006cdab  mov     edx, 7F0h
0x18006cdb0  mov     rax, [rax+8]
0x18006cdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cdb9  test    eax, eax
0x18006cdbb  jz      short loc_18006CDC6
0x18006cdbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cdc4  jmp     short loc_18006CDD4
0x18006cdc6  lea     rcx, qword_1800DBF70; this
0x18006cdcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cdd4  cmp     [rcx+8], r13b
0x18006cdd8  jz      short loc_18006CDFF
0x18006cdda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006cddf  cmp     [rax+7CCh], ebx
0x18006cde5  jz      short loc_18006CDFF
0x18006cde7  mov     r9d, ebx; int
0x18006cdea  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006cdf1  mov     r8d, 688h; int
0x18006cdf7  mov     rcx, rax; this
0x18006cdfa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006cdff  mov     edi, 1
  ... truncated ...
```
