# MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x18000b080`
- end: `0x18000b813`
- name: `?BeginCreateObject@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU5@@Z`
- size: `1939`
- prototype: `int(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000b080`
- `0x18000e670`
- `0x180010d70`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b0a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b0a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b0e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b1f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b31c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b3c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b449`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b4e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b589`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b6b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b75b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b0e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b1f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b31c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b3c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b449`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b4e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b589`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b6b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000b75b`
- `MFPlat!MFCreateAsyncResult` at `0x18000b60f`
- `MFPlat!MFCreateAsyncResult` at `0x18000b60f`

## string_xrefs

- `0x18000b7be`: `MkvMfSourceLib::MkvMfByteStreamHandler::BeginCreateObject`

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
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v23 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v28 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v37 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v35 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v64 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v59 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v54 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v49 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v42 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v21 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18000b080  mov     [rsp-28h+arg_10], rbx
0x18000b085  push    rbp
0x18000b086  push    rdi
0x18000b087  push    r12
0x18000b089  push    r14
0x18000b08b  push    r15
0x18000b08d  mov     rbp, rsp
0x18000b090  sub     rsp, 40h
0x18000b094  mov     ebx, r9d
0x18000b097  mov     rdi, rdx
0x18000b09a  mov     r14, rcx
0x18000b09d  lea     r15, [rcx+38h]
0x18000b0a1  mov     [rbp+var_8], r15
0x18000b0a5  mov     rcx, r15; lpCriticalSection
0x18000b0a8  call    cs:__imp_EnterCriticalSection
0x18000b0af  nop     dword ptr [rax+rax+00h]
0x18000b0b4  nop
0x18000b0b5  xor     r12d, r12d
0x18000b0b8  mov     [rbp+ppAsyncResult], r12
0x18000b0bc  mov     [rbp+arg_8], r12
0x18000b0c0  mov     [rbp+punkObject], r12
0x18000b0c4  test    rdi, rdi
0x18000b0c7  jnz     loc_18000B150
0x18000b0cd  mov     edi, 80070057h
0x18000b0d2  mov     ebx, edi
0x18000b0d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b0db  test    rcx, rcx
0x18000b0de  jnz     short loc_18000B127
0x18000b0e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b0e7  nop     dword ptr [rax+rax+00h]
0x18000b0ec  mov     rcx, rax
0x18000b0ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b0f6  test    rax, rax
0x18000b0f9  jz      short loc_18000B119
0x18000b0fb  mov     rax, [rax]
0x18000b0fe  mov     edx, 7F0h
0x18000b103  mov     rax, [rax+8]
0x18000b107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10c  test    eax, eax
0x18000b10e  jz      short loc_18000B119
0x18000b110  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b117  jmp     short loc_18000B127
0x18000b119  lea     rcx, qword_1800DBF70; this
0x18000b120  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b127  cmp     [rcx+8], r12b
0x18000b12b  jz      loc_18000B7CE
0x18000b131  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b136  cmp     [rax+7CCh], edi
0x18000b13c  jz      loc_18000B7CE
0x18000b142  mov     r9d, edi
0x18000b145  mov     r8d, 23h ; '#'
0x18000b14b  jmp     loc_18000B7BE
0x18000b150  cmp     [rbp+pCallback], r12
0x18000b154  jnz     loc_18000B1DD
0x18000b15a  mov     edi, 80070057h
0x18000b15f  mov     ebx, edi
0x18000b161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b168  test    rcx, rcx
0x18000b16b  jnz     short loc_18000B1B4
0x18000b16d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b174  nop     dword ptr [rax+rax+00h]
0x18000b179  mov     rcx, rax
0x18000b17c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b183  test    rax, rax
0x18000b186  jz      short loc_18000B1A6
0x18000b188  mov     rax, [rax]
0x18000b18b  mov     edx, 7F0h
0x18000b190  mov     rax, [rax+8]
0x18000b194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b199  test    eax, eax
0x18000b19b  jz      short loc_18000B1A6
0x18000b19d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1a4  jmp     short loc_18000B1B4
0x18000b1a6  lea     rcx, qword_1800DBF70; this
0x18000b1ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1b4  cmp     [rcx+8], r12b
0x18000b1b8  jz      loc_18000B7CE
0x18000b1be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b1c3  cmp     [rax+7CCh], edi
0x18000b1c9  jz      loc_18000B7CE
0x18000b1cf  mov     r9d, edi
0x18000b1d2  mov     r8d, 24h ; '$'
0x18000b1d8  jmp     loc_18000B7BE
0x18000b1dd  test    bl, 1
0x18000b1e0  jnz     loc_18000B269
0x18000b1e6  mov     edi, 80070057h
0x18000b1eb  mov     ebx, edi
0x18000b1ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1f4  test    rcx, rcx
0x18000b1f7  jnz     short loc_18000B240
0x18000b1f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b200  nop     dword ptr [rax+rax+00h]
0x18000b205  mov     rcx, rax
0x18000b208  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b20f  test    rax, rax
0x18000b212  jz      short loc_18000B232
0x18000b214  mov     rax, [rax]
0x18000b217  mov     edx, 7F0h
0x18000b21c  mov     rax, [rax+8]
0x18000b220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b225  test    eax, eax
0x18000b227  jz      short loc_18000B232
0x18000b229  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b230  jmp     short loc_18000B240
0x18000b232  lea     rcx, qword_1800DBF70; this
0x18000b239  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b240  cmp     [rcx+8], r12b
0x18000b244  jz      loc_18000B7CE
0x18000b24a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b24f  cmp     [rax+7CCh], edi
0x18000b255  jz      loc_18000B7CE
0x18000b25b  mov     r9d, edi
0x18000b25e  mov     r8d, 29h ; ')'
0x18000b264  jmp     loc_18000B7BE
0x18000b269  mov     [rbp+arg_0], r12d
0x18000b26d  mov     rax, [rdi]
0x18000b270  lea     rdx, [rbp+arg_0]
0x18000b274  mov     rcx, rdi
0x18000b277  mov     rax, [rax+18h]
0x18000b27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b280  mov     ebx, eax
0x18000b282  test    eax, eax
0x18000b284  jns     short loc_18000B2FF
0x18000b286  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b28d  test    rcx, rcx
0x18000b290  jnz     short loc_18000B2D9
0x18000b292  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b299  nop     dword ptr [rax+rax+00h]
0x18000b29e  mov     rcx, rax
0x18000b2a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b2a8  test    rax, rax
0x18000b2ab  jz      short loc_18000B2CB
0x18000b2ad  mov     rax, [rax]
0x18000b2b0  mov     edx, 7F0h
0x18000b2b5  mov     rax, [rax+8]
0x18000b2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2be  test    eax, eax
0x18000b2c0  jz      short loc_18000B2CB
0x18000b2c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b2c9  jmp     short loc_18000B2D9
0x18000b2cb  lea     rcx, qword_1800DBF70; this
0x18000b2d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b2d9  cmp     [rcx+8], r12b
0x18000b2dd  jz      loc_18000B7CE
0x18000b2e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b2e8  cmp     [rax+7CCh], ebx
0x18000b2ee  jz      loc_18000B7CE
0x18000b2f4  mov     r8d, 2Eh ; '.'
0x18000b2fa  jmp     loc_18000B7BB
0x18000b2ff  test    byte ptr [rbp+arg_0], 1
0x18000b303  jnz     loc_18000B38C
0x18000b309  mov     edi, 80070057h
0x18000b30e  mov     ebx, edi
0x18000b310  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b317  test    rcx, rcx
0x18000b31a  jnz     short loc_18000B363
0x18000b31c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b323  nop     dword ptr [rax+rax+00h]
0x18000b328  mov     rcx, rax
0x18000b32b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b332  test    rax, rax
0x18000b335  jz      short loc_18000B355
0x18000b337  mov     rax, [rax]
0x18000b33a  mov     edx, 7F0h
0x18000b33f  mov     rax, [rax+8]
0x18000b343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b348  test    eax, eax
0x18000b34a  jz      short loc_18000B355
0x18000b34c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b353  jmp     short loc_18000B363
0x18000b355  lea     rcx, qword_1800DBF70; this
0x18000b35c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b363  cmp     [rcx+8], r12b
0x18000b367  jz      loc_18000B7CE
0x18000b36d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b372  cmp     [rax+7CCh], edi
0x18000b378  jz      loc_18000B7CE
0x18000b37e  mov     r9d, edi
0x18000b381  mov     r8d, 32h ; '2'
0x18000b387  jmp     loc_18000B7BE
0x18000b38c  mov     [rbp+var_10], r12
0x18000b390  mov     rax, [rdi]
0x18000b393  lea     rdx, [rbp+var_10]
0x18000b397  mov     rcx, rdi
0x18000b39a  mov     rax, [rax+20h]
0x18000b39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a3  mov     ebx, eax
0x18000b3a5  test    eax, eax
0x18000b3a7  js      loc_18000B435
0x18000b3ad  cmp     [rbp+var_10], r12
0x18000b3b1  jnz     loc_18000B4B6
0x18000b3b7  mov     ebx, 0C00D36BEh
0x18000b3bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b3c3  test    rcx, rcx
0x18000b3c6  jnz     short loc_18000B40F
0x18000b3c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b3cf  nop     dword ptr [rax+rax+00h]
0x18000b3d4  mov     rcx, rax
0x18000b3d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b3de  test    rax, rax
0x18000b3e1  jz      short loc_18000B401
0x18000b3e3  mov     rax, [rax]
0x18000b3e6  mov     edx, 7F0h
0x18000b3eb  mov     rax, [rax+8]
0x18000b3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f4  test    eax, eax
0x18000b3f6  jz      short loc_18000B401
0x18000b3f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b3ff  jmp     short loc_18000B40F
0x18000b401  lea     rcx, qword_1800DBF70; this
0x18000b408  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b40f  cmp     [rcx+8], r12b
0x18000b413  jz      loc_18000B7CE
0x18000b419  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b41e  cmp     [rax+7CCh], ebx
0x18000b424  jz      loc_18000B7CE
0x18000b42a  mov     r8d, 3Dh ; '='
0x18000b430  jmp     loc_18000B7BB
0x18000b435  cmp     ebx, 0C00D36FBh
0x18000b43b  jz      short loc_18000B4B6
0x18000b43d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b444  test    rcx, rcx
0x18000b447  jnz     short loc_18000B490
0x18000b449  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b450  nop     dword ptr [rax+rax+00h]
0x18000b455  mov     rcx, rax
0x18000b458  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b45f  test    rax, rax
0x18000b462  jz      short loc_18000B482
0x18000b464  mov     rax, [rax]
0x18000b467  mov     edx, 7F0h
0x18000b46c  mov     rax, [rax+8]
0x18000b470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b475  test    eax, eax
0x18000b477  jz      short loc_18000B482
0x18000b479  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b480  jmp     short loc_18000B490
0x18000b482  lea     rcx, qword_1800DBF70; this
0x18000b489  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b490  cmp     [rcx+8], r12b
0x18000b494  jz      loc_18000B7CE
0x18000b49a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b49f  cmp     [rax+7CCh], ebx
0x18000b4a5  jz      loc_18000B7CE
0x18000b4ab  mov     r8d, 42h ; 'B'
0x18000b4b1  jmp     loc_18000B7BB
0x18000b4b6  lea     rcx, [rbp+arg_8]
0x18000b4ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b4bf  lea     r8, [rbp+arg_8]; struct MkvMfSourceLib::MkvMfSource **
0x18000b4c3  mov     rdx, [r14+60h]; struct IMFTelemetrySession *
0x18000b4c7  mov     rcx, rdi; struct IMFByteStream *
0x18000b4ca  call    ?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z; MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)
0x18000b4cf  mov     ebx, eax
0x18000b4d1  test    eax, eax
0x18000b4d3  jns     short loc_18000B54E
0x18000b4d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b4dc  test    rcx, rcx
0x18000b4df  jnz     short loc_18000B528
0x18000b4e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b4e8  nop     dword ptr [rax+rax+00h]
0x18000b4ed  mov     rcx, rax
0x18000b4f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b4f7  test    rax, rax
0x18000b4fa  jz      short loc_18000B51A
0x18000b4fc  mov     rax, [rax]
0x18000b4ff  mov     edx, 7F0h
0x18000b504  mov     rax, [rax+8]
0x18000b508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50d  test    eax, eax
0x18000b50f  jz      short loc_18000B51A
0x18000b511  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b518  jmp     short loc_18000B528
0x18000b51a  lea     rcx, qword_1800DBF70; this
0x18000b521  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b528  cmp     [rcx+8], r12b
0x18000b52c  jz      loc_18000B7CE
0x18000b532  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b537  cmp     [rax+7CCh], ebx
0x18000b53d  jz      loc_18000B7CE
0x18000b543  mov     r8d, 46h ; 'F'
0x18000b549  jmp     loc_18000B7BB
0x18000b54e  mov     rbx, [rbp+arg_8]
0x18000b552  mov     rax, [rbx]
0x18000b555  mov     rdi, [rax]
0x18000b558  lea     rcx, [rbp+punkObject]
0x18000b55c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b561  lea     r8, [rbp+punkObject]
0x18000b565  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x18000b56c  mov     rcx, rbx
0x18000b56f  mov     rax, rdi
0x18000b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b577  mov     ebx, eax
0x18000b579  test    eax, eax
0x18000b57b  jns     short loc_18000B5F6
0x18000b57d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b584  test    rcx, rcx
0x18000b587  jnz     short loc_18000B5D0
0x18000b589  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000b590  nop     dword ptr [rax+rax+00h]
0x18000b595  mov     rcx, rax
  ... truncated ...
```
