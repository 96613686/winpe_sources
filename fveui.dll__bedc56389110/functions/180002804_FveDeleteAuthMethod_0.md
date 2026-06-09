# FveDeleteAuthMethod_0

- ea: `0x180002804`
- end: `0x18000280a`
- name: `FveDeleteAuthMethod_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002868c`

## import_xrefs

- `FVEAPI!FveDeleteAuthMethod` at `0x180002804`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall FveDeleteAuthMethod_0(__int64 a1, __int64 a2)
{
  return FveDeleteAuthMethod(a1, a2);
}

```

## disassembly

```asm
0x180002804  jmp     cs:__imp_FveDeleteAuthMethod
```
