# CMFReadWriteTransform::ProcessInput(IMFSample *)

- ea: `0x18003d7d0`
- end: `0x18003dd29`
- name: `?ProcessInput@CMFReadWriteTransform@@UEAAJPEAUIMFSample@@@Z`
- size: `1369`
- prototype: `__int64 __fastcall(CMFReadWriteTransform *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006bd4`
- `0x180012640`
- `0x180014a14`
- `0x18003d7d0`
- `0x18003dd30`
- `0x18003e0a4`
- `0x1800f1070`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d92b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d92b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d866`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d816`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d950`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dacf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dc23`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d816`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d950`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dacf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dc23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003daf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003db89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dc44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003daf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003db89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dc44`

## string_xrefs

- `0x18003d7fa`: `CMFReadWriteTransform::ProcessInput`
- `0x18003dc83`: `CMFReadWriteTransform::ProcessInput`

## pseudocode

```c
__int64 __fastcall CMFReadWriteTransform::ProcessInput(CMFReadWriteTransform *this, struct IMFSample *a2)
{
  CallStackTracing *v2; // rdi
  char *v5; // rbp
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // edi
  CallStackTracing *v15; // rbx
  GUID *v16; // rsi
  DWORD v17; // ebp
  GUID *v18; // rax
  int v19; // eax
  int v20; // eax
  CallStackTracing *v22; // rbx
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  CallStackContext *v27; // r15
  DWORD v28; // r12d
  CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  CallStackTracing *v32; // r14
  CallStackTracing *v33; // rax
  __int64 v34; // rax
  CallStackTracing *v35; // r15
  CallStackTracing *v36; // rax
  CallStackContext *v37; // r12
  DWORD v38; // r13d
  CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 v43; // rax
  struct IMFSample *v44; // [rsp+70h] [rbp+8h] BYREF
  __int64 v45; // [rsp+78h] [rbp+10h] BYREF

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = (char *)v2 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
      if ( v24 )
        v5 = (char *)v24;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMFReadWriteTransform::ProcessInput";
      *(_DWORD *)&v5[8 * v9 + 8] = 912;
    }
    ++*((_DWORD *)v5 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  lpVtbl = a2->lpVtbl;
  v44 = 0;
  v45 = 0;
  ((void (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->GetSampleDuration)(a2, &v45);
  v11 = *((_DWORD *)this + 28);
  *((_QWORD *)this + 27) = v45;
  CMFReadWriteTransform::TraceSample(this, "MFT->ProcessInput", v11, a2, 1, 0);
  if ( !*((_BYTE *)this + 176) )
  {
    ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
    goto LABEL_11;
  }
  v14 = CMFReadWriteTransform::EnsureD3DSample(this, a2, &v44);
  if ( v14 >= 0 )
  {
    a2 = v44;
LABEL_11:
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFSample *, _QWORD))(**((_QWORD **)this + 9) + 192LL))(
            *((_QWORD *)this + 9),
            *((unsigned int *)this + 53),
            a2,
            0);
    if ( v14 < 0 )
    {
      if ( (Microsoft_Windows_MediaFoundation_MFReadWriteEnableBits & 0x10) != 0 )
        McTemplateU0pqpq_EventWriteTransfer(
          v13,
          (unsigned int)MFReadWrite_Transform_ProcessInputError,
          (_DWORD)this,
          *((_DWORD *)this + 28),
          *((_QWORD *)this + 9),
          v14);
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = (CallStackTracing *)((char *)v35 + 208);
        v38 = GetLastError();
        v39 = (CallStackContext *)TlsGetValue(*((_DWORD *)v35 + 3));
        if ( v39 )
        {
          v37 = v39;
        }
        else if ( !GetLastError() )
        {
          v41 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
            {
              v41 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v41 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
          if ( v43 )
            v37 = (CallStackContext *)v43;
        }
        SetLastError(v38);
        if ( *((_DWORD *)v37 + 499) != v14 )
          CallStackContext::TraceFailure(v37, "CMFReadWriteTransform::ProcessInput", 948, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_528c6086732434342200d826d3525973_Traceguids, this, v14);
    }
    goto LABEL_12;
  }
  v22 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v22 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v27 = (CallStackTracing *)((char *)v22 + 208);
    v28 = GetLastError();
    v29 = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v29 )
    {
      v27 = v29;
    }
    else if ( !GetLastError() )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v30);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
      if ( v34 )
        v27 = (CallStackContext *)v34;
    }
    SetLastError(v28);
    if ( *((_DWORD *)v27 + 499) != v14 )
      CallStackContext::TraceFailure(v27, "CMFReadWriteTransform::ProcessInput", 935, v14);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_528c6086732434342200d826d3525973_Traceguids, this, v14);
  a2 = v44;
