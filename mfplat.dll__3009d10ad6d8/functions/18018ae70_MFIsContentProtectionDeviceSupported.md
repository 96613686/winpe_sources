# MFIsContentProtectionDeviceSupported

- ea: `0x18018ae70`
- end: `0x18018b85a`
- name: `MFIsContentProtectionDeviceSupported`
- size: `2538`
- prototype: `HRESULT __stdcall(const GUID *const ProtectionSystemId, BOOL *isSupported)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000243c`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180082e30`
- `0x1800a0a24`
- `0x1800a0bdc`
- `0x1800ae824`
- `0x1800b095c`
- `0x1800bd40c`
- `0x18011fff0`
- `0x1801200d0`
- `0x1801200f4`
- `0x180125918`
- `0x180128588`
- `0x180130b70`
- `0x1801893d4`
- `0x1801896bc`
- `0x18018ae70`
- `0x18018b860`
- `0x18018b9cc`
- `0x18018c0a0`
- `0x18018c4d8`
- `0x18018d164`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18018b293`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18018b293`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18018b0e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18018b0e2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18018b54d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18018b54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018b55b`

## pseudocode

```c
HRESULT __stdcall MFIsContentProtectionDeviceSupported(const GUID *const ProtectionSystemId, BOOL *isSupported)
{
  bool v2; // zf
  char v4; // r14
  int v5; // edx
  signed int v6; // eax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  signed int v9; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  unsigned int v12; // ecx
  struct IMFContentDecryptorContext *v13; // r8
  struct CallStackContext *v14; // rax
  GUID *v15; // rax
  GUID *v16; // rdi
  HANDLE v17; // rbx
  signed int LastError; // eax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  DWORD v24; // eax
  DWORD v25; // edi
  unsigned int DriverDetailsForTelemetry; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // ebx
  unsigned int v30; // edi
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  signed int v36; // eax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  signed int v40; // eax
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  _BOOL8 v46; // r8
  struct CallStackContext *v47; // rax
  CallStackScopeTrace v49; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v50; // [rsp+44h] [rbp-25h] BYREF
  HANDLE v51; // [rsp+48h] [rbp-21h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp-19h] BYREF
  DWORD ExitCode; // [rsp+54h] [rbp-15h] BYREF
  unsigned int v54; // [rsp+58h] [rbp-11h] BYREF
  union _LARGE_INTEGER v55; // [rsp+60h] [rbp-9h] BYREF
  struct IMFContentProtectionDevice *v56; // [rsp+68h] [rbp-1h] BYREF
  union _LARGE_INTEGER v57; // [rsp+70h] [rbp+7h] BYREF
  GUID iid; // [rsp+78h] [rbp+Fh] BYREF

  v2 = *(_QWORD *)&ProtectionSystemId->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  iid = *ProtectionSystemId;
  v56 = 0;
  v4 = 0;
  if ( v2 && *(_QWORD *)ProtectionSystemId->Data4 == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    GetProtectionSystemID(&iid);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0j_EventWriteTransfer(
      Microsoft_Windows_MediaFoundation_Performance_Context,
      MFIsContentProtectionDeviceSupported_Start,
      &iid);
  CallStackScopeTrace::CallStackScopeTrace(&v49, "MFIsContentProtectionDeviceSupported", 253);
  if ( !isSupported )
  {
    v6 = MF::OriginateError((MF *)0x80070057LL, v5);
    v8 = CallStackTracing::s_wpInstance;
    v9 = v6;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v9 < 0 && ThreadRelativeContext->m_result != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFIsContentProtectionDeviceSupported", 253, v9);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v11 = 16;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, 0, v9);
      goto LABEL_132;
    }
    goto LABEL_132;
  }
  v9 = 0;
  *isSupported = 0;
  if ( !(unsigned __int8)EnableHWDRM() )
    goto LABEL_132;
  if ( !EnableSimulation(0, 0, 0) )
  {
    if ( (int)CMFTrEEDriver::CreateInstance(1u, &iid, v13, &v56) >= 0 )
      goto LABEL_131;
    v15 = (GUID *)operator new(0x10u);
    v16 = v15;
    if ( !v15 )
    {
      v8 = CallStackTracing::s_wpInstance;
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v8 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v8->m_fEnabled )
      {
        v47 = CallStackTracing::GetThreadRelativeContext(v8);
        if ( v47->m_result != -2147024882 )
          CallStackContext::TraceFailure(v47, "MFIsContentProtectionDeviceSupported", 267, -2147024882);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v11 = 18;
        goto LABEL_17;
      }
      goto LABEL_132;
    }
    *v15 = iid;
    ThreadId = 0;
    v17 = CreateThread(0, 0, CryptoSessionTestThreadProc, v15, 0, &ThreadId);
    v51 = v17;
    if ( (((unsigned __int64)v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      operator delete(v16, (const struct std::nothrow_t *)0x10);
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v19 = CallStackTracing::s_wpInstance;
      if ( v9 < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v19 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v19->m_fEnabled )
        {
          v20 = CallStackTracing::GetThreadRelativeContext(v19);
          if ( v20->m_result != v9 )
            CallStackContext::TraceFailure(v20, "MFIsContentProtectionDeviceSupported", 273, v9);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_46;
        v21 = 19;
        goto LABEL_45;
      }
      v9 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v19->m_fEnabled )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( v22->m_result != -1072875845 )
          CallStackContext::TraceFailure(v22, "MFIsContentProtectionDeviceSupported", 274, -1072875845);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_46;
      v23 = 20;
LABEL_56:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids,
        0,
        -1072875845);
      goto LABEL_46;
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 4u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, ThreadId);
    v24 = WaitForSingleObject(v17, 0x2710u);
    v25 = v24;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 4u )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids,
        ThreadId,
        v24);
    if ( v25 == 258 )
    {
      v55.QuadPart = 0;
      v50 = 0;
      DriverDetailsForTelemetry = GetDriverDetailsForTelemetry(&v50, &v55);
      v29 = DriverDetailsForTelemetry;
      v30 = v50;
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 4u )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))WPP_SF_DDi)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v27,
          v28,
          DriverDetailsForTelemetry,
          v50,
          (union _LARGE_INTEGER)v55.QuadPart);
      if ( (unsigned int)dword_1801F8368 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801F8368, 0x400000000000LL) )
      {
        v57 = v55;
        v50 = v29;
        v54 = v30;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v31,
          (unsigned int)byte_1801E70C3,
          v32,
          v33,
          (__int64)&v54,
          (__int64)&v57,
          (__int64)&v50);
      }
      v34 = CallStackTracing::s_wpInstance;
      v4 = 1;
      v9 = -2147417825;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v34->m_fEnabled )
      {
        v35 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( v35->m_result != -2147417825 )
          CallStackContext::TraceFailure(v35, "MFIsContentProtectionDeviceSupported", 298, -2147417825);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_46;
      v21 = 24;
    }
    else if ( v25 )
    {
      v36 = GetLastError();
      v9 = v36;
      if ( v36 > 0 )
        v9 = (unsigned __int16)v36 | 0x80070000;
      v37 = CallStackTracing::s_wpInstance;
      if ( v9 >= 0 )
      {
        v9 = -1072875845;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v37 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v37->m_fEnabled )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( v39->m_result != -1072875845 )
            CallStackContext::TraceFailure(v39, "MFIsContentProtectionDeviceSupported", 303, -1072875845);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_46;
        v23 = 26;
        goto LABEL_56;
      }
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v37->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v37);
        if ( v38->m_result != v9 )
          CallStackContext::TraceFailure(v38, "MFIsContentProtectionDeviceSupported", 302, v9);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_46;
      v21 = 25;
    }
    else
    {
      ExitCode = 0;
      if ( GetExitCodeThread(v17, &ExitCode) )
      {
        v9 = ExitCode;
        if ( (ExitCode & 0x80000000) == 0 )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
          goto LABEL_131;
        }
        v44 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v44 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v44->m_fEnabled )
        {
          v45 = CallStackTracing::GetThreadRelativeContext(v44);
          if ( v45->m_result != v9 )
            CallStackContext::TraceFailure(v45, "MFIsContentProtectionDeviceSupported", 312, v9);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
LABEL_46:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
          goto LABEL_132;
        }
        v21 = 29;
      }
      else
      {
        v40 = GetLastError();
        v9 = v40;
        if ( v40 > 0 )
          v9 = (unsigned __int16)v40 | 0x80070000;
        v41 = CallStackTracing::s_wpInstance;
        if ( v9 >= 0 )
        {
          v9 = -1072875845;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v41 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v41 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v41->m_fEnabled )
          {
            v43 = CallStackTracing::GetThreadRelativeContext(v41);
            if ( v43->m_result != -1072875845 )
              CallStackContext::TraceFailure(v43, "MFIsContentProtectionDeviceSupported", 310, -1072875845);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_46;
          v23 = 28;
          goto LABEL_56;
        }
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v41 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v41->m_fEnabled )
        {
          v42 = CallStackTracing::GetThreadRelativeContext(v41);
          if ( v42->m_result != v9 )
            CallStackContext::TraceFailure(v42, "MFIsContentProtectionDeviceSupported", 309, v9);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_46;
        v21 = 27;
      }
    }
LABEL_45:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, 0, v9);
    goto LABEL_46;
  }
  v9 = CMFSimulatedContentProtectionDevice::CreateInstance(v12, &iid, v13, &v56);
  if ( v9 >= 0 )
  {
LABEL_131:
    *isSupported = 1;
    goto LABEL_132;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v8 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v8->m_fEnabled )
  {
    v14 = CallStackTracing::GetThreadRelativeContext(v8);
    if ( v14->m_result != v9 )
      CallStackContext::TraceFailure(v14, "MFIsContentProtectionDeviceSupported", 260, v9);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v11 = 17;
    goto LABEL_17;
  }
LABEL_132:
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    if ( isSupported )
      v46 = *isSupported;
    else
      v46 = 0;
    McTemplateU0tq_EventWriteTransfer(v8, v7, v46, (unsigned int)v9);
  }
  if ( !v4 && v9 < 0 && isSupported )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids);
    v9 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v49);
  ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v56);
  return v9;
}

```

