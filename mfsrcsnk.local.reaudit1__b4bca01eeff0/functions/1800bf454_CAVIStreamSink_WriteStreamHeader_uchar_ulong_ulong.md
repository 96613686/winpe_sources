# CAVIStreamSink::WriteStreamHeader(uchar *,ulong,ulong *)

- ea: `0x1800bf454`
- end: `0x1800c0310`
- name: `?WriteStreamHeader@CAVIStreamSink@@QEAAJPEAEKPEAK@Z`
- size: `3772`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b1040`
- `0x1800bc17c`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18005a094`
- `0x180075838`
- `0x180079680`
- `0x1800bf454`
- `0x1800d70d0`
- `0x1800e6b94`
- `0x180110ed0`
- `0x180111960`
- `0x18012636c`
- `0x18012f8f0`
- `0x1801329cc`
- `0x18017b734`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf4ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf5c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf6a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf852`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf951`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfa27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfb03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfbc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfc7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfd37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfe76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bff1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c003f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c0126`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c0283`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf4ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf5c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf6a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf852`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bf951`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfa27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfb03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfbc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfc7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfd37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bfe76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bff1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c003f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c0126`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c0283`
- `MFPlat!MFIsBottomUpFormat` at `0x1800bf830`
- `MFPlat!MFIsBottomUpFormat` at `0x1800bf830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bffdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bffdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0102`

## string_xrefs

