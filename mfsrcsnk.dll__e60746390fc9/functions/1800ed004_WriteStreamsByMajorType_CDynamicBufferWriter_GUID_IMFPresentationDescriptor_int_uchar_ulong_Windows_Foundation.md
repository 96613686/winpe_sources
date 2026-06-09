# WriteStreamsByMajorType(CDynamicBufferWriter *,_GUID,IMFPresentationDescriptor *,int,uchar *,ulong,Windows::Foundation::IPropertyValueStatics *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x1800ed004`
- end: `0x1800edb95`
- name: `?WriteStreamsByMajorType@@YAJPEAVCDynamicBufferWriter@@U_GUID@@PEAUIMFPresentationDescriptor@@HPEAEKPEAUIPropertyValueStatics@Foundation@Windows@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@56@@Z`
- size: `2961`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180096930`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180056e38`
- `0x180073b14`
- `0x1800ed004`
- `0x1801099f0`
- `0x18010a4b0`
- `0x18014758c`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed0a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed15f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed20f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed409`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed578`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed62b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed6bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed74e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed7dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed86c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed98a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eda20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800edab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed0a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed15f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed20f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed409`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed578`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed62b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed6bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed74e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed7dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed86c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ed98a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eda20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800edab3`

## string_xrefs

- `0x1800ed05e`: `WriteStreamsByMajorType`
- `0x1800ed0f9`: `WriteStreamsByMajorType`
- `0x1800ed1b6`: `WriteStreamsByMajorType`
- `0x1800ed266`: `WriteStreamsByMajorType`
- `0x1800ed540`: `WriteStreamsByMajorType`
- `0x1800ed5cf`: `WriteStreamsByMajorType`
- `0x1800ed682`: `WriteStreamsByMajorType`
- `0x1800ed716`: `WriteStreamsByMajorType`
- `0x1800ed7a5`: `WriteStreamsByMajorType`
- `0x1800ed834`: `WriteStreamsByMajorType`
- `0x1800ed8c3`: `WriteStreamsByMajorType`
- `0x1800ed952`: `WriteStreamsByMajorType`
- `0x1800ed9e1`: `WriteStreamsByMajorType`
- `0x1800eda77`: `WriteStreamsByMajorType`
- `0x1800edb0a`: `WriteStreamsByMajorType`

## pseudocode

```c
__int64 __fastcall WriteStreamsByMajorType(
        __int64 a1,
        const void *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8)
{
  unsigned int v8; // esi
  __int64 v9; // r15
  __int64 v11; // r13
  const void *v12; // rdi
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  int v15; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(_QWORD, unsigned int *, __int64); // rdi
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v41; // rdx
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
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
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v76; // [rsp+20h] [rbp-E0h]
  _BYTE v77[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v78; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v79; // [rsp+40h] [rbp-C0h] BYREF
  int v80; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+5Ch] [rbp-A4h] BYREF
  const void *v84; // [rsp+60h] [rbp-A0h]
  __int64 v85; // [rsp+68h] [rbp-98h]
  __int128 Buf1; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v87[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v8 = 0;
  v9 = a7;
  v11 = a8;
  v12 = a2;
  v84 = a2;
  v85 = a1;
  v82 = 0;
  v83 = 0;
  v80 = 0;
  Buf1 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v77, "WriteStreamsByMajorType", 5097);
  if ( a5 )
  {
    if ( a3 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a3 + 264))(a3, &v82);
      if ( v15 >= 0 )
      {
        while ( 1 )
        {
          if ( v8 >= v82 )
            goto LABEL_169;
          v26 = *a3;
          v78 = 0;
          v79 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, __int64 *))(v26 + 272))(a3, v8, &v83, &v78);
          if ( v15 < 0 )
            break;
          if ( !v78 )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
            v15 = -1072875845;
            if ( !CallStackTracing::s_wpInstance )
            {
              v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v70;
              if ( v70
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "WriteStreamsByMajorType", 5108, -1072875845);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                484,
                &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                0,
                -1072875845);
            goto LABEL_168;
          }
          if ( (unsigned int)MFGetAttributeUINT32(v78, &MF_SD_PROTECTED, 0) )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 264LL))(v78, &v80);
            if ( v15 < 0 )
            {
              v66 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
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
                if ( *((_DWORD *)v68 + 499) != v15 )
                  CallStackContext::TraceFailure(v68, "WriteStreamsByMajorType", 5115, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v43 = 485;
              goto LABEL_167;
            }
            v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 272LL))(v78, &v79);
            if ( v15 < 0 )
            {
              v63 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                CallStackTracing::s_wpInstance = v64;
                if ( v64
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
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
                if ( *((_DWORD *)v65 + 499) != v15 )
                  CallStackContext::TraceFailure(v65, "WriteStreamsByMajorType", 5117, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v43 = 486;
              goto LABEL_167;
            }
            v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v79 + 64LL))(v79, &Buf1);
            if ( v15 < 0 )
            {
              v60 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
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
                if ( *((_DWORD *)v62 + 499) != v15 )
                  CallStackContext::TraceFailure(v62, "WriteStreamsByMajorType", 5119, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v43 = 487;
              goto LABEL_167;
            }
            if ( !memcmp_0(&Buf1, v12, 0x10u) )
            {
              v31 = (__int64 (__fastcall ***)(_QWORD, unsigned int *, __int64))(v85 + 520);
              v15 = (**(__int64 (__fastcall ***)(__int64, int *, __int64))(v85 + 520))(v85 + 520, &v80, 4);
              if ( v15 < 0 )
              {
                v57 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
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
                  if ( *((_DWORD *)v59 + 499) != v15 )
                    CallStackContext::TraceFailure(v59, "WriteStreamsByMajorType", 5122, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_168;
                v43 = 488;
                goto LABEL_167;
              }
              v15 = (**v31)(v31, &a6, 4);
              if ( v15 < 0 )
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
                  if ( *((_DWORD *)v56 + 499) != v15 )
                    CallStackContext::TraceFailure(v56, "WriteStreamsByMajorType", 5123, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_168;
                v43 = 489;
                goto LABEL_167;
              }
              if ( a6 )
              {
                v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, unsigned int *, __int64), __int64))**v31)(
                        v31,
                        a5);
                if ( v15 < 0 )
                {
                  v35 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
                    CallStackTracing::s_wpInstance = v36;
                    if ( v36
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                    {
                      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v35 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v35 + 8) )
                  {
                    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                    if ( *((_DWORD *)v42 + 499) != v15 )
                      CallStackContext::TraceFailure(v42, "WriteStreamsByMajorType", 5126, v15);
                  }
                  if ( g_wppLevels )
                  {
                    v43 = 490;
                    goto LABEL_167;
                  }
LABEL_168:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v79);
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v78);
                  goto LABEL_169;
                }
              }
              if ( v9 && v11 )
              {
                LODWORD(v76) = v80;
                v81 = 0;
                v77[0] = 0;
                if ( swprintf_s(Buffer, 0x104u, L"%s%d", L"StreamData.", v76) < 0 )
                {
                  v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v15 = -2147467259;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
                    if ( *((_DWORD *)v53 + 499) != -2147467259 )
                      CallStackContext::TraceFailure(v53, "WriteStreamsByMajorType", 5137, -2147467259);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_76;
                  v47 = 491;
LABEL_75:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v47,
                    &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                    0,
                    v15);
                  goto LABEL_76;
                }
                v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v9 + 208LL))(
                        v9,
                        a6,
                        a5,
                        &v81);
                if ( v15 < 0 )
                {
                  v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
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
                    if ( *((_DWORD *)v50 + 499) != v15 )
                      CallStackContext::TraceFailure(v50, "WriteStreamsByMajorType", 5139, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_76;
                  v47 = 492;
                  goto LABEL_75;
                }
                v39 = v81;
                v40 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v11 + 80LL);
                Windows::Internal::StringReference::_ConstructorHelper(
                  (Windows::Internal::StringReference *)v87,
                  Buffer);
                v15 = v40(v11, v87[0], v39, v77);
                if ( v15 < 0 )
                {
                  v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
                    CallStackTracing::s_wpInstance = v45;
                    if ( v45
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
                    if ( *((_DWORD *)v46 + 499) != v15 )
                      CallStackContext::TraceFailure(v46, "WriteStreamsByMajorType", 5140, v15);
                  }
                  if ( g_wppLevels )
                  {
                    v47 = 493;
                    goto LABEL_75;
                  }
LABEL_76:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v81);
                  goto LABEL_168;
                }
                ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v81);
              }
              v12 = v84;
            }
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v79);
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v78);
          ++v8;
        }
        v72 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
        if ( *((_BYTE *)v72 + 8) )
        {
          v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
          if ( *((_DWORD *)v74 + 499) != v15 )
            CallStackContext::TraceFailure(v74, "WriteStreamsByMajorType", 5107, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_168;
        v43 = 483;
LABEL_167:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, v15);
        goto LABEL_168;
      }
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v15 )
          CallStackContext::TraceFailure(v25, "WriteStreamsByMajorType", 5100, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, v15);
    }
    else
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      v15 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v21, "WriteStreamsByMajorType", 5098, -1072875845);
      }
      if ( g_wppLevels )
      {
        v18 = 481;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    v15 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v17 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v17, "WriteStreamsByMajorType", 5097, -1072875845);
    }
    if ( g_wppLevels )
    {
      v18 = 480;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        0,
        -1072875845);
    }
  }
