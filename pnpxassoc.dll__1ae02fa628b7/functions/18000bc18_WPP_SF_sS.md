# WPP_SF_sS

- ea: `0x18000bc18`
- end: `0x18000bc8f`
- name: `WPP_SF_sS`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a480`
- `0x18000b5c0`
- `0x18000c5a0`
- `0x18000ed14`

## callees

- `0x18000bc18`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000bc84`
- `ADVAPI32!TraceMessage` at `0x18000bc84`

## pseudocode

```c
ULONG __fastcall WPP_SF_sS(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, const wchar_t *a5)
{
  const wchar_t *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax

  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, " ", 2, v5, v7, 0);
}

```

## disassembly

```asm
0x18000bc18  sub     rsp, 58h
0x18000bc1c  mov     r9, [rsp+58h+arg_20]
0x18000bc24  xor     r11d, r11d
0x18000bc27  test    r9, r9
0x18000bc2a  jz      short loc_18000BC44
0x18000bc2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bc30  inc     rax
0x18000bc33  cmp     [r9+rax*2], r11w
0x18000bc38  jnz     short loc_18000BC30
0x18000bc3a  lea     rax, ds:2[rax*2]
0x18000bc42  jmp     short loc_18000BC49
0x18000bc44  mov     eax, 0Ah
0x18000bc49  mov     [rsp+58h+var_18], r11
0x18000bc4e  lea     r10, aNull; "NULL"
0x18000bc55  mov     [rsp+58h+var_20], rax
0x18000bc5a  test    r9, r9
0x18000bc5d  lea     rax, asc_180016AC4; " "
0x18000bc64  cmovz   r9, r10
0x18000bc68  mov     [rsp+58h+var_28], r9
0x18000bc6d  movzx   r9d, dx; MessageNumber
0x18000bc71  mov     edx, 2Bh ; '+'; MessageFlags
0x18000bc76  mov     [rsp+58h+var_30], 2
0x18000bc7f  mov     [rsp+58h+var_38], rax
0x18000bc84  call    cs:__imp_TraceMessage
0x18000bc8a  add     rsp, 58h
0x18000bc8e  retn
```
