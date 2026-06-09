# CsrCreateProcess

- ea: `0x180005880`
- end: `0x1800058a3`
- name: `CsrCreateProcess`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800058b0`

## pseudocode

```c
__int64 __fastcall CsrCreateProcess(void *a1, void *a2, _DWORD *a3, __int64 a4, __int16 a5)
{
  return CsrpCreateProcess(a1, a2, a3, a4, a5, 0, 0);
}

```

## disassembly

```asm
0x180005880  sub     rsp, 48h
0x180005884  xor     eax, eax
0x180005886  mov     [rsp+48h+var_18], rax; __int64
0x18000588b  mov     [rsp+48h+var_20], rax; __int64
0x180005890  mov     eax, [rsp+48h+arg_20]
0x180005894  mov     [rsp+48h+var_28], eax; int
0x180005898  call    CsrpCreateProcess
0x18000589d  add     rsp, 48h
0x1800058a1  retn
```
