# DllCanUnloadNow

- ea: `0x18000bd20`
- end: `0x18000bd49`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x18000bd20  sub     rsp, 28h
0x18000bd24  mov     rax, cs:?_AtlModule@@3VCComModule@ATL@@A; ATL::CComModule _AtlModule
0x18000bd2b  lea     rcx, ?_AtlModule@@3VCComModule@ATL@@A; ATL::CComModule _AtlModule
0x18000bd32  mov     rax, [rax+18h]
0x18000bd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd3b  xor     ecx, ecx
0x18000bd3d  test    eax, eax
0x18000bd3f  setnz   cl
0x18000bd42  mov     eax, ecx
0x18000bd44  add     rsp, 28h
0x18000bd48  retn
```
