# _ValidateWrite(void *,uint)

- ea: `0x180015280`
- end: `0x180015289`
- name: `?_ValidateWrite@@YAHPEAXI@Z`
- size: `9`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b8e4`
- `0x18000c2d0`
- `0x1800154e0`
- `0x1800158cc`

## pseudocode

```c
_BOOL8 __fastcall _ValidateWrite(void *a1)
{
  return a1 != 0;
}

```

## disassembly

```asm
0x180015280  xor     eax, eax
0x180015282  test    rcx, rcx
0x180015285  setnz   al
0x180015288  retn
```
