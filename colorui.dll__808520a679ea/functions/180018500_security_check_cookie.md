# __security_check_cookie

- ea: `0x180018500`
- end: `0x18001851e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001efc`
- `0x18000204c`
- `0x180002884`
- `0x180002b18`
- `0x180003828`
- `0x180003bf8`
- `0x180004314`
- `0x180004bb4`
- `0x180005c74`
- `0x18000607c`
- `0x180006880`
- `0x180007310`
- `0x180007818`
- `0x180007a98`
- `0x180007ba4`
- `0x180008558`
- `0x18000892c`
- `0x180008a7c`
- `0x180008c0c`
- `0x180008dd0`
- `0x180009e1c`
- `0x18000a47c`
- `0x18000a7ac`
- `0x18000aacc`
- `0x18000b540`
- `0x18000bab8`
- `0x18000bee0`
- `0x18000c018`
- `0x18000c770`
- `0x18000cc44`
- `0x18000d338`
- `0x18000d7dc`
- `0x18000dab4`
- `0x18000de80`
- `0x18000eb00`
- `0x18000f074`
- `0x18000f654`
- `0x180010780`
- `0x180010f58`
- `0x180011050`
- `0x180011318`
- `0x180011514`
- `0x1800117a8`
- `0x180011a34`
- `0x180011fb4`
- `0x180012228`
- `0x180012438`
- `0x180013050`
- `0x180013580`
- `0x180013c00`

## callees

- `0x1800018b0`
- `0x180018500`

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
0x180018500  cmp     rcx, cs:__security_cookie
0x180018507  jnz     short ReportFailure
0x180018509  rol     rcx, 10h
0x18001850d  test    cx, 0FFFFh
0x180018512  jnz     short RestoreRcx
0x180018514  retn
0x180018515  ror     rcx, 10h
0x180018519  jmp     __report_gsfailure
```
