# ModuleFailFastForHRESULT

- ea: `0x18000a5d0`
- end: `0x18000a5df`
- name: `ModuleFailFastForHRESULT`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c2c`
- `0x180007d0c`
- `0x180007e64`
- `0x180008140`
- `0x18000a844`

## callees

- `0x18000a924`

## pseudocode

```c
void __fastcall __noreturn ModuleFailFastForHRESULT(__int64 a1, const void *a2)
{
  MilFailFastForHR(-2147024882, a2);
  JUMPOUT(0x18000A5DELL);
}

```

## disassembly

```asm
0x18000a5d0  sub     rsp, 28h
0x18000a5d4  mov     ecx, 8007000Eh; int
0x18000a5d9  call    ?MilFailFastForHR@@YAXJPEBX@Z; MilFailFastForHR(long,void const *)
```
