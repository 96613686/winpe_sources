# WPP_SF_DS

- ea: `0x180033a9c`
- end: `0x180033b0b`
- name: `WPP_SF_DS`
- size: `111`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ed8`
- `0x180008f80`
- `0x1800097f0`
- `0x18001189c`
- `0x180011b98`
- `0x18001b314`
- `0x18001c0e4`
- `0x180020d50`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`
- `0x18002aa34`

## callees

- `0x180017a20`
- `0x180033a9c`

## pseudocode

```c
ULONG __fastcall WPP_SF_DS(__int16 a1, USHORT a2, ULONGLONG a3, int a4, const wchar_t *a5)
{
  const wchar_t *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = a4;
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
  return FastWppTraceMessage(a1, a2, a3, &v9, 4, v5, v7, 0);
}

```

## disassembly

```asm
0x180033a9c  mov     [rsp+arg_18], r9d
0x180033aa1  sub     rsp, 48h
0x180033aa5  mov     r9, [rsp+48h+arg_20]
0x180033aaa  xor     r11d, r11d
0x180033aad  test    r9, r9
0x180033ab0  jz      short loc_180033B04
0x180033ab2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033ab6  inc     rax
0x180033ab9  cmp     [r9+rax*2], r11w
0x180033abe  jnz     short loc_180033AB6
0x180033ac0  lea     rax, ds:2[rax*2]
0x180033ac8  mov     [rsp+48h+var_10], r11
0x180033acd  lea     r10, aNull_0; "NULL"
0x180033ad4  test    r9, r9
0x180033ad7  mov     [rsp+48h+var_18], rax
0x180033adc  movzx   edx, dx
0x180033adf  cmovz   r9, r10
0x180033ae3  movzx   ecx, cx
0x180033ae6  mov     [rsp+48h+var_20], r9
0x180033aeb  lea     r9, [rsp+48h+arg_18]
0x180033af0  mov     [rsp+48h+var_28], 4
0x180033af9  call    FastWppTraceMessage
0x180033afe  add     rsp, 48h
0x180033b02  retn
0x180033b04  mov     eax, 0Ah
0x180033b09  jmp     short loc_180033AC8
```
