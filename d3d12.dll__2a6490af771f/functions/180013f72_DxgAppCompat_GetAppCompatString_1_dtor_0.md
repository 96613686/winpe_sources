# _DxgAppCompat::GetAppCompatString_::_1_::dtor$0

- ea: `0x180013f72`
- end: `0x180013f7e`
- name: `_DxgAppCompat::GetAppCompatString_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010a8c`

## pseudocode

```c
__int64 __fastcall DxgAppCompat::GetAppCompatString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::lock_guard<std::mutex>::~lock_guard<std::mutex>(a2 + 136);
}

```

## disassembly

```asm
0x180013f72  lea     rcx, [rdx+88h]
0x180013f79  jmp     ??1?$lock_guard@Vmutex@std@@@std@@QEAA@XZ; std::lock_guard<std::mutex>::~lock_guard<std::mutex>(void)
```
