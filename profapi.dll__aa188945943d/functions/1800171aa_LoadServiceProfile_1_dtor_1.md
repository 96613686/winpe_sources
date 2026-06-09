# __LoadServiceProfile_::_1_::dtor$1

- ea: `0x1800171aa`
- end: `0x1800171b6`
- name: `__LoadServiceProfile_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180005b90`

## pseudocode

```c
__int64 __fastcall _LoadServiceProfile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a2 + 32);
}

```

## disassembly

```asm
0x1800171aa  lea     rcx, [rdx+20h]
0x1800171b1  jmp     ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
```
