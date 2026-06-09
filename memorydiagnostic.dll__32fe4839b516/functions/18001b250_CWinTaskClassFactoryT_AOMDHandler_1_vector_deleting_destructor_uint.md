# CWinTaskClassFactoryT<AOMDHandler,1>::`vector deleting destructor'(uint)

- ea: `0x18001b250`
- end: `0x18001b283`
- name: `??_E?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAPEAXI@Z`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002b0c`
- `0x18001b250`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<AOMDHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<AOMDHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001b250  push    rbx
0x18001b252  sub     rsp, 20h
0x18001b256  lea     rax, ??_7?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@6B@; const CWinTaskClassFactoryT<AOMDHandler,1>::`vftable'
0x18001b25d  mov     rbx, rcx
0x18001b260  mov     [rcx], rax
0x18001b263  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001b26a  test    dl, 1
0x18001b26d  jz      short loc_18001B279
0x18001b26f  mov     edx, 10h; unsigned __int64
0x18001b274  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b279  mov     rax, rbx
0x18001b27c  add     rsp, 20h
0x18001b280  pop     rbx
0x18001b281  retn
```
