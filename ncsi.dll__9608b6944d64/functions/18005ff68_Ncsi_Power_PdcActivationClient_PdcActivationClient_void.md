# Ncsi::Power::PdcActivationClient::~PdcActivationClient(void)

- ea: `0x18005ff68`
- end: `0x18005ffad`
- name: `??1PdcActivationClient@Power@Ncsi@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(Ncsi::Power::PdcActivationClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180060a60`

## callees

- `0x18002cea4`
- `0x18005ff68`
- `0x180060b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ffa6`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18005ff87`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18005ff87`

## pseudocode

```c
void __fastcall Ncsi::Power::PdcActivationClient::~PdcActivationClient(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rax

  if ( std::_Atomic_storage<void *,8>::load(&this[1]) )
  {
    v4 = std::_Atomic_storage<void *,8>::load(v3);
    Pdcv2ActivationClientUnregister(v4);
  }
  if ( Ncsi::Power::g_dtorRefPdcActivationEvent )
    wil::details::SetEvent(Ncsi::Power::g_dtorRefPdcActivationEvent, v2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18005ff68  push    rbx
0x18005ff6a  sub     rsp, 20h
0x18005ff6e  mov     rbx, rcx
0x18005ff71  add     rcx, 28h ; '('
0x18005ff75  call    ?load@?$_Atomic_storage@PEAX$07@std@@QEBAPEAXW4memory_order@2@@Z; std::_Atomic_storage<void *,8>::load(std::memory_order)
0x18005ff7a  test    rax, rax
0x18005ff7d  jz      short loc_18005FF8D
0x18005ff7f  call    ?load@?$_Atomic_storage@PEAX$07@std@@QEBAPEAXW4memory_order@2@@Z; std::_Atomic_storage<void *,8>::load(std::memory_order)
0x18005ff84  mov     rcx, rax
0x18005ff87  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18005ff8d  mov     rcx, cs:?g_dtorRefPdcActivationEvent@Power@Ncsi@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; this
0x18005ff94  test    rcx, rcx
0x18005ff97  jz      short loc_18005FF9E
0x18005ff99  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18005ff9e  mov     rcx, rbx
0x18005ffa1  add     rsp, 20h
0x18005ffa5  pop     rbx
0x18005ffa6  jmp     cs:__imp_DeleteCriticalSection
```