LABEL_12:
  if ( a2 )
    ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->Release)(a2);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v15 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v16 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v17 = GetLastError();
    v18 = (GUID *)TlsGetValue(*((_DWORD *)v15 + 3));
    if ( v18 )
    {
      v16 = v18;
    }
    else if ( !GetLastError() )
    {
      v25 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v25 = CallStackTracing::s_wpInstance;
      }
      v26 = (**(__int64 (__fastcall ***)(CallStackTracing *))v25)(v25);
      if ( v26 )
        v16 = (GUID *)v26;
    }
    SetLastError(v17);
    v19 = *(_DWORD *)&v16[124].Data2;
    if ( v19 )
    {
      v20 = v19 - 1;
      *(_DWORD *)&v16[124].Data2 = v20;
      if ( !v20 )
      {
        *(_DWORD *)&v16[124].Data2 = 0;
        *(_QWORD *)&v16[126].Data1 = 0;
        *(_DWORD *)&v16[124].Data4[4] = 0;
        v16[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v16[126].Data4 = 0;
        v16[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003d7d0  push    rbx
0x18003d7d2  push    rbp
0x18003d7d3  push    rsi
0x18003d7d4  push    rdi
0x18003d7d5  push    r14
0x18003d7d7  sub     rsp, 40h
0x18003d7db  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d7e2  mov     rbx, rdx
0x18003d7e5  mov     [rsp+68h+var_30], r13
0x18003d7ea  mov     rsi, rcx
0x18003d7ed  test    rdi, rdi
0x18003d7f0  jz      loc_18003DA1C
0x18003d7f6  cmp     byte ptr [rdi+8], 0
0x18003d7fa  lea     r13, aCmfreadwritetr_114; "CMFReadWriteTransform::ProcessInput"
0x18003d801  jz      short loc_18003D855
0x18003d803  lea     rbp, [rdi+0D0h]
0x18003d80a  call    cs:__imp_GetLastError
0x18003d810  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18003d813  mov     r14d, eax
0x18003d816  call    cs:__imp_TlsGetValue
0x18003d81c  test    rax, rax
0x18003d81f  jz      loc_18003DA2D
0x18003d825  mov     rbp, rax
0x18003d828  mov     ecx, r14d; dwErrCode
0x18003d82b  call    cs:__imp_SetLastError
0x18003d831  mov     eax, [rbp+7C4h]
0x18003d837  cmp     eax, [rbp+7C8h]
0x18003d83d  jnb     short loc_18003D84F
0x18003d83f  add     rax, rax
0x18003d842  mov     [rbp+rax*8+0], r13
0x18003d847  mov     dword ptr [rbp+rax*8+8], 390h
0x18003d84f  inc     dword ptr [rbp+7C4h]
0x18003d855  mov     [rsp+68h+arg_10], r12
0x18003d85d  lea     rcx, [rsi+18h]; lpCriticalSection
0x18003d861  mov     [rsp+68h+var_38], r15
0x18003d866  call    cs:__imp_EnterCriticalSection
0x18003d86c  mov     rax, [rbx]
0x18003d86f  lea     rdx, [rsp+68h+arg_8]
0x18003d874  xor     r14d, r14d
0x18003d877  mov     rcx, rbx
0x18003d87a  mov     [rsp+68h+arg_0], r14
0x18003d87f  mov     [rsp+68h+arg_8], r14
0x18003d884  mov     rax, [rax+128h]
0x18003d88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d890  mov     rax, [rsp+68h+arg_8]
0x18003d895  lea     rdx, aMftProcessinpu; "MFT->ProcessInput"
0x18003d89c  mov     r8d, [rsi+70h]; unsigned int
0x18003d8a0  mov     r9, rbx; struct IMFSample *
0x18003d8a3  mov     [rsp+68h+var_40], r14d; unsigned int
0x18003d8a8  mov     rcx, rsi; this
0x18003d8ab  mov     [rsi+0D8h], rax
0x18003d8b2  mov     [rsp+68h+var_48], 1; bool
0x18003d8b7  call    ?TraceSample@CMFReadWriteTransform@@AEAAXPEBDKPEAUIMFSample@@_NK@Z; CMFReadWriteTransform::TraceSample(char const *,ulong,IMFSample *,bool,ulong)
0x18003d8bc  cmp     [rsi+0B0h], r14b
0x18003d8c3  jnz     loc_18003D98C
0x18003d8c9  mov     rax, [rbx]
0x18003d8cc  mov     rcx, rbx
0x18003d8cf  mov     rax, [rax+8]
0x18003d8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8d8  mov     rcx, [rsi+48h]
0x18003d8dc  xor     r9d, r9d
0x18003d8df  mov     edx, [rsi+0D4h]
0x18003d8e5  mov     r8, rbx
0x18003d8e8  mov     rax, [rcx]
0x18003d8eb  mov     rax, [rax+0C0h]
0x18003d8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8f7  mov     edi, eax
0x18003d8f9  test    eax, eax
0x18003d8fb  js      loc_18003DCF7
0x18003d901  mov     r15, [rsp+68h+var_38]
0x18003d906  mov     r13, [rsp+68h+var_30]
0x18003d90b  mov     r12, [rsp+68h+arg_10]
0x18003d913  test    rbx, rbx
0x18003d916  jz      short loc_18003D927
0x18003d918  mov     rax, [rbx]
0x18003d91b  mov     rcx, rbx
0x18003d91e  mov     rax, [rax+10h]
0x18003d922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d927  lea     rcx, [rsi+18h]; lpCriticalSection
0x18003d92b  call    cs:__imp_LeaveCriticalSection
0x18003d931  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d938  cmp     byte ptr [rbx+8], 0
0x18003d93c  jz      short loc_18003D97F
0x18003d93e  lea     rsi, [rbx+0D0h]
0x18003d945  call    cs:__imp_GetLastError
0x18003d94b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003d94e  mov     ebp, eax
0x18003d950  call    cs:__imp_TlsGetValue
0x18003d956  test    rax, rax
0x18003d959  jz      loc_18003DA5E
0x18003d95f  mov     rsi, rax
0x18003d962  mov     ecx, ebp; dwErrCode
0x18003d964  call    cs:__imp_SetLastError
0x18003d96a  mov     eax, [rsi+7C4h]
0x18003d970  test    eax, eax
0x18003d972  jz      short loc_18003D97F
0x18003d974  sub     eax, 1
0x18003d977  mov     [rsi+7C4h], eax
0x18003d97d  jz      short loc_18003D9D3
0x18003d97f  mov     eax, edi
0x18003d981  add     rsp, 40h
0x18003d985  pop     r14
0x18003d987  pop     rdi
0x18003d988  pop     rsi
0x18003d989  pop     rbp
0x18003d98a  pop     rbx
0x18003d98b  retn
0x18003d98c  lea     r8, [rsp+68h+arg_0]; struct IMFSample **
0x18003d991  mov     rdx, rbx; struct IMFSample *
0x18003d994  mov     rcx, rsi; this
0x18003d997  call    ?EnsureD3DSample@CMFReadWriteTransform@@AEAAJPEAUIMFSample@@PEAPEAU2@@Z; CMFReadWriteTransform::EnsureD3DSample(IMFSample *,IMFSample * *)
0x18003d99c  mov     edi, eax
0x18003d99e  test    eax, eax
0x18003d9a0  jns     short loc_18003DA12
0x18003d9a2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9a9  test    rbx, rbx
0x18003d9ac  jz      loc_18003DA8F
0x18003d9b2  cmp     [rbx+8], r14b
0x18003d9b6  jnz     loc_18003DABC
0x18003d9bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d9c3  jnb     loc_18003DCCF
0x18003d9c9  mov     rbx, [rsp+68h+arg_0]
0x18003d9ce  jmp     loc_18003D901
0x18003d9d3  mov     [rsi+7C4h], r14d
0x18003d9da  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003d9e1  mov     qword ptr [rsi+7E0h], 0
0x18003d9ec  mov     [rsi+7CCh], r14d
0x18003d9f3  movups  xmmword ptr [rsi+7D0h], xmm0
0x18003d9fa  mov     [rsi+7E8h], r14d
0x18003da01  call    cs:__imp_GetCurrentThreadId
0x18003da07  mov     [rsi+7C0h], eax
0x18003da0d  jmp     loc_18003D97F
0x18003da12  mov     rbx, [rsp+68h+arg_0]
0x18003da17  jmp     loc_18003D8D8
0x18003da1c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003da21  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da28  jmp     loc_18003D7F6
0x18003da2d  call    cs:__imp_GetLastError
0x18003da33  test    eax, eax
0x18003da35  jnz     loc_18003D828
0x18003da3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da42  test    rcx, rcx
0x18003da45  jz      short loc_18003DAA0
0x18003da47  mov     rax, [rcx]
0x18003da4a  mov     rax, [rax]
0x18003da4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da52  test    rax, rax
0x18003da55  cmovnz  rbp, rax
0x18003da59  jmp     loc_18003D828
0x18003da5e  call    cs:__imp_GetLastError
0x18003da64  test    eax, eax
0x18003da66  jnz     loc_18003D962
0x18003da6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da73  test    rcx, rcx
0x18003da76  jz      short loc_18003DAAE
0x18003da78  mov     rax, [rcx]
0x18003da7b  mov     rax, [rax]
0x18003da7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da83  test    rax, rax
0x18003da86  cmovnz  rsi, rax
0x18003da8a  jmp     loc_18003D962
0x18003da8f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003da94  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da9b  jmp     loc_18003D9B2
0x18003daa0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003daa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003daac  jmp     short loc_18003DA47
0x18003daae  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003dab3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003daba  jmp     short loc_18003DA78
0x18003dabc  lea     r15, [rbx+0D0h]
0x18003dac3  call    cs:__imp_GetLastError
0x18003dac9  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003dacc  mov     r12d, eax
0x18003dacf  call    cs:__imp_TlsGetValue
0x18003dad5  test    rax, rax
0x18003dad8  jnz     short loc_18003DB2D
0x18003dada  call    cs:__imp_GetLastError
0x18003dae0  test    eax, eax
0x18003dae2  jnz     short loc_18003DB30
0x18003dae4  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003daeb  test    r14, r14
0x18003daee  jnz     short loc_18003DB13
0x18003daf0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003daf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dafd  mov     rcx, rax
0x18003db00  test    rax, rax
0x18003db03  jnz     short loc_18003DB5F
0x18003db05  lea     r14, qword_18010C230
0x18003db0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db13  mov     rax, [r14]
0x18003db16  mov     rcx, r14
0x18003db19  mov     rax, [rax]
0x18003db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db21  test    rax, rax
0x18003db24  cmovnz  r15, rax
0x18003db28  xor     r14d, r14d
0x18003db2b  jmp     short loc_18003DB30
0x18003db2d  mov     r15, rax
0x18003db30  mov     ecx, r12d; dwErrCode
0x18003db33  call    cs:__imp_SetLastError
0x18003db39  cmp     [r15+7CCh], edi
0x18003db40  jz      loc_18003D9BC
0x18003db46  mov     r9d, edi; int
0x18003db49  mov     r8d, 3A7h; int
0x18003db4f  mov     rdx, r13; char *
0x18003db52  mov     rcx, r15; this
0x18003db55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003db5a  jmp     loc_18003D9BC
0x18003db5f  mov     rax, [rax]
0x18003db62  mov     edx, 7F0h
0x18003db67  mov     rax, [rax+8]
0x18003db6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db70  test    eax, eax
0x18003db72  jz      short loc_18003DB05
0x18003db74  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db7b  jmp     short loc_18003DB13
0x18003db7d  mov     r15, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db84  test    r15, r15
0x18003db87  jnz     short loc_18003DBBA
0x18003db89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003db8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db96  mov     rcx, rax
0x18003db99  test    rax, rax
0x18003db9c  jz      short loc_18003DBFC
0x18003db9e  mov     rax, [rax]
0x18003dba1  mov     edx, 7F0h
0x18003dba6  mov     rax, [rax+8]
0x18003dbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbaf  test    eax, eax
0x18003dbb1  jz      short loc_18003DBFC
0x18003dbb3  mov     r15, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dbba  lea     r14, qword_18010C230
0x18003dbc1  cmp     byte ptr [r15+8], 0
0x18003dbc6  jnz     short loc_18003DC0F
0x18003dbc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dbcf  jb      short loc_18003DBF4
0x18003dbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dbd8  lea     r8, WPP_528c6086732434342200d826d3525973_Traceguids
0x18003dbdf  mov     edx, 5Fh ; '_'
0x18003dbe4  mov     dword ptr [rsp+68h+var_48], edi
0x18003dbe8  mov     r9, rsi
0x18003dbeb  mov     rcx, [rcx+10h]
0x18003dbef  call    WPP_SF_qD
0x18003dbf4  xor     r14d, r14d
0x18003dbf7  jmp     loc_18003D901
0x18003dbfc  lea     r14, qword_18010C230
0x18003dc03  mov     r15, r14
0x18003dc06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc0d  jmp     short loc_18003DBC1
0x18003dc0f  lea     r12, [r15+0D0h]
0x18003dc16  call    cs:__imp_GetLastError
0x18003dc1c  mov     ecx, [r15+0Ch]; dwTlsIndex
0x18003dc20  mov     r13d, eax
0x18003dc23  call    cs:__imp_TlsGetValue
0x18003dc29  test    rax, rax
0x18003dc2c  jnz     short loc_18003DC77
0x18003dc2e  call    cs:__imp_GetLastError
0x18003dc34  test    eax, eax
0x18003dc36  jnz     short loc_18003DC7A
0x18003dc38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc3f  test    rcx, rcx
0x18003dc42  jnz     short loc_18003DC63
0x18003dc44  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003dc4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc51  mov     rcx, rax
0x18003dc54  test    rax, rax
0x18003dc57  jnz     short loc_18003DCB1
0x18003dc59  mov     rcx, r14
0x18003dc5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dc63  mov     rax, [rcx]
0x18003dc66  mov     rax, [rax]
0x18003dc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc6e  test    rax, rax
0x18003dc71  cmovnz  r12, rax
0x18003dc75  jmp     short loc_18003DC7A
0x18003dc77  mov     r12, rax
0x18003dc7a  mov     ecx, r13d; dwErrCode
0x18003dc7d  call    cs:__imp_SetLastError
0x18003dc83  lea     r13, aCmfreadwritetr_114; "CMFReadWriteTransform::ProcessInput"
0x18003dc8a  cmp     [r12+7CCh], edi
0x18003dc92  jz      loc_18003DBC8
0x18003dc98  mov     r9d, edi; int
0x18003dc9b  mov     r8d, 3B4h; int
0x18003dca1  mov     rdx, r13; char *
0x18003dca4  mov     rcx, r12; this
0x18003dca7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dcac  jmp     loc_18003DBC8
0x18003dcb1  mov     rax, [rax]
0x18003dcb4  mov     edx, 7F0h
0x18003dcb9  mov     rax, [rax+8]
0x18003dcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcc2  test    eax, eax
0x18003dcc4  jz      short loc_18003DC59
0x18003dcc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dccd  jmp     short loc_18003DC63
0x18003dccf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dcd6  lea     r8, WPP_528c6086732434342200d826d3525973_Traceguids
0x18003dcdd  mov     edx, 5Eh ; '^'
0x18003dce2  mov     dword ptr [rsp+68h+var_48], edi
  ... truncated ...
```
