# operator delete(void *,unsigned __int64)

- ea: `0x18001f1c4`
- end: `0x18001f1c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `120`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001280`
- `0x180001a10`
- `0x180003ba0`
- `0x180003cf0`
- `0x180003d60`
- `0x180003df0`
- `0x180003e50`
- `0x180005850`
- `0x180006bb0`
- `0x1800075b0`
- `0x1800091b0`
- `0x1800091f0`
- `0x180009250`
- `0x180009654`
- `0x180009704`
- `0x180009900`
- `0x180009944`
- `0x180009980`
- `0x1800099bc`
- `0x180009fa0`
- `0x18000a158`
- `0x18000aaac`
- `0x18000ae28`
- `0x18000b2e4`
- `0x18000b6fc`
- `0x18000c1f4`
- `0x18000c6f0`
- `0x18000cc78`
- `0x18000e700`
- `0x18000eba0`
- `0x18000fc1c`
- `0x1800101ac`
- `0x1800105c4`
- `0x180010d00`
- `0x180010f30`
- `0x180012f10`
- `0x180012f58`
- `0x180013570`
- `0x180013be0`
- `0x180013d30`
- `0x180013d70`
- `0x180014540`
- `0x180014770`
- `0x180014830`
- `0x180015e84`
- `0x1800161e0`
- `0x1800173b0`
- `0x180017430`
- `0x180018adc`
- `0x1800196f0`

## callees

- `0x18001f21c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x18001f1c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
