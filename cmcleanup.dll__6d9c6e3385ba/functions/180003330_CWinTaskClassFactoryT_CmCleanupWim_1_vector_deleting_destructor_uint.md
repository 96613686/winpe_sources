# CWinTaskClassFactoryT<CmCleanupWim,1>::`vector deleting destructor'(uint)

- ea: `0x180003330`
- end: `0x180003362`
- name: `??_E?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001954`
- `0x180003330`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CmCleanupWim,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003330  push    rbx
0x180003332  sub     rsp, 20h
0x180003336  lea     rax, ??_7?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@6B@; const CWinTaskClassFactoryT<CmCleanupWim,1>::`vftable'
0x18000333d  mov     rbx, rcx
0x180003340  mov     [rcx], rax
0x180003343  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000334a  test    dl, 1
0x18000334d  jz      short loc_180003359
0x18000334f  mov     edx, 10h
0x180003354  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003359  mov     rax, rbx
0x18000335c  add     rsp, 20h
0x180003360  pop     rbx
0x180003361  retn
```
