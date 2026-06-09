# __security_check_cookie

- ea: `0x1800021d0`
- end: `0x1800021ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x180002fb0`
- `0x1800031b0`
- `0x180003430`
- `0x180003898`
- `0x180003fac`
- `0x180004258`
- `0x180004604`
- `0x180004998`
- `0x180004d74`
- `0x180005070`
- `0x180005584`
- `0x180005900`
- `0x18000766c`
- `0x180007b30`
- `0x1800088ac`
- `0x18000904c`
- `0x180009954`
- `0x18000aa00`
- `0x18000ab0c`
- `0x18000b4ac`
- `0x18000c86c`
- `0x18000cb14`
- `0x18000ed80`
- `0x18000f688`
- `0x18000f900`
- `0x180013ae0`
- `0x180013bd8`
- `0x180014740`
- `0x1800148b8`
- `0x1800149e8`
- `0x180015de0`
- `0x180016644`
- `0x1800167a0`
- `0x180018e1c`
- `0x180019794`
- `0x180019dc4`
- `0x18001a3a0`
- `0x18001a704`
- `0x18001aee0`
- `0x18001b108`
- `0x18001c57c`
- `0x18001ccc4`
- `0x18001cd90`
- `0x18001d040`
- `0x18001e4c8`
- `0x18001eda4`
- `0x18001f924`

## callees

- `0x1800021d0`
- `0x180002790`

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
0x1800021d0  cmp     rcx, cs:__security_cookie
0x1800021d7  jnz     short ReportFailure
0x1800021d9  rol     rcx, 10h
0x1800021dd  test    cx, 0FFFFh
0x1800021e2  jnz     short RestoreRcx
0x1800021e4  retn
0x1800021e5  ror     rcx, 10h; StackCookie
0x1800021e9  jmp     __report_gsfailure
```
