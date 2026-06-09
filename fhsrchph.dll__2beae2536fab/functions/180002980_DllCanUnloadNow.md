# DllCanUnloadNow

- ea: `0x180002980`
- end: `0x1800029a9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(g_atlModule + 24LL))(&g_atlModule) != 0;
}

```

## disassembly

```asm
0x180002980  sub     rsp, 28h
0x180002984  mov     rax, cs:?g_atlModule@@3VCDpSearchPHModule@@A; CDpSearchPHModule g_atlModule
0x18000298b  lea     rcx, ?g_atlModule@@3VCDpSearchPHModule@@A; CDpSearchPHModule g_atlModule
0x180002992  mov     rax, [rax+18h]
0x180002996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299b  xor     ecx, ecx
0x18000299d  test    eax, eax
0x18000299f  setnz   cl
0x1800029a2  mov     eax, ecx
0x1800029a4  add     rsp, 28h
0x1800029a8  retn
```
