# _ProcessFileThread_::_1_::dtor$0

- ea: `0x18000a505`
- end: `0x18000a511`
- name: `_ProcessFileThread_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b68`

## pseudocode

```c
_QWORD *__fastcall ProcessFileThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>((_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x18000a505  lea     rcx, [rdx+40h]
0x18000a50c  jmp     ??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)
```
