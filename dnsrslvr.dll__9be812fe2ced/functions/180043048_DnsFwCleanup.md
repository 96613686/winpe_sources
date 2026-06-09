# DnsFwCleanup

- ea: `0x180043048`
- end: `0x1800432f6`
- name: `DnsFwCleanup`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18003cfc0`
- `0x180045024`

## callees

- `0x180043048`
- `0x1800432fc`
- `0x1800444d0`
- `0x180046ec0`
- `0x18006faf0`
- `0x180086700`

## import_xrefs

- `DNSAPI!DnsCancelQueryRaw` at `0x180043192`
- `DNSAPI!DnsCancelQueryRaw` at `0x180043192`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800432a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800432b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800432a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800432b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180043185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800431a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180043185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800431a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004313a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004322c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004313a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004322c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800430c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800431ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800430c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800431ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18004326b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18004326b`
- `WS2_32!__imp_WSACleanup` at `0x18004328c`
- `WS2_32!__imp_WSACleanup` at `0x18004328c`

## pseudocode

```c
void DnsFwCleanup()
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v1; // rcx
  struct _LIST_ENTRY **p_Flink; // rcx
  struct _LIST_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rax
  struct _LIST_ENTRY *v6; // rax
  struct _LIST_ENTRY *v7; // rcx
  struct _LIST_ENTRY **v8; // rcx
  struct _LIST_ENTRY *v9; // rax
  __int64 *v10; // rbx
  __int64 *v11; // rax
  __int64 *v12; // [rsp+20h] [rbp-30h] BYREF
  struct _LIST_ENTRY *v13; // [rsp+28h] [rbp-28h]
  __int64 *v14; // [rsp+30h] [rbp-20h] BYREF
  struct _LIST_ENTRY *v15; // [rsp+38h] [rbp-18h]

  v14 = (__int64 *)&v14;
  v15 = (struct _LIST_ENTRY *)&v14;
  v12 = (__int64 *)&v12;
  v13 = (struct _LIST_ENTRY *)&v12;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 50, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids);
  if ( g_fVelocityZtdns )
  {
    if ( g_fForwarderRunning )
      DnsFwStop();
    EnterCriticalSection(&g_QueryContextListLock);
    while ( 1 )
    {
      Flink = g_QueryContextList.Flink;
      if ( g_QueryContextList.Flink == &g_QueryContextList )
        break;
      if ( g_QueryContextList.Flink->Blink != &g_QueryContextList
        || (v1 = g_QueryContextList.Flink->Flink, g_QueryContextList.Flink->Flink->Blink != g_QueryContextList.Flink)
        || (g_QueryContextList.Flink = g_QueryContextList.Flink->Flink,
            v1->Blink = &g_QueryContextList,
            Flink->Blink = Flink,
            Flink->Flink = Flink,
            _InterlockedIncrement((volatile signed __int32 *)&Flink[2]),
            p_Flink = &v13->Flink,
            (__int64 **)v13->Flink != &v12) )
      {
LABEL_28:
        __fastfail(3u);
      }
      v3 = Flink + 1;
      v3->Blink = v13;
      v3->Flink = (struct _LIST_ENTRY *)&v12;
      *p_Flink = v3;
      v13 = v3;
    }
    LeaveCriticalSection(&g_QueryContextListLock);
    while ( 1 )
    {
      v4 = v12;
      if ( v12 == (__int64 *)&v12 )
        break;
      if ( (__int64 **)v12[1] != &v12 )
        goto LABEL_28;
      v5 = (__int64 *)*v12;
      if ( *(__int64 **)(*v12 + 8) != v12 )
        goto LABEL_28;
      v12 = (__int64 *)*v12;
      v5[1] = (__int64)&v12;
      v4[1] = (__int64)v4;
      *v4 = (__int64)v4;
      WaitForSingleObject((HANDLE)v4[56], 0xFFFFFFFF);
      DnsCancelQueryRaw(v4 + 51);
      WaitForSingleObject((HANDLE)v4[57], 0xFFFFFFFF);
      DnsFwDerefContext((struct _DNS_FORWARD_CONTEXT *)(v4 - 2));
    }
    EnterCriticalSection(&g_SocketListLock);
    while ( 1 )
    {
      v6 = g_SocketList.Flink;
      if ( g_SocketList.Flink == &g_SocketList )
        break;
      if ( g_SocketList.Flink->Blink != &g_SocketList )
        goto LABEL_28;
      v7 = g_SocketList.Flink->Flink;
      if ( g_SocketList.Flink->Flink->Blink != g_SocketList.Flink )
        goto LABEL_28;
      g_SocketList.Flink = g_SocketList.Flink->Flink;
      v7->Blink = &g_SocketList;
      v6->Blink = v6;
      v6->Flink = v6;
      _InterlockedIncrement((volatile signed __int32 *)&v6[2].Blink);
      v8 = &v15->Flink;
      if ( (__int64 **)v15->Flink != &v14 )
        goto LABEL_28;
      v9 = v6 + 1;
      v9->Blink = v15;
      v9->Flink = (struct _LIST_ENTRY *)&v14;
      *v8 = v9;
      v15 = v9;
    }
    LeaveCriticalSection(&g_SocketListLock);
    while ( 1 )
    {
      v10 = v14;
      if ( v14 == (__int64 *)&v14 )
        break;
      if ( (__int64 **)v14[1] != &v14 )
        goto LABEL_28;
      v11 = (__int64 *)*v14;
      if ( *(__int64 **)(*v14 + 8) != v14 )
        goto LABEL_28;
      v14 = (__int64 *)*v14;
      v11[1] = (__int64)&v14;
      v10[1] = (__int64)v10;
      *v10 = (__int64)v10;
      WaitForThreadpoolIoCallbacks((PTP_IO)v10[7], 0);
      DnsFwDerefSocket((struct _DNS_FORWARD_SOCKET *)(v10 - 2));
    }
    if ( g_fWinsockStarted )
    {
      WSACleanup();
      g_fWinsockStarted = 0;
    }
    DeleteCriticalSection(&g_QueryContextListLock);
    DeleteCriticalSection(&g_SocketListLock);
    g_fInitialized = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 51, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids);
}

```

