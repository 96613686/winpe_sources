# IpTlsNetworkChangeNotification

- ea: `0x180013090`
- end: `0x180013356`
- name: `IpTlsNetworkChangeNotification`
- size: `710`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d7b0`
- `0x180012dbc`
- `0x180012fb0`
- `0x180013090`
- `0x180013360`
- `0x180013414`
- `0x180013490`
- `0x180013570`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800130fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800131fe`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800130fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800131fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001313d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001313d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013151`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013282`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013282`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001318d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001318d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013164`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013235`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013300`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013320`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013164`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013235`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013300`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013320`

## pseudocode

```c
void __fastcall IpTlsNetworkChangeNotification(struct _GUID *a1, unsigned int a2)
{
  __int64 *v4; // rdi
  __int64 *v5; // rbx
  __int64 *v6; // rsi
  char v7; // r15
  __int64 v8; // rax
  __int64 **v9; // rdx
  HANDLE ProcessHeap; // rax
  __int64 *v11; // rdi
  __int64 *v12; // rbx
  __int64 *v13; // r15
  char v14; // r12
  int v15; // edi
  __int64 v16; // rax
  struct _GUID v17; // xmm0
  __int64 *v18; // rcx

  EventWrite0(0x10000000, L"IpTlsNetworkChangeNotification");
  if ( !a2 )
  {
    EnterCriticalSection(&g_IpTlsConnectedNetworkListLock);
    v4 = (__int64 *)g_IpTlsConnectedNetworkList;
    v5 = 0;
    v6 = 0;
    v7 = 0;
    while ( v4 != &g_IpTlsConnectedNetworkList )
    {
      v6 = v4;
      v4 = (__int64 *)*v4;
      if ( RtlCompareMemory(v6 + 2, a1, 0x10u) == 16 )
      {
        v7 = 1;
        break;
      }
    }
    if ( v7 )
      v5 = v6;
    if ( !v5 )
      goto LABEL_12;
    v8 = *v5;
    if ( *(__int64 **)(*v5 + 8) == v5 )
    {
      v9 = (__int64 **)v5[1];
      if ( *v9 == v5 )
      {
        *v9 = (__int64 *)v8;
        *(_QWORD *)(v8 + 8) = v9;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v5);
LABEL_12:
        LeaveCriticalSection(&g_IpTlsConnectedNetworkListLock);
        IpTlsNetworkDeleteNotification(a1);
        if ( !g_IpTlsInternetConnectivityPresent )
          return;
        WaitForSingleObject(g_IpTlsNLMNotificationLock, 0xFFFFFFFF);
        IpTlsNotifyClientsOfInternetConnectivity();
        goto LABEL_14;
      }
    }
LABEL_30:
    __fastfail(3u);
  }
  EnterCriticalSection(&g_IpTlsConnectedNetworkListLock);
  v11 = (__int64 *)g_IpTlsConnectedNetworkList;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v11 != &g_IpTlsConnectedNetworkList )
  {
    v13 = v11;
    v11 = (__int64 *)*v11;
    if ( RtlCompareMemory(v13 + 2, a1, 0x10u) == 16 )
    {
      v14 = 1;
      break;
    }
  }
  if ( v14 )
    v12 = v13;
  if ( !v12 )
  {
    v16 = MALLOC(0x28u);
    if ( !v16 )
    {
      LeaveCriticalSection(&g_IpTlsConnectedNetworkListLock);
      EventWrite0(0x10000000, L"IpTlsNetworkChangeNotification: IpTlsAddNetwork failed with 0x%x", 8);
      return;
    }
    v17 = *a1;
    *(_DWORD *)(v16 + 32) = a2;
    *(struct _GUID *)(v16 + 16) = v17;
    v18 = (__int64 *)qword_1800CC4B8;
    if ( *(__int64 **)qword_1800CC4B8 == &g_IpTlsConnectedNetworkList )
    {
      *(_QWORD *)(v16 + 8) = qword_1800CC4B8;
      *(_QWORD *)v16 = &g_IpTlsConnectedNetworkList;
      *v18 = v16;
      qword_1800CC4B8 = v16;
      LeaveCriticalSection(&g_IpTlsConnectedNetworkListLock);
      IpTlsNetworkAddNotification(a1);
      return;
    }
    goto LABEL_30;
  }
  v15 = *((_DWORD *)v12 + 8);
  *((_DWORD *)v12 + 8) = a2;
  LeaveCriticalSection(&g_IpTlsConnectedNetworkListLock);
  if ( v15 == a2 )
  {
    EventWrite0(0x10000000, L"IpTlsNetworkChangeNotification; connectivity = 0x%x - trying to restart corp timer", a2);
    IpTlsAcquireLock(g_IpTlsConfigChangeLock);
    g_IpTlsCorpConnectivityAdjusted = 0;
    g_IpTlsCorpConnectivityTimeout = 100000000;
    ReleaseMutex(g_IpTlsConfigChangeLock);
    IpTlsAcquireLock(g_IpTlsNLMNotificationLock);
    if ( !g_IpTlsConfiguredForCorpConnectivity )
    {
      EventWrite0(0x10000000, L"IpTlsNetworkChangeNotification - restarting corp timer");
      IpTlsRestartCorpConnectivityTimer();
    }
LABEL_14:
    ReleaseMutex(g_IpTlsNLMNotificationLock);
  }
}

