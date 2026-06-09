# WPP_SF_

- ea: `0x18000aaa0`
- end: `0x18000aac1`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001520`
- `0x180003b40`
- `0x180004f00`
- `0x180006ae0`
- `0x180008c30`
- `0x1800093a8`
- `0x180009e50`
- `0x18000a190`
- `0x18000a2a4`
- `0x18000b8a0`
- `0x18000be10`
- `0x18000bf38`
- `0x18000e1a8`
- `0x180010430`
- `0x180011d10`
- `0x1800136b0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000aab6`
- `ntdll!EtwTraceMessage` at `0x18000aab6`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  return EtwTraceMessage(a1, 43, a3, a2, 0);
}

```

## disassembly

```asm
0x18000aaa0  sub     rsp, 38h
0x18000aaa4  movzx   r9d, dx
0x18000aaa8  mov     edx, 2Bh ; '+'
0x18000aaad  mov     [rsp+38h+var_18], 0
0x18000aab6  call    cs:__imp_EtwTraceMessage
0x18000aabc  add     rsp, 38h
0x18000aac0  retn
```
