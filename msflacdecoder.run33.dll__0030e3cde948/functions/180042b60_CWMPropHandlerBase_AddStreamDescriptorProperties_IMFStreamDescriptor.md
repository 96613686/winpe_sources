# CWMPropHandlerBase::AddStreamDescriptorProperties(IMFStreamDescriptor *)

- ea: `0x180042b60`
- end: `0x180043491`
- name: `?AddStreamDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFStreamDescriptor@@@Z`
- size: `2353`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFStreamDescriptor *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a980`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003f9f8`
- `0x180042b60`
- `0x180043498`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043034`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004330f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043034`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004330f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043050`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043116`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800431c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004328c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004332b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042bf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042cb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043050`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043116`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800431c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004328c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004332b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433bb`

## string_xrefs

- `0x180042b90`: `CWMPropHandlerBase::AddStreamDescriptorProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMPropHandlerBase::AddStreamDescriptorProperties(
        CWMPropHandlerBase *this,
        struct IMFStreamDescriptor *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  _BYTE v55[4]; // [rsp+30h] [rbp-50h] BYREF
  int v56; // [rsp+34h] [rbp-4Ch] BYREF
  struct IMFMediaType *v57; // [rsp+38h] [rbp-48h] BYREF
  __int64 v58; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-38h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v55,
    "CWMPropHandlerBase::AddStreamDescriptorProperties",
    1745);
  v58 = 0;
  v57 = 0;
  Buf2 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v56 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))a2->lpVtbl->GetMediaTypeHandler)(a2, &v58);
  if ( v5 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v58 + 56LL))(v58, &v57) >= 0
      || (v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v58 + 40LL))(
                 v58,
                 0,
                 &v57),
          v5 >= 0) )
    {
      v5 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))v57->lpVtbl->GetMajorType)(v57, &Buf2);
      if ( v5 >= 0 )
      {
        memset(&pvar, 0, sizeof(pvar));
        if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
        {
          *((_DWORD *)this + 225) = 1;
          v5 = CWMPropHandlerBase::AddAudioMediaTypeProperties(this, v57);
          if ( v5 >= 0 )
          {
            v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, int *))a2->lpVtbl->GetStreamIdentifier)(
                   a2,
                   &v56);
            if ( v5 >= 0 )
            {
              pvar.vt = 18;
              pvar.iVal = v56;
              v5 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                     this,
                     &PKEY_Audio_StreamNumber,
                     &pvar,
                     0,
                     1);
              if ( v5 >= 0 )
              {
                v5 = PropVariantClear(&pvar);
                if ( v5 < 0 )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                    CallStackTracing::s_wpInstance = v32;
                    if ( v32
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                    {
                      v31 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CWMPropHandlerBase::AddStreamDescriptorProperties",
                        1777,
                        v5);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v9 = 156;
                    goto LABEL_135;
                  }
                }
              }
              else
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                  {
                    v27 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v27 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v27 + 8) )
                {
                  v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                  if ( *((_DWORD *)v29 + 499) != v5 )
                    CallStackContext::TraceFailure(v29, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1776, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 155;
                  goto LABEL_135;
                }
              }
            }
            else
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
                CallStackTracing::s_wpInstance = v24;
                if ( v24
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
                {
                  v23 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v23 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v23 + 8) )
              {
                v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                if ( *((_DWORD *)v25 + 499) != v5 )
                  CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1772, v5);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 154;
                goto LABEL_135;
              }
            }
          }
          else
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)v21 + 499) != v5 )
                CallStackContext::TraceFailure(v21, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1769, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 153;
              goto LABEL_135;
            }
          }
        }
        else if ( !memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
        {
          *((_DWORD *)this + 226) = 1;
          v5 = CWMPropHandlerBase::AddVideoMediaTypeProperties(this, v57);
          if ( v5 >= 0 )
          {
            v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, int *))a2->lpVtbl->GetStreamIdentifier)(
                   a2,
                   &v56);
            if ( v5 >= 0 )
            {
              pvar.vt = 18;
              pvar.iVal = v56;
              v5 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                     this,
                     &PKEY_Video_StreamNumber,
                     &pvar,
                     0,
                     1);
              if ( v5 >= 0 )
              {
                v5 = PropVariantClear(&pvar);
                if ( v5 < 0 )
                {
                  v48 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
                    CallStackTracing::s_wpInstance = v49;
                    if ( v49
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                    {
                      v48 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v48 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v48 + 8) )
                  {
                    v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                    if ( *((_DWORD *)v50 + 499) != v5 )
                      CallStackContext::TraceFailure(v50, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1790, v5);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v9 = 160;
                    goto LABEL_135;
                  }
                }
              }
              else
              {
                v44 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
                  CallStackTracing::s_wpInstance = v45;
                  if ( v45
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
                  {
                    v44 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v44 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v44 + 8) )
                {
                  v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                  if ( *((_DWORD *)v46 + 499) != v5 )
                    CallStackContext::TraceFailure(v46, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1789, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 159;
                  goto LABEL_135;
                }
              }
            }
            else
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
                CallStackTracing::s_wpInstance = v41;
                if ( v41
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v40 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v40 + 8) )
              {
                v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                if ( *((_DWORD *)v42 + 499) != v5 )
                  CallStackContext::TraceFailure(v42, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1785, v5);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 158;
                goto LABEL_135;
              }
            }
          }
          else
          {
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
              CallStackTracing::s_wpInstance = v37;
              if ( v37
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
              {
                v36 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v36 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v36 + 8) )
            {
              v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
              if ( *((_DWORD *)v38 + 499) != v5 )
                CallStackContext::TraceFailure(v38, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1782, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 157;
              goto LABEL_135;
            }
          }
        }
        else
        {
          v5 = -2147418113;
          v51 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
            CallStackTracing::s_wpInstance = v52;
            if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
            {
              v51 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v51 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v51 + 8) )
          {
            v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
            if ( *((_DWORD *)v53 + 499) != -2147418113 )
              CallStackContext::TraceFailure(
                v53,
                "CWMPropHandlerBase::AddStreamDescriptorProperties",
                1798,
                -2147418113);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 161;
            goto LABEL_135;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1762, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 152;
          goto LABEL_135;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1759, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 151;
        goto LABEL_135;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CWMPropHandlerBase::AddStreamDescriptorProperties", 1754, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 150;
LABEL_135:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v5);
    }
  }
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v57);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v58);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180042b60  mov     [rsp-28h+arg_10], rbx
0x180042b65  push    rbp
0x180042b66  push    rsi
0x180042b67  push    rdi
0x180042b68  push    r14
0x180042b6a  push    r15
0x180042b6c  mov     rbp, rsp
0x180042b6f  sub     rsp, 80h
0x180042b76  mov     rax, cs:__security_cookie
0x180042b7d  xor     rax, rsp
0x180042b80  mov     [rbp+var_10], rax
0x180042b84  mov     rsi, rdx
0x180042b87  mov     rdi, rcx
0x180042b8a  mov     r8d, 6D1h; int
0x180042b90  lea     r15, aCwmprophandler_4; "CWMPropHandlerBase::AddStreamDescriptor"...
0x180042b97  mov     rdx, r15; char *
0x180042b9a  lea     rcx, [rbp+var_50]; this
0x180042b9e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180042ba3  xor     r14d, r14d
0x180042ba6  mov     [rbp+var_40], r14
0x180042baa  mov     [rbp+var_48], r14
0x180042bae  xorps   xmm0, xmm0
0x180042bb1  movups  [rbp+Buf2], xmm0
0x180042bb5  xorps   xmm1, xmm1
0x180042bb8  xor     eax, eax
0x180042bba  movups  xmmword ptr [rbp+pvar], xmm1
0x180042bbe  mov     qword ptr [rbp+pvar+10h], rax
0x180042bc2  mov     [rbp+var_4C], r14d
0x180042bc6  mov     rax, [rsi]
0x180042bc9  lea     rdx, [rbp+var_40]
0x180042bcd  mov     rcx, rsi
0x180042bd0  mov     rax, [rax+110h]
0x180042bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bdc  mov     ebx, eax
0x180042bde  test    eax, eax
0x180042be0  jns     loc_180042C71
0x180042be6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042bed  test    rcx, rcx
0x180042bf0  jnz     short loc_180042C33
0x180042bf2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042bf8  mov     rcx, rax
0x180042bfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042c02  test    rax, rax
0x180042c05  jz      short loc_180042C25
0x180042c07  mov     rax, [rax]
0x180042c0a  mov     edx, 7F0h
0x180042c0f  mov     rax, [rax+8]
0x180042c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c18  test    eax, eax
0x180042c1a  jz      short loc_180042C25
0x180042c1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042c23  jmp     short loc_180042C33
0x180042c25  lea     rcx, qword_18006EB20; this
0x180042c2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042c33  cmp     [rcx+8], r14b
0x180042c37  jz      short loc_180042C5A
0x180042c39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042c3e  cmp     [rax+7CCh], ebx
0x180042c44  jz      short loc_180042C5A
0x180042c46  mov     r9d, ebx; int
0x180042c49  mov     r8d, 6DAh; int
0x180042c4f  mov     rdx, r15; char *
0x180042c52  mov     rcx, rax; this
0x180042c55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042c5a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042c5f  cmp     al, 1
0x180042c61  jb      loc_180043450
0x180042c67  mov     edx, 96h
0x180042c6c  jmp     loc_180043431
0x180042c71  mov     rcx, [rbp+var_40]
0x180042c75  mov     rax, [rcx]
0x180042c78  lea     rdx, [rbp+var_48]
0x180042c7c  mov     rax, [rax+38h]
0x180042c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c85  test    eax, eax
0x180042c87  jns     loc_180042D38
0x180042c8d  mov     rcx, [rbp+var_40]
0x180042c91  mov     rax, [rcx]
0x180042c94  lea     r8, [rbp+var_48]
0x180042c98  xor     edx, edx
0x180042c9a  mov     rax, [rax+28h]
0x180042c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ca3  mov     ebx, eax
0x180042ca5  test    eax, eax
0x180042ca7  jns     loc_180042D38
0x180042cad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cb4  test    rcx, rcx
0x180042cb7  jnz     short loc_180042CFA
0x180042cb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042cbf  mov     rcx, rax
0x180042cc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cc9  test    rax, rax
0x180042ccc  jz      short loc_180042CEC
0x180042cce  mov     rax, [rax]
0x180042cd1  mov     edx, 7F0h
0x180042cd6  mov     rax, [rax+8]
0x180042cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cdf  test    eax, eax
0x180042ce1  jz      short loc_180042CEC
0x180042ce3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cea  jmp     short loc_180042CFA
0x180042cec  lea     rcx, qword_18006EB20; this
0x180042cf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cfa  cmp     [rcx+8], r14b
0x180042cfe  jz      short loc_180042D21
0x180042d00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042d05  cmp     [rax+7CCh], ebx
0x180042d0b  jz      short loc_180042D21
0x180042d0d  mov     r9d, ebx; int
0x180042d10  mov     r8d, 6DFh; int
0x180042d16  mov     rdx, r15; char *
0x180042d19  mov     rcx, rax; this
0x180042d1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042d21  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042d26  cmp     al, 1
0x180042d28  jb      loc_180043450
0x180042d2e  mov     edx, 97h
0x180042d33  jmp     loc_180043431
0x180042d38  mov     rcx, [rbp+var_48]
0x180042d3c  mov     rax, [rcx]
0x180042d3f  lea     rdx, [rbp+Buf2]
0x180042d43  mov     rax, [rax+108h]
0x180042d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d4f  mov     ebx, eax
0x180042d51  test    eax, eax
0x180042d53  jns     loc_180042DE4
0x180042d59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d60  test    rcx, rcx
0x180042d63  jnz     short loc_180042DA6
0x180042d65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042d6b  mov     rcx, rax
0x180042d6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d75  test    rax, rax
0x180042d78  jz      short loc_180042D98
0x180042d7a  mov     rax, [rax]
0x180042d7d  mov     edx, 7F0h
0x180042d82  mov     rax, [rax+8]
0x180042d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d8b  test    eax, eax
0x180042d8d  jz      short loc_180042D98
0x180042d8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d96  jmp     short loc_180042DA6
0x180042d98  lea     rcx, qword_18006EB20; this
0x180042d9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042da6  cmp     [rcx+8], r14b
0x180042daa  jz      short loc_180042DCD
0x180042dac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042db1  cmp     [rax+7CCh], ebx
0x180042db7  jz      short loc_180042DCD
0x180042db9  mov     r9d, ebx; int
0x180042dbc  mov     r8d, 6E2h; int
0x180042dc2  mov     rdx, r15; char *
0x180042dc5  mov     rcx, rax; this
0x180042dc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042dcd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042dd2  cmp     al, 1
0x180042dd4  jb      loc_180043450
0x180042dda  mov     edx, 98h
0x180042ddf  jmp     loc_180043431
0x180042de4  xorps   xmm0, xmm0
0x180042de7  xor     eax, eax
0x180042de9  movups  xmmword ptr [rbp+pvar], xmm0
0x180042ded  mov     qword ptr [rbp+pvar+10h], rax
0x180042df1  lea     ebx, [rax+10h]
0x180042df4  mov     r8d, ebx; Size
0x180042df7  lea     rdx, [rbp+Buf2]; Buf2
0x180042dfb  lea     rcx, MFMediaType_Audio; Buf1
0x180042e02  call    memcmp_0
0x180042e07  test    eax, eax
0x180042e09  jnz     loc_1800430CF
0x180042e0f  mov     dword ptr [rdi+384h], 1
0x180042e19  mov     rdx, [rbp+var_48]; struct IMFMediaType *
0x180042e1d  mov     rcx, rdi; this
0x180042e20  call    ?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z; CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)
0x180042e25  mov     ebx, eax
0x180042e27  test    eax, eax
0x180042e29  jns     loc_180042EBA
0x180042e2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e36  test    rcx, rcx
0x180042e39  jnz     short loc_180042E7C
0x180042e3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042e41  mov     rcx, rax
0x180042e44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e4b  test    rax, rax
0x180042e4e  jz      short loc_180042E6E
0x180042e50  mov     rax, [rax]
0x180042e53  mov     edx, 7F0h
0x180042e58  mov     rax, [rax+8]
0x180042e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e61  test    eax, eax
0x180042e63  jz      short loc_180042E6E
0x180042e65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e6c  jmp     short loc_180042E7C
0x180042e6e  lea     rcx, qword_18006EB20; this
0x180042e75  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e7c  cmp     [rcx+8], r14b
0x180042e80  jz      short loc_180042EA3
0x180042e82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042e87  cmp     [rax+7CCh], ebx
0x180042e8d  jz      short loc_180042EA3
0x180042e8f  mov     r9d, ebx; int
0x180042e92  mov     r8d, 6E9h; int
0x180042e98  mov     rdx, r15; char *
0x180042e9b  mov     rcx, rax; this
0x180042e9e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042ea3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042ea8  cmp     al, 1
0x180042eaa  jb      loc_180043450
0x180042eb0  mov     edx, 99h
0x180042eb5  jmp     loc_180043431
0x180042eba  mov     rax, [rsi]
0x180042ebd  lea     rdx, [rbp+var_4C]
0x180042ec1  mov     rcx, rsi
0x180042ec4  mov     rax, [rax+108h]
0x180042ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ed0  mov     ebx, eax
0x180042ed2  test    eax, eax
0x180042ed4  jns     loc_180042F65
0x180042eda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ee1  test    rcx, rcx
0x180042ee4  jnz     short loc_180042F27
0x180042ee6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042eec  mov     rcx, rax
0x180042eef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ef6  test    rax, rax
0x180042ef9  jz      short loc_180042F19
0x180042efb  mov     rax, [rax]
0x180042efe  mov     edx, 7F0h
0x180042f03  mov     rax, [rax+8]
0x180042f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f0c  test    eax, eax
0x180042f0e  jz      short loc_180042F19
0x180042f10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f17  jmp     short loc_180042F27
0x180042f19  lea     rcx, qword_18006EB20; this
0x180042f20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f27  cmp     [rcx+8], r14b
0x180042f2b  jz      short loc_180042F4E
0x180042f2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042f32  cmp     [rax+7CCh], ebx
0x180042f38  jz      short loc_180042F4E
0x180042f3a  mov     r9d, ebx; int
0x180042f3d  mov     r8d, 6ECh; int
0x180042f43  mov     rdx, r15; char *
0x180042f46  mov     rcx, rax; this
0x180042f49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042f4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042f53  cmp     al, 1
0x180042f55  jb      loc_180043450
0x180042f5b  mov     edx, 9Ah
0x180042f60  jmp     loc_180043431
0x180042f65  mov     eax, 12h
0x180042f6a  mov     word ptr [rbp+pvar], ax
0x180042f6e  movzx   eax, word ptr [rbp+var_4C]
0x180042f72  mov     word ptr [rbp+pvar+8], ax
0x180042f76  mov     rax, [rdi]
0x180042f79  mov     [rsp+80h+var_60], 1
0x180042f81  xor     r9d, r9d
0x180042f84  lea     r8, [rbp+pvar]
0x180042f88  lea     rdx, PKEY_Audio_StreamNumber
0x180042f8f  mov     rcx, rdi
0x180042f92  mov     rax, [rax+28h]
0x180042f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f9b  mov     ebx, eax
0x180042f9d  test    eax, eax
0x180042f9f  jns     loc_180043030
0x180042fa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042fac  test    rcx, rcx
0x180042faf  jnz     short loc_180042FF2
0x180042fb1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042fb7  mov     rcx, rax
0x180042fba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042fc1  test    rax, rax
0x180042fc4  jz      short loc_180042FE4
0x180042fc6  mov     rax, [rax]
0x180042fc9  mov     edx, 7F0h
0x180042fce  mov     rax, [rax+8]
0x180042fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fd7  test    eax, eax
0x180042fd9  jz      short loc_180042FE4
0x180042fdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042fe2  jmp     short loc_180042FF2
0x180042fe4  lea     rcx, qword_18006EB20; this
0x180042feb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ff2  cmp     [rcx+8], r14b
0x180042ff6  jz      short loc_180043019
0x180042ff8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042ffd  cmp     [rax+7CCh], ebx
0x180043003  jz      short loc_180043019
0x180043005  mov     r9d, ebx; int
0x180043008  mov     r8d, 6F0h; int
0x18004300e  mov     rdx, r15; char *
0x180043011  mov     rcx, rax; this
0x180043014  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043019  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004301e  cmp     al, 1
0x180043020  jb      loc_180043450
0x180043026  mov     edx, 9Bh
0x18004302b  jmp     loc_180043431
0x180043030  lea     rcx, [rbp+pvar]; pvar
  ... truncated ...
```
