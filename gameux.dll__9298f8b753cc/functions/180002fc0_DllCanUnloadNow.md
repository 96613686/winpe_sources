# DllCanUnloadNow

- ea: `0x180002fc0`
- end: `0x180002fe9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180002fc0  sub     rsp, 28h
0x180002fc4  mov     rax, cs:?_AtlModule@@3VCGamesUxModule@@A; CGamesUxModule _AtlModule
0x180002fcb  lea     rcx, ?_AtlModule@@3VCGamesUxModule@@A; CGamesUxModule _AtlModule
0x180002fd2  mov     rax, [rax+18h]
0x180002fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fdb  xor     ecx, ecx
0x180002fdd  test    eax, eax
0x180002fdf  setnz   cl
0x180002fe2  mov     eax, ecx
0x180002fe4  add     rsp, 28h
0x180002fe8  retn
```
