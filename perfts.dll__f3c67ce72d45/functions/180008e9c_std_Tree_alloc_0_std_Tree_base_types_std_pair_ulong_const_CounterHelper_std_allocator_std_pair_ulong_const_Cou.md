# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,CounterHelper *>,std::allocator<std::pair<ulong const,CounterHelper *>>>>::_Buyheadnode(void)

- ea: `0x180008e9c`
- end: `0x180008ed5`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@XZ`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012f0`
- `0x180001320`
- `0x180001350`

## callees

- `0x180001da8`
- `0x1800020e8`
- `0x180008e9c`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,CounterHelper *>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x30u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x180008e9c  mov     [rsp+arg_0], rcx
0x180008ea1  sub     rsp, 28h
0x180008ea5  mov     ecx, 30h ; '0'; Size
0x180008eaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008eaf  mov     [rsp+28h+arg_0], rax
0x180008eb4  test    rax, rax
0x180008eb7  jz      short loc_180008ECF
0x180008eb9  mov     [rax], rax
0x180008ebc  mov     [rax+8], rax
0x180008ec0  mov     [rax+10h], rax
0x180008ec4  mov     word ptr [rax+18h], 101h
0x180008eca  add     rsp, 28h
0x180008ece  retn
0x180008ecf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
