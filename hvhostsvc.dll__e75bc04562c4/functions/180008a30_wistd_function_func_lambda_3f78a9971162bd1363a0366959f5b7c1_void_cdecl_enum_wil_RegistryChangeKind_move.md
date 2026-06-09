# wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::__move

- ea: `0x180008a30`
- end: `0x180008a43`
- name: `wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::__move`
- size: `19`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl_enum_wil::RegistryChangeKind__::__move(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  *a2 = off_18000B0B0;
  result = *(_QWORD *)(a1 + 8);
  a2[1] = result;
  return result;
}

```

## disassembly

```asm
0x180008a30  lea     rax, off_18000B0B0
0x180008a37  mov     [rdx], rax
0x180008a3a  mov     rax, [rcx+8]
0x180008a3e  mov     [rdx+8], rax
0x180008a42  retn
```
