# _FdiCallbacks::CallbackFileOpen_::_1_::dtor$2

- ea: `0x180014316`
- end: `0x180014322`
- name: `_FdiCallbacks::CallbackFileOpen_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c894`

## pseudocode

```c
__int64 __fastcall FdiCallbacks::CallbackFileOpen_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Windows::AutoNewPtr<memContainer>::~AutoNewPtr<memContainer>(a2 + 40);
}

```

## disassembly

```asm
0x180014316  lea     rcx, [rdx+28h]
0x18001431d  jmp     ??1?$AutoNewPtr@UmemContainer@@@Windows@@QEAA@XZ; Windows::AutoNewPtr<memContainer>::~AutoNewPtr<memContainer>(void)
```
