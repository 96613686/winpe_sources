# CAVIStreamSink::WriteStreamHeader(uchar *,ulong,ulong *)

- ea: `0x1800b9a74`
- end: `0x1800ba8bd`
- name: `?WriteStreamHeader@CAVIStreamSink@@QEAAJPEAEKPEAK@Z`
- size: `3657`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800abd0c`
- `0x1800b68ac`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180056e38`
- `0x180073b14`
- `0x1800b9a74`
- `0x1800c6934`
- `0x1800d1150`
- `0x1800e043c`
- `0x1801099f0`
- `0x18010a450`
- `0x18011fc68`
- `0x180128750`
- `0x18012b6a0`
- `0x1801723d4`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9b1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9be3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9cb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9f4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba01d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba0f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba1ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba315`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba44e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba4f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba605`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba6e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba836`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9b1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9be3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9cb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9f4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba01d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba0f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba1ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba315`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba44e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba4f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba605`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba6e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba836`
- `MFPlat!MFIsBottomUpFormat` at `0x1800b9e38`
- `MFPlat!MFIsBottomUpFormat` at `0x1800b9e38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba6c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba6c2`

## string_xrefs

- `0x1800b9ac7`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9b76`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9c3a`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9d0b`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9de6`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9eab`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800b9fa4`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba074`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba14a`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba204`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba2ba`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba36c`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba4a5`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba548`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba65c`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba737`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800ba88d`: `CAVIStreamSink::WriteStreamHeader`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::WriteStreamHeader(
        CAVIStreamSink *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  GUID v4; // xmm6
  struct IMFMediaType *v7; // rbx
  int CurrentMediaType; // esi
  unsigned int v10; // r12d
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  _DWORD *v33; // r13
  unsigned int v34; // edi
  int v35; // eax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  int v59; // eax
  unsigned int v60; // r13d
  __int64 v61; // rdi
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  size_t v69; // r8
  void *v70; // rdx
  unsigned int v71; // edi
  struct IMFMediaTypeVtbl *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  int v82; // edi
  const void *v83; // rax
  size_t v84; // r8
  __int64 v85; // rdx
  __int64 v86; // r8
  struct IMFMediaTypeVtbl *v87; // rax
  wchar_t *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  unsigned int v92; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v93[4]; // [rsp+3Ch] [rbp-75h] BYREF
  unsigned int Size; // [rsp+40h] [rbp-71h] BYREF
  unsigned int Size_4; // [rsp+44h] [rbp-6Dh] BYREF
  void *Src; // [rsp+48h] [rbp-69h] BYREF
  int v97; // [rsp+50h] [rbp-61h] BYREF
  int v98; // [rsp+54h] [rbp-5Dh] BYREF
  struct IMFMediaType *v99[2]; // [rsp+58h] [rbp-59h] BYREF
  LPVOID pv[2]; // [rsp+68h] [rbp-49h] BYREF
  __int64 v101; // [rsp+78h] [rbp-39h] BYREF
  int v102; // [rsp+80h] [rbp-31h] BYREF
  __int64 v103; // [rsp+84h] [rbp-2Dh]
  int v104; // [rsp+8Ch] [rbp-25h]
  __int64 v105; // [rsp+90h] [rbp-21h]
  GUID v106; // [rsp+98h] [rbp-19h] BYREF
  GUID Buf1; // [rsp+A8h] [rbp-9h] BYREF

  Size_4 = a3;
  v4 = AM_MEDIA_TYPE_REPRESENTATION;
  *(_QWORD *)&v106.Data1 = a4;
  v7 = 0;
  v101 = 0;
  v99[0] = 0;
  v97 = 0;
  v92 = 0;
  CurrentMediaType = a4 == 0 ? 0x80004003 : 0;
  v98 = 0;
  v10 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v93, "CAVIStreamSink::WriteStreamHeader", 1083);
  if ( !a4 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentMediaType )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIStreamSink::WriteStreamHeader",
          1083,
          CurrentMediaType);
    }
    if ( g_wppLevels )
    {
      v15 = 182;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        this,
        CurrentMediaType);
      goto LABEL_191;
    }
    goto LABEL_191;
  }
  CurrentMediaType = CBaseStreamSink::GetCurrentMediaType((CAVIStreamSink *)((char *)this + 32), v99);
  if ( CurrentMediaType < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != CurrentMediaType )
        CallStackContext::TraceFailure(v19, "CAVIStreamSink::WriteStreamHeader", 1084, CurrentMediaType);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        183,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        this,
        CurrentMediaType);
    v7 = v99[0];
    goto LABEL_191;
  }
  v7 = v99[0];
  CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *))v99[0]->lpVtbl->GetMajorType)(
                       v99[0],
                       &Buf1);
  if ( CurrentMediaType >= 0 )
  {
    if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
      v4 = FORMAT_VideoInfo;
    lpVtbl = v7->lpVtbl;
    *(GUID *)pv = v4;
    CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, LPVOID *, __int64 *))lpVtbl->GetRepresentation)(
                         v7,
                         pv,
                         &v101);
    if ( CurrentMediaType < 0 )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v28, "CAVIStreamSink::WriteStreamHeader", 1091, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v15 = 185;
        goto LABEL_12;
      }
      goto LABEL_191;
    }
    if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
    {
      LODWORD(pv[0]) = 0;
      CurrentMediaType = MFIsBottomUpFormat(v7, pv);
      if ( CurrentMediaType < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v32, "CAVIStreamSink::WriteStreamHeader", 1096, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v15 = 186;
          goto LABEL_12;
        }
        goto LABEL_191;
      }
      v33 = (_DWORD *)(*(_QWORD *)(v101 + 80) + 48LL);
      v34 = *(_DWORD *)(v101 + 72) - 48;
      if ( LODWORD(pv[0]) && (int)MFGetAttributeUINT32(v7, &MF_MT_DEFAULT_STRIDE, 0) >= 0 )
      {
        v35 = -v33[2];
        if ( (int)v33[2] > 0 )
          v35 = v33[2];
        v33[2] = -v35;
      }
    }
    else
    {
      v33 = *(_DWORD **)(v101 + 80);
      v34 = *(_DWORD *)(v101 + 72);
    }
    LODWORD(Src) = v34 + 8;
    CurrentMediaType = AVIHelpers::AlignUp(&Src);
    if ( CurrentMediaType < 0 )
    {
      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v39, "CAVIStreamSink::WriteStreamHeader", 1116, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v15 = 187;
        goto LABEL_12;
      }
      goto LABEL_191;
    }
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, int *))v7->lpVtbl->GetBlobSize)(
           v7,
           &MF_MT_USER_DATA,
           &v97) >= 0 )
    {
      v92 = v97 + 8;
      CurrentMediaType = AVIHelpers::AlignUp(&v92);
      if ( CurrentMediaType < 0 )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
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
          if ( *((_DWORD *)v43 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v43, "CAVIStreamSink::WriteStreamHeader", 1121, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v15 = 188;
          goto LABEL_12;
        }
        goto LABEL_191;
      }
    }
    if ( ((int (__fastcall *)(struct IMFMediaType *, const IID *, int *))v7->lpVtbl->GetStringLength)(
           v7,
           &MF_SD_STREAM_NAME,
           &v98) >= 0 )
    {
      Size = v98 + 8;
      CurrentMediaType = AVIHelpers::AlignUp(&Size);
      if ( CurrentMediaType < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v47 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v47, "CAVIStreamSink::WriteStreamHeader", 1127, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v15 = 189;
          goto LABEL_12;
        }
        goto LABEL_191;
      }
      v10 = Size;
    }
    Size = (_DWORD)Src + 64 + v10 + v92;
    CurrentMediaType = AVIHelpers::AlignUp(&Size);
    if ( CurrentMediaType < 0 )
    {
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v51, "CAVIStreamSink::WriteStreamHeader", 1131, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v15 = 190;
        goto LABEL_12;
      }
      goto LABEL_191;
    }
    if ( !a2 )
    {
      **(_DWORD **)&v106.Data1 = Size;
      goto LABEL_191;
    }
    if ( Size_4 < Size )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      CurrentMediaType = -1072875855;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != -1072875855 )
          CallStackContext::TraceFailure(v54, "CAVIStreamSink::WriteStreamHeader", 1140, -1072875855);
      }
      if ( g_wppLevels )
      {
        v15 = 191;
        goto LABEL_12;
      }
      goto LABEL_191;
    }
    memset_0(a2, 0, Size);
    CurrentMediaType = CAVIStreamSink::PopulateStreamHeader(this);
    if ( CurrentMediaType < 0 )
    {
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
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
        if ( *((_DWORD *)v58 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v58, "CAVIStreamSink::WriteStreamHeader", 1146, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v15 = 192;
        goto LABEL_12;
      }
      goto LABEL_191;
    }
    v59 = (_DWORD)Src - 8;
    *(_OWORD *)a2 = *((_OWORD *)this + 25);
    *((_OWORD *)a2 + 1) = *((_OWORD *)this + 26);
    *((_OWORD *)a2 + 2) = *((_OWORD *)this + 27);
    *((_OWORD *)a2 + 3) = *((_OWORD *)this + 28);
    *((_DWORD *)a2 + 16) = 1718776947;
    *((_DWORD *)a2 + 17) = v59;
    memcpy_0(a2 + 72, v33, v34);
    v60 = v92;
    Size_4 = (_DWORD)Src + 72;
    v61 = (unsigned int)((_DWORD)Src + 64);
    if ( v92 )
    {
      Src = 0;
      v92 = 0;
      CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, void **, unsigned int *))v7->lpVtbl->GetAllocatedBlob)(
                           v7,
                           &MF_MT_USER_DATA,
                           &Src,
                           &v92);
      if ( CurrentMediaType < 0 )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
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
          if ( *((_DWORD *)v65 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v65, "CAVIStreamSink::WriteStreamHeader", 1162, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v15 = 193;
          goto LABEL_12;
        }
        goto LABEL_191;
      }
      if ( v92 > v60 )
      {
        v66 = (wchar_t *)CallStackTracing::s_wpInstance;
        CurrentMediaType = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
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
          if ( *((_DWORD *)v68 + 499) != -2147418113 )
            CallStackContext::TraceFailure(v68, "CAVIStreamSink::WriteStreamHeader", 1165, -2147418113);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            194,
            &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
            this,
            -2147418113);
        goto LABEL_191;
      }
      v69 = v92;
      v70 = Src;
      *(_DWORD *)&a2[v61 + 4] = v60 - 8;
      *(_DWORD *)&a2[v61] = 1685222515;
      v71 = Size_4;
      memcpy_0(&a2[Size_4], v70, v69);
      v61 = v60 + v71 - 8;
      CoTaskMemFree(Src);
    }
    if ( v10 )
    {
      v102 &= 0xFFFFFFF8;
      pv[0] = 0;
      Size_4 = 0;
      v72 = v7->lpVtbl;
      v103 = 0;
      v105 = 0;
      v104 = 0;
      CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, const IID *, LPVOID *, unsigned int *))v72->GetAllocatedString)(
                           v7,
                           &MF_SD_STREAM_NAME,
                           pv,
                           &Size_4);
      if ( CurrentMediaType < 0 )
      {
        v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73);
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
          if ( *((_DWORD *)v77 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v77, "CAVIStreamSink::WriteStreamHeader", 1181, CurrentMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_176;
        v78 = 195;
LABEL_175:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v78,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          this,
          CurrentMediaType);
LABEL_176:
        CMFBaseStringT<char>::~CMFBaseStringT<char>(&v102, v73, v74);
        goto LABEL_191;
      }
      CurrentMediaType = CMFBaseStringT<char>::Append(&v102, v73, pv[0], 0xFFFFFFFFLL);
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
      if ( CurrentMediaType < 0 )
      {
        v79 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73);
          CallStackTracing::s_wpInstance = v80;
          if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
          {
            v79 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v79 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v79 + 8) )
        {
          v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
          if ( *((_DWORD *)v81 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v81, "CAVIStreamSink::WriteStreamHeader", 1185, CurrentMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_176;
        v78 = 196;
        goto LABEL_175;
      }
      if ( (int)v103 >= 0 )
      {
        v73 = HIDWORD(v103);
        if ( HIDWORD(v103) > v10 )
        {
          v89 = (wchar_t *)CallStackTracing::s_wpInstance;
          CurrentMediaType = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, HIDWORD(v103));
            CallStackTracing::s_wpInstance = v90;
            if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
            {
              v89 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v89 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v89 + 8) )
          {
            v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
            if ( *((_DWORD *)v91 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v91, "CAVIStreamSink::WriteStreamHeader", 1189, -2147418113);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              197,
              &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
              this,
              -2147418113);
          goto LABEL_176;
        }
      }
      *(_DWORD *)&a2[v61] = 1852994675;
      *(_DWORD *)&a2[v61 + 4] = v10 - 8;
      v82 = v61 + 8;
      v83 = (const void *)CMFBaseStringT<char>::PContents(&v102);
      memcpy_0(&a2[v82], v83, v84);
      LODWORD(v61) = v10 + v82 - 8;
      CMFBaseStringT<char>::~CMFBaseStringT<char>(&v102, v85, v86);
    }
    **(_DWORD **)&v106.Data1 = v61;
    goto LABEL_191;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != CurrentMediaType )
      CallStackContext::TraceFailure(v23, "CAVIStreamSink::WriteStreamHeader", 1085, CurrentMediaType);
  }
  if ( g_wppLevels )
  {
    v15 = 184;
    goto LABEL_12;
  }
