# SetUserBroker(ulong)

- ea: `0x18005e610`
- end: `0x18005e691`
- name: `?SetUserBroker@@YAJK@Z`
- size: `129`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005e4c0`

## callees

- `0x18005e610`
- `0x18005e73c`
- `0x18005e7fc`
- `0x18005e85c`
- `0x18005e9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e67e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e67e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e623`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e658`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e658`

## pseudocode

```c
__int64 __fastcall SetUserBroker(unsigned int a1)
{
  int v2; // ebx
  DWORD CurrentThreadId; // eax
  DWORD v4; // eax

  EnterCriticalSection(&g_csInit);
  if ( a1 )
  {
    v2 = EnsureCDSA();
    if ( v2 >= 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v2 = AddGITCookie(a1, CurrentThreadId, 0);
    }
  }
  else if ( g_pcdsaThreadData )
  {
    v4 = GetCurrentThreadId();
    v2 = RemoveGITCookie(v4);
    if ( v2 >= 0 )
      DeleteCDSAIfEmpty();
  }
  else
  {
    v2 = -2147418113;
  }
  LeaveCriticalSection(&g_csInit);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005e610  mov     [rsp+arg_0], rbx
0x18005e615  push    rdi
0x18005e616  sub     rsp, 20h
0x18005e61a  mov     edi, ecx
0x18005e61c  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e623  call    cs:__imp_EnterCriticalSection
0x18005e629  test    edi, edi
0x18005e62b  jz      short loc_18005E64E
0x18005e62d  call    _EnsureCDSA
0x18005e632  mov     ebx, eax
0x18005e634  test    eax, eax
0x18005e636  js      short loc_18005E677
0x18005e638  call    cs:__imp_GetCurrentThreadId
0x18005e63e  xor     r8d, r8d
0x18005e641  mov     ecx, edi
0x18005e643  mov     edx, eax
0x18005e645  call    _AddGITCookie
0x18005e64a  mov     ebx, eax
0x18005e64c  jmp     short loc_18005E677
0x18005e64e  cmp     cs:?g_pcdsaThreadData@@3PEAV?$CDSA@UTHREAD_GIT_MAPPING@@@@EA, 0; CDSA<THREAD_GIT_MAPPING> * g_pcdsaThreadData
0x18005e656  jz      short loc_18005E672
0x18005e658  call    cs:__imp_GetCurrentThreadId
0x18005e65e  mov     ecx, eax
0x18005e660  call    _RemoveGITCookie
0x18005e665  mov     ebx, eax
0x18005e667  test    eax, eax
0x18005e669  js      short loc_18005E677
0x18005e66b  call    _DeleteCDSAIfEmpty
0x18005e670  jmp     short loc_18005E677
0x18005e672  mov     ebx, 8000FFFFh
0x18005e677  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e67e  call    cs:__imp_LeaveCriticalSection
0x18005e684  mov     eax, ebx
0x18005e686  mov     rbx, [rsp+28h+arg_0]
0x18005e68b  add     rsp, 20h
0x18005e68f  pop     rdi
0x18005e690  retn
```
