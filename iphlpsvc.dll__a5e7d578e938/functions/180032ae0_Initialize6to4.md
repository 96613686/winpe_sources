# Initialize6to4

- ea: `0x180032ae0`
- end: `0x180032e5e`
- name: `Initialize6to4`
- size: `894`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004ca0`
- `0x180004f60`
- `0x180009010`
- `0x18000cea0`
- `0x18000d7c0`
- `0x1800140a8`
- `0x180032ae0`
- `0x180033704`
- `0x1800338f4`
- `0x18003e110`
- `0x180040fe0`
- `0x180041350`
- `0x180042f2c`
- `0x180076dcc`
- `0x180076e24`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x180032be9`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x180032be9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032d70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032d70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032e05`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032e05`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032bff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032c51`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032bff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cd5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180032cbd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180032cbd`

## string_xrefs

- `0x180032d09`: `Process6to4ConfigurationChange`
- `0x180032cff`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032e43`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032b70`: `6to4.ipv6.microsoft.com.`
- `0x180032d1f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180032afd`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032d80`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`

## pseudocode

```c
void __fastcall Initialize6to4(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD LastError; // edi
  const wchar_t *v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  HANDLE v16; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax
  int v18; // eax
  HANDLE v19; // rbx
  __int64 v20; // [rsp+28h] [rbp-50h]
  BOOL v21; // [rsp+30h] [rbp-48h]

  v2 = 0;
  if ( !(unsigned int)GetAndTraceLock(
                        "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                        "Initialize6to4",
                        498,
                        g_6to4Lock) )
  {
    LastError = 1062;
LABEL_25:
    SetStopServiceEvent(LastError, v3, v4, v5);
    if ( dword_1800C975C )
    {
      StopWorkQueue(&CriticalSection);
      dword_1800C975C = 0;
    }
    if ( v2 )
      UninitializeWorkQueue(&CriticalSection);
    goto LABEL_31;
  }
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: Initialize6to4");
  InitializeGlobalState(&g_ProtocolState6to4);
  qword_1800C9748 = (__int64)off_1800C80A0;
  v7 = L"6to4.ipv6.microsoft.com.";
  v8 = &pszDest;
  xmmword_1800C9770 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  dword_1800C9784 = 1440;
  v9 = 2147483646;
  dword_1800C9780 = 2;
  v10 = 1025;
  do
  {
    if ( !v9 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  qword_1800C9F90 = 0;
  InitializeSListHead(&ListHead);
  qword_1800C9F98 = CreateEventW(0, 0, 0, 0);
  if ( qword_1800C9F98
    && (dword_1800C9758 = (unsigned __int8)IsOSServerSku(v13, v12, v14, v15) != 0,
        dword_1800C9760 = 0,
        (qword_1800C9768 = CreateEventW(0, 1, 0, 0)) != 0)
    && (unsigned int)InitializeWorkQueue(&CriticalSection) )
  {
    v2 = 1;
    if ( (unsigned int)StartWorkQueue(&CriticalSection) )
    {
      dword_1800C975C = 1;
      _InterlockedExchange(&dword_1800C9FA8, 1);
      v16 = qword_1800C9F98;
      ThreadpoolWait = CreateThreadpoolWait(OnResolutionTimerCancelled, 0, &CallbackEnvironment);
      qword_1800C9FA0 = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        TpclSetThreadpoolWait(ThreadpoolWait, v16);
        qword_1800C9FC0 = 0;
        dword_1800C9754 = 1;
        LastError = 0;
        EventWrite0(
          0x40000,
          L"ReferenceService: ++%u (%hs) @ %ls:%u",
          ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
          "Process6to4ConfigurationChange",
          L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
          597);
        while ( 1 )
        {
          v18 = g_Reference;
          if ( (g_Reference & 1) != 0 )
            break;
          if ( v18 == _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) )
          {
            Process6to4ConfigurationChange(0, 0);
            break;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        _InterlockedExchange(&dword_1800C9FA8, 0);
      }
    }
    else
    {
      LastError = 31;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  v19 = g_6to4Lock;
  v21 = ReleaseMutex(g_6to4Lock);
  LODWORD(v20) = 604;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v19,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "Initialize6to4",
    v20,
    v21);
  if ( LastError )
    goto LABEL_25;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 4) != 0 )
    McTemplateU0q_EventWriteTransfer(MS_IPHLPSVC_ETW_PROVIDER_ID_Context, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED, 0);
LABEL_31:
  SetEvent(g_6to4StartCompleteEvent);
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Leaving: Initialize6to4");
  DereferenceServiceEx("Initialize6to4", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c", 635);
}

```

## disassembly

