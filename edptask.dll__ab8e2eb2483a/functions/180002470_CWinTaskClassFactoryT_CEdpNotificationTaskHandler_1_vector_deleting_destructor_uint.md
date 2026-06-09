# CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180002470`
- end: `0x18000249e`
- name: `??_E?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002470`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000248f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000248f`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002470  push    rbx
0x180002472  sub     rsp, 20h
0x180002476  lea     rax, ??_7?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vftable'
0x18000247d  mov     rbx, rcx
0x180002480  mov     [rcx], rax
0x180002483  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000248a  test    dl, 1
0x18000248d  jz      short loc_180002495
0x18000248f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002495  mov     rax, rbx
0x180002498  add     rsp, 20h
0x18000249c  pop     rbx
0x18000249d  retn
```
