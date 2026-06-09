# NotifyServiceThreadsToTerminate(void)

- ea: `0x140047edc`
- end: `0x1400480e8`
- name: `?NotifyServiceThreadsToTerminate@@YAHXZ`
- size: `524`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140046a7c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140047edc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140047f4a`
- `KERNEL32!GetLastError` at `0x140047fa9`
- `KERNEL32!GetLastError` at `0x140048002`
- `KERNEL32!GetLastError` at `0x14004805f`
- `KERNEL32!GetLastError` at `0x1400480b8`
- `KERNEL32!GetLastError` at `0x140047f4a`
- `KERNEL32!GetLastError` at `0x140047fa9`
- `KERNEL32!GetLastError` at `0x140048002`
- `KERNEL32!GetLastError` at `0x14004805f`
- `KERNEL32!GetLastError` at `0x1400480b8`
- `KERNEL32!SetEvent` at `0x140047f28`
- `KERNEL32!SetEvent` at `0x140047f28`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140047f87`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140047fe0`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004803d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140048096`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140047f87`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140047fe0`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004803d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140048096`

## pseudocode

```c
__int64 NotifyServiceThreadsToTerminate(void)
{
  unsigned int v0; // ebx
  DWORD LastError; // eax
  DWORD v2; // eax
  DWORD v3; // eax
  void *v4; // rcx
  DWORD v5; // eax
  DWORD v6; // eax

  v0 = 1;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( !SetEvent(g_hServiceShutDownEvent) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
    }
    v0 = 0;
  }
  if ( g_hSendEventsCompPort && !PostQueuedCompletionStatus(g_hSendEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v2);
    }
    v0 = 0;
  }
  if ( g_hDispatchEventsCompPort && !PostQueuedCompletionStatus(g_hDispatchEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v3);
    }
    v0 = 0;
  }
  v4 = (void *)*((_QWORD *)g_pNotificationMap + 1);
  if ( v4 && !PostQueuedCompletionStatus(v4, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v5);
    }
    v0 = 0;
  }
  if ( g_StatusCompletionPortHandle && !PostQueuedCompletionStatus(g_StatusCompletionPortHandle, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v6);
    }
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x140047edc  push    rbx
0x140047ede  push    rsi
0x140047edf  push    r14
0x140047ee1  push    r15
0x140047ee3  sub     rsp, 28h
0x140047ee7  mov     ebx, 1
0x140047eec  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ef3  lea     rsi, WPP_GLOBAL_Control
0x140047efa  lea     r14, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140047f01  cmp     rcx, rsi
0x140047f04  jz      short loc_140047F21
0x140047f06  test    byte ptr [rcx+1Ch], 4
0x140047f0a  jz      short loc_140047F21
0x140047f0c  cmp     byte ptr [rcx+19h], 5
0x140047f10  jb      short loc_140047F21
0x140047f12  mov     rcx, [rcx+10h]
0x140047f16  lea     edx, [rbx+2Dh]
0x140047f19  mov     r8, r14
0x140047f1c  call    WPP_SF_
0x140047f21  mov     rcx, cs:?g_hServiceShutDownEvent@@3PEAXEA; hEvent
0x140047f28  call    cs:__imp_SetEvent
0x140047f2e  test    eax, eax
0x140047f30  jnz     short loc_140047F6D
0x140047f32  mov     rax, cs:WPP_GLOBAL_Control
0x140047f39  cmp     rax, rsi
0x140047f3c  jz      short loc_140047F6B
0x140047f3e  test    byte ptr [rax+1Ch], 4
0x140047f42  jz      short loc_140047F6B
0x140047f44  cmp     byte ptr [rax+19h], 2
0x140047f48  jb      short loc_140047F6B
0x140047f4a  call    cs:__imp_GetLastError
0x140047f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f57  mov     edx, 2Fh ; '/'
0x140047f5c  mov     r9d, eax
0x140047f5f  mov     r8, r14
0x140047f62  mov     rcx, [rcx+10h]
0x140047f66  call    WPP_SF_d
0x140047f6b  xor     ebx, ebx
0x140047f6d  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x140047f74  mov     r15d, 0FFFFFFFFh
0x140047f7a  test    rcx, rcx
0x140047f7d  jz      short loc_140047FCC
0x140047f7f  xor     r9d, r9d; lpOverlapped
0x140047f82  mov     r8d, r15d; dwCompletionKey
0x140047f85  xor     edx, edx; dwNumberOfBytesTransferred
0x140047f87  call    cs:__imp_PostQueuedCompletionStatus
0x140047f8d  test    eax, eax
0x140047f8f  jnz     short loc_140047FCC
0x140047f91  mov     rax, cs:WPP_GLOBAL_Control
0x140047f98  cmp     rax, rsi
0x140047f9b  jz      short loc_140047FCA
0x140047f9d  test    byte ptr [rax+1Ch], 4
0x140047fa1  jz      short loc_140047FCA
0x140047fa3  cmp     byte ptr [rax+19h], 2
0x140047fa7  jb      short loc_140047FCA
0x140047fa9  call    cs:__imp_GetLastError
0x140047faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140047fb6  mov     edx, 30h ; '0'
0x140047fbb  mov     r9d, eax
0x140047fbe  mov     r8, r14
0x140047fc1  mov     rcx, [rcx+10h]
0x140047fc5  call    WPP_SF_d
0x140047fca  xor     ebx, ebx
0x140047fcc  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x140047fd3  test    rcx, rcx
0x140047fd6  jz      short loc_140048025
0x140047fd8  xor     r9d, r9d; lpOverlapped
0x140047fdb  mov     r8, r15; dwCompletionKey
0x140047fde  xor     edx, edx; dwNumberOfBytesTransferred
0x140047fe0  call    cs:__imp_PostQueuedCompletionStatus
0x140047fe6  test    eax, eax
0x140047fe8  jnz     short loc_140048025
0x140047fea  mov     rax, cs:WPP_GLOBAL_Control
0x140047ff1  cmp     rax, rsi
0x140047ff4  jz      short loc_140048023
0x140047ff6  test    byte ptr [rax+1Ch], 4
0x140047ffa  jz      short loc_140048023
0x140047ffc  cmp     byte ptr [rax+19h], 2
0x140048000  jb      short loc_140048023
0x140048002  call    cs:__imp_GetLastError
0x140048008  mov     rcx, cs:WPP_GLOBAL_Control
0x14004800f  mov     edx, 31h ; '1'
0x140048014  mov     r9d, eax
0x140048017  mov     r8, r14
0x14004801a  mov     rcx, [rcx+10h]
0x14004801e  call    WPP_SF_d
0x140048023  xor     ebx, ebx
0x140048025  mov     rax, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14004802c  mov     rcx, [rax+8]; CompletionPort
0x140048030  test    rcx, rcx
0x140048033  jz      short loc_140048082
0x140048035  xor     r9d, r9d; lpOverlapped
0x140048038  mov     r8, r15; dwCompletionKey
0x14004803b  xor     edx, edx; dwNumberOfBytesTransferred
0x14004803d  call    cs:__imp_PostQueuedCompletionStatus
0x140048043  test    eax, eax
0x140048045  jnz     short loc_140048082
0x140048047  mov     rax, cs:WPP_GLOBAL_Control
0x14004804e  cmp     rax, rsi
0x140048051  jz      short loc_140048080
0x140048053  test    byte ptr [rax+1Ch], 4
0x140048057  jz      short loc_140048080
0x140048059  cmp     byte ptr [rax+19h], 2
0x14004805d  jb      short loc_140048080
0x14004805f  call    cs:__imp_GetLastError
0x140048065  mov     rcx, cs:WPP_GLOBAL_Control
0x14004806c  mov     edx, 32h ; '2'
0x140048071  mov     r9d, eax
0x140048074  mov     r8, r14
0x140048077  mov     rcx, [rcx+10h]
0x14004807b  call    WPP_SF_d
0x140048080  xor     ebx, ebx
0x140048082  mov     rcx, cs:?g_StatusCompletionPortHandle@@3PEAXEA; CompletionPort
0x140048089  test    rcx, rcx
0x14004808c  jz      short loc_1400480DB
0x14004808e  xor     r9d, r9d; lpOverlapped
0x140048091  mov     r8, r15; dwCompletionKey
0x140048094  xor     edx, edx; dwNumberOfBytesTransferred
0x140048096  call    cs:__imp_PostQueuedCompletionStatus
0x14004809c  test    eax, eax
0x14004809e  jnz     short loc_1400480DB
0x1400480a0  mov     rax, cs:WPP_GLOBAL_Control
0x1400480a7  cmp     rax, rsi
0x1400480aa  jz      short loc_1400480D9
0x1400480ac  test    byte ptr [rax+1Ch], 4
0x1400480b0  jz      short loc_1400480D9
0x1400480b2  cmp     byte ptr [rax+19h], 2
0x1400480b6  jb      short loc_1400480D9
0x1400480b8  call    cs:__imp_GetLastError
0x1400480be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400480c5  mov     edx, 33h ; '3'
0x1400480ca  mov     r9d, eax
0x1400480cd  mov     r8, r14
0x1400480d0  mov     rcx, [rcx+10h]
0x1400480d4  call    WPP_SF_d
0x1400480d9  xor     ebx, ebx
0x1400480db  mov     eax, ebx
0x1400480dd  add     rsp, 28h
0x1400480e1  pop     r15
0x1400480e3  pop     r14
0x1400480e5  pop     rsi
0x1400480e6  pop     rbx
0x1400480e7  retn
```
