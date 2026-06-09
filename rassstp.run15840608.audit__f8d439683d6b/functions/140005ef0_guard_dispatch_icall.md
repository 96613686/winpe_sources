# _guard_dispatch_icall

- ea: `0x140005ef0`
- end: `0x140005ef6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `43`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001010`
- `0x1400018b0`
- `0x140002030`
- `0x1400023f0`
- `0x140002700`
- `0x140002bd8`
- `0x140002c08`
- `0x140002f2c`
- `0x140002f88`
- `0x140002fc4`
- `0x140003010`
- `0x140003788`
- `0x140003864`
- `0x1400038d8`
- `0x140003938`
- `0x1400039a0`
- `0x1400039f8`
- `0x140003a64`
- `0x140003b58`
- `0x140004a1c`
- `0x140005398`
- `0x1400053ec`
- `0x140005454`
- `0x140007050`
- `0x14000e818`
- `0x14000e89c`
- `0x14000e930`
- `0x14000f9d0`
- `0x140010010`
- `0x140010c58`
- `0x140011500`
- `0x140011b00`
- `0x1400150e0`
- `0x140016734`
- `0x1400169a4`
- `0x140016cf0`
- `0x140016e84`
- `0x140018054`
- `0x140018ad0`
- `0x140018c70`
- `0x140019040`
- `0x140019420`
- `0x140019860`

## callees

- `0x140005e90`

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
0x140005ef0  jmp     cs:__guard_dispatch_icall_fptr
```
