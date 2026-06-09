# DllCanUnloadNow

- ea: `0x180005cc0`
- end: `0x180005cea`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(qword_180017B50 + 24LL))(&qword_180017B50) != 0;
}

```

## disassembly

```asm
0x180005cc0  sub     rsp, 28h
0x180005cc4  mov     rax, cs:qword_180017B50
0x180005ccb  lea     rcx, qword_180017B50
0x180005cd2  mov     rax, [rax+18h]
0x180005cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cdb  xor     ecx, ecx
0x180005cdd  test    eax, eax
0x180005cdf  setnz   cl
0x180005ce2  mov     eax, ecx
0x180005ce4  add     rsp, 28h
0x180005ce8  retn
```
