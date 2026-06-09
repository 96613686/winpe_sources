# _EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor$0

- ea: `0x18000e2e9`
- end: `0x18000e2f5`
- name: `_EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e24`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::PeerProxy::UninitComEnv_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEapHostPeerSessionApis>::~CComPtr<IEapHostPeerSessionApis>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18000e2e9  lea     rcx, [rdx+80h]
0x18000e2f0  jmp     ??1?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@QEAA@XZ; ATL::CComPtr<IEapHostPeerSessionApis>::~CComPtr<IEapHostPeerSessionApis>(void)
```
