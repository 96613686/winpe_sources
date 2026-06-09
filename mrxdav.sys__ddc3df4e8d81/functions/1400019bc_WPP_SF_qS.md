# WPP_SF_qS

- ea: `0x1400019bc`
- end: `0x140001a43`
- name: `WPP_SF_qS`
- size: `135`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140010620`
- `0x1400130e0`
- `0x1400145d0`
- `0x140014e00`
- `0x140015900`
- `0x140015c30`
- `0x140017310`
- `0x1400199a0`
- `0x14001b360`
- `0x14001bdf0`
- `0x14001dec0`
- `0x14001e6a0`
- `0x140020090`
- `0x140020660`
- `0x140020e80`
- `0x1400220c0`
- `0x140023530`

## callees

- `0x1400019bc`
- `0x140006880`

## pseudocode

```c
__int64 WPP_SF_qS(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  const wchar_t *v10; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, const wchar_t *);
  v3 = v10;
  if ( v10 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v10[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  if ( !v10 )
    v3 = L"NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           v3,
           v6,
           0);
}

```

## disassembly

```asm
0x1400019bc  mov     [rsp+arg_18], r9
0x1400019c1  sub     rsp, 58h
0x1400019c5  mov     r9, [rsp+58h+arg_20]
0x1400019cd  xor     r11d, r11d
0x1400019d0  mov     r10, rcx
0x1400019d3  test    r9, r9
0x1400019d6  jz      short loc_1400019F0
0x1400019d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400019dc  inc     rax
0x1400019df  cmp     [r9+rax*2], r11w
0x1400019e4  jnz     short loc_1400019DC
0x1400019e6  lea     rcx, ds:2[rax*2]
0x1400019ee  jmp     short loc_1400019F5
0x1400019f0  mov     ecx, 0Ah
0x1400019f5  mov     [rsp+58h+var_18], r11
0x1400019fa  lea     rax, aNull_0; "NULL"
0x140001a01  mov     [rsp+58h+var_20], rcx
0x140001a06  test    r9, r9
0x140001a09  lea     rcx, [rsp+58h+arg_18]
0x140001a0e  cmovz   r9, rax
0x140001a12  mov     rax, cs:pfnWppTraceMessage
0x140001a19  mov     [rsp+58h+var_28], r9
0x140001a1e  movzx   r9d, dx
0x140001a22  mov     edx, 2Bh ; '+'
0x140001a27  mov     [rsp+58h+var_30], 8
0x140001a30  mov     [rsp+58h+var_38], rcx
0x140001a35  mov     rcx, r10
0x140001a38  call    _guard_dispatch_icall
0x140001a3d  add     rsp, 58h
0x140001a41  retn
```
