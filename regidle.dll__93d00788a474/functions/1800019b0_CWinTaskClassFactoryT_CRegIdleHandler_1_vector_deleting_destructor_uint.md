# CWinTaskClassFactoryT<CRegIdleHandler,1>::`vector deleting destructor'(uint)

- ea: `0x1800019b0`
- end: `0x1800019dd`
- name: `??_E?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x1800019b0`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CRegIdleHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CRegIdleHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800019b0  push    rbx
0x1800019b2  sub     rsp, 20h
0x1800019b6  lea     rax, ??_7?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@6B@; const CWinTaskClassFactoryT<CRegIdleHandler,1>::`vftable'
0x1800019bd  mov     rbx, rcx
0x1800019c0  mov     [rcx], rax
0x1800019c3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800019ca  test    dl, 1
0x1800019cd  jz      short loc_1800019D4
0x1800019cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800019d4  mov     rax, rbx
0x1800019d7  add     rsp, 20h
0x1800019db  pop     rbx
0x1800019dc  retn
```
