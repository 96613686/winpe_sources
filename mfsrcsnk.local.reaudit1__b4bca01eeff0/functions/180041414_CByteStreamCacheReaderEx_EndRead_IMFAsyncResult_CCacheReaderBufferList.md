# CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)

- ea: `0x180041414`
- end: `0x180041712`
- name: `?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, struct IMFAsyncResult *, struct CCacheReaderBufferList **)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180040700`
- `0x18007395c`
- `0x1800e94ac`
- `0x180157364`
- `0x180174930`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x180041414`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041480`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041554`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041480`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004160e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004160e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041505`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041505`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800415a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800415a0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041466`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004153a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041466`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004153a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004166d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004166d`

## string_xrefs

- `0x180041441`: `CByteStreamCacheReaderEx::EndRead`

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
  struct CCacheReaderBufferList *v15; // rax
  CallStackTracing *v16; // rdi
  GUID *v17; // rbx
  DWORD v18; // esi
  GUID *v19; // rax
  int v20; // eax
  int v21; // eax
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
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
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
      if ( v24 )
        v7 = (char *)v24;
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
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v14 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReaderEx::EndRead", 215, v14);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v14);
  }
  else
  {
    v15 = (struct CCacheReaderBufferList *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    *a3 = v15;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v16 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v17 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v18 = GetLastError();
    v19 = (GUID *)TlsGetValue(*((_DWORD *)v16 + 3));
    if ( v19 )
    {
      v17 = v19;
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
        v17 = (GUID *)v26;
    }
    SetLastError(v18);
    v20 = *(_DWORD *)&v17[124].Data2;
    if ( v20 )
    {
      v21 = v20 - 1;
      *(_DWORD *)&v17[124].Data2 = v21;
      if ( !v21 )
      {
        *(_DWORD *)&v17[124].Data2 = 0;
        *(_QWORD *)&v17[126].Data1 = 0;
        *(_DWORD *)&v17[124].Data4[4] = 0;
        v17[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v17[126].Data4 = 0;
        v17[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180041414  push    rbx
0x180041416  push    rbp
0x180041417  push    rsi
0x180041418  push    rdi
0x180041419  push    r12
0x18004141b  push    r13
0x18004141d  push    r14
0x18004141f  push    r15
0x180041421  sub     rsp, 38h
0x180041425  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004142c  xor     r12d, r12d
0x18004142f  mov     r15, r8
0x180041432  mov     r14, rdx
0x180041435  mov     rsi, rcx
0x180041438  test    rdi, rdi
0x18004143b  jz      loc_1800415C6
0x180041441  lea     r13, aCbytestreamcac_14; "CByteStreamCacheReaderEx::EndRead"
0x180041448  cmp     [rdi+8], r12b
0x18004144c  jz      short loc_1800414AF
0x18004144e  lea     rbx, [rdi+0D0h]
0x180041455  call    cs:__imp_GetLastError
0x18004145c  nop     dword ptr [rax+rax+00h]
0x180041461  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180041464  mov     ebp, eax
0x180041466  call    cs:__imp_TlsGetValue
0x18004146d  nop     dword ptr [rax+rax+00h]
0x180041472  test    rax, rax
0x180041475  jz      loc_1800415D7
0x18004147b  mov     rbx, rax
0x18004147e  mov     ecx, ebp; dwErrCode
0x180041480  call    cs:__imp_SetLastError
0x180041487  nop     dword ptr [rax+rax+00h]
0x18004148c  mov     eax, [rbx+7C4h]
0x180041492  cmp     eax, [rbx+7C8h]
0x180041498  jnb     short loc_1800414A9
0x18004149a  add     rax, rax
0x18004149d  mov     [rbx+rax*8], r13
0x1800414a1  mov     dword ptr [rbx+rax*8+8], 0CDh
0x1800414a9  inc     dword ptr [rbx+7C4h]
0x1800414af  lea     rbx, [rsi+238h]
0x1800414b6  mov     rcx, rbx; lpCriticalSection
0x1800414b9  call    cs:__imp_EnterCriticalSection
0x1800414c0  nop     dword ptr [rax+rax+00h]
0x1800414c5  mov     rcx, [rsi+10h]
0x1800414c9  test    rcx, rcx
0x1800414cc  jz      short loc_1800414DE
0x1800414ce  mov     rax, [rcx]
0x1800414d1  mov     rax, [rax+10h]
0x1800414d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414da  mov     [rsi+10h], r12
0x1800414de  mov     rax, [r14]
0x1800414e1  mov     rcx, r14
0x1800414e4  mov     rax, [rax+20h]
0x1800414e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414ed  mov     ebp, eax
0x1800414ef  test    eax, eax
0x1800414f1  js      loc_180041661
0x1800414f7  mov     rax, [rsi+20h]
0x1800414fb  mov     [rsi+20h], r12
0x1800414ff  mov     [r15], rax
0x180041502  mov     rcx, rbx; lpCriticalSection
0x180041505  call    cs:__imp_LeaveCriticalSection
0x18004150c  nop     dword ptr [rax+rax+00h]
0x180041511  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041518  cmp     [rdi+8], r12b
0x18004151c  jz      loc_1800415B2
0x180041522  lea     rbx, [rdi+0D0h]
0x180041529  call    cs:__imp_GetLastError
0x180041530  nop     dword ptr [rax+rax+00h]
0x180041535  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180041538  mov     esi, eax
0x18004153a  call    cs:__imp_TlsGetValue
0x180041541  nop     dword ptr [rax+rax+00h]
0x180041546  test    rax, rax
0x180041549  jz      loc_18004160E
0x18004154f  mov     rbx, rax
0x180041552  mov     ecx, esi; dwErrCode
0x180041554  call    cs:__imp_SetLastError
0x18004155b  nop     dword ptr [rax+rax+00h]
0x180041560  mov     eax, [rbx+7C4h]
0x180041566  test    eax, eax
0x180041568  jz      short loc_1800415B2
0x18004156a  sub     eax, 1
0x18004156d  mov     [rbx+7C4h], eax
0x180041573  jnz     short loc_1800415B2
0x180041575  mov     [rbx+7C4h], r12d
0x18004157c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180041583  mov     [rbx+7E0h], r12
0x18004158a  mov     [rbx+7CCh], r12d
0x180041591  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x180041599  mov     [rbx+7E8h], r12d
0x1800415a0  call    cs:__imp_GetCurrentThreadId
0x1800415a7  nop     dword ptr [rax+rax+00h]
0x1800415ac  mov     [rbx+7C0h], eax
0x1800415b2  mov     eax, ebp
0x1800415b4  add     rsp, 38h
0x1800415b8  pop     r15
0x1800415ba  pop     r14
0x1800415bc  pop     r13
0x1800415be  pop     r12
0x1800415c0  pop     rdi
0x1800415c1  pop     rsi
0x1800415c2  pop     rbp
0x1800415c3  pop     rbx
0x1800415c4  retn
0x1800415c6  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800415cb  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415d2  jmp     loc_180041441
0x1800415d7  call    cs:__imp_GetLastError
0x1800415de  nop     dword ptr [rax+rax+00h]
0x1800415e3  test    eax, eax
0x1800415e5  jnz     loc_18004147E
0x1800415eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415f2  test    rcx, rcx
0x1800415f5  jz      short loc_180041645
0x1800415f7  mov     rax, [rcx]
0x1800415fa  mov     rax, [rax]
0x1800415fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041602  test    rax, rax
0x180041605  cmovnz  rbx, rax
0x180041609  jmp     loc_18004147E
0x18004160e  call    cs:__imp_GetLastError
0x180041615  nop     dword ptr [rax+rax+00h]
0x18004161a  test    eax, eax
0x18004161c  jnz     loc_180041552
0x180041622  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041629  test    rcx, rcx
0x18004162c  jz      short loc_180041653
0x18004162e  mov     rax, [rcx]
0x180041631  mov     rax, [rax]
0x180041634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041639  test    rax, rax
0x18004163c  cmovnz  rbx, rax
0x180041640  jmp     loc_180041552
0x180041645  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004164a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041651  jmp     short loc_1800415F7
0x180041653  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180041658  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004165f  jmp     short loc_18004162E
0x180041661  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041668  test    rcx, rcx
0x18004166b  jnz     short loc_1800416D7
0x18004166d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041674  nop     dword ptr [rax+rax+00h]
0x180041679  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041680  mov     rcx, rax
0x180041683  test    rax, rax
0x180041686  jnz     short loc_1800416BB
0x180041688  lea     rcx, qword_1801B97E0
0x18004168f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041696  jmp     short loc_1800416D7
0x180041698  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004169d  cmp     [rax+7CCh], ebp
0x1800416a3  jz      short loc_1800416DD
0x1800416a5  mov     r9d, ebp; int
0x1800416a8  mov     r8d, 0D7h; int
0x1800416ae  mov     rdx, r13; char *
0x1800416b1  mov     rcx, rax; this
0x1800416b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800416b9  jmp     short loc_1800416DD
0x1800416bb  mov     rax, [rax]
0x1800416be  mov     edx, 7F0h
0x1800416c3  mov     rax, [rax+8]
0x1800416c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416cc  test    eax, eax
0x1800416ce  jz      short loc_180041688
0x1800416d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800416d7  cmp     [rcx+8], r12b
0x1800416db  jnz     short loc_180041698
0x1800416dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800416e4  jb      loc_180041502
0x1800416ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416f1  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x1800416f8  mov     edx, 11h
0x1800416fd  mov     [rsp+78h+var_58], ebp
0x180041701  mov     r9, rsi
0x180041704  mov     rcx, [rcx+10h]
0x180041708  call    WPP_SF_qD
0x18004170d  jmp     loc_180041502
```
