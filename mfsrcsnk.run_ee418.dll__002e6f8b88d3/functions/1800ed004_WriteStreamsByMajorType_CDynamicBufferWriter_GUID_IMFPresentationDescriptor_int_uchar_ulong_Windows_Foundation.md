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
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rcx
  int v17; // ebx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 (__fastcall ***v43)(_QWORD, unsigned int *, __int64); // rdi
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rbx
  __int64 (__fastcall *v62)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  wchar_t *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  wchar_t *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  wchar_t *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  wchar_t *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  wchar_t *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  __int64 v100; // [rsp+20h] [rbp-E0h]
  _BYTE v101[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v102; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v103; // [rsp+40h] [rbp-C0h] BYREF
  int v104; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v105; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v106; // [rsp+58h] [rbp-A8h] BYREF
  int v107; // [rsp+5Ch] [rbp-A4h] BYREF
  const void *v108; // [rsp+60h] [rbp-A0h]
  __int64 v109; // [rsp+68h] [rbp-98h]
  __int128 Buf1; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v111[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v8 = 0;
  v9 = a7;
  v11 = a8;
  v12 = a2;
  v108 = a2;
  v109 = a1;
  v106 = 0;
  v107 = 0;
  v104 = 0;
  Buf1 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v101, "WriteStreamsByMajorType", 5097);
  if ( a5 )
  {
    if ( a3 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a3 + 264))(a3, &v106);
      if ( v17 >= 0 )
      {
        while ( 1 )
        {
          if ( v8 >= v106 )
            goto LABEL_169;
          v30 = *a3;
          v102 = 0;
          v103 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, __int64 *))(v30 + 272))(a3, v8, &v107, &v102);
          if ( v17 < 0 )
            break;
          if ( !v102 )
          {
            v93 = (wchar_t *)CallStackTracing::s_wpInstance;
            v17 = -1072875845;
            if ( !CallStackTracing::s_wpInstance )
            {
              v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
              CallStackTracing::s_wpInstance = v94;
              if ( v94
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
              {
                v93 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v93 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v93 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
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
          if ( (unsigned int)MFGetAttributeUINT32(v102, &MF_SD_PROTECTED, 0) )
          {
            v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v102 + 264LL))(v102, &v104);
            if ( v17 < 0 )
            {
              v90 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
                CallStackTracing::s_wpInstance = v91;
                if ( v91
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
                {
                  v90 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v90 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v90 + 8) )
              {
                v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
                if ( *((_DWORD *)v92 + 499) != v17 )
                  CallStackContext::TraceFailure(v92, "WriteStreamsByMajorType", 5115, v17);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v67 = 485;
              goto LABEL_167;
            }
            v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v102 + 272LL))(v102, &v103);
            if ( v17 < 0 )
            {
              v87 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
                CallStackTracing::s_wpInstance = v88;
                if ( v88
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
                {
                  v87 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v87 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v87 + 8) )
              {
                v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
                if ( *((_DWORD *)v89 + 499) != v17 )
                  CallStackContext::TraceFailure(v89, "WriteStreamsByMajorType", 5117, v17);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v67 = 486;
              goto LABEL_167;
            }
            v17 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v103 + 64LL))(v103, &Buf1);
            if ( v17 < 0 )
            {
              v84 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                CallStackTracing::s_wpInstance = v85;
                if ( v85
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
                {
                  v84 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v84 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v84 + 8) )
              {
                v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
                if ( *((_DWORD *)v86 + 499) != v17 )
                  CallStackContext::TraceFailure(v86, "WriteStreamsByMajorType", 5119, v17);
              }
              if ( !g_wppLevels )
                goto LABEL_168;
              v67 = 487;
              goto LABEL_167;
            }
            if ( !memcmp_0(&Buf1, v12, 0x10u) )
            {
              v43 = (__int64 (__fastcall ***)(_QWORD, unsigned int *, __int64))(v109 + 520);
              v17 = (**(__int64 (__fastcall ***)(__int64, int *, __int64))(v109 + 520))(v109 + 520, &v104, 4);
              if ( v17 < 0 )
              {
                v81 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
                  CallStackTracing::s_wpInstance = v82;
                  if ( v82
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
                  {
                    v81 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v81 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v81 + 8) )
                {
                  v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
                  if ( *((_DWORD *)v83 + 499) != v17 )
                    CallStackContext::TraceFailure(v83, "WriteStreamsByMajorType", 5122, v17);
                }
                if ( !g_wppLevels )
                  goto LABEL_168;
                v67 = 488;
                goto LABEL_167;
              }
              v17 = (**v43)(v43, &a6, 4);
              if ( v17 < 0 )
              {
                v78 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
                  CallStackTracing::s_wpInstance = v79;
                  if ( v79
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
                  {
                    v78 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v78 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v78 + 8) )
                {
                  v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
                  if ( *((_DWORD *)v80 + 499) != v17 )
                    CallStackContext::TraceFailure(v80, "WriteStreamsByMajorType", 5123, v17);
                }
                if ( !g_wppLevels )
                  goto LABEL_168;
                v67 = 489;
                goto LABEL_167;
              }
              if ( a6 )
              {
                v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, unsigned int *, __int64), __int64))**v43)(
                        v43,
                        a5);
                if ( v17 < 0 )
                {
                  v53 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
                    CallStackTracing::s_wpInstance = v54;
                    if ( v54
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
                    {
                      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v53 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v53 + 8) )
                  {
                    v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                    if ( *((_DWORD *)v66 + 499) != v17 )
                      CallStackContext::TraceFailure(v66, "WriteStreamsByMajorType", 5126, v17);
                  }
                  if ( g_wppLevels )
                  {
                    v67 = 490;
                    goto LABEL_167;
                  }
LABEL_168:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v103);
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
                  goto LABEL_169;
                }
              }
              if ( v9 && v11 )
              {
                LODWORD(v100) = v104;
                v105 = 0;
                v101[0] = 0;
                if ( swprintf_s(Buffer, 0x104u, L"%s%d", L"StreamData.", v100) < 0 )
                {
                  v75 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v17 = -2147467259;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
                    CallStackTracing::s_wpInstance = v76;
                    if ( v76
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
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
                    if ( *((_DWORD *)v77 + 499) != -2147467259 )
                      CallStackContext::TraceFailure(v77, "WriteStreamsByMajorType", 5137, -2147467259);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_76;
                  v71 = 491;
LABEL_75:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v71,
                    &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                    0,
                    v17);
                  goto LABEL_76;
                }
                v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v9 + 208LL))(
                        v9,
                        a6,
                        a5,
                        &v105);
                if ( v17 < 0 )
                {
                  v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
                    CallStackTracing::s_wpInstance = v73;
                    if ( v73
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
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
                    if ( *((_DWORD *)v74 + 499) != v17 )
                      CallStackContext::TraceFailure(v74, "WriteStreamsByMajorType", 5139, v17);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_76;
                  v71 = 492;
                  goto LABEL_75;
                }
                v61 = v105;
                v62 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v11 + 80LL);
                Windows::Internal::StringReference::_ConstructorHelper(
                  (Windows::Internal::StringReference *)v111,
                  Buffer);
                v17 = v62(v11, v111[0], v61, v101);
                if ( v17 < 0 )
                {
                  v68 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
                    CallStackTracing::s_wpInstance = v69;
                    if ( v69
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
                    {
                      v68 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v68 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v68 + 8) )
                  {
                    v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                    if ( *((_DWORD *)v70 + 499) != v17 )
                      CallStackContext::TraceFailure(v70, "WriteStreamsByMajorType", 5140, v17);
                  }
                  if ( g_wppLevels )
                  {
                    v71 = 493;
                    goto LABEL_75;
                  }
LABEL_76:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v105);
                  goto LABEL_168;
                }
                ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v105);
              }
              v12 = v108;
            }
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v103);
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
          ++v8;
        }
        v96 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v97;
          if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
          {
            v96 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v96 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v96 + 8) )
        {
          v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
          if ( *((_DWORD *)v98 + 499) != v17 )
            CallStackContext::TraceFailure(v98, "WriteStreamsByMajorType", 5107, v17);
        }
        if ( !g_wppLevels )
          goto LABEL_168;
        v67 = 483;
LABEL_167:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v67, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, v17);
        goto LABEL_168;
      }
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != v17 )
          CallStackContext::TraceFailure(v29, "WriteStreamsByMajorType", 5100, v17);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, v17);
    }
    else
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      v17 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
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
        if ( *((_DWORD *)v23 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v23, "WriteStreamsByMajorType", 5098, -1072875845);
      }
      if ( g_wppLevels )
      {
        v20 = 481;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    v17 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v19 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v19, "WriteStreamsByMajorType", 5097, -1072875845);
    }
    if ( g_wppLevels )
    {
      v20 = 480;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        0,
        -1072875845);
    }
  }
LABEL_169:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
  return (unsigned int)v17;
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
