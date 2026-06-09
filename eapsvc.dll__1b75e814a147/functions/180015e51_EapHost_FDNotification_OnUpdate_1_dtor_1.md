# _EapHost::FDNotification::OnUpdate_::_1_::dtor$1

- ea: `0x180015e51`
- end: `0x180015e5d`
- name: `_EapHost::FDNotification::OnUpdate_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a8f0`

## pseudocode

```c
__int64 __fastcall EapHost::FDNotification::OnUpdate_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x180015e51  lea     rcx, [rdx+30h]
0x180015e58  jmp     ??1?$CComPtr@UIFunctionDiscovery@@@ATL@@QEAA@XZ; ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>(void)
```
