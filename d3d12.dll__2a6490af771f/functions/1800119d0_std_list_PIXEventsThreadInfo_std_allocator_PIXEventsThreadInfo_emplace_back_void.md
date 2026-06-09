# std::list<PIXEventsThreadInfo,std::allocator<PIXEventsThreadInfo>>::emplace_back<>(void)

- ea: `0x1800119d0`
- end: `0x1800119e9`
- name: `??$emplace_back@$$V@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAAAEAUPIXEventsThreadInfo@@XZ`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002440`
- `0x1800027d0`

## callees

- `0x180011934`

## pseudocode

```c
_OWORD *__fastcall std::list<PIXEventsThreadInfo>::emplace_back<>(__int64 a1)
{
  return std::list<PIXEventsThreadInfo>::_Emplace<>(a1, qword_18001E8A0) + 1;
}

```

## disassembly

```asm
0x1800119d0  sub     rsp, 28h
0x1800119d4  mov     rdx, cs:qword_18001E8A0
0x1800119db  call    ??$_Emplace@$$V@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAAPEAU?$_List_node@UPIXEventsThreadInfo@@PEAX@1@QEAU21@@Z; std::list<PIXEventsThreadInfo>::_Emplace<>(std::_List_node<PIXEventsThreadInfo,void *> * const)
0x1800119e0  add     rax, 10h
0x1800119e4  add     rsp, 28h
0x1800119e8  retn
```
