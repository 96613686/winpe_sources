# SocketIoMonitor::HandleWaitCallback(_TP_CALLBACK_INSTANCE *,long)

- ea: `0x1800278e0`
- end: `0x180027a2f`
- name: `?HandleWaitCallback@SocketIoMonitor@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@J@Z`
- size: `335`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _TP_CALLBACK_INSTANCE *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180027a40`

## callees

- `0x180001ebc`
- `0x18000a0a0`
- `0x18001d8e0`
- `0x1800267d8`
- `0x1800278e0`
- `0x180027c50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027924`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800279cd`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800279d6`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800279d6`
- `WS2_32!WSAEnumNetworkEvents` at `0x180027969`
- `WS2_32!WSAEnumNetworkEvents` at `0x180027969`
- `WS2_32!__imp_WSAGetLastError` at `0x180027974`
- `WS2_32!__imp_WSAGetLastError` at `0x180027974`

## pseudocode

```c
void __fastcall SocketIoMonitor::HandleWaitCallback(
        struct _RTL_CRITICAL_SECTION *this,
        struct _TP_CALLBACK_INSTANCE *a2,
        unsigned int a3)
{
  int v4; // edi
  SocketBrokerContext *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rdx
  SOCKET SpinCount; // rcx
  __int64 v11; // r9
  const wchar_t *v12; // r8
  unsigned int Error; // eax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  _WSANETWORKEVENTS NetworkEvents; // [rsp+20h] [rbp-78h] BYREF

  v4 = 0;
  v7 = 0;
  memset(&NetworkEvents, 0, sizeof(NetworkEvents));
  v8 = 4;
  EnterCriticalSection(this + 1);
  SpinCount = this->SpinCount;
  LOBYTE(this[7].DebugInfo) = 0;
  if ( SpinCount != -1 )
  {
    if ( a3 )
    {
      v4 = a3;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_13;
      v11 = a3;
      v12 = L"HandleWaitCallback: IO Wait Result";
      goto LABEL_5;
    }
    if ( WSAEnumNetworkEvents(SpinCount, this[6].LockSemaphore, &NetworkEvents) == -1 )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v11 = Error;
        v12 = L"HandleWaitCallback: WSAEnumNetworkEvents failed";
LABEL_5:
        McTemplateU0zq_EventWriteTransfer(SpinCount, v9, v12, v11);
      }
    }
    else if ( (NetworkEvents.lNetworkEvents & 0x20) != 0 )
    {
      v4 = NetworkEvents.iErrorCode[5];
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v11 = (unsigned int)NetworkEvents.iErrorCode[5];
        v12 = L"HandleWaitCallback: Socket Closed";
        goto LABEL_5;
      }
    }
    else
    {
      v8 = 1;
    }
  }
LABEL_13:
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    v7 = (SocketBrokerContext *)this[2].DebugInfo;
    _InterlockedIncrement((volatile signed __int32 *)&DebugInfo->ProcessLocksList.Blink);
  }
  HIDWORD(this[2].SpinCount) = v8;
  LeaveCriticalSection(this + 1);
  DisassociateCurrentThreadFromCallback(a2);
  if ( v7 )
  {
    SocketBrokerContext::NotifyApp((__int64)v7, (__int64)this, v4, v8);
    SharedSocket::CreateRetryTriggerMonitor(this, v8);
    SocketBrokerContext::ReleaseRef(v7);
  }
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->CriticalSection)(this);
}

```

## disassembly

