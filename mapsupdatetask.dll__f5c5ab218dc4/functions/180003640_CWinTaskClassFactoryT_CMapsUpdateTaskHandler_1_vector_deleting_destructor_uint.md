# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180003640`
- end: `0x18000366d`
- name: `??_E?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x180001ff4`
- `0x180003640`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003640  push    rbx
0x180003642  sub     rsp, 20h
0x180003646  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vftable'
0x18000364d  mov     rbx, rcx
0x180003650  mov     [rcx], rax
0x180003653  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000365a  test    dl, 1
0x18000365d  jz      short loc_180003664
0x18000365f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003664  mov     rax, rbx
0x180003667  add     rsp, 20h
0x18000366b  pop     rbx
0x18000366c  retn
```
