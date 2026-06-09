# R<CQueue>::~R<CQueue>(void)

- ea: `0x140003bd8`
- end: `0x140003be0`
- name: `??1?$R@VCQueue@@@@QEAA@XZ`
- size: `8`
- prototype: `void __fastcall(CReference **)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d1d0`
- `0x14001dbc1`
- `0x14001dbe5`
- `0x14001dce6`
- `0x14001dd9a`
- `0x14001ddac`
- `0x14001dee2`
- `0x14001def4`
- `0x14001dfa2`
- `0x14001e17a`
- `0x14001e1ea`
- `0x14001e228`
- `0x14001e38e`
- `0x14001e570`

## callees

- `0x14000393c`

## pseudocode

```c
void __fastcall R<CQueue>::~R<CQueue>(CReference **a1)
{
  SafeRelease<CQueue>(*a1);
}

```

## disassembly

```asm
0x140003bd8  mov     rcx, [rcx]
0x140003bdb  jmp     ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
```
