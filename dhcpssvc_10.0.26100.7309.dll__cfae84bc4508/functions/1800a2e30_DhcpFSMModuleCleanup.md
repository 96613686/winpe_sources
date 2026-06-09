# DhcpFSMModuleCleanup

- ea: `0x1800a2e30`
- end: `0x1800a319c`
- name: `DhcpFSMModuleCleanup`
- size: `876`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800a032c`
- `0x1800a0ff0`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x180096080`
- `0x1800a2e30`
- `0x1800ae550`
- `0x1800be358`
- `0x1800cb938`
- `0x1800cc9e0`

## import_xrefs

- `WS2_32!WSASetEvent` at `0x1800a2e96`
- `WS2_32!WSASetEvent` at `0x1800a2f5b`
- `WS2_32!WSASetEvent` at `0x1800a2f9e`
- `WS2_32!WSASetEvent` at `0x1800a2fe1`
- `WS2_32!WSASetEvent` at `0x1800a2e96`
- `WS2_32!WSASetEvent` at `0x1800a2f5b`
- `WS2_32!WSASetEvent` at `0x1800a2f9e`
- `WS2_32!WSASetEvent` at `0x1800a2fe1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2ea6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2eec`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2f6b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2fae`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2ff1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3084`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2ea6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2eec`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2f6b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2fae`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a2ff1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3084`
- `KERNEL32!WaitForSingleObject` at `0x1800a2edc`
- `KERNEL32!WaitForSingleObject` at `0x1800a2edc`
- `KERNEL32!DeleteCriticalSection` at `0x1800a310f`
- `KERNEL32!DeleteCriticalSection` at `0x1800a314e`
- `KERNEL32!DeleteCriticalSection` at `0x1800a310f`
- `KERNEL32!DeleteCriticalSection` at `0x1800a314e`
- `KERNEL32!HeapFree` at `0x1800a316a`
- `KERNEL32!HeapFree` at `0x1800a316a`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a304f`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a304f`

## pseudocode

```c
int DhcpFSMModuleCleanup()
{
  LPCRITICAL_SECTION v0; // rax
  unsigned int Error; // eax
  unsigned int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  DWORD v8; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  LONG *p_LockCount; // rbx
  HANDLE Handles[2]; // [rsp+20h] [rbp-28h] BYREF
  HANDLE v17; // [rsp+30h] [rbp-18h]

  v17 = 0;
  v0 = g_FailoverEndpoints;
  *(_OWORD *)Handles = 0;
  if ( !g_FailoverEndpoints )
    return (int)v0;
  if ( ((__int64)g_FailoverEndpoints[1].DebugInfo & 2) != 0 )
  {
    if ( gTerminateCMThreadEvent && !WSASetEvent(gTerminateCMThreadEvent) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpFSMModuleCleanup", "WSASetEvent", 6470);
    }
    Handles[0] = gTerminateCMThreadCompleteEvent;
    if ( WaitForSingleObject(gTerminateCMThreadCompleteEvent, 0xFFFFFFFF) )
    {
      v2 = WSAGetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_14;
      }
      v4 = 225;
    }
    else
    {
      v2 = DhcpCMCleanup();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_14;
      }
      v4 = 226;
    }
    WPP_SF_D(v3[2], v4, &WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids, v2);
LABEL_14:
    v0 = g_FailoverEndpoints;
    LODWORD(g_FailoverEndpoints[1].DebugInfo) &= ~2u;
  }
  if ( ((__int64)v0[1].DebugInfo & 1) != 0 )
  {
    if ( gTerminateBndRecvThreadEvent && !WSASetEvent(gTerminateBndRecvThreadEvent) )
    {
      v5 = WSAGetLastError();
      DhcpPrintFOErrorEx(v5, "DhcpFSMModuleCleanup", "WSASetEvent", 6491);
    }
    if ( gTerminateBndSendThreadEvent && !WSASetEvent(gTerminateBndSendThreadEvent) )
    {
      v6 = WSAGetLastError();
      DhcpPrintFOErrorEx(v6, "DhcpFSMModuleCleanup", "WSASetEvent", 6492);
    }
    if ( gTerminateBndCoreThreadEvent && !WSASetEvent(gTerminateBndCoreThreadEvent) )
    {
      v7 = WSAGetLastError();
      DhcpPrintFOErrorEx(v7, "DhcpFSMModuleCleanup", "WSASetEvent", 6493);
    }
    Handles[0] = gTerminateBndRecvThreadCompleteEvent;
    Handles[1] = gTerminateBndSendThreadCompleteEvent;
    v17 = gTerminateBndCoreThreadCompleteEvent;
    v8 = WaitForMultipleObjects(3u, Handles, 1, 0xFFFFFFFF);
    if ( v8 == -1 || v8 == 258 )
    {
      v9 = WSAGetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_34;
      }
      v11 = 227;
    }
    else
    {
      v9 = DhcpBNDCleanup();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_34;
      }
      v11 = 228;
    }
    WPP_SF_D(v10[2], v11, &WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids, v9);
