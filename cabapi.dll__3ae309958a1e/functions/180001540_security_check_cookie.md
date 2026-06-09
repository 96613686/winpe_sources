# __security_check_cookie

- ea: `0x180001540`
- end: `0x18000155e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `76`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002a18`
- `0x180002cb4`
- `0x180003a68`
- `0x180003e38`
- `0x1800043c4`
- `0x180004760`
- `0x180004a34`
- `0x180005074`
- `0x180005110`
- `0x18000607c`
- `0x18000615c`
- `0x180006890`
- `0x1800069c0`
- `0x180006ac0`
- `0x180006b60`
- `0x180006d20`
- `0x180006fb0`
- `0x1800070f0`
- `0x180007220`
- `0x180007340`
- `0x180007490`
- `0x1800076f0`
- `0x1800085ac`
- `0x1800088dc`
- `0x180008c24`
- `0x180008d80`
- `0x180008fd8`
- `0x180009b60`
- `0x180009c20`
- `0x180009da4`
- `0x180009eac`
- `0x18000a09c`
- `0x18000a400`
- `0x18000a764`
- `0x18000b34c`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000b84c`
- `0x18000be70`
- `0x18000bfdc`
- `0x18000c060`
- `0x18000c38c`
- `0x18000c48c`
- `0x18000c8e0`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d590`
- `0x18000d7f0`

## callees

- `0x180001540`
- `0x180001b80`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001540  cmp     rcx, cs:__security_cookie
0x180001547  jnz     short ReportFailure
0x180001549  rol     rcx, 10h
0x18000154d  test    cx, 0FFFFh
0x180001552  jnz     short RestoreRcx
0x180001554  retn
0x180001555  ror     rcx, 10h; StackCookie
0x180001559  jmp     __report_gsfailure
```
