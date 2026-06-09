# WPP_SF_SSldDDLLS

- ea: `0x180012230`
- end: `0x18001239c`
- name: `WPP_SF_SSldDDLLS`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dbe0`

## callees

- `0x180003e70`
- `0x180012230`

## pseudocode

```c
ULONG __fastcall WPP_SF_SSldDDLLS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        const wchar_t *a12)
{
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r10
  __int64 v15; // rcx
  __int64 v16; // r11
  const wchar_t *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r8
  bool v20; // zf

  v12 = a12;
  v13 = -1;
  v14 = 10;
  if ( a12 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a12[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v17 = a5;
  if ( !a12 )
    v12 = L"NULL";
  if ( a5 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a5[v18] );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v19 = 10;
  }
  if ( !a5 )
    v17 = L"NULL";
  v20 = a4 == 0;
  if ( a4 )
  {
    do
      ++v13;
    while ( a4[v13] );
    v14 = 2 * v13 + 2;
    v20 = a4 == 0;
  }
  if ( v20 )
    a4 = L"NULL";
  return FastWppTraceMessage(
           1028,
           0xCu,
           (ULONGLONG)WPP_bced608cee43397007671a721f646035_Traceguids,
           a4,
           v14,
           v17,
           v19,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           &a10,
           4,
           &a11,
           4,
           v12,
           v16,
           0);
}

```

## disassembly

```asm
0x180012230  mov     [rsp+arg_0], rbx
0x180012235  mov     [rsp+arg_8], rsi
0x18001223a  push    rdi
0x18001223b  sub     rsp, 0B0h
0x180012242  mov     rdx, [rsp+0B8h+arg_58]
0x18001224a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001224e  xor     esi, esi
0x180012250  mov     r10d, 0Ah
0x180012256  test    rdx, rdx
0x180012259  jz      short loc_180012271
0x18001225b  mov     rcx, rax
0x18001225e  inc     rcx
0x180012261  cmp     [rdx+rcx*2], si
0x180012265  jnz     short loc_18001225E
0x180012267  lea     r11, ds:2[rcx*2]
0x18001226f  jmp     short loc_180012274
0x180012271  mov     r11, r10
0x180012274  mov     rcx, [rsp+0B8h+arg_20]
0x18001227c  lea     rbx, aNull; "NULL"
0x180012283  test    rdx, rdx
0x180012286  cmovz   rdx, rbx
0x18001228a  test    rcx, rcx
0x18001228d  jz      short loc_1800122A6
0x18001228f  mov     r8, rax
0x180012292  inc     r8
0x180012295  cmp     [rcx+r8*2], si
0x18001229a  jnz     short loc_180012292
0x18001229c  lea     r8, ds:2[r8*2]
0x1800122a4  jmp     short loc_1800122A9
0x1800122a6  mov     r8, r10
0x1800122a9  test    rcx, rcx
0x1800122ac  cmovz   rcx, rbx
0x1800122b0  test    r9, r9
0x1800122b3  jz      short loc_1800122CA
0x1800122b5  inc     rax
0x1800122b8  cmp     [r9+rax*2], si
0x1800122bd  jnz     short loc_1800122B5
0x1800122bf  lea     r10, ds:2[rax*2]
0x1800122c7  test    r9, r9
0x1800122ca  mov     [rsp+0B8h+var_10], rsi
0x1800122d2  lea     rax, [rsp+0B8h+arg_50]
0x1800122da  mov     [rsp+0B8h+var_18], r11
0x1800122e2  cmovz   r9, rbx
0x1800122e6  mov     [rsp+0B8h+var_20], rdx
0x1800122ee  mov     ebx, 0Ch
0x1800122f3  mov     edi, 404h
0x1800122f8  lea     edx, [rbx-8]
0x1800122fb  mov     [rsp+0B8h+var_28], rdx
0x180012303  mov     [rsp+0B8h+var_30], rax
0x18001230b  lea     rax, [rsp+0B8h+arg_48]
0x180012313  mov     [rsp+0B8h+var_38], rdx
0x18001231b  mov     [rsp+0B8h+var_40], rax
0x180012320  lea     rax, [rsp+0B8h+arg_40]
0x180012328  mov     [rsp+0B8h+var_48], rdx
0x18001232d  mov     [rsp+0B8h+var_50], rax
0x180012332  lea     rax, [rsp+0B8h+arg_38]
0x18001233a  mov     [rsp+0B8h+var_58], rdx
0x18001233f  mov     [rsp+0B8h+var_60], rax
0x180012344  lea     rax, [rsp+0B8h+arg_30]
0x18001234c  mov     [rsp+0B8h+var_68], rdx
0x180012351  mov     [rsp+0B8h+var_70], rax
0x180012356  lea     rax, [rsp+0B8h+arg_28]
0x18001235e  mov     [rsp+0B8h+var_78], rdx
0x180012363  mov     edx, ebx
0x180012365  mov     [rsp+0B8h+var_80], rax
0x18001236a  mov     [rsp+0B8h+var_88], r8
0x18001236f  lea     r8, WPP_bced608cee43397007671a721f646035_Traceguids
0x180012376  mov     [rsp+0B8h+var_90], rcx
0x18001237b  mov     ecx, edi
0x18001237d  mov     [rsp+0B8h+var_98], r10
0x180012382  call    FastWppTraceMessage
0x180012387  lea     r11, [rsp+0B8h+var_8]
0x18001238f  mov     rbx, [r11+10h]
0x180012393  mov     rsi, [r11+18h]
0x180012397  mov     rsp, r11
0x18001239a  pop     rdi
0x18001239b  retn
```
