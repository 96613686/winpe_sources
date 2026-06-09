# WPP_SF_DSS

- ea: `0x180012d20`
- end: `0x180012dde`
- name: `WPP_SF_DSS`
- size: `190`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001240`
- `0x180001490`
- `0x180005be0`
- `0x180005d30`
- `0x180006c90`
- `0x180006e10`
- `0x180007010`
- `0x180007480`
- `0x180007950`
- `0x180007c00`
- `0x180008210`
- `0x18000847c`
- `0x180008dd4`
- `0x18000a180`
- `0x18000a950`
- `0x18000ac50`
- `0x18000b180`
- `0x18000b360`
- `0x18000b590`
- `0x18000b7c0`
- `0x18000b9d0`
- `0x18000bd64`
- `0x18000bf80`
- `0x18000c110`
- `0x18000d660`

## callees

- `0x180003e70`
- `0x180012d20`

## pseudocode

```c
ULONG __fastcall WPP_SF_DSS(__int64 a1, USHORT a2, ULONGLONG a3, int a4, const wchar_t *a5, const wchar_t *a6)
{
  const wchar_t *v6; // r9
  __int64 v7; // rcx
  __int64 v9; // r10
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
  return FastWppTraceMessage(1028, a2, a3, &v15, 4, v12, v9, v6, v11, 0);
}

```

## disassembly

```asm
0x180012d20  mov     [rsp+arg_18], r9d
0x180012d25  push    rbx
0x180012d26  sub     rsp, 50h
0x180012d2a  mov     r9, [rsp+58h+arg_28]
0x180012d32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012d39  movzx   r11d, dx
0x180012d3d  mov     r10d, 0Ah
0x180012d43  test    r9, r9
0x180012d46  jz      loc_180012DD9
0x180012d4c  mov     rax, rcx
0x180012d4f  nop
0x180012d50  cmp     word ptr [r9+rax*2+2], 0
0x180012d57  lea     rax, [rax+1]
0x180012d5b  jnz     short loc_180012D50
0x180012d5d  lea     rdx, ds:2[rax*2]
0x180012d65  mov     rax, [rsp+58h+arg_20]
0x180012d6d  lea     rbx, aNull; "NULL"
0x180012d74  test    r9, r9
0x180012d77  cmovz   r9, rbx
0x180012d7b  test    rax, rax
0x180012d7e  jz      short loc_180012D97
0x180012d80  cmp     word ptr [rax+rcx*2+2], 0
0x180012d86  lea     rcx, [rcx+1]
0x180012d8a  jnz     short loc_180012D80
0x180012d8c  lea     r10, ds:2[rcx*2]
0x180012d94  test    rax, rax
0x180012d97  mov     [rsp+58h+var_10], 0
0x180012da0  cmovz   rax, rbx
0x180012da4  mov     [rsp+58h+var_18], rdx
0x180012da9  mov     ecx, 404h
0x180012dae  mov     [rsp+58h+var_20], r9
0x180012db3  mov     edx, r11d
0x180012db6  mov     [rsp+58h+var_28], r10
0x180012dbb  lea     r9, [rsp+58h+arg_18]
0x180012dc0  mov     [rsp+58h+var_30], rax
0x180012dc5  mov     [rsp+58h+var_38], 4
0x180012dce  call    FastWppTraceMessage
0x180012dd3  add     rsp, 50h
0x180012dd7  pop     rbx
0x180012dd8  retn
0x180012dd9  mov     rdx, r10
0x180012ddc  jmp     short loc_180012D65
```
