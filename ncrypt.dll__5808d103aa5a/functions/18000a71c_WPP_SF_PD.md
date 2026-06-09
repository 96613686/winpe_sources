# WPP_SF_PD

- ea: `0x18000a71c`
- end: `0x18000a76a`
- name: `WPP_SF_PD`
- size: `78`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180008820`
- `0x18000a3d0`
- `0x18000c5b0`
- `0x180010a90`
- `0x180011f00`
- `0x1800147a0`
- `0x180016620`
- `0x18001bed0`
- `0x18001c0b0`
- `0x18001c2c0`
- `0x18001c3a0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a75f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a75f`

## pseudocode

```c
ULONG WPP_SF_PD(TRACEHANDLE a1, USHORT a2, _QWORD a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids, a2, &v5, 8, va, 4, 0);
}

```

## disassembly

```asm
0x18000a71c  mov     r11, rsp
0x18000a71f  mov     [r11+20h], r9
0x18000a723  sub     rsp, 58h
0x18000a727  mov     qword ptr [r11-18h], 0
0x18000a72f  lea     rax, [r11+28h]
0x18000a733  mov     qword ptr [r11-20h], 4
0x18000a73b  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids; MessageGuid
0x18000a742  mov     [r11-28h], rax
0x18000a746  lea     rax, [r11+20h]
0x18000a74a  movzx   r9d, dx; MessageNumber
0x18000a74e  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a753  mov     qword ptr [r11-30h], 8
0x18000a75b  mov     [r11-38h], rax
0x18000a75f  call    cs:__imp_TraceMessage
0x18000a765  add     rsp, 58h
0x18000a769  retn
```
