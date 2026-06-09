# std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> const *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800180a0`
- end: `0x1800180be`
- name: `??$_Uninit_fill_n@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_KV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAXPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@_KPEBV10@AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019e70`

## callees

- `0x1800180a0`

## pseudocode

```c
__int64 __fastcall std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 result; // rax

  for ( ; a2; --a2 )
  {
    result = *a3;
    *a1++ = *a3;
  }
  return result;
}

```

## disassembly

```asm
0x1800180a0  sub     rsp, 28h
0x1800180a4  test    rdx, rdx
0x1800180a7  jz      short loc_1800180B9
0x1800180a9  mov     rax, [r8]
0x1800180ac  mov     [rcx], rax
0x1800180af  lea     rcx, [rcx+8]
0x1800180b3  sub     rdx, 1
0x1800180b7  jnz     short loc_1800180A9
0x1800180b9  add     rsp, 28h
0x1800180bd  retn
```
