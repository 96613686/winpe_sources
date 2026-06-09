# IpTlsNetworkChangeNotification

- ea: `0x1800130a0`
- end: `0x180013366`
- name: `IpTlsNetworkChangeNotification`
- size: `710`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d7c0`
- `0x180012dcc`
- `0x180012fc0`
- `0x1800130a0`
- `0x180013370`
- `0x180013424`
- `0x1800134a0`
- `0x180013580`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001310b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001320e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001310b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001320e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001314d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001314d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013161`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013292`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013292`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001319d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001319d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013245`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013330`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013245`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013330`

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
0x1800130a0  push    rbx
0x1800130a2  push    rbp
0x1800130a3  push    rsi
0x1800130a4  push    rdi
0x1800130a5  push    r14
0x1800130a7  push    r15
0x1800130a9  sub     rsp, 28h
0x1800130ad  mov     esi, edx
0x1800130af  mov     r14, rcx
0x1800130b2  lea     rdx, aIptlsnetworkch; "IpTlsNetworkChangeNotification"
0x1800130b9  mov     ecx, 10000000h
0x1800130be  call    EventWrite0
0x1800130c3  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800130ca  test    esi, esi
0x1800130cc  jnz     loc_1800131CF
0x1800130d2  call    cs:__imp_EnterCriticalSection
0x1800130d9  nop     dword ptr [rax+rax+00h]
0x1800130de  mov     rdi, cs:g_IpTlsConnectedNetworkList
0x1800130e5  lea     rbp, g_IpTlsConnectedNetworkList
0x1800130ec  xor     ebx, ebx
0x1800130ee  mov     esi, ebx
0x1800130f0  xor     r15b, r15b
0x1800130f3  cmp     rdi, rbp
0x1800130f6  jz      short loc_180013120
0x1800130f8  mov     rsi, rdi
0x1800130fb  mov     r8d, 10h; Length
0x180013101  mov     rdi, [rdi]
0x180013104  mov     rdx, r14; Source2
0x180013107  lea     rcx, [rsi+10h]; Source1
0x18001310b  call    cs:__imp_RtlCompareMemory
0x180013112  nop     dword ptr [rax+rax+00h]
0x180013117  cmp     rax, 10h
0x18001311b  jnz     short loc_1800130F3
0x18001311d  mov     r15b, 1
0x180013120  test    r15b, r15b
0x180013123  cmovnz  rbx, rsi
0x180013127  test    rbx, rbx
0x18001312a  jz      short loc_18001316D
0x18001312c  mov     rax, [rbx]
0x18001312f  cmp     [rax+8], rbx
0x180013133  jnz     loc_18001335F
0x180013139  mov     rdx, [rbx+8]
0x18001313d  cmp     [rdx], rbx
0x180013140  jnz     loc_18001335F
0x180013146  mov     [rdx], rax
0x180013149  mov     [rax+8], rdx
0x18001314d  call    cs:__imp_GetProcessHeap
0x180013154  nop     dword ptr [rax+rax+00h]
0x180013159  mov     r8, rbx; lpMem
0x18001315c  xor     edx, edx; dwFlags
0x18001315e  mov     rcx, rax; hHeap
0x180013161  call    cs:__imp_HeapFree
0x180013168  nop     dword ptr [rax+rax+00h]
0x18001316d  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013174  call    cs:__imp_LeaveCriticalSection
0x18001317b  nop     dword ptr [rax+rax+00h]
0x180013180  mov     rcx, r14; struct _GUID *
0x180013183  call    IpTlsNetworkDeleteNotification
0x180013188  cmp     cs:g_IpTlsInternetConnectivityPresent, 0
0x18001318f  jz      short loc_1800131C1
0x180013191  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x180013198  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001319d  call    cs:__imp_WaitForSingleObject
0x1800131a4  nop     dword ptr [rax+rax+00h]
0x1800131a9  call    IpTlsNotifyClientsOfInternetConnectivity
0x1800131ae  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x1800131b5  call    cs:__imp_ReleaseMutex
0x1800131bc  nop     dword ptr [rax+rax+00h]
0x1800131c1  add     rsp, 28h
0x1800131c5  pop     r15
0x1800131c7  pop     r14
0x1800131c9  pop     rdi
0x1800131ca  pop     rsi
0x1800131cb  pop     rbp
0x1800131cc  pop     rbx
0x1800131cd  retn
0x1800131cf  mov     [rsp+58h+arg_0], r12
0x1800131d4  call    cs:__imp_EnterCriticalSection
0x1800131db  nop     dword ptr [rax+rax+00h]
0x1800131e0  mov     rdi, cs:g_IpTlsConnectedNetworkList
0x1800131e7  lea     rbp, g_IpTlsConnectedNetworkList
0x1800131ee  xor     ebx, ebx
0x1800131f0  mov     r15d, ebx
0x1800131f3  xor     r12b, r12b
0x1800131f6  cmp     rdi, rbp
0x1800131f9  jz      short loc_180013223
0x1800131fb  mov     r15, rdi
0x1800131fe  mov     r8d, 10h; Length
0x180013204  mov     rdi, [rdi]
0x180013207  mov     rdx, r14; Source2
0x18001320a  lea     rcx, [r15+10h]; Source1
0x18001320e  call    cs:__imp_RtlCompareMemory
0x180013215  nop     dword ptr [rax+rax+00h]
0x18001321a  cmp     rax, 10h
0x18001321e  jnz     short loc_1800131F6
0x180013220  mov     r12b, 1
0x180013223  test    r12b, r12b
0x180013226  mov     r12, [rsp+58h+arg_0]
0x18001322b  cmovnz  rbx, r15
0x18001322f  test    rbx, rbx
0x180013232  jz      loc_1800132D2
0x180013238  mov     edi, [rbx+20h]
0x18001323b  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013242  mov     [rbx+20h], esi
0x180013245  call    cs:__imp_LeaveCriticalSection
0x18001324c  nop     dword ptr [rax+rax+00h]
0x180013251  cmp     edi, esi
0x180013253  jnz     loc_1800131C1
0x180013259  mov     r8d, esi
0x18001325c  lea     rdx, aIptlsnetworkch_1; "IpTlsNetworkChangeNotification; connect"...
0x180013263  mov     ecx, 10000000h
0x180013268  call    EventWrite0
0x18001326d  mov     rcx, cs:g_IpTlsConfigChangeLock
0x180013274  call    IpTlsAcquireLock
0x180013279  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180013280  mov     cs:g_IpTlsCorpConnectivityAdjusted, 0
0x180013287  mov     cs:g_IpTlsCorpConnectivityTimeout, 5F5E100h
0x180013292  call    cs:__imp_ReleaseMutex
0x180013299  nop     dword ptr [rax+rax+00h]
0x18001329e  mov     rcx, cs:g_IpTlsNLMNotificationLock
0x1800132a5  call    IpTlsAcquireLock
0x1800132aa  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, 0
0x1800132b1  jnz     loc_1800131AE
0x1800132b7  lea     rdx, aIptlsnetworkch_0; "IpTlsNetworkChangeNotification - restar"...
0x1800132be  mov     ecx, 10000000h
0x1800132c3  call    EventWrite0
0x1800132c8  call    IpTlsRestartCorpConnectivityTimer
0x1800132cd  jmp     loc_1800131AE
0x1800132d2  mov     ecx, 28h ; '('; dwBytes
0x1800132d7  call    MALLOC
0x1800132dc  test    rax, rax
0x1800132df  jz      short loc_180013329
0x1800132e1  movups  xmm0, xmmword ptr [r14]
0x1800132e5  mov     [rax+20h], esi
0x1800132e8  movups  xmmword ptr [rax+10h], xmm0
0x1800132ec  mov     rcx, cs:qword_1800CC4B8
0x1800132f3  cmp     [rcx], rbp
0x1800132f6  jnz     short loc_18001335F
0x1800132f8  mov     [rax+8], rcx
0x1800132fc  mov     [rax], rbp
0x1800132ff  mov     [rcx], rax
0x180013302  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013309  mov     cs:qword_1800CC4B8, rax
0x180013310  call    cs:__imp_LeaveCriticalSection
0x180013317  nop     dword ptr [rax+rax+00h]
0x18001331c  mov     rcx, r14; struct _GUID *
0x18001331f  call    IpTlsNetworkAddNotification
0x180013324  jmp     loc_1800131C1
0x180013329  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180013330  call    cs:__imp_LeaveCriticalSection
0x180013337  nop     dword ptr [rax+rax+00h]
0x18001333c  mov     r8d, 8
0x180013342  lea     rdx, aIptlsnetworkch_2; "IpTlsNetworkChangeNotification: IpTlsAd"...
0x180013349  mov     ecx, 10000000h
0x18001334e  add     rsp, 28h
0x180013352  pop     r15
0x180013354  pop     r14
0x180013356  pop     rdi
0x180013357  pop     rsi
0x180013358  pop     rbp
0x180013359  pop     rbx
0x18001335a  jmp     EventWrite0
0x18001335f  mov     ecx, 3
0x180013364  int     29h; Win8: RtlFailFast(ecx)
```
