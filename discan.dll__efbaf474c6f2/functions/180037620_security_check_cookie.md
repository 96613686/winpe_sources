# __security_check_cookie

- ea: `0x180037620`
- end: `0x18003763e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001070`
- `0x1800010f4`
- `0x180001194`
- `0x180001354`
- `0x180001428`
- `0x18000150c`
- `0x180001740`
- `0x180002934`
- `0x180002a5c`
- `0x180006ba4`
- `0x180006d40`
- `0x180008a6c`
- `0x180008e48`
- `0x1800090a4`
- `0x180009960`
- `0x180009bc4`
- `0x18000a2a4`
- `0x18000a5f4`
- `0x18000b6bc`
- `0x18000b9a8`
- `0x18000bc5c`
- `0x18000be0c`
- `0x18000beec`
- `0x18000d2ec`
- `0x18000d4f0`
- `0x18000d730`
- `0x18000d9bc`
- `0x18000e2f8`
- `0x18000e574`
- `0x18000e748`
- `0x18000ef90`
- `0x18000fd70`
- `0x18001018c`
- `0x180010c7c`
- `0x180010db0`
- `0x180010ea8`
- `0x180011190`
- `0x180011414`
- `0x180011508`
- `0x180011624`
- `0x180011914`
- `0x180011ba0`
- `0x180011c8c`
- `0x180012a44`
- `0x180012ccc`
- `0x180013b48`
- `0x1800148f4`
- `0x180015940`
- `0x180018130`

## callees

- `0x180002370`
- `0x180037620`

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
0x180037620  cmp     rcx, cs:__security_cookie
0x180037627  jnz     short ReportFailure
0x180037629  rol     rcx, 10h
0x18003762d  test    cx, 0FFFFh
0x180037632  jnz     short RestoreRcx
0x180037634  retn
0x180037635  ror     rcx, 10h
0x180037639  jmp     __report_gsfailure
```
