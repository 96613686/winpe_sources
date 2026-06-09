# DisposeIfPtr

- ea: `0x1800042e0`
- end: `0x1800042f5`
- name: `DisposeIfPtr`
- size: `21`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `34`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c0c`
- `0x180002344`
- `0x1800023c8`
- `0x1800029a4`
- `0x1800042fc`
- `0x18000464c`
- `0x180005974`
- `0x1800067e4`
- `0x180006f00`
- `0x180007130`
- `0x180007234`
- `0x180007418`
- `0x180007fe0`
- `0x1800177ac`
- `0x180018960`
- `0x180019b00`
- `0x18001a6c8`
- `0x18001a7d0`
- `0x18001bb30`
- `0x18001c4a0`
- `0x18001d680`
- `0x18001de14`
- `0x18001e1ec`
- `0x18001e97c`
- `0x18001ef48`
- `0x18001f14c`
- `0x18001f23c`
- `0x18001fc68`
- `0x180021060`
- `0x1800211ec`
- `0x18002145c`
- `0x180021554`
- `0x1800217fc`
- `0x180021a38`

## callees

- `0x1800042e0`
- `0x18001d151`

## pseudocode

```c
__int64 __fastcall DisposeIfPtr(void *a1)
{
  if ( a1 )
    free_0(a1);
  return 0;
}

```

## disassembly

```asm
0x1800042e0  sub     rsp, 28h
0x1800042e4  test    rcx, rcx
0x1800042e7  jz      short loc_1800042EE
0x1800042e9  call    free_0
0x1800042ee  xor     eax, eax
0x1800042f0  add     rsp, 28h
0x1800042f4  retn
```
