# WPP_SF_

- ea: `0x18000adb4`
- end: `0x18000addc`
- name: `WPP_SF_`
- size: `40`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006100`
- `0x180007090`
- `0x180007330`
- `0x180007a80`
- `0x180007d40`
- `0x1800080c0`
- `0x180009b90`
- `0x18000a8f0`
- `0x18000bd30`
- `0x18000c500`
- `0x18000cae8`
- `0x18000e1cb`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000adca`
- `ntdll!EtwTraceMessage` at `0x18000adca`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  return EtwTraceMessage(a1, 43, a3, a2, 0);
}

```

## disassembly

```asm
0x18000adb4  sub     rsp, 38h
0x18000adb8  movzx   r9d, dx
0x18000adbc  mov     edx, 2Bh ; '+'
0x18000adc1  mov     [rsp+38h+var_18], 0
0x18000adca  call    cs:__imp_EtwTraceMessage
0x18000add1  nop     dword ptr [rax+rax+00h]
0x18000add6  add     rsp, 38h
0x18000adda  retn
```
