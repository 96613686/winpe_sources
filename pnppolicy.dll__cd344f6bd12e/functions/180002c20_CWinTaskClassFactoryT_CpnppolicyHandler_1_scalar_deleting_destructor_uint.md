# CWinTaskClassFactoryT<CpnppolicyHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180002c20`
- end: `0x180002c4d`
- name: `??_G?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180002c20`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CpnppolicyHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002c20  push    rbx
0x180002c22  sub     rsp, 20h
0x180002c26  lea     rax, ??_7?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@6B@; const CWinTaskClassFactoryT<CpnppolicyHandler,1>::`vftable'
0x180002c2d  mov     rbx, rcx
0x180002c30  mov     [rcx], rax
0x180002c33  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002c3a  test    dl, 1
0x180002c3d  jz      short loc_180002C44
0x180002c3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c44  mov     rax, rbx
0x180002c47  add     rsp, 20h
0x180002c4b  pop     rbx
0x180002c4c  retn
```
