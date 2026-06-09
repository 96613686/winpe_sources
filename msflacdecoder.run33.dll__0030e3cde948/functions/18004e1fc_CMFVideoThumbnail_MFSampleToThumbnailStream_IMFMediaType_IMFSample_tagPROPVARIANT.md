# CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)

- ea: `0x18004e1fc`
- end: `0x18004ee07`
- name: `?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z`
- size: `3083`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaType *, struct IMFSample *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004c254`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x180020398`
- `0x180020484`
- `0x18002fa8c`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800462a0`
- `0x180048710`
- `0x1800495d0`
- `0x18004c890`
- `0x18004e1fc`
- `0x1800508c4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004e953`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004e953`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e411`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e4d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e593`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e758`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e8c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e96f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ea25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eadb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eb90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ec44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ecfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e411`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e4d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e593`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e758`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e8c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e96f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ea25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eadb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eb90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ec44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ecfb`

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
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct IMFSample *v21; // rdi
  HRESULT (__stdcall *GetBufferByIndex)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  unsigned int v31; // r14d
  unsigned int v32; // r15d
  unsigned int v33; // ecx
  unsigned __int8 Level; // al
  int v35; // ecx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  int v46; // ebx
  unsigned __int64 v47; // rdx
  int v48; // ebx
  unsigned __int64 v49; // rcx
  unsigned int v50; // eax
  bool v51; // zf
  unsigned int v52; // ecx
  __int64 v53; // rdx
  unsigned int v54; // r14d
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  _BYTE v82[8]; // [rsp+40h] [rbp-99h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-91h] BYREF
  struct IMFMediaType *v84; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v85; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v86; // [rsp+5Ch] [rbp-7Dh] BYREF
  unsigned int v87; // [rsp+60h] [rbp-79h] BYREF
  __int64 v88; // [rsp+68h] [rbp-71h] BYREF
  struct IMFSample *v89; // [rsp+70h] [rbp-69h] BYREF
  int v90; // [rsp+78h] [rbp-61h] BYREF
  __int64 v91; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v92[2]; // [rsp+88h] [rbp-51h] BYREF
  int v93; // [rsp+98h] [rbp-41h] BYREF
  __int128 v94; // [rsp+9Ch] [rbp-3Dh]
  __int128 v95; // [rsp+ACh] [rbp-2Dh]
  __int64 v96; // [rsp+BCh] [rbp-1Dh]
  __int128 Buf2; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v98[16]; // [rsp+D8h] [rbp-1h] BYREF

  memset(v92, 0, 14);
  v93 = 0;
  v96 = 0;
  v84 = 0;
  v89 = 0;
  v94 = 0;
  v88 = 0;
  v95 = 0;
  ppstm = 0;
  Buf2 = 0;
  v85 = 0;
  v87 = 0;
  v91 = 0;
  v90 = 0;
  v86 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v82,
    "CMFVideoThumbnail::MFSampleToThumbnailStream",
    1654);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v98);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  v12 = CMFVideoThumbnail::ConvertYUVtoRGB32(this, a3, a2, &v89, &v84);
  if ( v12 < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v12 )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1657, v12);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v16 = 145;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
      goto LABEL_169;
    }
    goto LABEL_169;
  }
  v12 = MFGetAttribute2UINT32asUINT64(v84, &MF_MT_FRAME_SIZE, &v85, &v87);
  if ( v12 >= 0 )
  {
    v21 = v89;
    GetBufferByIndex = v89->lpVtbl->GetBufferByIndex;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    v12 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))GetBufferByIndex)(v21, 0, &v88);
    if ( v12 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v12 )
          CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1661, v12);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 147;
        goto LABEL_15;
      }
      goto LABEL_169;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *, unsigned int *))(*(_QWORD *)v88 + 24LL))(
            v88,
            &v91,
            &v90,
            &v86);
    if ( v12 < 0 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
        if ( *((_DWORD *)v30 + 499) != v12 )
          CallStackContext::TraceFailure(v30, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1663, v12);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 148;
        goto LABEL_15;
      }
      goto LABEL_169;
    }
    v31 = v87;
    v32 = v85;
    v33 = -(int)(v86 / v87);
    if ( (int)(v86 / v87) > 0 )
      v33 = v86 / v87;
    if ( v33 < 4 * v85 )
    {
      Level = _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel();
      v37 = 32;
      if ( Level >= 0x20u )
        WPP_SF_qlPD(*((_QWORD *)WPP_GLOBAL_Control + 17), 32, v36, this, v35, (unsigned int)v36);
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      v12 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
        if ( *((_DWORD *)v40 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v40, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1672, -2147024809);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_168;
      v41 = 150;
      goto LABEL_167;
    }
    v93 = 40;
    DWORD2(v94) = 2097153;
    LODWORD(v94) = v85;
    v12 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))v84->lpVtbl->GetGUID)(
            v84,
            &MF_MT_SUBTYPE,
            &Buf2);
    if ( v12 < 0 )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
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
        if ( *((_DWORD *)v45 + 499) != v12 )
          CallStackContext::TraceFailure(v45, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1696, v12);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_168;
      v41 = 151;
      goto LABEL_167;
    }
    v46 = 1;
    if ( !memcmp_0(&MFVideoFormat_RGB32, &Buf2, 0x10u) )
      v46 = MFGetAttributeUINT32(v84, &MF_MT_DEFAULT_STRIDE, v32);
    v48 = v31 * (((v46 >> 31) & 2) - 1);
    DWORD1(v94) = v48;
    if ( v48 == 0x80000000 || (int)v94 < 0 || (v47 = WORD5(v94), !WORD5(v94)) )
    {
      v12 = -2147024809;
    }
    else
    {
      v49 = WORD5(v94) * (unsigned __int64)(unsigned int)v94;
      if ( v49 <= 0xFFFFFFFF )
      {
        v50 = (unsigned int)v49 >> 3;
        v51 = (v49 & 7) == 0;
        v52 = ((unsigned int)v49 >> 3) + 1;
        if ( v51 )
          v52 = v50;
        if ( (v52 & 3) != 0 )
          v52 = v52 - (v52 & 3) + 4;
        v53 = (unsigned int)-v48;
        if ( v48 > 0 )
          v53 = (unsigned int)v48;
        v47 = v52 * v53;
        if ( v47 <= 0xFFFFFFFF )
        {
          strcpy((char *)v92, "BM");
          LODWORD(v95) = v47;
          BYTE3(v92[0]) = 0;
          WORD2(v92[0]) = 0;
          *(_QWORD *)((char *)v92 + 6) = 0x3A00000000LL;
          v54 = 4 * v32 * v31;
          if ( v54 < 0xFFFFFFC6 )
          {
            *(_DWORD *)((char *)v92 + 2) = v54 + 58;
            v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v12 >= 0 )
            {
              v12 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD *, __int64))ppstm->lpVtbl->Write)(ppstm, v92, 14);
              if ( v12 >= 0 )
              {
                v12 = ((__int64 (__fastcall *)(LPSTREAM, int *, __int64))ppstm->lpVtbl->Write)(ppstm, &v93, 44);
                if ( v12 >= 0 )
                {
                  v12 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
                          ppstm,
                          v91,
                          v54,
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
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 32LL))(v88);
                      goto LABEL_169;
                    }
                    v75 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
                      CallStackTracing::s_wpInstance = v76;
                      if ( v76
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(
                             v76,
                             2032) )
                      {
                        v75 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v75 = &qword_18006EB20;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                      }
                    }
                    if ( *((_BYTE *)v75 + 8) )
                    {
                      v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
                      if ( *((_DWORD *)v77 + 499) != v12 )
                        CallStackContext::TraceFailure(v77, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1731, v12);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_168;
                    v41 = 158;
                  }
                  else
                  {
                    v71 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70);
                      CallStackTracing::s_wpInstance = v72;
                      if ( v72
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(
                             v72,
                             2032) )
                      {
                        v71 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v71 = &qword_18006EB20;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                      }
                    }
                    if ( *((_BYTE *)v71 + 8) )
                    {
                      v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
                      if ( *((_DWORD *)v73 + 499) != v12 )
                        CallStackContext::TraceFailure(v73, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1730, v12);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_168;
                    v41 = 157;
                  }
                }
                else
                {
                  v67 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66);
                    CallStackTracing::s_wpInstance = v68;
                    if ( v68
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                    {
                      v67 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v67 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v67 + 8) )
                  {
                    v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                    if ( *((_DWORD *)v69 + 499) != v12 )
                      CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1726, v12);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_168;
                  v41 = 156;
                }
              }
              else
              {
                v63 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
                  CallStackTracing::s_wpInstance = v64;
                  if ( v64
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
                  {
                    v63 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v63 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v63 + 8) )
                {
                  v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                  if ( *((_DWORD *)v65 + 499) != v12 )
                    CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1725, v12);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_168;
                v41 = 155;
              }
            }
            else
            {
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
                if ( *((_DWORD *)v61 + 499) != v12 )
                  CallStackContext::TraceFailure(v61, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1722, v12);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_168;
              v41 = 154;
            }
          }
          else
          {
            v55 = (__int64 *)CallStackTracing::s_wpInstance;
            v12 = -2147024362;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
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
              if ( *((_DWORD *)v57 + 499) != -2147024362 )
                CallStackContext::TraceFailure(v57, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1719, -2147024362);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_168;
            v41 = 153;
          }
LABEL_167:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v41,
            &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
            this,
            v12);
          goto LABEL_168;
        }
      }
      v12 = -2147024362;
    }
    v78 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
      CallStackTracing::s_wpInstance = v79;
      if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
      {
        v78 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v78 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v78 + 8) )
    {
      v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
      if ( *((_DWORD *)v80 + 499) != v12 )
        CallStackContext::TraceFailure(v80, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1705, v12);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_168;
    v41 = 152;
    goto LABEL_167;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v12 )
      CallStackContext::TraceFailure(v20, "CMFVideoThumbnail::MFSampleToThumbnailStream", 1659, v12);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v16 = 146;
    goto LABEL_15;
  }
LABEL_169:
  if ( ppstm )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    ppstm = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v82);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004e1fc  push    rbp
0x18004e1fe  push    rbx
0x18004e1ff  push    rsi
0x18004e200  push    rdi
0x18004e201  push    r12
0x18004e203  push    r13
0x18004e205  push    r14
0x18004e207  push    r15
0x18004e209  lea     rbp, [rsp-1Fh]
0x18004e20e  sub     rsp, 0F8h
0x18004e215  mov     rax, cs:__security_cookie
0x18004e21c  xor     rax, rsp
0x18004e21f  mov     [rbp+57h+var_48], rax
0x18004e223  xor     r13d, r13d
0x18004e226  xor     eax, eax
0x18004e228  xorps   xmm0, xmm0
0x18004e22b  mov     [rbp+57h+var_A8], rax
0x18004e22f  mov     r15, r8
0x18004e232  mov     [rbp+57h+var_A0], eax
0x18004e235  mov     r14, rdx
0x18004e238  mov     [rbp+57h+var_9C], ax
0x18004e23c  mov     rsi, rcx
0x18004e23f  mov     [rbp+57h+var_98], r13d
0x18004e243  mov     r8d, 676h; int
0x18004e249  mov     [rbp+57h+var_74], rax
0x18004e24d  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e254  mov     [rsp+130h+var_E0], r13
0x18004e259  lea     rcx, [rsp+130h+var_F0]; this
0x18004e25e  mov     [rbp+57h+var_C0], r13
0x18004e262  movups  [rbp+57h+var_94], xmm0
0x18004e266  mov     [rbp+57h+var_C8], r13
0x18004e26a  mov     r12, r9
0x18004e26d  movups  [rbp+57h+var_84], xmm0
0x18004e271  mov     [rsp+130h+ppstm], r13
0x18004e276  movups  [rbp+57h+Buf2], xmm0
0x18004e27a  mov     [rsp+130h+var_D8], r13d
0x18004e27f  mov     [rbp+57h+var_D0], r13d
0x18004e283  mov     [rbp+57h+var_B0], r13
0x18004e287  mov     [rbp+57h+var_B8], r13d
0x18004e28b  mov     [rbp+57h+var_D4], r13d
0x18004e28f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004e294  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004e29b  cmp     [rcx+8], r13b
0x18004e29f  jz      short loc_18004E2F5
0x18004e2a1  cmp     [rsi+190h], r13
0x18004e2a8  jz      short loc_18004E2F5
0x18004e2aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e2af  mov     rcx, [rsi+190h]
0x18004e2b6  mov     rdi, rax
0x18004e2b9  mov     rdx, [rcx]
0x18004e2bc  mov     rax, [rdx+128h]
0x18004e2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2c8  mov     rcx, [rsi+190h]
0x18004e2cf  mov     ebx, eax
0x18004e2d1  mov     rdx, [rcx]
0x18004e2d4  mov     rax, [rdx+118h]
0x18004e2db  lea     rdx, [rbp+57h+var_58]
0x18004e2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2e4  movups  xmm0, xmmword ptr [rax]
0x18004e2e7  mov     [rdi+7E0h], ebx
0x18004e2ed  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004e2f5  lea     rcx, [rsp+130h+var_E0]
0x18004e2fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e2ff  lea     rcx, [rbp+57h+var_C0]
0x18004e303  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e308  lea     rax, [rsp+130h+var_E0]
0x18004e30d  mov     r8, r14; struct IMFMediaType *
0x18004e310  lea     r9, [rbp+57h+var_C0]; struct IMFSample **
0x18004e314  mov     [rsp+130h+var_110], rax; struct IMFMediaType **
0x18004e319  mov     rdx, r15; struct IMFSample *
0x18004e31c  mov     rcx, rsi; this
0x18004e31f  call    ?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z; CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)
0x18004e324  mov     ebx, eax
0x18004e326  test    eax, eax
0x18004e328  jns     loc_18004E3E1
0x18004e32e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e335  test    rcx, rcx
0x18004e338  jnz     short loc_18004E37B
0x18004e33a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e340  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e347  mov     rcx, rax
0x18004e34a  test    rax, rax
0x18004e34d  jz      short loc_18004E36D
0x18004e34f  mov     rax, [rax]
0x18004e352  mov     edx, 7F0h
0x18004e357  mov     rax, [rax+8]
0x18004e35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e360  test    eax, eax
0x18004e362  jz      short loc_18004E36D
0x18004e364  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e36b  jmp     short loc_18004E37B
0x18004e36d  lea     rcx, qword_18006EB20; this
0x18004e374  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e37b  cmp     [rcx+8], r13b
0x18004e37f  jz      short loc_18004E3A6
0x18004e381  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e386  cmp     [rax+7CCh], ebx
0x18004e38c  jz      short loc_18004E3A6
0x18004e38e  mov     r9d, ebx; int
0x18004e391  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e398  mov     r8d, 679h; int
0x18004e39e  mov     rcx, rax; this
0x18004e3a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e3a6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e3ab  mov     edi, 1
0x18004e3b0  cmp     al, dil
0x18004e3b3  jb      loc_18004EDA4
0x18004e3b9  mov     edx, 91h
0x18004e3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e3c5  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004e3cc  mov     r9, rsi
0x18004e3cf  mov     dword ptr [rsp+130h+var_110], ebx
0x18004e3d3  mov     rcx, [rcx+10h]
0x18004e3d7  call    WPP_SF_qd
0x18004e3dc  jmp     loc_18004EDA4
0x18004e3e1  mov     rcx, [rsp+130h+var_E0]
0x18004e3e6  lea     r9, [rbp+57h+var_D0]
0x18004e3ea  lea     r8, [rsp+130h+var_D8]
0x18004e3ef  lea     rdx, MF_MT_FRAME_SIZE
0x18004e3f6  call    MFGetAttribute2UINT32asUINT64
0x18004e3fb  mov     ebx, eax
0x18004e3fd  test    eax, eax
0x18004e3ff  jns     loc_18004E49A
0x18004e405  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e40c  test    rcx, rcx
0x18004e40f  jnz     short loc_18004E452
0x18004e411  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e417  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e41e  mov     rcx, rax
0x18004e421  test    rax, rax
0x18004e424  jz      short loc_18004E444
0x18004e426  mov     rax, [rax]
0x18004e429  mov     edx, 7F0h
0x18004e42e  mov     rax, [rax+8]
0x18004e432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e437  test    eax, eax
0x18004e439  jz      short loc_18004E444
0x18004e43b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e442  jmp     short loc_18004E452
0x18004e444  lea     rcx, qword_18006EB20; this
0x18004e44b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e452  cmp     [rcx+8], r13b
0x18004e456  jz      short loc_18004E47D
0x18004e458  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e45d  cmp     [rax+7CCh], ebx
0x18004e463  jz      short loc_18004E47D
0x18004e465  mov     r9d, ebx; int
0x18004e468  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e46f  mov     r8d, 67Bh; int
0x18004e475  mov     rcx, rax; this
0x18004e478  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e47d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e482  mov     edi, 1
0x18004e487  cmp     al, dil
0x18004e48a  jb      loc_18004EDA4
0x18004e490  mov     edx, 92h
0x18004e495  jmp     loc_18004E3BE
0x18004e49a  mov     rdi, [rbp+57h+var_C0]
0x18004e49e  lea     rcx, [rbp+57h+var_C8]
0x18004e4a2  mov     rax, [rdi]
0x18004e4a5  mov     rbx, [rax+140h]
0x18004e4ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e4b1  lea     r8, [rbp+57h+var_C8]
0x18004e4b5  xor     edx, edx
0x18004e4b7  mov     rcx, rdi
0x18004e4ba  mov     rax, rbx
0x18004e4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4c2  mov     ebx, eax
0x18004e4c4  test    eax, eax
0x18004e4c6  jns     loc_18004E561
0x18004e4cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e4d3  test    rcx, rcx
0x18004e4d6  jnz     short loc_18004E519
0x18004e4d8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e4de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e4e5  mov     rcx, rax
0x18004e4e8  test    rax, rax
0x18004e4eb  jz      short loc_18004E50B
0x18004e4ed  mov     rax, [rax]
0x18004e4f0  mov     edx, 7F0h
0x18004e4f5  mov     rax, [rax+8]
0x18004e4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4fe  test    eax, eax
0x18004e500  jz      short loc_18004E50B
0x18004e502  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e509  jmp     short loc_18004E519
0x18004e50b  lea     rcx, qword_18006EB20; this
0x18004e512  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e519  cmp     [rcx+8], r13b
0x18004e51d  jz      short loc_18004E544
0x18004e51f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e524  cmp     [rax+7CCh], ebx
0x18004e52a  jz      short loc_18004E544
0x18004e52c  mov     r9d, ebx; int
0x18004e52f  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e536  mov     r8d, 67Dh; int
0x18004e53c  mov     rcx, rax; this
0x18004e53f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e544  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e549  mov     edi, 1
0x18004e54e  cmp     al, dil
0x18004e551  jb      loc_18004EDA4
0x18004e557  mov     edx, 93h
0x18004e55c  jmp     loc_18004E3BE
0x18004e561  mov     rcx, [rbp+57h+var_C8]
0x18004e565  lea     r9, [rbp+57h+var_D4]
0x18004e569  lea     r8, [rbp+57h+var_B8]
0x18004e56d  lea     rdx, [rbp+57h+var_B0]
0x18004e571  mov     rax, [rcx]
0x18004e574  mov     rax, [rax+18h]
0x18004e578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e57d  mov     ebx, eax
0x18004e57f  test    eax, eax
0x18004e581  jns     loc_18004E61C
0x18004e587  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e58e  test    rcx, rcx
0x18004e591  jnz     short loc_18004E5D4
0x18004e593  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e599  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5a0  mov     rcx, rax
0x18004e5a3  test    rax, rax
0x18004e5a6  jz      short loc_18004E5C6
0x18004e5a8  mov     rax, [rax]
0x18004e5ab  mov     edx, 7F0h
0x18004e5b0  mov     rax, [rax+8]
0x18004e5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5b9  test    eax, eax
0x18004e5bb  jz      short loc_18004E5C6
0x18004e5bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5c4  jmp     short loc_18004E5D4
0x18004e5c6  lea     rcx, qword_18006EB20; this
0x18004e5cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5d4  cmp     [rcx+8], r13b
0x18004e5d8  jz      short loc_18004E5FF
0x18004e5da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e5df  cmp     [rax+7CCh], ebx
0x18004e5e5  jz      short loc_18004E5FF
0x18004e5e7  mov     r9d, ebx; int
0x18004e5ea  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e5f1  mov     r8d, 67Fh; int
0x18004e5f7  mov     rcx, rax; this
0x18004e5fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e5ff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e604  mov     edi, 1
0x18004e609  cmp     al, dil
0x18004e60c  jb      loc_18004EDA4
0x18004e612  mov     edx, 94h
0x18004e617  jmp     loc_18004E3BE
0x18004e61c  mov     eax, [rbp+57h+var_D4]
0x18004e61f  xor     edx, edx
0x18004e621  mov     r14d, [rbp+57h+var_D0]
0x18004e625  mov     r15d, [rsp+130h+var_D8]
0x18004e62a  div     r14d
0x18004e62d  lea     r8d, ds:0[r15*4]
0x18004e635  mov     ecx, eax
0x18004e637  neg     ecx
0x18004e639  cmovs   ecx, eax
0x18004e63c  cmp     ecx, r8d
0x18004e63f  jnb     loc_18004E70F
0x18004e645  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_SOURCES@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel(void)
0x18004e64a  mov     edx, 20h ; ' '
0x18004e64f  cmp     al, dl
0x18004e651  jb      short loc_18004E675
0x18004e653  mov     eax, r8d
0x18004e656  mov     r9, rsi
0x18004e659  mov     [rsp+130h+var_108], rax
0x18004e65e  mov     dword ptr [rsp+130h+var_110], ecx
0x18004e662  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e669  mov     rcx, [rcx+88h]
0x18004e670  call    WPP_SF_qlPD
0x18004e675  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e67c  mov     ebx, 80070057h
0x18004e681  test    rcx, rcx
0x18004e684  jnz     short loc_18004E6C7
0x18004e686  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e68c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e693  mov     rcx, rax
0x18004e696  test    rax, rax
0x18004e699  jz      short loc_18004E6B9
0x18004e69b  mov     rax, [rax]
0x18004e69e  mov     edx, 7F0h
0x18004e6a3  mov     rax, [rax+8]
0x18004e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6ac  test    eax, eax
0x18004e6ae  jz      short loc_18004E6B9
0x18004e6b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6b7  jmp     short loc_18004E6C7
0x18004e6b9  lea     rcx, qword_18006EB20; this
0x18004e6c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6c7  cmp     [rcx+8], r13b
0x18004e6cb  jz      short loc_18004E6F2
0x18004e6cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e6d2  cmp     [rax+7CCh], ebx
0x18004e6d8  jz      short loc_18004E6F2
0x18004e6da  mov     r9d, ebx; int
0x18004e6dd  lea     rdx, aCmfvideothumbn_11; "CMFVideoThumbnail::MFSampleToThumbnailS"...
0x18004e6e4  mov     r8d, 688h; int
0x18004e6ea  mov     rcx, rax; this
0x18004e6ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e6f2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
  ... truncated ...
```
