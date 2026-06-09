# std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>::~vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>(void)

- ea: `0x1800183e4`
- end: `0x180018417`
- name: `??1?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001dce9`

## callees

- `0x1800014d0`
- `0x1800183e4`

## pseudocode

```c
void __fastcall std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::~vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
    operator delete(v2);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800183e4  push    rbx
0x1800183e6  sub     rsp, 20h
0x1800183ea  mov     rbx, rcx
0x1800183ed  mov     rcx, [rcx]; Block
0x1800183f0  test    rcx, rcx
0x1800183f3  jz      short loc_1800183FA
0x1800183f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800183fa  mov     qword ptr [rbx], 0
0x180018401  mov     qword ptr [rbx+8], 0
0x180018409  mov     qword ptr [rbx+10h], 0
0x180018411  add     rsp, 20h
0x180018415  pop     rbx
0x180018416  retn
```
