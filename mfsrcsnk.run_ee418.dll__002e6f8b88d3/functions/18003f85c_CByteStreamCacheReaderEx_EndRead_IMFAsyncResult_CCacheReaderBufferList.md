# CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)

- ea: `0x18003f85c`
- end: `0x18003fb0d`
- name: `?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, struct IMFAsyncResult *, struct CCacheReaderBufferList **)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18003eb70`
- `0x18007dfa8`
- `0x1800e2c40`
- `0x18014ee74`
- `0x18016b860`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18003f85c`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f8bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f96e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f8bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f96e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f94f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f94f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f8ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f8ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f9b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f9b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f8a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f95a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f8a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f95a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fa6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fa6e`

## string_xrefs

- `0x18003f889`: `CByteStreamCacheReaderEx::EndRead`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReaderEx::EndRead(
        CByteStreamCacheReaderEx *this,
        struct IMFAsyncResult *a2,
        struct CCacheReaderBufferList **a3)
{
  CallStackTracing *v3; // rdi
  char *v7; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // ebp
  __int64 v15; // r8
  __int64 v16; // r9
  struct CCacheReaderBufferList *v17; // rax
  CallStackTracing *v18; // rdi
  GUID *v19; // rbx
  DWORD v20; // esi
  GUID *v21; // rax
  int v22; // eax
  int v23; // eax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  CallStackTracing *v27; // rcx
  __int64 v28; // rax
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
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
        v7 = (char *)v26;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CByteStreamCacheReaderEx::EndRead";
      *(_DWORD *)&v7[8 * v11 + 8] = 205;
    }
    ++*((_DWORD *)v7 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v12 = *((_QWORD *)this + 2);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 2) = 0;
  }
  v14 = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
  if ( v14 < 0 )
  {
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v15, v16);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v14 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReaderEx::EndRead", 215, v14);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v14);
  }
  else
  {
    v17 = (struct CCacheReaderBufferList *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    *a3 = v17;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v18 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v19 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v20 = GetLastError();
    v21 = (GUID *)TlsGetValue(*((_DWORD *)v18 + 3));
    if ( v21 )
    {
      v19 = v21;
    }
    else if ( !GetLastError() )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v27 = CallStackTracing::s_wpInstance;
      }
      v28 = (**(__int64 (__fastcall ***)(CallStackTracing *))v27)(v27);
      if ( v28 )
        v19 = (GUID *)v28;
    }
    SetLastError(v20);
    v22 = *(_DWORD *)&v19[124].Data2;
    if ( v22 )
    {
      v23 = v22 - 1;
      *(_DWORD *)&v19[124].Data2 = v23;
      if ( !v23 )
      {
        *(_DWORD *)&v19[124].Data2 = 0;
        *(_QWORD *)&v19[126].Data1 = 0;
        *(_DWORD *)&v19[124].Data4[4] = 0;
        v19[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v19[126].Data4 = 0;
        v19[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003f85c  push    rbx
0x18003f85e  push    rbp
0x18003f85f  push    rsi
0x18003f860  push    rdi
0x18003f861  push    r12
0x18003f863  push    r13
0x18003f865  push    r14
0x18003f867  push    r15
0x18003f869  sub     rsp, 38h
0x18003f86d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f874  xor     r12d, r12d
0x18003f877  mov     r15, r8
0x18003f87a  mov     r14, rdx
0x18003f87d  mov     rsi, rcx
0x18003f880  test    rdi, rdi
0x18003f883  jz      loc_18003F9D3
0x18003f889  lea     r13, aCbytestreamcac_14; "CByteStreamCacheReaderEx::EndRead"
0x18003f890  cmp     [rdi+8], r12b
0x18003f894  jz      short loc_18003F8E5
0x18003f896  lea     rbx, [rdi+0D0h]
0x18003f89d  call    cs:__imp_GetLastError
0x18003f8a3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18003f8a6  mov     ebp, eax
0x18003f8a8  call    cs:__imp_TlsGetValue
0x18003f8ae  test    rax, rax
0x18003f8b1  jz      loc_18003F9E4
0x18003f8b7  mov     rbx, rax
0x18003f8ba  mov     ecx, ebp; dwErrCode
0x18003f8bc  call    cs:__imp_SetLastError
0x18003f8c2  mov     eax, [rbx+7C4h]
0x18003f8c8  cmp     eax, [rbx+7C8h]
0x18003f8ce  jnb     short loc_18003F8DF
0x18003f8d0  add     rax, rax
0x18003f8d3  mov     [rbx+rax*8], r13
0x18003f8d7  mov     dword ptr [rbx+rax*8+8], 0CDh
0x18003f8df  inc     dword ptr [rbx+7C4h]
0x18003f8e5  lea     rbx, [rsi+238h]
0x18003f8ec  mov     rcx, rbx; lpCriticalSection
0x18003f8ef  call    cs:__imp_EnterCriticalSection
0x18003f8f5  mov     rcx, [rsi+10h]
0x18003f8f9  test    rcx, rcx
0x18003f8fc  jz      short loc_18003F90E
0x18003f8fe  mov     rax, [rcx]
0x18003f901  mov     rax, [rax+10h]
0x18003f905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f90a  mov     [rsi+10h], r12
0x18003f90e  mov     rax, [r14]
0x18003f911  mov     rcx, r14
0x18003f914  mov     rax, [rax+20h]
0x18003f918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f91d  mov     ebp, eax
0x18003f91f  test    eax, eax
0x18003f921  js      loc_18003FA62
0x18003f927  mov     rax, [rsi+20h]
0x18003f92b  mov     [rsi+20h], r12
0x18003f92f  mov     [r15], rax
0x18003f932  mov     rcx, rbx; lpCriticalSection
0x18003f935  call    cs:__imp_LeaveCriticalSection
0x18003f93b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f942  cmp     [rdi+8], r12b
0x18003f946  jz      short loc_18003F9C0
0x18003f948  lea     rbx, [rdi+0D0h]
0x18003f94f  call    cs:__imp_GetLastError
0x18003f955  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18003f958  mov     esi, eax
0x18003f95a  call    cs:__imp_TlsGetValue
0x18003f960  test    rax, rax
0x18003f963  jz      loc_18003FA15
0x18003f969  mov     rbx, rax
0x18003f96c  mov     ecx, esi; dwErrCode
0x18003f96e  call    cs:__imp_SetLastError
0x18003f974  mov     eax, [rbx+7C4h]
0x18003f97a  test    eax, eax
0x18003f97c  jz      short loc_18003F9C0
0x18003f97e  sub     eax, 1
0x18003f981  mov     [rbx+7C4h], eax
0x18003f987  jnz     short loc_18003F9C0
0x18003f989  mov     [rbx+7C4h], r12d
0x18003f990  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003f997  mov     [rbx+7E0h], r12
0x18003f99e  mov     [rbx+7CCh], r12d
0x18003f9a5  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18003f9ad  mov     [rbx+7E8h], r12d
0x18003f9b4  call    cs:__imp_GetCurrentThreadId
0x18003f9ba  mov     [rbx+7C0h], eax
0x18003f9c0  mov     eax, ebp
0x18003f9c2  add     rsp, 38h
0x18003f9c6  pop     r15
0x18003f9c8  pop     r14
0x18003f9ca  pop     r13
0x18003f9cc  pop     r12
0x18003f9ce  pop     rdi
0x18003f9cf  pop     rsi
0x18003f9d0  pop     rbp
0x18003f9d1  pop     rbx
0x18003f9d2  retn
0x18003f9d3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003f9d8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f9df  jmp     loc_18003F889
0x18003f9e4  call    cs:__imp_GetLastError
0x18003f9ea  test    eax, eax
0x18003f9ec  jnz     loc_18003F8BA
0x18003f9f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f9f9  test    rcx, rcx
0x18003f9fc  jz      short loc_18003FA46
0x18003f9fe  mov     rax, [rcx]
0x18003fa01  mov     rax, [rax]
0x18003fa04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa09  test    rax, rax
0x18003fa0c  cmovnz  rbx, rax
0x18003fa10  jmp     loc_18003F8BA
0x18003fa15  call    cs:__imp_GetLastError
0x18003fa1b  test    eax, eax
0x18003fa1d  jnz     loc_18003F96C
0x18003fa23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa2a  test    rcx, rcx
0x18003fa2d  jz      short loc_18003FA54
0x18003fa2f  mov     rax, [rcx]
0x18003fa32  mov     rax, [rax]
0x18003fa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa3a  test    rax, rax
0x18003fa3d  cmovnz  rbx, rax
0x18003fa41  jmp     loc_18003F96C
0x18003fa46  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003fa4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa52  jmp     short loc_18003F9FE
0x18003fa54  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003fa59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa60  jmp     short loc_18003FA2F
0x18003fa62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa69  test    rcx, rcx
0x18003fa6c  jnz     short loc_18003FAD2
0x18003fa6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fa74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa7b  mov     rcx, rax
0x18003fa7e  test    rax, rax
0x18003fa81  jnz     short loc_18003FAB6
0x18003fa83  lea     rcx, qword_1801B07E0
0x18003fa8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fa91  jmp     short loc_18003FAD2
0x18003fa93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fa98  cmp     [rax+7CCh], ebp
0x18003fa9e  jz      short loc_18003FAD8
0x18003faa0  mov     r9d, ebp; int
0x18003faa3  mov     r8d, 0D7h; int
0x18003faa9  mov     rdx, r13; char *
0x18003faac  mov     rcx, rax; this
0x18003faaf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fab4  jmp     short loc_18003FAD8
0x18003fab6  mov     rax, [rax]
0x18003fab9  mov     edx, 7F0h
0x18003fabe  mov     rax, [rax+8]
0x18003fac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fac7  test    eax, eax
0x18003fac9  jz      short loc_18003FA83
0x18003facb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003fad2  cmp     [rcx+8], r12b
0x18003fad6  jnz     short loc_18003FA93
0x18003fad8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fadf  jb      loc_18003F932
0x18003fae5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003faec  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x18003faf3  mov     edx, 11h
0x18003faf8  mov     [rsp+78h+var_58], ebp
0x18003fafc  mov     r9, rsi
0x18003faff  mov     rcx, [rcx+10h]
0x18003fb03  call    WPP_SF_qD
0x18003fb08  jmp     loc_18003F932
```
