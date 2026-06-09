# operator delete(void *)

- ea: `0x1400010a4`
- end: `0x1400010c1`
- name: `??3@YAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `68`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400011ac`
- `0x140001a04`
- `0x140002fc0`
- `0x1400033f0`
- `0x140003aa0`
- `0x140003af0`
- `0x140003b20`
- `0x140004314`
- `0x1400058fc`
- `0x140007e3c`
- `0x1400085f4`
- `0x140008b78`
- `0x14000bb00`
- `0x14000c100`
- `0x14000c2a8`
- `0x14000c388`
- `0x14000c780`
- `0x14000ce0c`
- `0x14000cecc`
- `0x14000cef8`
- `0x14000d748`
- `0x14000d810`
- `0x14000dec4`
- `0x14000e488`
- `0x14000e5f4`
- `0x14000e710`
- `0x14000ee68`
- `0x14000eea0`
- `0x14000eef0`
- `0x14000ef28`
- `0x14000ef78`
- `0x14000efc8`
- `0x14000f320`
- `0x14000f54c`
- `0x14000fca0`
- `0x14000fcb8`
- `0x140010568`
- `0x140010984`
- `0x140010e2c`
- `0x140011300`
- `0x1400113c0`
- `0x140011bf4`
- `0x140011c20`
- `0x140011cc8`
- `0x140012c80`
- `0x140012cc0`
- `0x14001a630`
- `0x14001a900`
- `0x14001aa04`
- `0x14001aa94`

## callees

- `0x1400010a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400010af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400010af`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x1400010a4  sub     rsp, 28h
0x1400010a8  test    rcx, rcx
0x1400010ab  jz      short loc_1400010BB
0x1400010ad  xor     edx, edx; Tag
0x1400010af  call    cs:__imp_ExFreePoolWithTag
0x1400010b6  nop     dword ptr [rax+rax+00h]
0x1400010bb  add     rsp, 28h
0x1400010bf  retn
```
