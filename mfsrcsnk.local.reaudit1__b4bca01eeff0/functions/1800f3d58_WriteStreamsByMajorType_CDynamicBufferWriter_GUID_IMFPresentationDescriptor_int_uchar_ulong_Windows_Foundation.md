# WriteStreamsByMajorType(CDynamicBufferWriter *,_GUID,IMFPresentationDescriptor *,int,uchar *,ulong,Windows::Foundation::IPropertyValueStatics *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x1800f3d58`
- end: `0x1800f493e`
- name: `?WriteStreamsByMajorType@@YAJPEAVCDynamicBufferWriter@@U_GUID@@PEAUIMFPresentationDescriptor@@HPEAEKPEAUIPropertyValueStatics@Foundation@Windows@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@56@@Z`
- size: `3046`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18009bdd8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18005a094`
- `0x180079680`
- `0x1800f3d58`
- `0x180110ed0`
- `0x1801119c0`
- `0x18014f6bc`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3eb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3f6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f416f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f42e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f439d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4437`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f44cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f45f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f468b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4720`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f47bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4855`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3eb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3f6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f416f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f42e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f439d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4437`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f44cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f45f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f468b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4720`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f47bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4855`

## string_xrefs

- `0x1800f3db2`: `WriteStreamsByMajorType`
- `0x1800f3e53`: `WriteStreamsByMajorType`
- `0x1800f3f16`: `WriteStreamsByMajorType`
- `0x1800f3fcc`: `WriteStreamsByMajorType`
- `0x1800f42ac`: `WriteStreamsByMajorType`
- `0x1800f4341`: `WriteStreamsByMajorType`
- `0x1800f43fa`: `WriteStreamsByMajorType`
- `0x1800f4494`: `WriteStreamsByMajorType`
- `0x1800f4529`: `WriteStreamsByMajorType`
- `0x1800f45be`: `WriteStreamsByMajorType`
- `0x1800f4653`: `WriteStreamsByMajorType`
- `0x1800f46e8`: `WriteStreamsByMajorType`
- `0x1800f477d`: `WriteStreamsByMajorType`
- `0x1800f4819`: `WriteStreamsByMajorType`
- `0x1800f48b2`: `WriteStreamsByMajorType`

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
                v69 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v66 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v63 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v60 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v57 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v54 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v35 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v51 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v48 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v44 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v72 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v23 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v19 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800f3d58  mov     [rsp-8+arg_8], rbx
0x1800f3d5d  push    rbp
0x1800f3d5e  push    rsi
0x1800f3d5f  push    rdi
0x1800f3d60  push    r12
0x1800f3d62  push    r13
0x1800f3d64  push    r14
0x1800f3d66  push    r15
0x1800f3d68  lea     rbp, [rsp-1C0h]
0x1800f3d70  sub     rsp, 2C0h
0x1800f3d77  mov     rax, cs:__security_cookie
0x1800f3d7e  xor     rax, rsp
0x1800f3d81  mov     [rbp+1F0h+var_40], rax
0x1800f3d88  mov     r12, [rbp+1F0h+arg_20]
0x1800f3d8f  xor     esi, esi
0x1800f3d91  mov     r15, [rbp+1F0h+arg_30]
0x1800f3d98  mov     r14, r8
0x1800f3d9b  mov     r13, [rbp+1F0h+arg_38]
0x1800f3da2  mov     rdi, rdx
0x1800f3da5  mov     [rsp+2F0h+var_290], rdx
0x1800f3daa  xorps   xmm0, xmm0
0x1800f3dad  mov     [rsp+2F0h+var_288], rcx
0x1800f3db2  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800f3db9  mov     r8d, 13E9h; int
0x1800f3dbf  mov     [rsp+2F0h+var_298], esi
0x1800f3dc3  lea     rcx, [rsp+2F0h+var_2C0]; this
0x1800f3dc8  mov     [rsp+2F0h+var_294], esi
0x1800f3dcc  mov     [rsp+2F0h+var_2A8], esi
0x1800f3dd0  movups  [rsp+2F0h+Buf1], xmm0
0x1800f3dd5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f3dda  test    r12, r12
0x1800f3ddd  jnz     loc_1800F3E9D
0x1800f3de3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3dea  mov     edi, 0C00D36BBh
0x1800f3def  mov     ebx, edi
0x1800f3df1  test    rcx, rcx
0x1800f3df4  jnz     short loc_1800F3E3D
0x1800f3df6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3dfd  nop     dword ptr [rax+rax+00h]
0x1800f3e02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3e09  mov     rcx, rax
0x1800f3e0c  test    rax, rax
0x1800f3e0f  jz      short loc_1800F3E2F
0x1800f3e11  mov     rax, [rax]
0x1800f3e14  mov     edx, 7F0h
0x1800f3e19  mov     rax, [rax+8]
0x1800f3e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3e22  test    eax, eax
0x1800f3e24  jz      short loc_1800F3E2F
0x1800f3e26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3e2d  jmp     short loc_1800F3E3D
0x1800f3e2f  lea     rcx, qword_1801B97E0; this
0x1800f3e36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3e3d  cmp     [rcx+8], sil
0x1800f3e41  jz      short loc_1800F3E68
0x1800f3e43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f3e48  cmp     [rax+7CCh], edi
0x1800f3e4e  jz      short loc_1800F3E68
0x1800f3e50  mov     r9d, edi; int
0x1800f3e53  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800f3e5a  mov     r8d, 13E9h; int
0x1800f3e60  mov     rcx, rax; this
0x1800f3e63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f3e68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f3e6f  jb      loc_1800F4907
0x1800f3e75  mov     edx, 1E0h
0x1800f3e7a  mov     [rsp+2F0h+var_2D0], edi
0x1800f3e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3e85  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800f3e8c  xor     r9d, r9d
0x1800f3e8f  mov     rcx, [rcx+10h]
0x1800f3e93  call    WPP_SF_qD
0x1800f3e98  jmp     loc_1800F4907
0x1800f3e9d  test    r14, r14
0x1800f3ea0  jnz     loc_1800F3F42
0x1800f3ea6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3ead  mov     edi, 0C00D36BBh
0x1800f3eb2  mov     ebx, edi
0x1800f3eb4  test    rcx, rcx
0x1800f3eb7  jnz     short loc_1800F3F00
0x1800f3eb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3ec0  nop     dword ptr [rax+rax+00h]
0x1800f3ec5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3ecc  mov     rcx, rax
0x1800f3ecf  test    rax, rax
0x1800f3ed2  jz      short loc_1800F3EF2
0x1800f3ed4  mov     rax, [rax]
0x1800f3ed7  mov     edx, 7F0h
0x1800f3edc  mov     rax, [rax+8]
0x1800f3ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3ee5  test    eax, eax
0x1800f3ee7  jz      short loc_1800F3EF2
0x1800f3ee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3ef0  jmp     short loc_1800F3F00
0x1800f3ef2  lea     rcx, qword_1801B97E0; this
0x1800f3ef9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3f00  cmp     [rcx+8], sil
0x1800f3f04  jz      short loc_1800F3F2B
0x1800f3f06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f3f0b  cmp     [rax+7CCh], edi
0x1800f3f11  jz      short loc_1800F3F2B
0x1800f3f13  mov     r9d, edi; int
0x1800f3f16  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800f3f1d  mov     r8d, 13EAh; int
0x1800f3f23  mov     rcx, rax; this
0x1800f3f26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f3f2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f3f32  jb      loc_1800F4907
0x1800f3f38  mov     edx, 1E1h
0x1800f3f3d  jmp     loc_1800F3E7A
0x1800f3f42  mov     rax, [r14]
0x1800f3f45  lea     rdx, [rsp+2F0h+var_298]
0x1800f3f4a  mov     rcx, r14
0x1800f3f4d  mov     rax, [rax+108h]
0x1800f3f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3f59  mov     ebx, eax
0x1800f3f5b  test    eax, eax
0x1800f3f5d  jns     loc_1800F3FFC
0x1800f3f63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3f6a  test    rcx, rcx
0x1800f3f6d  jnz     short loc_1800F3FB6
0x1800f3f6f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3f76  nop     dword ptr [rax+rax+00h]
0x1800f3f7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3f82  mov     rcx, rax
0x1800f3f85  test    rax, rax
0x1800f3f88  jz      short loc_1800F3FA8
0x1800f3f8a  mov     rax, [rax]
0x1800f3f8d  mov     edx, 7F0h
0x1800f3f92  mov     rax, [rax+8]
0x1800f3f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3f9b  test    eax, eax
0x1800f3f9d  jz      short loc_1800F3FA8
0x1800f3f9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3fa6  jmp     short loc_1800F3FB6
0x1800f3fa8  lea     rcx, qword_1801B97E0; this
0x1800f3faf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3fb6  cmp     [rcx+8], sil
0x1800f3fba  jz      short loc_1800F3FE1
0x1800f3fbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f3fc1  cmp     [rax+7CCh], ebx
0x1800f3fc7  jz      short loc_1800F3FE1
0x1800f3fc9  mov     r9d, ebx; int
0x1800f3fcc  lea     rdx, aWritestreamsby; "WriteStreamsByMajorType"
0x1800f3fd3  mov     r8d, 13ECh; int
0x1800f3fd9  mov     rcx, rax; this
0x1800f3fdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f3fe1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f3fe8  jb      loc_1800F4907
0x1800f3fee  mov     edx, 1E2h
0x1800f3ff3  mov     [rsp+2F0h+var_2D0], ebx
0x1800f3ff7  jmp     loc_1800F3E7E
0x1800f3ffc  cmp     esi, [rsp+2F0h+var_298]
0x1800f4000  jnb     loc_1800F4907
0x1800f4006  mov     rax, [r14]
0x1800f4009  lea     r9, [rsp+2F0h+var_2B8]
0x1800f400e  lea     r8, [rsp+2F0h+var_294]
0x1800f4013  mov     [rsp+2F0h+var_2B8], 0
0x1800f401c  mov     edx, esi
0x1800f401e  mov     [rsp+2F0h+var_2B0], 0
0x1800f4027  mov     rcx, r14
0x1800f402a  mov     rax, [rax+110h]
0x1800f4031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4036  mov     ebx, eax
0x1800f4038  test    eax, eax
0x1800f403a  js      loc_1800F4849
0x1800f4040  mov     rcx, [rsp+2F0h+var_2B8]
0x1800f4045  test    rcx, rcx
0x1800f4048  jz      loc_1800F47A9
0x1800f404e  xor     r8d, r8d
0x1800f4051  lea     rdx, MF_SD_PROTECTED
0x1800f4058  call    MFGetAttributeUINT32
0x1800f405d  test    eax, eax
0x1800f405f  jz      loc_1800F426D
0x1800f4065  mov     rcx, [rsp+2F0h+var_2B8]
0x1800f406a  lea     rdx, [rsp+2F0h+var_2A8]
0x1800f406f  mov     rax, [rcx]
0x1800f4072  mov     rax, [rax+108h]
0x1800f4079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f407e  mov     ebx, eax
0x1800f4080  test    eax, eax
0x1800f4082  js      loc_1800F4714
0x1800f4088  mov     rcx, [rsp+2F0h+var_2B8]
0x1800f408d  lea     rdx, [rsp+2F0h+var_2B0]
0x1800f4092  mov     rax, [rcx]
0x1800f4095  mov     rax, [rax+110h]
0x1800f409c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f40a1  mov     ebx, eax
0x1800f40a3  test    eax, eax
0x1800f40a5  js      loc_1800F467F
0x1800f40ab  mov     rcx, [rsp+2F0h+var_2B0]
0x1800f40b0  lea     rdx, [rsp+2F0h+Buf1]
0x1800f40b5  mov     rax, [rcx]
0x1800f40b8  mov     rax, [rax+40h]
0x1800f40bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f40c1  mov     ebx, eax
0x1800f40c3  test    eax, eax
0x1800f40c5  js      loc_1800F45EA
0x1800f40cb  mov     r8d, 10h; Size
0x1800f40d1  lea     rcx, [rsp+2F0h+Buf1]; Buf1
0x1800f40d6  mov     rdx, rdi; Buf2
0x1800f40d9  call    memcmp_0
0x1800f40de  test    eax, eax
0x1800f40e0  jnz     loc_1800F426D
0x1800f40e6  mov     rdi, [rsp+2F0h+var_288]
0x1800f40eb  lea     rdx, [rsp+2F0h+var_2A8]
0x1800f40f0  add     rdi, 208h
0x1800f40f7  mov     r8d, 4
0x1800f40fd  mov     rcx, rdi
0x1800f4100  mov     rax, [rdi]
0x1800f4103  mov     rax, [rax]
0x1800f4106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f410b  mov     ebx, eax
0x1800f410d  test    eax, eax
0x1800f410f  js      loc_1800F4555
0x1800f4115  mov     rax, [rdi]
0x1800f4118  lea     rdx, [rbp+1F0h+arg_28]
0x1800f411f  mov     r8d, 4
0x1800f4125  mov     rcx, rdi
0x1800f4128  mov     rax, [rax]
0x1800f412b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4130  mov     ebx, eax
0x1800f4132  test    eax, eax
0x1800f4134  js      loc_1800F44C0
0x1800f413a  mov     r8d, [rbp+1F0h+arg_28]
0x1800f4141  test    r8d, r8d
0x1800f4144  jz      short loc_1800F41B3
0x1800f4146  mov     rax, [rdi]
0x1800f4149  mov     rdx, r12
0x1800f414c  mov     rcx, rdi
0x1800f414f  mov     rax, [rax]
0x1800f4152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4157  xor     edi, edi
0x1800f4159  mov     ebx, eax
0x1800f415b  test    eax, eax
0x1800f415d  jns     short loc_1800F41B5
0x1800f415f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f4166  test    rcx, rcx
0x1800f4169  jnz     loc_1800F4296
0x1800f416f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f4176  nop     dword ptr [rax+rax+00h]
0x1800f417b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f4182  mov     rcx, rax
0x1800f4185  test    rax, rax
0x1800f4188  jz      loc_1800F4288
0x1800f418e  mov     rax, [rax]
0x1800f4191  mov     edx, 7F0h
0x1800f4196  mov     rax, [rax+8]
0x1800f419a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f419f  test    eax, eax
0x1800f41a1  jz      loc_1800F4288
0x1800f41a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f41ae  jmp     loc_1800F4296
0x1800f41b3  xor     edi, edi
0x1800f41b5  test    r15, r15
0x1800f41b8  jz      loc_1800F4268
0x1800f41be  test    r13, r13
0x1800f41c1  jz      loc_1800F4268
0x1800f41c7  mov     eax, [rsp+2F0h+var_2A8]
0x1800f41cb  lea     r9, aStreamdata; "StreamData."
0x1800f41d2  lea     r8, aSD; "%s%d"
0x1800f41d9  mov     [rsp+2F0h+var_2D0], eax
0x1800f41dd  mov     edx, 104h; BufferCount
0x1800f41e2  mov     [rsp+2F0h+var_2A0], rdi
0x1800f41e7  lea     rcx, [rbp+1F0h+Buffer]; Buffer
0x1800f41eb  mov     [rsp+2F0h+var_2C0], dil
0x1800f41f0  call    swprintf_s
0x1800f41f5  test    eax, eax
0x1800f41f7  js      loc_1800F4426
0x1800f41fd  mov     rax, [r15]
0x1800f4200  lea     r9, [rsp+2F0h+var_2A0]
0x1800f4205  mov     edx, [rbp+1F0h+arg_28]
0x1800f420b  mov     r8, r12
0x1800f420e  mov     rcx, r15
0x1800f4211  mov     rax, [rax+0D0h]
0x1800f4218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f421d  mov     ebx, eax
0x1800f421f  test    eax, eax
0x1800f4221  js      loc_1800F4391
0x1800f4227  mov     rax, [r13+0]
0x1800f422b  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x1800f422f  mov     rbx, [rsp+2F0h+var_2A0]
0x1800f4234  lea     rcx, [rbp+1F0h+var_270]; this
0x1800f4238  mov     rdi, [rax+50h]
0x1800f423c  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800f4241  mov     rdx, [rbp+1F0h+var_270]
0x1800f4245  lea     r9, [rsp+2F0h+var_2C0]
0x1800f424a  mov     r8, rbx
0x1800f424d  mov     rcx, r13
0x1800f4250  mov     rax, rdi
0x1800f4253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4258  mov     ebx, eax
0x1800f425a  test    eax, eax
0x1800f425c  js      short loc_1800F42D8
0x1800f425e  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x1800f4263  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f4268  mov     rdi, [rsp+2F0h+var_290]
0x1800f426d  lea     rcx, [rsp+2F0h+var_2B0]; void *
0x1800f4272  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f4277  lea     rcx, [rsp+2F0h+var_2B8]; void *
  ... truncated ...
```
