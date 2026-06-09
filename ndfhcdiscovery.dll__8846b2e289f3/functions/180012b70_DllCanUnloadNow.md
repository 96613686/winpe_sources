# DllCanUnloadNow

- ea: `0x180012b70`
- end: `0x180012b9a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180015010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180012b70  sub     rsp, 28h
0x180012b74  mov     rax, cs:?_AtlModule@@3VNDFHCDiscModule@@A; NDFHCDiscModule _AtlModule
0x180012b7b  lea     rcx, ?_AtlModule@@3VNDFHCDiscModule@@A; NDFHCDiscModule _AtlModule
0x180012b82  mov     rax, [rax+18h]
0x180012b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b8b  xor     ecx, ecx
0x180012b8d  test    eax, eax
0x180012b8f  setnz   cl
0x180012b92  mov     eax, ecx
0x180012b94  add     rsp, 28h
0x180012b98  retn
```
