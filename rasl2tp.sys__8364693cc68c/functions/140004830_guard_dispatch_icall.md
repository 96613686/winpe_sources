# _guard_dispatch_icall

- ea: `0x140004830`
- end: `0x140004836`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `56`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001820`
- `0x1400019a0`
- `0x140003050`
- `0x140003080`
- `0x1400030c4`
- `0x1400031ec`
- `0x140003230`
- `0x14000328c`
- `0x1400032f0`
- `0x140003344`
- `0x14000351c`
- `0x1400035f0`
- `0x140003a04`
- `0x140003a58`
- `0x140003ac8`
- `0x140003b1c`
- `0x140003b88`
- `0x140003cf8`
- `0x140003d54`
- `0x140003df0`
- `0x140003ec8`
- `0x140004018`
- `0x140006010`
- `0x14000f698`
- `0x14000f930`
- `0x14000fd0c`
- `0x140018260`
- `0x140019940`
- `0x14001ae40`
- `0x14001c6d0`
- `0x14001d010`
- `0x14001d100`
- `0x14001dd40`
- `0x14001eb80`
- `0x14001f008`
- `0x14001f454`
- `0x14001f520`
- `0x14001f5ac`
- `0x14001f61c`
- `0x14001f774`
- `0x14001f7d0`
- `0x14001f830`
- `0x14001f980`
- `0x14001fa24`
- `0x14001fb10`
- `0x14001fd14`
- `0x14001fd40`
- `0x14001fe6c`
- `0x14001ff90`
- `0x140020100`

## callees

- `0x140004860`

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
0x140004830  jmp     cs:__guard_dispatch_icall_fptr
```
