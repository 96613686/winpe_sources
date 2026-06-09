# _guard_dispatch_icall

- ea: `0x180010920`
- end: `0x180010926`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `120`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001da0`
- `0x180001e30`
- `0x180002010`
- `0x1800025f0`
- `0x180002680`
- `0x1800026d0`
- `0x180002710`
- `0x180002930`
- `0x180002970`
- `0x1800029b0`
- `0x180002a50`
- `0x180002a84`
- `0x18000368c`
- `0x180003a54`
- `0x180003c38`
- `0x1800040e0`
- `0x180004140`
- `0x1800044f0`
- `0x180004530`
- `0x180004590`
- `0x1800045d0`
- `0x180004630`
- `0x180004690`
- `0x180004840`
- `0x180004aa0`
- `0x180004c74`
- `0x1800075c4`
- `0x1800076a0`
- `0x180007ba8`
- `0x180007bd8`
- `0x180007c1c`
- `0x180007c70`
- `0x180007cf0`
- `0x180007f70`
- `0x18000ad04`
- `0x18000b298`
- `0x18000b2ec`
- `0x18000b350`
- `0x18000b79c`
- `0x18000bc60`
- `0x18000bf50`
- `0x18000c1f0`
- `0x18000c400`
- `0x18000c44c`
- `0x18000c4c0`
- `0x18000c5ec`
- `0x18000d01c`
- `0x18000dc78`
- `0x18000dce0`
- `0x18000dd48`

## callees

- `0x1800108c0`

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
0x180010920  jmp     cs:__guard_dispatch_icall_fptr
```
