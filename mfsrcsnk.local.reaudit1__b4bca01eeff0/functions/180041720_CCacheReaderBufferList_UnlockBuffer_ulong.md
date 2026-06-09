# CCacheReaderBufferList::UnlockBuffer(ulong)

- ea: `0x180041720`
- end: `0x180041a87`
- name: `?UnlockBuffer@CCacheReaderBufferList@@QEAAJK@Z`
- size: `871`
- prototype: `__int64 __fastcall(CCacheReaderBufferList *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180021fb0`
- `0x180040700`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x180041720`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800417a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004187a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800417a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004187a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004194f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004194f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800418c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800418c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041789`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041860`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041789`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800419af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800419af`

## string_xrefs

- `0x18004175a`: `CCacheReaderBufferList::UnlockBuffer`

## pseudocode

```c
__int64 __fastcall CCacheReaderBufferList::UnlockBuffer(__int64 **this, __int64 a2)
{
  unsigned int v3; // r14d
  CallStackTracing *v4; // rbx
  char *v5; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ebp
  __int64 *v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  CallStackTracing *v16; // rbx
  GUID *v17; // rdi
  DWORD v18; // esi
  GUID *v19; // rax
  int v20; // eax
  int v21; // eax
  CallStackTracing *v23; // rax
  CallStackTracing *v24; // rcx
  __int64 v25; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v30; // rdx

  v3 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v23;
    if ( !v23 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      v25 = (**(__int64 (__fastcall ***)(CallStackTracing *))v24)(v24);
      if ( v25 )
        v5 = (char *)v25;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CCacheReaderBufferList::UnlockBuffer";
      *(_DWORD *)&v5[8 * v9 + 8] = 867;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( v3 > *((_DWORD *)this + 116) )
  {
    v10 = -1072875829;
    if ( g_wppLevels )
    {
      v30 = 56;
LABEL_47:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v10);
    }
  }
  else
  {
    v10 = 0;
    v11 = this[54];
    v12 = 0;
    while ( v11 )
    {
      v13 = *v11;
      v11 = (__int64 *)v11[1];
      v12 += *(_DWORD *)(v13 + 32);
      if ( v3 + *((_DWORD *)this + 114) < v12 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 16) + 32LL))(*(_QWORD *)(v13 + 16));
        if ( v10 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, v14);
            CallStackTracing::s_wpInstance = v28;
            if ( !v28
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CCacheReaderBufferList::UnlockBuffer", 893, v10);
          }
          if ( g_wppLevels )
          {
            v30 = 57;
            goto LABEL_47;
          }
        }
        break;
      }
    }
  }
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
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = CallStackTracing::s_wpInstance;
      }
      v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
      if ( v27 )
        v17 = (GUID *)v27;
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
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180041720  push    rbx
0x180041722  push    rsi
0x180041723  push    r15
0x180041725  sub     rsp, 40h
0x180041729  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180041731  mov     rsi, rcx
0x180041734  mov     [rsp+58h+arg_10], r12
0x180041739  mov     [rsp+58h+var_20], r13
0x18004173e  lea     r13, qword_1801B97E0
0x180041745  mov     [rsp+58h+var_28], r14
0x18004174a  mov     r14d, edx
0x18004174d  jz      loc_1800418ED
0x180041753  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004175a  lea     r12, aCcachereaderbu_0; "CCacheReaderBufferList::UnlockBuffer"
0x180041761  mov     [rsp+58h+arg_0], rbp
0x180041766  mov     [rsp+58h+arg_8], rdi
0x18004176b  cmp     byte ptr [rbx+8], 0
0x18004176f  jz      short loc_1800417D2
0x180041771  lea     rdi, [rbx+0D0h]
0x180041778  call    cs:__imp_GetLastError
0x18004177f  nop     dword ptr [rax+rax+00h]
0x180041784  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180041787  mov     ebp, eax
0x180041789  call    cs:__imp_TlsGetValue
0x180041790  nop     dword ptr [rax+rax+00h]
0x180041795  test    rax, rax
0x180041798  jz      loc_180041918
0x18004179e  mov     rdi, rax
0x1800417a1  mov     ecx, ebp; dwErrCode
0x1800417a3  call    cs:__imp_SetLastError
0x1800417aa  nop     dword ptr [rax+rax+00h]
0x1800417af  mov     eax, [rdi+7C4h]
0x1800417b5  cmp     eax, [rdi+7C8h]
0x1800417bb  jnb     short loc_1800417CC
0x1800417bd  add     rax, rax
0x1800417c0  mov     [rdi+rax*8], r12
0x1800417c4  mov     dword ptr [rdi+rax*8+8], 363h
0x1800417cc  inc     dword ptr [rdi+7C4h]
0x1800417d2  xor     r15d, r15d
0x1800417d5  cmp     r14d, [rsi+1D0h]
0x1800417dc  ja      loc_180041A17
0x1800417e2  mov     r9d, [rsi+1C8h]
0x1800417e9  mov     ebp, r15d
0x1800417ec  mov     rcx, [rsi+1B0h]
0x1800417f3  add     r9d, r14d
0x1800417f6  mov     edx, r15d
0x1800417f9  test    rcx, rcx
0x1800417fc  jz      short loc_180041828
0x1800417fe  mov     r8, [rcx]
0x180041801  mov     rcx, [rcx+8]
0x180041805  add     edx, [r8+20h]
0x180041809  cmp     r9d, edx
0x18004180c  jnb     short loc_1800417F9
0x18004180e  mov     rcx, [r8+10h]
0x180041812  mov     rax, [rcx]
0x180041815  mov     rax, [rax+20h]
0x180041819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004181e  mov     ebp, eax
0x180041820  test    eax, eax
0x180041822  js      loc_1800419A2
0x180041828  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004182f  mov     r14, [rsp+58h+var_28]
0x180041834  mov     r13, [rsp+58h+var_20]
0x180041839  mov     r12, [rsp+58h+arg_10]
0x18004183e  cmp     [rbx+8], r15b
0x180041842  jz      loc_1800418D7
0x180041848  lea     rdi, [rbx+0D0h]
0x18004184f  call    cs:__imp_GetLastError
0x180041856  nop     dword ptr [rax+rax+00h]
0x18004185b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004185e  mov     esi, eax
0x180041860  call    cs:__imp_TlsGetValue
0x180041867  nop     dword ptr [rax+rax+00h]
0x18004186c  test    rax, rax
0x18004186f  jz      loc_18004194F
0x180041875  mov     rdi, rax
0x180041878  mov     ecx, esi; dwErrCode
0x18004187a  call    cs:__imp_SetLastError
0x180041881  nop     dword ptr [rax+rax+00h]
0x180041886  mov     eax, [rdi+7C4h]
0x18004188c  test    eax, eax
0x18004188e  jz      short loc_1800418D7
0x180041890  sub     eax, 1
0x180041893  mov     [rdi+7C4h], eax
0x180041899  jnz     short loc_1800418D7
0x18004189b  mov     [rdi+7C4h], r15d
0x1800418a2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800418a9  mov     [rdi+7E0h], r15
0x1800418b0  mov     [rdi+7CCh], r15d
0x1800418b7  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800418be  mov     [rdi+7E8h], r15d
0x1800418c5  call    cs:__imp_GetCurrentThreadId
0x1800418cc  nop     dword ptr [rax+rax+00h]
0x1800418d1  mov     [rdi+7C0h], eax
0x1800418d7  mov     rdi, [rsp+58h+arg_8]
0x1800418dc  mov     eax, ebp
0x1800418de  mov     rbp, [rsp+58h+arg_0]
0x1800418e3  add     rsp, 40h
0x1800418e7  pop     r15
0x1800418e9  pop     rsi
0x1800418ea  pop     rbx
0x1800418eb  retn
0x1800418ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800418f4  nop     dword ptr [rax+rax+00h]
0x1800418f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041900  mov     rcx, rax
0x180041903  test    rax, rax
0x180041906  jnz     loc_1800419F9
0x18004190c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180041913  jmp     loc_180041753
0x180041918  call    cs:__imp_GetLastError
0x18004191f  nop     dword ptr [rax+rax+00h]
0x180041924  test    eax, eax
0x180041926  jnz     loc_1800417A1
0x18004192c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041933  test    rcx, rcx
0x180041936  jz      short loc_180041986
0x180041938  mov     rax, [rcx]
0x18004193b  mov     rax, [rax]
0x18004193e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041943  test    rax, rax
0x180041946  cmovnz  rdi, rax
0x18004194a  jmp     loc_1800417A1
0x18004194f  call    cs:__imp_GetLastError
0x180041956  nop     dword ptr [rax+rax+00h]
0x18004195b  test    eax, eax
0x18004195d  jnz     loc_180041878
0x180041963  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004196a  test    rcx, rcx
0x18004196d  jz      short loc_180041994
0x18004196f  mov     rax, [rcx]
0x180041972  mov     rax, [rax]
0x180041975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004197a  test    rax, rax
0x18004197d  cmovnz  rdi, rax
0x180041981  jmp     loc_180041878
0x180041986  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004198b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041992  jmp     short loc_180041938
0x180041994  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180041999  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419a0  jmp     short loc_18004196F
0x1800419a2  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419a9  jnz     loc_180041A45
0x1800419af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800419b6  nop     dword ptr [rax+rax+00h]
0x1800419bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419c2  mov     rcx, rax
0x1800419c5  test    rax, rax
0x1800419c8  jnz     short loc_180041A30
0x1800419ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419d1  jmp     short loc_180041A45
0x1800419d3  mov     rcx, rbx; this
0x1800419d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800419db  cmp     [rax+7CCh], ebp
0x1800419e1  jz      short loc_180041A52
0x1800419e3  mov     r9d, ebp; int
0x1800419e6  mov     r8d, 37Dh; int
0x1800419ec  mov     rdx, r12; char *
0x1800419ef  mov     rcx, rax; this
0x1800419f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800419f7  jmp     short loc_180041A52
0x1800419f9  mov     rax, [rax]
0x1800419fc  mov     edx, 7F0h
0x180041a01  mov     rax, [rax+8]
0x180041a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a0a  test    eax, eax
0x180041a0c  jnz     loc_180041753
0x180041a12  jmp     loc_18004190C
0x180041a17  mov     ebp, 0C00D36CBh
0x180041a1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041a23  jb      loc_180041828
0x180041a29  mov     edx, 38h ; '8'
0x180041a2e  jmp     short loc_180041A64
0x180041a30  mov     rax, [rax]
0x180041a33  mov     edx, 7F0h
0x180041a38  mov     rax, [rax+8]
0x180041a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a41  test    eax, eax
0x180041a43  jz      short loc_1800419CA
0x180041a45  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a4c  cmp     [rbx+8], r15b
0x180041a50  jnz     short loc_1800419D3
0x180041a52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041a59  jb      loc_180041828
0x180041a5f  mov     edx, 39h ; '9'
0x180041a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a6b  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x180041a72  mov     r9, rsi
0x180041a75  mov     [rsp+58h+var_38], ebp
0x180041a79  mov     rcx, [rcx+10h]
0x180041a7d  call    WPP_SF_qD
0x180041a82  jmp     loc_180041828
```
