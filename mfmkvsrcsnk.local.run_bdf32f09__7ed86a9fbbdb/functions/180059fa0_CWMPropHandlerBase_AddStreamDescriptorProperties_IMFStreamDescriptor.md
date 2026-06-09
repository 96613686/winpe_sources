# CWMPropHandlerBase::AddStreamDescriptorProperties(IMFStreamDescriptor *)

- ea: `0x180059fa0`
- end: `0x18005a8cf`
- name: `?AddStreamDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `2351`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d7c0`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004f47c`
- `0x180056e58`
- `0x180059fa0`
- `0x18005a8d8`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a474`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a74f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a474`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a74f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a0f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a1a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a27b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a3f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a490`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a601`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a6cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a76b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a7fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a0f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a1a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a27b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a3f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a490`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a601`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a6cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a76b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a7fb`

## string_xrefs

- `0x180059fc7`: `CWMPropHandlerBase::AddStreamDescriptorProperties`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddStreamDescriptorProperties(
        CWMPropHandlerBase *this,
        struct IMFStreamDescriptor *a2)
{
  struct IMFStreamDescriptorVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetMediaTypeHandler)(IMFStreamDescriptor *, IMFMediaTypeHandler **); // rax
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  struct IMFMediaType *v26; // rdx
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
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  struct IMFMediaType *v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  _BYTE v83[4]; // [rsp+30h] [rbp-50h] BYREF
  int v84; // [rsp+34h] [rbp-4Ch] BYREF
  struct IMFMediaType *v85; // [rsp+38h] [rbp-48h] BYREF
  __int64 v86; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-38h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v83,
    "CWMPropHandlerBase::AddStreamDescriptorProperties",
    1745);
  lpVtbl = a2->lpVtbl;
  v86 = 0;
  v85 = 0;
  Buf2 = 0;
  GetMediaTypeHandler = lpVtbl->GetMediaTypeHandler;
  memset(&pvar, 0, sizeof(pvar));
  v84 = 0;
  v7 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))GetMediaTypeHandler)(a2, &v86);
  if ( v7 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v86 + 56LL))(v86, &v85) >= 0
      || (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v86 + 40LL))(
                 v86,
                 0,
                 &v85),
          v7 >= 0) )
    {
      v7 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))v85->lpVtbl->GetMajorType)(v85, &Buf2);
      if ( v7 >= 0 )
      {
        memset(&pvar, 0, sizeof(pvar));
        if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
        {
          v26 = v85;
          *((_DWORD *)this + 225) = 1;
          v7 = CWMPropHandlerBase::AddAudioMediaTypeProperties(this, v26);
          if ( v7 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, int *))a2->lpVtbl->GetStreamIdentifier)(
                   a2,
                   &v84);
            if ( v7 >= 0 )
            {
              pvar.vt = 18;
              pvar.iVal = v84;
              v7 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                     this,
                     &PKEY_Audio_StreamNumber,
                     &pvar,
                     0,
                     1);
              if ( v7 >= 0 )
              {
                v7 = PropVariantClear(&pvar);
                if ( v7 < 0 )
                {
                  v48 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                    CallStackTracing::s_wpInstance = v49;
                    if ( v49
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                    {
                      v48 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v48 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v48 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CWMPropHandlerBase::AddStreamDescriptorProperties",
                        1777,
                        v7);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 156;
                    goto LABEL_135;
                  }
                }
              }
              else
              {
                v42 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
                  CallStackTracing::s_wpInstance = v43;
                  if ( v43
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                  {
                    v42 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v42 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v42 + 8) )
                {
                  v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
                  if ( *((_DWORD *)v44 + 499) != v7 )
                    CallStackContext::TraceFailure(v44, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1776, v7);
                }
                if ( g_wppLevels )
                {
                  v13 = 155;
                  goto LABEL_135;
                }
              }
            }
            else
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
                if ( *((_DWORD *)v38 + 499) != v7 )
                  CallStackContext::TraceFailure(v38, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1772, v7);
              }
              if ( g_wppLevels )
              {
                v13 = 154;
                goto LABEL_135;
              }
            }
          }
          else
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
              CallStackTracing::s_wpInstance = v31;
              if ( v31
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
              if ( *((_DWORD *)v32 + 499) != v7 )
                CallStackContext::TraceFailure(v32, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1769, v7);
            }
            if ( g_wppLevels )
            {
              v13 = 153;
              goto LABEL_135;
            }
          }
        }
        else if ( !memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
        {
          v54 = v85;
          *((_DWORD *)this + 226) = 1;
          v7 = CWMPropHandlerBase::AddVideoMediaTypeProperties(this, v54);
          if ( v7 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, int *))a2->lpVtbl->GetStreamIdentifier)(
                   a2,
                   &v84);
            if ( v7 >= 0 )
            {
              pvar.vt = 18;
              pvar.iVal = v84;
              v7 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                     this,
                     &PKEY_Video_StreamNumber,
                     &pvar,
                     0,
                     1);
              if ( v7 >= 0 )
              {
                v7 = PropVariantClear(&pvar);
                if ( v7 < 0 )
                {
                  v76 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73, v74, v75);
                    CallStackTracing::s_wpInstance = v77;
                    if ( v77
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
                    {
                      v76 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v76 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v76 + 8) )
                  {
                    v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
                    if ( *((_DWORD *)v78 + 499) != v7 )
                      CallStackContext::TraceFailure(v78, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1790, v7);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 160;
                    goto LABEL_135;
                  }
                }
              }
              else
              {
                v70 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
                  CallStackTracing::s_wpInstance = v71;
                  if ( v71
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
                  {
                    v70 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v70 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v70 + 8) )
                {
                  v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
                  if ( *((_DWORD *)v72 + 499) != v7 )
                    CallStackContext::TraceFailure(v72, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1789, v7);
                }
                if ( g_wppLevels )
                {
                  v13 = 159;
                  goto LABEL_135;
                }
              }
            }
            else
            {
              v64 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
                CallStackTracing::s_wpInstance = v65;
                if ( v65
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                {
                  v64 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v64 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v64 + 8) )
              {
                v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                if ( *((_DWORD *)v66 + 499) != v7 )
                  CallStackContext::TraceFailure(v66, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1785, v7);
              }
              if ( g_wppLevels )
              {
                v13 = 158;
                goto LABEL_135;
              }
            }
          }
          else
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
              CallStackTracing::s_wpInstance = v59;
              if ( v59
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
              {
                v58 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v58 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v58 + 8) )
            {
              v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
              if ( *((_DWORD *)v60 + 499) != v7 )
                CallStackContext::TraceFailure(v60, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1782, v7);
            }
            if ( g_wppLevels )
            {
              v13 = 157;
              goto LABEL_135;
            }
          }
        }
        else
        {
          v79 = (__int64 *)CallStackTracing::s_wpInstance;
          v7 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
            CallStackTracing::s_wpInstance = v80;
            if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
            {
              v79 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v79 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v79 + 8) )
          {
            v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
            if ( *((_DWORD *)v81 + 499) != -2147418113 )
              CallStackContext::TraceFailure(
                v81,
                "CWMPropHandlerBase::AddStreamDescriptorProperties",
                1798,
                -2147418113);
          }
          if ( g_wppLevels )
          {
            v13 = 161;
            goto LABEL_135;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v7 )
            CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1762, v7);
        }
        if ( g_wppLevels )
        {
          v13 = 152;
          goto LABEL_135;
        }
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v7 )
          CallStackContext::TraceFailure(v19, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1759, v7);
      }
      if ( g_wppLevels )
      {
        v13 = 151;
        goto LABEL_135;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v7 )
        CallStackContext::TraceFailure(v12, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1754, v7);
    }
    if ( g_wppLevels )
    {
      v13 = 150;
LABEL_135:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v7);
    }
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v85);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v86);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v83);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180059fa0  mov     [rsp-28h+arg_10], rbx
0x180059fa5  push    rbp
0x180059fa6  push    rsi
0x180059fa7  push    rdi
0x180059fa8  push    r14
0x180059faa  push    r15
0x180059fac  mov     rbp, rsp
0x180059faf  sub     rsp, 80h
0x180059fb6  mov     rax, cs:__security_cookie
0x180059fbd  xor     rax, rsp
0x180059fc0  mov     [rbp+var_10], rax
0x180059fc4  mov     rsi, rdx
0x180059fc7  lea     r15, aCwmprophandler_4; "CWMPropHandlerBase::AddStreamDescriptor"...
0x180059fce  mov     rdi, rcx
0x180059fd1  mov     rdx, r15; char *
0x180059fd4  mov     r8d, 6D1h; int
0x180059fda  lea     rcx, [rbp+var_50]; this
0x180059fde  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180059fe3  xor     eax, eax
0x180059fe5  lea     rdx, [rbp+var_40]
0x180059fe9  mov     qword ptr [rbp+pvar+10h], rax
0x180059fed  xor     r14d, r14d
0x180059ff0  mov     rax, [rsi]
0x180059ff3  xorps   xmm0, xmm0
0x180059ff6  xorps   xmm1, xmm1
0x180059ff9  mov     [rbp+var_40], r14
0x180059ffd  mov     rcx, rsi
0x18005a000  mov     [rbp+var_48], r14
0x18005a004  movups  [rbp+Buf2], xmm0
0x18005a008  mov     rax, [rax+110h]
0x18005a00f  movups  xmmword ptr [rbp+pvar], xmm1
0x18005a013  mov     [rbp+var_4C], r14d
0x18005a017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a01c  mov     ebx, eax
0x18005a01e  test    eax, eax
0x18005a020  jns     loc_18005A0B1
0x18005a026  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a02d  test    rcx, rcx
0x18005a030  jnz     short loc_18005A073
0x18005a032  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a038  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a03f  mov     rcx, rax
0x18005a042  test    rax, rax
0x18005a045  jz      short loc_18005A065
0x18005a047  mov     rax, [rax]
0x18005a04a  mov     edx, 7F0h
0x18005a04f  mov     rax, [rax+8]
0x18005a053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a058  test    eax, eax
0x18005a05a  jz      short loc_18005A065
0x18005a05c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a063  jmp     short loc_18005A073
0x18005a065  lea     rcx, qword_1800D6F70; this
0x18005a06c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a073  cmp     [rcx+8], r14b
0x18005a077  jz      short loc_18005A09A
0x18005a079  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a07e  cmp     [rax+7CCh], ebx
0x18005a084  jz      short loc_18005A09A
0x18005a086  mov     r9d, ebx; int
0x18005a089  mov     r8d, 6DAh; int
0x18005a08f  mov     rdx, r15; char *
0x18005a092  mov     rcx, rax; this
0x18005a095  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a09a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a0a1  jb      loc_18005A88F
0x18005a0a7  mov     edx, 96h
0x18005a0ac  jmp     loc_18005A871
0x18005a0b1  mov     rcx, [rbp+var_40]
0x18005a0b5  lea     rdx, [rbp+var_48]
0x18005a0b9  mov     rax, [rcx]
0x18005a0bc  mov     rax, [rax+38h]
0x18005a0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0c5  test    eax, eax
0x18005a0c7  jns     loc_18005A178
0x18005a0cd  mov     rcx, [rbp+var_40]
0x18005a0d1  lea     r8, [rbp+var_48]
0x18005a0d5  xor     edx, edx
0x18005a0d7  mov     rax, [rcx]
0x18005a0da  mov     rax, [rax+28h]
0x18005a0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0e3  mov     ebx, eax
0x18005a0e5  test    eax, eax
0x18005a0e7  jns     loc_18005A178
0x18005a0ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a0f4  test    rcx, rcx
0x18005a0f7  jnz     short loc_18005A13A
0x18005a0f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a0ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a106  mov     rcx, rax
0x18005a109  test    rax, rax
0x18005a10c  jz      short loc_18005A12C
0x18005a10e  mov     rax, [rax]
0x18005a111  mov     edx, 7F0h
0x18005a116  mov     rax, [rax+8]
0x18005a11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a11f  test    eax, eax
0x18005a121  jz      short loc_18005A12C
0x18005a123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a12a  jmp     short loc_18005A13A
0x18005a12c  lea     rcx, qword_1800D6F70; this
0x18005a133  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a13a  cmp     [rcx+8], r14b
0x18005a13e  jz      short loc_18005A161
0x18005a140  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a145  cmp     [rax+7CCh], ebx
0x18005a14b  jz      short loc_18005A161
0x18005a14d  mov     r9d, ebx; int
0x18005a150  mov     r8d, 6DFh; int
0x18005a156  mov     rdx, r15; char *
0x18005a159  mov     rcx, rax; this
0x18005a15c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a161  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a168  jb      loc_18005A88F
0x18005a16e  mov     edx, 97h
0x18005a173  jmp     loc_18005A871
0x18005a178  mov     rcx, [rbp+var_48]
0x18005a17c  lea     rdx, [rbp+Buf2]
0x18005a180  mov     rax, [rcx]
0x18005a183  mov     rax, [rax+108h]
0x18005a18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a18f  mov     ebx, eax
0x18005a191  test    eax, eax
0x18005a193  jns     loc_18005A224
0x18005a199  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a1a0  test    rcx, rcx
0x18005a1a3  jnz     short loc_18005A1E6
0x18005a1a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a1ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a1b2  mov     rcx, rax
0x18005a1b5  test    rax, rax
0x18005a1b8  jz      short loc_18005A1D8
0x18005a1ba  mov     rax, [rax]
0x18005a1bd  mov     edx, 7F0h
0x18005a1c2  mov     rax, [rax+8]
0x18005a1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1cb  test    eax, eax
0x18005a1cd  jz      short loc_18005A1D8
0x18005a1cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a1d6  jmp     short loc_18005A1E6
0x18005a1d8  lea     rcx, qword_1800D6F70; this
0x18005a1df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a1e6  cmp     [rcx+8], r14b
0x18005a1ea  jz      short loc_18005A20D
0x18005a1ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a1f1  cmp     [rax+7CCh], ebx
0x18005a1f7  jz      short loc_18005A20D
0x18005a1f9  mov     r9d, ebx; int
0x18005a1fc  mov     r8d, 6E2h; int
0x18005a202  mov     rdx, r15; char *
0x18005a205  mov     rcx, rax; this
0x18005a208  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a20d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a214  jb      loc_18005A88F
0x18005a21a  mov     edx, 98h
0x18005a21f  jmp     loc_18005A871
0x18005a224  xor     eax, eax
0x18005a226  lea     rdx, [rbp+Buf2]; Buf2
0x18005a22a  xorps   xmm0, xmm0
0x18005a22d  mov     qword ptr [rbp+pvar+10h], rax
0x18005a231  lea     rcx, MFMediaType_Audio; Buf1
0x18005a238  movups  xmmword ptr [rbp+pvar], xmm0
0x18005a23c  lea     ebx, [rax+10h]
0x18005a23f  mov     r8d, ebx; Size
0x18005a242  call    memcmp_0
0x18005a247  test    eax, eax
0x18005a249  jnz     loc_18005A50F
0x18005a24f  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x18005a253  mov     rcx, rdi; this
0x18005a256  mov     dword ptr [rdi+384h], 1
0x18005a260  call    ?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z; CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)
0x18005a265  mov     ebx, eax
0x18005a267  test    eax, eax
0x18005a269  jns     loc_18005A2FA
0x18005a26f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a276  test    rcx, rcx
0x18005a279  jnz     short loc_18005A2BC
0x18005a27b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a281  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a288  mov     rcx, rax
0x18005a28b  test    rax, rax
0x18005a28e  jz      short loc_18005A2AE
0x18005a290  mov     rax, [rax]
0x18005a293  mov     edx, 7F0h
0x18005a298  mov     rax, [rax+8]
0x18005a29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2a1  test    eax, eax
0x18005a2a3  jz      short loc_18005A2AE
0x18005a2a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a2ac  jmp     short loc_18005A2BC
0x18005a2ae  lea     rcx, qword_1800D6F70; this
0x18005a2b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a2bc  cmp     [rcx+8], r14b
0x18005a2c0  jz      short loc_18005A2E3
0x18005a2c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a2c7  cmp     [rax+7CCh], ebx
0x18005a2cd  jz      short loc_18005A2E3
0x18005a2cf  mov     r9d, ebx; int
0x18005a2d2  mov     r8d, 6E9h; int
0x18005a2d8  mov     rdx, r15; char *
0x18005a2db  mov     rcx, rax; this
0x18005a2de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a2e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a2ea  jb      loc_18005A88F
0x18005a2f0  mov     edx, 99h
0x18005a2f5  jmp     loc_18005A871
0x18005a2fa  mov     rax, [rsi]
0x18005a2fd  lea     rdx, [rbp+var_4C]
0x18005a301  mov     rcx, rsi
0x18005a304  mov     rax, [rax+108h]
0x18005a30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a310  mov     ebx, eax
0x18005a312  test    eax, eax
0x18005a314  jns     loc_18005A3A5
0x18005a31a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a321  test    rcx, rcx
0x18005a324  jnz     short loc_18005A367
0x18005a326  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a32c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a333  mov     rcx, rax
0x18005a336  test    rax, rax
0x18005a339  jz      short loc_18005A359
0x18005a33b  mov     rax, [rax]
0x18005a33e  mov     edx, 7F0h
0x18005a343  mov     rax, [rax+8]
0x18005a347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a34c  test    eax, eax
0x18005a34e  jz      short loc_18005A359
0x18005a350  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a357  jmp     short loc_18005A367
0x18005a359  lea     rcx, qword_1800D6F70; this
0x18005a360  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a367  cmp     [rcx+8], r14b
0x18005a36b  jz      short loc_18005A38E
0x18005a36d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a372  cmp     [rax+7CCh], ebx
0x18005a378  jz      short loc_18005A38E
0x18005a37a  mov     r9d, ebx; int
0x18005a37d  mov     r8d, 6ECh; int
0x18005a383  mov     rdx, r15; char *
0x18005a386  mov     rcx, rax; this
0x18005a389  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a38e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a395  jb      loc_18005A88F
0x18005a39b  mov     edx, 9Ah
0x18005a3a0  jmp     loc_18005A871
0x18005a3a5  mov     eax, 12h
0x18005a3aa  mov     [rsp+80h+var_60], 1
0x18005a3b2  mov     word ptr [rbp+pvar], ax
0x18005a3b6  lea     r8, [rbp+pvar]
0x18005a3ba  movzx   eax, word ptr [rbp+var_4C]
0x18005a3be  lea     rdx, PKEY_Audio_StreamNumber
0x18005a3c5  mov     word ptr [rbp+pvar+8], ax
0x18005a3c9  xor     r9d, r9d
0x18005a3cc  mov     rax, [rdi]
0x18005a3cf  mov     rcx, rdi
0x18005a3d2  mov     rax, [rax+28h]
0x18005a3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3db  mov     ebx, eax
0x18005a3dd  test    eax, eax
0x18005a3df  jns     loc_18005A470
0x18005a3e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a3ec  test    rcx, rcx
0x18005a3ef  jnz     short loc_18005A432
0x18005a3f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a3f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a3fe  mov     rcx, rax
0x18005a401  test    rax, rax
0x18005a404  jz      short loc_18005A424
0x18005a406  mov     rax, [rax]
0x18005a409  mov     edx, 7F0h
0x18005a40e  mov     rax, [rax+8]
0x18005a412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a417  test    eax, eax
0x18005a419  jz      short loc_18005A424
0x18005a41b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a422  jmp     short loc_18005A432
0x18005a424  lea     rcx, qword_1800D6F70; this
0x18005a42b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a432  cmp     [rcx+8], r14b
0x18005a436  jz      short loc_18005A459
0x18005a438  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a43d  cmp     [rax+7CCh], ebx
0x18005a443  jz      short loc_18005A459
0x18005a445  mov     r9d, ebx; int
0x18005a448  mov     r8d, 6F0h; int
0x18005a44e  mov     rdx, r15; char *
0x18005a451  mov     rcx, rax; this
0x18005a454  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a459  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a460  jb      loc_18005A88F
0x18005a466  mov     edx, 9Bh
0x18005a46b  jmp     loc_18005A871
0x18005a470  lea     rcx, [rbp+pvar]; pvar
0x18005a474  call    cs:__imp_PropVariantClear
0x18005a47a  mov     ebx, eax
0x18005a47c  test    eax, eax
0x18005a47e  jns     loc_18005A88F
0x18005a484  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a48b  test    rcx, rcx
  ... truncated ...
```
