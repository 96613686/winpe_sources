# _guard_dispatch_icall

- ea: `0x14002c710`
- end: `0x14002c716`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `64`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001030`
- `0x140001da4`
- `0x140001e78`
- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x1400051e8`
- `0x14000522c`
- `0x1400052a0`
- `0x140006374`
- `0x1400064c0`
- `0x140007ca0`
- `0x14000bab4`
- `0x14000bb10`
- `0x14000bb78`
- `0x14000bbfc`
- `0x14000fd80`
- `0x14000fe04`
- `0x14000fe48`
- `0x140010c74`
- `0x140010ce4`
- `0x140010d50`
- `0x140011624`
- `0x140013f74`
- `0x140013fd0`
- `0x1400145f8`
- `0x140015be8`
- `0x140016ad8`
- `0x140017100`
- `0x140019cec`
- `0x14001afac`
- `0x14001b074`
- `0x14001b150`
- `0x14001c7ec`
- `0x14001ecb0`
- `0x14001ed10`
- `0x14001edc4`
- `0x14001ee34`
- `0x14001f868`
- `0x140020970`
- `0x140021150`
- `0x140021cf0`
- `0x140022320`
- `0x140023160`
- `0x140023940`
- `0x1400244e0`
- `0x140024cc0`
- `0x14002597c`
- `0x14002665c`
- `0x1400275d0`

## callees

- `0x14002c740`

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
0x14002c710  jmp     cs:__guard_dispatch_icall_fptr
```
