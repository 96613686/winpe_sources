# _guard_dispatch_icall

- ea: `0x140005c30`
- end: `0x140005c36`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400034a0`
- `0x1400035c0`
- `0x140003680`
- `0x140004078`
- `0x1400040a8`
- `0x1400040ec`
- `0x140004154`
- `0x1400041c0`
- `0x14000420c`
- `0x140004258`
- `0x1400042c0`
- `0x14000431c`
- `0x140004370`
- `0x1400043dc`
- `0x14000445c`
- `0x140004500`
- `0x140005118`
- `0x14000518c`
- `0x1400051e8`
- `0x140005244`
- `0x1400052b0`
- `0x14000533c`
- `0x1400053c8`
- `0x140005460`
- `0x140005520`
- `0x1400055dc`
- `0x140005670`
- `0x140005834`
- `0x140005890`
- `0x1400058fc`
- `0x140005990`
- `0x140007010`
- `0x14000fc6c`
- `0x14000fcf0`
- `0x14000fd84`
- `0x14000fed0`
- `0x140015030`

## callees

- `0x140005c60`

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
0x140005c30  jmp     cs:__guard_dispatch_icall_fptr
```