LABEL_34:
    v0 = g_FailoverEndpoints;
    LODWORD(g_FailoverEndpoints[1].DebugInfo) &= ~1u;
  }
  if ( ((__int64)v0[1].DebugInfo & 4) != 0 )
  {
    v12 = MessageQCleanup(gFailoverFreePacketPool);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids, v12);
    v0 = g_FailoverEndpoints;
    LODWORD(g_FailoverEndpoints[1].DebugInfo) &= ~4u;
  }
  if ( ((__int64)v0[1].DebugInfo & 8) != 0 )
  {
    DeleteCriticalSection(&gXidCS);
    v13 = g_FailoverEndpoints;
    p_LockCount = &g_FailoverEndpoints[1].LockCount;
    if ( g_FailoverEndpoints != (LPCRITICAL_SECTION)-48LL )
    {
      if ( g_FailoverEndpoints[1].OwningThread )
      {
        MemFree(g_FailoverEndpoints[1].OwningThread);
        v13 = g_FailoverEndpoints;
      }
      p_LockCount[1] = 0;
      *p_LockCount = 0;
      *((_QWORD *)p_LockCount + 1) = 0;
    }
    DeleteCriticalSection(v13);
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, g_FailoverEndpoints);
    g_FailoverEndpoints = 0;
  }
  return (int)v0;
}

