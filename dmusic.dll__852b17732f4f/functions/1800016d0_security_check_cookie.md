# __security_check_cookie

- ea: `0x1800016d0`
- end: `0x1800016ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ad4`
- `0x180002d68`
- `0x180003ac8`
- `0x180003e98`
- `0x180004290`
- `0x180004de4`
- `0x180005160`
- `0x1800064a8`
- `0x1800065b4`
- `0x180006fbc`
- `0x1800085ec`
- `0x1800090f0`
- `0x180009218`
- `0x1800094e8`
- `0x18000b274`
- `0x18000b730`
- `0x18000baf0`
- `0x18000c8b0`
- `0x18000cd90`
- `0x18000d8c8`
- `0x18000e178`
- `0x1800127d0`
- `0x180012e60`
- `0x180013580`
- `0x180014530`
- `0x1800151a0`
- `0x180015254`
- `0x180015474`
- `0x180015630`
- `0x180015f2c`
- `0x180016ee8`
- `0x18001afa8`
- `0x18001b590`
- `0x18001bd10`
- `0x18001c7f0`
- `0x18001c970`
- `0x18001cfb0`
- `0x18001daa8`
- `0x18001e0c8`
- `0x18001e2b0`
- `0x18001e528`
- `0x18001f51c`
- `0x180020220`
- `0x180020e30`
- `0x180021600`

## callees

- `0x1800016d0`
- `0x180001ad0`

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
0x1800016d0  cmp     rcx, cs:__security_cookie
0x1800016d7  jnz     short ReportFailure
0x1800016d9  rol     rcx, 10h
0x1800016dd  test    cx, 0FFFFh
0x1800016e2  jnz     short RestoreRcx
0x1800016e4  retn
0x1800016e5  ror     rcx, 10h; StackCookie
0x1800016e9  jmp     __report_gsfailure
```