- `0x1800bf4a7`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf55c`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf626`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf6fd`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf7de`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf8af`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bf9ae`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfa84`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfb60`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfc20`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfcdc`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfd94`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bfed3`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800bff7c`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800c009c`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800c0183`: `CAVIStreamSink::WriteStreamHeader`
- `0x1800c02e0`: `CAVIStreamSink::WriteStreamHeader`

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
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v26 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v37 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v41 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v45 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v49 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v52 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v56 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v63 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v66 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v75 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v79 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v89 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v21 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800bf454  mov     rax, rsp
0x1800bf457  mov     [rax+18h], rbx
0x1800bf45b  push    rbp
0x1800bf45c  push    rsi
0x1800bf45d  push    rdi
0x1800bf45e  push    r12
0x1800bf460  push    r13
0x1800bf462  push    r14
0x1800bf464  push    r15
0x1800bf466  lea     rbp, [rax-5Fh]
0x1800bf46a  sub     rsp, 0D0h
0x1800bf471  movaps  xmmword ptr [rax-48h], xmm6
0x1800bf475  mov     rax, cs:__security_cookie
0x1800bf47c  xor     rax, rsp
0x1800bf47f  mov     [rbp+57h+var_50], rax
0x1800bf483  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bf48a  mov     rax, r9
0x1800bf48d  mov     dword ptr [rbp+57h+Size+4], r8d
0x1800bf491  movups  xmm6, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x1800bf498  neg     rax
0x1800bf49b  mov     qword ptr [rbp+57h+var_70], r9
0x1800bf49f  mov     r15, rdx
0x1800bf4a2  mov     r14, rcx
0x1800bf4a5  sbb     esi, esi
0x1800bf4a7  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf4ae  xor     r13d, r13d
0x1800bf4b1  lea     rcx, [rbp+57h+var_D0+4]; this
0x1800bf4b5  mov     ebx, r13d
0x1800bf4b8  mov     [rbp+57h+var_90], r13
0x1800bf4bc  not     esi
0x1800bf4be  mov     [rbp+57h+var_B0], rbx
0x1800bf4c2  mov     r8d, 43Bh; int
0x1800bf4c8  mov     [rbp+57h+var_B8], r13d
0x1800bf4cc  mov     rdi, r9
0x1800bf4cf  mov     dword ptr [rbp+57h+var_D0], r13d
0x1800bf4d3  and     esi, 80004003h
0x1800bf4d9  mov     [rbp+57h+var_B4], r13d
0x1800bf4dd  mov     r12d, r13d
0x1800bf4e0  movdqu  [rbp+57h+Buf1], xmm0
0x1800bf4e5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bf4ea  test    rdi, rdi
0x1800bf4ed  jnz     loc_1800BF5A6
0x1800bf4f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf4fa  test    rcx, rcx
0x1800bf4fd  jnz     short loc_1800BF546
0x1800bf4ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bf506  nop     dword ptr [rax+rax+00h]
0x1800bf50b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf512  mov     rcx, rax
0x1800bf515  test    rax, rax
0x1800bf518  jz      short loc_1800BF538
0x1800bf51a  mov     rax, [rax]
0x1800bf51d  mov     edx, 7F0h
0x1800bf522  mov     rax, [rax+8]
0x1800bf526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf52b  test    eax, eax
0x1800bf52d  jz      short loc_1800BF538
0x1800bf52f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf536  jmp     short loc_1800BF546
0x1800bf538  lea     rcx, qword_1801B97E0; this
0x1800bf53f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf546  cmp     [rcx+8], r13b
0x1800bf54a  jz      short loc_1800BF571
0x1800bf54c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bf551  cmp     [rax+7CCh], esi
0x1800bf557  jz      short loc_1800BF571
0x1800bf559  mov     r9d, esi; int
0x1800bf55c  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf563  mov     r8d, 43Bh; int
0x1800bf569  mov     rcx, rax; this
0x1800bf56c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bf571  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bf578  jb      loc_1800C01FF
0x1800bf57e  mov     edx, 0B6h
0x1800bf583  mov     [rsp+100h+var_E0], esi
0x1800bf587  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf58e  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800bf595  mov     r9, r14
0x1800bf598  mov     rcx, [rcx+10h]
0x1800bf59c  call    WPP_SF_qD
0x1800bf5a1  jmp     loc_1800C01FF
0x1800bf5a6  lea     rcx, [r14+20h]; this
0x1800bf5aa  lea     rdx, [rbp+57h+var_B0]; struct IMFMediaType **
0x1800bf5ae  call    ?GetCurrentMediaType@CBaseStreamSink@@UEAAJPEAPEAUIMFMediaType@@@Z; CBaseStreamSink::GetCurrentMediaType(IMFMediaType * *)
0x1800bf5b3  mov     esi, eax
0x1800bf5b5  test    eax, eax
0x1800bf5b7  jns     loc_1800BF670
0x1800bf5bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf5c4  test    rcx, rcx
0x1800bf5c7  jnz     short loc_1800BF610
0x1800bf5c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bf5d0  nop     dword ptr [rax+rax+00h]
0x1800bf5d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf5dc  mov     rcx, rax
0x1800bf5df  test    rax, rax
0x1800bf5e2  jz      short loc_1800BF602
0x1800bf5e4  mov     rax, [rax]
0x1800bf5e7  mov     edx, 7F0h
0x1800bf5ec  mov     rax, [rax+8]
0x1800bf5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5f5  test    eax, eax
0x1800bf5f7  jz      short loc_1800BF602
0x1800bf5f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf600  jmp     short loc_1800BF610
0x1800bf602  lea     rcx, qword_1801B97E0; this
0x1800bf609  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf610  cmp     [rcx+8], r13b
0x1800bf614  jz      short loc_1800BF63B
0x1800bf616  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bf61b  cmp     [rax+7CCh], esi
0x1800bf621  jz      short loc_1800BF63B
0x1800bf623  mov     r9d, esi; int
0x1800bf626  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf62d  mov     r8d, 43Ch; int
0x1800bf633  mov     rcx, rax; this
0x1800bf636  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bf63b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bf642  jb      short loc_1800BF667
0x1800bf644  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf64b  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800bf652  mov     edx, 0B7h
0x1800bf657  mov     [rsp+100h+var_E0], esi
0x1800bf65b  mov     r9, r14
0x1800bf65e  mov     rcx, [rcx+10h]
0x1800bf662  call    WPP_SF_qD
0x1800bf667  mov     rbx, [rbp+57h+var_B0]
0x1800bf66b  jmp     loc_1800C01FF
0x1800bf670  mov     rbx, [rbp+57h+var_B0]
0x1800bf674  lea     rdx, [rbp+57h+Buf1]
0x1800bf678  mov     rcx, rbx
0x1800bf67b  mov     rax, [rbx]
0x1800bf67e  mov     rax, [rax+108h]
0x1800bf685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf68a  mov     esi, eax
0x1800bf68c  test    eax, eax
0x1800bf68e  jns     loc_1800BF729
0x1800bf694  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf69b  test    rcx, rcx
0x1800bf69e  jnz     short loc_1800BF6E7
0x1800bf6a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bf6a7  nop     dword ptr [rax+rax+00h]
0x1800bf6ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf6b3  mov     rcx, rax
0x1800bf6b6  test    rax, rax
0x1800bf6b9  jz      short loc_1800BF6D9
0x1800bf6bb  mov     rax, [rax]
0x1800bf6be  mov     edx, 7F0h
0x1800bf6c3  mov     rax, [rax+8]
0x1800bf6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6cc  test    eax, eax
0x1800bf6ce  jz      short loc_1800BF6D9
0x1800bf6d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf6d7  jmp     short loc_1800BF6E7
0x1800bf6d9  lea     rcx, qword_1801B97E0; this
0x1800bf6e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf6e7  cmp     [rcx+8], r13b
0x1800bf6eb  jz      short loc_1800BF712
0x1800bf6ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bf6f2  cmp     [rax+7CCh], esi
0x1800bf6f8  jz      short loc_1800BF712
0x1800bf6fa  mov     r9d, esi; int
0x1800bf6fd  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf704  mov     r8d, 43Dh; int
0x1800bf70a  mov     rcx, rax; this
0x1800bf70d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bf712  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bf719  jb      loc_1800C01FF
0x1800bf71f  mov     edx, 0B8h
0x1800bf724  jmp     loc_1800BF583
0x1800bf729  mov     edi, 10h
0x1800bf72e  lea     rdx, MFMediaType_Video; Buf2
0x1800bf735  mov     r8d, edi; Size
0x1800bf738  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800bf73c  call    memcmp_0
0x1800bf741  test    eax, eax
0x1800bf743  jnz     short loc_1800BF74C
0x1800bf745  movups  xmm6, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x1800bf74c  mov     rax, [rbx]
0x1800bf74f  lea     r8, [rbp+57h+var_90]
0x1800bf753  lea     rdx, [rbp+57h+pv]
0x1800bf757  movdqa  xmmword ptr [rbp+57h+pv], xmm6
0x1800bf75c  mov     rcx, rbx
0x1800bf75f  mov     rax, [rax+120h]
0x1800bf766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf76b  mov     esi, eax
0x1800bf76d  test    eax, eax
0x1800bf76f  jns     loc_1800BF80A
0x1800bf775  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf77c  test    rcx, rcx
0x1800bf77f  jnz     short loc_1800BF7C8
0x1800bf781  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bf788  nop     dword ptr [rax+rax+00h]
0x1800bf78d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf794  mov     rcx, rax
0x1800bf797  test    rax, rax
0x1800bf79a  jz      short loc_1800BF7BA
0x1800bf79c  mov     rax, [rax]
0x1800bf79f  mov     edx, 7F0h
0x1800bf7a4  mov     rax, [rax+8]
0x1800bf7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf7ad  test    eax, eax
0x1800bf7af  jz      short loc_1800BF7BA
0x1800bf7b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf7b8  jmp     short loc_1800BF7C8
0x1800bf7ba  lea     rcx, qword_1801B97E0; this
0x1800bf7c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf7c8  cmp     [rcx+8], r13b
0x1800bf7cc  jz      short loc_1800BF7F3
0x1800bf7ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bf7d3  cmp     [rax+7CCh], esi
0x1800bf7d9  jz      short loc_1800BF7F3
0x1800bf7db  mov     r9d, esi; int
0x1800bf7de  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf7e5  mov     r8d, 443h; int
0x1800bf7eb  mov     rcx, rax; this
0x1800bf7ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bf7f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bf7fa  jb      loc_1800C01FF
0x1800bf800  mov     edx, 0B9h
0x1800bf805  jmp     loc_1800BF583
0x1800bf80a  mov     r8, rdi; Size
0x1800bf80d  lea     rdx, MFMediaType_Video; Buf2
0x1800bf814  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800bf818  call    memcmp_0
0x1800bf81d  test    eax, eax
0x1800bf81f  jnz     loc_1800BF91D
0x1800bf825  lea     rdx, [rbp+57h+pv]
0x1800bf829  mov     dword ptr [rbp+57h+pv], r13d
0x1800bf82d  mov     rcx, rbx
0x1800bf830  call    cs:__imp_MFIsBottomUpFormat
0x1800bf837  nop     dword ptr [rax+rax+00h]
0x1800bf83c  mov     esi, eax
0x1800bf83e  test    eax, eax
0x1800bf840  jns     loc_1800BF8DB
0x1800bf846  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf84d  test    rcx, rcx
0x1800bf850  jnz     short loc_1800BF899
0x1800bf852  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bf859  nop     dword ptr [rax+rax+00h]
0x1800bf85e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf865  mov     rcx, rax
0x1800bf868  test    rax, rax
0x1800bf86b  jz      short loc_1800BF88B
0x1800bf86d  mov     rax, [rax]
0x1800bf870  mov     edx, 7F0h
0x1800bf875  mov     rax, [rax+8]
0x1800bf879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf87e  test    eax, eax
0x1800bf880  jz      short loc_1800BF88B
0x1800bf882  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf889  jmp     short loc_1800BF899
0x1800bf88b  lea     rcx, qword_1801B97E0; this
0x1800bf892  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf899  cmp     [rcx+8], r13b
0x1800bf89d  jz      short loc_1800BF8C4
0x1800bf89f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bf8a4  cmp     [rax+7CCh], esi
0x1800bf8aa  jz      short loc_1800BF8C4
0x1800bf8ac  mov     r9d, esi; int
0x1800bf8af  lea     rdx, aCavistreamsink_24; "CAVIStreamSink::WriteStreamHeader"
0x1800bf8b6  mov     r8d, 448h; int
0x1800bf8bc  mov     rcx, rax; this
0x1800bf8bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bf8c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bf8cb  jb      loc_1800C01FF
0x1800bf8d1  mov     edx, 0BAh
0x1800bf8d6  jmp     loc_1800BF583
0x1800bf8db  mov     r8, [rbp+57h+var_90]
0x1800bf8df  mov     r13, [r8+50h]
0x1800bf8e3  mov     edi, [r8+48h]
0x1800bf8e7  add     r13, 30h ; '0'
0x1800bf8eb  sub     edi, 30h ; '0'
0x1800bf8ee  cmp     dword ptr [rbp+57h+pv], r12d
0x1800bf8f2  jz      short loc_1800BF929
0x1800bf8f4  xor     r8d, r8d
0x1800bf8f7  lea     rdx, MF_MT_DEFAULT_STRIDE
0x1800bf8fe  mov     rcx, rbx
0x1800bf901  call    MFGetAttributeUINT32
0x1800bf906  test    eax, eax
0x1800bf908  js      short loc_1800BF929
0x1800bf90a  mov     eax, [r13+8]
0x1800bf90e  neg     eax
0x1800bf910  cmovs   eax, [r13+8]
0x1800bf915  neg     eax
0x1800bf917  mov     [r13+8], eax
0x1800bf91b  jmp     short loc_1800BF929
0x1800bf91d  mov     r8, [rbp+57h+var_90]
0x1800bf921  mov     r13, [r8+50h]
0x1800bf925  mov     edi, [r8+48h]
0x1800bf929  lea     eax, [rdi+8]
0x1800bf92c  lea     rcx, [rbp+57h+Src]
0x1800bf930  mov     dword ptr [rbp+57h+Src], eax
0x1800bf933  call    AVIHelpers__AlignUp
0x1800bf938  mov     esi, eax
0x1800bf93a  test    eax, eax
0x1800bf93c  jns     loc_1800BF9DA
0x1800bf942  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bf949  xor     r13d, r13d
0x1800bf94c  test    rcx, rcx
0x1800bf94f  jnz     short loc_1800BF998
  ... truncated ...
```
