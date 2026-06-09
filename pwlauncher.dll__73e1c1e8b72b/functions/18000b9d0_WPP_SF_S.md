# WPP_SF_S

- ea: `0x18000b9d0`
- end: `0x18000ba2a`
- name: `WPP_SF_S`
- size: `90`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b5d8`
- `0x18000de18`
- `0x18000e430`
- `0x18000e948`
- `0x18000eb10`
- `0x18000ec5c`
- `0x18000ee48`
- `0x18000ef8c`

## callees

- `0x18000b9d0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000ba1f`
- `ADVAPI32!TraceMessage` at `0x18000ba1f`

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
0x18000b9d0  sub     rsp, 48h
0x18000b9d4  xor     r11d, r11d
0x18000b9d7  test    r9, r9
0x18000b9da  jz      short loc_18000B9F4
0x18000b9dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b9e0  inc     rax
0x18000b9e3  cmp     [r9+rax*2], r11w
0x18000b9e8  jnz     short loc_18000B9E0
0x18000b9ea  lea     rax, ds:2[rax*2]
0x18000b9f2  jmp     short loc_18000B9F9
0x18000b9f4  mov     eax, 0Ah
0x18000b9f9  test    r9, r9
0x18000b9fc  mov     [rsp+48h+var_18], r11
0x18000ba01  lea     r10, aNull_0; "NULL"
0x18000ba08  mov     [rsp+48h+var_20], rax
0x18000ba0d  cmovz   r9, r10
0x18000ba11  mov     [rsp+48h+var_28], r9
0x18000ba16  movzx   r9d, dx; MessageNumber
0x18000ba1a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ba1f  call    cs:__imp_TraceMessage
0x18000ba25  add     rsp, 48h
0x18000ba29  retn
```
