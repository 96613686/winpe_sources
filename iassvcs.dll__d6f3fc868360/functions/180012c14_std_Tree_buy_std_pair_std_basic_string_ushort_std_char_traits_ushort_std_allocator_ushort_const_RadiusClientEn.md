# std::_Tree_buy<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>>>::_Freenode0(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_RadiusClientEntry *>,void *> *)

- ea: `0x180012c14`
- end: `0x180012c1e`
- name: `?_Freenode0@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_RadiusClientEntry@@@std@@PEAX@2@@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180018b19`
- `0x180018b7a`
- `0x180018ba0`
- `0x180018c32`

## import_xrefs

- `msvcrt!free` at `0x180012c17`

## pseudocode

```c
void __fastcall std::_Tree_buy<std::pair<std::wstring const,_RadiusClientEntry *>>::_Freenode0(__int64 a1, void *a2)
{
  free(a2);
}

```

## disassembly

```asm
0x180012c14  mov     rcx, rdx
0x180012c17  jmp     cs:__imp_free
```
