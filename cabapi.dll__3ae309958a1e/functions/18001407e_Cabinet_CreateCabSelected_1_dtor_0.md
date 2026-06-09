# _Cabinet::CreateCabSelected_::_1_::dtor$0

- ea: `0x18001407e`
- end: `0x18001408a`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$0`
- size: `12`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008338`

## pseudocode

```c
BOOL __fastcall Cabinet::CreateCabSelected_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<void *,FciDeleter>::~unique_ptr<void *,FciDeleter>((HFCI **)(a2 + 160));
}

```

## disassembly

```asm
0x18001407e  lea     rcx, [rdx+0A0h]
0x180014085  jmp     ??1?$unique_ptr@PEAXUFciDeleter@@@std@@QEAA@XZ; std::unique_ptr<void *,FciDeleter>::~unique_ptr<void *,FciDeleter>(void)
```
