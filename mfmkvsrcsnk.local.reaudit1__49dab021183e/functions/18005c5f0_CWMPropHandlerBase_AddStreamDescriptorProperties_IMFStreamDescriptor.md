# CWMPropHandlerBase::AddStreamDescriptorProperties(IMFStreamDescriptor *)

- ea: `0x18005c5f0`
- end: `0x18005cf74`
- name: `?AddStreamDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `2436`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f800`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800516a4`
- `0x180059304`
- `0x18005c5f0`
- `0x18005cf7c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005cae8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005cde1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005cae8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005cde1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c682`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c74f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c8dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c98e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ca5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cb0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cbd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cc87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cd58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c682`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c74f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c8dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c98e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ca5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cb0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cbd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cc87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005cd58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce99`

## string_xrefs

- `0x18005c617`: `CWMPropHandlerBase::AddStreamDescriptorProperties`

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
                      v48 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v42 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v36 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v30 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                      v76 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v70 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v64 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v58 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v79 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v17 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18005c5f0  mov     [rsp-28h+arg_10], rbx
0x18005c5f5  push    rbp
0x18005c5f6  push    rsi
0x18005c5f7  push    rdi
0x18005c5f8  push    r14
0x18005c5fa  push    r15
0x18005c5fc  mov     rbp, rsp
0x18005c5ff  sub     rsp, 80h
0x18005c606  mov     rax, cs:__security_cookie
0x18005c60d  xor     rax, rsp
0x18005c610  mov     [rbp+var_10], rax
0x18005c614  mov     rsi, rdx
0x18005c617  lea     r15, aCwmprophandler_4; "CWMPropHandlerBase::AddStreamDescriptor"...
0x18005c61e  mov     rdi, rcx
0x18005c621  mov     rdx, r15; char *
0x18005c624  mov     r8d, 6D1h; int
0x18005c62a  lea     rcx, [rbp+var_50]; this
0x18005c62e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005c633  xor     eax, eax
0x18005c635  lea     rdx, [rbp+var_40]
0x18005c639  mov     qword ptr [rbp+pvar+10h], rax
0x18005c63d  xor     r14d, r14d
0x18005c640  mov     rax, [rsi]
0x18005c643  xorps   xmm0, xmm0
0x18005c646  xorps   xmm1, xmm1
0x18005c649  mov     [rbp+var_40], r14
0x18005c64d  mov     rcx, rsi
0x18005c650  mov     [rbp+var_48], r14
0x18005c654  movups  [rbp+Buf2], xmm0
0x18005c658  mov     rax, [rax+110h]
0x18005c65f  movups  xmmword ptr [rbp+pvar], xmm1
0x18005c663  mov     [rbp+var_4C], r14d
0x18005c667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c66c  mov     ebx, eax
0x18005c66e  test    eax, eax
0x18005c670  jns     loc_18005C707
0x18005c676  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c67d  test    rcx, rcx
0x18005c680  jnz     short loc_18005C6C9
0x18005c682  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c689  nop     dword ptr [rax+rax+00h]
0x18005c68e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c695  mov     rcx, rax
0x18005c698  test    rax, rax
0x18005c69b  jz      short loc_18005C6BB
0x18005c69d  mov     rax, [rax]
0x18005c6a0  mov     edx, 7F0h
0x18005c6a5  mov     rax, [rax+8]
0x18005c6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c6ae  test    eax, eax
0x18005c6b0  jz      short loc_18005C6BB
0x18005c6b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c6b9  jmp     short loc_18005C6C9
0x18005c6bb  lea     rcx, qword_1800DBF70; this
0x18005c6c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c6c9  cmp     [rcx+8], r14b
0x18005c6cd  jz      short loc_18005C6F0
0x18005c6cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c6d4  cmp     [rax+7CCh], ebx
0x18005c6da  jz      short loc_18005C6F0
0x18005c6dc  mov     r9d, ebx; int
0x18005c6df  mov     r8d, 6DAh; int
0x18005c6e5  mov     rdx, r15; char *
0x18005c6e8  mov     rcx, rax; this
0x18005c6eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c6f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c6f7  jb      loc_18005CF33
0x18005c6fd  mov     edx, 96h
0x18005c702  jmp     loc_18005CF15
0x18005c707  mov     rcx, [rbp+var_40]
0x18005c70b  lea     rdx, [rbp+var_48]
0x18005c70f  mov     rax, [rcx]
0x18005c712  mov     rax, [rax+38h]
0x18005c716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c71b  test    eax, eax
0x18005c71d  jns     loc_18005C7D4
0x18005c723  mov     rcx, [rbp+var_40]
0x18005c727  lea     r8, [rbp+var_48]
0x18005c72b  xor     edx, edx
0x18005c72d  mov     rax, [rcx]
0x18005c730  mov     rax, [rax+28h]
0x18005c734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c739  mov     ebx, eax
0x18005c73b  test    eax, eax
0x18005c73d  jns     loc_18005C7D4
0x18005c743  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c74a  test    rcx, rcx
0x18005c74d  jnz     short loc_18005C796
0x18005c74f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c756  nop     dword ptr [rax+rax+00h]
0x18005c75b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c762  mov     rcx, rax
0x18005c765  test    rax, rax
0x18005c768  jz      short loc_18005C788
0x18005c76a  mov     rax, [rax]
0x18005c76d  mov     edx, 7F0h
0x18005c772  mov     rax, [rax+8]
0x18005c776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c77b  test    eax, eax
0x18005c77d  jz      short loc_18005C788
0x18005c77f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c786  jmp     short loc_18005C796
0x18005c788  lea     rcx, qword_1800DBF70; this
0x18005c78f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c796  cmp     [rcx+8], r14b
0x18005c79a  jz      short loc_18005C7BD
0x18005c79c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c7a1  cmp     [rax+7CCh], ebx
0x18005c7a7  jz      short loc_18005C7BD
0x18005c7a9  mov     r9d, ebx; int
0x18005c7ac  mov     r8d, 6DFh; int
0x18005c7b2  mov     rdx, r15; char *
0x18005c7b5  mov     rcx, rax; this
0x18005c7b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c7bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c7c4  jb      loc_18005CF33
0x18005c7ca  mov     edx, 97h
0x18005c7cf  jmp     loc_18005CF15
0x18005c7d4  mov     rcx, [rbp+var_48]
0x18005c7d8  lea     rdx, [rbp+Buf2]
0x18005c7dc  mov     rax, [rcx]
0x18005c7df  mov     rax, [rax+108h]
0x18005c7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7eb  mov     ebx, eax
0x18005c7ed  test    eax, eax
0x18005c7ef  jns     loc_18005C886
0x18005c7f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c7fc  test    rcx, rcx
0x18005c7ff  jnz     short loc_18005C848
0x18005c801  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c808  nop     dword ptr [rax+rax+00h]
0x18005c80d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c814  mov     rcx, rax
0x18005c817  test    rax, rax
0x18005c81a  jz      short loc_18005C83A
0x18005c81c  mov     rax, [rax]
0x18005c81f  mov     edx, 7F0h
0x18005c824  mov     rax, [rax+8]
0x18005c828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c82d  test    eax, eax
0x18005c82f  jz      short loc_18005C83A
0x18005c831  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c838  jmp     short loc_18005C848
0x18005c83a  lea     rcx, qword_1800DBF70; this
0x18005c841  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c848  cmp     [rcx+8], r14b
0x18005c84c  jz      short loc_18005C86F
0x18005c84e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c853  cmp     [rax+7CCh], ebx
0x18005c859  jz      short loc_18005C86F
0x18005c85b  mov     r9d, ebx; int
0x18005c85e  mov     r8d, 6E2h; int
0x18005c864  mov     rdx, r15; char *
0x18005c867  mov     rcx, rax; this
0x18005c86a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c86f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c876  jb      loc_18005CF33
0x18005c87c  mov     edx, 98h
0x18005c881  jmp     loc_18005CF15
0x18005c886  xor     eax, eax
0x18005c888  lea     rdx, [rbp+Buf2]; Buf2
0x18005c88c  xorps   xmm0, xmm0
0x18005c88f  mov     qword ptr [rbp+pvar+10h], rax
0x18005c893  lea     rcx, MFMediaType_Audio; Buf1
0x18005c89a  movups  xmmword ptr [rbp+pvar], xmm0
0x18005c89e  lea     ebx, [rax+10h]
0x18005c8a1  mov     r8d, ebx; Size
0x18005c8a4  call    memcmp_0
0x18005c8a9  test    eax, eax
0x18005c8ab  jnz     loc_18005CB8F
0x18005c8b1  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x18005c8b5  mov     rcx, rdi; this
0x18005c8b8  mov     dword ptr [rdi+384h], 1
0x18005c8c2  call    ?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z; CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)
0x18005c8c7  mov     ebx, eax
0x18005c8c9  test    eax, eax
0x18005c8cb  jns     loc_18005C962
0x18005c8d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c8d8  test    rcx, rcx
0x18005c8db  jnz     short loc_18005C924
0x18005c8dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c8e4  nop     dword ptr [rax+rax+00h]
0x18005c8e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c8f0  mov     rcx, rax
0x18005c8f3  test    rax, rax
0x18005c8f6  jz      short loc_18005C916
0x18005c8f8  mov     rax, [rax]
0x18005c8fb  mov     edx, 7F0h
0x18005c900  mov     rax, [rax+8]
0x18005c904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c909  test    eax, eax
0x18005c90b  jz      short loc_18005C916
0x18005c90d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c914  jmp     short loc_18005C924
0x18005c916  lea     rcx, qword_1800DBF70; this
0x18005c91d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c924  cmp     [rcx+8], r14b
0x18005c928  jz      short loc_18005C94B
0x18005c92a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c92f  cmp     [rax+7CCh], ebx
0x18005c935  jz      short loc_18005C94B
0x18005c937  mov     r9d, ebx; int
0x18005c93a  mov     r8d, 6E9h; int
0x18005c940  mov     rdx, r15; char *
0x18005c943  mov     rcx, rax; this
0x18005c946  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c94b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005c952  jb      loc_18005CF33
0x18005c958  mov     edx, 99h
0x18005c95d  jmp     loc_18005CF15
0x18005c962  mov     rax, [rsi]
0x18005c965  lea     rdx, [rbp+var_4C]
0x18005c969  mov     rcx, rsi
0x18005c96c  mov     rax, [rax+108h]
0x18005c973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c978  mov     ebx, eax
0x18005c97a  test    eax, eax
0x18005c97c  jns     loc_18005CA13
0x18005c982  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c989  test    rcx, rcx
0x18005c98c  jnz     short loc_18005C9D5
0x18005c98e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005c995  nop     dword ptr [rax+rax+00h]
0x18005c99a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c9a1  mov     rcx, rax
0x18005c9a4  test    rax, rax
0x18005c9a7  jz      short loc_18005C9C7
0x18005c9a9  mov     rax, [rax]
0x18005c9ac  mov     edx, 7F0h
0x18005c9b1  mov     rax, [rax+8]
0x18005c9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9ba  test    eax, eax
0x18005c9bc  jz      short loc_18005C9C7
0x18005c9be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c9c5  jmp     short loc_18005C9D5
0x18005c9c7  lea     rcx, qword_1800DBF70; this
0x18005c9ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005c9d5  cmp     [rcx+8], r14b
0x18005c9d9  jz      short loc_18005C9FC
0x18005c9db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005c9e0  cmp     [rax+7CCh], ebx
0x18005c9e6  jz      short loc_18005C9FC
0x18005c9e8  mov     r9d, ebx; int
0x18005c9eb  mov     r8d, 6ECh; int
0x18005c9f1  mov     rdx, r15; char *
0x18005c9f4  mov     rcx, rax; this
0x18005c9f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005c9fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005ca03  jb      loc_18005CF33
0x18005ca09  mov     edx, 9Ah
0x18005ca0e  jmp     loc_18005CF15
0x18005ca13  mov     eax, 12h
0x18005ca18  mov     [rsp+80h+var_60], 1
0x18005ca20  mov     word ptr [rbp+pvar], ax
0x18005ca24  lea     r8, [rbp+pvar]
0x18005ca28  movzx   eax, word ptr [rbp+var_4C]
0x18005ca2c  lea     rdx, PKEY_Audio_StreamNumber
0x18005ca33  mov     word ptr [rbp+pvar+8], ax
0x18005ca37  xor     r9d, r9d
0x18005ca3a  mov     rax, [rdi]
0x18005ca3d  mov     rcx, rdi
0x18005ca40  mov     rax, [rax+28h]
0x18005ca44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca49  mov     ebx, eax
0x18005ca4b  test    eax, eax
0x18005ca4d  jns     loc_18005CAE4
0x18005ca53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ca5a  test    rcx, rcx
0x18005ca5d  jnz     short loc_18005CAA6
0x18005ca5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ca66  nop     dword ptr [rax+rax+00h]
0x18005ca6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ca72  mov     rcx, rax
0x18005ca75  test    rax, rax
0x18005ca78  jz      short loc_18005CA98
0x18005ca7a  mov     rax, [rax]
0x18005ca7d  mov     edx, 7F0h
0x18005ca82  mov     rax, [rax+8]
0x18005ca86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca8b  test    eax, eax
0x18005ca8d  jz      short loc_18005CA98
0x18005ca8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ca96  jmp     short loc_18005CAA6
0x18005ca98  lea     rcx, qword_1800DBF70; this
0x18005ca9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005caa6  cmp     [rcx+8], r14b
0x18005caaa  jz      short loc_18005CACD
0x18005caac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005cab1  cmp     [rax+7CCh], ebx
0x18005cab7  jz      short loc_18005CACD
0x18005cab9  mov     r9d, ebx; int
0x18005cabc  mov     r8d, 6F0h; int
0x18005cac2  mov     rdx, r15; char *
0x18005cac5  mov     rcx, rax; this
0x18005cac8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005cacd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005cad4  jb      loc_18005CF33
0x18005cada  mov     edx, 9Bh
0x18005cadf  jmp     loc_18005CF15
0x18005cae4  lea     rcx, [rbp+pvar]; pvar
  ... truncated ...
```
