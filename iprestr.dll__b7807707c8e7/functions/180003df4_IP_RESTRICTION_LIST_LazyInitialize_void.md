# IP_RESTRICTION_LIST::LazyInitialize(void)

- ea: `0x180003df4`
- end: `0x180003f21`
- name: `?LazyInitialize@IP_RESTRICTION_LIST@@SAJXZ`
- size: `301`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004110`

## callees

- `0x180003df4`
- `0x180004aa6`
- `0x180004ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003eca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003eca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003e36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003e36`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003ee2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003ee2`
- `iisutil!PuDbgPrint` at `0x180003eaf`
- `iisutil!PuDbgPrint` at `0x180003eaf`
- `W3TP!?CreateThreadPool@THREAD_POOL@@SAHPEAPEAV1@PEAUTHREAD_POOL_CONFIG@@@Z` at `0x180003e75`
- `W3TP!?CreateThreadPool@THREAD_POOL@@SAHPEAPEAV1@PEAUTHREAD_POOL_CONFIG@@@Z` at `0x180003e75`

## string_xrefs

- `0x180003e8f`: `Failed to create ThreadPool for DNS lookups\n`
- `0x180003ea8`: `servercommon\inetsrv\iis\iisrearc\iis70\iprestriction\ip_restriction_list.cxx`

## pseudocode

