# WPP_SF_

- ea: `0x180007dec`
- end: `0x180007e0d`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800081ec`
- `0x180008bb0`
- `0x180008f5c`
- `0x180009054`
- `0x180009148`
- `0x18000931c`
- `0x180009394`
- `0x180009450`
- `0x18000957c`
- `0x180009f38`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007e02`
- `ntdll!EtwTraceMessage` at `0x180007e02`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  return EtwTraceMessage(a1, 43, a3, a2, 0);
}

```

## disassembly

```asm
0x180007dec  sub     rsp, 38h
0x180007df0  movzx   r9d, dx
0x180007df4  mov     edx, 2Bh ; '+'
0x180007df9  mov     [rsp+38h+var_18], 0
0x180007e02  call    cs:__imp_EtwTraceMessage
0x180007e08  add     rsp, 38h
0x180007e0c  retn
```
