# DllCanUnloadNow

- ea: `0x180005a40`
- end: `0x180005a69`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(g_atlModule + 24LL))(&g_atlModule) != 0;
}

```

## disassembly

```asm
0x180005a40  sub     rsp, 28h
0x180005a44  mov     rax, cs:?g_atlModule@@3VCTaskModule@@A; CTaskModule g_atlModule
0x180005a4b  lea     rcx, ?g_atlModule@@3VCTaskModule@@A; CTaskModule g_atlModule
0x180005a52  mov     rax, [rax+18h]
0x180005a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5b  xor     ecx, ecx
0x180005a5d  test    eax, eax
0x180005a5f  setnz   cl
0x180005a62  mov     eax, ecx
0x180005a64  add     rsp, 28h
0x180005a68  retn
```
