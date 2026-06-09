# WPP_SF_qdd

- ea: `0x1800218bc`
- end: `0x180021918`
- name: `WPP_SF_qdd`
- size: `92`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, ...)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180015ec0`
- `0x18001f590`
- `0x18001f8b0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002190d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002190d`

## pseudocode

```c
ULONG WPP_SF_qdd(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return TraceMessage(a1, 0x2Bu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a2, va, 8, va1, 4, va2, 4, 0);
}

```

## disassembly

```asm
0x1800218bc  mov     r11, rsp
0x1800218bf  mov     [r11+20h], r9
0x1800218c3  sub     rsp, 68h
0x1800218c7  mov     qword ptr [r11-18h], 0
0x1800218cf  lea     rax, [r11+30h]
0x1800218d3  mov     r8d, 4
0x1800218d9  movzx   r9d, dx; MessageNumber
0x1800218dd  mov     [r11-20h], r8
0x1800218e1  mov     edx, 2Bh ; '+'; MessageFlags
0x1800218e6  mov     [r11-28h], rax
0x1800218ea  lea     rax, [r11+28h]
0x1800218ee  mov     [r11-30h], r8
0x1800218f2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids; MessageGuid
0x1800218f9  mov     [r11-38h], rax
0x1800218fd  lea     rax, [r11+20h]
0x180021901  mov     qword ptr [r11-40h], 8
0x180021909  mov     [r11-48h], rax
0x18002190d  call    cs:__imp_TraceMessage
0x180021913  add     rsp, 68h
0x180021917  retn
```
