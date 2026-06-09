# ShutDownPushRouterSynchronously

- ea: `0x180010930`
- end: `0x180010a2f`
- name: `ShutDownPushRouterSynchronously`
- size: `255`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003a14`
- `0x180010930`
- `0x180013c24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800109cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800109cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010943`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010943`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001099c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001099c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010960`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010960`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ShutDownPushRouterSynchronously()
{
  signed int v0; // ebx
  signed int v1; // eax
  void *v2; // rcx
  signed int LastError; // eax
  PushRouter *v4; // rdi

  v0 = 0;
  EnterCriticalSection(&g_csPushRouter);
  if ( g_pPushRouter )
  {
    g_hevtShutdownComplete = CreateEventW(0, 0, 0, 0);
    if ( g_hevtShutdownComplete )
    {
      v2 = (void *)*((_QWORD *)g_pPushRouter + 25);
      if ( v2 )
      {
        if ( !SetEvent(v2) )
        {
          LastError = GetLastError();
          v0 = LastError;
          if ( LastError > 0 )
            v0 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      if ( v0 >= 0 )
        WaitForSingleObject(g_hevtShutdownComplete, 0x7530u);
      v4 = g_pPushRouter;
      if ( g_pPushRouter )
      {
        PushRouter::~PushRouter(g_pPushRouter);
        operator delete(v4, (const struct std::nothrow_t *)0x118);
      }
      g_pPushRouter = 0;
    }
    else
    {
      v1 = GetLastError();
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
    }
  }
  CloseHandle(g_hevtShutdownComplete);
  g_hevtShutdownComplete = 0;
  LeaveCriticalSection(&g_csPushRouter);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180010930  mov     [rsp+arg_0], rbx
0x180010935  push    rdi
0x180010936  sub     rsp, 20h
0x18001093a  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010941  xor     ebx, ebx
0x180010943  call    cs:__imp_EnterCriticalSection
0x180010949  cmp     cs:?g_pPushRouter@@3PEAVPushRouter@@EA, rbx; PushRouter * g_pPushRouter
0x180010950  jz      loc_1800109FD
0x180010956  xor     r9d, r9d; lpName
0x180010959  xor     r8d, r8d; bInitialState
0x18001095c  xor     edx, edx; bManualReset
0x18001095e  xor     ecx, ecx; lpEventAttributes
0x180010960  call    cs:__imp_CreateEventW
0x180010966  mov     cs:?g_hevtShutdownComplete@@3PEAXEA, rax; void * g_hevtShutdownComplete
0x18001096d  test    rax, rax
0x180010970  jnz     short loc_180010989
0x180010972  call    cs:__imp_GetLastError
0x180010978  mov     ebx, eax
0x18001097a  test    eax, eax
0x18001097c  jle     short loc_1800109FD
0x18001097e  movzx   ebx, ax
0x180010981  or      ebx, 80070000h
0x180010987  jmp     short loc_1800109FD
0x180010989  mov     rax, cs:?g_pPushRouter@@3PEAVPushRouter@@EA; PushRouter * g_pPushRouter
0x180010990  mov     rcx, [rax+0C8h]; hEvent
0x180010997  test    rcx, rcx
0x18001099a  jz      short loc_1800109BB
0x18001099c  call    cs:__imp_SetEvent
0x1800109a2  test    eax, eax
0x1800109a4  jnz     short loc_1800109BB
0x1800109a6  call    cs:__imp_GetLastError
0x1800109ac  mov     ebx, eax
0x1800109ae  test    eax, eax
0x1800109b0  jle     short loc_1800109BB
0x1800109b2  movzx   ebx, ax
0x1800109b5  or      ebx, 80070000h
0x1800109bb  test    ebx, ebx
0x1800109bd  js      short loc_1800109D1
0x1800109bf  mov     rcx, cs:?g_hevtShutdownComplete@@3PEAXEA; hHandle
0x1800109c6  mov     edx, 7530h; dwMilliseconds
0x1800109cb  call    cs:__imp_WaitForSingleObject
0x1800109d1  mov     rdi, cs:?g_pPushRouter@@3PEAVPushRouter@@EA; PushRouter * g_pPushRouter
0x1800109d8  test    rdi, rdi
0x1800109db  jz      short loc_1800109F2
0x1800109dd  mov     rcx, rdi; this
0x1800109e0  call    ??1PushRouter@@QEAA@XZ; PushRouter::~PushRouter(void)
0x1800109e5  mov     edx, 118h; struct std::nothrow_t *
0x1800109ea  mov     rcx, rdi; void *
0x1800109ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800109f2  mov     cs:?g_pPushRouter@@3PEAVPushRouter@@EA, 0; PushRouter * g_pPushRouter
0x1800109fd  mov     rcx, cs:?g_hevtShutdownComplete@@3PEAXEA; hObject
0x180010a04  call    cs:__imp_CloseHandle
0x180010a0a  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010a11  mov     cs:?g_hevtShutdownComplete@@3PEAXEA, 0; void * g_hevtShutdownComplete
0x180010a1c  call    cs:__imp_LeaveCriticalSection
0x180010a22  mov     eax, ebx
0x180010a24  mov     rbx, [rsp+28h+arg_0]
0x180010a29  add     rsp, 20h
0x180010a2d  pop     rdi
0x180010a2e  retn
```
