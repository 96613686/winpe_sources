# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x18001b290`
- end: `0x18001b2c3`
- name: `??_G?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAPEAXI@Z`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002b0c`
- `0x18001b290`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001b290  push    rbx
0x18001b292  sub     rsp, 20h
0x18001b296  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable'
0x18001b29d  mov     rbx, rcx
0x18001b2a0  mov     [rcx], rax
0x18001b2a3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001b2aa  test    dl, 1
0x18001b2ad  jz      short loc_18001B2B9
0x18001b2af  mov     edx, 10h; unsigned __int64
0x18001b2b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b2b9  mov     rax, rbx
0x18001b2bc  add     rsp, 20h
0x18001b2c0  pop     rbx
0x18001b2c1  retn
```
