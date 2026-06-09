# DllCanUnloadNow

- ea: `0x180005970`
- end: `0x180005999`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(qword_18001CF70 + 24LL))(&qword_18001CF70) != 0;
}

```

## disassembly

```asm
0x180005970  sub     rsp, 28h
0x180005974  mov     rax, cs:qword_18001CF70
0x18000597b  lea     rcx, qword_18001CF70
0x180005982  mov     rax, [rax+18h]
0x180005986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000598b  xor     ecx, ecx
0x18000598d  test    eax, eax
0x18000598f  setnz   cl
0x180005992  mov     eax, ecx
0x180005994  add     rsp, 28h
0x180005998  retn
```
