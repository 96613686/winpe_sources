# SocketIoMonitor::Initialize(SocketBrokerContext *,ushort const *,bool,int,int,int,ulong,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)

- ea: `0x180012260`
- end: `0x180012483`
- name: `?Initialize@SocketIoMonitor@@UEAAKPEAVSocketBrokerContext@@PEBG_NHHHK_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct SocketBrokerContext *, const unsigned __int16 *, char, int, int, int, char vInBuffer, void *, void *, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000a0a0`
- `0x180012260`
- `0x180012490`
- `0x1800267d8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012435`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012280`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800123b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800123b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012354`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012354`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800123aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800123aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180012334`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180012334`
- `WS2_32!WSAEventSelect` at `0x180012375`
- `WS2_32!WSAEventSelect` at `0x180012375`
- `WS2_32!__imp_WSAGetLastError` at `0x180012453`
- `WS2_32!__imp_WSAGetLastError` at `0x180012453`

## string_xrefs

- `0x1800123e3`: `SocketIoMonitor: CreateThreadpoolWait failed`

## pseudocode

```c
__int64 __fastcall SocketIoMonitor::Initialize(
        struct _RTL_CRITICAL_SECTION *this,
        struct SocketBrokerContext *a2,
        const unsigned __int16 *a3,
        char a4,
        int a5,
        int a6,
        int a7,
        char vInBuffer,
        void *a9,
        void *a10,
        unsigned int a11,
        struct _SOCKET_BROKER_APP_CONTEXT *a12,
        struct _SOCKET_BROKER_SSL_CONTEXT *a13,
        struct _DNS_REGISTRATION_DATA *a14)
{
  char v18; // bp
  unsigned int LastError; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  HANDLE EventW; // rax
  HANDLE LockSemaphore; // rdx
  struct _TP_WAIT *SpinCount; // rcx
  const wchar_t *v28; // r8

  v18 = 0;
  EnterCriticalSection(this + 1);
  LastError = SharedSocket::Initialize(
                (SharedSocket *)this,
                a2,
                a3,
                a4,
                a5,
                a6,
                a7,
                vInBuffer,
                a9,
                a10,
                a11,
                a12,
                a13,
                a14);
  v22 = LastError;
  if ( LastError )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_7;
    v28 = L"SocketIoMonitor: SharedSocket::Initialize failed with";
    goto LABEL_17;
  }
  if ( this[4].OwningThread )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v21,
        v20,
        L"SocketIoMonitor::Initialize, notifying App because of available packet",
        0);
    v18 = 1;
    HIDWORD(this[2].SpinCount) = 1;
  }
  else
  {
    ThreadpoolWait = CreateThreadpoolWait(SocketIoMonitor::ThreadpoolWaitCallback, this, 0);
    this[6].SpinCount = (ULONG_PTR)ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_7;
      v28 = L"SocketIoMonitor: CreateThreadpoolWait failed";
      goto LABEL_17;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    this[6].LockSemaphore = EventW;
    if ( EventW )
    {
      if ( WSAEventSelect(this->SpinCount, EventW, v22 + 41) != -1 )
      {
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->Type)(this);
        LockSemaphore = this[6].LockSemaphore;
        SpinCount = (struct _TP_WAIT *)this[6].SpinCount;
        LOBYTE(this[7].DebugInfo) = 1;
        SetThreadpoolWait(SpinCount, LockSemaphore, 0);
        goto LABEL_7;
      }
      LastError = WSAGetLastError();
      v22 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v28 = L"SocketIoMonitor: WSAEventSelect failed";
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v28 = L"SocketIoMonitor: creating IO event failed";
LABEL_17:
        McTemplateU0zq_EventWriteTransfer(v21, v20, v28, LastError);
      }
    }
  }
LABEL_7:
  LeaveCriticalSection(this + 1);
  if ( v18 )
    SocketBrokerContext::NotifyApp(a2, this, v22, 1);
  return v22;
}

