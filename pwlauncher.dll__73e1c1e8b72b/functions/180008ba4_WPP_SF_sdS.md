# WPP_SF_sdS

- ea: `0x180008ba4`
- end: `0x180008c38`
- name: `WPP_SF_sdS`
- size: `148`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, __int64, char, const wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005c98`
- `0x180007c78`

## callees

- `0x180008ba4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008c2d`
- `ADVAPI32!TraceMessage` at `0x180008c2d`

## string_xrefs

- `0x180008c18`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
ULONG __fastcall WPP_SF_sdS(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, char a5, const wchar_t *a6)
{
  const wchar_t *v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax

  v6 = a6;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  if ( !a6 )
    v6 = L"NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
           a2,
           "drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
           42,
           &a5,
           4,
           v6,
           v8,
           0);
}

```

## disassembly

```asm
0x180008ba4  sub     rsp, 68h
0x180008ba8  mov     r8, [rsp+68h+arg_28]
0x180008bb0  xor     r10d, r10d
0x180008bb3  test    r8, r8
0x180008bb6  jz      short loc_180008BD0
0x180008bb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008bbc  inc     rax
0x180008bbf  cmp     [r8+rax*2], r10w
0x180008bc4  jnz     short loc_180008BBC
0x180008bc6  lea     rax, ds:2[rax*2]
0x180008bce  jmp     short loc_180008BD5
0x180008bd0  mov     eax, 0Ah
0x180008bd5  mov     [rsp+68h+var_18], r10
0x180008bda  lea     r9, aNull_0; "NULL"
0x180008be1  mov     [rsp+68h+var_20], rax
0x180008be6  test    r8, r8
0x180008be9  lea     rax, [rsp+68h+arg_20]
0x180008bf1  cmovz   r8, r9
0x180008bf5  movzx   r9d, dx; MessageNumber
0x180008bf9  mov     [rsp+68h+var_28], r8
0x180008bfe  mov     edx, 2Bh ; '+'; MessageFlags
0x180008c03  mov     [rsp+68h+var_30], 4
0x180008c0c  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids; MessageGuid
0x180008c13  mov     [rsp+68h+var_38], rax
0x180008c18  lea     rax, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180008c1f  mov     [rsp+68h+var_40], 2Ah ; '*'
0x180008c28  mov     [rsp+68h+var_48], rax
0x180008c2d  call    cs:__imp_TraceMessage
0x180008c33  add     rsp, 68h
0x180008c37  retn
```
