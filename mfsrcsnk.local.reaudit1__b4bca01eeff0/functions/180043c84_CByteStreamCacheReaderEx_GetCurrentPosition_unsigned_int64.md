# CByteStreamCacheReaderEx::GetCurrentPosition(unsigned __int64 *)

- ea: `0x180043c84`
- end: `0x180043eec`
- name: `?GetCurrentPosition@CByteStreamCacheReaderEx@@QEAAJPEA_K@Z`
- size: `616`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, unsigned __int64 *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180051904`
- `0x18007395c`
- `0x1800a781c`
- `0x1800e94ac`
- `0x180157364`
- `0x180157dec`
- `0x180173e2c`

## callees

- `0x180043c84`
- `0x180077708`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043cdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043d92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043cdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043d1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043deb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043deb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043cc3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043d78`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043cc3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043d78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043e0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043e0b`

## string_xrefs

- `0x180043cfa`: `CByteStreamCacheReaderEx::GetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReaderEx::GetCurrentPosition(CByteStreamCacheReaderEx *this, unsigned __int64 *a2)
{
  wchar_t *v2; // rbx
  wchar_t *v5; // rdi
  DWORD LastError; // ebp
  wchar_t *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  CallStackTracing *v11; // rdi
  GUID *v12; // rbx
  DWORD v13; // esi
  GUID *v14; // rax
  int v15; // eax
  int v16; // eax
  CallStackTracing *v18; // rax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax

  v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = v2 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v19 = CallStackTracing::s_wpInstance;
      }
      v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
      if ( v20 )
        v5 = (wchar_t *)v20;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[4 * v9] = "CByteStreamCacheReaderEx::GetCurrentPosition";
      *(_DWORD *)&v5[4 * v9 + 4] = 439;
    }
    ++*((_DWORD *)v5 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v10 = *((_QWORD *)this + 64);
  if ( v10 == -1 )
    v10 = *((_QWORD *)this + 63);
  *a2 = v10;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v11 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v12 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v13 = GetLastError();
    v14 = (GUID *)TlsGetValue(*((_DWORD *)v11 + 3));
    if ( v14 )
    {
      v12 = v14;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v21 = CallStackTracing::s_wpInstance;
      }
      v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v22 )
        v12 = (GUID *)v22;
    }
    SetLastError(v13);
    v15 = *(_DWORD *)&v12[124].Data2;
    if ( v15 )
    {
      v16 = v15 - 1;
      *(_DWORD *)&v12[124].Data2 = v16;
      if ( !v16 )
      {
        *(_DWORD *)&v12[124].Data2 = 0;
        *(_QWORD *)&v12[126].Data1 = 0;
        *(_DWORD *)&v12[124].Data4[4] = 0;
        v12[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v12[126].Data4 = 0;
        v12[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180043c84  push    rbx
0x180043c86  push    rbp
0x180043c87  push    rsi
0x180043c88  push    rdi
0x180043c89  push    r14
0x180043c8b  sub     rsp, 20h
0x180043c8f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043c96  mov     r14, rdx
0x180043c99  mov     rsi, rcx
0x180043c9c  test    rbx, rbx
0x180043c9f  jz      loc_180043E0B
0x180043ca5  cmp     byte ptr [rbx+8], 0
0x180043ca9  jz      short loc_180043D13
0x180043cab  lea     rdi, [rbx+0D0h]
0x180043cb2  call    cs:__imp_GetLastError
0x180043cb9  nop     dword ptr [rax+rax+00h]
0x180043cbe  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180043cc1  mov     ebp, eax
0x180043cc3  call    cs:__imp_TlsGetValue
0x180043cca  nop     dword ptr [rax+rax+00h]
0x180043ccf  test    rax, rax
0x180043cd2  jz      loc_180043E3D
0x180043cd8  mov     rdi, rax
0x180043cdb  mov     ecx, ebp; dwErrCode
0x180043cdd  call    cs:__imp_SetLastError
0x180043ce4  nop     dword ptr [rax+rax+00h]
0x180043ce9  mov     eax, [rdi+7C4h]
0x180043cef  cmp     eax, [rdi+7C8h]
0x180043cf5  jnb     short loc_180043D0D
0x180043cf7  add     rax, rax
0x180043cfa  lea     rcx, aCbytestreamcac_21; "CByteStreamCacheReaderEx::GetCurrentPos"...
0x180043d01  mov     [rdi+rax*8], rcx
0x180043d05  mov     dword ptr [rdi+rax*8+8], 1B7h
0x180043d0d  inc     dword ptr [rdi+7C4h]
0x180043d13  lea     rbx, [rsi+238h]
0x180043d1a  mov     rcx, rbx; lpCriticalSection
0x180043d1d  call    cs:__imp_EnterCriticalSection
0x180043d24  nop     dword ptr [rax+rax+00h]
0x180043d29  mov     rax, [rsi+200h]
0x180043d30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043d34  jnz     short loc_180043D3D
0x180043d36  mov     rax, [rsi+1F8h]
0x180043d3d  mov     rcx, rbx; lpCriticalSection
0x180043d40  mov     [r14], rax
0x180043d43  call    cs:__imp_LeaveCriticalSection
0x180043d4a  nop     dword ptr [rax+rax+00h]
0x180043d4f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043d56  cmp     byte ptr [rdi+8], 0
0x180043d5a  jz      loc_180043DFD
0x180043d60  lea     rbx, [rdi+0D0h]
0x180043d67  call    cs:__imp_GetLastError
0x180043d6e  nop     dword ptr [rax+rax+00h]
0x180043d73  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180043d76  mov     esi, eax
0x180043d78  call    cs:__imp_TlsGetValue
0x180043d7f  nop     dword ptr [rax+rax+00h]
0x180043d84  test    rax, rax
0x180043d87  jz      loc_180043E74
0x180043d8d  mov     rbx, rax
0x180043d90  mov     ecx, esi; dwErrCode
0x180043d92  call    cs:__imp_SetLastError
0x180043d99  nop     dword ptr [rax+rax+00h]
0x180043d9e  mov     eax, [rbx+7C4h]
0x180043da4  test    eax, eax
0x180043da6  jz      short loc_180043DFD
0x180043da8  sub     eax, 1
0x180043dab  mov     [rbx+7C4h], eax
0x180043db1  jnz     short loc_180043DFD
0x180043db3  mov     dword ptr [rbx+7C4h], 0
0x180043dbd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180043dc4  mov     qword ptr [rbx+7E0h], 0
0x180043dcf  mov     dword ptr [rbx+7CCh], 0
0x180043dd9  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x180043de1  mov     dword ptr [rbx+7E8h], 0
0x180043deb  call    cs:__imp_GetCurrentThreadId
0x180043df2  nop     dword ptr [rax+rax+00h]
0x180043df7  mov     [rbx+7C0h], eax
0x180043dfd  xor     eax, eax
0x180043dff  add     rsp, 20h
0x180043e03  pop     r14
0x180043e05  pop     rdi
0x180043e06  pop     rsi
0x180043e07  pop     rbp
0x180043e08  pop     rbx
0x180043e09  retn
0x180043e0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043e12  nop     dword ptr [rax+rax+00h]
0x180043e17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e1e  mov     rcx, rax
0x180043e21  test    rax, rax
0x180043e24  jnz     loc_180043EC7
0x180043e2a  lea     rbx, qword_1801B97E0
0x180043e31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e38  jmp     loc_180043CA5
0x180043e3d  call    cs:__imp_GetLastError
0x180043e44  nop     dword ptr [rax+rax+00h]
0x180043e49  test    eax, eax
0x180043e4b  jnz     loc_180043CDB
0x180043e51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e58  test    rcx, rcx
0x180043e5b  jz      short loc_180043EAB
0x180043e5d  mov     rax, [rcx]
0x180043e60  mov     rax, [rax]
0x180043e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e68  test    rax, rax
0x180043e6b  cmovnz  rdi, rax
0x180043e6f  jmp     loc_180043CDB
0x180043e74  call    cs:__imp_GetLastError
0x180043e7b  nop     dword ptr [rax+rax+00h]
0x180043e80  test    eax, eax
0x180043e82  jnz     loc_180043D90
0x180043e88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e8f  test    rcx, rcx
0x180043e92  jz      short loc_180043EB9
0x180043e94  mov     rax, [rcx]
0x180043e97  mov     rax, [rax]
0x180043e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e9f  test    rax, rax
0x180043ea2  cmovnz  rbx, rax
0x180043ea6  jmp     loc_180043D90
0x180043eab  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180043eb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043eb7  jmp     short loc_180043E5D
0x180043eb9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180043ebe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043ec5  jmp     short loc_180043E94
0x180043ec7  mov     rax, [rax]
0x180043eca  mov     edx, 7F0h
0x180043ecf  mov     rax, [rax+8]
0x180043ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ed8  test    eax, eax
0x180043eda  jz      loc_180043E2A
0x180043ee0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043ee7  jmp     loc_180043CA5
```
