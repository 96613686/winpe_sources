# ___CxxFrameHandler3

- ea: `0x1004d406`
- end: `0x1004d40c`
- name: `___CxxFrameHandler3`
- size: `6`
- prototype: ``
- caller_count: `93`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1000c0d0`
- `0x1000c750`
- `0x1000ce70`
- `0x1000cff0`
- `0x1000d150`
- `0x1000d5b0`
- `0x1000d8e0`
- `0x1000ddb0`
- `0x1000e140`
- `0x1000eab0`
- `0x1000f260`
- `0x1000fc70`
- `0x1000fcf0`
- `0x10010b50`
- `0x10011380`
- `0x10011530`
- `0x100118b0`
- `0x10011d40`
- `0x10012270`
- `0x10012e10`
- `0x10012f70`
- `0x100132e0`
- `0x10013890`
- `0x10013d50`
- `0x10014d90`
- `0x100153e0`
- `0x10015dc0`
- `0x10016040`
- `0x10016f60`
- `0x10017160`
- `0x10017960`
- `0x10017b50`
- `0x10018750`
- `0x1001a540`
- `0x1001a700`
- `0x1001a970`
- `0x1001af60`
- `0x1001b4a0`
- `0x1001b720`
- `0x1001b930`
- `0x1001d4b0`
- `0x1001d7f0`
- `0x1001df20`
- `0x1001e350`
- `0x1001ebc0`
- `0x1001f370`
- `0x1001f750`
- `0x1001f8e0`
- `0x100205d0`
- `0x10024540`

## import_xrefs

- `msvcrt!__CxxFrameHandler3` at `0x1004d406`

## pseudocode

```c
// attributes: thunk
int __CxxFrameHandler3()
{
  return ___CxxFrameHandler3();
}

```

## disassembly

```asm
0x1004d406  jmp     ds:__imp____CxxFrameHandler3
```
