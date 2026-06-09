# nap::auto_xxx<IIASVssWriter *,void (*)(IIASVssWriter *),&nap::_delete<IIASVssWriter>(IIASVssWriter *),0,nap::no_copy>::operator->(void)

- ea: `0x180007840`
- end: `0x180007844`
- name: `??C?$auto_xxx@PEAUIIASVssWriter@@P6AXPEAU1@@Z$1??$_delete@UIIASVssWriter@@@nap@@YAX0@Z$0A@Vno_copy@2@@nap@@QEBAPEAUIIASVssWriter@@XZ`
- size: `4`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ecaa`
- `0x18000ed55`

## pseudocode

```c
__int64 __fastcall nap::auto_xxx<IIASVssWriter *,void (*)(IIASVssWriter *),&void nap::_delete<IIASVssWriter>(IIASVssWriter *),0,nap::no_copy>::operator->(
        __int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x180007840  mov     rax, [rcx]
0x180007843  retn
```
