# __security_check_cookie

- ea: `0x180012e70`
- end: `0x180012e8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `55`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002320`
- `0x18000261c`
- `0x180002a90`
- `0x1800034ec`
- `0x180003884`
- `0x180003cf0`
- `0x18000486c`
- `0x180004914`
- `0x180004a40`
- `0x180005c40`
- `0x180006050`
- `0x1800061c0`
- `0x180006540`
- `0x180006890`
- `0x180006b50`
- `0x180007860`
- `0x180008150`
- `0x180008570`
- `0x1800089e4`
- `0x180008b28`
- `0x180008d00`
- `0x180009d1c`
- `0x18000a020`
- `0x18000b600`
- `0x18000b954`
- `0x18000c220`
- `0x18000c738`
- `0x18000d4e0`
- `0x18000d644`
- `0x18000d710`
- `0x18000da44`
- `0x18000e198`
- `0x18000e4a8`
- `0x18000e8ac`
- `0x18000ea28`
- `0x18000ec64`
- `0x18000ef28`
- `0x18000f074`
- `0x18000f264`
- `0x18000f384`
- `0x18000f64c`
- `0x18000f774`
- `0x18000f9f4`
- `0x18000fb1c`
- `0x18000fe44`
- `0x180010144`
- `0x180010364`
- `0x180010574`
- `0x1800106fc`
- `0x180010970`

## callees

- `0x180001520`
- `0x180012e70`

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
0x180012e70  cmp     rcx, cs:__security_cookie
0x180012e77  jnz     short ReportFailure
0x180012e79  rol     rcx, 10h
0x180012e7d  test    cx, 0FFFFh
0x180012e82  jnz     short RestoreRcx
0x180012e84  retn
0x180012e85  ror     rcx, 10h
0x180012e89  jmp     __report_gsfailure
```
