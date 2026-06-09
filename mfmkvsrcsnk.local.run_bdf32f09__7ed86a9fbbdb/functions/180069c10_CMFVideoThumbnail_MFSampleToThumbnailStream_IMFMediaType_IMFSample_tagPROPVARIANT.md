# CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)

- ea: `0x180069c10`
- end: `0x18006a80d`
- name: `?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z`
- size: `3069`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaType *, struct IMFSample *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180067c44`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180051c90`
- `0x18005d6f4`
- `0x180064fc8`
- `0x180069c10`
- `0x18006c280`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006a35f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006a35f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069eea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069fa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a095`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a2d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a37b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a4e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a64c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a702`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069eea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069fa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a095`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a2d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a37b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a4e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a64c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a702`

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
        v15 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v30 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
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
          v44 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v50 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v88 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v83 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                      v78 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v73 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v68 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v63 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v91 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v22 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180069c10  push    rbp
0x180069c12  push    rbx
0x180069c13  push    rsi
0x180069c14  push    rdi
0x180069c15  push    r12
0x180069c17  push    r13
0x180069c19  push    r14
0x180069c1b  push    r15
0x180069c1d  lea     rbp, [rsp-1Fh]
0x180069c22  sub     rsp, 0F8h
0x180069c29  mov     rax, cs:__security_cookie
0x180069c30  xor     rax, rsp
0x180069c33  mov     [rbp+57h+var_48], rax
0x180069c37  xor     r13d, r13d
0x180069c3a  xor     eax, eax
0x180069c3c  xorps   xmm0, xmm0
0x180069c3f  mov     [rbp+57h+var_A8], rax
0x180069c43  mov     r15, r8
0x180069c46  mov     [rbp+57h+var_A0], eax
0x180069c49  mov     r14, rdx
0x180069c4c  mov     [rbp+57h+var_9C], ax
0x180069c50  mov     rsi, rcx
0x180069c53  mov     [rbp+57h+var_98], r13d
0x180069c57  mov     r8d, 676h; int
0x180069c5d  mov     [rbp+57h+var_74], rax
0x180069c61  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x180069c68  mov     [rsp+130h+var_E0], r13
0x180069c6d  lea     rcx, [rsp+130h+var_F0]; this
0x180069c72  mov     [rbp+57h+var_C0], r13
0x180069c76  movups  [rbp+57h+var_94], xmm0
0x180069c7a  mov     [rbp+57h+var_C8], r13
0x180069c7e  mov     r12, r9
0x180069c81  movups  [rbp+57h+var_84], xmm0
0x180069c85  mov     [rsp+130h+ppstm], r13
0x180069c8a  movups  [rbp+57h+Buf2], xmm0
0x180069c8e  mov     [rsp+130h+var_D8], r13d
0x180069c93  mov     [rbp+57h+var_D0], r13d
0x180069c97  mov     [rbp+57h+var_B0], r13
0x180069c9b  mov     [rbp+57h+var_B8], r13d
0x180069c9f  mov     [rbp+57h+var_D4], r13d
0x180069ca3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180069ca8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180069caf  cmp     [rcx+8], r13b
0x180069cb3  jz      short loc_180069D09
0x180069cb5  cmp     [rsi+190h], r13
0x180069cbc  jz      short loc_180069D09
0x180069cbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069cc3  mov     rcx, [rsi+190h]
0x180069cca  mov     rdi, rax
0x180069ccd  mov     rdx, [rcx]
0x180069cd0  mov     rax, [rdx+128h]
0x180069cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069cdc  mov     rcx, [rsi+190h]
0x180069ce3  mov     ebx, eax
0x180069ce5  mov     rdx, [rcx]
0x180069ce8  mov     rax, [rdx+118h]
0x180069cef  lea     rdx, [rbp+57h+var_58]
0x180069cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069cf8  movups  xmm0, xmmword ptr [rax]
0x180069cfb  mov     [rdi+7E0h], ebx
0x180069d01  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180069d09  lea     rcx, [rsp+130h+var_E0]
0x180069d0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069d13  lea     rcx, [rbp+57h+var_C0]
0x180069d17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069d1c  lea     rax, [rsp+130h+var_E0]
0x180069d21  mov     r8, r14; struct IMFMediaType *
0x180069d24  lea     r9, [rbp+57h+var_C0]; struct IMFSample **
0x180069d28  mov     [rsp+130h+var_110], rax; struct IMFMediaType **
0x180069d2d  mov     rdx, r15; struct IMFSample *
0x180069d30  mov     rcx, rsi; this
0x180069d33  call    ?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z; CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)
0x180069d38  mov     ebx, eax
0x180069d3a  test    eax, eax
0x180069d3c  jns     loc_180069DF4
0x180069d42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d49  test    rcx, rcx
0x180069d4c  jnz     short loc_180069D8F
0x180069d4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069d54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d5b  mov     rcx, rax
0x180069d5e  test    rax, rax
0x180069d61  jz      short loc_180069D81
0x180069d63  mov     rax, [rax]
0x180069d66  mov     edx, 7F0h
0x180069d6b  mov     rax, [rax+8]
0x180069d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d74  test    eax, eax
0x180069d76  jz      short loc_180069D81
0x180069d78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d7f  jmp     short loc_180069D8F
0x180069d81  lea     rcx, qword_1800D6F70; this
0x180069d88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d8f  cmp     [rcx+8], r13b
0x180069d93  jz      short loc_180069DBA
0x180069d95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069d9a  cmp     [rax+7CCh], ebx
0x180069da0  jz      short loc_180069DBA
0x180069da2  mov     r9d, ebx; int
0x180069da5  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x180069dac  mov     r8d, 679h; int
0x180069db2  mov     rcx, rax; this
0x180069db5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069dba  mov     edi, 1
0x180069dbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180069dc6  jb      loc_18006A7AA
0x180069dcc  mov     edx, 91h
0x180069dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180069dd8  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180069ddf  mov     r9, rsi
0x180069de2  mov     dword ptr [rsp+130h+var_110], ebx
0x180069de6  mov     rcx, [rcx+10h]
0x180069dea  call    WPP_SF_qD
0x180069def  jmp     loc_18006A7AA
0x180069df4  mov     rcx, [rsp+130h+var_E0]
0x180069df9  lea     r9, [rbp+57h+var_D0]
0x180069dfd  lea     r8, [rsp+130h+var_D8]
0x180069e02  lea     rdx, MF_MT_FRAME_SIZE
0x180069e09  call    MFGetAttribute2UINT32asUINT64
0x180069e0e  mov     ebx, eax
0x180069e10  test    eax, eax
0x180069e12  jns     loc_180069EAC
0x180069e18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069e1f  test    rcx, rcx
0x180069e22  jnz     short loc_180069E65
0x180069e24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069e2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069e31  mov     rcx, rax
0x180069e34  test    rax, rax
0x180069e37  jz      short loc_180069E57
0x180069e39  mov     rax, [rax]
0x180069e3c  mov     edx, 7F0h
0x180069e41  mov     rax, [rax+8]
0x180069e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e4a  test    eax, eax
0x180069e4c  jz      short loc_180069E57
0x180069e4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069e55  jmp     short loc_180069E65
0x180069e57  lea     rcx, qword_1800D6F70; this
0x180069e5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069e65  cmp     [rcx+8], r13b
0x180069e69  jz      short loc_180069E90
0x180069e6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069e70  cmp     [rax+7CCh], ebx
0x180069e76  jz      short loc_180069E90
0x180069e78  mov     r9d, ebx; int
0x180069e7b  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x180069e82  mov     r8d, 67Bh; int
0x180069e88  mov     rcx, rax; this
0x180069e8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069e90  mov     edi, 1
0x180069e95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180069e9c  jb      loc_18006A7AA
0x180069ea2  mov     edx, 92h
0x180069ea7  jmp     loc_180069DD1
0x180069eac  mov     rdi, [rbp+57h+var_C0]
0x180069eb0  lea     rcx, [rbp+57h+var_C8]
0x180069eb4  mov     rax, [rdi]
0x180069eb7  mov     rbx, [rax+140h]
0x180069ebe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069ec3  lea     r8, [rbp+57h+var_C8]
0x180069ec7  xor     edx, edx
0x180069ec9  mov     rcx, rdi
0x180069ecc  mov     rax, rbx
0x180069ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ed4  mov     ebx, eax
0x180069ed6  test    eax, eax
0x180069ed8  jns     loc_180069F72
0x180069ede  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069ee5  test    rcx, rcx
0x180069ee8  jnz     short loc_180069F2B
0x180069eea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069ef0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069ef7  mov     rcx, rax
0x180069efa  test    rax, rax
0x180069efd  jz      short loc_180069F1D
0x180069eff  mov     rax, [rax]
0x180069f02  mov     edx, 7F0h
0x180069f07  mov     rax, [rax+8]
0x180069f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f10  test    eax, eax
0x180069f12  jz      short loc_180069F1D
0x180069f14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f1b  jmp     short loc_180069F2B
0x180069f1d  lea     rcx, qword_1800D6F70; this
0x180069f24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f2b  cmp     [rcx+8], r13b
0x180069f2f  jz      short loc_180069F56
0x180069f31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069f36  cmp     [rax+7CCh], ebx
0x180069f3c  jz      short loc_180069F56
0x180069f3e  mov     r9d, ebx; int
0x180069f41  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x180069f48  mov     r8d, 67Dh; int
0x180069f4e  mov     rcx, rax; this
0x180069f51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069f56  mov     edi, 1
0x180069f5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180069f62  jb      loc_18006A7AA
0x180069f68  mov     edx, 93h
0x180069f6d  jmp     loc_180069DD1
0x180069f72  mov     rcx, [rbp+57h+var_C8]
0x180069f76  lea     r9, [rbp+57h+var_D4]
0x180069f7a  lea     r8, [rbp+57h+var_B8]
0x180069f7e  lea     rdx, [rbp+57h+var_B0]
0x180069f82  mov     rax, [rcx]
0x180069f85  mov     rax, [rax+18h]
0x180069f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f8e  mov     ebx, eax
0x180069f90  test    eax, eax
0x180069f92  jns     loc_18006A02C
0x180069f98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f9f  test    rcx, rcx
0x180069fa2  jnz     short loc_180069FE5
0x180069fa4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069faa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069fb1  mov     rcx, rax
0x180069fb4  test    rax, rax
0x180069fb7  jz      short loc_180069FD7
0x180069fb9  mov     rax, [rax]
0x180069fbc  mov     edx, 7F0h
0x180069fc1  mov     rax, [rax+8]
0x180069fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069fca  test    eax, eax
0x180069fcc  jz      short loc_180069FD7
0x180069fce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069fd5  jmp     short loc_180069FE5
0x180069fd7  lea     rcx, qword_1800D6F70; this
0x180069fde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069fe5  cmp     [rcx+8], r13b
0x180069fe9  jz      short loc_18006A010
0x180069feb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069ff0  cmp     [rax+7CCh], ebx
0x180069ff6  jz      short loc_18006A010
0x180069ff8  mov     r9d, ebx; int
0x180069ffb  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006a002  mov     r8d, 67Fh; int
0x18006a008  mov     rcx, rax; this
0x18006a00b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a010  mov     edi, 1
0x18006a015  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006a01c  jb      loc_18006A7AA
0x18006a022  mov     edx, 94h
0x18006a027  jmp     loc_180069DD1
0x18006a02c  mov     eax, [rbp+57h+var_D4]
0x18006a02f  xor     edx, edx
0x18006a031  mov     r14d, [rbp+57h+var_D0]
0x18006a035  mov     r15d, [rsp+130h+var_D8]
0x18006a03a  div     r14d
0x18006a03d  lea     r8d, ds:0[r15*4]
0x18006a045  mov     ecx, eax
0x18006a047  neg     ecx
0x18006a049  cmovs   ecx, eax
0x18006a04c  cmp     ecx, r8d
0x18006a04f  jnb     loc_18006A11D
0x18006a055  mov     eax, 20h ; ' '
0x18006a05a  cmp     cs:byte_1800D78D3, al
0x18006a060  jb      short loc_18006A084
0x18006a062  mov     eax, r8d
0x18006a065  mov     r9, rsi
0x18006a068  mov     [rsp+130h+var_108], rax
0x18006a06d  mov     dword ptr [rsp+130h+var_110], ecx
0x18006a071  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a078  mov     rcx, [rcx+88h]
0x18006a07f  call    WPP_SF_qlPD
0x18006a084  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a08b  mov     ebx, 80070057h
0x18006a090  test    rcx, rcx
0x18006a093  jnz     short loc_18006A0D6
0x18006a095  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a09b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a0a2  mov     rcx, rax
0x18006a0a5  test    rax, rax
0x18006a0a8  jz      short loc_18006A0C8
0x18006a0aa  mov     rax, [rax]
0x18006a0ad  mov     edx, 7F0h
0x18006a0b2  mov     rax, [rax+8]
0x18006a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a0bb  test    eax, eax
0x18006a0bd  jz      short loc_18006A0C8
0x18006a0bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a0c6  jmp     short loc_18006A0D6
0x18006a0c8  lea     rcx, qword_1800D6F70; this
0x18006a0cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a0d6  cmp     [rcx+8], r13b
0x18006a0da  jz      short loc_18006A101
0x18006a0dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a0e1  cmp     [rax+7CCh], ebx
0x18006a0e7  jz      short loc_18006A101
0x18006a0e9  mov     r9d, ebx; int
0x18006a0ec  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18006a0f3  mov     r8d, 688h; int
0x18006a0f9  mov     rcx, rax; this
0x18006a0fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a101  mov     edi, 1
0x18006a106  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006a10d  jb      loc_18006A79A
0x18006a113  mov     edx, 96h
0x18006a118  jmp     loc_18006A77C
0x18006a11d  mov     rcx, [rsp+130h+var_E0]
  ... truncated ...
```
