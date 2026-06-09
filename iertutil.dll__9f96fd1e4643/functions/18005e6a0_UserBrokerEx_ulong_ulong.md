# UserBrokerEx(ulong,ulong *)

- ea: `0x18005e6a0`
- end: `0x18005e736`
- name: `?UserBrokerEx@@YAJKPEAK@Z`
- size: `150`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005e6a0`
- `0x18005e73c`
- `0x18005e7fc`
- `0x18005e904`
- `0x18005e9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e6b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e6b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e6ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e6ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e703`

## pseudocode

```c
__int64 __fastcall UserBrokerEx(int a1, unsigned int *a2)
{
  int v4; // ebx
  int v5; // ebx
  DWORD v6; // eax
  __int64 v7; // r8
  int GITCookie; // eax
  DWORD CurrentThreadId; // eax

  EnterCriticalSection(&g_csInit);
  if ( !g_pcdsaThreadData )
  {
    v5 = -2147418113;
    goto LABEL_12;
  }
  if ( !a1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    GITCookie = FindGITCookie(CurrentThreadId, a2);
    goto LABEL_10;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v6 = GetCurrentThreadId();
    LOBYTE(v7) = 1;
    GITCookie = AddGITCookie(*a2, v6, v7);
LABEL_10:
    v5 = GITCookie;
    goto LABEL_12;
  }
  if ( v4 == 1 )
  {
    v5 = RemoveGITCookie(*a2);
    if ( v5 >= 0 )
      DeleteCDSAIfEmpty();
  }
  else
  {
    v5 = -2147467259;
  }
LABEL_12:
  LeaveCriticalSection(&g_csInit);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005e6a0  mov     [rsp+arg_0], rbx
0x18005e6a5  push    rdi
0x18005e6a6  sub     rsp, 20h
0x18005e6aa  mov     ebx, ecx
0x18005e6ac  mov     rdi, rdx
0x18005e6af  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e6b6  call    cs:__imp_EnterCriticalSection
0x18005e6bc  cmp     cs:?g_pcdsaThreadData@@3PEAV?$CDSA@UTHREAD_GIT_MAPPING@@@@EA, 0; CDSA<THREAD_GIT_MAPPING> * g_pcdsaThreadData
0x18005e6c4  jz      short loc_18005E717
0x18005e6c6  test    ebx, ebx
0x18005e6c8  jz      short loc_18005E703
0x18005e6ca  sub     ebx, 1
0x18005e6cd  jz      short loc_18005E6EF
0x18005e6cf  cmp     ebx, 1
0x18005e6d2  jz      short loc_18005E6DB
0x18005e6d4  mov     ebx, 80004005h
0x18005e6d9  jmp     short loc_18005E71C
0x18005e6db  mov     ecx, [rdi]
0x18005e6dd  call    _RemoveGITCookie
0x18005e6e2  mov     ebx, eax
0x18005e6e4  test    eax, eax
0x18005e6e6  js      short loc_18005E71C
0x18005e6e8  call    _DeleteCDSAIfEmpty
0x18005e6ed  jmp     short loc_18005E71C
0x18005e6ef  call    cs:__imp_GetCurrentThreadId
0x18005e6f5  mov     ecx, [rdi]
0x18005e6f7  mov     r8b, 1
0x18005e6fa  mov     edx, eax
0x18005e6fc  call    _AddGITCookie
0x18005e701  jmp     short loc_18005E713
0x18005e703  call    cs:__imp_GetCurrentThreadId
0x18005e709  mov     ecx, eax
0x18005e70b  mov     rdx, rdi
0x18005e70e  call    _FindGITCookie
0x18005e713  mov     ebx, eax
0x18005e715  jmp     short loc_18005E71C
0x18005e717  mov     ebx, 8000FFFFh
0x18005e71c  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e723  call    cs:__imp_LeaveCriticalSection
0x18005e729  mov     eax, ebx
0x18005e72b  mov     rbx, [rsp+28h+arg_0]
0x18005e730  add     rsp, 20h
0x18005e734  pop     rdi
0x18005e735  retn
```
