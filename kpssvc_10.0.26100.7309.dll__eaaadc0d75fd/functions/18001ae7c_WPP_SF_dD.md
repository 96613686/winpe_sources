# WPP_SF_dD

- ea: `0x18001ae7c`
- end: `0x18001aec5`
- name: `WPP_SF_dD`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180019ad0`
- `0x18001fd08`
- `0x1800208d8`
- `0x180020d0c`
- `0x18002cc3c`
- `0x18002ccd0`
- `0x18002ed24`
- `0x1800302a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001aeb3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001aeb3`

## pseudocode

```c
ULONG WPP_SF_dD(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x18001ae7c  mov     r11, rsp
0x18001ae7f  mov     [r11+20h], r9d
0x18001ae83  sub     rsp, 58h
0x18001ae87  and     qword ptr [r11-18h], 0
0x18001ae8c  lea     rax, [r11+28h]
0x18001ae90  mov     r9d, 4
0x18001ae96  mov     [r11-20h], r9
0x18001ae9a  mov     [r11-28h], rax
0x18001ae9e  lea     rax, [r11+20h]
0x18001aea2  mov     [r11-30h], r9
0x18001aea6  movzx   r9d, dx; MessageNumber
0x18001aeaa  mov     edx, 2Bh ; '+'; MessageFlags
0x18001aeaf  mov     [r11-38h], rax
0x18001aeb3  call    cs:__imp_TraceMessage
0x18001aeba  nop     dword ptr [rax+rax+00h]
0x18001aebf  add     rsp, 58h
0x18001aec3  retn
```
