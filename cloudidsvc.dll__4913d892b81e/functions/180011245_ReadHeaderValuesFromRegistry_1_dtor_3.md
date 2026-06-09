# _ReadHeaderValuesFromRegistry_::_1_::dtor$3

- ea: `0x180011245`
- end: `0x180011251`
- name: `_ReadHeaderValuesFromRegistry_::_1_::dtor$3`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a820`

## pseudocode

```c
HLOCAL __fastcall ReadHeaderValuesFromRegistry_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 64));
}

```

## disassembly

```asm
0x180011245  lea     rcx, [rdx+40h]
0x18001124c  jmp     ??1?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
