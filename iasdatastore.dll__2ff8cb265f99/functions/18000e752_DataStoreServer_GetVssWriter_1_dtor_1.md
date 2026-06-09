# _DataStoreServer::GetVssWriter_::_1_::dtor$1

- ea: `0x18000e752`
- end: `0x18000e75e`
- name: `_DataStoreServer::GetVssWriter_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800076b4`

## pseudocode

```c
__int64 __fastcall DataStoreServer::GetVssWriter_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return nap::auto_ptr<IASVssWriter>::~auto_ptr<IASVssWriter>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 104));
}

```

## disassembly

```asm
0x18000e752  lea     rcx, [rdx+68h]
0x18000e759  jmp     ??1?$auto_ptr@VIASVssWriter@@@nap@@QEAA@XZ; nap::auto_ptr<IASVssWriter>::~auto_ptr<IASVssWriter>(void)
```
