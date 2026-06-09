# EnsureDSSvcRunning(void)

- ea: `0x1800031a8`
- end: `0x1800031c8`
- name: `?EnsureDSSvcRunning@@YAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800015a0`
- `0x180001810`
- `0x180002060`
- `0x18000313c`
- `0x1800031d0`
- `0x1800032a0`
- `0x180003380`
- `0x180003460`

## callees

- `0x180003518`

## pseudocode

```c
__int64 __fastcall EnsureDSSvcRunning(int a1, int a2, int a3, int a4)
{
  return ((int)StartAndWaitForService(a1, a2, a3, a4) >> 31) & 0xC1130002;
}

```

## disassembly

```asm
0x1800031a8  sub     rsp, 38h
0x1800031ac  lea     rax, [rsp+38h+arg_0]
0x1800031b1  mov     [rsp+38h+var_10], rax
0x1800031b6  call    StartAndWaitForService
0x1800031bb  sar     eax, 1Fh
0x1800031be  and     eax, 0C1130002h
0x1800031c3  add     rsp, 38h
0x1800031c7  retn
```
