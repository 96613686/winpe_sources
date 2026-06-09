# RtlReportErrorOrigination

- ea: `0x180012fd8`
- end: `0x180013038`
- name: `RtlReportErrorOrigination`
- size: `96`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f940`
- `0x18000fa80`
- `0x18000fc8c`
- `0x180013040`
- `0x180013194`
- `0x180013394`
- `0x1800135f4`
- `0x180013774`

## callees

- `0x180012fd8`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180013021`
- `ntdll!DbgPrintEx` at `0x180013021`
- `ntdll!RtlRaiseStatus` at `0x18001302c`
- `ntdll!RtlRaiseStatus` at `0x18001302c`

## pseudocode

```c
void __fastcall RtlReportErrorOrigination(__int64 a1, __int64 a2, int a3)
{
  int v3; // edx
  const char *v4; // rax
  const char *v5; // r9

  if ( a3 == g_NTSTATUS_to_break_on )
    __debugbreak();
  if ( a3 == -1073741595 )
  {
    if ( a1 )
    {
      v3 = *(_DWORD *)(a1 + 16);
      v4 = *(const char **)a1;
      v5 = *(const char **)(a1 + 24);
    }
    else
    {
      v5 = (const char *)&pszCabPath;
      v3 = 0;
      v4 = (const char *)&pszCabPath;
    }
    DbgPrintEx(0x65u, 0, "\n*** Assertion failed: %s\n***   Source File: %s, line %ld\n\n", v5, v4, v3);
    RtlRaiseStatus(-1073740768);
  }
}

```

## disassembly

```asm
0x180012fd8  sub     rsp, 38h
0x180012fdc  cmp     r8d, cs:g_NTSTATUS_to_break_on
0x180012fe3  jnz     short loc_180012FE6
0x180012fe5  int     3; Trap to Debugger
0x180012fe6  cmp     r8d, 0C00000E5h
0x180012fed  jnz     short loc_180013033
0x180012fef  test    rcx, rcx
0x180012ff2  jz      short loc_180013000
0x180012ff4  mov     edx, [rcx+10h]
0x180012ff7  mov     rax, [rcx]
0x180012ffa  mov     r9, [rcx+18h]
0x180012ffe  jmp     short loc_18001300C
0x180013000  lea     r9, pszCabPath
0x180013007  xor     edx, edx
0x180013009  mov     rax, r9
0x18001300c  mov     [rsp+38h+var_10], edx
0x180013010  lea     r8, aAssertionFaile; "\n*** Assertion failed: %s\n***   Sourc"...
0x180013017  xor     edx, edx; Level
0x180013019  mov     [rsp+38h+var_18], rax
0x18001301e  lea     ecx, [rdx+65h]; ComponentId
0x180013021  call    cs:__imp_DbgPrintEx
0x180013027  mov     ecx, 0C0000420h; Status
0x18001302c  call    cs:__imp_RtlRaiseStatus
0x180013032  int     3; Trap to Debugger
0x180013033  add     rsp, 38h
0x180013037  retn
```
