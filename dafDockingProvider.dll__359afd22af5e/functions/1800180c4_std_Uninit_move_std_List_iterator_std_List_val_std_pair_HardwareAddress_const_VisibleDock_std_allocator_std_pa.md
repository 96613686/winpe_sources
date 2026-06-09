# std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800180c4`
- end: `0x1800180e5`
- name: `??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `33`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019e70`
- `0x18001a24c`

## callees

- `0x1800180c4`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x1800180c4  sub     rsp, 28h
0x1800180c8  jmp     short loc_1800180D8
0x1800180ca  mov     rax, [rcx]
0x1800180cd  mov     [r8], rax
0x1800180d0  add     r8, 8
0x1800180d4  add     rcx, 8
0x1800180d8  cmp     rcx, rdx
0x1800180db  jnz     short loc_1800180CA
0x1800180dd  mov     rax, r8
0x1800180e0  add     rsp, 28h
0x1800180e4  retn
```
