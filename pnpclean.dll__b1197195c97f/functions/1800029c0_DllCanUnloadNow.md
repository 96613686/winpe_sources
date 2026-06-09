# DllCanUnloadNow

- ea: `0x1800029c0`
- end: `0x1800029e9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(g_AtlModule + 24LL))(&g_AtlModule) != 0;
}

```

## disassembly

```asm
0x1800029c0  sub     rsp, 28h
0x1800029c4  mov     rax, cs:?g_AtlModule@@3VCPnpCleanModule@@A; CPnpCleanModule g_AtlModule
0x1800029cb  lea     rcx, ?g_AtlModule@@3VCPnpCleanModule@@A; CPnpCleanModule g_AtlModule
0x1800029d2  mov     rax, [rax+18h]
0x1800029d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029db  xor     ecx, ecx
0x1800029dd  test    eax, eax
0x1800029df  setnz   cl
0x1800029e2  mov     eax, ecx
0x1800029e4  add     rsp, 28h
0x1800029e8  retn
```
