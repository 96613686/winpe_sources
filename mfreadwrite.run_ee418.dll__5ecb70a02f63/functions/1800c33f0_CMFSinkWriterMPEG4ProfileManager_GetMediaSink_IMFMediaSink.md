# CMFSinkWriterMPEG4ProfileManager::GetMediaSink(IMFMediaSink * *)

- ea: `0x1800c33f0`
- end: `0x1800c3897`
- name: `?GetMediaSink@CMFSinkWriterMPEG4ProfileManager@@UEAAJPEAPEAUIMFMediaSink@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(CMFSinkWriterMPEG4ProfileManager *__hidden this, struct IMFMediaSink **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000517c`
- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x1800252a0`
- `0x1800acd2c`
- `0x1800c33f0`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c36af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c36af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c379a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c37b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c379a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c37b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c34d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c3633`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c37a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c34d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c3633`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c37a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c347b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c34ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c35d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3659`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c37cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c347b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c34ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c35d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3659`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c37cc`
- `MFCORE!CopyPropertyStore` at `0x1800c372c`
- `MFCORE!CopyPropertyStore` at `0x1800c372c`
- `MFCORE!MFGetService` at `0x1800c370e`
- `MFCORE!MFGetService` at `0x1800c370e`

## string_xrefs

- `0x1800c3408`: `CMFSinkWriterMPEG4ProfileManager::GetMediaSink`
- `0x1800c3566`: `CMFSinkWriterMPEG4ProfileManager::GetMediaSink`
- `0x1800c36c0`: `CMFSinkWriterMPEG4ProfileManager::GetMediaSink`
- `0x1800c3833`: `CMFSinkWriterMPEG4ProfileManager::GetMediaSink`

## pseudocode

