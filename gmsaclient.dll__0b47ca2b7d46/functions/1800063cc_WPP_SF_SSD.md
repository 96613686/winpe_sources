# WPP_SF_SSD

- ea: `0x1800063cc`
- end: `0x18000648e`
- name: `WPP_SF_SSD`
- size: `194`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002380`
- `0x180002e18`
- `0x1800036c0`
- `0x180003e84`
- `0x180005e70`
- `0x180007064`

## callees

- `0x1800063cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006471`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006471`

## pseudocode

```c
ULONG WPP_SF_SSD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v7, v5, v9, va, 4, 0);
}

```

## disassembly

```asm
0x1800063cc  mov     [rsp+arg_0], rbx
0x1800063d1  mov     [rsp+arg_8], rsi
0x1800063d6  push    rdi
0x1800063d7  sub     rsp, 60h
0x1800063db  mov     r11, [rsp+68h+arg_20]
0x1800063e3  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800063e7  xor     edi, edi
0x1800063e9  mov     ebx, 0Ah
0x1800063ee  test    r11, r11
0x1800063f1  jz      short loc_18000640A
0x1800063f3  mov     rax, r10
0x1800063f6  inc     rax
0x1800063f9  cmp     [r11+rax*2], di
0x1800063fe  jnz     short loc_1800063F6
0x180006400  lea     rax, ds:2[rax*2]
0x180006408  jmp     short loc_18000640D
0x18000640a  mov     rax, rbx
0x18000640d  test    r11, r11
0x180006410  lea     rsi, aNull; "NULL"
0x180006417  cmovz   r11, rsi
0x18000641b  test    r9, r9
0x18000641e  jz      short loc_180006435
0x180006420  inc     r10
0x180006423  cmp     [r9+r10*2], di
0x180006428  jnz     short loc_180006420
0x18000642a  lea     rbx, ds:2[r10*2]
0x180006432  test    r9, r9
0x180006435  mov     [rsp+68h+var_18], rdi
0x18000643a  lea     r10, [rsp+68h+arg_28]
0x180006442  mov     [rsp+68h+var_20], 4
0x18000644b  cmovz   r9, rsi
0x18000644f  mov     [rsp+68h+var_28], r10
0x180006454  mov     [rsp+68h+var_30], rax
0x180006459  mov     [rsp+68h+var_38], r11
0x18000645e  mov     [rsp+68h+var_40], rbx
0x180006463  mov     [rsp+68h+var_48], r9
0x180006468  movzx   r9d, dx; MessageNumber
0x18000646c  mov     edx, 2Bh ; '+'; MessageFlags
0x180006471  call    cs:__imp_TraceMessage
0x180006478  nop     dword ptr [rax+rax+00h]
0x18000647d  mov     rbx, [rsp+68h+arg_0]
0x180006482  mov     rsi, [rsp+68h+arg_8]
0x180006487  add     rsp, 60h
0x18000648b  pop     rdi
0x18000648c  retn
```
