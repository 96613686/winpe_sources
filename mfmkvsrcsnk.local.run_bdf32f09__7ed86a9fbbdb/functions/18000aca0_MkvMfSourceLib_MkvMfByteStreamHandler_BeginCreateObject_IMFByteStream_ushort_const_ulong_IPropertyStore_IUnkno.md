# MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x18000aca0`
- end: `0x18000b3c8`
- name: `?BeginCreateObject@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU5@@Z`
- size: `1832`
- prototype: `int(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000aca0`
- `0x18000e060`
- `0x18001065c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b3ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000acf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ad79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000adfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ae8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000af0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000afb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b02f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b0c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b163`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b1fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b281`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b31d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000acf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ad79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000adfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000ae8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000af0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000afb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b02f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b0c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b163`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b1fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b281`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b31d`
- `MFPlat!MFCreateAsyncResult` at `0x18000b1e3`
- `MFPlat!MFCreateAsyncResult` at `0x18000b1e3`

## string_xrefs

- `0x18000b37a`: `MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject(
        struct IMFTelemetrySession **this,
        struct IMFByteStream *a2,
        const unsigned __int16 *a3,
        char a4,
        struct IPropertyStore *a5,
        struct IUnknown **a6,
        struct IMFAsyncCallback *pCallback,
        struct IUnknown *punkState)
{
  struct _RTL_CRITICAL_SECTION *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  HRESULT v15; // ebx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v19; // r9d
  int v20; // r8d
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct MkvMfSourceLib::MkvMfSource *v44; // rbx
  __int64 (__fastcall *v45)(struct MkvMfSourceLib::MkvMfSource *, GUID *, IUnknown **); // rdi
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  IMFAsyncResult *ppAsyncResult; // [rsp+20h] [rbp-20h] BYREF
  IUnknown *punkObject; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v69[2]; // [rsp+30h] [rbp-10h] BYREF
  int v70; // [rsp+70h] [rbp+30h] BYREF
  struct MkvMfSourceLib::MkvMfSource *v71; // [rsp+78h] [rbp+38h] BYREF

  v11 = (struct _RTL_CRITICAL_SECTION *)(this + 7);
  v69[1] = this + 7;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 7));
  ppAsyncResult = 0;
  v71 = 0;
  punkObject = 0;
  if ( !a2 )
  {
    v15 = -2147024809;
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
      {
        v19 = -2147024809;
        v20 = 35;
LABEL_112:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject",
          v20,
          v19);
        goto LABEL_113;
      }
    }
    goto LABEL_113;
  }
  if ( pCallback )
  {
    if ( (a4 & 1) == 0 )
    {
      v15 = -2147024809;
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        {
          v19 = -2147024809;
          v20 = 41;
          goto LABEL_112;
        }
      }
      goto LABEL_113;
    }
    v70 = 0;
    v15 = ((__int64 (__fastcall *)(struct IMFByteStream *, int *))a2->lpVtbl->GetCapabilities)(a2, &v70);
    if ( v15 < 0 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( !*((_BYTE *)v28 + 8) )
        goto LABEL_113;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
        goto LABEL_113;
      v20 = 46;
      goto LABEL_111;
    }
    if ( (v70 & 1) == 0 )
    {
      v15 = -2147024809;
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        {
          v19 = -2147024809;
          v20 = 50;
          goto LABEL_112;
        }
      }
      goto LABEL_113;
    }
    v69[0] = 0;
    v15 = ((__int64 (__fastcall *)(struct IMFByteStream *, _QWORD *))a2->lpVtbl->GetLength)(a2, v69);
    if ( v15 < 0 )
    {
      if ( v15 != -1072875781 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( !*((_BYTE *)v37 + 8) )
          goto LABEL_113;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
          goto LABEL_113;
        v20 = 66;
LABEL_111:
        v19 = v15;
        goto LABEL_112;
      }
    }
    else if ( !v69[0] )
    {
      v15 = -1072875842;
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( !*((_BYTE *)v35 + 8) )
        goto LABEL_113;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == -1072875842 )
        goto LABEL_113;
      v20 = 61;
      goto LABEL_111;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
    v15 = MkvMfSourceLib::MkvMfSource::CreateSource(a2, this[12], &v71);
    if ( v15 >= 0 )
    {
      v44 = v71;
      v45 = **(__int64 (__fastcall ***)(struct MkvMfSourceLib::MkvMfSource *, GUID *, IUnknown **))v71;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkObject);
      v15 = v45(v44, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66, &punkObject);
      if ( v15 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
        v15 = MFCreateAsyncResult(punkObject, pCallback, punkState, &ppAsyncResult);
        if ( v15 >= 0 )
        {
          v15 = MkvMfSourceLib::MkvMfSource::BeginLoad(v71, ppAsyncResult);
          if ( v15 >= 0 )
          {
            if ( !a6 )
              goto LABEL_113;
            v15 = ((__int64 (__fastcall *)(IMFAsyncResult *, GUID *))ppAsyncResult->lpVtbl->QueryInterface)(
                    ppAsyncResult,
                    &GUID_00000000_0000_0000_c000_000000000046);
            if ( v15 >= 0 )
              goto LABEL_113;
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
            if ( !*((_BYTE *)v64 + 8) )
              goto LABEL_113;
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
            if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
              goto LABEL_113;
            v20 = 79;
          }
          else
          {
            v59 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
              CallStackTracing::s_wpInstance = v60;
              if ( v60
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
              {
                v59 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v59 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( !*((_BYTE *)v59 + 8) )
              goto LABEL_113;
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
            if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
              goto LABEL_113;
            v20 = 75;
          }
        }
        else
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v54 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v54 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( !*((_BYTE *)v54 + 8) )
            goto LABEL_113;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
            goto LABEL_113;
          v20 = 73;
        }
      }
      else
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( !*((_BYTE *)v49 + 8) )
          goto LABEL_113;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
          goto LABEL_113;
        v20 = 72;
      }
    }
    else
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( !*((_BYTE *)v42 + 8) )
        goto LABEL_113;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v15 )
        goto LABEL_113;
      v20 = 70;
    }
    goto LABEL_111;
  }
  v15 = -2147024809;
  v21 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
    {
      v19 = -2147024809;
      v20 = 36;
      goto LABEL_112;
    }
  }
LABEL_113:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkObject);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
  LeaveCriticalSection(v11);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000aca0  mov     [rsp-28h+arg_10], rbx
0x18000aca5  push    rbp
0x18000aca6  push    rdi
0x18000aca7  push    r12
0x18000aca9  push    r14
0x18000acab  push    r15
0x18000acad  mov     rbp, rsp
0x18000acb0  sub     rsp, 40h
0x18000acb4  mov     ebx, r9d
0x18000acb7  mov     rdi, rdx
0x18000acba  mov     r14, rcx
0x18000acbd  lea     r15, [rcx+38h]
0x18000acc1  mov     [rbp+var_8], r15
0x18000acc5  mov     rcx, r15; lpCriticalSection
0x18000acc8  call    cs:__imp_EnterCriticalSection
0x18000acce  nop
0x18000accf  xor     r12d, r12d
0x18000acd2  mov     [rbp+ppAsyncResult], r12
0x18000acd6  mov     [rbp+arg_8], r12
0x18000acda  mov     [rbp+punkObject], r12
0x18000acde  test    rdi, rdi
0x18000ace1  jnz     short loc_18000AD60
0x18000ace3  mov     edi, 80070057h
0x18000ace8  mov     ebx, edi
0x18000acea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000acf1  test    rcx, rcx
0x18000acf4  jnz     short loc_18000AD37
0x18000acf6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000acfc  mov     rcx, rax
0x18000acff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ad06  test    rax, rax
0x18000ad09  jz      short loc_18000AD29
0x18000ad0b  mov     rax, [rax]
0x18000ad0e  mov     edx, 7F0h
0x18000ad13  mov     rax, [rax+8]
0x18000ad17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1c  test    eax, eax
0x18000ad1e  jz      short loc_18000AD29
0x18000ad20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ad27  jmp     short loc_18000AD37
0x18000ad29  lea     rcx, qword_1800D6F70; this
0x18000ad30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ad37  cmp     [rcx+8], r12b
0x18000ad3b  jz      loc_18000B38A
0x18000ad41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ad46  cmp     [rax+7CCh], edi
0x18000ad4c  jz      loc_18000B38A
0x18000ad52  mov     r9d, edi
0x18000ad55  mov     r8d, 23h ; '#'
0x18000ad5b  jmp     loc_18000B37A
0x18000ad60  cmp     [rbp+pCallback], r12
0x18000ad64  jnz     short loc_18000ADE3
0x18000ad66  mov     edi, 80070057h
0x18000ad6b  mov     ebx, edi
0x18000ad6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ad74  test    rcx, rcx
0x18000ad77  jnz     short loc_18000ADBA
0x18000ad79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ad7f  mov     rcx, rax
0x18000ad82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ad89  test    rax, rax
0x18000ad8c  jz      short loc_18000ADAC
0x18000ad8e  mov     rax, [rax]
0x18000ad91  mov     edx, 7F0h
0x18000ad96  mov     rax, [rax+8]
0x18000ad9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9f  test    eax, eax
0x18000ada1  jz      short loc_18000ADAC
0x18000ada3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000adaa  jmp     short loc_18000ADBA
0x18000adac  lea     rcx, qword_1800D6F70; this
0x18000adb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000adba  cmp     [rcx+8], r12b
0x18000adbe  jz      loc_18000B38A
0x18000adc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000adc9  cmp     [rax+7CCh], edi
0x18000adcf  jz      loc_18000B38A
0x18000add5  mov     r9d, edi
0x18000add8  mov     r8d, 24h ; '$'
0x18000adde  jmp     loc_18000B37A
0x18000ade3  test    bl, 1
0x18000ade6  jnz     short loc_18000AE65
0x18000ade8  mov     edi, 80070057h
0x18000aded  mov     ebx, edi
0x18000adef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000adf6  test    rcx, rcx
0x18000adf9  jnz     short loc_18000AE3C
0x18000adfb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ae01  mov     rcx, rax
0x18000ae04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ae0b  test    rax, rax
0x18000ae0e  jz      short loc_18000AE2E
0x18000ae10  mov     rax, [rax]
0x18000ae13  mov     edx, 7F0h
0x18000ae18  mov     rax, [rax+8]
0x18000ae1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae21  test    eax, eax
0x18000ae23  jz      short loc_18000AE2E
0x18000ae25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ae2c  jmp     short loc_18000AE3C
0x18000ae2e  lea     rcx, qword_1800D6F70; this
0x18000ae35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ae3c  cmp     [rcx+8], r12b
0x18000ae40  jz      loc_18000B38A
0x18000ae46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000ae4b  cmp     [rax+7CCh], edi
0x18000ae51  jz      loc_18000B38A
0x18000ae57  mov     r9d, edi
0x18000ae5a  mov     r8d, 29h ; ')'
0x18000ae60  jmp     loc_18000B37A
0x18000ae65  mov     [rbp+arg_0], r12d
0x18000ae69  mov     rax, [rdi]
0x18000ae6c  lea     rdx, [rbp+arg_0]
0x18000ae70  mov     rcx, rdi
0x18000ae73  mov     rax, [rax+18h]
0x18000ae77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7c  mov     ebx, eax
0x18000ae7e  test    eax, eax
0x18000ae80  jns     short loc_18000AEF5
0x18000ae82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ae89  test    rcx, rcx
0x18000ae8c  jnz     short loc_18000AECF
0x18000ae8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000ae94  mov     rcx, rax
0x18000ae97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000ae9e  test    rax, rax
0x18000aea1  jz      short loc_18000AEC1
0x18000aea3  mov     rax, [rax]
0x18000aea6  mov     edx, 7F0h
0x18000aeab  mov     rax, [rax+8]
0x18000aeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb4  test    eax, eax
0x18000aeb6  jz      short loc_18000AEC1
0x18000aeb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aebf  jmp     short loc_18000AECF
0x18000aec1  lea     rcx, qword_1800D6F70; this
0x18000aec8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aecf  cmp     [rcx+8], r12b
0x18000aed3  jz      loc_18000B38A
0x18000aed9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000aede  cmp     [rax+7CCh], ebx
0x18000aee4  jz      loc_18000B38A
0x18000aeea  mov     r8d, 2Eh ; '.'
0x18000aef0  jmp     loc_18000B377
0x18000aef5  test    byte ptr [rbp+arg_0], 1
0x18000aef9  jnz     short loc_18000AF78
0x18000aefb  mov     edi, 80070057h
0x18000af00  mov     ebx, edi
0x18000af02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000af09  test    rcx, rcx
0x18000af0c  jnz     short loc_18000AF4F
0x18000af0e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000af14  mov     rcx, rax
0x18000af17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000af1e  test    rax, rax
0x18000af21  jz      short loc_18000AF41
0x18000af23  mov     rax, [rax]
0x18000af26  mov     edx, 7F0h
0x18000af2b  mov     rax, [rax+8]
0x18000af2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af34  test    eax, eax
0x18000af36  jz      short loc_18000AF41
0x18000af38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000af3f  jmp     short loc_18000AF4F
0x18000af41  lea     rcx, qword_1800D6F70; this
0x18000af48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000af4f  cmp     [rcx+8], r12b
0x18000af53  jz      loc_18000B38A
0x18000af59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000af5e  cmp     [rax+7CCh], edi
0x18000af64  jz      loc_18000B38A
0x18000af6a  mov     r9d, edi
0x18000af6d  mov     r8d, 32h ; '2'
0x18000af73  jmp     loc_18000B37A
0x18000af78  mov     [rbp+var_10], r12
0x18000af7c  mov     rax, [rdi]
0x18000af7f  lea     rdx, [rbp+var_10]
0x18000af83  mov     rcx, rdi
0x18000af86  mov     rax, [rax+20h]
0x18000af8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8f  mov     ebx, eax
0x18000af91  test    eax, eax
0x18000af93  js      loc_18000B01B
0x18000af99  cmp     [rbp+var_10], r12
0x18000af9d  jnz     loc_18000B096
0x18000afa3  mov     ebx, 0C00D36BEh
0x18000afa8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000afaf  test    rcx, rcx
0x18000afb2  jnz     short loc_18000AFF5
0x18000afb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000afba  mov     rcx, rax
0x18000afbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000afc4  test    rax, rax
0x18000afc7  jz      short loc_18000AFE7
0x18000afc9  mov     rax, [rax]
0x18000afcc  mov     edx, 7F0h
0x18000afd1  mov     rax, [rax+8]
0x18000afd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afda  test    eax, eax
0x18000afdc  jz      short loc_18000AFE7
0x18000afde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000afe5  jmp     short loc_18000AFF5
0x18000afe7  lea     rcx, qword_1800D6F70; this
0x18000afee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aff5  cmp     [rcx+8], r12b
0x18000aff9  jz      loc_18000B38A
0x18000afff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b004  cmp     [rax+7CCh], ebx
0x18000b00a  jz      loc_18000B38A
0x18000b010  mov     r8d, 3Dh ; '='
0x18000b016  jmp     loc_18000B377
0x18000b01b  cmp     ebx, 0C00D36FBh
0x18000b021  jz      short loc_18000B096
0x18000b023  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b02a  test    rcx, rcx
0x18000b02d  jnz     short loc_18000B070
0x18000b02f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b035  mov     rcx, rax
0x18000b038  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b03f  test    rax, rax
0x18000b042  jz      short loc_18000B062
0x18000b044  mov     rax, [rax]
0x18000b047  mov     edx, 7F0h
0x18000b04c  mov     rax, [rax+8]
0x18000b050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b055  test    eax, eax
0x18000b057  jz      short loc_18000B062
0x18000b059  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b060  jmp     short loc_18000B070
0x18000b062  lea     rcx, qword_1800D6F70; this
0x18000b069  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b070  cmp     [rcx+8], r12b
0x18000b074  jz      loc_18000B38A
0x18000b07a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b07f  cmp     [rax+7CCh], ebx
0x18000b085  jz      loc_18000B38A
0x18000b08b  mov     r8d, 42h ; 'B'
0x18000b091  jmp     loc_18000B377
0x18000b096  lea     rcx, [rbp+arg_8]
0x18000b09a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b09f  lea     r8, [rbp+arg_8]; struct MkvMfSourceLib::MkvMfSource **
0x18000b0a3  mov     rdx, [r14+60h]; struct IMFTelemetrySession *
0x18000b0a7  mov     rcx, rdi; struct IMFByteStream *
0x18000b0aa  call    ?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z; MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)
0x18000b0af  mov     ebx, eax
0x18000b0b1  test    eax, eax
0x18000b0b3  jns     short loc_18000B128
0x18000b0b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b0bc  test    rcx, rcx
0x18000b0bf  jnz     short loc_18000B102
0x18000b0c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b0c7  mov     rcx, rax
0x18000b0ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b0d1  test    rax, rax
0x18000b0d4  jz      short loc_18000B0F4
0x18000b0d6  mov     rax, [rax]
0x18000b0d9  mov     edx, 7F0h
0x18000b0de  mov     rax, [rax+8]
0x18000b0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e7  test    eax, eax
0x18000b0e9  jz      short loc_18000B0F4
0x18000b0eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b0f2  jmp     short loc_18000B102
0x18000b0f4  lea     rcx, qword_1800D6F70; this
0x18000b0fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b102  cmp     [rcx+8], r12b
0x18000b106  jz      loc_18000B38A
0x18000b10c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b111  cmp     [rax+7CCh], ebx
0x18000b117  jz      loc_18000B38A
0x18000b11d  mov     r8d, 46h ; 'F'
0x18000b123  jmp     loc_18000B377
0x18000b128  mov     rbx, [rbp+arg_8]
0x18000b12c  mov     rax, [rbx]
0x18000b12f  mov     rdi, [rax]
0x18000b132  lea     rcx, [rbp+punkObject]
0x18000b136  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b13b  lea     r8, [rbp+punkObject]
0x18000b13f  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x18000b146  mov     rcx, rbx
0x18000b149  mov     rax, rdi
0x18000b14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b151  mov     ebx, eax
0x18000b153  test    eax, eax
0x18000b155  jns     short loc_18000B1CA
0x18000b157  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b15e  test    rcx, rcx
0x18000b161  jnz     short loc_18000B1A4
0x18000b163  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b169  mov     rcx, rax
0x18000b16c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b173  test    rax, rax
0x18000b176  jz      short loc_18000B196
0x18000b178  mov     rax, [rax]
0x18000b17b  mov     edx, 7F0h
0x18000b180  mov     rax, [rax+8]
0x18000b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b189  test    eax, eax
0x18000b18b  jz      short loc_18000B196
0x18000b18d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