LABEL_191:
  if ( v101 )
  {
    v87 = v7->lpVtbl;
    v106 = v4;
    ((void (__fastcall *)(struct IMFMediaType *, GUID *))v87->FreeRepresentation)(v7, &v106);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v93);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v99);
  return (unsigned int)CurrentMediaType;
}

```

## disassembly

```asm
0x1800b9a74  mov     rax, rsp
0x1800b9a77  mov     [rax+18h], rbx
0x1800b9a7b  push    rbp
0x1800b9a7c  push    rsi
0x1800b9a7d  push    rdi
0x1800b9a7e  push    r12
0x1800b9a80  push    r13
0x1800b9a82  push    r14
0x1800b9a84  push    r15
0x1800b9a86  lea     rbp, [rax-5Fh]
0x1800b9a8a  sub     rsp, 0D0h
0x1800b9a91  movaps  xmmword ptr [rax-48h], xmm6
0x1800b9a95  mov     rax, cs:__security_cookie
0x1800b9a9c  xor     rax, rsp
0x1800b9a9f  mov     [rbp+57h+var_50], rax
0x1800b9aa3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800b9aaa  mov     rax, r9
0x1800b9aad  mov     dword ptr [rbp+57h+Size+4], r8d
0x1800b9ab1  movups  xmm6, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x1800b9ab8  neg     rax
0x1800b9abb  mov     qword ptr [rbp+57h+var_70], r9
0x1800b9abf  mov     r15, rdx
0x1800b9ac2  mov     r14, rcx
0x1800b9ac5  sbb     esi, esi
0x1800b9ac7  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9ace  xor     r13d, r13d
0x1800b9ad1  lea     rcx, [rbp+57h+var_D0+4]; this
0x1800b9ad5  mov     ebx, r13d
0x1800b9ad8  mov     [rbp+57h+var_90], r13
0x1800b9adc  not     esi
0x1800b9ade  mov     [rbp+57h+var_B0], rbx
0x1800b9ae2  mov     r8d, 43Bh; int
0x1800b9ae8  mov     [rbp+57h+var_B8], r13d
0x1800b9aec  mov     rdi, r9
0x1800b9aef  mov     dword ptr [rbp+57h+var_D0], r13d
0x1800b9af3  and     esi, 80004003h
0x1800b9af9  mov     [rbp+57h+var_B4], r13d
0x1800b9afd  mov     r12d, r13d
0x1800b9b00  movdqu  [rbp+57h+Buf1], xmm0
0x1800b9b05  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b9b0a  test    rdi, rdi
0x1800b9b0d  jnz     loc_1800B9BC0
0x1800b9b13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9b1a  test    rcx, rcx
0x1800b9b1d  jnz     short loc_1800B9B60
0x1800b9b1f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9b25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9b2c  mov     rcx, rax
0x1800b9b2f  test    rax, rax
0x1800b9b32  jz      short loc_1800B9B52
0x1800b9b34  mov     rax, [rax]
0x1800b9b37  mov     edx, 7F0h
0x1800b9b3c  mov     rax, [rax+8]
0x1800b9b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9b45  test    eax, eax
0x1800b9b47  jz      short loc_1800B9B52
0x1800b9b49  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9b50  jmp     short loc_1800B9B60
0x1800b9b52  lea     rcx, qword_1801B07E0; this
0x1800b9b59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9b60  cmp     [rcx+8], r13b
0x1800b9b64  jz      short loc_1800B9B8B
0x1800b9b66  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9b6b  cmp     [rax+7CCh], esi
0x1800b9b71  jz      short loc_1800B9B8B
0x1800b9b73  mov     r9d, esi; int
0x1800b9b76  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9b7d  mov     r8d, 43Bh; int
0x1800b9b83  mov     rcx, rax; this
0x1800b9b86  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9b8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9b92  jb      loc_1800BA7B3
0x1800b9b98  mov     edx, 0B6h
0x1800b9b9d  mov     [rsp+100h+var_E0], esi
0x1800b9ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ba8  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800b9baf  mov     r9, r14
0x1800b9bb2  mov     rcx, [rcx+10h]
0x1800b9bb6  call    WPP_SF_qD
0x1800b9bbb  jmp     loc_1800BA7B3
0x1800b9bc0  lea     rcx, [r14+20h]; this
0x1800b9bc4  lea     rdx, [rbp+57h+var_B0]; struct IMFMediaType **
0x1800b9bc8  call    ?GetCurrentMediaType@CBaseStreamSink@@UEAAJPEAPEAUIMFMediaType@@@Z; CBaseStreamSink::GetCurrentMediaType(IMFMediaType * *)
0x1800b9bcd  mov     esi, eax
0x1800b9bcf  test    eax, eax
0x1800b9bd1  jns     loc_1800B9C84
0x1800b9bd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9bde  test    rcx, rcx
0x1800b9be1  jnz     short loc_1800B9C24
0x1800b9be3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9be9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9bf0  mov     rcx, rax
0x1800b9bf3  test    rax, rax
0x1800b9bf6  jz      short loc_1800B9C16
0x1800b9bf8  mov     rax, [rax]
0x1800b9bfb  mov     edx, 7F0h
0x1800b9c00  mov     rax, [rax+8]
0x1800b9c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c09  test    eax, eax
0x1800b9c0b  jz      short loc_1800B9C16
0x1800b9c0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9c14  jmp     short loc_1800B9C24
0x1800b9c16  lea     rcx, qword_1801B07E0; this
0x1800b9c1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9c24  cmp     [rcx+8], r13b
0x1800b9c28  jz      short loc_1800B9C4F
0x1800b9c2a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9c2f  cmp     [rax+7CCh], esi
0x1800b9c35  jz      short loc_1800B9C4F
0x1800b9c37  mov     r9d, esi; int
0x1800b9c3a  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9c41  mov     r8d, 43Ch; int
0x1800b9c47  mov     rcx, rax; this
0x1800b9c4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9c4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9c56  jb      short loc_1800B9C7B
0x1800b9c58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c5f  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800b9c66  mov     edx, 0B7h
0x1800b9c6b  mov     [rsp+100h+var_E0], esi
0x1800b9c6f  mov     r9, r14
0x1800b9c72  mov     rcx, [rcx+10h]
0x1800b9c76  call    WPP_SF_qD
0x1800b9c7b  mov     rbx, [rbp+57h+var_B0]
0x1800b9c7f  jmp     loc_1800BA7B3
0x1800b9c84  mov     rbx, [rbp+57h+var_B0]
0x1800b9c88  lea     rdx, [rbp+57h+Buf1]
0x1800b9c8c  mov     rcx, rbx
0x1800b9c8f  mov     rax, [rbx]
0x1800b9c92  mov     rax, [rax+108h]
0x1800b9c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c9e  mov     esi, eax
0x1800b9ca0  test    eax, eax
0x1800b9ca2  jns     loc_1800B9D37
0x1800b9ca8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9caf  test    rcx, rcx
0x1800b9cb2  jnz     short loc_1800B9CF5
0x1800b9cb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9cba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9cc1  mov     rcx, rax
0x1800b9cc4  test    rax, rax
0x1800b9cc7  jz      short loc_1800B9CE7
0x1800b9cc9  mov     rax, [rax]
0x1800b9ccc  mov     edx, 7F0h
0x1800b9cd1  mov     rax, [rax+8]
0x1800b9cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9cda  test    eax, eax
0x1800b9cdc  jz      short loc_1800B9CE7
0x1800b9cde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9ce5  jmp     short loc_1800B9CF5
0x1800b9ce7  lea     rcx, qword_1801B07E0; this
0x1800b9cee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9cf5  cmp     [rcx+8], r13b
0x1800b9cf9  jz      short loc_1800B9D20
0x1800b9cfb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9d00  cmp     [rax+7CCh], esi
0x1800b9d06  jz      short loc_1800B9D20
0x1800b9d08  mov     r9d, esi; int
0x1800b9d0b  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9d12  mov     r8d, 43Dh; int
0x1800b9d18  mov     rcx, rax; this
0x1800b9d1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9d20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9d27  jb      loc_1800BA7B3
0x1800b9d2d  mov     edx, 0B8h
0x1800b9d32  jmp     loc_1800B9B9D
0x1800b9d37  mov     edi, 10h
0x1800b9d3c  lea     rdx, MFMediaType_Video; Buf2
0x1800b9d43  mov     r8d, edi; Size
0x1800b9d46  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b9d4a  call    memcmp_0
0x1800b9d4f  test    eax, eax
0x1800b9d51  jnz     short loc_1800B9D5A
0x1800b9d53  movups  xmm6, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x1800b9d5a  mov     rax, [rbx]
0x1800b9d5d  lea     r8, [rbp+57h+var_90]
0x1800b9d61  lea     rdx, [rbp+57h+pv]
0x1800b9d65  movdqa  xmmword ptr [rbp+57h+pv], xmm6
0x1800b9d6a  mov     rcx, rbx
0x1800b9d6d  mov     rax, [rax+120h]
0x1800b9d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d79  mov     esi, eax
0x1800b9d7b  test    eax, eax
0x1800b9d7d  jns     loc_1800B9E12
0x1800b9d83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9d8a  test    rcx, rcx
0x1800b9d8d  jnz     short loc_1800B9DD0
0x1800b9d8f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9d95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9d9c  mov     rcx, rax
0x1800b9d9f  test    rax, rax
0x1800b9da2  jz      short loc_1800B9DC2
0x1800b9da4  mov     rax, [rax]
0x1800b9da7  mov     edx, 7F0h
0x1800b9dac  mov     rax, [rax+8]
0x1800b9db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9db5  test    eax, eax
0x1800b9db7  jz      short loc_1800B9DC2
0x1800b9db9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9dc0  jmp     short loc_1800B9DD0
0x1800b9dc2  lea     rcx, qword_1801B07E0; this
0x1800b9dc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9dd0  cmp     [rcx+8], r13b
0x1800b9dd4  jz      short loc_1800B9DFB
0x1800b9dd6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9ddb  cmp     [rax+7CCh], esi
0x1800b9de1  jz      short loc_1800B9DFB
0x1800b9de3  mov     r9d, esi; int
0x1800b9de6  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9ded  mov     r8d, 443h; int
0x1800b9df3  mov     rcx, rax; this
0x1800b9df6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9dfb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9e02  jb      loc_1800BA7B3
0x1800b9e08  mov     edx, 0B9h
0x1800b9e0d  jmp     loc_1800B9B9D
0x1800b9e12  mov     r8, rdi; Size
0x1800b9e15  lea     rdx, MFMediaType_Video; Buf2
0x1800b9e1c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b9e20  call    memcmp_0
0x1800b9e25  test    eax, eax
0x1800b9e27  jnz     loc_1800B9F19
0x1800b9e2d  lea     rdx, [rbp+57h+pv]
0x1800b9e31  mov     dword ptr [rbp+57h+pv], r13d
0x1800b9e35  mov     rcx, rbx
0x1800b9e38  call    cs:__imp_MFIsBottomUpFormat
0x1800b9e3e  mov     esi, eax
0x1800b9e40  test    eax, eax
0x1800b9e42  jns     loc_1800B9ED7
0x1800b9e48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e4f  test    rcx, rcx
0x1800b9e52  jnz     short loc_1800B9E95
0x1800b9e54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9e5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e61  mov     rcx, rax
0x1800b9e64  test    rax, rax
0x1800b9e67  jz      short loc_1800B9E87
0x1800b9e69  mov     rax, [rax]
0x1800b9e6c  mov     edx, 7F0h
0x1800b9e71  mov     rax, [rax+8]
0x1800b9e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e7a  test    eax, eax
0x1800b9e7c  jz      short loc_1800B9E87
0x1800b9e7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e85  jmp     short loc_1800B9E95
0x1800b9e87  lea     rcx, qword_1801B07E0; this
0x1800b9e8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9e95  cmp     [rcx+8], r13b
0x1800b9e99  jz      short loc_1800B9EC0
0x1800b9e9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b9ea0  cmp     [rax+7CCh], esi
0x1800b9ea6  jz      short loc_1800B9EC0
0x1800b9ea8  mov     r9d, esi; int
0x1800b9eab  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800b9eb2  mov     r8d, 448h; int
0x1800b9eb8  mov     rcx, rax; this
0x1800b9ebb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9ec0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b9ec7  jb      loc_1800BA7B3
0x1800b9ecd  mov     edx, 0BAh
0x1800b9ed2  jmp     loc_1800B9B9D
0x1800b9ed7  mov     r8, [rbp+57h+var_90]
0x1800b9edb  mov     r13, [r8+50h]
0x1800b9edf  mov     edi, [r8+48h]
0x1800b9ee3  add     r13, 30h ; '0'
0x1800b9ee7  sub     edi, 30h ; '0'
0x1800b9eea  cmp     dword ptr [rbp+57h+pv], r12d
0x1800b9eee  jz      short loc_1800B9F25
0x1800b9ef0  xor     r8d, r8d
0x1800b9ef3  lea     rdx, MF_MT_DEFAULT_STRIDE
0x1800b9efa  mov     rcx, rbx
0x1800b9efd  call    MFGetAttributeUINT32
0x1800b9f02  test    eax, eax
0x1800b9f04  js      short loc_1800B9F25
0x1800b9f06  mov     eax, [r13+8]
0x1800b9f0a  neg     eax
0x1800b9f0c  cmovs   eax, [r13+8]
0x1800b9f11  neg     eax
0x1800b9f13  mov     [r13+8], eax
0x1800b9f17  jmp     short loc_1800B9F25
0x1800b9f19  mov     r8, [rbp+57h+var_90]
0x1800b9f1d  mov     r13, [r8+50h]
0x1800b9f21  mov     edi, [r8+48h]
0x1800b9f25  lea     eax, [rdi+8]
0x1800b9f28  lea     rcx, [rbp+57h+Src]
0x1800b9f2c  mov     dword ptr [rbp+57h+Src], eax
0x1800b9f2f  call    AVIHelpers__AlignUp
0x1800b9f34  mov     esi, eax
0x1800b9f36  test    eax, eax
0x1800b9f38  jns     loc_1800B9FD0
0x1800b9f3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9f45  xor     r13d, r13d
0x1800b9f48  test    rcx, rcx
0x1800b9f4b  jnz     short loc_1800B9F8E
0x1800b9f4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9f53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9f5a  mov     rcx, rax
0x1800b9f5d  test    rax, rax
0x1800b9f60  jz      short loc_1800B9F80
0x1800b9f62  mov     rax, [rax]
  ... truncated ...
```
