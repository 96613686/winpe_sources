# __security_check_cookie

- ea: `0x18001ed20`
- end: `0x18001ed3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001414`
- `0x180002e00`
- `0x1800032c0`
- `0x180003a10`
- `0x180004404`
- `0x180005bc0`
- `0x180006a48`
- `0x1800070d0`
- `0x180008e60`
- `0x180009db0`
- `0x18000bab8`
- `0x18000bf1c`
- `0x18000d388`
- `0x18000dcf0`
- `0x18000e5ec`
- `0x18000ef54`
- `0x180010480`
- `0x180010574`
- `0x180010b6c`
- `0x180010cd4`
- `0x180010e9c`
- `0x1800119d4`
- `0x180011d88`
- `0x1800131b0`
- `0x180013530`
- `0x180014970`
- `0x180015438`
- `0x1800160bc`
- `0x1800166d8`
- `0x1800169d4`
- `0x180016f70`
- `0x180017b60`
- `0x18001a3b4`
- `0x18001bba4`
- `0x18001e9ec`
- `0x18001ebf0`

## callees

- `0x18000f800`
- `0x18001ed20`

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
0x18001ed20  cmp     rcx, cs:__security_cookie
0x18001ed27  jnz     short ReportFailure
0x18001ed29  rol     rcx, 10h
0x18001ed2d  test    cx, 0FFFFh
0x18001ed32  jnz     short RestoreRcx
0x18001ed34  retn
0x18001ed35  ror     rcx, 10h
0x18001ed39  jmp     __report_gsfailure
```
