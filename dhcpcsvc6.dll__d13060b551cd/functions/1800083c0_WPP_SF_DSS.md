# WPP_SF_DSS

- ea: `0x1800083c0`
- end: `0x180008484`
- name: `WPP_SF_DSS`
- size: `196`
- prototype: `ULONG __fastcall(__int64, USHORT, __int64, int, const wchar_t *, const wchar_t *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180004870`
- `0x180004ad0`
- `0x180004e10`
- `0x180005040`
- `0x180005270`
- `0x180005640`
- `0x180005b30`
- `0x180005ec0`
- `0x1800062f0`
- `0x180006820`
- `0x180006cb0`

## callees

- `0x180002ec0`
- `0x1800083c0`

## pseudocode

```c
ULONG __fastcall WPP_SF_DSS(__int64 a1, USHORT a2, __int64 a3, int a4, const wchar_t *a5, const wchar_t *a6)
{
  const wchar_t *v6; // r8
  __int64 v7; // rcx
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rdx
  const wchar_t *v12; // rax
  bool v13; // zf
  int v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = a4;
  v6 = a6;
  v7 = -1;
  v9 = 10;
  if ( a6 )
  {
    v10 = -1;
    do
      v13 = a6[++v10] == 0;
    while ( !v13 );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v12 = a5;
  if ( !a6 )
    v6 = L"NULL";
  v13 = a5 == 0;
  if ( a5 )
  {
    do
      v13 = a5[++v7] == 0;
    while ( !v13 );
    v9 = 2 * v7 + 2;
    v13 = a5 == 0;
  }
  if ( v13 )
    v12 = L"NULL";
  return FastWppTraceMessage(
           1028,
           a2,
           (ULONGLONG)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
           &v15,
           4,
           v12,
           v9,
           v6,
           v11,
           0);
}

```

## disassembly

```asm
0x1800083c0  mov     [rsp+arg_18], r9d
0x1800083c5  sub     rsp, 58h
0x1800083c9  mov     r8, [rsp+58h+arg_28]
0x1800083d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800083d8  movzx   r10d, dx
0x1800083dc  mov     r9d, 0Ah
0x1800083e2  test    r8, r8
0x1800083e5  jz      loc_18000847F
0x1800083eb  mov     rax, rcx
0x1800083ee  xchg    ax, ax
0x1800083f0  cmp     word ptr [r8+rax*2+2], 0
0x1800083f7  lea     rax, [rax+1]
0x1800083fb  jnz     short loc_1800083F0
0x1800083fd  lea     rdx, ds:2[rax*2]
0x180008405  mov     rax, [rsp+58h+arg_20]
0x18000840d  lea     r11, aNull; "NULL"
0x180008414  test    r8, r8
0x180008417  cmovz   r8, r11
0x18000841b  test    rax, rax
0x18000841e  jz      short loc_180008437
0x180008420  cmp     word ptr [rax+rcx*2+2], 0
0x180008426  lea     rcx, [rcx+1]
0x18000842a  jnz     short loc_180008420
0x18000842c  lea     r9, ds:2[rcx*2]
0x180008434  test    rax, rax
0x180008437  mov     [rsp+58h+var_10], 0
0x180008440  cmovz   rax, r11
0x180008444  mov     [rsp+58h+var_18], rdx
0x180008449  mov     ecx, 404h
0x18000844e  mov     [rsp+58h+var_20], r8
0x180008453  mov     edx, r10d
0x180008456  mov     [rsp+58h+var_28], r9
0x18000845b  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180008462  mov     [rsp+58h+var_30], rax
0x180008467  lea     r9, [rsp+58h+arg_18]
0x18000846c  mov     [rsp+58h+var_38], 4
0x180008475  call    FastWppTraceMessage
0x18000847a  add     rsp, 58h
0x18000847e  retn
0x18000847f  mov     rdx, r9
0x180008482  jmp     short loc_180008405
```