```c
__int64 IP_RESTRICTION_LIST::LazyInitialize(void)
{
  int v0; // eax
  DWORD dwNumberOfProcessors; // eax
  unsigned int v2; // ebx
  signed __int32 v4[8]; // [rsp+0h] [rbp-79h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-49h] BYREF
  int v6; // [rsp+60h] [rbp-19h] BYREF
  int v7; // [rsp+64h] [rbp-15h]
  DWORD v8; // [rsp+68h] [rbp-11h]
  __int64 v9; // [rsp+6Ch] [rbp-Dh]
  int v10; // [rsp+78h] [rbp-1h]

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  memset_0(&v6, 0, 0x54u);
  GetSystemInfo(&SystemInfo);
  v0 = v7;
  v9 = 600000;
  if ( !v7 )
    v0 = 256;
  v6 = 1;
  v10 = v0;
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  if ( SystemInfo.dwNumberOfProcessors < 2 )
    dwNumberOfProcessors = 2;
  v8 = dwNumberOfProcessors;
  if ( THREAD_POOL::CreateThreadPool(&IP_RESTRICTION_LIST::sm_pThreadPool, (struct THREAD_POOL_CONFIG *)&v6) )
  {
    _InterlockedOr(v4, 0);
    IP_RESTRICTION_LIST::sm_fLazyInitializeComplete = 1;
    return 0;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\iprestriction\\ip_restriction_list.cxx",
        1649,
        "IP_RESTRICTION_LIST::LazyInitialize",
        "Failed to create ThreadPool for DNS lookups\n");
    v2 = -2147467259;
    if ( IP_RESTRICTION_LIST::sm_fInitCritSec )
      DeleteCriticalSection(&IP_RESTRICTION_LIST::sm_csLazyInitialize);
    if ( IP_RESTRICTION_LIST::sm_hTimer )
    {
      DeleteTimerQueueTimer(0, IP_RESTRICTION_LIST::sm_hTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      IP_RESTRICTION_LIST::sm_hTimer = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003df4  mov     [rsp-8+arg_0], rbx
0x180003df9  push    rbp
0x180003dfa  lea     rbp, [rsp-57h]
0x180003dff  sub     rsp, 0D0h
0x180003e06  mov     rax, cs:__security_cookie
0x180003e0d  xor     rax, rsp
0x180003e10  mov     [rbp+57h+var_10], rax
0x180003e14  xorps   xmm0, xmm0
0x180003e17  lea     rcx, [rbp+57h+var_70]; void *
0x180003e1b  xor     edx, edx; Val
0x180003e1d  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180003e21  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180003e25  lea     r8d, [rdx+54h]; Size
0x180003e29  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180003e2d  call    memset_0
0x180003e32  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180003e36  call    cs:__imp_GetSystemInfo
0x180003e3c  mov     eax, [rbp+57h+var_6C]
0x180003e3f  lea     rdx, [rbp+57h+var_70]
0x180003e43  test    eax, eax
0x180003e45  mov     [rbp+57h+var_64], 927C0h
0x180003e4d  mov     ecx, 100h
0x180003e52  mov     ebx, 1
0x180003e57  cmovz   eax, ecx
0x180003e5a  mov     [rbp+57h+var_70], ebx
0x180003e5d  mov     [rbp+57h+var_58], eax
0x180003e60  mov     eax, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x180003e63  lea     ecx, [rbx+1]
0x180003e66  cmp     eax, ecx
0x180003e68  cmovb   eax, ecx
0x180003e6b  lea     rcx, ?sm_pThreadPool@IP_RESTRICTION_LIST@@0PEAVTHREAD_POOL@@EA; THREAD_POOL * IP_RESTRICTION_LIST::sm_pThreadPool
0x180003e72  mov     [rbp+57h+var_68], eax
0x180003e75  call    cs:__imp_?CreateThreadPool@THREAD_POOL@@SAHPEAPEAV1@PEAUTHREAD_POOL_CONFIG@@@Z; THREAD_POOL::CreateThreadPool(THREAD_POOL * *,THREAD_POOL_CONFIG *)
0x180003e7b  test    eax, eax
0x180003e7d  jnz     short loc_180003EF5
0x180003e7f  test    cs:g_dwDebugFlags, 3
0x180003e86  jz      short loc_180003EB5
0x180003e88  mov     rcx, cs:g_pDebug
0x180003e8f  lea     rax, aFailedToCreate; "Failed to create ThreadPool for DNS loo"...
0x180003e96  lea     r9, aIpRestrictionL; "IP_RESTRICTION_LIST::LazyInitialize"
0x180003e9d  mov     [rsp+0D0h+var_B0], rax
0x180003ea2  mov     r8d, 671h
0x180003ea8  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003eaf  call    cs:__imp_PuDbgPrint
0x180003eb5  cmp     cs:?sm_fInitCritSec@IP_RESTRICTION_LIST@@0HA, 0; int IP_RESTRICTION_LIST::sm_fInitCritSec
0x180003ebc  mov     ebx, 80004005h
0x180003ec1  jz      short loc_180003ED0
0x180003ec3  lea     rcx, ?sm_csLazyInitialize@IP_RESTRICTION_LIST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003eca  call    cs:__imp_DeleteCriticalSection
0x180003ed0  mov     rdx, cs:?sm_hTimer@IP_RESTRICTION_LIST@@0PEAXEA; Timer
0x180003ed7  test    rdx, rdx
0x180003eda  jz      short loc_180003F02
0x180003edc  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003ee0  xor     ecx, ecx; TimerQueue
0x180003ee2  call    cs:__imp_DeleteTimerQueueTimer
0x180003ee8  mov     cs:?sm_hTimer@IP_RESTRICTION_LIST@@0PEAXEA, 0; void * IP_RESTRICTION_LIST::sm_hTimer
0x180003ef3  jmp     short loc_180003F02
0x180003ef5  lock or [rsp+0D0h+var_D0], 0
0x180003efa  mov     cs:?sm_fLazyInitializeComplete@IP_RESTRICTION_LIST@@0HA, ebx; int IP_RESTRICTION_LIST::sm_fLazyInitializeComplete
0x180003f00  xor     ebx, ebx
0x180003f02  mov     eax, ebx
0x180003f04  mov     rcx, [rbp+57h+var_10]
0x180003f08  xor     rcx, rsp; StackCookie
0x180003f0b  call    __security_check_cookie
0x180003f10  mov     rbx, [rsp+0D0h+arg_0]
0x180003f18  add     rsp, 0D0h
0x180003f1f  pop     rbp
0x180003f20  retn
```