```

## disassembly

```asm
0x1800a2e30  mov     [rsp+arg_0], rbx
0x1800a2e35  mov     [rsp+arg_8], rbp
0x1800a2e3a  push    rsi
0x1800a2e3b  sub     rsp, 40h
0x1800a2e3f  mov     rax, cs:__security_cookie
0x1800a2e46  xor     rax, rsp
0x1800a2e49  mov     [rsp+48h+var_10], rax
0x1800a2e4e  xor     eax, eax
0x1800a2e50  xorps   xmm0, xmm0
0x1800a2e53  mov     [rsp+48h+var_18], rax
0x1800a2e58  mov     rax, cs:g_FailoverEndpoints
0x1800a2e5f  movups  xmmword ptr [rsp+48h+Handles], xmm0
0x1800a2e64  test    rax, rax
0x1800a2e67  jz      loc_1800A317E
0x1800a2e6d  test    byte ptr [rax+28h], 2
0x1800a2e71  lea     rsi, WPP_GLOBAL_Control
0x1800a2e78  mov     ebx, 800000h
0x1800a2e7d  lea     rbp, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a2e84  jz      loc_1800A2F45
0x1800a2e8a  mov     rcx, cs:gTerminateCMThreadEvent; hEvent
0x1800a2e91  test    rcx, rcx
0x1800a2e94  jz      short loc_1800A2ECD
0x1800a2e96  call    cs:__imp_WSASetEvent
0x1800a2e9d  nop     dword ptr [rax+rax+00h]
0x1800a2ea2  test    eax, eax
0x1800a2ea4  jnz     short loc_1800A2ECD
0x1800a2ea6  call    cs:__imp_WSAGetLastError
0x1800a2ead  nop     dword ptr [rax+rax+00h]
0x1800a2eb2  mov     r9d, 1946h
0x1800a2eb8  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a2ebf  mov     ecx, eax
0x1800a2ec1  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a2ec8  call    DhcpPrintFOErrorEx
0x1800a2ecd  mov     rcx, cs:gTerminateCMThreadCompleteEvent; hHandle
0x1800a2ed4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a2ed7  mov     [rsp+48h+Handles], rcx
0x1800a2edc  call    cs:__imp_WaitForSingleObject
0x1800a2ee3  nop     dword ptr [rax+rax+00h]
0x1800a2ee8  test    eax, eax
0x1800a2eea  jz      short loc_1800A2F10
0x1800a2eec  call    cs:__imp_WSAGetLastError
0x1800a2ef3  nop     dword ptr [rax+rax+00h]
0x1800a2ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2eff  cmp     rcx, rsi
0x1800a2f02  jz      short loc_1800A2F3A
0x1800a2f04  test    [rcx+1Ch], ebx
0x1800a2f07  jz      short loc_1800A2F3A
0x1800a2f09  mov     edx, 0E1h
0x1800a2f0e  jmp     short loc_1800A2F2B
0x1800a2f10  call    DhcpCMCleanup
0x1800a2f15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2f1c  cmp     rcx, rsi
0x1800a2f1f  jz      short loc_1800A2F3A
0x1800a2f21  test    [rcx+1Ch], ebx
0x1800a2f24  jz      short loc_1800A2F3A
0x1800a2f26  mov     edx, 0E2h
0x1800a2f2b  mov     rcx, [rcx+10h]
0x1800a2f2f  mov     r9d, eax
0x1800a2f32  mov     r8, rbp
0x1800a2f35  call    WPP_SF_D
0x1800a2f3a  mov     rax, cs:g_FailoverEndpoints
0x1800a2f41  and     dword ptr [rax+28h], 0FFFFFFFDh
0x1800a2f45  test    byte ptr [rax+28h], 1
0x1800a2f49  jz      loc_1800A30C0
0x1800a2f4f  mov     rcx, cs:gTerminateBndRecvThreadEvent; hEvent
0x1800a2f56  test    rcx, rcx
0x1800a2f59  jz      short loc_1800A2F92
0x1800a2f5b  call    cs:__imp_WSASetEvent
0x1800a2f62  nop     dword ptr [rax+rax+00h]
0x1800a2f67  test    eax, eax
0x1800a2f69  jnz     short loc_1800A2F92
0x1800a2f6b  call    cs:__imp_WSAGetLastError
0x1800a2f72  nop     dword ptr [rax+rax+00h]
0x1800a2f77  mov     r9d, 195Bh
0x1800a2f7d  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a2f84  mov     ecx, eax
0x1800a2f86  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a2f8d  call    DhcpPrintFOErrorEx
0x1800a2f92  mov     rcx, cs:gTerminateBndSendThreadEvent; hEvent
0x1800a2f99  test    rcx, rcx
0x1800a2f9c  jz      short loc_1800A2FD5
0x1800a2f9e  call    cs:__imp_WSASetEvent
0x1800a2fa5  nop     dword ptr [rax+rax+00h]
0x1800a2faa  test    eax, eax
0x1800a2fac  jnz     short loc_1800A2FD5
0x1800a2fae  call    cs:__imp_WSAGetLastError
0x1800a2fb5  nop     dword ptr [rax+rax+00h]
0x1800a2fba  mov     r9d, 195Ch
0x1800a2fc0  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a2fc7  mov     ecx, eax
0x1800a2fc9  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a2fd0  call    DhcpPrintFOErrorEx
0x1800a2fd5  mov     rcx, cs:gTerminateBndCoreThreadEvent; hEvent
0x1800a2fdc  test    rcx, rcx
0x1800a2fdf  jz      short loc_1800A3018
0x1800a2fe1  call    cs:__imp_WSASetEvent
0x1800a2fe8  nop     dword ptr [rax+rax+00h]
0x1800a2fed  test    eax, eax
0x1800a2fef  jnz     short loc_1800A3018
0x1800a2ff1  call    cs:__imp_WSAGetLastError
0x1800a2ff8  nop     dword ptr [rax+rax+00h]
0x1800a2ffd  mov     r9d, 195Dh
0x1800a3003  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a300a  mov     ecx, eax
0x1800a300c  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a3013  call    DhcpPrintFOErrorEx
0x1800a3018  mov     rax, cs:gTerminateBndRecvThreadCompleteEvent
0x1800a301f  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800a3024  mov     [rsp+48h+Handles], rax
0x1800a3029  mov     r8d, 1; bWaitAll
0x1800a302f  mov     rax, cs:gTerminateBndSendThreadCompleteEvent
0x1800a3036  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a303a  mov     [rsp+48h+Handles+8], rax
0x1800a303f  mov     rax, cs:gTerminateBndCoreThreadCompleteEvent
0x1800a3046  lea     ecx, [r8+2]; nCount
0x1800a304a  mov     [rsp+48h+var_18], rax
0x1800a304f  call    cs:__imp_WaitForMultipleObjects
0x1800a3056  nop     dword ptr [rax+rax+00h]
0x1800a305b  cmp     eax, 0FFFFFFFFh
0x1800a305e  jz      short loc_1800A3084
0x1800a3060  cmp     eax, 102h
0x1800a3065  jz      short loc_1800A3084
0x1800a3067  call    DhcpBNDCleanup
0x1800a306c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3073  cmp     rcx, rsi
0x1800a3076  jz      short loc_1800A30B5
0x1800a3078  test    [rcx+1Ch], ebx
0x1800a307b  jz      short loc_1800A30B5
0x1800a307d  mov     edx, 0E4h
0x1800a3082  jmp     short loc_1800A30A6
0x1800a3084  call    cs:__imp_WSAGetLastError
0x1800a308b  nop     dword ptr [rax+rax+00h]
0x1800a3090  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3097  cmp     rcx, rsi
0x1800a309a  jz      short loc_1800A30B5
0x1800a309c  test    [rcx+1Ch], ebx
0x1800a309f  jz      short loc_1800A30B5
0x1800a30a1  mov     edx, 0E3h
0x1800a30a6  mov     rcx, [rcx+10h]
0x1800a30aa  mov     r9d, eax
0x1800a30ad  mov     r8, rbp
0x1800a30b0  call    WPP_SF_D
0x1800a30b5  mov     rax, cs:g_FailoverEndpoints
0x1800a30bc  and     dword ptr [rax+28h], 0FFFFFFFEh
0x1800a30c0  test    byte ptr [rax+28h], 4
0x1800a30c4  jz      short loc_1800A3102
0x1800a30c6  mov     rcx, cs:gFailoverFreePacketPool; lpMem
0x1800a30cd  call    MessageQCleanup
0x1800a30d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a30d9  cmp     rcx, rsi
0x1800a30dc  jz      short loc_1800A30F7
0x1800a30de  test    [rcx+1Ch], ebx
0x1800a30e1  jz      short loc_1800A30F7
0x1800a30e3  mov     rcx, [rcx+10h]
0x1800a30e7  mov     edx, 0E5h
0x1800a30ec  mov     r9d, eax
0x1800a30ef  mov     r8, rbp
0x1800a30f2  call    WPP_SF_D
0x1800a30f7  mov     rax, cs:g_FailoverEndpoints
0x1800a30fe  and     dword ptr [rax+28h], 0FFFFFFFBh
0x1800a3102  test    byte ptr [rax+28h], 8
0x1800a3106  jz      short loc_1800A317E
0x1800a3108  lea     rcx, gXidCS; lpCriticalSection
0x1800a310f  call    cs:__imp_DeleteCriticalSection
0x1800a3116  nop     dword ptr [rax+rax+00h]
0x1800a311b  mov     rcx, cs:g_FailoverEndpoints
0x1800a3122  lea     rbx, [rcx+30h]
0x1800a3126  test    rbx, rbx
0x1800a3129  jz      short loc_1800A314E
0x1800a312b  cmp     qword ptr [rbx+8], 0
0x1800a3130  jz      short loc_1800A3142
0x1800a3132  mov     rcx, [rbx+8]; lpMem
0x1800a3136  call    MemFree
0x1800a313b  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a3142  and     dword ptr [rbx+4], 0
0x1800a3146  and     dword ptr [rbx], 0
0x1800a3149  and     qword ptr [rbx+8], 0
0x1800a314e  call    cs:__imp_DeleteCriticalSection
0x1800a3155  nop     dword ptr [rax+rax+00h]
0x1800a315a  mov     r8, cs:g_FailoverEndpoints; lpMem
0x1800a3161  xor     edx, edx; dwFlags
0x1800a3163  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a316a  call    cs:__imp_HeapFree
0x1800a3171  nop     dword ptr [rax+rax+00h]
0x1800a3176  and     cs:g_FailoverEndpoints, 0
0x1800a317e  mov     rcx, [rsp+48h+var_10]
0x1800a3183  xor     rcx, rsp; StackCookie
0x1800a3186  call    __security_check_cookie
0x1800a318b  mov     rbx, [rsp+48h+arg_0]
0x1800a3190  mov     rbp, [rsp+48h+arg_8]
0x1800a3195  add     rsp, 40h
0x1800a3199  pop     rsi
0x1800a319a  retn
```
