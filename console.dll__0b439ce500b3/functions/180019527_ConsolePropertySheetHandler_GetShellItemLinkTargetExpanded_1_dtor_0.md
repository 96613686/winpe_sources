# _ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded_::_1_::dtor$0

- ea: `0x180019527`
- end: `0x180019533`
- name: `_ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800132a8`

## pseudocode

```c
__int64 __fastcall ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x180019527  lea     rcx, [rdx+48h]
0x18001952e  jmp     ??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)
```
