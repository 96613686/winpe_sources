# _guard_dispatch_icall

- ea: `0x180027c80`
- end: `0x180027c86`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `116`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000150c`
- `0x180003190`
- `0x1800043a0`
- `0x180006780`
- `0x180006940`
- `0x180008420`
- `0x180008850`
- `0x1800094b0`
- `0x180009a78`
- `0x18000a020`
- `0x18000a15c`
- `0x18000a430`
- `0x18000c44c`
- `0x18000ca30`
- `0x18000d6e4`
- `0x18000daa8`
- `0x18000dbfc`
- `0x18000ddc8`
- `0x18000e210`
- `0x18000ec10`
- `0x18000f178`
- `0x18000f364`
- `0x18000ff44`
- `0x180010f58`
- `0x18001198c`
- `0x180011ab0`
- `0x180011db0`
- `0x18001215c`
- `0x180012304`
- `0x1800127d0`
- `0x180012d1c`
- `0x180012e6c`
- `0x1800132e4`
- `0x180013860`
- `0x180013b5c`
- `0x180013d94`
- `0x180013f7c`
- `0x18001414c`
- `0x180014368`
- `0x180014854`
- `0x180014e80`
- `0x180015174`
- `0x1800163bc`
- `0x18001667c`
- `0x1800177e4`
- `0x1800178f4`
- `0x1800180b4`
- `0x18001828c`
- `0x180018468`
- `0x180018638`

## callees

- `0x180027c20`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180027c80  jmp     cs:__guard_dispatch_icall_fptr
```
