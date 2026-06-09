# WPP_SF_S

- ea: `0x1800090dc`
- end: `0x18000913d`
- name: `WPP_SF_S`
- size: `97`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031a4`
- `0x180006890`
- `0x180007860`
- `0x180008150`
- `0x18000a61c`
- `0x18000abcc`
- `0x18000b0d8`
- `0x18000bb40`

## callees

- `0x1800090dc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000912b`
- `ADVAPI32!TraceMessage` at `0x18000912b`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x1800090dc  sub     rsp, 48h
0x1800090e0  xor     r11d, r11d
0x1800090e3  test    r9, r9
0x1800090e6  jz      short loc_180009100
0x1800090e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800090ec  inc     rax
0x1800090ef  cmp     [r9+rax*2], r11w
0x1800090f4  jnz     short loc_1800090EC
0x1800090f6  lea     rax, ds:2[rax*2]
0x1800090fe  jmp     short loc_180009105
0x180009100  mov     eax, 0Ah
0x180009105  test    r9, r9
0x180009108  mov     [rsp+48h+var_18], r11
0x18000910d  lea     r10, aNull_0; "NULL"
0x180009114  mov     [rsp+48h+var_20], rax
0x180009119  cmovz   r9, r10
0x18000911d  mov     [rsp+48h+var_28], r9
0x180009122  movzx   r9d, dx; MessageNumber
0x180009126  mov     edx, 2Bh ; '+'; MessageFlags
0x18000912b  call    cs:__imp_TraceMessage
0x180009132  nop     dword ptr [rax+rax+00h]
0x180009137  add     rsp, 48h
0x18000913b  retn
```