```asm
0x180032ae0  push    rbx
0x180032ae2  push    rbp
0x180032ae3  push    rsi
0x180032ae4  push    rdi
0x180032ae5  push    r13
0x180032ae7  push    r14
0x180032ae9  sub     rsp, 48h
0x180032aed  mov     r9, cs:g_6to4Lock
0x180032af4  lea     r13, aInitialize6to4; "Initialize6to4"
0x180032afb  xor     ebp, ebp
0x180032afd  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032b04  mov     rdx, r13
0x180032b07  mov     r8d, 1F2h
0x180032b0d  mov     esi, ebp
0x180032b0f  call    GetAndTraceLock
0x180032b14  test    eax, eax
0x180032b16  jnz     short loc_180032B22
0x180032b18  mov     edi, 426h
0x180032b1d  jmp     loc_180032DAC
0x180032b22  cmp     cs:IpHlpSvcEtwEnabled, bpl
0x180032b29  jz      short loc_180032B4E
0x180032b2b  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, bpl
0x180032b32  jge     short loc_180032B4E
0x180032b34  lea     r8, aEnteredInitial_1; "Entered: Initialize6to4"
0x180032b3b  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032b42  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032b49  call    McTemplateU0z_EventWriteTransfer
0x180032b4e  lea     rcx, g_ProtocolState6to4
0x180032b55  call    InitializeGlobalState
0x180032b5a  movdqa  xmm0, cs:__xmm@00000001000000010000000300000003
0x180032b62  lea     rax, off_1800C80A0
0x180032b69  mov     cs:qword_1800C9748, rax
0x180032b70  lea     r8, a6to4Ipv6Micros; "6to4.ipv6.microsoft.com."
0x180032b77  lea     rax, pszDest
0x180032b7e  movdqa  cs:xmmword_1800C9770, xmm0
0x180032b86  mov     cs:dword_1800C9784, 5A0h
0x180032b90  mov     ecx, 7FFFFFFEh
0x180032b95  mov     cs:dword_1800C9780, 2
0x180032b9f  mov     edx, 401h
0x180032ba4  mov     r14d, 1
0x180032baa  test    rcx, rcx
0x180032bad  jz      short loc_180032BCD
0x180032baf  movzx   r9d, word ptr [r8]
0x180032bb3  test    r9w, r9w
0x180032bb7  jz      short loc_180032BCD
0x180032bb9  mov     [rax], r9w
0x180032bbd  add     r8, 2
0x180032bc1  add     rax, 2
0x180032bc5  sub     rcx, r14
0x180032bc8  sub     rdx, r14
0x180032bcb  jnz     short loc_180032BAA
0x180032bcd  test    rdx, rdx
0x180032bd0  lea     rcx, [rax-2]
0x180032bd4  cmovnz  rcx, rax
0x180032bd8  mov     [rcx], bp
0x180032bdb  lea     rcx, ListHead; ListHead
0x180032be2  mov     cs:qword_1800C9F90, rbp
0x180032be9  call    cs:__imp_InitializeSListHead
0x180032bf0  nop     dword ptr [rax+rax+00h]
0x180032bf5  xor     r9d, r9d; lpName
0x180032bf8  xor     r8d, r8d; bInitialState
0x180032bfb  xor     edx, edx; bManualReset
0x180032bfd  xor     ecx, ecx; lpEventAttributes
0x180032bff  call    cs:__imp_CreateEventW
0x180032c06  nop     dword ptr [rax+rax+00h]
0x180032c0b  mov     cs:qword_1800C9F98, rax
0x180032c12  test    rax, rax
0x180032c15  jnz     short loc_180032C2A
0x180032c17  call    cs:__imp_GetLastError
0x180032c1e  nop     dword ptr [rax+rax+00h]
0x180032c23  mov     edi, eax
0x180032c25  jmp     loc_180032D66
0x180032c2a  mov     cs:dword_1800C9758, ebp
0x180032c30  call    IsOSServerSku
0x180032c35  test    al, al
0x180032c37  jz      short loc_180032C40
0x180032c39  mov     cs:dword_1800C9758, r14d
0x180032c40  xor     r9d, r9d; lpName
0x180032c43  mov     cs:dword_1800C9760, ebp
0x180032c49  xor     r8d, r8d; bInitialState
0x180032c4c  mov     edx, r14d; bManualReset
0x180032c4f  xor     ecx, ecx; lpEventAttributes
0x180032c51  call    cs:__imp_CreateEventW
0x180032c58  nop     dword ptr [rax+rax+00h]
0x180032c5d  mov     cs:qword_1800C9768, rax
0x180032c64  test    rax, rax
0x180032c67  jz      short loc_180032C17
0x180032c69  xor     edx, edx
0x180032c6b  lea     rcx, CriticalSection; lpCriticalSection
0x180032c72  call    InitializeWorkQueue
0x180032c77  test    eax, eax
0x180032c79  jz      short loc_180032C17
0x180032c7b  lea     rcx, CriticalSection
0x180032c82  mov     esi, r14d
0x180032c85  call    StartWorkQueue
0x180032c8a  test    eax, eax
0x180032c8c  jnz     short loc_180032C96
0x180032c8e  lea     edi, [rax+1Fh]
0x180032c91  jmp     loc_180032D66
0x180032c96  mov     eax, r14d
0x180032c99  mov     cs:dword_1800C975C, r14d
0x180032ca0  xchg    eax, cs:dword_1800C9FA8
0x180032ca6  mov     rbx, cs:qword_1800C9F98
0x180032cad  lea     r8, CallbackEnvironment; pcbe
0x180032cb4  xor     edx, edx; pv
0x180032cb6  lea     rcx, OnResolutionTimerCancelled; pfnwa
0x180032cbd  call    cs:__imp_CreateThreadpoolWait
0x180032cc4  nop     dword ptr [rax+rax+00h]
0x180032cc9  mov     cs:qword_1800C9FA0, rax
0x180032cd0  test    rax, rax
0x180032cd3  jnz     short loc_180032CED
0x180032cd5  call    cs:__imp_GetLastError
0x180032cdc  nop     dword ptr [rax+rax+00h]
0x180032ce1  mov     edi, eax
0x180032ce3  mov     eax, ebp
0x180032ce5  xchg    eax, cs:dword_1800C9FA8
0x180032ceb  jmp     short loc_180032D66
0x180032ced  mov     rdx, rbx
0x180032cf0  mov     rcx, rax
0x180032cf3  call    TpclSetThreadpoolWait
0x180032cf8  mov     r8d, cs:g_Reference
0x180032cff  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032d06  shr     r8d, 1
0x180032d09  lea     r9, aProcess6to4con; "Process6to4ConfigurationChange"
0x180032d10  and     r8d, 3FFFFFFFh
0x180032d17  mov     dword ptr [rsp+78h+var_50], 255h
0x180032d1f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180032d26  mov     cs:qword_1800C9FC0, rbp
0x180032d2d  mov     ecx, 40000h
0x180032d32  mov     cs:dword_1800C9754, r14d
0x180032d39  mov     edi, ebp
0x180032d3b  mov     [rsp+78h+var_58], rax
0x180032d40  call    EventWrite0
0x180032d45  mov     eax, cs:g_Reference
0x180032d4b  test    r14b, al
0x180032d4e  jnz     short loc_180032D66
0x180032d50  lea     ecx, [rax+2]
0x180032d53  lock cmpxchg cs:g_Reference, ecx
0x180032d5b  jnz     short loc_180032D45
0x180032d5d  xor     edx, edx; Context
0x180032d5f  xor     ecx, ecx; Instance
0x180032d61  call    Process6to4ConfigurationChange
0x180032d66  mov     rbx, cs:g_6to4Lock
0x180032d6d  mov     rcx, rbx; hMutex
0x180032d70  call    cs:__imp_ReleaseMutex
0x180032d77  nop     dword ptr [rax+rax+00h]
0x180032d7c  mov     [rsp+78h+var_48], eax
0x180032d80  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032d87  mov     dword ptr [rsp+78h+var_50], 25Ch
0x180032d8f  mov     r8, rbx
0x180032d92  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180032d99  mov     [rsp+78h+var_58], r13
0x180032d9e  mov     ecx, 800000h
0x180032da3  call    EventWrite0
0x180032da8  test    edi, edi
0x180032daa  jz      short loc_180032DDF
0x180032dac  mov     ecx, edi
0x180032dae  call    SetStopServiceEvent
0x180032db3  cmp     cs:dword_1800C975C, ebp
0x180032db9  jz      short loc_180032DCD
0x180032dbb  lea     rcx, CriticalSection
0x180032dc2  call    StopWorkQueue
0x180032dc7  mov     cs:dword_1800C975C, ebp
0x180032dcd  test    esi, esi
0x180032dcf  jz      short loc_180032DFE
0x180032dd1  lea     rcx, CriticalSection
0x180032dd8  call    UninitializeWorkQueue
0x180032ddd  jmp     short loc_180032DFE
0x180032ddf  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180032de6  jz      short loc_180032DFE
0x180032de8  xor     r8d, r8d
0x180032deb  lea     rdx, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED
0x180032df2  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032df9  call    McTemplateU0q_EventWriteTransfer
0x180032dfe  mov     rcx, cs:g_6to4StartCompleteEvent; hEvent
0x180032e05  call    cs:__imp_SetEvent
0x180032e0c  nop     dword ptr [rax+rax+00h]
0x180032e11  cmp     cs:IpHlpSvcEtwEnabled, bpl
0x180032e18  jz      short loc_180032E3D
0x180032e1a  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, bpl
0x180032e21  jge     short loc_180032E3D
0x180032e23  lea     r8, aLeavingInitial; "Leaving: Initialize6to4"
0x180032e2a  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032e31  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032e38  call    McTemplateU0z_EventWriteTransfer
0x180032e3d  mov     r8d, 27Bh
0x180032e43  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032e4a  mov     rcx, r13
0x180032e4d  add     rsp, 48h
0x180032e51  pop     r14
0x180032e53  pop     r13
0x180032e55  pop     rdi
0x180032e56  pop     rsi
0x180032e57  pop     rbp
0x180032e58  pop     rbx
0x180032e59  jmp     DereferenceServiceEx
```
