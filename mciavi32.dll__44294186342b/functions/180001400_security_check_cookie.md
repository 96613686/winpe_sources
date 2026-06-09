# __security_check_cookie

- ea: `0x180001400`
- end: `0x18000141e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f7c`
- `0x180002c2c`
- `0x180002d0c`
- `0x180002db4`
- `0x180003348`
- `0x180003eb8`
- `0x1800051e8`
- `0x180005524`
- `0x180005c6c`
- `0x1800060a0`
- `0x180006f50`
- `0x1800075cc`
- `0x1800078e4`
- `0x180007dd8`
- `0x1800090e0`
- `0x180009190`
- `0x180009344`
- `0x180009860`
- `0x180009c00`
- `0x18000a85c`
- `0x18000ae48`
- `0x18000b0d8`
- `0x18000b2f0`
- `0x18000b840`
- `0x18000bbb4`
- `0x18000c6b8`
- `0x18000c830`
- `0x18000ca00`
- `0x18000cce4`
- `0x18000cda8`
- `0x18000d220`
- `0x18000d6bc`
- `0x18000d7b0`
- `0x18000db04`
- `0x18000dcd0`
- `0x18000ef88`
- `0x18000f050`
- `0x18000fad8`
- `0x18000fce0`
- `0x1800103ac`
- `0x18001065c`
- `0x180010710`
- `0x180010acc`
- `0x180010bcc`
- `0x180010cd4`
- `0x180011010`
- `0x1800112a0`
- `0x180011a00`
- `0x180011cd4`
- `0x180011e28`

## callees

- `0x180001400`
- `0x180001430`

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
0x180001400  cmp     rcx, cs:__security_cookie
0x180001407  jnz     short ReportFailure
0x180001409  rol     rcx, 10h
0x18000140d  test    cx, 0FFFFh
0x180001412  jnz     short RestoreRcx
0x180001414  retn
0x180001415  ror     rcx, 10h; StackCookie
0x180001419  jmp     __report_gsfailure
```
