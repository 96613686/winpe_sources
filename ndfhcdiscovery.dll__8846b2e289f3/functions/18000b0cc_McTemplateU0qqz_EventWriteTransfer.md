# McTemplateU0qqz_EventWriteTransfer

- ea: `0x18000b0cc`
- end: `0x18000b175`
- name: `McTemplateU0qqz_EventWriteTransfer`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007260`
- `0x1800075c0`
- `0x180008a20`
- `0x18000ebf8`

## callees

- `0x18000b06c`
- `0x18000b0cc`
- `0x1800136b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-50h] BYREF
  int *v10; // [rsp+40h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-38h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  const wchar_t *v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+A0h] [rbp+20h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF

  v18 = a4;
  v17 = a3;
  v5 = a5;
  v10 = &v17;
  v11 = 4;
  v13 = 4;
  v12 = &v18;
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
  v15 = v7;
  v16 = 0;
  if ( !a5 )
    v5 = L"NULL";
  v14 = v5;
  return McGenEventWrite_EventWriteTransfer((__int64)v5, a2, (__int64)L"NULL", 4u, &v9);
}

```

## disassembly

```asm
0x18000b0cc  mov     [rsp-8+arg_18], r9d
0x18000b0d1  mov     [rsp-8+arg_10], r8d
0x18000b0d6  push    rbp
0x18000b0d7  mov     rbp, rsp
0x18000b0da  sub     rsp, 80h
0x18000b0e1  mov     rax, cs:__security_cookie
0x18000b0e8  xor     rax, rsp
0x18000b0eb  mov     [rbp+var_10], rax
0x18000b0ef  mov     rcx, [rbp+arg_20]
0x18000b0f3  lea     rax, [rbp+arg_10]
0x18000b0f7  mov     r10d, 4
0x18000b0fd  mov     [rbp+var_40], rax
0x18000b101  xor     r9d, r9d
0x18000b104  mov     [rbp+var_38], r10
0x18000b108  mov     [rbp+var_28], r10
0x18000b10c  lea     rax, [rbp+arg_18]
0x18000b110  mov     [rbp+var_30], rax
0x18000b114  test    rcx, rcx
0x18000b117  jz      short loc_18000B130
0x18000b119  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b11d  inc     rax
0x18000b120  cmp     [rcx+rax*2], r9w
0x18000b125  jnz     short loc_18000B11D
0x18000b127  lea     eax, ds:2[rax*2]
0x18000b12e  jmp     short loc_18000B135
0x18000b130  mov     eax, 0Ah
0x18000b135  test    rcx, rcx
0x18000b138  mov     [rbp+var_18], eax
0x18000b13b  lea     r8, aNull; "NULL"
0x18000b142  mov     [rbp+var_14], r9d
0x18000b146  cmovz   rcx, r8
0x18000b14a  lea     rax, [rbp+var_50]
0x18000b14e  mov     r9d, r10d
0x18000b151  mov     [rbp+var_20], rcx
0x18000b155  mov     [rsp+80h+var_60], rax
0x18000b15a  call    McGenEventWrite_EventWriteTransfer
0x18000b15f  mov     rcx, [rbp+var_10]
0x18000b163  xor     rcx, rsp; StackCookie
0x18000b166  call    __security_check_cookie
0x18000b16b  add     rsp, 80h
0x18000b172  pop     rbp
0x18000b173  retn
```
