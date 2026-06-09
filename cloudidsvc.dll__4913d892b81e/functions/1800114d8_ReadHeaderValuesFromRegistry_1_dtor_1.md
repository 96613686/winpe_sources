# _ReadHeaderValuesFromRegistry_::_1_::dtor$1

- ea: `0x1800114d8`
- end: `0x1800114e4`
- name: `_ReadHeaderValuesFromRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a820`

## pseudocode

```c
HLOCAL __fastcall ReadHeaderValuesFromRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 48));
}

```

## disassembly

```asm
0x1800114d8  lea     rcx, [rdx+30h]
0x1800114df  jmp     ??1?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
