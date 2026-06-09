# _ReadHeaderValuesFromRegistry_::_1_::dtor$2

- ea: `0x1800114ea`
- end: `0x1800114f6`
- name: `_ReadHeaderValuesFromRegistry_::_1_::dtor$2`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a820`

## pseudocode

```c
HLOCAL __fastcall ReadHeaderValuesFromRegistry_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 56));
}

```

## disassembly

```asm
0x1800114ea  lea     rcx, [rdx+38h]
0x1800114f1  jmp     ??1?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
