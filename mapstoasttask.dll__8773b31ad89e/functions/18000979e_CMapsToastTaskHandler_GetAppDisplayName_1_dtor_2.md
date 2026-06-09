# _CMapsToastTaskHandler::GetAppDisplayName_::_1_::dtor$2

- ea: `0x18000979e`
- end: `0x1800097aa`
- name: `_CMapsToastTaskHandler::GetAppDisplayName_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800027a8`

## pseudocode

```c
void __fastcall CMapsToastTaskHandler::GetAppDisplayName_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::~NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>(a2 + 40);
}

```

## disassembly

```asm
0x18000979e  lea     rcx, [rdx+28h]
0x1800097a5  jmp     ??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)
```
