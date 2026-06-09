# DnsDhcpSrvRegisterInitEx

- ea: `0x18008e5c0`
- end: `0x18008e7fd`
- name: `DnsDhcpSrvRegisterInitEx`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180096240`

## callees

- `0x1800662b0`
- `0x18008972c`
- `0x18008b5f0`
- `0x18008dc64`
- `0x18008dd00`
- `0x18008e5c0`
- `0x1800a7374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e604`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e7d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e7d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e640`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e640`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18008e67b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18008e67b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008e773`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008e773`
- `ntdll!RtlInitializeCriticalSection` at `0x18008e6ca`
- `ntdll!RtlInitializeCriticalSection` at `0x18008e6ca`

## pseudocode

```c
__int64 __fastcall DnsDhcpSrvRegisterInitEx(STRSAFE_LPCWSTR *a1, unsigned int a2, unsigned int a3)
{
  DWORD LastError; // ebx
  int v7; // edi
  DWORD ThreadId; // [rsp+30h] [rbp-38h] BYREF

  ThreadId = 0;
  if ( !g_fVelocityDisableInternalExports && a3 <= 3 )
    g_DhcpMaxRetiesDnsReg = a3;
  EnterCriticalSection(&g_DhcpSrvCS);
  if ( g_DhcpSrvState == 10 )
    goto LABEL_5;
  g_DhcpSrvState = 5;
  g_fDhcpSrvStop = 0;
  g_DhcpSrvQuitEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_DhcpSrvQuitEvent )
    goto LABEL_25;
  v7 = 0xFFFF;
  g_DhcpSrvSem = CreateSemaphoreExW(0, 0, 0xFFFF, 0, 0, 0x1F0003u);
  if ( !g_DhcpSrvSem )
    goto LABEL_25;
  g_DhcpSrvWaitHandles = g_DhcpSrvQuitEvent;
  qword_180111A30 = (__int64)g_DhcpSrvSem;
  if ( g_fVelocityDisableInternalExports && a3 <= 3 )
    g_DhcpMaxRetiesDnsReg = a3;
  LastError = RtlInitializeCriticalSection(&g_DhcpSrvQueueCS);
  if ( LastError )
    goto LABEL_27;
  g_fDhcpSrvQueueCsCreated = 1;
  LastError = DhcpSrv_InitializeQueues();
  if ( LastError )
  {
    g_pDhcpSrvQueue = 0;
    g_pDhcpSrvTimedOutQueue = 0;
LABEL_27:
    DhcpSrv_PrivateCleanup();
    g_DhcpSrvState = 1;
    goto LABEL_28;
  }
  if ( a1 )
  {
    g_pIdentityCreds = (LPVOID)Dns_AllocateCredentials(*a1, a1[1], a1[2]);
    if ( !g_pIdentityCreds )
      goto LABEL_25;
    if ( (unsigned int)Dns_StartSecurity(0) || (unsigned int)Dns_RefreshSSpiCredentialsHandle(g_pIdentityCreds) )
    {
      LastError = 1368;
      goto LABEL_27;
    }
  }
  g_hDhcpSrvRegThread = CreateThread(0, 0, DynDnsConsumerThread, 0, 0, &ThreadId);
  if ( !g_hDhcpSrvRegThread )
  {
LABEL_25:
    LastError = GetLastError();
    if ( !LastError )
      LastError = 14;
    goto LABEL_27;
  }
  if ( a2 )
  {
    if ( a2 <= 0xFFFF )
      v7 = a2;
    g_DhcpSrvMaxQueueSize = v7;
  }
  g_DhcpSrvState = 10;
LABEL_5:
  LastError = 0;
LABEL_28:
  LeaveCriticalSection(&g_DhcpSrvCS);
  return LastError;
}