## disassembly

```asm
0x180043048  mov     [rsp-8+arg_0], rbx
0x18004304d  push    rbp
0x18004304e  mov     rbp, rsp
0x180043051  sub     rsp, 50h
0x180043055  mov     rax, cs:__security_cookie
0x18004305c  xor     rax, rsp
0x18004305f  mov     [rbp+var_10], rax
0x180043063  lea     rax, [rbp+var_20]
0x180043067  mov     [rbp+var_20], rax
0x18004306b  lea     rax, [rbp+var_20]
0x18004306f  mov     [rbp+var_18], rax
0x180043073  lea     rax, [rbp+var_30]
0x180043077  mov     [rbp+var_30], rax
0x18004307b  lea     rax, [rbp+var_30]
0x18004307f  mov     [rbp+var_28], rax
0x180043083  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004308a  jz      short loc_1800430A2
0x18004308c  mov     edx, 32h ; '2'
0x180043091  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180043098  mov     ecx, 40Bh
0x18004309d  call    WPP_SF_
0x1800430a2  cmp     cs:g_fVelocityZtdns, 0
0x1800430a9  jz      loc_1800432C0
0x1800430af  cmp     cs:?g_fForwarderRunning@@3HA, 0; int g_fForwarderRunning
0x1800430b6  jz      short loc_1800430BD
0x1800430b8  call    DnsFwStop
0x1800430bd  lea     rcx, ?g_QueryContextListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800430c4  call    cs:__imp_EnterCriticalSection
0x1800430ca  lea     r8, ?g_QueryContextList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueryContextList
0x1800430d1  mov     rax, cs:?g_QueryContextList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueryContextList
0x1800430d8  cmp     rax, r8
0x1800430db  jz      short loc_180043133
0x1800430dd  cmp     [rax+8], r8
0x1800430e1  jnz     loc_18004327C
0x1800430e7  mov     rcx, [rax]
0x1800430ea  cmp     [rcx+8], rax
0x1800430ee  jnz     loc_18004327C
0x1800430f4  mov     cs:?g_QueryContextList@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY g_QueryContextList
0x1800430fb  mov     [rcx+8], r8
0x1800430ff  mov     [rax+8], rax
0x180043103  mov     [rax], rax
0x180043106  lock inc dword ptr [rax+20h]
0x18004310a  mov     rcx, [rbp+var_28]
0x18004310e  lea     rdx, [rbp+var_30]
0x180043112  cmp     [rcx], rdx
0x180043115  jnz     loc_18004327C
0x18004311b  add     rax, 10h
0x18004311f  lea     rdx, [rbp+var_30]
0x180043123  mov     [rax+8], rcx
0x180043127  mov     [rax], rdx
0x18004312a  mov     [rcx], rax
0x18004312d  mov     [rbp+var_28], rax
0x180043131  jmp     short loc_1800430D1
0x180043133  lea     rcx, ?g_QueryContextListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004313a  call    cs:__imp_LeaveCriticalSection
0x180043140  mov     rbx, [rbp+var_30]
0x180043144  lea     rax, [rbp+var_30]
0x180043148  cmp     rbx, rax
0x18004314b  jz      short loc_1800431B3
0x18004314d  lea     rax, [rbp+var_30]
0x180043151  cmp     [rbx+8], rax
0x180043155  jnz     loc_18004327C
0x18004315b  mov     rax, [rbx]
0x18004315e  cmp     [rax+8], rbx
0x180043162  jnz     loc_18004327C
0x180043168  mov     [rbp+var_30], rax
0x18004316c  lea     rcx, [rbp+var_30]
0x180043170  mov     [rax+8], rcx
0x180043174  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180043177  mov     [rbx+8], rbx
0x18004317b  mov     [rbx], rbx
0x18004317e  mov     rcx, [rbx+1C0h]; hHandle
0x180043185  call    cs:__imp_WaitForSingleObject
0x18004318b  lea     rcx, [rbx+198h]
0x180043192  call    cs:__imp_DnsCancelQueryRaw
0x180043198  mov     rcx, [rbx+1C8h]; hHandle
0x18004319f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800431a2  call    cs:__imp_WaitForSingleObject
0x1800431a8  lea     rcx, [rbx-10h]; lpMem
0x1800431ac  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x1800431b1  jmp     short loc_180043140
0x1800431b3  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800431ba  call    cs:__imp_EnterCriticalSection
0x1800431c0  lea     r8, ?g_SocketList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SocketList
0x1800431c7  mov     rax, cs:?g_SocketList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SocketList
0x1800431ce  cmp     rax, r8
0x1800431d1  jz      short loc_180043225
0x1800431d3  cmp     [rax+8], r8
0x1800431d7  jnz     loc_18004327C
0x1800431dd  mov     rcx, [rax]
0x1800431e0  cmp     [rcx+8], rax
0x1800431e4  jnz     loc_18004327C
0x1800431ea  mov     cs:?g_SocketList@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY g_SocketList
0x1800431f1  mov     [rcx+8], r8
0x1800431f5  mov     [rax+8], rax
0x1800431f9  mov     [rax], rax
0x1800431fc  lock inc dword ptr [rax+28h]
0x180043200  mov     rcx, [rbp+var_18]
0x180043204  lea     rdx, [rbp+var_20]
0x180043208  cmp     [rcx], rdx
0x18004320b  jnz     short loc_18004327C
0x18004320d  add     rax, 10h
0x180043211  lea     rdx, [rbp+var_20]
0x180043215  mov     [rax+8], rcx
0x180043219  mov     [rax], rdx
0x18004321c  mov     [rcx], rax
0x18004321f  mov     [rbp+var_18], rax
0x180043223  jmp     short loc_1800431C7
0x180043225  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004322c  call    cs:__imp_LeaveCriticalSection
0x180043232  mov     rbx, [rbp+var_20]
0x180043236  lea     rax, [rbp+var_20]
0x18004323a  cmp     rbx, rax
0x18004323d  jz      short loc_180043283
0x18004323f  lea     rax, [rbp+var_20]
0x180043243  cmp     [rbx+8], rax
0x180043247  jnz     short loc_18004327C
0x180043249  mov     rax, [rbx]
0x18004324c  cmp     [rax+8], rbx
0x180043250  jnz     short loc_18004327C
0x180043252  mov     [rbp+var_20], rax
0x180043256  lea     rcx, [rbp+var_20]
0x18004325a  mov     [rax+8], rcx
0x18004325e  xor     edx, edx; fCancelPendingCallbacks
0x180043260  mov     [rbx+8], rbx
0x180043264  mov     [rbx], rbx
0x180043267  mov     rcx, [rbx+38h]; pio
0x18004326b  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180043271  lea     rcx, [rbx-10h]; lpMem
0x180043275  call    ?DnsFwDerefSocket@@YAXPEAU_DNS_FORWARD_SOCKET@@@Z; DnsFwDerefSocket(_DNS_FORWARD_SOCKET *)
0x18004327a  jmp     short loc_180043232
0x18004327c  mov     ecx, 3
0x180043281  int     29h; Win8: RtlFailFast(ecx)
0x180043283  cmp     cs:?g_fWinsockStarted@@3HA, 0; int g_fWinsockStarted
0x18004328a  jz      short loc_18004329C
0x18004328c  call    cs:__imp_WSACleanup
0x180043292  mov     cs:?g_fWinsockStarted@@3HA, 0; int g_fWinsockStarted
0x18004329c  lea     rcx, ?g_QueryContextListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800432a3  call    cs:__imp_DeleteCriticalSection
0x1800432a9  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800432b0  call    cs:__imp_DeleteCriticalSection
0x1800432b6  mov     cs:?g_fInitialized@@3HA, 0; int g_fInitialized
0x1800432c0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800432c7  jz      short loc_1800432DF
0x1800432c9  mov     edx, 33h ; '3'
0x1800432ce  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800432d5  mov     ecx, 40Bh
0x1800432da  call    WPP_SF_
0x1800432df  mov     rcx, [rbp+var_10]
0x1800432e3  xor     rcx, rsp; StackCookie
0x1800432e6  call    __security_check_cookie
0x1800432eb  mov     rbx, [rsp+50h+arg_0]
0x1800432f0  add     rsp, 50h
0x1800432f4  pop     rbp
0x1800432f5  retn
```
