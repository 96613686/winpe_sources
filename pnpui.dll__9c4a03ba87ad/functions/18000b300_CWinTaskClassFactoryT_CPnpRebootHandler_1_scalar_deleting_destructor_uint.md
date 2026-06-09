# CWinTaskClassFactoryT<CPnpRebootHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x18000b300`
- end: `0x18000b32d`
- name: `??_G?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001294`
- `0x18000b300`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CPnpRebootHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b300  push    rbx
0x18000b302  sub     rsp, 20h
0x18000b306  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPnpRebootHandler,1>::`vftable'
0x18000b30d  mov     rbx, rcx
0x18000b310  mov     [rcx], rax
0x18000b313  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b31a  test    dl, 1
0x18000b31d  jz      short loc_18000B324
0x18000b31f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b324  mov     rax, rbx
0x18000b327  add     rsp, 20h
0x18000b32b  pop     rbx
0x18000b32c  retn
```
