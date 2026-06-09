# operator delete(void *)

- ea: `0x18000a2d4`
- end: `0x18000a2f1`
- name: `??3@YAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004348`
- `0x18000a138`
- `0x180012c20`
- `0x18003d450`
- `0x180042f60`
- `0x180043d60`
- `0x180043d98`
- `0x180044c50`
- `0x180046a50`
- `0x180046e70`
- `0x18004f2a0`
- `0x1800503f4`
- `0x180053128`
- `0x180056dc4`
- `0x180056e00`
- `0x180056e6c`
- `0x180057200`
- `0x180057274`
- `0x180057590`
- `0x180057674`
- `0x180057874`
- `0x18005799c`
- `0x18005b4e8`
- `0x18005e950`
- `0x18005fdd8`
- `0x180061700`
- `0x180061e8c`

## callees

- `0x18000a2d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000a2df`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a2df`

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
0x18000a2d4  sub     rsp, 28h
0x18000a2d8  test    rcx, rcx
0x18000a2db  jz      short loc_18000A2EB
0x18000a2dd  xor     edx, edx; Tag
0x18000a2df  call    cs:__imp_ExFreePoolWithTag
0x18000a2e6  nop     dword ptr [rax+rax+00h]
0x18000a2eb  add     rsp, 28h
0x18000a2ef  retn
```
