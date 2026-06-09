# _EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor$1

- ea: `0x18000e2fb`
- end: `0x18000e307`
- name: `_EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cdfc`

## pseudocode

```c
void __fastcall EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)(a2 + 32));
}

```

## disassembly

```asm
0x18000e2fb  lea     rcx, [rdx+20h]; this
0x18000e302  jmp     ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
```
