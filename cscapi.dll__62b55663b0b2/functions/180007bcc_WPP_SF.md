# WPP_SF_

- ea: `0x180007bcc`
- end: `0x180007bed`
- name: `WPP_SF_`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003f50`
- `0x180004000`
- `0x1800073f0`
- `0x180007950`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007be2`
- `ntdll!EtwTraceMessage` at `0x180007be2`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  __int64 v4; // [rsp+28h] [rbp-10h]
  __int64 v5; // [rsp+30h] [rbp-8h]

  return EtwTraceMessage(a1, 43, a3, a2, 0, v4, v5);
}

```

## disassembly

```asm
0x180007bcc  sub     rsp, 38h
0x180007bd0  movzx   r9d, dx
0x180007bd4  mov     edx, 2Bh ; '+'
0x180007bd9  mov     [rsp+38h+var_18], 0
0x180007be2  call    cs:__imp_EtwTraceMessage
0x180007be8  add     rsp, 38h
0x180007bec  retn
```