## disassembly

```asm
0x18018ae70  mov     [rsp-8+arg_10], rbx
0x18018ae75  push    rbp
0x18018ae76  push    rsi
0x18018ae77  push    rdi
0x18018ae78  push    r12
0x18018ae7a  push    r13
0x18018ae7c  push    r14
0x18018ae7e  push    r15
0x18018ae80  lea     rbp, [rsp-27h]
0x18018ae85  sub     rsp, 90h
0x18018ae8c  mov     rax, cs:__security_cookie
0x18018ae93  xor     rax, rsp
0x18018ae96  mov     [rbp+57h+var_38], rax
0x18018ae9a  movups  xmm0, xmmword ptr [rcx]
0x18018ae9d  mov     rax, [rcx]
0x18018aea0  xor     r15d, r15d
0x18018aea3  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18018aeaa  mov     rsi, rdx
0x18018aead  movdqu  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18018aeb2  mov     [rbp+57h+var_58], r15
0x18018aeb6  mov     r14b, r15b
0x18018aeb9  jnz     short loc_18018AED1
0x18018aebb  mov     rax, [rcx+8]
0x18018aebf  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18018aec6  jnz     short loc_18018AED1
0x18018aec8  lea     rcx, [rbp+57h+iid]; lpiid
0x18018aecc  call    GetProtectionSystemID
0x18018aed1  mov     r12d, 1
0x18018aed7  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, r12b
0x18018aede  jz      short loc_18018AEF7
0x18018aee0  lea     r8, [rbp+57h+iid]
0x18018aee4  lea     rdx, MFIsContentProtectionDeviceSupported_Start
0x18018aeeb  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Context
0x18018aef2  call    McTemplateU0j_EventWriteTransfer
0x18018aef7  mov     edi, 0FDh
0x18018aefc  lea     r13, aMfiscontentpro_0; "MFIsContentProtectionDeviceSupported"
0x18018af03  mov     r8d, edi; int
0x18018af06  lea     rcx, [rbp+57h+var_80]; this
0x18018af0a  mov     rdx, r13; char *
0x18018af0d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18018af12  test    rsi, rsi
0x18018af15  jnz     loc_18018AFCE
0x18018af1b  mov     ecx, 80070057h; this
0x18018af20  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18018af25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018af2c  mov     ebx, eax
0x18018af2e  test    rcx, rcx
0x18018af31  jnz     short loc_18018AF71
0x18018af33  mov     rdx, cs:stru_1801FC290.__vftable
0x18018af3a  lea     rcx, stru_1801FC290
0x18018af41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018af48  mov     rax, [rdx+8]
0x18018af4c  mov     edx, 7F0h
0x18018af51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018af56  test    eax, eax
0x18018af58  jnz     short loc_18018AF6A
0x18018af5a  lea     rcx, stru_1801F8A30
0x18018af61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018af68  jmp     short loc_18018AF71
0x18018af6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018af71  cmp     [rcx+8], r15b
0x18018af75  jz      short loc_18018AF99
0x18018af77  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018af7c  test    ebx, ebx
0x18018af7e  jns     short loc_18018AF99
0x18018af80  cmp     [rax+7CCh], ebx
0x18018af86  jz      short loc_18018AF99
0x18018af88  mov     r9d, ebx; int
0x18018af8b  mov     r8d, edi; int
0x18018af8e  mov     rdx, r13; char *
0x18018af91  mov     rcx, rax; this
0x18018af94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018af99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18018afa0  jb      loc_18018B733
0x18018afa6  mov     edx, 10h
0x18018afab  mov     rcx, cs:WPP_GLOBAL_Control
0x18018afb2  lea     r8, WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids
0x18018afb9  xor     r9d, r9d
0x18018afbc  mov     [rsp+0C0h+dwCreationFlags], ebx
0x18018afc0  mov     rcx, [rcx+10h]
0x18018afc4  call    WPP_SF_qD
0x18018afc9  jmp     loc_18018B733
0x18018afce  mov     ebx, r15d
0x18018afd1  mov     [rsi], r15d
0x18018afd4  call    EnableHWDRM
0x18018afd9  test    al, al
0x18018afdb  jz      loc_18018B733
0x18018afe1  xor     r8d, r8d; bool *
0x18018afe4  xor     edx, edx; unsigned int
0x18018afe6  xor     ecx, ecx; pvData
0x18018afe8  call    ?EnableSimulation@@YA_NPEAEKPEA_N@Z; EnableSimulation(uchar *,ulong,bool *)
0x18018afed  lea     r9, [rbp+57h+var_58]; struct IMFContentProtectionDevice **
0x18018aff1  lea     rdx, [rbp+57h+iid]; struct _GUID *
0x18018aff5  test    al, al
0x18018aff7  jz      loc_18018B094
0x18018affd  call    ?CreateInstance@CMFSimulatedContentProtectionDevice@@SAJKAEBU_GUID@@PEAUIMFContentDecryptorContext@@PEAPEAUIMFContentProtectionDevice@@@Z; CMFSimulatedContentProtectionDevice::CreateInstance(ulong,_GUID const &,IMFContentDecryptorContext *,IMFContentProtectionDevice * *)
0x18018b002  mov     ebx, eax
0x18018b004  test    eax, eax
0x18018b006  jns     loc_18018B730
0x18018b00c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b013  test    rcx, rcx
0x18018b016  jnz     short loc_18018B056
0x18018b018  mov     rax, cs:stru_1801FC290.__vftable
0x18018b01f  lea     rcx, stru_1801FC290
0x18018b026  mov     edx, 7F0h
0x18018b02b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b032  mov     rax, [rax+8]
0x18018b036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b03b  test    eax, eax
0x18018b03d  jnz     short loc_18018B04F
0x18018b03f  lea     rcx, stru_1801F8A30
0x18018b046  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b04d  jmp     short loc_18018B056
0x18018b04f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018b056  cmp     [rcx+8], r15b
0x18018b05a  jz      short loc_18018B07D
0x18018b05c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018b061  cmp     [rax+7CCh], ebx
0x18018b067  jz      short loc_18018B07D
0x18018b069  mov     r9d, ebx; int
0x18018b06c  mov     r8d, 104h; int
0x18018b072  mov     rdx, r13; char *
0x18018b075  mov     rcx, rax; this
0x18018b078  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018b07d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18018b084  jb      loc_18018B733
0x18018b08a  mov     edx, 11h
0x18018b08f  jmp     loc_18018AFAB
0x18018b094  mov     ecx, r12d; unsigned int
0x18018b097  call    ?CreateInstance@CMFTrEEDriver@@SAJKAEBU_GUID@@PEAUIMFContentDecryptorContext@@PEAPEAUIMFContentProtectionDevice@@@Z; CMFTrEEDriver::CreateInstance(ulong,_GUID const &,IMFContentDecryptorContext *,IMFContentProtectionDevice * *)
0x18018b09c  test    eax, eax
0x18018b09e  jns     loc_18018B730
0x18018b0a4  mov     ecx, 10h; Size
0x18018b0a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018b0ae  mov     rdi, rax
0x18018b0b1  test    rax, rax
0x18018b0b4  jz      loc_18018B751
0x18018b0ba  movups  xmm0, xmmword ptr [rbp+57h+iid.Data1]
0x18018b0be  mov     r9, rdi; lpParameter
0x18018b0c1  lea     r8, CryptoSessionTestThreadProc; lpStartAddress
0x18018b0c8  xor     edx, edx; dwStackSize
0x18018b0ca  xor     ecx, ecx; lpThreadAttributes
0x18018b0cc  movdqu  xmmword ptr [rax], xmm0
0x18018b0d0  lea     rax, [rbp+57h+ThreadId]
0x18018b0d4  mov     [rbp+57h+ThreadId], r15d
0x18018b0d8  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x18018b0dd  mov     [rsp+0C0h+dwCreationFlags], r15d; dwCreationFlags
0x18018b0e2  call    cs:__imp_CreateThread
0x18018b0e8  mov     rbx, rax
0x18018b0eb  mov     [rbp+57h+var_78], rax
0x18018b0ef  inc     rax
0x18018b0f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18018b0f8  jnz     loc_18018B25F
0x18018b0fe  mov     edx, 10h; struct std::nothrow_t *
0x18018b103  mov     rcx, rdi; void *
0x18018b106  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018b10b  call    cs:__imp_GetLastError
0x18018b111  mov     ebx, eax
0x18018b113  test    eax, eax
0x18018b115  jle     short loc_18018B120
0x18018b117  movzx   ebx, ax
0x18018b11a  or      ebx, 80070000h
0x18018b120  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b127  test    ebx, ebx
0x18018b129  jns     loc_18018B1D3
0x18018b12f  test    rcx, rcx
0x18018b132  jnz     short loc_18018B172
0x18018b134  mov     rax, cs:stru_1801FC290.__vftable
0x18018b13b  lea     rcx, stru_1801FC290
0x18018b142  mov     edx, 7F0h
0x18018b147  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b14e  mov     rax, [rax+8]
0x18018b152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b157  test    eax, eax
0x18018b159  jnz     short loc_18018B16B
0x18018b15b  lea     rcx, stru_1801F8A30
0x18018b162  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b169  jmp     short loc_18018B172
0x18018b16b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018b172  cmp     [rcx+8], r15b
0x18018b176  jz      short loc_18018B199
0x18018b178  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018b17d  cmp     [rax+7CCh], ebx
0x18018b183  jz      short loc_18018B199
0x18018b185  mov     r9d, ebx; int
0x18018b188  mov     r8d, 111h; int
0x18018b18e  mov     rdx, r13; char *
0x18018b191  mov     rcx, rax; this
0x18018b194  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018b199  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18018b1a0  jb      short loc_18018B1C5
0x18018b1a2  mov     edx, 13h
0x18018b1a7  mov     [rsp+0C0h+dwCreationFlags], ebx
0x18018b1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18018b1b2  lea     r8, WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids
0x18018b1b9  xor     r9d, r9d
0x18018b1bc  mov     rcx, [rcx+10h]
0x18018b1c0  call    WPP_SF_qD
0x18018b1c5  lea     rcx, [rbp+57h+var_78]
0x18018b1c9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18018b1ce  jmp     loc_18018B733
0x18018b1d3  mov     edi, 0C00D36BBh
0x18018b1d8  mov     ebx, edi
0x18018b1da  test    rcx, rcx
0x18018b1dd  jnz     short loc_18018B21D
0x18018b1df  mov     rax, cs:stru_1801FC290.__vftable
0x18018b1e6  lea     rcx, stru_1801FC290
0x18018b1ed  mov     edx, 7F0h
0x18018b1f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b1f9  mov     rax, [rax+8]
0x18018b1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b202  test    eax, eax
0x18018b204  jnz     short loc_18018B216
0x18018b206  lea     rcx, stru_1801F8A30
0x18018b20d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b214  jmp     short loc_18018B21D
0x18018b216  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18018b21d  cmp     [rcx+8], r15b
0x18018b221  jz      short loc_18018B244
0x18018b223  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018b228  cmp     [rax+7CCh], edi
0x18018b22e  jz      short loc_18018B244
0x18018b230  mov     r9d, edi; int
0x18018b233  mov     r8d, 112h; int
0x18018b239  mov     rdx, r13; char *
0x18018b23c  mov     rcx, rax; this
0x18018b23f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018b244  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18018b24b  jb      loc_18018B1C5
0x18018b251  mov     edx, 14h
0x18018b256  mov     [rsp+0C0h+dwCreationFlags], edi
0x18018b25a  jmp     loc_18018B1AB
0x18018b25f  mov     r13b, 4
0x18018b262  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18018b269  jb      short loc_18018B28B
0x18018b26b  mov     rcx, cs:WPP_GLOBAL_Control
0x18018b272  lea     r8, WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids
0x18018b279  mov     r9d, [rbp+57h+ThreadId]
0x18018b27d  mov     edx, 15h
0x18018b282  mov     rcx, [rcx+10h]
0x18018b286  call    WPP_SF_d
0x18018b28b  mov     edx, 2710h; dwMilliseconds
0x18018b290  mov     rcx, rbx; hHandle
0x18018b293  call    cs:__imp_WaitForSingleObject
0x18018b299  mov     edi, eax
0x18018b29b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18018b2a2  jb      short loc_18018B2C8
0x18018b2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18018b2ab  lea     r8, WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids
0x18018b2b2  mov     r9d, [rbp+57h+ThreadId]
0x18018b2b6  mov     edx, 16h
0x18018b2bb  mov     [rsp+0C0h+dwCreationFlags], eax
0x18018b2bf  mov     rcx, [rcx+10h]
0x18018b2c3  call    WPP_SF_Dd
0x18018b2c8  cmp     edi, 102h
0x18018b2ce  jnz     loc_18018B405
0x18018b2d4  lea     rdx, [rbp+57h+var_60]; union _LARGE_INTEGER *
0x18018b2d8  mov     qword ptr [rbp+57h+var_60], r15
0x18018b2dc  lea     rcx, [rbp+57h+var_7C]; unsigned int *
0x18018b2e0  mov     [rbp+57h+var_7C], r15d
0x18018b2e4  call    ?GetDriverDetailsForTelemetry@@YAJPEAIPEAT_LARGE_INTEGER@@@Z; GetDriverDetailsForTelemetry(uint *,_LARGE_INTEGER *)
0x18018b2e9  mov     ebx, eax
0x18018b2eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18018b2f2  mov     edi, [rbp+57h+var_7C]
0x18018b2f5  jb      short loc_18018B317
0x18018b2f7  mov     rcx, qword ptr [rbp+57h+var_60]
0x18018b2fb  mov     r9d, eax
0x18018b2fe  mov     [rsp+0C0h+lpThreadId], rcx
0x18018b303  mov     rcx, cs:WPP_GLOBAL_Control
0x18018b30a  mov     [rsp+0C0h+dwCreationFlags], edi
0x18018b30e  mov     rcx, [rcx+10h]
0x18018b312  call    WPP_SF_DDi
0x18018b317  mov     eax, cs:dword_1801F8368
0x18018b31d  cmp     eax, 5
0x18018b320  jbe     short loc_18018B371
0x18018b322  mov     rdx, 400000000000h
0x18018b32c  lea     rcx, dword_1801F8368
0x18018b333  call    _tlgKeywordOn
0x18018b338  test    al, al
0x18018b33a  jz      short loc_18018B371
0x18018b33c  mov     rax, qword ptr [rbp+57h+var_60]
0x18018b340  lea     rdx, byte_1801E70C3
0x18018b347  mov     [rbp+57h+var_50], rax
0x18018b34b  lea     rax, [rbp+57h+var_7C]
0x18018b34f  mov     [rsp+0C0h+var_90], rax
0x18018b354  lea     rax, [rbp+57h+var_50]
0x18018b358  mov     [rsp+0C0h+lpThreadId], rax
0x18018b35d  lea     rax, [rbp+57h+var_68]
0x18018b361  mov     qword ptr [rsp+0C0h+dwCreationFlags], rax
0x18018b366  mov     [rbp+57h+var_7C], ebx
0x18018b369  mov     [rbp+57h+var_68], edi
0x18018b36c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18018b371  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018b378  mov     r14b, r12b
0x18018b37b  mov     ebx, 8001011Fh
0x18018b380  test    rcx, rcx
0x18018b383  jnz     short loc_18018B3C3
0x18018b385  mov     rax, cs:stru_1801FC290.__vftable
0x18018b38c  lea     rcx, stru_1801FC290
0x18018b393  mov     edx, 7F0h
  ... truncated ...
```
