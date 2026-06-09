# CWinTaskClassFactoryT<CEnergyTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180001ae0`
- end: `0x180001b0d`
- name: `??_G?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180001ae0`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CEnergyTaskHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CEnergyTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001ae0  push    rbx
0x180001ae2  sub     rsp, 20h
0x180001ae6  lea     rax, ??_7?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CEnergyTaskHandler,1>::`vftable'
0x180001aed  mov     rbx, rcx
0x180001af0  mov     [rcx], rax
0x180001af3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001afa  test    dl, 1
0x180001afd  jz      short loc_180001B04
0x180001aff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001b04  mov     rax, rbx
0x180001b07  add     rsp, 20h
0x180001b0b  pop     rbx
0x180001b0c  retn
```
