# WPP_SF_Sd

- ea: `0x18000d6bc`
- end: `0x18000d72c`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c90`
- `0x18000f2c4`
- `0x18000f3e4`

## callees

- `0x18000d6bc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000d721`
- `ADVAPI32!TraceMessage` at `0x18000d721`

## pseudocode

```c
ULONG WPP_SF_Sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x18000d6bc  sub     rsp, 58h
0x18000d6c0  xor     r11d, r11d
0x18000d6c3  test    r9, r9
0x18000d6c6  jz      short loc_18000D6E0
0x18000d6c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d6cc  inc     rax
0x18000d6cf  cmp     [r9+rax*2], r11w
0x18000d6d4  jnz     short loc_18000D6CC
0x18000d6d6  lea     rax, ds:2[rax*2]
0x18000d6de  jmp     short loc_18000D6E5
0x18000d6e0  mov     eax, 0Ah
0x18000d6e5  mov     [rsp+58h+var_18], r11
0x18000d6ea  lea     r10, aNull; "NULL"
0x18000d6f1  test    r9, r9
0x18000d6f4  mov     [rsp+58h+var_20], 4
0x18000d6fd  cmovz   r9, r10
0x18000d701  lea     r10, [rsp+58h+arg_20]
0x18000d709  mov     [rsp+58h+var_28], r10
0x18000d70e  mov     [rsp+58h+var_30], rax
0x18000d713  mov     [rsp+58h+var_38], r9
0x18000d718  movzx   r9d, dx; MessageNumber
0x18000d71c  mov     edx, 2Bh ; '+'; MessageFlags
0x18000d721  call    cs:__imp_TraceMessage
0x18000d727  add     rsp, 58h
0x18000d72b  retn
```
