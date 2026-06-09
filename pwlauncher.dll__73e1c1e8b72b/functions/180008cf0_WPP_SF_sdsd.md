# WPP_SF_sdsd

- ea: `0x180008cf0`
- end: `0x180008d93`
- name: `WPP_SF_sdsd`
- size: `163`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, __int64, ...)`
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005638`
- `0x180005a68`
- `0x180005c98`
- `0x1800065bc`
- `0x180006814`
- `0x180006b34`
- `0x180006e44`
- `0x1800070ec`
- `0x1800074e4`
- `0x1800077f8`
- `0x180007994`
- `0x180007c78`
- `0x180007e74`
- `0x18000810c`
- `0x18000830c`
- `0x180008488`
- `0x180008798`

## callees

- `0x180008cf0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008d88`
- `ADVAPI32!TraceMessage` at `0x180008d88`

## string_xrefs

- `0x180008d6b`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
ULONG WPP_SF_sdsd(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  const char *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v8; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  const char *v10; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, const char *);
  v4 = v10;
  if ( v10 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v10[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !v10 )
    v4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
           a2,
           "drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
           42,
           va,
           4,
           v4,
           v6,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x180008cf0  sub     rsp, 78h
0x180008cf4  mov     r8, [rsp+78h+arg_28]
0x180008cfc  test    r8, r8
0x180008cff  jz      short loc_180008D14
0x180008d01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008d05  inc     rax
0x180008d08  cmp     byte ptr [r8+rax], 0
0x180008d0d  jnz     short loc_180008D05
0x180008d0f  inc     rax
0x180008d12  jmp     short loc_180008D19
0x180008d14  mov     eax, 5
0x180008d19  mov     [rsp+78h+var_18], 0
0x180008d22  lea     r9, aNull; "NULL"
0x180008d29  mov     r10d, 4
0x180008d2f  test    r8, r8
0x180008d32  mov     [rsp+78h+var_20], r10
0x180008d37  cmovz   r8, r9
0x180008d3b  lea     r9, [rsp+78h+arg_30]
0x180008d43  mov     [rsp+78h+var_28], r9
0x180008d48  mov     [rsp+78h+var_30], rax
0x180008d4d  lea     rax, [rsp+78h+arg_20]
0x180008d55  mov     [rsp+78h+var_38], r8
0x180008d5a  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids; MessageGuid
0x180008d61  mov     [rsp+78h+var_40], r10
0x180008d66  mov     [rsp+78h+var_48], rax
0x180008d6b  lea     rax, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180008d72  movzx   r9d, dx; MessageNumber
0x180008d76  lea     edx, [r10+27h]; MessageFlags
0x180008d7a  mov     [rsp+78h+var_50], 2Ah ; '*'
0x180008d83  mov     [rsp+78h+var_58], rax
0x180008d88  call    cs:__imp_TraceMessage
0x180008d8e  add     rsp, 78h
0x180008d92  retn
```
