# WPP_SF_DDS

- ea: `0x1800110f8`
- end: `0x180011189`
- name: `WPP_SF_DDS`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007dd0`
- `0x180009d40`
- `0x18000a4d0`

## callees

- `0x180003e70`
- `0x1800110f8`

## pseudocode

```c
ULONG __fastcall WPP_SF_DDS(__int64 a1, USHORT a2, __int64 a3, int a4, char a5, const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  int v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = a4;
  v6 = a6;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  if ( !a6 )
    v6 = L"NULL";
  return FastWppTraceMessage(
           1028,
           a2,
           (ULONGLONG)WPP_e15037783097355a5233924022d92169_Traceguids,
           &v10,
           4,
           &a5,
           4,
           v6,
           v8,
           0);
}

```

## disassembly

```asm
0x1800110f8  mov     [rsp+arg_18], r9d
0x1800110fd  sub     rsp, 58h
0x180011101  mov     rcx, [rsp+58h+arg_28]
0x180011109  xor     r9d, r9d
0x18001110c  test    rcx, rcx
0x18001110f  jz      short loc_180011129
0x180011111  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011115  inc     rax
0x180011118  cmp     [rcx+rax*2], r9w
0x18001111d  jnz     short loc_180011115
0x18001111f  lea     rax, ds:2[rax*2]
0x180011127  jmp     short loc_18001112E
0x180011129  mov     eax, 0Ah
0x18001112e  mov     [rsp+58h+var_10], r9
0x180011133  lea     r8, aNull; "NULL"
0x18001113a  mov     [rsp+58h+var_18], rax
0x18001113f  lea     r9, [rsp+58h+arg_18]
0x180011144  test    rcx, rcx
0x180011147  movzx   edx, dx
0x18001114a  lea     rax, [rsp+58h+arg_20]
0x180011152  mov     r10d, 404h
0x180011158  cmovz   rcx, r8
0x18001115c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180011163  mov     [rsp+58h+var_20], rcx
0x180011168  mov     ecx, 4
0x18001116d  mov     [rsp+58h+var_28], rcx
0x180011172  mov     [rsp+58h+var_30], rax
0x180011177  mov     [rsp+58h+var_38], rcx
0x18001117c  mov     ecx, r10d
0x18001117f  call    FastWppTraceMessage
0x180011184  add     rsp, 58h
0x180011188  retn
```
