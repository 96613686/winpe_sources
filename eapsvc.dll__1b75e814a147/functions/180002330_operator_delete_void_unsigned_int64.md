# operator delete(void *,unsigned __int64)

- ea: `0x180002330`
- end: `0x180002335`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `37`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004260`
- `0x1800042a0`
- `0x1800042e0`
- `0x180004340`
- `0x180004380`
- `0x1800043e0`
- `0x18000aa48`
- `0x18000abc0`
- `0x18000ac00`
- `0x18000b5c0`
- `0x18000b690`
- `0x18000c880`
- `0x18000cc1c`
- `0x18000ccd8`
- `0x18000d570`
- `0x18000da70`
- `0x18000dab0`
- `0x18000db10`
- `0x18000e1c0`
- `0x18000e640`
- `0x18000e680`
- `0x18000e7e8`
- `0x18000e844`
- `0x18000e8a0`
- `0x18000e90c`
- `0x18000eafc`
- `0x18000ecfc`
- `0x18000eda8`
- `0x18001100c`
- `0x180011500`
- `0x180011524`
- `0x1800115fc`
- `0x1800153d6`
- `0x1800153f9`
- `0x1800154ab`
- `0x180015543`
- `0x1800157c5`

## callees

- `0x18000ab70`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *lpMem)
{
  ??3@YAXPEAX@Z(lpMem);
}

```

## disassembly

```asm
0x180002330  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
