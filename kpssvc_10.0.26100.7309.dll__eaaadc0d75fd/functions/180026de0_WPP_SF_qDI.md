# WPP_SF_qDI

- ea: `0x180026de0`
- end: `0x180026e40`
- name: `WPP_SF_qDI`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180020610`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800215c0`
- `0x1800216f4`
- `0x1800223fc`
- `0x180022708`
- `0x180022a5c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026e2e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026e2e`

## pseudocode

```c
ULONG WPP_SF_qDI(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
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
  return TraceMessage(a1, 0x2Bu, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, a2, va, 8, va1, 4, va2, 8, 0);
}

```

## disassembly

```asm
0x180026de0  mov     r11, rsp
0x180026de3  mov     [r11+20h], r9
0x180026de7  sub     rsp, 68h
0x180026deb  and     qword ptr [r11-18h], 0
0x180026df0  lea     rax, [r11+30h]
0x180026df4  mov     r8d, 8
0x180026dfa  movzx   r9d, dx; MessageNumber
0x180026dfe  mov     [r11-20h], r8
0x180026e02  mov     edx, 2Bh ; '+'; MessageFlags
0x180026e07  mov     [r11-28h], rax
0x180026e0b  lea     rax, [r11+28h]
0x180026e0f  mov     qword ptr [r11-30h], 4
0x180026e17  mov     [r11-38h], rax
0x180026e1b  lea     rax, [r11+20h]
0x180026e1f  mov     [r11-40h], r8
0x180026e23  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids; MessageGuid
0x180026e2a  mov     [r11-48h], rax
0x180026e2e  call    cs:__imp_TraceMessage
0x180026e35  nop     dword ptr [rax+rax+00h]
0x180026e3a  add     rsp, 68h
0x180026e3e  retn
```
