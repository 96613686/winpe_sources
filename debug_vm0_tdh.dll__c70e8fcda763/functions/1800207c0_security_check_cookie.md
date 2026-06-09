# __security_check_cookie

- ea: `0x1800207c0`
- end: `0x1800207de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `110`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x180001730`
- `0x180003270`
- `0x180003940`
- `0x180004fb0`
- `0x180005ec0`
- `0x180007e78`
- `0x180008970`
- `0x180009710`
- `0x18000ba44`
- `0x18000d824`
- `0x18000dcb0`
- `0x18000e7f4`
- `0x18000e928`
- `0x18000ed38`
- `0x18000eed0`
- `0x18000ef7c`
- `0x18000f040`
- `0x18000f250`
- `0x18000f3f4`
- `0x18000f4e4`
- `0x18000f648`
- `0x18000f870`
- `0x18000faf0`
- `0x180010490`
- `0x1800110f0`
- `0x1800117c8`
- `0x180012b70`
- `0x180012c34`
- `0x180012d9c`
- `0x180012e50`
- `0x180013ca4`
- `0x18001443c`
- `0x180014ff4`
- `0x180015e08`
- `0x180017070`
- `0x180018484`
- `0x18001a15c`
- `0x18001a390`
- `0x18001a594`
- `0x18001a964`
- `0x18001b79c`
- `0x18001bf7c`
- `0x18001d2e0`
- `0x18001df64`
- `0x18001e970`
- `0x18001f48c`
- `0x18001f748`
- `0x180021ea0`
- `0x1800220f0`

## callees

- `0x1800207c0`
- `0x180020840`

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
0x1800207c0  cmp     rcx, cs:__security_cookie
0x1800207c7  jnz     short ReportFailure
0x1800207c9  rol     rcx, 10h
0x1800207cd  test    cx, 0FFFFh
0x1800207d2  jnz     short RestoreRcx
0x1800207d4  retn
0x1800207d5  ror     rcx, 10h; StackCookie
0x1800207d9  jmp     __report_gsfailure
```
