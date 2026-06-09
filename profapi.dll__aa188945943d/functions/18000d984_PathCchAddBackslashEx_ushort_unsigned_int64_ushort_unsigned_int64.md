# PathCchAddBackslashEx(ushort *,unsigned __int64,ushort * *,unsigned __int64 *)

- ea: `0x18000d984`
- end: `0x18000da42`
- name: `?PathCchAddBackslashEx@@YAJPEAG_KPEAPEAGPEA_K@Z`
- size: `190`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18000d620`
- `0x180016d14`

## callees

- `0x18000d984`
- `0x180016b30`

## pseudocode

```c
__int64 __fastcall PathCchAddBackslashEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  unsigned __int64 v7; // rax
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // r8
  unsigned int v11; // [rsp+28h] [rbp-10h]
  unsigned __int16 *v12; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = a2;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( v7 >= 0x104 )
    return 2147942522LL;
  v9 = 260 - v7;
  v10 = &a1[v7];
  v12 = v10;
  v13 = 260 - v7;
  if ( !v7 || *(v10 - 1) == 92 )
  {
    result = 1;
  }
  else
  {
    result = StringCchCopyExW(v10, v9, v10, &v12, &v13, v11);
    if ( (int)result < 0 )
      return result;
    v10 = v12;
    v9 = v13;
  }
  if ( a3 )
    *a3 = v10;
  if ( a4 )
    *a4 = v9;
  return result;
}

```

## disassembly

```asm
0x18000d984  mov     [rsp+arg_0], rbx
0x18000d989  mov     [rsp+arg_18], rsi
0x18000d98e  mov     [rsp+arg_8], rdx
0x18000d993  push    rdi
0x18000d994  sub     rsp, 30h
0x18000d998  xor     esi, esi
0x18000d99a  mov     rbx, r9
0x18000d99d  mov     rdi, r8
0x18000d9a0  mov     rdx, rcx
0x18000d9a3  test    r8, r8
0x18000d9a6  jz      short loc_18000D9AB
0x18000d9a8  mov     [r8], rsi
0x18000d9ab  test    rbx, rbx
0x18000d9ae  jz      short loc_18000D9B3
0x18000d9b0  mov     [r9], rsi
0x18000d9b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d9b7  inc     rax
0x18000d9ba  cmp     [rcx+rax*2], si
0x18000d9be  jnz     short loc_18000D9B7
0x18000d9c0  mov     ecx, 104h
0x18000d9c5  cmp     rax, rcx
0x18000d9c8  jb      short loc_18000D9D1
0x18000d9ca  mov     eax, 8007007Ah
0x18000d9cf  jmp     short loc_18000DA32
0x18000d9d1  sub     rcx, rax
0x18000d9d4  lea     r8, [rdx+rax*2]; unsigned __int16 *
0x18000d9d8  mov     [rsp+38h+arg_8], r8
0x18000d9dd  mov     [rsp+38h+arg_10], rcx
0x18000d9e2  test    rax, rax
0x18000d9e5  jz      short loc_18000DA1D
0x18000d9e7  mov     eax, 5Ch ; '\'
0x18000d9ec  cmp     ax, [r8-2]
0x18000d9f1  jz      short loc_18000DA1D
0x18000d9f3  lea     rax, [rsp+38h+arg_10]
0x18000d9f8  mov     rdx, rcx; unsigned __int64
0x18000d9fb  mov     rcx, r8; unsigned __int16 *
0x18000d9fe  mov     [rsp+38h+var_18], rax; unsigned __int64 *
0x18000da03  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x18000da08  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000da0d  test    eax, eax
0x18000da0f  js      short loc_18000DA32
0x18000da11  mov     r8, [rsp+38h+arg_8]
0x18000da16  mov     rcx, [rsp+38h+arg_10]
0x18000da1b  jmp     short loc_18000DA22
0x18000da1d  mov     eax, 1
0x18000da22  test    rdi, rdi
0x18000da25  jz      short loc_18000DA2A
0x18000da27  mov     [rdi], r8
0x18000da2a  test    rbx, rbx
0x18000da2d  jz      short loc_18000DA32
0x18000da2f  mov     [rbx], rcx
0x18000da32  mov     rbx, [rsp+38h+arg_0]
0x18000da37  mov     rsi, [rsp+38h+arg_18]
0x18000da3c  add     rsp, 30h
0x18000da40  pop     rdi
0x18000da41  retn
```
