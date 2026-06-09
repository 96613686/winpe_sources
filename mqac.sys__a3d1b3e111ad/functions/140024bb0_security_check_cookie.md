# __security_check_cookie

- ea: `0x140024bb0`
- end: `0x140024bce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001df4`
- `0x140001f7c`
- `0x140002094`
- `0x140002950`
- `0x14000713c`
- `0x14000881c`
- `0x140008b78`
- `0x14000bb00`
- `0x14000cef8`
- `0x14000d42c`
- `0x14000d558`
- `0x1400118ec`
- `0x140018644`
- `0x140018810`
- `0x14001cd90`
- `0x14001e768`
- `0x1400209b8`
- `0x140024a0c`
- `0x14002f8f0`
- `0x140030138`

## callees

- `0x140001070`
- `0x140024bb0`

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
0x140024bb0  cmp     rcx, cs:__security_cookie
0x140024bb7  jnz     short ReportFailure
0x140024bb9  rol     rcx, 10h
0x140024bbd  test    cx, 0FFFFh
0x140024bc2  jnz     short RestoreRcx
0x140024bc4  retn
0x140024bc5  ror     rcx, 10h; StackCookie
0x140024bc9  jmp     __report_gsfailure
```
