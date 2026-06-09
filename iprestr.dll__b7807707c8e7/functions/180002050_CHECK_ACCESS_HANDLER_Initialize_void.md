# CHECK_ACCESS_HANDLER::Initialize(void)

- ea: `0x180002050`
- end: `0x180002100`
- name: `?Initialize@CHECK_ACCESS_HANDLER@@SAJXZ`
- size: `176`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a40`

## callees

- `0x180002050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020a1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000205f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000205f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002097`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002097`
- `iisutil!PuDbgPrint` at `0x1800020ee`
- `iisutil!PuDbgPrint` at `0x1800020ee`

## string_xrefs

- `0x1800020d5`: `CHECK_ACCESS_HANDLER::Initialize`
- `0x1800020e7`: `servercommon\inetsrv\iis\iisrearc\iis70\iprestriction\ip_restriction_handler.cxx`

## pseudocode

```c
__int64 CHECK_ACCESS_HANDLER::Initialize(void)
{
  signed int LastError; // eax
  signed int v1; // ebx

  IP_RESTRICTION_LIST::sm_fInitCritSec = InitializeCriticalSectionAndSpinCount(
                                           &IP_RESTRICTION_LIST::sm_csLazyInitialize,
                                           0);
  if ( IP_RESTRICTION_LIST::sm_fInitCritSec
    && CreateTimerQueueTimer(
         &IP_RESTRICTION_LIST::sm_hTimer,
         0,
         IP_RESTRICTION_LIST::TimerCallback,
         0,
         0x23C34600u,
         0x23C34600u,
         0x10u) )
  {
    return 0;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
    return 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\iprestriction\\ip_restriction_handler.cxx",
      249,
      "CHECK_ACCESS_HANDLER::Initialize",
      "Error initializing IP_RESTRICTION_LIST.  hr = 0x%x\n",
      v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002050  push    rbx
0x180002052  sub     rsp, 40h
0x180002056  xor     edx, edx; dwSpinCount
0x180002058  lea     rcx, ?sm_csLazyInitialize@IP_RESTRICTION_LIST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000205f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002065  mov     cs:?sm_fInitCritSec@IP_RESTRICTION_LIST@@0HA, eax; int IP_RESTRICTION_LIST::sm_fInitCritSec
0x18000206b  test    eax, eax
0x18000206d  jz      short loc_1800020A1
0x18000206f  mov     eax, 23C34600h
0x180002074  mov     [rsp+48h+Flags], 10h; Flags
0x18000207c  mov     [rsp+48h+Period], eax; Period
0x180002080  lea     r8, ?TimerCallback@IP_RESTRICTION_LIST@@SAXPEAXE@Z; Callback
0x180002087  xor     r9d, r9d; Parameter
0x18000208a  mov     [rsp+48h+DueTime], eax; DueTime
0x18000208e  xor     edx, edx; TimerQueue
0x180002090  lea     rcx, ?sm_hTimer@IP_RESTRICTION_LIST@@0PEAXEA; phNewTimer
0x180002097  call    cs:__imp_CreateTimerQueueTimer
0x18000209d  test    eax, eax
0x18000209f  jnz     short loc_1800020F8
0x1800020a1  call    cs:__imp_GetLastError
0x1800020a7  mov     ebx, eax
0x1800020a9  test    eax, eax
0x1800020ab  jle     short loc_1800020B6
0x1800020ad  movzx   ebx, ax
0x1800020b0  or      ebx, 80070000h
0x1800020b6  test    ebx, ebx
0x1800020b8  jns     short loc_1800020F8
0x1800020ba  test    cs:g_dwDebugFlags, 3
0x1800020c1  jz      short loc_1800020F4
0x1800020c3  mov     rcx, cs:g_pDebug
0x1800020ca  lea     rax, aErrorInitializ; "Error initializing IP_RESTRICTION_LIST."...
0x1800020d1  mov     [rsp+48h+Period], ebx
0x1800020d5  lea     r9, aCheckAccessHan; "CHECK_ACCESS_HANDLER::Initialize"
0x1800020dc  mov     r8d, 0F9h
0x1800020e2  mov     qword ptr [rsp+48h+DueTime], rax
0x1800020e7  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800020ee  call    cs:__imp_PuDbgPrint
0x1800020f4  mov     eax, ebx
0x1800020f6  jmp     short loc_1800020FA
0x1800020f8  xor     eax, eax
0x1800020fa  add     rsp, 40h
0x1800020fe  pop     rbx
0x1800020ff  retn
```
