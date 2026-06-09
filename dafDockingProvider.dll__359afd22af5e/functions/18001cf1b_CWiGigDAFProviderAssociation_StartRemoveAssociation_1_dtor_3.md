# _CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor$3

- ea: `0x18001cf1b`
- end: `0x18001cf2b`
- name: `_CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008674`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::StartRemoveAssociation_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>((__int64 *)(*(_QWORD *)(a2 + 48) + 8LL));
}

```

## disassembly

```asm
0x18001cf1b  mov     rcx, [rdx+30h]
0x18001cf22  add     rcx, 8
0x18001cf26  jmp     ??1?$ComPtr@UIAepDevnode@@@@QEAA@XZ; ComPtr<IAepDevnode>::~ComPtr<IAepDevnode>(void)
```
