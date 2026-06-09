# __GetUserFolderPathFromSid_::_1_::dtor$0

- ea: `0x180017150`
- end: `0x18001715c`
- name: `__GetUserFolderPathFromSid_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180005b90`

## pseudocode

```c
__int64 __fastcall _GetUserFolderPathFromSid_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a2 + 104);
}

```

## disassembly

```asm
0x180017150  lea     rcx, [rdx+68h]
0x180017157  jmp     ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
```
