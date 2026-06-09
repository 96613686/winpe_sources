# SafeRelease<CQueue>(CQueue *)

- ea: `0x14000393c`
- end: `0x14000394f`
- name: `??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z`
- size: `19`
- prototype: `void __fastcall(CReference *)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140003bd8`
- `0x140003c2c`
- `0x140003f54`
- `0x140006ee4`
- `0x140007374`
- `0x140007ea8`
- `0x1400080a0`
- `0x140009b68`
- `0x140009f80`
- `0x14000ac9c`
- `0x14000afa0`
- `0x14000b984`
- `0x14000baa8`
- `0x14000bdc0`
- `0x14000c720`
- `0x14000d110`
- `0x14000d75c`
- `0x14000e768`

## callees

- `0x14000393c`
- `0x140004538`

## pseudocode

```c
void __fastcall SafeRelease<CQueue>(CReference *a1)
{
  if ( a1 )
    CReference::Release(a1);
}

```

## disassembly

```asm
0x14000393c  sub     rsp, 28h
0x140003940  test    rcx, rcx
0x140003943  jz      short loc_14000394A
0x140003945  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x14000394a  add     rsp, 28h
0x14000394e  retn
```
