# WPP_SF_qSd

- ea: `0x18000cbc0`
- end: `0x18000cc53`
- name: `WPP_SF_qSd`
- size: `147`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6e4`
- `0x18000e7d0`
- `0x18000f3ec`
- `0x180014230`
- `0x18001b428`
- `0x18001c1d0`

## callees

- `0x18000cbc0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000cc48`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000cc48`

## pseudocode

```c
ULONG WPP_SF_qSd(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  const wchar_t *v9; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

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
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, v3, v5, va1, 4, 0);
}

```

## disassembly

```asm
0x18000cbc0  mov     [rsp+arg_18], r9
0x18000cbc5  sub     rsp, 68h
0x18000cbc9  mov     r9, [rsp+68h+arg_20]
0x18000cbd1  xor     r11d, r11d
0x18000cbd4  test    r9, r9
0x18000cbd7  jz      short loc_18000CBF1
0x18000cbd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cbdd  inc     rax
0x18000cbe0  cmp     [r9+rax*2], r11w
0x18000cbe5  jnz     short loc_18000CBDD
0x18000cbe7  lea     rax, ds:2[rax*2]
0x18000cbef  jmp     short loc_18000CBF6
0x18000cbf1  mov     eax, 0Ah
0x18000cbf6  mov     [rsp+68h+var_18], r11
0x18000cbfb  lea     r10, aNull_0; "NULL"
0x18000cc02  mov     [rsp+68h+var_20], 4
0x18000cc0b  test    r9, r9
0x18000cc0e  cmovz   r9, r10
0x18000cc12  lea     r10, [rsp+68h+arg_28]
0x18000cc1a  mov     [rsp+68h+var_28], r10
0x18000cc1f  mov     [rsp+68h+var_30], rax
0x18000cc24  lea     rax, [rsp+68h+arg_18]
0x18000cc2c  mov     [rsp+68h+var_38], r9
0x18000cc31  movzx   r9d, dx; MessageNumber
0x18000cc35  mov     edx, 2Bh ; '+'; MessageFlags
0x18000cc3a  mov     [rsp+68h+var_40], 8
0x18000cc43  mov     [rsp+68h+var_48], rax
0x18000cc48  call    cs:__imp_TraceMessage
0x18000cc4e  add     rsp, 68h
0x18000cc52  retn
```