```

## disassembly

```asm
0x180012260  push    rbx
0x180012262  push    rbp
0x180012263  push    rsi
0x180012264  push    rdi
0x180012265  push    r14
0x180012267  push    r15
0x180012269  sub     rsp, 78h
0x18001226d  mov     rsi, rcx
0x180012270  mov     bl, r9b
0x180012273  add     rcx, 28h ; '('; lpCriticalSection
0x180012277  mov     rdi, r8
0x18001227a  mov     r15, rdx
0x18001227d  xor     bpl, bpl
0x180012280  call    cs:__imp_EnterCriticalSection
0x180012286  mov     rax, [rsp+0A8h+arg_68]
0x18001228e  mov     r9b, bl; bool
0x180012291  mov     [rsp+0A8h+var_40], rax; struct _DNS_REGISTRATION_DATA *
0x180012296  mov     r8, rdi; unsigned __int16 *
0x180012299  mov     rax, [rsp+0A8h+arg_60]
0x1800122a1  mov     rdx, r15; struct SocketBrokerContext *
0x1800122a4  mov     [rsp+0A8h+var_48], rax; struct _SOCKET_BROKER_SSL_CONTEXT *
0x1800122a9  mov     rcx, rsi; this
0x1800122ac  mov     rax, [rsp+0A8h+arg_58]
0x1800122b4  mov     [rsp+0A8h+var_50], rax; struct _SOCKET_BROKER_APP_CONTEXT *
0x1800122b9  mov     eax, [rsp+0A8h+arg_50]
0x1800122c0  mov     [rsp+0A8h+var_58], eax; unsigned int
0x1800122c4  mov     rax, [rsp+0A8h+arg_48]
0x1800122cc  mov     [rsp+0A8h+var_60], rax; void *
0x1800122d1  mov     rax, [rsp+0A8h+arg_40]
0x1800122d9  mov     [rsp+0A8h+var_68], rax; unsigned __int64
0x1800122de  mov     eax, dword ptr [rsp+0A8h+arg_38]
0x1800122e5  mov     dword ptr [rsp+0A8h+vInBuffer], eax; vInBuffer
0x1800122e9  mov     eax, [rsp+0A8h+arg_30]
0x1800122f0  mov     [rsp+0A8h+var_78], eax; int
0x1800122f4  mov     eax, [rsp+0A8h+arg_28]
0x1800122fb  mov     [rsp+0A8h+var_80], eax; int
0x1800122ff  mov     eax, [rsp+0A8h+arg_20]
0x180012306  mov     [rsp+0A8h+var_88], eax; int
0x18001230a  call    ?Initialize@SharedSocket@@UEAAKPEAVSocketBrokerContext@@PEBG_NHHHK_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z; SharedSocket::Initialize(SocketBrokerContext *,ushort const *,bool,int,int,int,ulong,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)
0x18001230f  mov     ebx, eax
0x180012311  test    eax, eax
0x180012313  jnz     loc_180012401
0x180012319  cmp     qword ptr [rsi+0B0h], 0
0x180012321  jnz     loc_1800123EC
0x180012327  xor     r8d, r8d; pcbe
0x18001232a  lea     rcx, ?ThreadpoolWaitCallback@SocketIoMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180012331  mov     rdx, rsi; pv
0x180012334  call    cs:__imp_CreateThreadpoolWait
0x18001233a  mov     [rsi+110h], rax
0x180012341  test    rax, rax
0x180012344  jz      loc_1800123D2
0x18001234a  xor     r9d, r9d; lpName
0x18001234d  xor     r8d, r8d; bInitialState
0x180012350  xor     edx, edx; bManualReset
0x180012352  xor     ecx, ecx; lpEventAttributes
0x180012354  call    cs:__imp_CreateEventW
0x18001235a  mov     [rsi+108h], rax
0x180012361  test    rax, rax
0x180012364  jz      loc_180012435
0x18001236a  mov     rcx, [rsi+20h]; s
0x18001236e  lea     r8d, [rbx+29h]; lNetworkEvents
0x180012372  mov     rdx, rax; hEventObject
0x180012375  call    cs:__imp_WSAEventSelect
0x18001237b  cmp     eax, 0FFFFFFFFh
0x18001237e  jz      loc_180012453
0x180012384  mov     rax, [rsi]
0x180012387  mov     rcx, rsi
0x18001238a  mov     rax, [rax]
0x18001238d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012392  mov     rdx, [rsi+108h]; h
0x180012399  xor     r8d, r8d; pftTimeout
0x18001239c  mov     rcx, [rsi+110h]; pwa
0x1800123a3  mov     byte ptr [rsi+118h], 1
0x1800123aa  call    cs:__imp_SetThreadpoolWait
0x1800123b0  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800123b4  call    cs:__imp_LeaveCriticalSection
0x1800123ba  test    bpl, bpl
0x1800123bd  jnz     loc_18001246A
0x1800123c3  mov     eax, ebx
0x1800123c5  add     rsp, 78h
0x1800123c9  pop     r15
0x1800123cb  pop     r14
0x1800123cd  pop     rdi
0x1800123ce  pop     rsi
0x1800123cf  pop     rbp
0x1800123d0  pop     rbx
0x1800123d1  retn
0x1800123d2  call    cs:__imp_GetLastError
0x1800123d8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800123df  mov     ebx, eax
0x1800123e1  jz      short loc_1800123B0
0x1800123e3  lea     r8, aSocketiomonito_1; "SocketIoMonitor: CreateThreadpoolWait f"...
0x1800123ea  jmp     short loc_18001241A
0x1800123ec  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800123f3  jnz     short loc_180012424
0x1800123f5  mov     bpl, 1
0x1800123f8  mov     dword ptr [rsi+74h], 1
0x1800123ff  jmp     short loc_1800123B0
0x180012401  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012408  jz      short loc_1800123B0
0x18001240a  lea     r8, aSocketiomonito_0; "SocketIoMonitor: SharedSocket::Initiali"...
0x180012411  jmp     short loc_18001241A
0x180012413  lea     r8, aSocketiomonito_3; "SocketIoMonitor: WSAEventSelect failed"
0x18001241a  mov     r9d, eax
0x18001241d  call    McTemplateU0zq_EventWriteTransfer
0x180012422  jmp     short loc_1800123B0
0x180012424  xor     r9d, r9d
0x180012427  lea     r8, aSocketiomonito; "SocketIoMonitor::Initialize, notifying "...
0x18001242e  call    McTemplateU0zq_EventWriteTransfer
0x180012433  jmp     short loc_1800123F5
0x180012435  call    cs:__imp_GetLastError
0x18001243b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012442  mov     ebx, eax
0x180012444  jz      loc_1800123B0
0x18001244a  lea     r8, aSocketiomonito_2; "SocketIoMonitor: creating IO event fail"...
0x180012451  jmp     short loc_18001241A
0x180012453  call    cs:__imp_WSAGetLastError
0x180012459  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012460  mov     ebx, eax
0x180012462  jz      loc_1800123B0
0x180012468  jmp     short loc_180012413
0x18001246a  mov     r9d, 1
0x180012470  mov     r8d, ebx
0x180012473  mov     rdx, rsi
0x180012476  mov     rcx, r15
0x180012479  call    ?NotifyApp@SocketBrokerContext@@QEAAXPEAVSharedSocket@@KW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SocketBrokerContext::NotifyApp(SharedSocket *,ulong,_SOCKET_BROKER_TRIGGER_REASON)
0x18001247e  jmp     loc_1800123C3
```
