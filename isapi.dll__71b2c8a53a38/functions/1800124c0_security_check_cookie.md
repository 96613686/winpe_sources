# __security_check_cookie

- ea: `0x1800124c0`
- end: `0x1800124de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003bc0`
- `0x180003ef0`
- `0x180004b70`
- `0x1800050fc`
- `0x1800055ac`
- `0x180005640`
- `0x180006970`
- `0x180008118`
- `0x1800097a0`
- `0x18000a1ec`
- `0x18000a820`
- `0x18000b060`
- `0x18000c898`
- `0x18000cc50`
- `0x18000d1cc`
- `0x18000d340`
- `0x18000d880`
- `0x18000df10`
- `0x18000e1bc`
- `0x18000e370`
- `0x18000e600`
- `0x18000eff0`
- `0x18000f5a0`
- `0x18000f91c`
- `0x18000fb14`
- `0x180010250`
- `0x180010cd4`
- `0x180010fa0`
- `0x180011400`
- `0x1800117cc`
- `0x180012400`

## callees

- `0x180001580`
- `0x1800124c0`

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
0x1800124c0  cmp     rcx, cs:__security_cookie
0x1800124c7  jnz     short ReportFailure
0x1800124c9  rol     rcx, 10h
0x1800124cd  test    cx, 0FFFFh
0x1800124d2  jnz     short RestoreRcx
0x1800124d4  retn
0x1800124d5  ror     rcx, 10h
0x1800124d9  jmp     __report_gsfailure
```
