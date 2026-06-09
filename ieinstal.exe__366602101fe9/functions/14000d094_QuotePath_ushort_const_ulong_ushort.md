# QuotePath(ushort const *,ulong,ushort *)

- ea: `0x14000d094`
- end: `0x14000d1b0`
- name: `?QuotePath@@YAJPEBGKPEAG@Z`
- size: `284`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140005630`
- `0x14000c498`

## callees

- `0x1400017f1`
- `0x140001af3`
- `0x14000d094`
- `0x14000d1b8`

## pseudocode

```c
__int64 __fastcall QuotePath(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r15
  bool v4; // zf
  unsigned __int16 *v6; // rcx
  int v8; // edi
  unsigned __int16 *v9; // rbx
  size_t v10; // r12
  unsigned int v12; // [rsp+28h] [rbp-8h]
  unsigned int v13; // [rsp+28h] [rbp-8h]
  unsigned __int16 *v14; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int64 v15; // [rsp+88h] [rbp+58h] BYREF

  v3 = (unsigned int)a2;
  v14 = a3;
  v4 = *a1 == 34;
  v15 = (unsigned int)a2;
  v6 = a3;
  a2 = (unsigned int)a2;
  if ( !v4 )
  {
    v8 = StringCchCopyExW(a3, (unsigned int)a2, L"\"", &v14, &v15, v12);
    if ( v8 < 0 )
      return (unsigned int)v8;
    a2 = v15;
    v6 = v14;
  }
  v8 = StringCchCopyExW(v6, a2, a1, &v14, &v15, v12);
  if ( v8 >= 0 )
  {
    v9 = v14;
    if ( v14 <= a3 + 1 || (v10 = 2 * v3, v14 >= &a3[v3]) || *(v14 - 1) != 34 )
    {
      v10 = 2 * v3;
      v8 = StringCchCopyExW(v14, v15, L"\"", &v14, &v15, v13);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v9 = v14;
    }
    if ( *a3 != 34 || v9 <= a3 + 1 || wcschr_0(a3 + 1, 0x22u) != v9 - 1 )
    {
      memset_0(a3, 0, v10);
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000d094  mov     [rsp-38h+arg_0], rbx
0x14000d099  push    rbp
0x14000d09a  push    rsi
0x14000d09b  push    rdi
0x14000d09c  push    r12
0x14000d09e  push    r13
0x14000d0a0  push    r14
0x14000d0a2  push    r15
0x14000d0a4  mov     rbp, rsp
0x14000d0a7  sub     rsp, 30h
0x14000d0ab  mov     r15d, edx
0x14000d0ae  lea     rax, [rbp+arg_18]
0x14000d0b2  mov     r13d, 22h ; '"'
0x14000d0b8  mov     [rbp+arg_10], r8
0x14000d0bc  cmp     r13w, [rcx]
0x14000d0c0  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x14000d0c4  mov     rbx, rcx
0x14000d0c7  mov     [rbp+arg_18], r15
0x14000d0cb  mov     rcx, r8; unsigned __int16 *
0x14000d0ce  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x14000d0d3  mov     rsi, r8
0x14000d0d6  mov     edx, r15d; unsigned __int64
0x14000d0d9  jz      short loc_14000D106
0x14000d0db  lea     r8, asc_14001369C; "\""
0x14000d0e2  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14000d0e7  mov     edi, eax
0x14000d0e9  test    eax, eax
0x14000d0eb  js      loc_14000D198
0x14000d0f1  mov     rdx, [rbp+arg_18]; unsigned __int64
0x14000d0f5  lea     rax, [rbp+arg_18]
0x14000d0f9  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x14000d0fd  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x14000d101  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x14000d106  mov     r8, rbx; unsigned __int16 *
0x14000d109  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14000d10e  mov     edi, eax
0x14000d110  test    eax, eax
0x14000d112  js      loc_14000D198
0x14000d118  mov     rbx, [rbp+arg_10]
0x14000d11c  lea     r14, [rsi+2]
0x14000d120  cmp     rbx, r14
0x14000d123  jbe     short loc_14000D139
0x14000d125  lea     r12, [r15+r15]
0x14000d129  lea     rax, [r12+rsi]
0x14000d12d  cmp     rbx, rax
0x14000d130  jnb     short loc_14000D139
0x14000d132  cmp     [rbx-2], r13w
0x14000d137  jz      short loc_14000D167
0x14000d139  mov     rdx, [rbp+arg_18]; unsigned __int64
0x14000d13d  lea     rax, [rbp+arg_18]
0x14000d141  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x14000d145  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x14000d14a  lea     r8, asc_14001369C; "\""
0x14000d151  mov     rcx, rbx; unsigned __int16 *
0x14000d154  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14000d159  lea     r12, [r15+r15]
0x14000d15d  mov     edi, eax
0x14000d15f  test    eax, eax
0x14000d161  js      short loc_14000D198
0x14000d163  mov     rbx, [rbp+arg_10]
0x14000d167  cmp     [rsi], r13w
0x14000d16b  jnz     short loc_14000D186
0x14000d16d  cmp     rbx, r14
0x14000d170  jbe     short loc_14000D186
0x14000d172  mov     edx, r13d; Ch
0x14000d175  mov     rcx, r14; Str
0x14000d178  call    wcschr_0
0x14000d17d  lea     rcx, [rbx-2]
0x14000d181  cmp     rax, rcx
0x14000d184  jz      short loc_14000D198
0x14000d186  mov     r8, r12; Size
0x14000d189  xor     edx, edx; Val
0x14000d18b  mov     rcx, rsi; void *
0x14000d18e  call    memset_0
0x14000d193  mov     edi, 80070057h
0x14000d198  mov     rbx, [rsp+30h+arg_0]
0x14000d19d  mov     eax, edi
0x14000d19f  add     rsp, 30h
0x14000d1a3  pop     r15
0x14000d1a5  pop     r14
0x14000d1a7  pop     r13
0x14000d1a9  pop     r12
0x14000d1ab  pop     rdi
0x14000d1ac  pop     rsi
0x14000d1ad  pop     rbp
0x14000d1ae  retn
```
