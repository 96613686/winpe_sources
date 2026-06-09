# ActivateClassicITA(IMFPMPHost *,ushort const *,IStream *,_GUID const &,void * *)

- ea: `0x18008b354`
- end: `0x18008bdb6`
- name: `?ActivateClassicITA@@YAJPEAUIMFPMPHost@@PEBGPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `2658`
- prototype: `__int64 __fastcall(struct IMFPMPHost *, const unsigned __int16 *, struct IStream *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180103ad4`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x18008b354`
- `0x180109590`
- `0x1801095a8`
- `0x1801099f0`
- `0x18010a450`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b3e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b4a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b562`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b60a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b6d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b791`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b83c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b8e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b9b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008ba6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bb63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bc12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bcce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b3e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b4a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b562`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b60a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b6d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b791`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b83c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b8e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008b9b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008ba6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bb63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bc12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bcce`
- `MFPlat!MFSerializeAttributesToStream` at `0x18008b8ca`
- `MFPlat!MFSerializeAttributesToStream` at `0x18008b8ca`
- `MFPlat!MFCreateAttributes` at `0x18008b3cd`
- `MFPlat!MFCreateAttributes` at `0x18008b3cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ba51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ba51`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18008b820`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18008b820`

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
  __int64 v12; // r8
  __int64 v13; // r9
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  wchar_t *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  wchar_t *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  _BYTE v93[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v94; // [rsp+38h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v96; // [rsp+48h] [rbp-79h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv[3]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v99[16]; // [rsp+70h] [rbp-51h] BYREF
  size_t Size; // [rsp+80h] [rbp-41h]

  v96 = 0;
  v9 = 0;
  memset_0(v99, 0, 0x50u);
  ppv[0] = 0;
  ppMFAttributes = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v93, "ActivateClassicITA", 5337);
  Instance = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( Instance < 0 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
        CallStackContext::TraceFailure(ThreadRelativeContext, "ActivateClassicITA", 5337, Instance);
    }
    if ( g_wppLevels )
    {
      v17 = 518;
LABEL_149:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
      goto LABEL_150;
    }
    goto LABEL_150;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, void *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
               ppMFAttributes,
               &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID,
               a2);
  if ( Instance >= 0 )
  {
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      v94 = 0;
      Instance = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))lpVtbl->Stat)(a3, v99, 3);
      if ( Instance < 0 )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != Instance )
            CallStackContext::TraceFailure(v30, "ActivateClassicITA", 5344, Instance);
        }
        if ( g_wppLevels )
        {
          v17 = 520;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v9 = operator new((unsigned int)Size);
      if ( !v9 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        Instance = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v36, "ActivateClassicITA", 5348, -2147024882);
        }
        if ( g_wppLevels )
        {
          v17 = 521;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      ((void (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a3->lpVtbl->Seek)(a3, v94, 0, 0);
      Instance = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a3->lpVtbl->Read)(
                   a3,
                   v9,
                   (unsigned int)Size,
                   &v96);
      if ( Instance < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != Instance )
            CallStackContext::TraceFailure(v42, "ActivateClassicITA", 5351, Instance);
        }
        if ( g_wppLevels )
        {
          v17 = 522;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      Instance = ((__int64 (__fastcall *)(IMFAttributes *, void *, void *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
                   ppMFAttributes,
                   &MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA,
                   v9,
                   v96);
      if ( Instance < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != Instance )
            CallStackContext::TraceFailure(v48, "ActivateClassicITA", 5352, Instance);
        }
        if ( g_wppLevels )
        {
          v17 = 523;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( Instance < 0 )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
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
        if ( *((_DWORD *)v54 + 499) != Instance )
          CallStackContext::TraceFailure(v54, "ActivateClassicITA", 5356, Instance);
      }
      if ( g_wppLevels )
      {
        v17 = 524;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    Instance = MFSerializeAttributesToStream(ppMFAttributes, 0, ppstm);
    if ( Instance < 0 )
    {
      v58 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
        CallStackTracing::s_wpInstance = v59;
        if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        {
          v58 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
        if ( *((_DWORD *)v60 + 499) != Instance )
          CallStackContext::TraceFailure(v60, "ActivateClassicITA", 5357, Instance);
      }
      if ( g_wppLevels )
      {
        v17 = 525;
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
        v64 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v64 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v64 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v64 + 8) )
        {
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
          if ( *((_DWORD *)v66 + 499) != Instance )
            CallStackContext::TraceFailure(v66, "ActivateClassicITA", 5363, Instance);
        }
        if ( g_wppLevels )
        {
          v17 = 526;
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
        v89 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v86, v87, v88);
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
          if ( *((_DWORD *)v91 + 499) != Instance )
            CallStackContext::TraceFailure(v91, "ActivateClassicITA", 5381, Instance);
        }
        if ( g_wppLevels )
        {
          v17 = 530;
          goto LABEL_149;
        }
      }
      goto LABEL_150;
    }
    v94 = 0;
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
      Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv[0])(ppv[0], &IID_IPersistStream, &v94);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v94 + 40LL))(v94, ppstm);
        if ( Instance >= 0 )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v94);
          goto LABEL_138;
        }
        v83 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v80, v81, v82);
          CallStackTracing::s_wpInstance = v84;
          if ( v84 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
          {
            v83 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v83 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v83 + 8) )
        {
          v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
          if ( *((_DWORD *)v85 + 499) != Instance )
            CallStackContext::TraceFailure(v85, "ActivateClassicITA", 5377, Instance);
        }
        if ( !g_wppLevels )
        {
LABEL_114:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v94);
          goto LABEL_150;
        }
        v73 = 529;
      }
      else
      {
        v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75, v76);
          CallStackTracing::s_wpInstance = v78;
          if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
          {
            v77 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v77 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v77 + 8) )
        {
          v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
          if ( *((_DWORD *)v79 + 499) != Instance )
            CallStackContext::TraceFailure(v79, "ActivateClassicITA", 5376, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_114;
        v73 = 528;
      }
    }
    else
    {
      v70 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
        CallStackTracing::s_wpInstance = v71;
        if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
        {
          v70 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v70 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v70 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
        if ( *((_DWORD *)v72 + 499) != Instance )
          CallStackContext::TraceFailure(v72, "ActivateClassicITA", 5369, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_114;
      v73 = 527;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v73, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
    goto LABEL_114;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
    if ( *((_DWORD *)v23 + 499) != Instance )
      CallStackContext::TraceFailure(v23, "ActivateClassicITA", 5338, Instance);
  }
  if ( g_wppLevels )
  {
    v17 = 519;
    goto LABEL_149;
  }
LABEL_150:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v93);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFAttributes);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18008b354  push    rbp
0x18008b356  push    rbx
0x18008b357  push    rsi
0x18008b358  push    rdi
0x18008b359  push    r12
0x18008b35b  push    r13
0x18008b35d  push    r14
0x18008b35f  push    r15
0x18008b361  lea     rbp, [rsp-17h]
0x18008b366  sub     rsp, 0D8h
0x18008b36d  mov     rax, cs:__security_cookie
0x18008b374  xor     rax, rsp
0x18008b377  mov     [rbp+4Fh+var_50], rax
0x18008b37b  mov     r12, [rbp+4Fh+arg_20]
0x18008b37f  xor     ebx, ebx
0x18008b381  mov     rdi, r8
0x18008b384  mov     [rbp+4Fh+var_C8], ebx
0x18008b387  mov     r14, rdx
0x18008b38a  mov     rsi, rcx
0x18008b38d  xor     edx, edx; Val
0x18008b38f  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18008b393  lea     r8d, [rbx+50h]; Size
0x18008b397  mov     r15, r9
0x18008b39a  mov     r13d, ebx
0x18008b39d  call    memset_0
0x18008b3a2  mov     r8d, 14D9h; int
0x18008b3a8  mov     [rbp+4Fh+var_B8], rbx
0x18008b3ac  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b3b3  mov     [rbp+4Fh+ppMFAttributes], rbx
0x18008b3b7  lea     rcx, [rsp+110h+var_E0]; this
0x18008b3bc  mov     [rsp+110h+ppstm], rbx
0x18008b3c1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008b3c6  lea     edx, [rbx+3]; cInitialSize
0x18008b3c9  lea     rcx, [rbp+4Fh+ppMFAttributes]; ppMFAttributes
0x18008b3cd  call    cs:__imp_MFCreateAttributes
0x18008b3d3  mov     ebx, eax
0x18008b3d5  test    eax, eax
0x18008b3d7  jns     loc_18008B46C
0x18008b3dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b3e4  test    rcx, rcx
0x18008b3e7  jnz     short loc_18008B42A
0x18008b3e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b3ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b3f6  mov     rcx, rax
0x18008b3f9  test    rax, rax
0x18008b3fc  jz      short loc_18008B41C
0x18008b3fe  mov     rax, [rax]
0x18008b401  mov     edx, 7F0h
0x18008b406  mov     rax, [rax+8]
0x18008b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b40f  test    eax, eax
0x18008b411  jz      short loc_18008B41C
0x18008b413  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b41a  jmp     short loc_18008B42A
0x18008b41c  lea     rcx, qword_1801B07E0; this
0x18008b423  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b42a  cmp     [rcx+8], r13b
0x18008b42e  jz      short loc_18008B455
0x18008b430  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b435  cmp     [rax+7CCh], ebx
0x18008b43b  jz      short loc_18008B455
0x18008b43d  mov     r9d, ebx; int
0x18008b440  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b447  mov     r8d, 14D9h; int
0x18008b44d  mov     rcx, rax; this
0x18008b450  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b455  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b45c  jb      loc_18008BD66
0x18008b462  mov     edx, 206h
0x18008b467  jmp     loc_18008BD48
0x18008b46c  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x18008b470  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID
0x18008b477  mov     r8, r14
0x18008b47a  mov     rax, [rcx]
0x18008b47d  mov     rax, [rax+0C8h]
0x18008b484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b489  xor     r14d, r14d
0x18008b48c  mov     ebx, eax
0x18008b48e  test    eax, eax
0x18008b490  jns     loc_18008B525
0x18008b496  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b49d  test    rcx, rcx
0x18008b4a0  jnz     short loc_18008B4E3
0x18008b4a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b4a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b4af  mov     rcx, rax
0x18008b4b2  test    rax, rax
0x18008b4b5  jz      short loc_18008B4D5
0x18008b4b7  mov     rax, [rax]
0x18008b4ba  mov     edx, 7F0h
0x18008b4bf  mov     rax, [rax+8]
0x18008b4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b4c8  test    eax, eax
0x18008b4ca  jz      short loc_18008B4D5
0x18008b4cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b4d3  jmp     short loc_18008B4E3
0x18008b4d5  lea     rcx, qword_1801B07E0; this
0x18008b4dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b4e3  cmp     [rcx+8], r14b
0x18008b4e7  jz      short loc_18008B50E
0x18008b4e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b4ee  cmp     [rax+7CCh], ebx
0x18008b4f4  jz      short loc_18008B50E
0x18008b4f6  mov     r9d, ebx; int
0x18008b4f9  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b500  mov     r8d, 14DAh; int
0x18008b506  mov     rcx, rax; this
0x18008b509  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b50e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b515  jb      loc_18008BD66
0x18008b51b  mov     edx, 207h
0x18008b520  jmp     loc_18008BD48
0x18008b525  test    rdi, rdi
0x18008b528  jz      loc_18008B814
0x18008b52e  mov     rax, [rdi]
0x18008b531  lea     rdx, [rbp+4Fh+var_A0]
0x18008b535  mov     r8d, 3
0x18008b53b  mov     [rsp+110h+var_D8], r14
0x18008b540  mov     rcx, rdi
0x18008b543  mov     rax, [rax+60h]
0x18008b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b54c  mov     ebx, eax
0x18008b54e  test    eax, eax
0x18008b550  jns     loc_18008B5E5
0x18008b556  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b55d  test    rcx, rcx
0x18008b560  jnz     short loc_18008B5A3
0x18008b562  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b568  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b56f  mov     rcx, rax
0x18008b572  test    rax, rax
0x18008b575  jz      short loc_18008B595
0x18008b577  mov     rax, [rax]
0x18008b57a  mov     edx, 7F0h
0x18008b57f  mov     rax, [rax+8]
0x18008b583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b588  test    eax, eax
0x18008b58a  jz      short loc_18008B595
0x18008b58c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b593  jmp     short loc_18008B5A3
0x18008b595  lea     rcx, qword_1801B07E0; this
0x18008b59c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b5a3  cmp     [rcx+8], r14b
0x18008b5a7  jz      short loc_18008B5CE
0x18008b5a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b5ae  cmp     [rax+7CCh], ebx
0x18008b5b4  jz      short loc_18008B5CE
0x18008b5b6  mov     r9d, ebx; int
0x18008b5b9  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b5c0  mov     r8d, 14E0h; int
0x18008b5c6  mov     rcx, rax; this
0x18008b5c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b5ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b5d5  jb      loc_18008BD66
0x18008b5db  mov     edx, 208h
0x18008b5e0  jmp     loc_18008BD48
0x18008b5e5  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x18008b5e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008b5ed  mov     r13, rax
0x18008b5f0  test    rax, rax
0x18008b5f3  jnz     loc_18008B68D
0x18008b5f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b600  mov     ebx, 8007000Eh
0x18008b605  test    rcx, rcx
0x18008b608  jnz     short loc_18008B64B
0x18008b60a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b610  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b617  mov     rcx, rax
0x18008b61a  test    rax, rax
0x18008b61d  jz      short loc_18008B63D
0x18008b61f  mov     rax, [rax]
0x18008b622  mov     edx, 7F0h
0x18008b627  mov     rax, [rax+8]
0x18008b62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b630  test    eax, eax
0x18008b632  jz      short loc_18008B63D
0x18008b634  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b63b  jmp     short loc_18008B64B
0x18008b63d  lea     rcx, qword_1801B07E0; this
0x18008b644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b64b  cmp     [rcx+8], r14b
0x18008b64f  jz      short loc_18008B676
0x18008b651  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b656  cmp     [rax+7CCh], ebx
0x18008b65c  jz      short loc_18008B676
0x18008b65e  mov     r9d, ebx; int
0x18008b661  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b668  mov     r8d, 14E4h; int
0x18008b66e  mov     rcx, rax; this
0x18008b671  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b676  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b67d  jb      loc_18008BD66
0x18008b683  mov     edx, 209h
0x18008b688  jmp     loc_18008BD48
0x18008b68d  mov     rax, [rdi]
0x18008b690  xor     r9d, r9d
0x18008b693  mov     rdx, [rsp+110h+var_D8]
0x18008b698  xor     r8d, r8d
0x18008b69b  mov     rcx, rdi
0x18008b69e  mov     rax, [rax+28h]
0x18008b6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6a7  mov     rax, [rdi]
0x18008b6aa  lea     r9, [rbp+4Fh+var_C8]
0x18008b6ae  mov     r8d, dword ptr [rbp+4Fh+Size]
0x18008b6b2  mov     rdx, r13
0x18008b6b5  mov     rcx, rdi
0x18008b6b8  mov     rax, [rax+18h]
0x18008b6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6c1  mov     ebx, eax
0x18008b6c3  test    eax, eax
0x18008b6c5  jns     loc_18008B75A
0x18008b6cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b6d2  test    rcx, rcx
0x18008b6d5  jnz     short loc_18008B718
0x18008b6d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b6dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b6e4  mov     rcx, rax
0x18008b6e7  test    rax, rax
0x18008b6ea  jz      short loc_18008B70A
0x18008b6ec  mov     rax, [rax]
0x18008b6ef  mov     edx, 7F0h
0x18008b6f4  mov     rax, [rax+8]
0x18008b6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6fd  test    eax, eax
0x18008b6ff  jz      short loc_18008B70A
0x18008b701  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b708  jmp     short loc_18008B718
0x18008b70a  lea     rcx, qword_1801B07E0; this
0x18008b711  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b718  cmp     [rcx+8], r14b
0x18008b71c  jz      short loc_18008B743
0x18008b71e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b723  cmp     [rax+7CCh], ebx
0x18008b729  jz      short loc_18008B743
0x18008b72b  mov     r9d, ebx; int
0x18008b72e  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b735  mov     r8d, 14E7h; int
0x18008b73b  mov     rcx, rax; this
0x18008b73e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b743  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b74a  jb      loc_18008BD66
0x18008b750  mov     edx, 20Ah
0x18008b755  jmp     loc_18008BD48
0x18008b75a  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x18008b75e  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA
0x18008b765  mov     r9d, [rbp+4Fh+var_C8]
0x18008b769  mov     r8, r13
0x18008b76c  mov     rax, [rcx]
0x18008b76f  mov     rax, [rax+0D0h]
0x18008b776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b77b  mov     ebx, eax
0x18008b77d  test    eax, eax
0x18008b77f  jns     loc_18008B814
0x18008b785  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b78c  test    rcx, rcx
0x18008b78f  jnz     short loc_18008B7D2
0x18008b791  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b797  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b79e  mov     rcx, rax
0x18008b7a1  test    rax, rax
0x18008b7a4  jz      short loc_18008B7C4
0x18008b7a6  mov     rax, [rax]
0x18008b7a9  mov     edx, 7F0h
0x18008b7ae  mov     rax, [rax+8]
0x18008b7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b7b7  test    eax, eax
0x18008b7b9  jz      short loc_18008B7C4
0x18008b7bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b7c2  jmp     short loc_18008B7D2
0x18008b7c4  lea     rcx, qword_1801B07E0; this
0x18008b7cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b7d2  cmp     [rcx+8], r14b
0x18008b7d6  jz      short loc_18008B7FD
0x18008b7d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008b7dd  cmp     [rax+7CCh], ebx
0x18008b7e3  jz      short loc_18008B7FD
0x18008b7e5  mov     r9d, ebx; int
0x18008b7e8  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18008b7ef  mov     r8d, 14E8h; int
0x18008b7f5  mov     rcx, rax; this
0x18008b7f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008b7fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008b804  jb      loc_18008BD66
0x18008b80a  mov     edx, 20Bh
0x18008b80f  jmp     loc_18008BD48
0x18008b814  lea     r8, [rsp+110h+ppstm]; ppstm
0x18008b819  mov     edx, 1; fDeleteOnRelease
0x18008b81e  xor     ecx, ecx; hGlobal
0x18008b820  call    cs:__imp_CreateStreamOnHGlobal
0x18008b826  mov     ebx, eax
0x18008b828  test    eax, eax
0x18008b82a  jns     loc_18008B8BF
0x18008b830  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b837  test    rcx, rcx
0x18008b83a  jnz     short loc_18008B87D
0x18008b83c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008b842  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008b849  mov     rcx, rax
0x18008b84c  test    rax, rax
0x18008b84f  jz      short loc_18008B86F
  ... truncated ...
```
