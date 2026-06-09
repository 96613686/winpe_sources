# _EapHost::Peer::PeerProxy::InitComEnv_::_1_::dtor$0

- ea: `0x18000e2d7`
- end: `0x18000e2e3`
- name: `_EapHost::Peer::PeerProxy::InitComEnv_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cdfc`

## pseudocode

```c
void __fastcall EapHost::Peer::PeerProxy::InitComEnv_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)(a2 + 48));
}

```

## disassembly

```asm
0x18000e2d7  lea     rcx, [rdx+30h]; this
0x18000e2de  jmp     ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
```