```

## disassembly

```asm
0x18008e5c0  push    rbx
0x18008e5c2  push    rsi
0x18008e5c3  push    rdi
0x18008e5c4  push    r14
0x18008e5c6  sub     rsp, 48h
0x18008e5ca  mov     rax, cs:__security_cookie
0x18008e5d1  xor     rax, rsp
0x18008e5d4  mov     [rsp+68h+var_30], rax
0x18008e5d9  cmp     cs:g_fVelocityDisableInternalExports, 0
0x18008e5e0  mov     ebx, r8d
0x18008e5e3  mov     esi, edx
0x18008e5e5  mov     [rsp+68h+ThreadId], 0
0x18008e5ed  mov     r14, rcx
0x18008e5f0  jnz     short loc_18008E5FD
0x18008e5f2  cmp     ebx, 3
0x18008e5f5  ja      short loc_18008E5FD
0x18008e5f7  mov     cs:g_DhcpMaxRetiesDnsReg, ebx
0x18008e5fd  lea     rcx, g_DhcpSrvCS; lpCriticalSection
0x18008e604  call    cs:__imp_EnterCriticalSection
0x18008e60b  nop     dword ptr [rax+rax+00h]
0x18008e610  cmp     cs:g_DhcpSrvState, 0Ah
0x18008e617  jnz     short loc_18008E620
0x18008e619  xor     ebx, ebx
0x18008e61b  jmp     loc_18008E7D0
0x18008e620  xor     r9d, r9d; lpName
0x18008e623  mov     cs:g_DhcpSrvState, 5
0x18008e62d  xor     r8d, r8d; bInitialState
0x18008e630  mov     cs:g_fDhcpSrvStop, 0
0x18008e63a  xor     ecx, ecx; lpEventAttributes
0x18008e63c  lea     edx, [r9+1]; bManualReset
0x18008e640  call    cs:__imp_CreateEventW
0x18008e647  nop     dword ptr [rax+rax+00h]
0x18008e64c  mov     cs:g_DhcpSrvQuitEvent, rax
0x18008e653  test    rax, rax
0x18008e656  jz      loc_18008E7A9
0x18008e65c  mov     edi, 0FFFFh
0x18008e661  mov     [rsp+68h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18008e669  mov     r8d, edi; lMaximumCount
0x18008e66c  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18008e674  xor     r9d, r9d; lpName
0x18008e677  xor     edx, edx; lInitialCount
0x18008e679  xor     ecx, ecx; lpSemaphoreAttributes
0x18008e67b  call    cs:__imp_CreateSemaphoreExW
0x18008e682  nop     dword ptr [rax+rax+00h]
0x18008e687  mov     cs:g_DhcpSrvSem, rax
0x18008e68e  mov     rcx, rax
0x18008e691  test    rax, rax
0x18008e694  jz      loc_18008E7A9
0x18008e69a  cmp     cs:g_fVelocityDisableInternalExports, 0
0x18008e6a1  mov     rax, cs:g_DhcpSrvQuitEvent
0x18008e6a8  mov     cs:g_DhcpSrvWaitHandles, rax
0x18008e6af  mov     cs:qword_180111A30, rcx
0x18008e6b6  jz      short loc_18008E6C3
0x18008e6b8  cmp     ebx, 3
0x18008e6bb  ja      short loc_18008E6C3
0x18008e6bd  mov     cs:g_DhcpMaxRetiesDnsReg, ebx
0x18008e6c3  lea     rcx, g_DhcpSrvQueueCS; CriticalSection
0x18008e6ca  call    cs:__imp_RtlInitializeCriticalSection
0x18008e6d1  nop     dword ptr [rax+rax+00h]
0x18008e6d6  mov     ebx, eax
0x18008e6d8  test    eax, eax
0x18008e6da  jnz     loc_18008E7C1
0x18008e6e0  mov     cs:g_fDhcpSrvQueueCsCreated, 1
0x18008e6ea  call    DhcpSrv_InitializeQueues
0x18008e6ef  mov     ebx, eax
0x18008e6f1  test    eax, eax
0x18008e6f3  jz      short loc_18008E710
0x18008e6f5  mov     cs:g_pDhcpSrvQueue, 0
0x18008e700  mov     cs:g_pDhcpSrvTimedOutQueue, 0
0x18008e70b  jmp     loc_18008E7C1
0x18008e710  test    r14, r14
0x18008e713  jz      short loc_18008E753
0x18008e715  mov     r8, [r14+10h]; STRSAFE_LPCWSTR
0x18008e719  mov     rdx, [r14+8]; STRSAFE_LPCWSTR
0x18008e71d  mov     rcx, [r14]; pszSrc
0x18008e720  call    Dns_AllocateCredentials
0x18008e725  mov     cs:g_pIdentityCreds, rax
0x18008e72c  test    rax, rax
0x18008e72f  jz      short loc_18008E7A9
0x18008e731  xor     ecx, ecx
0x18008e733  call    Dns_StartSecurity
0x18008e738  test    eax, eax
0x18008e73a  jz      short loc_18008E743
0x18008e73c  mov     ebx, 558h
0x18008e741  jmp     short loc_18008E7C1
0x18008e743  mov     rcx, cs:g_pIdentityCreds; pAuthData
0x18008e74a  call    Dns_RefreshSSpiCredentialsHandle
0x18008e74f  test    eax, eax
0x18008e751  jnz     short loc_18008E73C
0x18008e753  lea     rax, [rsp+68h+ThreadId]
0x18008e758  xor     r9d, r9d; lpParameter
0x18008e75b  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpThreadId
0x18008e760  lea     r8, DynDnsConsumerThread; lpStartAddress
0x18008e767  xor     edx, edx; dwStackSize
0x18008e769  mov     [rsp+68h+dwFlags], 0; dwCreationFlags
0x18008e771  xor     ecx, ecx; lpThreadAttributes
0x18008e773  call    cs:__imp_CreateThread
0x18008e77a  nop     dword ptr [rax+rax+00h]
0x18008e77f  mov     cs:g_hDhcpSrvRegThread, rax
0x18008e786  test    rax, rax
0x18008e789  jz      short loc_18008E7A9
0x18008e78b  test    esi, esi
0x18008e78d  jz      short loc_18008E79A
0x18008e78f  cmp     esi, edi
0x18008e791  cmovbe  edi, esi
0x18008e794  mov     cs:g_DhcpSrvMaxQueueSize, edi
0x18008e79a  mov     cs:g_DhcpSrvState, 0Ah
0x18008e7a4  jmp     loc_18008E619
0x18008e7a9  call    cs:__imp_GetLastError
0x18008e7b0  nop     dword ptr [rax+rax+00h]
0x18008e7b5  mov     ebx, eax
0x18008e7b7  mov     eax, 0Eh
0x18008e7bc  test    ebx, ebx
0x18008e7be  cmovz   ebx, eax
0x18008e7c1  call    DhcpSrv_PrivateCleanup
0x18008e7c6  mov     cs:g_DhcpSrvState, 1
0x18008e7d0  lea     rcx, g_DhcpSrvCS; lpCriticalSection
0x18008e7d7  call    cs:__imp_LeaveCriticalSection
0x18008e7de  nop     dword ptr [rax+rax+00h]
0x18008e7e3  mov     eax, ebx
0x18008e7e5  mov     rcx, [rsp+68h+var_30]
0x18008e7ea  xor     rcx, rsp; StackCookie
0x18008e7ed  call    __security_check_cookie
0x18008e7f2  add     rsp, 48h
0x18008e7f6  pop     r14
0x18008e7f8  pop     rdi
0x18008e7f9  pop     rsi
0x18008e7fa  pop     rbx
0x18008e7fb  retn
```
