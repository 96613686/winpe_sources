# __security_check_cookie

- ea: `0x18000be40`
- end: `0x18000be5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `141`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001680`
- `0x1800019a0`
- `0x180001ce0`
- `0x180002410`
- `0x180002b90`
- `0x180002fd0`
- `0x18000392c`
- `0x180004094`
- `0x1800042b0`
- `0x180004824`
- `0x180004a20`
- `0x180004b98`
- `0x180004d30`
- `0x1800051e0`
- `0x180005640`
- `0x1800056f0`
- `0x180006e54`
- `0x1800070a0`
- `0x180007320`
- `0x180007608`
- `0x1800076b0`
- `0x180007898`
- `0x180007968`
- `0x180007ca0`
- `0x18000849c`
- `0x180008888`
- `0x180008a6c`
- `0x180008b8c`
- `0x180008ccc`
- `0x1800091f8`
- `0x18000938c`
- `0x1800095cc`
- `0x18000a2bc`
- `0x18000a59c`
- `0x18000a710`
- `0x18000a918`
- `0x18000af70`
- `0x18000b0d0`
- `0x18000b60c`
- `0x18000b71c`
- `0x18000b928`
- `0x18000d4bc`
- `0x18000d764`
- `0x18000e108`
- `0x18000e274`
- `0x18000e440`
- `0x18000e5d4`
- `0x18000e7c4`
- `0x18000ebd4`
- `0x18000eef8`

## callees

- `0x18000be40`
- `0x18000c270`

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
0x18000be40  cmp     rcx, cs:__security_cookie
0x18000be47  jnz     short ReportFailure
0x18000be49  rol     rcx, 10h
0x18000be4d  test    cx, 0FFFFh
0x18000be52  jnz     short RestoreRcx
0x18000be54  retn
0x18000be55  ror     rcx, 10h; StackCookie
0x18000be59  jmp     __report_gsfailure
```
