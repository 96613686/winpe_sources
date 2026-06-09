# DhcpFSMModuleCleanup

- ea: `0x1800a3b60`
- end: `0x1800a3ed2`
- name: `DhcpFSMModuleCleanup`
- size: `882`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800a1004`
- `0x1800a1ce4`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x1800962b0`
- `0x1800a3b60`
- `0x1800af304`
- `0x1800bf348`
- `0x1800cc9e4`
- `0x1800cdac0`

## import_xrefs

- `WS2_32!WSASetEvent` at `0x1800a3bc6`
- `WS2_32!WSASetEvent` at `0x1800a3c8b`
- `WS2_32!WSASetEvent` at `0x1800a3cce`
- `WS2_32!WSASetEvent` at `0x1800a3d11`
- `WS2_32!WSASetEvent` at `0x1800a3bc6`
- `WS2_32!WSASetEvent` at `0x1800a3c8b`
- `WS2_32!WSASetEvent` at `0x1800a3cce`
- `WS2_32!WSASetEvent` at `0x1800a3d11`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3bd6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3c1c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3c9b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3cde`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3d21`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3db4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3bd6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3c1c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3c9b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3cde`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3d21`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a3db4`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a3d7f`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a3d7f`
- `KERNEL32!WaitForSingleObject` at `0x1800a3c0c`
- `KERNEL32!WaitForSingleObject` at `0x1800a3c0c`
- `KERNEL32!DeleteCriticalSection` at `0x1800a3e3f`
- `KERNEL32!DeleteCriticalSection` at `0x1800a3e81`
- `KERNEL32!DeleteCriticalSection` at `0x1800a3e3f`
- `KERNEL32!DeleteCriticalSection` at `0x1800a3e81`
- `KERNEL32!HeapFree` at `0x1800a3e9d`
- `KERNEL32!HeapFree` at `0x1800a3e9d`

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
      *(_QWORD *)p_LockCount = 0;
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
0x1800a3b60  mov     [rsp+arg_0], rbx
0x1800a3b65  mov     [rsp+arg_8], rbp
0x1800a3b6a  push    rsi
0x1800a3b6b  sub     rsp, 40h
0x1800a3b6f  mov     rax, cs:__security_cookie
0x1800a3b76  xor     rax, rsp
0x1800a3b79  mov     [rsp+48h+var_10], rax
0x1800a3b7e  xor     eax, eax
0x1800a3b80  xorps   xmm0, xmm0
0x1800a3b83  mov     [rsp+48h+var_18], rax
0x1800a3b88  mov     rax, cs:g_FailoverEndpoints
0x1800a3b8f  movups  xmmword ptr [rsp+48h+Handles], xmm0
0x1800a3b94  test    rax, rax
0x1800a3b97  jz      loc_1800A3EB4
0x1800a3b9d  test    byte ptr [rax+28h], 2
0x1800a3ba1  lea     rsi, WPP_GLOBAL_Control
0x1800a3ba8  mov     ebx, 800000h
0x1800a3bad  lea     rbp, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a3bb4  jz      loc_1800A3C75
0x1800a3bba  mov     rcx, cs:gTerminateCMThreadEvent; hEvent
0x1800a3bc1  test    rcx, rcx
0x1800a3bc4  jz      short loc_1800A3BFD
0x1800a3bc6  call    cs:__imp_WSASetEvent
0x1800a3bcd  nop     dword ptr [rax+rax+00h]
0x1800a3bd2  test    eax, eax
0x1800a3bd4  jnz     short loc_1800A3BFD
0x1800a3bd6  call    cs:__imp_WSAGetLastError
0x1800a3bdd  nop     dword ptr [rax+rax+00h]
0x1800a3be2  mov     r9d, 1946h
0x1800a3be8  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a3bef  mov     ecx, eax
0x1800a3bf1  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a3bf8  call    DhcpPrintFOErrorEx
0x1800a3bfd  mov     rcx, cs:gTerminateCMThreadCompleteEvent; hHandle
0x1800a3c04  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a3c07  mov     [rsp+48h+Handles], rcx
0x1800a3c0c  call    cs:__imp_WaitForSingleObject
0x1800a3c13  nop     dword ptr [rax+rax+00h]
0x1800a3c18  test    eax, eax
0x1800a3c1a  jz      short loc_1800A3C40
0x1800a3c1c  call    cs:__imp_WSAGetLastError
0x1800a3c23  nop     dword ptr [rax+rax+00h]
0x1800a3c28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3c2f  cmp     rcx, rsi
0x1800a3c32  jz      short loc_1800A3C6A
0x1800a3c34  test    [rcx+1Ch], ebx
0x1800a3c37  jz      short loc_1800A3C6A
0x1800a3c39  mov     edx, 0E1h
0x1800a3c3e  jmp     short loc_1800A3C5B
0x1800a3c40  call    DhcpCMCleanup
0x1800a3c45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3c4c  cmp     rcx, rsi
0x1800a3c4f  jz      short loc_1800A3C6A
0x1800a3c51  test    [rcx+1Ch], ebx
0x1800a3c54  jz      short loc_1800A3C6A
0x1800a3c56  mov     edx, 0E2h
0x1800a3c5b  mov     rcx, [rcx+10h]
0x1800a3c5f  mov     r9d, eax
0x1800a3c62  mov     r8, rbp
0x1800a3c65  call    WPP_SF_D
0x1800a3c6a  mov     rax, cs:g_FailoverEndpoints
0x1800a3c71  and     dword ptr [rax+28h], 0FFFFFFFDh
0x1800a3c75  test    byte ptr [rax+28h], 1
0x1800a3c79  jz      loc_1800A3DF0
0x1800a3c7f  mov     rcx, cs:gTerminateBndRecvThreadEvent; hEvent
0x1800a3c86  test    rcx, rcx
0x1800a3c89  jz      short loc_1800A3CC2
0x1800a3c8b  call    cs:__imp_WSASetEvent
0x1800a3c92  nop     dword ptr [rax+rax+00h]
0x1800a3c97  test    eax, eax
0x1800a3c99  jnz     short loc_1800A3CC2
0x1800a3c9b  call    cs:__imp_WSAGetLastError
0x1800a3ca2  nop     dword ptr [rax+rax+00h]
0x1800a3ca7  mov     r9d, 195Bh
0x1800a3cad  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a3cb4  mov     ecx, eax
0x1800a3cb6  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a3cbd  call    DhcpPrintFOErrorEx
0x1800a3cc2  mov     rcx, cs:gTerminateBndSendThreadEvent; hEvent
0x1800a3cc9  test    rcx, rcx
0x1800a3ccc  jz      short loc_1800A3D05
0x1800a3cce  call    cs:__imp_WSASetEvent
0x1800a3cd5  nop     dword ptr [rax+rax+00h]
0x1800a3cda  test    eax, eax
0x1800a3cdc  jnz     short loc_1800A3D05
0x1800a3cde  call    cs:__imp_WSAGetLastError
0x1800a3ce5  nop     dword ptr [rax+rax+00h]
0x1800a3cea  mov     r9d, 195Ch
0x1800a3cf0  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a3cf7  mov     ecx, eax
0x1800a3cf9  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a3d00  call    DhcpPrintFOErrorEx
0x1800a3d05  mov     rcx, cs:gTerminateBndCoreThreadEvent; hEvent
0x1800a3d0c  test    rcx, rcx
0x1800a3d0f  jz      short loc_1800A3D48
0x1800a3d11  call    cs:__imp_WSASetEvent
0x1800a3d18  nop     dword ptr [rax+rax+00h]
0x1800a3d1d  test    eax, eax
0x1800a3d1f  jnz     short loc_1800A3D48
0x1800a3d21  call    cs:__imp_WSAGetLastError
0x1800a3d28  nop     dword ptr [rax+rax+00h]
0x1800a3d2d  mov     r9d, 195Dh
0x1800a3d33  lea     r8, aWsasetevent; "WSASetEvent"
0x1800a3d3a  mov     ecx, eax
0x1800a3d3c  lea     rdx, aDhcpfsmmodulec; "DhcpFSMModuleCleanup"
0x1800a3d43  call    DhcpPrintFOErrorEx
0x1800a3d48  mov     rax, cs:gTerminateBndRecvThreadCompleteEvent
0x1800a3d4f  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800a3d54  mov     [rsp+48h+Handles], rax
0x1800a3d59  mov     r8d, 1; bWaitAll
0x1800a3d5f  mov     rax, cs:gTerminateBndSendThreadCompleteEvent
0x1800a3d66  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a3d6a  mov     [rsp+48h+Handles+8], rax
0x1800a3d6f  mov     rax, cs:gTerminateBndCoreThreadCompleteEvent
0x1800a3d76  lea     ecx, [r8+2]; nCount
0x1800a3d7a  mov     [rsp+48h+var_18], rax
0x1800a3d7f  call    cs:__imp_WaitForMultipleObjects
0x1800a3d86  nop     dword ptr [rax+rax+00h]
0x1800a3d8b  cmp     eax, 0FFFFFFFFh
0x1800a3d8e  jz      short loc_1800A3DB4
0x1800a3d90  cmp     eax, 102h
0x1800a3d95  jz      short loc_1800A3DB4
0x1800a3d97  call    DhcpBNDCleanup
0x1800a3d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3da3  cmp     rcx, rsi
0x1800a3da6  jz      short loc_1800A3DE5
0x1800a3da8  test    [rcx+1Ch], ebx
0x1800a3dab  jz      short loc_1800A3DE5
0x1800a3dad  mov     edx, 0E4h
0x1800a3db2  jmp     short loc_1800A3DD6
0x1800a3db4  call    cs:__imp_WSAGetLastError
0x1800a3dbb  nop     dword ptr [rax+rax+00h]
0x1800a3dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3dc7  cmp     rcx, rsi
0x1800a3dca  jz      short loc_1800A3DE5
0x1800a3dcc  test    [rcx+1Ch], ebx
0x1800a3dcf  jz      short loc_1800A3DE5
0x1800a3dd1  mov     edx, 0E3h
0x1800a3dd6  mov     rcx, [rcx+10h]
0x1800a3dda  mov     r9d, eax
0x1800a3ddd  mov     r8, rbp
0x1800a3de0  call    WPP_SF_D
0x1800a3de5  mov     rax, cs:g_FailoverEndpoints
0x1800a3dec  and     dword ptr [rax+28h], 0FFFFFFFEh
0x1800a3df0  test    byte ptr [rax+28h], 4
0x1800a3df4  jz      short loc_1800A3E32
0x1800a3df6  mov     rcx, cs:gFailoverFreePacketPool; lpMem
0x1800a3dfd  call    MessageQCleanup
0x1800a3e02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3e09  cmp     rcx, rsi
0x1800a3e0c  jz      short loc_1800A3E27
0x1800a3e0e  test    [rcx+1Ch], ebx
0x1800a3e11  jz      short loc_1800A3E27
0x1800a3e13  mov     rcx, [rcx+10h]
0x1800a3e17  mov     edx, 0E5h
0x1800a3e1c  mov     r9d, eax
0x1800a3e1f  mov     r8, rbp
0x1800a3e22  call    WPP_SF_D
0x1800a3e27  mov     rax, cs:g_FailoverEndpoints
0x1800a3e2e  and     dword ptr [rax+28h], 0FFFFFFFBh
0x1800a3e32  test    byte ptr [rax+28h], 8
0x1800a3e36  jz      short loc_1800A3EB4
0x1800a3e38  lea     rcx, gXidCS; lpCriticalSection
0x1800a3e3f  call    cs:__imp_DeleteCriticalSection
0x1800a3e46  nop     dword ptr [rax+rax+00h]
0x1800a3e4b  mov     rcx, cs:g_FailoverEndpoints
0x1800a3e52  lea     rbx, [rcx+30h]
0x1800a3e56  test    rbx, rbx
0x1800a3e59  jz      short loc_1800A3E81
0x1800a3e5b  cmp     qword ptr [rbx+8], 0
0x1800a3e60  jz      short loc_1800A3E72
0x1800a3e62  mov     rcx, [rbx+8]; lpMem
0x1800a3e66  call    MemFree
0x1800a3e6b  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a3e72  mov     qword ptr [rbx], 0
0x1800a3e79  mov     qword ptr [rbx+8], 0
0x1800a3e81  call    cs:__imp_DeleteCriticalSection
0x1800a3e88  nop     dword ptr [rax+rax+00h]
0x1800a3e8d  mov     r8, cs:g_FailoverEndpoints; lpMem
0x1800a3e94  xor     edx, edx; dwFlags
0x1800a3e96  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a3e9d  call    cs:__imp_HeapFree
0x1800a3ea4  nop     dword ptr [rax+rax+00h]
0x1800a3ea9  mov     cs:g_FailoverEndpoints, 0
0x1800a3eb4  mov     rcx, [rsp+48h+var_10]
0x1800a3eb9  xor     rcx, rsp; StackCookie
0x1800a3ebc  call    __security_check_cookie
0x1800a3ec1  mov     rbx, [rsp+48h+arg_0]
0x1800a3ec6  mov     rbp, [rsp+48h+arg_8]
0x1800a3ecb  add     rsp, 40h
0x1800a3ecf  pop     rsi
0x1800a3ed0  retn
```
