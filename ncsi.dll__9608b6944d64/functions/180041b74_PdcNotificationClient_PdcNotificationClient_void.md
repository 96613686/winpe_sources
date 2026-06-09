# PdcNotificationClient::~PdcNotificationClient(void)

- ea: `0x180041b74`
- end: `0x180041bd7`
- name: `??1PdcNotificationClient@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(PdcNotificationClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180060a70`

## callees

- `0x18002cea4`
- `0x180041b74`
- `0x180041be0`
- `0x180041cc0`
- `0x180060b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041bd0`
- `UMPDC!PdcNotificationClientUnregister` at `0x180041b9a`
- `UMPDC!PdcNotificationClientUnregister` at `0x180041b9a`

## pseudocode

```c
void __fastcall PdcNotificationClient::~PdcNotificationClient(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  void *v4; // rdx

  if ( std::_Atomic_storage<void *,8>::load(&this[6].LockSemaphore) )
  {
    v3 = std::_Atomic_storage<void *,8>::load(v2);
    PdcNotificationClientUnregister(v3);
  }
  WcmCommon::ThreadPoolProcessLatestWorkItem<1>::Cancel(this + 1);
  if ( g_dtorRefPdcNotificationEvent )
    wil::details::SetEvent(g_dtorRefPdcNotificationEvent, v4);
  WcmCommon::ThreadPoolProcessLatestWorkItem<1>::~ThreadPoolProcessLatestWorkItem<1>((__int64)&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180041b74  mov     [rsp+arg_0], rbx
0x180041b79  push    rdi
0x180041b7a  sub     rsp, 20h
0x180041b7e  mov     rbx, rcx
0x180041b81  add     rcx, 108h
0x180041b88  call    ?load@?$_Atomic_storage@PEAX$07@std@@QEBAPEAXW4memory_order@2@@Z; std::_Atomic_storage<void *,8>::load(std::memory_order)
0x180041b8d  test    rax, rax
0x180041b90  jz      short loc_180041BA0
0x180041b92  call    ?load@?$_Atomic_storage@PEAX$07@std@@QEBAPEAXW4memory_order@2@@Z; std::_Atomic_storage<void *,8>::load(std::memory_order)
0x180041b97  mov     rcx, rax
0x180041b9a  call    cs:__imp_PdcNotificationClientUnregister
0x180041ba0  lea     rcx, [rbx+28h]; lpCriticalSection
0x180041ba4  call    ?Cancel@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::Cancel(void)
0x180041ba9  mov     rcx, cs:?g_dtorRefPdcNotificationEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; this
0x180041bb0  test    rcx, rcx
0x180041bb3  jz      short loc_180041BBA
0x180041bb5  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180041bba  lea     rcx, [rbx+28h]
0x180041bbe  call    ??1?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::~ThreadPoolProcessLatestWorkItem<1>(void)
0x180041bc3  mov     rcx, rbx
0x180041bc6  mov     rbx, [rsp+28h+arg_0]
0x180041bcb  add     rsp, 20h
0x180041bcf  pop     rdi
0x180041bd0  jmp     cs:__imp_DeleteCriticalSection
```