```

## disassembly

```asm
0x180013090  push    rbx
0x180013092  push    rbp
0x180013093  push    rsi
0x180013094  push    rdi
0x180013095  push    r14
0x180013097  push    r15
0x180013099  sub     rsp, 28h
0x18001309d  mov     esi, edx
0x18001309f  mov     r14, rcx
0x1800130a2  lea     rdx, aIptlsnetworkch; "IpTlsNetworkChangeNotification"
0x1800130a9  mov     ecx, 10000000h
0x1800130ae  call    EventWrite0
0x1800130b3  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800130ba  test    esi, esi
0x1800130bc  jnz     loc_1800131BF
0x1800130c2  call    cs:__imp_EnterCriticalSection
0x1800130c9  nop     dword ptr [rax+rax+00h]
0x1800130ce  mov     rdi, cs:g_IpTlsConnectedNetworkList
0x1800130d5  lea     rbp, g_IpTlsConnectedNetworkList
0x1800130dc  xor     ebx, ebx
0x1800130de  mov     esi, ebx
0x1800130e0  xor     r15b, r15b
0x1800130e3  cmp     rdi, rbp
0x1800130e6  jz      short loc_180013110
0x1800130e8  mov     rsi, rdi
0x1800130eb  mov     r8d, 10h; Length
0x1800130f1  mov     rdi, [rdi]
0x1800130f4  mov     rdx, r14; Source2
0x1800130f7  lea     rcx, [rsi+10h]; Source1
0x1800130fb  call    cs:__imp_RtlCompareMemory
0x180013102  nop     dword ptr [rax+rax+00h]
0x180013107  cmp     rax, 10h
0x18001310b  jnz     short loc_1800130E3
0x18001310d  mov     r15b, 1
0x180013110  test    r15b, r15b
0x180013113  cmovnz  rbx, rsi
0x180013117  test    rbx, rbx
0x18001311a  jz      short loc_18001315D
0x18001311c  mov     rax, [rbx]
0x18001311f  cmp     [rax+8], rbx
0x180013123  jnz     loc_18001334F
0x180013129  mov     rdx, [rbx+8]
0x18001312d  cmp     [rdx], rbx
0x180013130  jnz     loc_18001334F
0x180013136  mov     [rdx], rax
0x180013139  mov     [rax+8], rdx
0x18001313d  call    cs:__imp_GetProcessHeap
0x180013144  nop     dword ptr [rax+rax+00h]
0x180013149  mov     r8, rbx; lpMem
0x18001314c  xor     edx, edx; dwFlags
0x18001314e  mov     rcx, rax; hHeap
0x180013151  call    cs:__imp_HeapFree
0x180013158  nop     dword ptr [rax+rax+00h]
0x18001315d  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013164  call    cs:__imp_LeaveCriticalSection
0x18001316b  nop     dword ptr [rax+rax+00h]
0x180013170  mov     rcx, r14; struct _GUID *
0x180013173  call    IpTlsNetworkDeleteNotification
0x180013178  cmp     cs:g_IpTlsInternetConnectivityPresent, 0
0x18001317f  jz      short loc_1800131B1
0x180013181  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x180013188  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001318d  call    cs:__imp_WaitForSingleObject
0x180013194  nop     dword ptr [rax+rax+00h]
0x180013199  call    IpTlsNotifyClientsOfInternetConnectivity
0x18001319e  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x1800131a5  call    cs:__imp_ReleaseMutex
0x1800131ac  nop     dword ptr [rax+rax+00h]
0x1800131b1  add     rsp, 28h
0x1800131b5  pop     r15
0x1800131b7  pop     r14
0x1800131b9  pop     rdi
0x1800131ba  pop     rsi
0x1800131bb  pop     rbp
0x1800131bc  pop     rbx
0x1800131bd  retn
0x1800131bf  mov     [rsp+58h+arg_0], r12
0x1800131c4  call    cs:__imp_EnterCriticalSection
0x1800131cb  nop     dword ptr [rax+rax+00h]
0x1800131d0  mov     rdi, cs:g_IpTlsConnectedNetworkList
0x1800131d7  lea     rbp, g_IpTlsConnectedNetworkList
0x1800131de  xor     ebx, ebx
0x1800131e0  mov     r15d, ebx
0x1800131e3  xor     r12b, r12b
0x1800131e6  cmp     rdi, rbp
0x1800131e9  jz      short loc_180013213
0x1800131eb  mov     r15, rdi
0x1800131ee  mov     r8d, 10h; Length
0x1800131f4  mov     rdi, [rdi]
0x1800131f7  mov     rdx, r14; Source2
0x1800131fa  lea     rcx, [r15+10h]; Source1
0x1800131fe  call    cs:__imp_RtlCompareMemory
0x180013205  nop     dword ptr [rax+rax+00h]
0x18001320a  cmp     rax, 10h
0x18001320e  jnz     short loc_1800131E6
0x180013210  mov     r12b, 1
0x180013213  test    r12b, r12b
0x180013216  mov     r12, [rsp+58h+arg_0]
0x18001321b  cmovnz  rbx, r15
0x18001321f  test    rbx, rbx
0x180013222  jz      loc_1800132C2
0x180013228  mov     edi, [rbx+20h]
0x18001322b  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013232  mov     [rbx+20h], esi
0x180013235  call    cs:__imp_LeaveCriticalSection
0x18001323c  nop     dword ptr [rax+rax+00h]
0x180013241  cmp     edi, esi
0x180013243  jnz     loc_1800131B1
0x180013249  mov     r8d, esi
0x18001324c  lea     rdx, aIptlsnetworkch_1; "IpTlsNetworkChangeNotification; connect"...
0x180013253  mov     ecx, 10000000h
0x180013258  call    EventWrite0
0x18001325d  mov     rcx, cs:g_IpTlsConfigChangeLock
0x180013264  call    IpTlsAcquireLock
0x180013269  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180013270  mov     cs:g_IpTlsCorpConnectivityAdjusted, 0
0x180013277  mov     cs:g_IpTlsCorpConnectivityTimeout, 5F5E100h
0x180013282  call    cs:__imp_ReleaseMutex
0x180013289  nop     dword ptr [rax+rax+00h]
0x18001328e  mov     rcx, cs:g_IpTlsNLMNotificationLock
0x180013295  call    IpTlsAcquireLock
0x18001329a  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, 0
0x1800132a1  jnz     loc_18001319E
0x1800132a7  lea     rdx, aIptlsnetworkch_0; "IpTlsNetworkChangeNotification - restar"...
0x1800132ae  mov     ecx, 10000000h
0x1800132b3  call    EventWrite0
0x1800132b8  call    IpTlsRestartCorpConnectivityTimer
0x1800132bd  jmp     loc_18001319E
0x1800132c2  mov     ecx, 28h ; '('; dwBytes
0x1800132c7  call    MALLOC
0x1800132cc  test    rax, rax
0x1800132cf  jz      short loc_180013319
0x1800132d1  movups  xmm0, xmmword ptr [r14]
0x1800132d5  mov     [rax+20h], esi
0x1800132d8  movups  xmmword ptr [rax+10h], xmm0
0x1800132dc  mov     rcx, cs:qword_1800CC4B8
0x1800132e3  cmp     [rcx], rbp
0x1800132e6  jnz     short loc_18001334F
0x1800132e8  mov     [rax+8], rcx
0x1800132ec  mov     [rax], rbp
0x1800132ef  mov     [rcx], rax
0x1800132f2  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800132f9  mov     cs:qword_1800CC4B8, rax
0x180013300  call    cs:__imp_LeaveCriticalSection
0x180013307  nop     dword ptr [rax+rax+00h]
0x18001330c  mov     rcx, r14; struct _GUID *
0x18001330f  call    IpTlsNetworkAddNotification
0x180013314  jmp     loc_1800131B1
0x180013319  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013320  call    cs:__imp_LeaveCriticalSection
0x180013327  nop     dword ptr [rax+rax+00h]
0x18001332c  mov     r8d, 8
0x180013332  lea     rdx, aIptlsnetworkch_2; "IpTlsNetworkChangeNotification: IpTlsAd"...
0x180013339  mov     ecx, 10000000h
0x18001333e  add     rsp, 28h
0x180013342  pop     r15
0x180013344  pop     r14
0x180013346  pop     rdi
0x180013347  pop     rsi
0x180013348  pop     rbp
0x180013349  pop     rbx
0x18001334a  jmp     EventWrite0
0x18001334f  mov     ecx, 3
0x180013354  int     29h; Win8: RtlFailFast(ecx)
```
