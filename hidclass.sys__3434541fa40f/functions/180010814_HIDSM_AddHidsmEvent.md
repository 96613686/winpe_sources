# HIDSM_AddHidsmEvent

- ea: `0x180010814`
- end: `0x18001082a`
- name: `HIDSM_AddHidsmEvent`
- size: `22`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f4f0`
- `0x18000fd60`
- `0x1800100e4`
- `0x180010454`
- `0x180012090`
- `0x180016e14`
- `0x18001a560`
- `0x18001a5b0`
- `0x18001a6b0`
- `0x18001b4f0`
- `0x18003b444`
- `0x18003f2b4`
- `0x180042b00`

## callees

- `0x180010830`

## pseudocode

```c
void __fastcall HIDSM_AddHidsmEvent(__int64 a1, int a2)
{
  HIDSM_AddEvent((KSPIN_LOCK *)(a1 + 704), a2);
}

```

## disassembly

```asm
0x180010814  sub     rsp, 28h
0x180010818  add     rcx, 2C0h; Context
0x18001081f  call    HIDSM_AddEvent
0x180010824  add     rsp, 28h
0x180010828  retn
```
