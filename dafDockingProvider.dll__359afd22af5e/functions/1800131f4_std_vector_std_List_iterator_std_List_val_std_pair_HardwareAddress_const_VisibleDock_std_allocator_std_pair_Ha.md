# std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>::_Xlen(void)

- ea: `0x1800131f4`
- end: `0x180013205`
- name: `?_Xlen@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001321c`
- `0x180013390`
- `0x180019e70`
- `0x18001a24c`

## callees

- `0x180001588`

## pseudocode

```c
void __noreturn std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x1800131f4  sub     rsp, 28h
0x1800131f8  lea     rcx, aVectorTTooLong
0x1800131ff  call    ?_Xlength_error@std@@YAXPEBD@Z
```
