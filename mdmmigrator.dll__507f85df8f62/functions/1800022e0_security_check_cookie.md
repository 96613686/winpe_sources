# __security_check_cookie

- ea: `0x1800022e0`
- end: `0x1800022fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `82`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000113c`
- `0x18000125c`
- `0x180001468`
- `0x180001514`
- `0x180001628`
- `0x18000174c`
- `0x180001824`
- `0x1800018cc`
- `0x1800019e4`
- `0x180001b0c`
- `0x180001bd0`
- `0x180002e80`
- `0x180003100`
- `0x180003520`
- `0x180003e50`
- `0x1800040fc`
- `0x1800046a8`
- `0x180004a78`
- `0x1800050a4`
- `0x180005420`
- `0x180006d7c`
- `0x180007250`
- `0x180007890`
- `0x18000797c`
- `0x1800083ec`
- `0x180008520`
- `0x180008940`
- `0x180009f44`
- `0x18000a2a4`
- `0x18000a8a8`
- `0x18000ac08`
- `0x18000be00`
- `0x18000c214`
- `0x18000c740`
- `0x18000ca90`
- `0x18000cb50`
- `0x18000da88`
- `0x18000de8c`
- `0x18000e284`
- `0x18000eae0`
- `0x18000ee18`
- `0x18000f004`
- `0x18000f5c4`
- `0x180010170`
- `0x180010610`
- `0x180010864`
- `0x180010dc0`
- `0x180011610`
- `0x180011ccc`

## callees

- `0x1800022e0`
- `0x1800028a0`

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
0x1800022e0  cmp     rcx, cs:__security_cookie
0x1800022e7  jnz     short ReportFailure
0x1800022e9  rol     rcx, 10h
0x1800022ed  test    cx, 0FFFFh
0x1800022f2  jnz     short RestoreRcx
0x1800022f4  retn
0x1800022f5  ror     rcx, 10h; StackCookie
0x1800022f9  jmp     __report_gsfailure
```
