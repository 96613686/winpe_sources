# CWinTaskClassFactoryT<CDsregTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180001e80`
- end: `0x180001eb2`
- name: `??_G?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001830`
- `0x180001e80`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CDsregTaskHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CDsregTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001e80  push    rbx
0x180001e82  sub     rsp, 20h
0x180001e86  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDsregTaskHandler,1>::`vftable'
0x180001e8d  mov     rbx, rcx
0x180001e90  mov     [rcx], rax
0x180001e93  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001e9a  test    dl, 1
0x180001e9d  jz      short loc_180001EA9
0x180001e9f  mov     edx, 10h; unsigned __int64
0x180001ea4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001ea9  mov     rax, rbx
0x180001eac  add     rsp, 20h
0x180001eb0  pop     rbx
0x180001eb1  retn
```