```asm
0x1800278e0  push    rbx
0x1800278e2  push    rbp
0x1800278e3  push    rsi
0x1800278e4  push    rdi
0x1800278e5  push    r12
0x1800278e7  push    r14
0x1800278e9  push    r15
0x1800278eb  sub     rsp, 60h
0x1800278ef  mov     rax, cs:__security_cookie
0x1800278f6  xor     rax, rsp
0x1800278f9  mov     [rsp+98h+var_48], rax
0x1800278fe  xorps   xmm0, xmm0
0x180027901  mov     rbx, rcx
0x180027904  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+0Ch], xmm0
0x180027909  xor     edi, edi
0x18002790b  add     rcx, 28h ; '('; lpCriticalSection
0x18002790f  mov     r14d, r8d
0x180027912  mov     r12, rdx
0x180027915  xor     ebp, ebp
0x180027917  movups  xmmword ptr [rsp+98h+NetworkEvents.lNetworkEvents], xmm0
0x18002791c  lea     esi, [rdi+4]
0x18002791f  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+18h], xmm0
0x180027924  call    cs:__imp_EnterCriticalSection
0x18002792a  mov     rcx, [rbx+20h]; s
0x18002792e  mov     [rbx+118h], dil
0x180027935  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027939  jz      short loc_1800279B6
0x18002793b  test    r14d, r14d
0x18002793e  jz      short loc_18002795D
0x180027940  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027947  mov     edi, r14d
0x18002794a  jz      short loc_1800279B6
0x18002794c  mov     r9d, r14d
0x18002794f  lea     r8, aHandlewaitcall_0; "HandleWaitCallback: IO Wait Result"
0x180027956  call    McTemplateU0zq_EventWriteTransfer
0x18002795b  jmp     short loc_1800279B6
0x18002795d  mov     rdx, [rbx+108h]; hEventObject
0x180027964  lea     r8, [rsp+98h+NetworkEvents]; lpNetworkEvents
0x180027969  call    cs:__imp_WSAEnumNetworkEvents
0x18002796f  cmp     eax, 0FFFFFFFFh
0x180027972  jnz     short loc_180027991
0x180027974  call    cs:__imp_WSAGetLastError
0x18002797a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027981  mov     edi, eax
0x180027983  jz      short loc_1800279B6
0x180027985  mov     r9d, eax
0x180027988  lea     r8, aHandlewaitcall_1; "HandleWaitCallback: WSAEnumNetworkEvent"...
0x18002798f  jmp     short loc_180027956
0x180027991  test    byte ptr [rsp+98h+NetworkEvents.lNetworkEvents], 20h
0x180027996  jz      short loc_1800279B1
0x180027998  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002799f  mov     edi, [rsp+98h+NetworkEvents.iErrorCode+14h]
0x1800279a3  jz      short loc_1800279B6
0x1800279a5  mov     r9d, edi
0x1800279a8  lea     r8, aHandlewaitcall; "HandleWaitCallback: Socket Closed"
0x1800279af  jmp     short loc_180027956
0x1800279b1  mov     esi, 1
0x1800279b6  mov     rax, [rbx+50h]
0x1800279ba  test    rax, rax
0x1800279bd  jz      short loc_1800279C6
0x1800279bf  mov     rbp, rax
0x1800279c2  lock inc dword ptr [rax+18h]
0x1800279c6  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800279ca  mov     [rbx+74h], esi
0x1800279cd  call    cs:__imp_LeaveCriticalSection
0x1800279d3  mov     rcx, r12; pci
0x1800279d6  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x1800279dc  test    rbp, rbp
0x1800279df  jz      short loc_180027A04
0x1800279e1  mov     r9d, esi
0x1800279e4  mov     r8d, edi
0x1800279e7  mov     rdx, rbx
0x1800279ea  mov     rcx, rbp
0x1800279ed  call    ?NotifyApp@SocketBrokerContext@@QEAAXPEAVSharedSocket@@KW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SocketBrokerContext::NotifyApp(SharedSocket *,ulong,_SOCKET_BROKER_TRIGGER_REASON)
0x1800279f2  mov     edx, esi
0x1800279f4  mov     rcx, rbx
0x1800279f7  call    ?CreateRetryTriggerMonitor@SharedSocket@@IEAAKW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SharedSocket::CreateRetryTriggerMonitor(_SOCKET_BROKER_TRIGGER_REASON)
0x1800279fc  mov     rcx, rbp; this
0x1800279ff  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180027a04  mov     rax, [rbx]
0x180027a07  mov     rcx, rbx
0x180027a0a  mov     rax, [rax+8]
0x180027a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a13  mov     rcx, [rsp+98h+var_48]
0x180027a18  xor     rcx, rsp; StackCookie
0x180027a1b  call    __security_check_cookie
0x180027a20  add     rsp, 60h
0x180027a24  pop     r15
0x180027a26  pop     r14
0x180027a28  pop     r12
0x180027a2a  pop     rdi
0x180027a2b  pop     rsi
0x180027a2c  pop     rbp
0x180027a2d  pop     rbx
0x180027a2e  retn
```