LABEL_169:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v77);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800ed004  mov     [rsp-8+arg_8], rbx
0x1800ed009  push    rbp
0x1800ed00a  push    rsi
0x1800ed00b  push    rdi
0x1800ed00c  push    r12
0x1800ed00e  push    r13
0x1800ed010  push    r14
0x1800ed012  push    r15
0x1800ed014  lea     rbp, [rsp-1C0h]
0x1800ed01c  sub     rsp, 2C0h
0x1800ed023  mov     rax, cs:__security_cookie
0x1800ed02a  xor     rax, rsp
0x1800ed02d  mov     [rbp+1F0h+var_40], rax
0x1800ed034  mov     r12, [rbp+1F0h+arg_20]
0x1800ed03b  xor     esi, esi
0x1800ed03d  mov     r15, [rbp+1F0h+arg_30]
0x1800ed044  mov     r14, r8
0x1800ed047  mov     r13, [rbp+1F0h+arg_38]
0x1800ed04e  mov     rdi, rdx
0x1800ed051  mov     [rsp+2F0h+var_290], rdx
0x1800ed056  xorps   xmm0, xmm0
0x1800ed059  mov     [rsp+2F0h+var_288], rcx
0x1800ed05e  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800ed065  mov     r8d, 13E9h; int
0x1800ed06b  mov     [rsp+2F0h+var_298], esi
0x1800ed06f  lea     rcx, [rsp+2F0h+var_2C0]; this
0x1800ed074  mov     [rsp+2F0h+var_294], esi
0x1800ed078  mov     [rsp+2F0h+var_2A8], esi
0x1800ed07c  movups  [rsp+2F0h+Buf1], xmm0
0x1800ed081  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ed086  test    r12, r12
0x1800ed089  jnz     loc_1800ED143
0x1800ed08f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed096  mov     edi, 0C00D36BBh
0x1800ed09b  mov     ebx, edi
0x1800ed09d  test    rcx, rcx
0x1800ed0a0  jnz     short loc_1800ED0E3
0x1800ed0a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed0a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed0af  mov     rcx, rax
0x1800ed0b2  test    rax, rax
0x1800ed0b5  jz      short loc_1800ED0D5
0x1800ed0b7  mov     rax, [rax]
0x1800ed0ba  mov     edx, 7F0h
0x1800ed0bf  mov     rax, [rax+8]
0x1800ed0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed0c8  test    eax, eax
0x1800ed0ca  jz      short loc_1800ED0D5
0x1800ed0cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed0d3  jmp     short loc_1800ED0E3
0x1800ed0d5  lea     rcx, qword_1801B07E0; this
0x1800ed0dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed0e3  cmp     [rcx+8], sil
0x1800ed0e7  jz      short loc_1800ED10E
0x1800ed0e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed0ee  cmp     [rax+7CCh], edi
0x1800ed0f4  jz      short loc_1800ED10E
0x1800ed0f6  mov     r9d, edi; int
0x1800ed0f9  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800ed100  mov     r8d, 13E9h; int
0x1800ed106  mov     rcx, rax; this
0x1800ed109  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed10e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed115  jb      loc_1800EDB5F
0x1800ed11b  mov     edx, 1E0h
0x1800ed120  mov     [rsp+2F0h+var_2D0], edi
0x1800ed124  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed12b  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800ed132  xor     r9d, r9d
0x1800ed135  mov     rcx, [rcx+10h]
0x1800ed139  call    WPP_SF_qD
0x1800ed13e  jmp     loc_1800EDB5F
0x1800ed143  test    r14, r14
0x1800ed146  jnz     loc_1800ED1E2
0x1800ed14c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed153  mov     edi, 0C00D36BBh
0x1800ed158  mov     ebx, edi
0x1800ed15a  test    rcx, rcx
0x1800ed15d  jnz     short loc_1800ED1A0
0x1800ed15f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed16c  mov     rcx, rax
0x1800ed16f  test    rax, rax
0x1800ed172  jz      short loc_1800ED192
0x1800ed174  mov     rax, [rax]
0x1800ed177  mov     edx, 7F0h
0x1800ed17c  mov     rax, [rax+8]
0x1800ed180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed185  test    eax, eax
0x1800ed187  jz      short loc_1800ED192
0x1800ed189  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed190  jmp     short loc_1800ED1A0
0x1800ed192  lea     rcx, qword_1801B07E0; this
0x1800ed199  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed1a0  cmp     [rcx+8], sil
0x1800ed1a4  jz      short loc_1800ED1CB
0x1800ed1a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed1ab  cmp     [rax+7CCh], edi
0x1800ed1b1  jz      short loc_1800ED1CB
0x1800ed1b3  mov     r9d, edi; int
0x1800ed1b6  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800ed1bd  mov     r8d, 13EAh; int
0x1800ed1c3  mov     rcx, rax; this
0x1800ed1c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed1cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed1d2  jb      loc_1800EDB5F
0x1800ed1d8  mov     edx, 1E1h
0x1800ed1dd  jmp     loc_1800ED120
0x1800ed1e2  mov     rax, [r14]
0x1800ed1e5  lea     rdx, [rsp+2F0h+var_298]
0x1800ed1ea  mov     rcx, r14
0x1800ed1ed  mov     rax, [rax+108h]
0x1800ed1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed1f9  mov     ebx, eax
0x1800ed1fb  test    eax, eax
0x1800ed1fd  jns     loc_1800ED296
0x1800ed203  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed20a  test    rcx, rcx
0x1800ed20d  jnz     short loc_1800ED250
0x1800ed20f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed215  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed21c  mov     rcx, rax
0x1800ed21f  test    rax, rax
0x1800ed222  jz      short loc_1800ED242
0x1800ed224  mov     rax, [rax]
0x1800ed227  mov     edx, 7F0h
0x1800ed22c  mov     rax, [rax+8]
0x1800ed230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed235  test    eax, eax
0x1800ed237  jz      short loc_1800ED242
0x1800ed239  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed240  jmp     short loc_1800ED250
0x1800ed242  lea     rcx, qword_1801B07E0; this
0x1800ed249  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed250  cmp     [rcx+8], sil
0x1800ed254  jz      short loc_1800ED27B
0x1800ed256  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed25b  cmp     [rax+7CCh], ebx
0x1800ed261  jz      short loc_1800ED27B
0x1800ed263  mov     r9d, ebx; int
0x1800ed266  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800ed26d  mov     r8d, 13ECh; int
0x1800ed273  mov     rcx, rax; this
0x1800ed276  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed27b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed282  jb      loc_1800EDB5F
0x1800ed288  mov     edx, 1E2h
0x1800ed28d  mov     [rsp+2F0h+var_2D0], ebx
0x1800ed291  jmp     loc_1800ED124
0x1800ed296  cmp     esi, [rsp+2F0h+var_298]
0x1800ed29a  jnb     loc_1800EDB5F
0x1800ed2a0  mov     rax, [r14]
0x1800ed2a3  lea     r9, [rsp+2F0h+var_2B8]
0x1800ed2a8  lea     r8, [rsp+2F0h+var_294]
0x1800ed2ad  mov     [rsp+2F0h+var_2B8], 0
0x1800ed2b6  mov     edx, esi
0x1800ed2b8  mov     [rsp+2F0h+var_2B0], 0
0x1800ed2c1  mov     rcx, r14
0x1800ed2c4  mov     rax, [rax+110h]
0x1800ed2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed2d0  mov     ebx, eax
0x1800ed2d2  test    eax, eax
0x1800ed2d4  js      loc_1800EDAA7
0x1800ed2da  mov     rcx, [rsp+2F0h+var_2B8]
0x1800ed2df  test    rcx, rcx
0x1800ed2e2  jz      loc_1800EDA0D
0x1800ed2e8  xor     r8d, r8d
0x1800ed2eb  lea     rdx, MF_SD_PROTECTED
0x1800ed2f2  call    MFGetAttributeUINT32
0x1800ed2f7  test    eax, eax
0x1800ed2f9  jz      loc_1800ED501
0x1800ed2ff  mov     rcx, [rsp+2F0h+var_2B8]
0x1800ed304  lea     rdx, [rsp+2F0h+var_2A8]
0x1800ed309  mov     rax, [rcx]
0x1800ed30c  mov     rax, [rax+108h]
0x1800ed313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed318  mov     ebx, eax
0x1800ed31a  test    eax, eax
0x1800ed31c  js      loc_1800ED97E
0x1800ed322  mov     rcx, [rsp+2F0h+var_2B8]
0x1800ed327  lea     rdx, [rsp+2F0h+var_2B0]
0x1800ed32c  mov     rax, [rcx]
0x1800ed32f  mov     rax, [rax+110h]
0x1800ed336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed33b  mov     ebx, eax
0x1800ed33d  test    eax, eax
0x1800ed33f  js      loc_1800ED8EF
0x1800ed345  mov     rcx, [rsp+2F0h+var_2B0]
0x1800ed34a  lea     rdx, [rsp+2F0h+Buf1]
0x1800ed34f  mov     rax, [rcx]
0x1800ed352  mov     rax, [rax+40h]
0x1800ed356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed35b  mov     ebx, eax
0x1800ed35d  test    eax, eax
0x1800ed35f  js      loc_1800ED860
0x1800ed365  mov     r8d, 10h; Size
0x1800ed36b  lea     rcx, [rsp+2F0h+Buf1]; Buf1
0x1800ed370  mov     rdx, rdi; Buf2
0x1800ed373  call    memcmp_0
0x1800ed378  test    eax, eax
0x1800ed37a  jnz     loc_1800ED501
0x1800ed380  mov     rdi, [rsp+2F0h+var_288]
0x1800ed385  lea     rdx, [rsp+2F0h+var_2A8]
0x1800ed38a  add     rdi, 208h
0x1800ed391  mov     r8d, 4
0x1800ed397  mov     rcx, rdi
0x1800ed39a  mov     rax, [rdi]
0x1800ed39d  mov     rax, [rax]
0x1800ed3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3a5  mov     ebx, eax
0x1800ed3a7  test    eax, eax
0x1800ed3a9  js      loc_1800ED7D1
0x1800ed3af  mov     rax, [rdi]
0x1800ed3b2  lea     rdx, [rbp+1F0h+arg_28]
0x1800ed3b9  mov     r8d, 4
0x1800ed3bf  mov     rcx, rdi
0x1800ed3c2  mov     rax, [rax]
0x1800ed3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3ca  mov     ebx, eax
0x1800ed3cc  test    eax, eax
0x1800ed3ce  js      loc_1800ED742
0x1800ed3d4  mov     r8d, [rbp+1F0h+arg_28]
0x1800ed3db  test    r8d, r8d
0x1800ed3de  jz      short loc_1800ED447
0x1800ed3e0  mov     rax, [rdi]
0x1800ed3e3  mov     rdx, r12
0x1800ed3e6  mov     rcx, rdi
0x1800ed3e9  mov     rax, [rax]
0x1800ed3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3f1  xor     edi, edi
0x1800ed3f3  mov     ebx, eax
0x1800ed3f5  test    eax, eax
0x1800ed3f7  jns     short loc_1800ED449
0x1800ed3f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed400  test    rcx, rcx
0x1800ed403  jnz     loc_1800ED52A
0x1800ed409  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ed40f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed416  mov     rcx, rax
0x1800ed419  test    rax, rax
0x1800ed41c  jz      loc_1800ED51C
0x1800ed422  mov     rax, [rax]
0x1800ed425  mov     edx, 7F0h
0x1800ed42a  mov     rax, [rax+8]
0x1800ed42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed433  test    eax, eax
0x1800ed435  jz      loc_1800ED51C
0x1800ed43b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed442  jmp     loc_1800ED52A
0x1800ed447  xor     edi, edi
0x1800ed449  test    r15, r15
0x1800ed44c  jz      loc_1800ED4FC
0x1800ed452  test    r13, r13
0x1800ed455  jz      loc_1800ED4FC
0x1800ed45b  mov     eax, [rsp+2F0h+var_2A8]
0x1800ed45f  lea     r9, aStreamdata; "StreamData."
0x1800ed466  lea     r8, aSD; "%s%d"
0x1800ed46d  mov     [rsp+2F0h+var_2D0], eax
0x1800ed471  mov     edx, 104h; BufferCount
0x1800ed476  mov     [rsp+2F0h+var_2A0], rdi
0x1800ed47b  lea     rcx, [rbp+1F0h+Buffer]; Buffer
0x1800ed47f  mov     [rsp+2F0h+var_2C0], dil
0x1800ed484  call    swprintf_s
0x1800ed489  test    eax, eax
0x1800ed48b  js      loc_1800ED6AE
0x1800ed491  mov     rax, [r15]
0x1800ed494  lea     r9, [rsp+2F0h+var_2A0]
0x1800ed499  mov     edx, [rbp+1F0h+arg_28]
0x1800ed49f  mov     r8, r12
0x1800ed4a2  mov     rcx, r15
0x1800ed4a5  mov     rax, [rax+0D0h]
0x1800ed4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed4b1  mov     ebx, eax
0x1800ed4b3  test    eax, eax
0x1800ed4b5  js      loc_1800ED61F
0x1800ed4bb  mov     rax, [r13+0]
0x1800ed4bf  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x1800ed4c3  mov     rbx, [rsp+2F0h+var_2A0]
0x1800ed4c8  lea     rcx, [rbp+1F0h+var_270]; this
0x1800ed4cc  mov     rdi, [rax+50h]
0x1800ed4d0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800ed4d5  mov     rdx, [rbp+1F0h+var_270]
0x1800ed4d9  lea     r9, [rsp+2F0h+var_2C0]
0x1800ed4de  mov     r8, rbx
0x1800ed4e1  mov     rcx, r13
0x1800ed4e4  mov     rax, rdi
0x1800ed4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed4ec  mov     ebx, eax
0x1800ed4ee  test    eax, eax
0x1800ed4f0  js      short loc_1800ED56C
0x1800ed4f2  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x1800ed4f7  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed4fc  mov     rdi, [rsp+2F0h+var_290]
0x1800ed501  lea     rcx, [rsp+2F0h+var_2B0]; void *
0x1800ed506  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed50b  lea     rcx, [rsp+2F0h+var_2B8]; void *
0x1800ed510  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed515  inc     esi
0x1800ed517  jmp     loc_1800ED296
0x1800ed51c  lea     rcx, qword_1801B07E0; this
  ... truncated ...
```
