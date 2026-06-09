# __LoadServiceProfile_::_1_::dtor$0

- ea: `0x180017186`
- end: `0x180017192`
- name: `__LoadServiceProfile_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180005b90`

## pseudocode

```c
__int64 __fastcall _LoadServiceProfile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a2 + 56);
}

```

## disassembly

```asm
0x180017186  lea     rcx, [rdx+38h]
0x18001718d  jmp     ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
```
