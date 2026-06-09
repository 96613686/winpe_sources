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
- `0x18003d460`
- `0x180042f60`
- `0x180043d60`
- `0x180043d98`
- `0x180044c50`
- `0x180046a50`
- `0x180046e70`
- `0x18004f100`
- `0x180050254`
- `0x180052f88`
- `0x180056c24`
- `0x180056c60`
- `0x180056ccc`
- `0x180057060`
- `0x1800570d4`
- `0x1800573f0`
- `0x1800574d4`
- `0x1800576d4`
- `0x1800577fc`
- `0x18005b348`
- `0x18005e7b0`
- `0x18005fc38`
- `0x180061560`
- `0x180061cec`

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
