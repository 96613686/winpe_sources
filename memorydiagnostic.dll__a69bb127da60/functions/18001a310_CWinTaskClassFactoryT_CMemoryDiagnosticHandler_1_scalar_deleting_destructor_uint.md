# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x18001a310`
- end: `0x18001a342`
- name: `??_G?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180003294`
- `0x18001a310`

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
0x18001a310  push    rbx
0x18001a312  sub     rsp, 20h
0x18001a316  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable'
0x18001a31d  mov     rbx, rcx
0x18001a320  mov     [rcx], rax
0x18001a323  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001a32a  test    dl, 1
0x18001a32d  jz      short loc_18001A339
0x18001a32f  mov     edx, 10h
0x18001a334  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a339  mov     rax, rbx
0x18001a33c  add     rsp, 20h
0x18001a340  pop     rbx
0x18001a341  retn
```
