# _guard_dispatch_icall

- ea: `0x14000daa0`
- end: `0x14000daa6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `52`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001130`
- `0x1400014e0`
- `0x140001d30`
- `0x140002610`
- `0x140004180`
- `0x1400043e0`
- `0x140004530`
- `0x140004780`
- `0x1400048f0`
- `0x140005140`
- `0x140005440`
- `0x1400059c0`
- `0x140006170`
- `0x1400062b0`
- `0x1400066d0`
- `0x140006950`
- `0x140006a60`
- `0x140007b10`
- `0x140008a10`
- `0x140008d80`
- `0x140009d04`
- `0x140009e28`
- `0x14000a67c`
- `0x14000a7b8`
- `0x14000a8e8`
- `0x14000a9c0`
- `0x14000aaac`
- `0x14000af6c`
- `0x14000afe8`
- `0x14000b334`
- `0x14000bd6c`
- `0x14000bef4`
- `0x14000c0a4`
- `0x14000c9f8`
- `0x14000cc5c`
- `0x14000cd68`
- `0x14000ce54`
- `0x14000cf48`
- `0x14000d054`
- `0x14000d780`
- `0x14000f010`
- `0x1400175e8`
- `0x14001769c`
- `0x140017764`
- `0x1400178b0`
- `0x1400183a4`
- `0x140018bf0`
- `0x14001908c`
- `0x14001aa98`
- `0x14001d8b0`

## callees

- `0x14000dad0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14000daa0  jmp     cs:__guard_dispatch_icall_fptr
```
