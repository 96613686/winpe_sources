# operator delete(void *,int,char const *,int)

- ea: `0x1400028ac`
- end: `0x1400028b1`
- name: `??3@YAXPEAXHPEBDH@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `136`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002e54`
- `0x1400032ec`
- `0x140003358`
- `0x1400035a4`
- `0x140003640`
- `0x140003680`
- `0x140004210`
- `0x1400048c0`
- `0x140004910`
- `0x1400056ac`
- `0x140005758`
- `0x140005a60`
- `0x140005a90`
- `0x1400064e0`
- `0x1400069ec`
- `0x140006d24`
- `0x140007590`
- `0x140007ce0`
- `0x140007d50`
- `0x140009c20`
- `0x140009f28`
- `0x140009f58`
- `0x140009fd0`
- `0x14000a1a0`
- `0x14000a310`
- `0x14000ab04`
- `0x14000be5c`
- `0x14000bff8`
- `0x14000d02c`
- `0x14000d060`
- `0x14000d0d0`
- `0x14000d384`
- `0x14000df44`
- `0x14000e6a0`
- `0x14000ea0c`
- `0x14000f170`
- `0x14000f978`
- `0x14000fd2c`
- `0x14000fd50`
- `0x14000fdc0`
- `0x14000fdfc`
- `0x14000fe68`
- `0x14000ff6c`
- `0x140010070`
- `0x1400100b0`
- `0x140010378`
- `0x140010cc4`
- `0x1400111f4`
- `0x140011338`
- `0x140014414`

## callees

- `0x140001820`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1400028ac  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
