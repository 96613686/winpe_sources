# CASPPerfManager::Init(int)

- ea: `0x18001e7b0`
- end: `0x18001ea2c`
- name: `?Init@CASPPerfManager@@QEAAJH@Z`
- size: `636`
- prototype: `__int64 __fastcall(CASPPerfManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ef10`

## callees

- `0x18001db14`
- `0x18001e7b0`
- `0x18001ebcc`
- `0x18001ecd0`
- `0x180021a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e9b1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e9b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001e907`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001e907`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001e7ec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18001e7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e98f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e81a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e81a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e922`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001e985`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001e985`
- `iisutil!PuDbgPrint` at `0x18001e87c`
- `iisutil!PuDbgPrint` at `0x18001ea07`
- `iisutil!PuDbgPrint` at `0x18001e87c`
- `iisutil!PuDbgPrint` at `0x18001ea07`

## string_xrefs

- `0x18001e86e`: `servercommon\inetsrv\iis\inc\asppdef.h`
- `0x18001e9f9`: `servercommon\inetsrv\iis\inc\asppdef.h`

## pseudocode

```c
__int64 __fastcall CASPPerfManager::Init(CASPPerfManager *this)
{
  _DWORD *v2; // rsi
  signed int inited; // ebx
  HANDLE MutexA; // rax
  signed int EventForSharedMemoryShutdown; // eax
  bool v6; // cc
  signed int LastError; // eax

  v2 = (_DWORD *)((char *)this + 10520);
  *((_DWORD *)this + 2630) &= ~2u;
  inited = CSharedMemBlock::InitSD(this);
  if ( inited < 0 )
    goto LABEL_9;
  MutexA = CreateMutexA((LPSECURITY_ATTRIBUTES)((char *)this + 16), 0, "Global\\ASP_PERFMON_MUTEX");
  *((_QWORD *)this + 6) = MutexA;
  if ( MutexA )
  {
    if ( GetLastError() == 183 )
    {
      GetLastError();
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    GetLastError();
  }
  if ( !*((_QWORD *)this + 6) )
  {
    inited = -2147467259;
LABEL_8:
    CPerfMainBlock::UnInit(this);
    goto LABEL_9;
  }
  inited = CSharedMemBlock::InitMap(this, "Global\\ASP_PERFMON_MAIN_BLOCK", 0x28ACu, 1);
  if ( inited >= 0 )
  {
    *((_QWORD *)this + 1313) = *((_QWORD *)this + 1);
    EventForSharedMemoryShutdown = CPerfMainBlock::CreateEventForSharedMemoryShutdown(this);
    inited = EventForSharedMemoryShutdown;
    v6 = EventForSharedMemoryShutdown <= 0;
    if ( EventForSharedMemoryShutdown )
      goto LABEL_14;
    *(_DWORD *)(*((_QWORD *)this + 1313) + 8360LL) = GetCurrentProcessId();
    inited = CSharedMemBlock::InitSD(this);
    if ( inited >= 0 )
    {
      *((_QWORD *)this + 7) = CreateEventA(
                                (LPSECURITY_ATTRIBUTES)((char *)this + 16),
                                0,
                                0,
                                "Global\\ASP_PERFMON_ADD_EVENT");
      if ( GetLastError() == 183 )
      {
        CloseHandle(*((HANDLE *)this + 7));
        *((_QWORD *)this + 7) = 0;
        inited = -2147024713;
      }
      else
      {
        if ( !*((_QWORD *)this + 7) )
        {
          EventForSharedMemoryShutdown = GetLastError();
          inited = EventForSharedMemoryShutdown;
          v6 = EventForSharedMemoryShutdown <= 0;
LABEL_14:
          if ( !v6 )
            inited = (unsigned __int16)EventForSharedMemoryShutdown | 0x80070000;
          goto LABEL_22;
        }
        inited = 0;
      }
    }
  }
LABEL_22:
  if ( inited < 0 )
    goto LABEL_8;
  *((_DWORD *)this + 10) |= 1u;
LABEL_9:
  if ( inited >= 0 )
  {
    if ( !RegisterWaitForSingleObject(
            (PHANDLE)this + 1314,
            *((HANDLE *)this + 7),
            CASPPerfManager::ChangeEventWaitCallback,
            this,
            0xFFFFFFFF,
            1u) )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
    }
    if ( inited < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\inc\\asppdef.h",
          1652,
          "CASPPerfManager::Init",
          "Initializing CASPPerfManager FAILED (%x)\n",
          inited);
      CPerfMainBlock::UnInit(this);
    }
    else
    {
      inited = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 35104));
      *v2 |= 1u;
      *v2 |= 4u;
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\inc\\asppdef.h",
      1624,
      "CASPPerfManager::Init",
      "Initializing CASPPerfManager FAILED (%x)\n",
      inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001e7b0  mov     [rsp+arg_8], rbx
0x18001e7b5  mov     [rsp+arg_0], rcx
0x18001e7ba  push    rsi
0x18001e7bb  push    rdi
0x18001e7bc  push    r14
0x18001e7be  sub     rsp, 30h
0x18001e7c2  mov     rdi, rcx
0x18001e7c5  lea     rsi, [rcx+2918h]
0x18001e7cc  mov     [rsp+48h+arg_10], rsi
0x18001e7d1  and     dword ptr [rsi], 0FFFFFFFDh
0x18001e7d4  call    ?InitSD@CSharedMemBlock@@QEAAJXZ; CSharedMemBlock::InitSD(void)
0x18001e7d9  mov     ebx, eax
0x18001e7db  test    eax, eax
0x18001e7dd  js      short loc_18001E83C
0x18001e7df  lea     r8, Name; "Global\\ASP_PERFMON_MUTEX"
0x18001e7e6  xor     edx, edx; bInitialOwner
0x18001e7e8  lea     rcx, [rdi+10h]; lpMutexAttributes
0x18001e7ec  call    cs:__imp_CreateMutexA
0x18001e7f2  mov     [rdi+30h], rax
0x18001e7f6  test    rax, rax
0x18001e7f9  jnz     short loc_18001E803
0x18001e7fb  call    cs:__imp_GetLastError
0x18001e801  jmp     short loc_18001E828
0x18001e803  call    cs:__imp_GetLastError
0x18001e809  cmp     eax, 0B7h
0x18001e80e  jnz     short loc_18001E828
0x18001e810  call    cs:__imp_GetLastError
0x18001e816  mov     rcx, [rdi+30h]; hObject
0x18001e81a  call    cs:__imp_CloseHandle
0x18001e820  mov     qword ptr [rdi+30h], 0
0x18001e828  cmp     qword ptr [rdi+30h], 0
0x18001e82d  jnz     short loc_18001E887
0x18001e82f  mov     ebx, 80004005h
0x18001e834  mov     rcx, rdi; this
0x18001e837  call    ?UnInit@CPerfMainBlock@@QEAAJXZ; CPerfMainBlock::UnInit(void)
0x18001e83c  test    ebx, ebx
0x18001e83e  jns     loc_18001E960
0x18001e844  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e84b  jz      loc_18001EA1C
0x18001e851  mov     [rsp+48h+dwFlags], ebx
0x18001e855  lea     rax, aInitializingCa; "Initializing CASPPerfManager FAILED (%x"...
0x18001e85c  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x18001e861  lea     r9, aCaspperfmanage; "CASPPerfManager::Init"
0x18001e868  mov     r8d, 658h
0x18001e86e  lea     rdx, aServercommonIn_50; "servercommon\\inetsrv\\iis\\inc\\asppde"...
0x18001e875  mov     rcx, cs:g_pDebug
0x18001e87c  call    cs:__imp_PuDbgPrint
0x18001e882  jmp     loc_18001EA1C
0x18001e887  mov     r9d, 1; int
0x18001e88d  mov     r8d, 28ACh; unsigned int
0x18001e893  lea     rdx, aGlobalAspPerfm_2; "Global\\ASP_PERFMON_MAIN_BLOCK"
0x18001e89a  mov     rcx, rdi; this
0x18001e89d  call    ?InitMap@CSharedMemBlock@@QEAAJPEBDKH@Z; CSharedMemBlock::InitMap(char const *,ulong,int)
0x18001e8a2  mov     ebx, eax
0x18001e8a4  test    eax, eax
0x18001e8a6  js      loc_18001E94F
0x18001e8ac  mov     rax, [rdi+8]
0x18001e8b0  mov     [rdi+2908h], rax
0x18001e8b7  mov     rcx, rdi; this
0x18001e8ba  call    ?CreateEventForSharedMemoryShutdown@CPerfMainBlock@@QEAAJXZ; CPerfMainBlock::CreateEventForSharedMemoryShutdown(void)
0x18001e8bf  mov     ebx, eax
0x18001e8c1  test    eax, eax
0x18001e8c3  jz      short loc_18001E8D6
0x18001e8c5  jle     loc_18001E94F
0x18001e8cb  movzx   ebx, ax
0x18001e8ce  or      ebx, 80070000h
0x18001e8d4  jmp     short loc_18001E94F
0x18001e8d6  call    cs:__imp_GetCurrentProcessId
0x18001e8dc  mov     rcx, [rdi+2908h]
0x18001e8e3  mov     [rcx+20A8h], eax
0x18001e8e9  mov     rcx, rdi; this
0x18001e8ec  call    ?InitSD@CSharedMemBlock@@QEAAJXZ; CSharedMemBlock::InitSD(void)
0x18001e8f1  mov     ebx, eax
0x18001e8f3  test    eax, eax
0x18001e8f5  js      short loc_18001E94F
0x18001e8f7  lea     r9, aGlobalAspPerfm; "Global\\ASP_PERFMON_ADD_EVENT"
0x18001e8fe  xor     r8d, r8d; bInitialState
0x18001e901  xor     edx, edx; bManualReset
0x18001e903  lea     rcx, [rdi+10h]; lpEventAttributes
0x18001e907  call    cs:__imp_CreateEventA
0x18001e90d  mov     [rdi+38h], rax
0x18001e911  call    cs:__imp_GetLastError
0x18001e917  cmp     eax, 0B7h
0x18001e91c  jnz     short loc_18001E937
0x18001e91e  mov     rcx, [rdi+38h]; hObject
0x18001e922  call    cs:__imp_CloseHandle
0x18001e928  mov     qword ptr [rdi+38h], 0
0x18001e930  mov     ebx, 800700B7h
0x18001e935  jmp     short loc_18001E94F
0x18001e937  cmp     qword ptr [rdi+38h], 0
0x18001e93c  jnz     short loc_18001E94D
0x18001e93e  call    cs:__imp_GetLastError
0x18001e944  mov     ebx, eax
0x18001e946  test    eax, eax
0x18001e948  jmp     loc_18001E8C5
0x18001e94d  xor     ebx, ebx
0x18001e94f  test    ebx, ebx
0x18001e951  js      loc_18001E834
0x18001e957  or      dword ptr [rdi+28h], 1
0x18001e95b  jmp     loc_18001E83C
0x18001e960  lea     rcx, [rdi+2910h]; phNewWaitObject
0x18001e967  mov     [rsp+48h+dwFlags], 1; dwFlags
0x18001e96f  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18001e977  mov     r9, rdi; Context
0x18001e97a  lea     r8, ?ChangeEventWaitCallback@CASPPerfManager@@CAXPEAXE@Z; Callback
0x18001e981  mov     rdx, [rdi+38h]; hObject
0x18001e985  call    cs:__imp_RegisterWaitForSingleObject
0x18001e98b  test    eax, eax
0x18001e98d  jnz     short loc_18001E9A4
0x18001e98f  call    cs:__imp_GetLastError
0x18001e995  mov     ebx, eax
0x18001e997  test    eax, eax
0x18001e999  jle     short loc_18001E9A4
0x18001e99b  movzx   ebx, ax
0x18001e99e  or      ebx, 80070000h
0x18001e9a4  test    ebx, ebx
0x18001e9a6  js      short loc_18001E9D3
0x18001e9a8  xor     ebx, ebx
0x18001e9aa  lea     rcx, [rdi+8920h]; lpCriticalSection
0x18001e9b1  call    cs:__imp_InitializeCriticalSection
0x18001e9b7  jmp     short loc_18001E9C8
0x18001e9b9  mov     ebx, 8000FFFFh
0x18001e9be  mov     rdi, [rsp+48h+arg_0]
0x18001e9c3  mov     rsi, [rsp+48h+arg_10]
0x18001e9c8  test    ebx, ebx
0x18001e9ca  js      short loc_18001E9D3
0x18001e9cc  or      dword ptr [rsi], 1
0x18001e9cf  test    ebx, ebx
0x18001e9d1  jns     short loc_18001EA19
0x18001e9d3  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e9da  jz      short loc_18001EA0D
0x18001e9dc  mov     [rsp+48h+dwFlags], ebx
0x18001e9e0  lea     rax, aInitializingCa; "Initializing CASPPerfManager FAILED (%x"...
0x18001e9e7  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x18001e9ec  lea     r9, aCaspperfmanage; "CASPPerfManager::Init"
0x18001e9f3  mov     r8d, 674h
0x18001e9f9  lea     rdx, aServercommonIn_50; "servercommon\\inetsrv\\iis\\inc\\asppde"...
0x18001ea00  mov     rcx, cs:g_pDebug
0x18001ea07  call    cs:__imp_PuDbgPrint
0x18001ea0d  mov     rcx, rdi; this
0x18001ea10  call    ?UnInit@CPerfMainBlock@@QEAAJXZ; CPerfMainBlock::UnInit(void)
0x18001ea15  test    ebx, ebx
0x18001ea17  js      short loc_18001EA1C
0x18001ea19  or      dword ptr [rsi], 4
0x18001ea1c  mov     eax, ebx
0x18001ea1e  mov     rbx, [rsp+48h+arg_8]
0x18001ea23  add     rsp, 30h
0x18001ea27  pop     r14
0x18001ea29  pop     rdi
0x18001ea2a  pop     rsi
0x18001ea2b  retn
```
