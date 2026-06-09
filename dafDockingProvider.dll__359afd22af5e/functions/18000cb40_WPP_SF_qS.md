# WPP_SF_qS

- ea: `0x18000cb40`
- end: `0x18000cbba`
- name: `WPP_SF_qS`
- size: `122`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c680`
- `0x18000c6e4`
- `0x18000c970`
- `0x18000dda0`
- `0x18000f3ec`
- `0x1800112b4`
- `0x180011c2c`
- `0x180011ee8`
- `0x180011ff8`
- `0x180012180`
- `0x180012ddc`
- `0x180015848`
- `0x180016374`
- `0x18001884c`
- `0x180019260`
- `0x1800195cc`
- `0x18001c1d0`
- `0x18001d233`
- `0x18001d299`
- `0x18001d335`
- `0x18001d39b`
- `0x18001d425`
- `0x18001d48b`
- `0x18001d503`
- `0x18001d569`

## callees

- `0x18000cb40`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000cbaf`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000cbaf`

## pseudocode

```c
ULONG WPP_SF_qS(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  const wchar_t *v9; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  v9 = va_arg(va1, const wchar_t *);
  v3 = v9;
  if ( v9 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v9[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !v9 )
    v3 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, v3, v5, 0);
}

```

## disassembly

```asm
0x18000cb40  mov     [rsp+arg_18], r9
0x18000cb45  sub     rsp, 58h
0x18000cb49  mov     r9, [rsp+58h+arg_20]
0x18000cb51  xor     r11d, r11d
0x18000cb54  test    r9, r9
0x18000cb57  jz      short loc_18000CB71
0x18000cb59  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cb5d  inc     rax
0x18000cb60  cmp     [r9+rax*2], r11w
0x18000cb65  jnz     short loc_18000CB5D
0x18000cb67  lea     rax, ds:2[rax*2]
0x18000cb6f  jmp     short loc_18000CB76
0x18000cb71  mov     eax, 0Ah
0x18000cb76  mov     [rsp+58h+var_18], r11
0x18000cb7b  lea     r10, aNull_0; "NULL"
0x18000cb82  mov     [rsp+58h+var_20], rax
0x18000cb87  test    r9, r9
0x18000cb8a  lea     rax, [rsp+58h+arg_18]
0x18000cb8f  cmovz   r9, r10
0x18000cb93  mov     [rsp+58h+var_28], r9
0x18000cb98  movzx   r9d, dx; MessageNumber
0x18000cb9c  mov     edx, 2Bh ; '+'; MessageFlags
0x18000cba1  mov     [rsp+58h+var_30], 8
0x18000cbaa  mov     [rsp+58h+var_38], rax
0x18000cbaf  call    cs:__imp_TraceMessage
0x18000cbb5  add     rsp, 58h
0x18000cbb9  retn
```
