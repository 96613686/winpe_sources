# _ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$1

- ea: `0x14000eeaa`
- end: `0x14000eeb6`
- name: `_ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000c2bc`

## pseudocode

```c
__int64 __fastcall ProvisioningFileManager::TryCreateProvisioningFileManager_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>::~unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>(a2 + 112);
}

```

## disassembly

```asm
0x14000eeaa  lea     rcx, [rdx+70h]
0x14000eeb1  jmp     ??1?$unique_ptr@UIElementEnumerator@@U?$ProvReleaser@UIElementEnumerator@@@@@std@@QEAA@XZ; std::unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>::~unique_ptr<IElementEnumerator,ProvReleaser<IElementEnumerator>>(void)
```
