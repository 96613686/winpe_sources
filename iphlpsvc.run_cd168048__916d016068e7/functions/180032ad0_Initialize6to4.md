# Initialize6to4

- ea: `0x180032ad0`
- end: `0x180032e4e`
- name: `Initialize6to4`
- size: `894`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004c90`
- `0x180004f50`
- `0x180009000`
- `0x18000ce90`
- `0x18000d7b0`
- `0x180014098`
- `0x180032ad0`
- `0x1800336f4`
- `0x1800338e4`
- `0x18003e154`
- `0x180041020`
- `0x180041390`
- `0x180042f6c`
- `0x180076dac`
- `0x180076e04`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x180032bd9`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x180032bd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032d60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032df5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032df5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032bef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032c41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032bef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cc5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180032cad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180032cad`

## string_xrefs

- `0x180032cf9`: `Process6to4ConfigurationChange`
- `0x180032cef`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032e33`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032b60`: `6to4.ipv6.microsoft.com.`
- `0x180032d0f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180032aed`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180032d70`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`

## pseudocode

```c
void __fastcall Initialize6to4(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  int v2; // esi
  DWORD LastError; // edi
  const wchar_t *v4; // r8
  wchar_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  HANDLE v13; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax
  int v15; // eax
  HANDLE v16; // rbx
  __int64 v17; // [rsp+28h] [rbp-50h]
  BOOL v18; // [rsp+30h] [rbp-48h]

  v2 = 0;
  if ( !(unsigned int)GetAndTraceLock(
                        "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                        "Initialize6to4",
                        498,
                        g_6to4Lock) )
  {
    LastError = 1062;
LABEL_25:
    SetStopServiceEvent(LastError);
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
  v4 = L"6to4.ipv6.microsoft.com.";
  v5 = &pszDest;
  xmmword_1800C9770 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  dword_1800C9784 = 1440;
  v6 = 2147483646;
  dword_1800C9780 = 2;
  v7 = 1025;
  do
  {
    if ( !v6 )
      break;
    if ( !*v4 )
      break;
    *v5++ = *v4++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v5 - 1;
  if ( v7 )
    v8 = v5;
  *v8 = 0;
  qword_1800C9F90 = 0;
  InitializeSListHead(&ListHead);
  qword_1800C9F98 = CreateEventW(0, 0, 0, 0);
  if ( qword_1800C9F98
    && (dword_1800C9758 = (unsigned __int8)IsOSServerSku(v10, v9, v11, v12) != 0,
        dword_1800C9760 = 0,
        (qword_1800C9768 = CreateEventW(0, 1, 0, 0)) != 0)
    && (unsigned int)InitializeWorkQueue(&CriticalSection) )
  {
    v2 = 1;
    if ( (unsigned int)StartWorkQueue(&CriticalSection) )
    {
      dword_1800C975C = 1;
      _InterlockedExchange(&dword_1800C9FA8, 1);
      v13 = qword_1800C9F98;
      ThreadpoolWait = CreateThreadpoolWait(OnResolutionTimerCancelled, 0, &CallbackEnvironment);
      qword_1800C9FA0 = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        TpclSetThreadpoolWait(ThreadpoolWait, v13);
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
          v15 = g_Reference;
          if ( (g_Reference & 1) != 0 )
            break;
          if ( v15 == _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) )
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
  v16 = g_6to4Lock;
  v18 = ReleaseMutex(g_6to4Lock);
  LODWORD(v17) = 604;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v16,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "Initialize6to4",
    v17,
    v18);
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
0x180032ad0  push    rbx
0x180032ad2  push    rbp
0x180032ad3  push    rsi
0x180032ad4  push    rdi
0x180032ad5  push    r13
0x180032ad7  push    r14
0x180032ad9  sub     rsp, 48h
0x180032add  mov     r9, cs:g_6to4Lock
0x180032ae4  lea     r13, aInitialize6to4; "Initialize6to4"
0x180032aeb  xor     ebp, ebp
0x180032aed  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032af4  mov     rdx, r13
0x180032af7  mov     r8d, 1F2h
0x180032afd  mov     esi, ebp
0x180032aff  call    GetAndTraceLock
0x180032b04  test    eax, eax
0x180032b06  jnz     short loc_180032B12
0x180032b08  mov     edi, 426h
0x180032b0d  jmp     loc_180032D9C
0x180032b12  cmp     cs:IpHlpSvcEtwEnabled, bpl
0x180032b19  jz      short loc_180032B3E
0x180032b1b  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, bpl
0x180032b22  jge     short loc_180032B3E
0x180032b24  lea     r8, aEnteredInitial_1; "Entered: Initialize6to4"
0x180032b2b  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032b32  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032b39  call    McTemplateU0z_EventWriteTransfer
0x180032b3e  lea     rcx, g_ProtocolState6to4
0x180032b45  call    InitializeGlobalState
0x180032b4a  movdqa  xmm0, cs:__xmm@00000001000000010000000300000003
0x180032b52  lea     rax, off_1800C80A0
0x180032b59  mov     cs:qword_1800C9748, rax
0x180032b60  lea     r8, a6to4Ipv6Micros; "6to4.ipv6.microsoft.com."
0x180032b67  lea     rax, pszDest
0x180032b6e  movdqa  cs:xmmword_1800C9770, xmm0
0x180032b76  mov     cs:dword_1800C9784, 5A0h
0x180032b80  mov     ecx, 7FFFFFFEh
0x180032b85  mov     cs:dword_1800C9780, 2
0x180032b8f  mov     edx, 401h
0x180032b94  mov     r14d, 1
0x180032b9a  test    rcx, rcx
0x180032b9d  jz      short loc_180032BBD
0x180032b9f  movzx   r9d, word ptr [r8]
0x180032ba3  test    r9w, r9w
0x180032ba7  jz      short loc_180032BBD
0x180032ba9  mov     [rax], r9w
0x180032bad  add     r8, 2
0x180032bb1  add     rax, 2
0x180032bb5  sub     rcx, r14
0x180032bb8  sub     rdx, r14
0x180032bbb  jnz     short loc_180032B9A
0x180032bbd  test    rdx, rdx
0x180032bc0  lea     rcx, [rax-2]
0x180032bc4  cmovnz  rcx, rax
0x180032bc8  mov     [rcx], bp
0x180032bcb  lea     rcx, ListHead; ListHead
0x180032bd2  mov     cs:qword_1800C9F90, rbp
0x180032bd9  call    cs:__imp_InitializeSListHead
0x180032be0  nop     dword ptr [rax+rax+00h]
0x180032be5  xor     r9d, r9d; lpName
0x180032be8  xor     r8d, r8d; bInitialState
0x180032beb  xor     edx, edx; bManualReset
0x180032bed  xor     ecx, ecx; lpEventAttributes
0x180032bef  call    cs:__imp_CreateEventW
0x180032bf6  nop     dword ptr [rax+rax+00h]
0x180032bfb  mov     cs:qword_1800C9F98, rax
0x180032c02  test    rax, rax
0x180032c05  jnz     short loc_180032C1A
0x180032c07  call    cs:__imp_GetLastError
0x180032c0e  nop     dword ptr [rax+rax+00h]
0x180032c13  mov     edi, eax
0x180032c15  jmp     loc_180032D56
0x180032c1a  mov     cs:dword_1800C9758, ebp
0x180032c20  call    IsOSServerSku
0x180032c25  test    al, al
0x180032c27  jz      short loc_180032C30
0x180032c29  mov     cs:dword_1800C9758, r14d
0x180032c30  xor     r9d, r9d; lpName
0x180032c33  mov     cs:dword_1800C9760, ebp
0x180032c39  xor     r8d, r8d; bInitialState
0x180032c3c  mov     edx, r14d; bManualReset
0x180032c3f  xor     ecx, ecx; lpEventAttributes
0x180032c41  call    cs:__imp_CreateEventW
0x180032c48  nop     dword ptr [rax+rax+00h]
0x180032c4d  mov     cs:qword_1800C9768, rax
0x180032c54  test    rax, rax
0x180032c57  jz      short loc_180032C07
0x180032c59  xor     edx, edx
0x180032c5b  lea     rcx, CriticalSection; lpCriticalSection
0x180032c62  call    InitializeWorkQueue
0x180032c67  test    eax, eax
0x180032c69  jz      short loc_180032C07
0x180032c6b  lea     rcx, CriticalSection
0x180032c72  mov     esi, r14d
0x180032c75  call    StartWorkQueue
0x180032c7a  test    eax, eax
0x180032c7c  jnz     short loc_180032C86
0x180032c7e  lea     edi, [rax+1Fh]
0x180032c81  jmp     loc_180032D56
0x180032c86  mov     eax, r14d
0x180032c89  mov     cs:dword_1800C975C, r14d
0x180032c90  xchg    eax, cs:dword_1800C9FA8
0x180032c96  mov     rbx, cs:qword_1800C9F98
0x180032c9d  lea     r8, CallbackEnvironment; pcbe
0x180032ca4  xor     edx, edx; pv
0x180032ca6  lea     rcx, OnResolutionTimerCancelled; pfnwa
0x180032cad  call    cs:__imp_CreateThreadpoolWait
0x180032cb4  nop     dword ptr [rax+rax+00h]
0x180032cb9  mov     cs:qword_1800C9FA0, rax
0x180032cc0  test    rax, rax
0x180032cc3  jnz     short loc_180032CDD
0x180032cc5  call    cs:__imp_GetLastError
0x180032ccc  nop     dword ptr [rax+rax+00h]
0x180032cd1  mov     edi, eax
0x180032cd3  mov     eax, ebp
0x180032cd5  xchg    eax, cs:dword_1800C9FA8
0x180032cdb  jmp     short loc_180032D56
0x180032cdd  mov     rdx, rbx
0x180032ce0  mov     rcx, rax
0x180032ce3  call    TpclSetThreadpoolWait
0x180032ce8  mov     r8d, cs:g_Reference
0x180032cef  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032cf6  shr     r8d, 1
0x180032cf9  lea     r9, aProcess6to4con; "Process6to4ConfigurationChange"
0x180032d00  and     r8d, 3FFFFFFFh
0x180032d07  mov     dword ptr [rsp+78h+var_50], 255h
0x180032d0f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180032d16  mov     cs:qword_1800C9FC0, rbp
0x180032d1d  mov     ecx, 40000h
0x180032d22  mov     cs:dword_1800C9754, r14d
0x180032d29  mov     edi, ebp
0x180032d2b  mov     [rsp+78h+var_58], rax
0x180032d30  call    EventWrite0
0x180032d35  mov     eax, cs:g_Reference
0x180032d3b  test    r14b, al
0x180032d3e  jnz     short loc_180032D56
0x180032d40  lea     ecx, [rax+2]
0x180032d43  lock cmpxchg cs:g_Reference, ecx
0x180032d4b  jnz     short loc_180032D35
0x180032d4d  xor     edx, edx; Context
0x180032d4f  xor     ecx, ecx; Instance
0x180032d51  call    Process6to4ConfigurationChange
0x180032d56  mov     rbx, cs:g_6to4Lock
0x180032d5d  mov     rcx, rbx; hMutex
0x180032d60  call    cs:__imp_ReleaseMutex
0x180032d67  nop     dword ptr [rax+rax+00h]
0x180032d6c  mov     [rsp+78h+var_48], eax
0x180032d70  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032d77  mov     dword ptr [rsp+78h+var_50], 25Ch
0x180032d7f  mov     r8, rbx
0x180032d82  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180032d89  mov     [rsp+78h+var_58], r13
0x180032d8e  mov     ecx, 800000h
0x180032d93  call    EventWrite0
0x180032d98  test    edi, edi
0x180032d9a  jz      short loc_180032DCF
0x180032d9c  mov     ecx, edi
0x180032d9e  call    SetStopServiceEvent
0x180032da3  cmp     cs:dword_1800C975C, ebp
0x180032da9  jz      short loc_180032DBD
0x180032dab  lea     rcx, CriticalSection
0x180032db2  call    StopWorkQueue
0x180032db7  mov     cs:dword_1800C975C, ebp
0x180032dbd  test    esi, esi
0x180032dbf  jz      short loc_180032DEE
0x180032dc1  lea     rcx, CriticalSection
0x180032dc8  call    UninitializeWorkQueue
0x180032dcd  jmp     short loc_180032DEE
0x180032dcf  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180032dd6  jz      short loc_180032DEE
0x180032dd8  xor     r8d, r8d
0x180032ddb  lea     rdx, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED
0x180032de2  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032de9  call    McTemplateU0q_EventWriteTransfer
0x180032dee  mov     rcx, cs:g_6to4StartCompleteEvent; hEvent
0x180032df5  call    cs:__imp_SetEvent
0x180032dfc  nop     dword ptr [rax+rax+00h]
0x180032e01  cmp     cs:IpHlpSvcEtwEnabled, bpl
0x180032e08  jz      short loc_180032E2D
0x180032e0a  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, bpl
0x180032e11  jge     short loc_180032E2D
0x180032e13  lea     r8, aLeavingInitial; "Leaving: Initialize6to4"
0x180032e1a  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032e21  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032e28  call    McTemplateU0z_EventWriteTransfer
0x180032e2d  mov     r8d, 27Bh
0x180032e33  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032e3a  mov     rcx, r13
0x180032e3d  add     rsp, 48h
0x180032e41  pop     r14
0x180032e43  pop     r13
0x180032e45  pop     rdi
0x180032e46  pop     rsi
0x180032e47  pop     rbp
0x180032e48  pop     rbx
0x180032e49  jmp     DereferenceServiceEx
```
