# WPP_SF_sqd

- ea: `0x18000bd30`
- end: `0x18000bd86`
- name: `WPP_SF_sqd`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `30`
- callee_count: `0`
- tags: ``

## callers

- `0x180009b20`
- `0x180009c10`
- `0x18000a070`
- `0x18000a28c`
- `0x18000a480`
- `0x18000a780`
- `0x18000a854`
- `0x18000a9e8`
- `0x18000b2e4`
- `0x18000b500`
- `0x18000b5c0`
- `0x18000b8e0`
- `0x18000b9b4`
- `0x18000c144`
- `0x18000c510`
- `0x18000c5a0`
- `0x18000ccec`
- `0x18000d16c`
- `0x18000d6a0`
- `0x18000d880`
- `0x18000d9d0`
- `0x18000dbc0`
- `0x18000ded0`
- `0x18000e104`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`
- `0x18000ed14`
- `0x18000f020`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000bd7b`
- `ADVAPI32!TraceMessage` at `0x18000bd7b`

## pseudocode

```c
ULONG WPP_SF_sqd(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return TraceMessage(a1, 0x2Bu, a3, a2, " ", 2, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x18000bd30  mov     r11, rsp
0x18000bd33  sub     rsp, 68h
0x18000bd37  mov     qword ptr [r11-18h], 0
0x18000bd3f  lea     rax, [r11+30h]
0x18000bd43  mov     qword ptr [r11-20h], 4
0x18000bd4b  mov     [r11-28h], rax
0x18000bd4f  lea     rax, [r11+28h]
0x18000bd53  mov     qword ptr [r11-30h], 8
0x18000bd5b  mov     [r11-38h], rax
0x18000bd5f  lea     rax, asc_180016AC4; " "
0x18000bd66  movzx   r9d, dx; MessageNumber
0x18000bd6a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000bd6f  mov     qword ptr [r11-40h], 2
0x18000bd77  mov     [r11-48h], rax
0x18000bd7b  call    cs:__imp_TraceMessage
0x18000bd81  add     rsp, 68h
0x18000bd85  retn
```
