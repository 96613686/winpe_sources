# WPP_SF_ss

- ea: `0x1800107ac`
- end: `0x180010840`
- name: `WPP_SF_ss`
- size: `148`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e80`
- `0x1800086e0`
- `0x18000c210`
- `0x18000c5d4`

## callees

- `0x1800107ac`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18001082f`
- `ADVAPI32!TraceMessage` at `0x18001082f`

## pseudocode

```c
ULONG __fastcall WPP_SF_ss(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, const char *a5)
{
  const char *v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 5;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v9 = 5;
  }
  if ( !a5 )
    v5 = "NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = v6 + 1;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v7, v5, v9, 0);
}

```

## disassembly

```asm
0x1800107ac  mov     [rsp+arg_0], rbx
0x1800107b1  push    rsi
0x1800107b2  sub     rsp, 50h
0x1800107b6  mov     r11, [rsp+58h+arg_20]
0x1800107be  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800107c2  mov     ebx, 5
0x1800107c7  test    r11, r11
0x1800107ca  jz      short loc_1800107DE
0x1800107cc  mov     rax, r10
0x1800107cf  inc     rax
0x1800107d2  cmp     byte ptr [r11+rax], 0
0x1800107d7  jnz     short loc_1800107CF
0x1800107d9  inc     rax
0x1800107dc  jmp     short loc_1800107E1
0x1800107de  mov     rax, rbx
0x1800107e1  test    r11, r11
0x1800107e4  lea     rsi, aNull; "NULL"
0x1800107eb  cmovz   r11, rsi
0x1800107ef  test    r9, r9
0x1800107f2  jz      short loc_180010805
0x1800107f4  inc     r10
0x1800107f7  cmp     byte ptr [r9+r10], 0
0x1800107fc  jnz     short loc_1800107F4
0x1800107fe  lea     rbx, [r10+1]
0x180010802  test    r9, r9
0x180010805  mov     [rsp+58h+var_18], 0
0x18001080e  cmovz   r9, rsi
0x180010812  mov     [rsp+58h+var_20], rax
0x180010817  mov     [rsp+58h+var_28], r11
0x18001081c  mov     [rsp+58h+var_30], rbx
0x180010821  mov     [rsp+58h+var_38], r9
0x180010826  movzx   r9d, dx; MessageNumber
0x18001082a  mov     edx, 2Bh ; '+'; MessageFlags
0x18001082f  call    cs:__imp_TraceMessage
0x180010835  mov     rbx, [rsp+58h+arg_0]
0x18001083a  add     rsp, 50h
0x18001083e  pop     rsi
0x18001083f  retn
```
