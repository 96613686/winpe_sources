# __security_check_cookie

- ea: `0x18001ac90`
- end: `0x18001acae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `72`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000132c`
- `0x1800015e0`
- `0x180001908`
- `0x180001978`
- `0x180001a08`
- `0x180001a98`
- `0x180001d90`
- `0x180002a70`
- `0x180002c80`
- `0x1800031ec`
- `0x180003488`
- `0x180003698`
- `0x180003c38`
- `0x180003e00`
- `0x180004284`
- `0x180004680`
- `0x180006c50`
- `0x1800075f4`
- `0x180007800`
- `0x1800079b8`
- `0x180008714`
- `0x1800087e8`
- `0x1800089c8`
- `0x180009544`
- `0x180009978`
- `0x18000a688`
- `0x18000a8dc`
- `0x18000b334`
- `0x18000b498`
- `0x18000b888`
- `0x18000bad4`
- `0x18000bc9c`
- `0x18000bdd4`
- `0x18000c1d0`
- `0x18000c588`
- `0x18000c874`
- `0x18000d45c`
- `0x18000de24`
- `0x18000e214`
- `0x18000e34c`
- `0x18000e9e8`
- `0x18000ec50`
- `0x180010454`
- `0x18001077c`
- `0x1800108e4`
- `0x180010fd4`
- `0x1800118bc`
- `0x180011f48`
- `0x180012640`

## callees

- `0x1800028c0`
- `0x18001ac90`

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
0x18001ac90  cmp     rcx, cs:__security_cookie
0x18001ac97  jnz     short ReportFailure
0x18001ac99  rol     rcx, 10h
0x18001ac9d  test    cx, 0FFFFh
0x18001aca2  jnz     short RestoreRcx
0x18001aca4  retn
0x18001aca5  ror     rcx, 10h
0x18001aca9  jmp     __report_gsfailure
```
