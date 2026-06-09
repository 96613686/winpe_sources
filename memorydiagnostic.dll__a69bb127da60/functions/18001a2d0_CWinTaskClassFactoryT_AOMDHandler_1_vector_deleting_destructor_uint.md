# CWinTaskClassFactoryT<AOMDHandler,1>::`vector deleting destructor'(uint)

- ea: `0x18001a2d0`
- end: `0x18001a302`
- name: `??_E?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180003294`
- `0x18001a2d0`

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
0x18001a2d0  push    rbx
0x18001a2d2  sub     rsp, 20h
0x18001a2d6  lea     rax, ??_7?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@6B@; const CWinTaskClassFactoryT<AOMDHandler,1>::`vftable'
0x18001a2dd  mov     rbx, rcx
0x18001a2e0  mov     [rcx], rax
0x18001a2e3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001a2ea  test    dl, 1
0x18001a2ed  jz      short loc_18001A2F9
0x18001a2ef  mov     edx, 10h
0x18001a2f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a2f9  mov     rax, rbx
0x18001a2fc  add     rsp, 20h
0x18001a300  pop     rbx
0x18001a301  retn
```