```c
__int64 __fastcall CMFSinkWriterMPEG4ProfileManager::GetMediaSink(
        CMFSinkWriterMPEG4ProfileManager *this,
        struct IMFMediaSink **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rax
  CallStackTracing *v7; // rdi
  int v8; // ebx
  CallStackTracing *v9; // rax
  CallStackContext *v10; // rbp
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  CallStackTracing *v20; // rdi
  CallStackTracing *v21; // rax
  CallStackContext *v22; // rbp
  DWORD v23; // r15d
  CallStackContext *v24; // rax
  __int64 v25; // rdx
  CallStackTracing *v26; // rcx
  CallStackTracing *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  CallStackTracing *v31; // rdi
  CallStackTracing *v32; // rax
  CallStackContext *v33; // rbp
  DWORD v34; // r15d
  CallStackContext *v35; // rax
  __int64 v36; // rdx
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  __int64 v39; // rax
  struct IMFMediaSink *v40; // rcx
  char v42; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppvObject; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v42,
    "CMFSinkWriterMPEG4ProfileManager::GetMediaSink",
    969);
  v6 = *((_QWORD *)this + 5);
  ppvObject = 0;
  if ( *(_OWORD *)(v6 + 8) == 0 )
  {
    if ( byte_18010CAF1 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, &WPP_cb88a1e5dded39afaa094c6f3342a822_Traceguids, this);
    v7 = CallStackTracing::s_wpInstance;
    v8 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = (CallStackTracing *)((char *)v7 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v7 + 3));
      if ( Value )
      {
        v10 = Value;
      }
      else if ( !GetLastError() )
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v16 = (**(__int64 (__fastcall ***)(CallStackTracing *))v14)(v14);
        if ( v16 )
          v10 = (CallStackContext *)v16;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v10 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v10, "CMFSinkWriterMPEG4ProfileManager::GetMediaSink", 979, -1072875854);
    }
    if ( g_wppLevels )
    {
      v17 = 94;
LABEL_24:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_cb88a1e5dded39afaa094c6f3342a822_Traceguids, this, v8);
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(CMFSinkWriterMPEG4ProfileManager *))(*(_QWORD *)this + 72LL))(this);
    if ( v8 >= 0 )
    {
      if ( !*((_QWORD *)this + 7)
        || MFGetService(
             *((IUnknown **)this + 2),
             &MF_PROPERTY_HANDLER_SERVICE,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &ppvObject) < 0
        || (v8 = CopyPropertyStore(&GUID_00000000_0000_0000_0000_000000000000, ppvObject, *((_QWORD *)this + 7)), v8 >= 0) )
      {
        v40 = (struct IMFMediaSink *)*((_QWORD *)this + 2);
        *a2 = v40;
        ((void (__fastcall *)(struct IMFMediaSink *))v40->lpVtbl->AddRef)(v40);
        goto LABEL_70;
      }
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v30, v29);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = (CallStackTracing *)((char *)v31 + 208);
        v34 = GetLastError();
        v35 = (CallStackContext *)TlsGetValue(*((_DWORD *)v31 + 3));
        if ( v35 )
        {
          v33 = v35;
        }
        else if ( !GetLastError() )
        {
          v37 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
            CallStackTracing::s_wpInstance = v38;
            if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
            {
              v37 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v37 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v37)(v37);
          if ( v39 )
            v33 = (CallStackContext *)v39;
        }
        SetLastError(v34);
        if ( *((_DWORD *)v33 + 499) != v8 )
          CallStackContext::TraceFailure(v33, "CMFSinkWriterMPEG4ProfileManager::GetMediaSink", 993, v8);
      }
      if ( g_wppLevels )
      {
        v17 = 96;
        goto LABEL_24;
      }
    }
    else
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = (CallStackTracing *)((char *)v20 + 208);
        v23 = GetLastError();
        v24 = (CallStackContext *)TlsGetValue(*((_DWORD *)v20 + 3));
        if ( v24 )
        {
          v22 = v24;
        }
        else if ( !GetLastError() )
        {
          v26 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v28 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
          if ( v28 )
            v22 = (CallStackContext *)v28;
        }
        SetLastError(v23);
        if ( *((_DWORD *)v22 + 499) != v8 )
          CallStackContext::TraceFailure(v22, "CMFSinkWriterMPEG4ProfileManager::GetMediaSink", 985, v8);
      }
      if ( g_wppLevels )
      {
        v17 = 95;
        goto LABEL_24;
      }
    }
  }
LABEL_70:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppvObject);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c33f0  mov     [rsp+arg_8], rbx
0x1800c33f5  mov     [rsp+arg_18], rbp
0x1800c33fa  push    rsi
0x1800c33fb  push    rdi
0x1800c33fc  push    r15
0x1800c33fe  sub     rsp, 30h
0x1800c3402  mov     rdi, rdx
0x1800c3405  mov     rsi, rcx
0x1800c3408  lea     rdx, aCmfsinkwriterm_3; "CMFSinkWriterMPEG4ProfileManager::GetMe"...
0x1800c340f  mov     r8d, 3C9h; int
0x1800c3415  lea     rcx, [rsp+48h+arg_0]; this
0x1800c341a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c341f  mov     rax, [rsi+28h]
0x1800c3423  mov     [rsp+48h+ppvObject], 0
0x1800c342c  cmp     qword ptr [rax+10h], 0
0x1800c3431  jnz     loc_1800C35B0
0x1800c3437  cmp     qword ptr [rax+8], 0
0x1800c343c  jnz     loc_1800C35B0
0x1800c3442  cmp     cs:byte_18010CAF1, 1
0x1800c3449  jb      short loc_1800C346A
0x1800c344b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3452  lea     r8, WPP_cb88a1e5dded39afaa094c6f3342a822_Traceguids
0x1800c3459  mov     edx, 5Dh ; ']'
0x1800c345e  mov     r9, rsi
0x1800c3461  mov     rcx, [rcx+38h]
0x1800c3465  call    WPP_SF_q
0x1800c346a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3471  mov     ebx, 0C00D36B2h
0x1800c3476  test    rdi, rdi
0x1800c3479  jnz     short loc_1800C34BC
0x1800c347b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3481  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3488  mov     rcx, rax
0x1800c348b  test    rax, rax
0x1800c348e  jz      short loc_1800C34AE
0x1800c3490  mov     rax, [rax]
0x1800c3493  mov     edx, 7F0h
0x1800c3498  mov     rax, [rax+8]
0x1800c349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c34a1  test    eax, eax
0x1800c34a3  jz      short loc_1800C34AE
0x1800c34a5  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c34ac  jmp     short loc_1800C34BC
0x1800c34ae  lea     rdi, qword_18010C230
0x1800c34b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c34bc  cmp     byte ptr [rdi+8], 0
0x1800c34c0  jz      loc_1800C357B
0x1800c34c6  lea     rbp, [rdi+0D0h]
0x1800c34cd  call    cs:__imp_GetLastError
0x1800c34d3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800c34d6  mov     r15d, eax
0x1800c34d9  call    cs:__imp_TlsGetValue
0x1800c34df  test    rax, rax
0x1800c34e2  jz      short loc_1800C34E9
0x1800c34e4  mov     rbp, rax
0x1800c34e7  jmp     short loc_1800C3552
0x1800c34e9  call    cs:__imp_GetLastError
0x1800c34ef  test    eax, eax
0x1800c34f1  jnz     short loc_1800C3552
0x1800c34f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c34fa  test    rcx, rcx
0x1800c34fd  jnz     short loc_1800C3540
0x1800c34ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3505  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c350c  mov     rcx, rax
0x1800c350f  test    rax, rax
0x1800c3512  jz      short loc_1800C3532
0x1800c3514  mov     rax, [rax]
0x1800c3517  mov     edx, 7F0h
0x1800c351c  mov     rax, [rax+8]
0x1800c3520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3525  test    eax, eax
0x1800c3527  jz      short loc_1800C3532
0x1800c3529  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3530  jmp     short loc_1800C3540
0x1800c3532  lea     rcx, qword_18010C230
0x1800c3539  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3540  mov     rax, [rcx]
0x1800c3543  mov     rax, [rax]
0x1800c3546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c354b  test    rax, rax
0x1800c354e  cmovnz  rbp, rax
0x1800c3552  mov     ecx, r15d; dwErrCode
0x1800c3555  call    cs:__imp_SetLastError
0x1800c355b  cmp     [rbp+7CCh], ebx
0x1800c3561  jz      short loc_1800C357B
0x1800c3563  mov     r9d, ebx; int
0x1800c3566  lea     rdx, aCmfsinkwriterm_3; "CMFSinkWriterMPEG4ProfileManager::GetMe"...
0x1800c356d  mov     r8d, 3D3h; int
0x1800c3573  mov     rcx, rbp; this
0x1800c3576  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c357b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c3582  jb      loc_1800C386E
0x1800c3588  mov     edx, 5Eh ; '^'
0x1800c358d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3594  lea     r8, WPP_cb88a1e5dded39afaa094c6f3342a822_Traceguids
0x1800c359b  mov     r9, rsi
0x1800c359e  mov     [rsp+48h+var_28], ebx
0x1800c35a2  mov     rcx, [rcx+10h]
0x1800c35a6  call    WPP_SF_qD
0x1800c35ab  jmp     loc_1800C386E
0x1800c35b0  mov     rax, [rsi]
0x1800c35b3  mov     rcx, rsi
0x1800c35b6  mov     rax, [rax+48h]
0x1800c35ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c35bf  mov     ebx, eax
0x1800c35c1  test    eax, eax
0x1800c35c3  jns     loc_1800C36EC
0x1800c35c9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c35d0  test    rdi, rdi
0x1800c35d3  jnz     short loc_1800C3616
0x1800c35d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c35db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c35e2  mov     rcx, rax
0x1800c35e5  test    rax, rax
0x1800c35e8  jz      short loc_1800C3608
0x1800c35ea  mov     rax, [rax]
0x1800c35ed  mov     edx, 7F0h
0x1800c35f2  mov     rax, [rax+8]
0x1800c35f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c35fb  test    eax, eax
0x1800c35fd  jz      short loc_1800C3608
0x1800c35ff  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3606  jmp     short loc_1800C3616
0x1800c3608  lea     rdi, qword_18010C230
0x1800c360f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3616  cmp     byte ptr [rdi+8], 0
0x1800c361a  jz      loc_1800C36D5
0x1800c3620  lea     rbp, [rdi+0D0h]
0x1800c3627  call    cs:__imp_GetLastError
0x1800c362d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800c3630  mov     r15d, eax
0x1800c3633  call    cs:__imp_TlsGetValue
0x1800c3639  test    rax, rax
0x1800c363c  jz      short loc_1800C3643
0x1800c363e  mov     rbp, rax
0x1800c3641  jmp     short loc_1800C36AC
0x1800c3643  call    cs:__imp_GetLastError
0x1800c3649  test    eax, eax
0x1800c364b  jnz     short loc_1800C36AC
0x1800c364d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3654  test    rcx, rcx
0x1800c3657  jnz     short loc_1800C369A
0x1800c3659  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c365f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3666  mov     rcx, rax
0x1800c3669  test    rax, rax
0x1800c366c  jz      short loc_1800C368C
0x1800c366e  mov     rax, [rax]
0x1800c3671  mov     edx, 7F0h
0x1800c3676  mov     rax, [rax+8]
0x1800c367a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c367f  test    eax, eax
0x1800c3681  jz      short loc_1800C368C
0x1800c3683  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c368a  jmp     short loc_1800C369A
0x1800c368c  lea     rcx, qword_18010C230
0x1800c3693  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c369a  mov     rax, [rcx]
0x1800c369d  mov     rax, [rax]
0x1800c36a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c36a5  test    rax, rax
0x1800c36a8  cmovnz  rbp, rax
0x1800c36ac  mov     ecx, r15d; dwErrCode
0x1800c36af  call    cs:__imp_SetLastError
0x1800c36b5  cmp     [rbp+7CCh], ebx
0x1800c36bb  jz      short loc_1800C36D5
0x1800c36bd  mov     r9d, ebx; int
0x1800c36c0  lea     rdx, aCmfsinkwriterm_3; "CMFSinkWriterMPEG4ProfileManager::GetMe"...
0x1800c36c7  mov     r8d, 3D9h; int
0x1800c36cd  mov     rcx, rbp; this
0x1800c36d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c36d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c36dc  jb      loc_1800C386E
0x1800c36e2  mov     edx, 5Fh ; '_'
0x1800c36e7  jmp     loc_1800C358D
0x1800c36ec  cmp     qword ptr [rsi+38h], 0
0x1800c36f1  jz      loc_1800C385B
0x1800c36f7  mov     rcx, [rsi+10h]; punkObject
0x1800c36fb  lea     r9, [rsp+48h+ppvObject]; ppvObject
0x1800c3700  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800c3707  lea     rdx, MF_PROPERTY_HANDLER_SERVICE; guidService
0x1800c370e  call    cs:__imp_MFGetService
0x1800c3714  test    eax, eax
0x1800c3716  js      loc_1800C385B
0x1800c371c  mov     r8, [rsi+38h]
0x1800c3720  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x1800c3727  mov     rdx, [rsp+48h+ppvObject]
0x1800c372c  call    cs:__imp_CopyPropertyStore
0x1800c3732  mov     ebx, eax
0x1800c3734  test    eax, eax
0x1800c3736  jns     loc_1800C385B
0x1800c373c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3743  test    rdi, rdi
0x1800c3746  jnz     short loc_1800C3789
0x1800c3748  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c374e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3755  mov     rcx, rax
0x1800c3758  test    rax, rax
0x1800c375b  jz      short loc_1800C377B
0x1800c375d  mov     rax, [rax]
0x1800c3760  mov     edx, 7F0h
0x1800c3765  mov     rax, [rax+8]
0x1800c3769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c376e  test    eax, eax
0x1800c3770  jz      short loc_1800C377B
0x1800c3772  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3779  jmp     short loc_1800C3789
0x1800c377b  lea     rdi, qword_18010C230
0x1800c3782  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3789  cmp     byte ptr [rdi+8], 0
0x1800c378d  jz      loc_1800C3848
0x1800c3793  lea     rbp, [rdi+0D0h]
0x1800c379a  call    cs:__imp_GetLastError
0x1800c37a0  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800c37a3  mov     r15d, eax
0x1800c37a6  call    cs:__imp_TlsGetValue
0x1800c37ac  test    rax, rax
0x1800c37af  jz      short loc_1800C37B6
0x1800c37b1  mov     rbp, rax
0x1800c37b4  jmp     short loc_1800C381F
0x1800c37b6  call    cs:__imp_GetLastError
0x1800c37bc  test    eax, eax
0x1800c37be  jnz     short loc_1800C381F
0x1800c37c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c37c7  test    rcx, rcx
0x1800c37ca  jnz     short loc_1800C380D
0x1800c37cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c37d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c37d9  mov     rcx, rax
0x1800c37dc  test    rax, rax
0x1800c37df  jz      short loc_1800C37FF
0x1800c37e1  mov     rax, [rax]
0x1800c37e4  mov     edx, 7F0h
0x1800c37e9  mov     rax, [rax+8]
0x1800c37ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c37f2  test    eax, eax
0x1800c37f4  jz      short loc_1800C37FF
0x1800c37f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c37fd  jmp     short loc_1800C380D
0x1800c37ff  lea     rcx, qword_18010C230
0x1800c3806  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c380d  mov     rax, [rcx]
0x1800c3810  mov     rax, [rax]
0x1800c3813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3818  test    rax, rax
0x1800c381b  cmovnz  rbp, rax
0x1800c381f  mov     ecx, r15d; dwErrCode
0x1800c3822  call    cs:__imp_SetLastError
0x1800c3828  cmp     [rbp+7CCh], ebx
0x1800c382e  jz      short loc_1800C3848
0x1800c3830  mov     r9d, ebx; int
0x1800c3833  lea     rdx, aCmfsinkwriterm_3; "CMFSinkWriterMPEG4ProfileManager::GetMe"...
0x1800c383a  mov     r8d, 3E1h; int
0x1800c3840  mov     rcx, rbp; this
0x1800c3843  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c3848  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c384f  jb      short loc_1800C386E
0x1800c3851  mov     edx, 60h ; '`'
0x1800c3856  jmp     loc_1800C358D
0x1800c385b  mov     rcx, [rsi+10h]
0x1800c385f  mov     [rdi], rcx
0x1800c3862  mov     rdx, [rcx]
0x1800c3865  mov     rax, [rdx+8]
0x1800c3869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c386e  lea     rcx, [rsp+48h+ppvObject]
0x1800c3873  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800c3878  lea     rcx, [rsp+48h+arg_0]; this
0x1800c387d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800c3882  mov     rbp, [rsp+48h+arg_18]
0x1800c3887  mov     eax, ebx
0x1800c3889  mov     rbx, [rsp+48h+arg_8]
0x1800c388e  add     rsp, 30h
0x1800c3892  pop     r15
0x1800c3894  pop     rdi
0x1800c3895  pop     rsi
0x1800c3896  retn
```
