# __security_check_cookie

- ea: `0x180001460`
- end: `0x18000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `199`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e0c`
- `0x1800023c0`
- `0x180003170`
- `0x18000339c`
- `0x180003568`
- `0x1800036f8`
- `0x18000380c`
- `0x18000423c`
- `0x18000442c`
- `0x1800046e0`
- `0x1800049e4`
- `0x180005054`
- `0x180005380`
- `0x1800055b0`
- `0x180005698`
- `0x180005908`
- `0x18000638c`
- `0x180006970`
- `0x180007020`
- `0x1800071f0`
- `0x180007b40`
- `0x180007bd0`
- `0x180008630`
- `0x180008c70`
- `0x180008d10`
- `0x1800097a0`
- `0x180009920`
- `0x180009aac`
- `0x180009cd0`
- `0x180009fd0`
- `0x18000a280`
- `0x18000a4c0`
- `0x18000a6e0`
- `0x18000a790`
- `0x18000a8c0`
- `0x18000a9f0`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000bc54`
- `0x18000be68`
- `0x18000c050`
- `0x18000c234`
- `0x18000c3e8`
- `0x18000c8d4`
- `0x18000cc7c`
- `0x18000cdc8`
- `0x18000cf3c`
- `0x18000d450`
- `0x18000d6b4`

## callees

- `0x180001460`
- `0x180001490`

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
0x180001460  cmp     rcx, cs:__security_cookie
0x180001467  jnz     short ReportFailure
0x180001469  rol     rcx, 10h
0x18000146d  test    cx, 0FFFFh
0x180001472  jnz     short RestoreRcx
0x180001474  retn
0x180001475  ror     rcx, 10h; StackCookie
0x180001479  jmp     __report_gsfailure
```
