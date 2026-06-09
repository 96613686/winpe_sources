# __security_check_cookie

- ea: `0x18000cd10`
- end: `0x18000cd2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b70`
- `0x180002f00`
- `0x180003110`
- `0x1800036a0`
- `0x1800037c4`
- `0x180003950`
- `0x1800040fc`
- `0x180004398`
- `0x180004d1c`
- `0x1800050c0`
- `0x180005490`
- `0x1800056f4`
- `0x180005fd4`
- `0x180006444`
- `0x180006700`
- `0x1800069e0`
- `0x180007080`
- `0x180007630`
- `0x180008178`
- `0x1800083f8`
- `0x180008504`
- `0x180008eac`
- `0x180009cc0`
- `0x18000a6c0`
- `0x18000a9cc`
- `0x18000ad24`
- `0x18000b710`
- `0x18000b868`
- `0x18000c008`
- `0x18000cbe0`

## callees

- `0x180001a90`
- `0x18000cd10`

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
0x18000cd10  cmp     rcx, cs:__security_cookie
0x18000cd17  jnz     short ReportFailure
0x18000cd19  rol     rcx, 10h
0x18000cd1d  test    cx, 0FFFFh
0x18000cd22  jnz     short RestoreRcx
0x18000cd24  retn
0x18000cd25  ror     rcx, 10h
0x18000cd29  jmp     __report_gsfailure
```
