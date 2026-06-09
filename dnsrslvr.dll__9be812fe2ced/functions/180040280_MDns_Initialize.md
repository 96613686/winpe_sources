# MDns_Initialize

- ea: `0x180040280`
- end: `0x1800403e8`
- name: `MDns_Initialize`
- size: `360`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800495c0`

## callees

- `0x180040280`
- `0x180052260`
- `0x1800527fc`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040367`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004031f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004031f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800402f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800402f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800402bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180040355`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800402bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180040355`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800402f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180040393`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800402f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180040393`

## pseudocode

```c
__int64 MDns_Initialize()
{
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD LastError; // eax
  DWORD v2; // ebx
  __int64 v3; // rdx
  DWORD v4; // eax
  struct _TP_WORK *v5; // rax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 44, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids);
  ThreadpoolWork = CreateThreadpoolWork(MDnsIndicateFirewallPortInUseCb, 0, 0);
  g_pOpenMDnsFirewallPortWork = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_14;
    v3 = 45;
    goto LABEL_13;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  g_randSeed = GetTickCount();
  v4 = MDnsProbeAnnounceTask::Init();
  v2 = v4;
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 46, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v4);
    goto LABEL_19;
  }
  g_hMDnsInitDoneEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hMDnsInitDoneEvent )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_14;
    v3 = 47;
    goto LABEL_13;
  }
  v5 = CreateThreadpoolWork(MDnsInitCb, 0, 0);
  g_pMDnsInitWork = v5;
  if ( v5 )
  {
    SubmitThreadpoolWork(v5);
    goto LABEL_20;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v3 = 48;
LABEL_13:
    WPP_SF_d(1035, v3, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LastError);
  }
LABEL_14:
  if ( v2 )
LABEL_19:
    MDns_Shutdown();
LABEL_20:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 49, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180040280  mov     [rsp+arg_0], rbx
0x180040285  mov     [rsp+arg_8], rbp
0x18004028a  push    rsi
0x18004028b  sub     rsp, 20h
0x18004028f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040296  lea     rbp, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x18004029d  mov     esi, 40Bh
0x1800402a2  jz      short loc_1800402B3
0x1800402a4  mov     edx, 2Ch ; ','
0x1800402a9  mov     ecx, esi
0x1800402ab  mov     r8, rbp
0x1800402ae  call    WPP_SF_
0x1800402b3  xor     r8d, r8d; pcbe
0x1800402b6  lea     rcx, MDnsIndicateFirewallPortInUseCb; pfnwk
0x1800402bd  xor     edx, edx; pv
0x1800402bf  call    cs:__imp_CreateThreadpoolWork
0x1800402c5  mov     cs:?g_pOpenMDnsFirewallPortWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_pOpenMDnsFirewallPortWork
0x1800402cc  test    rax, rax
0x1800402cf  jnz     short loc_1800402F0
0x1800402d1  call    cs:__imp_GetLastError
0x1800402d7  mov     ebx, eax
0x1800402d9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800402e0  jz      loc_18004038A
0x1800402e6  mov     edx, 2Dh ; '-'
0x1800402eb  jmp     loc_18004037D
0x1800402f0  mov     rcx, rax; pwk
0x1800402f3  call    cs:__imp_SubmitThreadpoolWork
0x1800402f9  call    cs:__imp_GetTickCount
0x1800402ff  mov     cs:?g_randSeed@@3KA, eax; ulong g_randSeed
0x180040305  call    ?Init@MDnsProbeAnnounceTask@@SAKXZ; MDnsProbeAnnounceTask::Init(void)
0x18004030a  mov     ebx, eax
0x18004030c  test    eax, eax
0x18004030e  jnz     loc_18004039B
0x180040314  xor     r9d, r9d; lpName
0x180040317  lea     edx, [rax+1]; bManualReset
0x18004031a  xor     r8d, r8d; bInitialState
0x18004031d  xor     ecx, ecx; lpEventAttributes
0x18004031f  call    cs:__imp_CreateEventW
0x180040325  mov     cs:?g_hMDnsInitDoneEvent@@3PEAXEA, rax; void * g_hMDnsInitDoneEvent
0x18004032c  test    rax, rax
0x18004032f  jnz     short loc_180040349
0x180040331  call    cs:__imp_GetLastError
0x180040337  mov     ebx, eax
0x180040339  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040340  jz      short loc_18004038A
0x180040342  mov     edx, 2Fh ; '/'
0x180040347  jmp     short loc_18004037D
0x180040349  xor     r8d, r8d; pcbe
0x18004034c  lea     rcx, MDnsInitCb; pfnwk
0x180040353  xor     edx, edx; pv
0x180040355  call    cs:__imp_CreateThreadpoolWork
0x18004035b  mov     cs:?g_pMDnsInitWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_pMDnsInitWork
0x180040362  test    rax, rax
0x180040365  jnz     short loc_180040390
0x180040367  call    cs:__imp_GetLastError
0x18004036d  mov     ebx, eax
0x18004036f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040376  jz      short loc_18004038A
0x180040378  mov     edx, 30h ; '0'
0x18004037d  mov     r9d, eax
0x180040380  mov     r8, rbp
0x180040383  mov     ecx, esi
0x180040385  call    WPP_SF_d
0x18004038a  test    ebx, ebx
0x18004038c  jnz     short loc_1800403B6
0x18004038e  jmp     short loc_1800403BB
0x180040390  mov     rcx, rax; pwk
0x180040393  call    cs:__imp_SubmitThreadpoolWork
0x180040399  jmp     short loc_1800403BB
0x18004039b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800403a2  jz      short loc_1800403B6
0x1800403a4  mov     edx, 2Eh ; '.'
0x1800403a9  mov     ecx, esi
0x1800403ab  mov     r9d, eax
0x1800403ae  mov     r8, rbp
0x1800403b1  call    WPP_SF_d
0x1800403b6  call    MDns_Shutdown
0x1800403bb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800403c2  jz      short loc_1800403D6
0x1800403c4  mov     edx, 31h ; '1'
0x1800403c9  mov     ecx, esi
0x1800403cb  mov     r9d, ebx
0x1800403ce  mov     r8, rbp
0x1800403d1  call    WPP_SF_d
0x1800403d6  mov     rbp, [rsp+28h+arg_8]
0x1800403db  mov     eax, ebx
0x1800403dd  mov     rbx, [rsp+28h+arg_0]
0x1800403e2  add     rsp, 20h
0x1800403e6  pop     rsi
0x1800403e7  retn
```
