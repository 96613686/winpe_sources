# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180001810`
- end: `0x18000183e`
- name: `??_G?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180001810`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001810  push    rbx
0x180001812  sub     rsp, 20h
0x180001816  lea     rax, ??_7?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable'
0x18000181d  mov     rbx, rcx
0x180001820  mov     [rcx], rax
0x180001823  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000182a  test    dl, 1
0x18000182d  jz      short loc_180001834
0x18000182f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001834  mov     rax, rbx
0x180001837  add     rsp, 20h
0x18000183b  pop     rbx
0x18000183c  retn
```
