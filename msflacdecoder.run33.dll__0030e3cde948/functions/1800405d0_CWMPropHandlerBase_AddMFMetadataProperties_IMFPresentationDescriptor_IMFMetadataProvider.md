# CWMPropHandlerBase::AddMFMetadataProperties(IMFPresentationDescriptor *,IMFMetadataProvider *)

- ea: `0x1800405d0`
- end: `0x180040e04`
- name: `?AddMFMetadataProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@PEAUIMFMetadataProvider@@@Z`
- size: `2100`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFPresentationDescriptor *, struct IMFMetadataProvider *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800405d0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004066a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800407d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040988`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040b29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040bb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040c62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040d35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004066a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800407d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040988`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040b29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040bb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040c62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040d35`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddMFMetadataProperties(
        CWMPropHandlerBase *this,
        struct IMFPresentationDescriptor *a2,
        struct IMFMetadataProvider *a3)
{
  struct IMFMetadataProviderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetMFMetadata)(IMFMetadataProvider *, IMFPresentationDescriptor *, DWORD, DWORD, IMFMetadata **); // rax
  __int64 v8; // rdx
  int v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  unsigned int i; // esi
  struct IMFPresentationDescriptorVtbl *v24; // rax
  HRESULT (__stdcall *GetStreamDescriptorByIndex)(IMFPresentationDescriptor *, DWORD, BOOL *, IMFStreamDescriptor **); // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  _BYTE v57[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v58; // [rsp+38h] [rbp-51h] BYREF
  __int64 v59; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v60; // [rsp+48h] [rbp-41h] BYREF
  int v61; // [rsp+4Ch] [rbp-3Dh] BYREF
  _DWORD v62[4]; // [rsp+50h] [rbp-39h] BYREF
  GUID v63; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v64[2]; // [rsp+70h] [rbp-19h] BYREF
  GUID v65; // [rsp+80h] [rbp-9h] BYREF
  GUID v66; // [rsp+90h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v57,
    "CWMPropHandlerBase::AddMFMetadataProperties",
    1684);
  lpVtbl = a3->lpVtbl;
  v64[0] = 0;
  GetMFMetadata = lpVtbl->GetMFMetadata;
  v60 = 0;
  v66 = GUID_00000000_0000_0000_0000_000000000000;
  v9 = ((__int64 (__fastcall *)(struct IMFMetadataProvider *, struct IMFPresentationDescriptor *, _QWORD, _QWORD, _QWORD *))GetMFMetadata)(
         a3,
         a2,
         0,
         0,
         v64);
  if ( v9 >= 0 )
  {
    v14 = *(_QWORD *)this;
    v63 = v66;
    v9 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, _QWORD, GUID *))(v14 + 192))(this, v64[0], &v63);
    if ( v9 >= 0 )
    {
      if ( a2 )
      {
        v9 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))a2->lpVtbl->GetStreamDescriptorCount)(
               a2,
               &v60);
        if ( v9 >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v60 )
              goto LABEL_109;
            v24 = a2->lpVtbl;
            v59 = 0;
            v58 = 0;
            v61 = 0;
            GetStreamDescriptorByIndex = v24->GetStreamDescriptorByIndex;
            v62[0] = 0;
            v9 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))GetStreamDescriptorByIndex)(
                   a2,
                   i,
                   &v61,
                   &v58);
            if ( v9 < 0 )
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v49 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CWMPropHandlerBase::AddMFMetadataProperties",
                    1716,
                    v9);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                WPP_SF_qd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  143,
                  &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
                  this,
                  v9);
              goto LABEL_108;
            }
            if ( v61 )
            {
              *(_QWORD *)&v63.Data1 = 0;
              v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v58 + 264LL))(v58, v62);
              if ( v9 < 0 )
              {
                v46 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                  CallStackTracing::s_wpInstance = v47;
                  if ( v47
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                  {
                    v46 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v46 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v46 + 8) )
                {
                  v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                  if ( *((_DWORD *)v48 + 499) != v9 )
                    CallStackContext::TraceFailure(v48, "CWMPropHandlerBase::AddMFMetadataProperties", 1721, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_97;
                v36 = 144;
LABEL_96:
                WPP_SF_qd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v36,
                  &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
                  this,
                  v9);
                goto LABEL_97;
              }
              v9 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v58 + 272LL))(v58, &v63);
              if ( v9 < 0 )
              {
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
                  CallStackTracing::s_wpInstance = v44;
                  if ( v44
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                  {
                    v43 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v43 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v43 + 8) )
                {
                  v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                  if ( *((_DWORD *)v45 + 499) != v9 )
                    CallStackContext::TraceFailure(v45, "CWMPropHandlerBase::AddMFMetadataProperties", 1723, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_97;
                v36 = 145;
                goto LABEL_96;
              }
              v9 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v63.Data1 + 64LL))(
                     *(_QWORD *)&v63.Data1,
                     &v66);
              if ( v9 < 0 )
              {
                v40 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
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
                  if ( *((_DWORD *)v42 + 499) != v9 )
                    CallStackContext::TraceFailure(v42, "CWMPropHandlerBase::AddMFMetadataProperties", 1725, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_97;
                v36 = 146;
                goto LABEL_96;
              }
              v9 = ((__int64 (__fastcall *)(struct IMFMetadataProvider *, struct IMFPresentationDescriptor *, _QWORD, _QWORD, __int64 *))a3->lpVtbl->GetMFMetadata)(
                     a3,
                     a2,
                     v62[0],
                     0,
                     &v59);
              if ( v9 < 0 )
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                  CallStackTracing::s_wpInstance = v38;
                  if ( v38
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                  {
                    v37 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v37 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v37 + 8) )
                {
                  v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                  if ( *((_DWORD *)v39 + 499) != v9 )
                    CallStackContext::TraceFailure(v39, "CWMPropHandlerBase::AddMFMetadataProperties", 1728, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_97;
                v36 = 147;
                goto LABEL_96;
              }
              v31 = *(_QWORD *)this;
              v65 = v66;
              v9 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, __int64, GUID *))(v31 + 192))(this, v59, &v65);
              if ( v9 < 0 )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                  CallStackTracing::s_wpInstance = v34;
                  if ( v34
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                  {
                    v33 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v33 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v33 + 8) )
                {
                  v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                  if ( *((_DWORD *)v35 + 499) != v9 )
                    CallStackContext::TraceFailure(v35, "CWMPropHandlerBase::AddMFMetadataProperties", 1730, v9);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v36 = 148;
                  goto LABEL_96;
                }
LABEL_97:
                ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v63);
LABEL_108:
                ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v58);
                ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v59);
                goto LABEL_121;
              }
              ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v63);
            }
            ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v58);
            ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v59);
          }
        }
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v9 )
            CallStackContext::TraceFailure(v22, "CWMPropHandlerBase::AddMFMetadataProperties", 1706, v9);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v13 = 142;
          goto LABEL_120;
        }
      }
      else
      {
LABEL_109:
        v9 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *))(*(_QWORD *)this + 224LL))(this);
        if ( v9 < 0 )
        {
          v53 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != v9 )
              CallStackContext::TraceFailure(v55, "CWMPropHandlerBase::AddMFMetadataProperties", 1735, v9);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 149;
            goto LABEL_120;
          }
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v9 )
          CallStackContext::TraceFailure(v18, "CWMPropHandlerBase::AddMFMetadataProperties", 1702, v9);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 141;
        goto LABEL_120;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CWMPropHandlerBase::AddMFMetadataProperties", 1700, v9);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 140;
LABEL_120:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v9);
    }
  }
LABEL_121:
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(v64);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v57);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800405d0  mov     [rsp-8+arg_18], rbx
0x1800405d5  push    rbp
0x1800405d6  push    rsi
0x1800405d7  push    rdi
0x1800405d8  push    r12
0x1800405da  push    r13
0x1800405dc  push    r14
0x1800405de  push    r15
0x1800405e0  lea     rbp, [rsp-27h]
0x1800405e5  sub     rsp, 0B0h
0x1800405ec  mov     rax, cs:__security_cookie
0x1800405f3  xor     rax, rsp
0x1800405f6  mov     [rbp+57h+var_40], rax
0x1800405fa  mov     r15, r8
0x1800405fd  lea     r13, aCwmprophandler_2; "CWMPropHandlerBase::AddMFMetadataProper"...
0x180040604  mov     r14, rdx
0x180040607  mov     rdi, rcx
0x18004060a  mov     rdx, r13; char *
0x18004060d  lea     rcx, [rbp+57h+var_B0]; this
0x180040611  mov     r8d, 694h; int
0x180040617  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004061c  mov     rax, [r15]
0x18004061f  lea     rcx, [rbp+57h+var_70]
0x180040623  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004062a  xor     r12d, r12d
0x18004062d  mov     [rsp+0E0h+var_C0], rcx
0x180040632  xor     r9d, r9d
0x180040635  mov     [rbp+57h+var_70], r12
0x180040639  mov     rax, [rax+18h]
0x18004063d  xor     r8d, r8d
0x180040640  mov     rdx, r14
0x180040643  mov     [rbp+57h+var_98], r12d
0x180040647  mov     rcx, r15
0x18004064a  movdqu  [rbp+57h+var_50], xmm0
0x18004064f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040654  mov     ebx, eax
0x180040656  test    eax, eax
0x180040658  jns     loc_1800406E9
0x18004065e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040665  test    rcx, rcx
0x180040668  jnz     short loc_1800406AB
0x18004066a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040670  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040677  mov     rcx, rax
0x18004067a  test    rax, rax
0x18004067d  jz      short loc_18004069D
0x18004067f  mov     rax, [rax]
0x180040682  mov     edx, 7F0h
0x180040687  mov     rax, [rax+8]
0x18004068b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040690  test    eax, eax
0x180040692  jz      short loc_18004069D
0x180040694  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004069b  jmp     short loc_1800406AB
0x18004069d  lea     rcx, qword_18006EB20; this
0x1800406a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800406ab  cmp     [rcx+8], r12b
0x1800406af  jz      short loc_1800406D2
0x1800406b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800406b6  cmp     [rax+7CCh], ebx
0x1800406bc  jz      short loc_1800406D2
0x1800406be  mov     r9d, ebx; int
0x1800406c1  mov     r8d, 6A4h; int
0x1800406c7  mov     rdx, r13; char *
0x1800406ca  mov     rcx, rax; this
0x1800406cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800406d2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800406d7  cmp     al, 1
0x1800406d9  jb      loc_180040DC9
0x1800406df  mov     edx, 8Ch
0x1800406e4  jmp     loc_180040DAB
0x1800406e9  mov     rax, [rdi]
0x1800406ec  lea     r8, [rbp+57h+var_80]
0x1800406f0  movaps  xmm0, [rbp+57h+var_50]
0x1800406f4  mov     rcx, rdi
0x1800406f7  mov     rdx, [rbp+57h+var_70]
0x1800406fb  movdqa  [rbp+57h+var_80], xmm0
0x180040700  mov     rax, [rax+0C0h]
0x180040707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004070c  mov     ebx, eax
0x18004070e  test    eax, eax
0x180040710  jns     loc_1800407A1
0x180040716  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004071d  test    rcx, rcx
0x180040720  jnz     short loc_180040763
0x180040722  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040728  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004072f  mov     rcx, rax
0x180040732  test    rax, rax
0x180040735  jz      short loc_180040755
0x180040737  mov     rax, [rax]
0x18004073a  mov     edx, 7F0h
0x18004073f  mov     rax, [rax+8]
0x180040743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040748  test    eax, eax
0x18004074a  jz      short loc_180040755
0x18004074c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040753  jmp     short loc_180040763
0x180040755  lea     rcx, qword_18006EB20; this
0x18004075c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180040763  cmp     [rcx+8], r12b
0x180040767  jz      short loc_18004078A
0x180040769  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004076e  cmp     [rax+7CCh], ebx
0x180040774  jz      short loc_18004078A
0x180040776  mov     r9d, ebx; int
0x180040779  mov     r8d, 6A6h; int
0x18004077f  mov     rdx, r13; char *
0x180040782  mov     rcx, rax; this
0x180040785  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004078a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004078f  cmp     al, 1
0x180040791  jb      loc_180040DC9
0x180040797  mov     edx, 8Dh
0x18004079c  jmp     loc_180040DAB
0x1800407a1  test    r14, r14
0x1800407a4  jz      loc_180040D0D
0x1800407aa  mov     rax, [r14]
0x1800407ad  lea     rdx, [rbp+57h+var_98]
0x1800407b1  mov     rcx, r14
0x1800407b4  mov     rax, [rax+108h]
0x1800407bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407c0  mov     ebx, eax
0x1800407c2  test    eax, eax
0x1800407c4  jns     loc_180040855
0x1800407ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407d1  test    rcx, rcx
0x1800407d4  jnz     short loc_180040817
0x1800407d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800407dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407e3  mov     rcx, rax
0x1800407e6  test    rax, rax
0x1800407e9  jz      short loc_180040809
0x1800407eb  mov     rax, [rax]
0x1800407ee  mov     edx, 7F0h
0x1800407f3  mov     rax, [rax+8]
0x1800407f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407fc  test    eax, eax
0x1800407fe  jz      short loc_180040809
0x180040800  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040807  jmp     short loc_180040817
0x180040809  lea     rcx, qword_18006EB20; this
0x180040810  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180040817  cmp     [rcx+8], r12b
0x18004081b  jz      short loc_18004083E
0x18004081d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180040822  cmp     [rax+7CCh], ebx
0x180040828  jz      short loc_18004083E
0x18004082a  mov     r9d, ebx; int
0x18004082d  mov     r8d, 6AAh; int
0x180040833  mov     rdx, r13; char *
0x180040836  mov     rcx, rax; this
0x180040839  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004083e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040843  cmp     al, 1
0x180040845  jb      loc_180040DC9
0x18004084b  mov     edx, 8Eh
0x180040850  jmp     loc_180040DAB
0x180040855  mov     esi, r12d
0x180040858  cmp     esi, [rbp+57h+var_98]
0x18004085b  jnb     loc_180040D0D
0x180040861  mov     rax, [r14]
0x180040864  lea     r9, [rbp+57h+var_A8]
0x180040868  lea     r8, [rbp+57h+var_94]
0x18004086c  mov     [rbp+57h+var_A0], r12
0x180040870  mov     edx, esi
0x180040872  mov     [rbp+57h+var_A8], r12
0x180040876  mov     rcx, r14
0x180040879  mov     [rbp+57h+var_94], r12d
0x18004087d  mov     rax, [rax+110h]
0x180040884  mov     [rbp+57h+var_90], r12d
0x180040888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004088d  mov     ebx, eax
0x18004088f  test    eax, eax
0x180040891  js      loc_180040C56
0x180040897  cmp     [rbp+57h+var_94], r12d
0x18004089b  jz      loc_180040963
0x1800408a1  mov     rcx, [rbp+57h+var_A8]
0x1800408a5  lea     rdx, [rbp+57h+var_90]
0x1800408a9  mov     qword ptr [rbp+57h+var_80], r12
0x1800408ad  mov     rax, [rcx]
0x1800408b0  mov     rax, [rax+108h]
0x1800408b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408bc  mov     ebx, eax
0x1800408be  test    eax, eax
0x1800408c0  js      loc_180040BA8
0x1800408c6  mov     rcx, [rbp+57h+var_A8]
0x1800408ca  lea     rdx, [rbp+57h+var_80]
0x1800408ce  mov     rax, [rcx]
0x1800408d1  mov     rax, [rax+110h]
0x1800408d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408dd  mov     ebx, eax
0x1800408df  test    eax, eax
0x1800408e1  js      loc_180040B1D
0x1800408e7  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800408eb  lea     rdx, [rbp+57h+var_50]
0x1800408ef  mov     rax, [rcx]
0x1800408f2  mov     rax, [rax+40h]
0x1800408f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408fb  mov     ebx, eax
0x1800408fd  test    eax, eax
0x1800408ff  js      loc_180040A92
0x180040905  mov     rax, [r15]
0x180040908  lea     rcx, [rbp+57h+var_A0]
0x18004090c  mov     r8d, [rbp+57h+var_90]
0x180040910  xor     r9d, r9d
0x180040913  mov     [rsp+0E0h+var_C0], rcx
0x180040918  mov     rdx, r14
0x18004091b  mov     rcx, r15
0x18004091e  mov     rax, [rax+18h]
0x180040922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040927  mov     ebx, eax
0x180040929  test    eax, eax
0x18004092b  js      loc_180040A07
0x180040931  mov     rax, [rdi]
0x180040934  lea     r8, [rbp+57h+var_60]
0x180040938  movaps  xmm0, [rbp+57h+var_50]
0x18004093c  mov     rcx, rdi
0x18004093f  mov     rdx, [rbp+57h+var_A0]
0x180040943  movdqa  [rbp+57h+var_60], xmm0
0x180040948  mov     rax, [rax+0C0h]
0x18004094f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040954  mov     ebx, eax
0x180040956  test    eax, eax
0x180040958  js      short loc_18004097C
0x18004095a  lea     rcx, [rbp+57h+var_80]
0x18004095e  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180040963  lea     rcx, [rbp+57h+var_A8]
0x180040967  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18004096c  lea     rcx, [rbp+57h+var_A0]
0x180040970  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180040975  inc     esi
0x180040977  jmp     loc_180040858
0x18004097c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040983  test    rcx, rcx
0x180040986  jnz     short loc_1800409C9
0x180040988  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004098e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040995  mov     rcx, rax
0x180040998  test    rax, rax
0x18004099b  jz      short loc_1800409BB
0x18004099d  mov     rax, [rax]
0x1800409a0  mov     edx, 7F0h
0x1800409a5  mov     rax, [rax+8]
0x1800409a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409ae  test    eax, eax
0x1800409b0  jz      short loc_1800409BB
0x1800409b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409b9  jmp     short loc_1800409C9
0x1800409bb  lea     rcx, qword_18006EB20; this
0x1800409c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409c9  cmp     [rcx+8], r12b
0x1800409cd  jz      short loc_1800409F0
0x1800409cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800409d4  cmp     [rax+7CCh], ebx
0x1800409da  jz      short loc_1800409F0
0x1800409dc  mov     r9d, ebx; int
0x1800409df  mov     r8d, 6C2h; int
0x1800409e5  mov     rdx, r13; char *
0x1800409e8  mov     rcx, rax; this
0x1800409eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800409f0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800409f5  cmp     al, 1
0x1800409f7  jb      loc_180040C48
0x1800409fd  mov     edx, 94h
0x180040a02  jmp     loc_180040C2A
0x180040a07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a0e  test    rcx, rcx
0x180040a11  jnz     short loc_180040A54
0x180040a13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040a19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a20  mov     rcx, rax
0x180040a23  test    rax, rax
0x180040a26  jz      short loc_180040A46
0x180040a28  mov     rax, [rax]
0x180040a2b  mov     edx, 7F0h
0x180040a30  mov     rax, [rax+8]
0x180040a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a39  test    eax, eax
0x180040a3b  jz      short loc_180040A46
0x180040a3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a44  jmp     short loc_180040A54
0x180040a46  lea     rcx, qword_18006EB20; this
0x180040a4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a54  cmp     [rcx+8], r12b
0x180040a58  jz      short loc_180040A7B
0x180040a5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180040a5f  cmp     [rax+7CCh], ebx
0x180040a65  jz      short loc_180040A7B
0x180040a67  mov     r9d, ebx; int
0x180040a6a  mov     r8d, 6C0h; int
0x180040a70  mov     rdx, r13; char *
0x180040a73  mov     rcx, rax; this
0x180040a76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180040a7b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040a80  cmp     al, 1
0x180040a82  jb      loc_180040C48
0x180040a88  mov     edx, 93h
0x180040a8d  jmp     loc_180040C2A
0x180040a92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
