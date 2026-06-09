# McTemplateU0zzzzd_EventWriteTransfer

- ea: `0x14000d238`
- end: `0x14000d378`
- name: `McTemplateU0zzzzd_EventWriteTransfer`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bd90`
- `0x14000c084`

## callees

- `0x14000cd7c`
- `0x14000d238`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        char a7)
{
  __int64 v7; // rax
  int v9; // r10d
  __int64 v10; // rcx
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // ecx
  const wchar_t *v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  const wchar_t *v17; // rcx
  bool v18; // zf
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-21h]
  int v22; // [rsp+48h] [rbp-19h]
  int v23; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v24; // [rsp+50h] [rbp-11h]
  int v25; // [rsp+58h] [rbp-9h]
  int v26; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v27; // [rsp+60h] [rbp-1h]
  int v28; // [rsp+68h] [rbp+7h]
  int v29; // [rsp+6Ch] [rbp+Bh]
  const wchar_t *v30; // [rsp+70h] [rbp+Fh]
  int v31; // [rsp+78h] [rbp+17h]
  int v32; // [rsp+7Ch] [rbp+1Bh]
  char *v33; // [rsp+80h] [rbp+1Fh]
  __int64 v34; // [rsp+88h] [rbp+27h]

  v7 = -1;
  v9 = 10;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v22 = v11;
  v23 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v21 = a3;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v25 = v13;
  v14 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v26 = 0;
  v24 = a4;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v28 = v16;
  v29 = 0;
  if ( !a5 )
    v14 = L"NULL";
  v27 = v14;
  v17 = a6;
  v18 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v9 = 2 * v7 + 2;
    v18 = a6 == 0;
  }
  v31 = v9;
  v33 = &a7;
  if ( v18 )
    v17 = L"NULL";
  v30 = v17;
  v32 = 0;
  v34 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)v17, a2, (__int64)a3, 6u, &v20);
}

```

## disassembly

```asm
0x14000d238  mov     [rsp-8+arg_0], rbx
0x14000d23d  mov     [rsp-8+arg_10], rdi
0x14000d242  push    rbp
0x14000d243  lea     rbp, [rsp-3Fh]
0x14000d248  sub     rsp, 0A0h
0x14000d24f  mov     rax, cs:__security_cookie
0x14000d256  xor     rax, rsp
0x14000d259  mov     [rbp+3Fh+var_10], rax
0x14000d25d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d261  xor     ebx, ebx
0x14000d263  mov     r11, rdx
0x14000d266  mov     r10d, 0Ah
0x14000d26c  test    r8, r8
0x14000d26f  jz      short loc_14000D287
0x14000d271  mov     rcx, rax
0x14000d274  inc     rcx
0x14000d277  cmp     [r8+rcx*2], bx
0x14000d27c  jnz     short loc_14000D274
0x14000d27e  lea     ecx, ds:2[rcx*2]
0x14000d285  jmp     short loc_14000D28A
0x14000d287  mov     ecx, r10d
0x14000d28a  test    r8, r8
0x14000d28d  mov     [rbp+3Fh+var_58], ecx
0x14000d290  lea     rdi, aNull; "NULL"
0x14000d297  mov     [rbp+3Fh+var_54], ebx
0x14000d29a  cmovz   r8, rdi
0x14000d29e  mov     [rbp+3Fh+var_60], r8
0x14000d2a2  test    r9, r9
0x14000d2a5  jz      short loc_14000D2BD
0x14000d2a7  mov     rcx, rax
0x14000d2aa  inc     rcx
0x14000d2ad  cmp     [r9+rcx*2], bx
0x14000d2b2  jnz     short loc_14000D2AA
0x14000d2b4  lea     ecx, ds:2[rcx*2]
0x14000d2bb  jmp     short loc_14000D2C0
0x14000d2bd  mov     ecx, r10d
0x14000d2c0  test    r9, r9
0x14000d2c3  mov     [rbp+3Fh+var_48], ecx
0x14000d2c6  mov     rcx, [rbp+3Fh+arg_20]
0x14000d2ca  cmovz   r9, rdi
0x14000d2ce  mov     [rbp+3Fh+var_44], ebx
0x14000d2d1  mov     [rbp+3Fh+var_50], r9
0x14000d2d5  test    rcx, rcx
0x14000d2d8  jz      short loc_14000D2EF
0x14000d2da  mov     rdx, rax
0x14000d2dd  inc     rdx
0x14000d2e0  cmp     [rcx+rdx*2], bx
0x14000d2e4  jnz     short loc_14000D2DD
0x14000d2e6  lea     edx, ds:2[rdx*2]
0x14000d2ed  jmp     short loc_14000D2F2
0x14000d2ef  mov     edx, r10d
0x14000d2f2  test    rcx, rcx
0x14000d2f5  mov     [rbp+3Fh+var_38], edx
0x14000d2f8  mov     [rbp+3Fh+var_34], ebx
0x14000d2fb  cmovz   rcx, rdi
0x14000d2ff  mov     [rbp+3Fh+var_40], rcx
0x14000d303  mov     rcx, [rbp+3Fh+arg_28]
0x14000d307  test    rcx, rcx
0x14000d30a  jz      short loc_14000D320
0x14000d30c  inc     rax
0x14000d30f  cmp     [rcx+rax*2], bx
0x14000d313  jnz     short loc_14000D30C
0x14000d315  lea     r10d, ds:2[rax*2]
0x14000d31d  test    rcx, rcx
0x14000d320  lea     rax, [rbp+3Fh+arg_30]
0x14000d324  mov     [rbp+3Fh+var_28], r10d
0x14000d328  mov     [rbp+3Fh+var_20], rax
0x14000d32c  cmovz   rcx, rdi
0x14000d330  lea     rax, [rbp+3Fh+var_70]
0x14000d334  mov     [rbp+3Fh+var_30], rcx
0x14000d338  mov     r9d, 6
0x14000d33e  mov     [rsp+0A0h+var_80], rax
0x14000d343  mov     rdx, r11
0x14000d346  mov     [rbp+3Fh+var_24], ebx
0x14000d349  mov     [rbp+3Fh+var_18], 4
0x14000d351  call    McGenEventWrite_EventWriteTransfer
0x14000d356  mov     rcx, [rbp+3Fh+var_10]
0x14000d35a  xor     rcx, rsp; StackCookie
0x14000d35d  call    __security_check_cookie
0x14000d362  lea     r11, [rsp+0A0h+var_s0]
0x14000d36a  mov     rbx, [r11+10h]
0x14000d36e  mov     rdi, [r11+20h]
0x14000d372  mov     rsp, r11
0x14000d375  pop     rbp
0x14000d376  retn
```
