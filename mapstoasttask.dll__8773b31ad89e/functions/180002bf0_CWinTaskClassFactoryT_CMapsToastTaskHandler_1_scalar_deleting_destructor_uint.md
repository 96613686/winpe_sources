# CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180002bf0`
- end: `0x180002c1d`
- name: `??_G?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001618`
- `0x180002bf0`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002bf0  push    rbx
0x180002bf2  sub     rsp, 20h
0x180002bf6  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`vftable'
0x180002bfd  mov     rbx, rcx
0x180002c00  mov     [rcx], rax
0x180002c03  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002c0a  test    dl, 1
0x180002c0d  jz      short loc_180002C14
0x180002c0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c14  mov     rax, rbx
0x180002c17  add     rsp, 20h
0x180002c1b  pop     rbx
0x180002c1c  retn
```
