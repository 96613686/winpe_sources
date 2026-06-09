# ActivateClassicITA(IMFPMPHost *,ushort const *,IStream *,_GUID const &,void * *)

- ea: `0x180090288`
- end: `0x180090d51`
- name: `?ActivateClassicITA@@YAJPEAUIMFPMPHost@@PEBGPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `2761`
- prototype: `__int64 __fastcall(struct IMFPMPHost *, const unsigned __int16 *, struct IStream *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18010accc`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180090288`
- `0x180110a7c`
- `0x180110a94`
- `0x180110ed0`
- `0x180111960`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090323`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800903e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800904a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090629`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800906e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800907a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800909ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090aeb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090c62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090323`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800903e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800904a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090629`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800906e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800907a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800909ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090aeb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090c62`
- `MFPlat!MFSerializeAttributesToStream` at `0x180090834`
- `MFPlat!MFSerializeAttributesToStream` at `0x180090834`
- `MFPlat!MFCreateAttributes` at `0x180090301`
- `MFPlat!MFCreateAttributes` at `0x180090301`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800909cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800909cd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009077e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009077e`

## pseudocode

```c
__int64 __fastcall ActivateClassicITA(
        struct IMFPMPHost *a1,
        const unsigned __int16 *a2,
        struct IStream *a3,
        const struct _GUID *a4,
        void **a5)
{
  void *v9; // r13
  __int64 v10; // rdx
  HRESULT Instance; // ebx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  _BYTE v67[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v68; // [rsp+38h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v70; // [rsp+48h] [rbp-79h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv[3]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v73[16]; // [rsp+70h] [rbp-51h] BYREF
  size_t Size; // [rsp+80h] [rbp-41h]

  v70 = 0;
  v9 = 0;
  memset_0(v73, 0, 0x50u);
  ppv[0] = 0;
  ppMFAttributes = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v67, "ActivateClassicITA", 5337);
  Instance = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( Instance < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
        CallStackContext::TraceFailure(ThreadRelativeContext, "ActivateClassicITA", 5337, Instance);
    }
    if ( g_wppLevels )
    {
      v15 = 518;
LABEL_149:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
      goto LABEL_150;
    }
    goto LABEL_150;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
               ppMFAttributes,
               MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID,
               a2);
  if ( Instance >= 0 )
  {
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      v68 = 0;
      Instance = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))lpVtbl->Stat)(a3, v73, 3);
      if ( Instance < 0 )
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != Instance )
            CallStackContext::TraceFailure(v24, "ActivateClassicITA", 5344, Instance);
        }
        if ( g_wppLevels )
        {
          v15 = 520;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v9 = operator new((unsigned int)Size);
      if ( !v9 )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        Instance = -2147024882;
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
          if ( *((_DWORD *)v28 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v28, "ActivateClassicITA", 5348, -2147024882);
        }
        if ( g_wppLevels )
        {
          v15 = 521;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      ((void (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a3->lpVtbl->Seek)(a3, v68, 0, 0);
      Instance = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a3->lpVtbl->Read)(
                   a3,
                   v9,
                   (unsigned int)Size,
                   &v70);
      if ( Instance < 0 )
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
          if ( *((_DWORD *)v32 + 499) != Instance )
            CallStackContext::TraceFailure(v32, "ActivateClassicITA", 5351, Instance);
        }
        if ( g_wppLevels )
        {
          v15 = 522;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
                   ppMFAttributes,
                   MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA,
                   v9,
                   v70);
      if ( Instance < 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != Instance )
            CallStackContext::TraceFailure(v36, "ActivateClassicITA", 5352, Instance);
        }
        if ( g_wppLevels )
        {
          v15 = 523;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( Instance < 0 )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != Instance )
          CallStackContext::TraceFailure(v40, "ActivateClassicITA", 5356, Instance);
      }
      if ( g_wppLevels )
      {
        v15 = 524;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    Instance = MFSerializeAttributesToStream(ppMFAttributes, 0, ppstm);
    if ( Instance < 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != Instance )
          CallStackContext::TraceFailure(v44, "ActivateClassicITA", 5357, Instance);
      }
      if ( g_wppLevels )
      {
        v15 = 525;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    if ( a1 )
    {
      Instance = ((__int64 (__fastcall *)(struct IMFPMPHost *, const IID *, LPSTREAM, GUID *, LPVOID *))a1->lpVtbl->CreateObjectByCLSID)(
                   a1,
                   &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                   ppstm,
                   &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                   ppv);
      if ( Instance < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != Instance )
            CallStackContext::TraceFailure(v48, "ActivateClassicITA", 5363, Instance);
        }
        if ( g_wppLevels )
        {
          v15 = 526;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
LABEL_138:
      Instance = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, void **))(*(_QWORD *)ppv[0] + 264LL))(
                   ppv[0],
                   a4,
                   a5);
      if ( Instance < 0 )
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
          if ( *((_DWORD *)v65 + 499) != Instance )
            CallStackContext::TraceFailure(v65, "ActivateClassicITA", 5381, Instance);
        }
        if ( g_wppLevels )
        {
          v15 = 530;
          goto LABEL_149;
        }
      }
      goto LABEL_150;
    }
    v68 = 0;
    Instance = CoCreateInstance(
                 &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                 0,
                 1u,
                 &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                 ppv);
    if ( Instance >= 0 )
    {
      ppv[1] = 0;
      ((void (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv[0])(ppv[0], &IID_IPersistStream, &v68);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v68 + 40LL))(v68, ppstm);
        if ( Instance >= 0 )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v68);
          goto LABEL_138;
        }
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          {
            v59 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v59 + 8) )
        {
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
          if ( *((_DWORD *)v61 + 499) != Instance )
            CallStackContext::TraceFailure(v61, "ActivateClassicITA", 5377, Instance);
        }
        if ( !g_wppLevels )
        {
LABEL_114:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v68);
          goto LABEL_150;
        }
        v53 = 529;
      }
      else
      {
        v55 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          {
            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v55 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v55 + 8) )
        {
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v57 + 499) != Instance )
            CallStackContext::TraceFailure(v57, "ActivateClassicITA", 5376, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_114;
        v53 = 528;
      }
    }
    else
    {
      v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != Instance )
          CallStackContext::TraceFailure(v52, "ActivateClassicITA", 5369, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_114;
      v53 = 527;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
    goto LABEL_114;
  }
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
    if ( *((_DWORD *)v19 + 499) != Instance )
      CallStackContext::TraceFailure(v19, "ActivateClassicITA", 5338, Instance);
  }
  if ( g_wppLevels )
  {
    v15 = 519;
    goto LABEL_149;
  }
LABEL_150:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFAttributes);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180090288  push    rbp
0x18009028a  push    rbx
0x18009028b  push    rsi
0x18009028c  push    rdi
0x18009028d  push    r12
0x18009028f  push    r13
0x180090291  push    r14
0x180090293  push    r15
0x180090295  lea     rbp, [rsp-17h]
0x18009029a  sub     rsp, 0D8h
0x1800902a1  mov     rax, cs:__security_cookie
0x1800902a8  xor     rax, rsp
0x1800902ab  mov     [rbp+4Fh+var_50], rax
0x1800902af  mov     r12, [rbp+4Fh+arg_20]
0x1800902b3  xor     ebx, ebx
0x1800902b5  mov     rdi, r8
0x1800902b8  mov     [rbp+4Fh+var_C8], ebx
0x1800902bb  mov     r14, rdx
0x1800902be  mov     rsi, rcx
0x1800902c1  xor     edx, edx; Val
0x1800902c3  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1800902c7  lea     r8d, [rbx+50h]; Size
0x1800902cb  mov     r15, r9
0x1800902ce  mov     r13d, ebx
0x1800902d1  call    memset_0
0x1800902d6  mov     r8d, 14D9h; int
0x1800902dc  mov     [rbp+4Fh+var_B8], rbx
0x1800902e0  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x1800902e7  mov     [rbp+4Fh+ppMFAttributes], rbx
0x1800902eb  lea     rcx, [rsp+110h+var_E0]; this
0x1800902f0  mov     [rsp+110h+ppstm], rbx
0x1800902f5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800902fa  lea     edx, [rbx+3]; cInitialSize
0x1800902fd  lea     rcx, [rbp+4Fh+ppMFAttributes]; ppMFAttributes
0x180090301  call    cs:__imp_MFCreateAttributes
0x180090308  nop     dword ptr [rax+rax+00h]
0x18009030d  mov     ebx, eax
0x18009030f  test    eax, eax
0x180090311  jns     loc_1800903AC
0x180090317  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009031e  test    rcx, rcx
0x180090321  jnz     short loc_18009036A
0x180090323  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009032a  nop     dword ptr [rax+rax+00h]
0x18009032f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180090336  mov     rcx, rax
0x180090339  test    rax, rax
0x18009033c  jz      short loc_18009035C
0x18009033e  mov     rax, [rax]
0x180090341  mov     edx, 7F0h
0x180090346  mov     rax, [rax+8]
0x18009034a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009034f  test    eax, eax
0x180090351  jz      short loc_18009035C
0x180090353  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009035a  jmp     short loc_18009036A
0x18009035c  lea     rcx, qword_1801B97E0; this
0x180090363  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009036a  cmp     [rcx+8], r13b
0x18009036e  jz      short loc_180090395
0x180090370  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180090375  cmp     [rax+7CCh], ebx
0x18009037b  jz      short loc_180090395
0x18009037d  mov     r9d, ebx; int
0x180090380  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x180090387  mov     r8d, 14D9h; int
0x18009038d  mov     rcx, rax; this
0x180090390  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180090395  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009039c  jb      loc_180090D00
0x1800903a2  mov     edx, 206h
0x1800903a7  jmp     loc_180090CE2
0x1800903ac  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x1800903b0  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID
0x1800903b7  mov     r8, r14
0x1800903ba  mov     rax, [rcx]
0x1800903bd  mov     rax, [rax+0C8h]
0x1800903c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903c9  xor     r14d, r14d
0x1800903cc  mov     ebx, eax
0x1800903ce  test    eax, eax
0x1800903d0  jns     loc_18009046B
0x1800903d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800903dd  test    rcx, rcx
0x1800903e0  jnz     short loc_180090429
0x1800903e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800903e9  nop     dword ptr [rax+rax+00h]
0x1800903ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800903f5  mov     rcx, rax
0x1800903f8  test    rax, rax
0x1800903fb  jz      short loc_18009041B
0x1800903fd  mov     rax, [rax]
0x180090400  mov     edx, 7F0h
0x180090405  mov     rax, [rax+8]
0x180090409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009040e  test    eax, eax
0x180090410  jz      short loc_18009041B
0x180090412  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090419  jmp     short loc_180090429
0x18009041b  lea     rcx, qword_1801B97E0; this
0x180090422  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180090429  cmp     [rcx+8], r14b
0x18009042d  jz      short loc_180090454
0x18009042f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180090434  cmp     [rax+7CCh], ebx
0x18009043a  jz      short loc_180090454
0x18009043c  mov     r9d, ebx; int
0x18009043f  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x180090446  mov     r8d, 14DAh; int
0x18009044c  mov     rcx, rax; this
0x18009044f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180090454  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009045b  jb      loc_180090D00
0x180090461  mov     edx, 207h
0x180090466  jmp     loc_180090CE2
0x18009046b  test    rdi, rdi
0x18009046e  jz      loc_180090772
0x180090474  mov     rax, [rdi]
0x180090477  lea     rdx, [rbp+4Fh+var_A0]
0x18009047b  mov     r8d, 3
0x180090481  mov     [rsp+110h+var_D8], r14
0x180090486  mov     rcx, rdi
0x180090489  mov     rax, [rax+60h]
0x18009048d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090492  mov     ebx, eax
0x180090494  test    eax, eax
0x180090496  jns     loc_180090531
0x18009049c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800904a3  test    rcx, rcx
0x1800904a6  jnz     short loc_1800904EF
0x1800904a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800904af  nop     dword ptr [rax+rax+00h]
0x1800904b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800904bb  mov     rcx, rax
0x1800904be  test    rax, rax
0x1800904c1  jz      short loc_1800904E1
0x1800904c3  mov     rax, [rax]
0x1800904c6  mov     edx, 7F0h
0x1800904cb  mov     rax, [rax+8]
0x1800904cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904d4  test    eax, eax
0x1800904d6  jz      short loc_1800904E1
0x1800904d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800904df  jmp     short loc_1800904EF
0x1800904e1  lea     rcx, qword_1801B97E0; this
0x1800904e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800904ef  cmp     [rcx+8], r14b
0x1800904f3  jz      short loc_18009051A
0x1800904f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800904fa  cmp     [rax+7CCh], ebx
0x180090500  jz      short loc_18009051A
0x180090502  mov     r9d, ebx; int
0x180090505  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18009050c  mov     r8d, 14E0h; int
0x180090512  mov     rcx, rax; this
0x180090515  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009051a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180090521  jb      loc_180090D00
0x180090527  mov     edx, 208h
0x18009052c  jmp     loc_180090CE2
0x180090531  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x180090534  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090539  mov     r13, rax
0x18009053c  test    rax, rax
0x18009053f  jnz     loc_1800905DF
0x180090545  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009054c  mov     ebx, 8007000Eh
0x180090551  test    rcx, rcx
0x180090554  jnz     short loc_18009059D
0x180090556  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009055d  nop     dword ptr [rax+rax+00h]
0x180090562  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180090569  mov     rcx, rax
0x18009056c  test    rax, rax
0x18009056f  jz      short loc_18009058F
0x180090571  mov     rax, [rax]
0x180090574  mov     edx, 7F0h
0x180090579  mov     rax, [rax+8]
0x18009057d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090582  test    eax, eax
0x180090584  jz      short loc_18009058F
0x180090586  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009058d  jmp     short loc_18009059D
0x18009058f  lea     rcx, qword_1801B97E0; this
0x180090596  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009059d  cmp     [rcx+8], r14b
0x1800905a1  jz      short loc_1800905C8
0x1800905a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800905a8  cmp     [rax+7CCh], ebx
0x1800905ae  jz      short loc_1800905C8
0x1800905b0  mov     r9d, ebx; int
0x1800905b3  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x1800905ba  mov     r8d, 14E4h; int
0x1800905c0  mov     rcx, rax; this
0x1800905c3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800905c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800905cf  jb      loc_180090D00
0x1800905d5  mov     edx, 209h
0x1800905da  jmp     loc_180090CE2
0x1800905df  mov     rax, [rdi]
0x1800905e2  xor     r9d, r9d
0x1800905e5  mov     rdx, [rsp+110h+var_D8]
0x1800905ea  xor     r8d, r8d
0x1800905ed  mov     rcx, rdi
0x1800905f0  mov     rax, [rax+28h]
0x1800905f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905f9  mov     rax, [rdi]
0x1800905fc  lea     r9, [rbp+4Fh+var_C8]
0x180090600  mov     r8d, dword ptr [rbp+4Fh+Size]
0x180090604  mov     rdx, r13
0x180090607  mov     rcx, rdi
0x18009060a  mov     rax, [rax+18h]
0x18009060e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090613  mov     ebx, eax
0x180090615  test    eax, eax
0x180090617  jns     loc_1800906B2
0x18009061d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090624  test    rcx, rcx
0x180090627  jnz     short loc_180090670
0x180090629  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180090630  nop     dword ptr [rax+rax+00h]
0x180090635  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009063c  mov     rcx, rax
0x18009063f  test    rax, rax
0x180090642  jz      short loc_180090662
0x180090644  mov     rax, [rax]
0x180090647  mov     edx, 7F0h
0x18009064c  mov     rax, [rax+8]
0x180090650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090655  test    eax, eax
0x180090657  jz      short loc_180090662
0x180090659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090660  jmp     short loc_180090670
0x180090662  lea     rcx, qword_1801B97E0; this
0x180090669  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180090670  cmp     [rcx+8], r14b
0x180090674  jz      short loc_18009069B
0x180090676  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009067b  cmp     [rax+7CCh], ebx
0x180090681  jz      short loc_18009069B
0x180090683  mov     r9d, ebx; int
0x180090686  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18009068d  mov     r8d, 14E7h; int
0x180090693  mov     rcx, rax; this
0x180090696  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009069b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800906a2  jb      loc_180090D00
0x1800906a8  mov     edx, 20Ah
0x1800906ad  jmp     loc_180090CE2
0x1800906b2  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x1800906b6  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA
0x1800906bd  mov     r9d, [rbp+4Fh+var_C8]
0x1800906c1  mov     r8, r13
0x1800906c4  mov     rax, [rcx]
0x1800906c7  mov     rax, [rax+0D0h]
0x1800906ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906d3  mov     ebx, eax
0x1800906d5  test    eax, eax
0x1800906d7  jns     loc_180090772
0x1800906dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800906e4  test    rcx, rcx
0x1800906e7  jnz     short loc_180090730
0x1800906e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800906f0  nop     dword ptr [rax+rax+00h]
0x1800906f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800906fc  mov     rcx, rax
0x1800906ff  test    rax, rax
0x180090702  jz      short loc_180090722
0x180090704  mov     rax, [rax]
0x180090707  mov     edx, 7F0h
0x18009070c  mov     rax, [rax+8]
0x180090710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090715  test    eax, eax
0x180090717  jz      short loc_180090722
0x180090719  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090720  jmp     short loc_180090730
0x180090722  lea     rcx, qword_1801B97E0; this
0x180090729  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180090730  cmp     [rcx+8], r14b
0x180090734  jz      short loc_18009075B
0x180090736  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009073b  cmp     [rax+7CCh], ebx
0x180090741  jz      short loc_18009075B
0x180090743  mov     r9d, ebx; int
0x180090746  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18009074d  mov     r8d, 14E8h; int
0x180090753  mov     rcx, rax; this
0x180090756  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009075b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180090762  jb      loc_180090D00
0x180090768  mov     edx, 20Bh
0x18009076d  jmp     loc_180090CE2
0x180090772  lea     r8, [rsp+110h+ppstm]; ppstm
0x180090777  mov     edx, 1; fDeleteOnRelease
0x18009077c  xor     ecx, ecx; hGlobal
0x18009077e  call    cs:__imp_CreateStreamOnHGlobal
0x180090785  nop     dword ptr [rax+rax+00h]
0x18009078a  mov     ebx, eax
0x18009078c  test    eax, eax
0x18009078e  jns     loc_180090829
  ... truncated ...
```
