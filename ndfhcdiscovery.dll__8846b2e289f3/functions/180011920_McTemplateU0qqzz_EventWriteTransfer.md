# McTemplateU0qqzz_EventWriteTransfer

- ea: `0x180011920`
- end: `0x180011a09`
- name: `McTemplateU0qqzz_EventWriteTransfer`
- size: `233`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d670`
- `0x18000e2a0`
- `0x18000e600`
- `0x18000e7c0`
- `0x18000ebf8`
- `0x18000f5d8`
- `0x18000f970`

## callees

- `0x18000b06c`
- `0x180011920`
- `0x1800136b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqzz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  const wchar_t *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  bool v13; // zf
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-19h] BYREF
  int *v16; // [rsp+40h] [rbp-9h]
  __int64 v17; // [rsp+48h] [rbp-1h]
  int *v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  const wchar_t *v20; // [rsp+60h] [rbp+17h]
  int v21; // [rsp+68h] [rbp+1Fh]
  int v22; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v23; // [rsp+70h] [rbp+27h]
  int v24; // [rsp+78h] [rbp+2Fh]
  int v25; // [rsp+7Ch] [rbp+33h]
  int v26; // [rsp+B0h] [rbp+67h] BYREF
  int v27; // [rsp+B8h] [rbp+6Fh] BYREF

  v27 = a4;
  v26 = a3;
  v17 = 4;
  v16 = &v26;
  v19 = 4;
  v18 = &v27;
  v7 = a5;
  v8 = -1;
  v9 = 10;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v21 = v11;
  v12 = a6;
  if ( !a5 )
    v7 = L"NULL";
  v22 = 0;
  v20 = v7;
  v13 = a6 == 0;
  if ( a6 )
  {
    do
      ++v8;
    while ( a6[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v13 = a6 == 0;
  }
  if ( v13 )
    v12 = L"NULL";
  v25 = 0;
  v23 = v12;
  v24 = v9;
  return McGenEventWrite_EventWriteTransfer((__int64)v12, a2, v9, 5u, &v15);
}

```

## disassembly

```asm
0x180011920  mov     [rsp-8+arg_18], r9d
0x180011925  mov     [rsp-8+arg_10], r8d
0x18001192a  push    rbp
0x18001192b  lea     rbp, [rsp-47h]
0x180011930  sub     rsp, 90h
0x180011937  mov     rax, cs:__security_cookie
0x18001193e  xor     rax, rsp
0x180011941  mov     [rbp+47h+var_10], rax
0x180011945  lea     rax, [rbp+47h+arg_10]
0x180011949  mov     [rbp+47h+var_48], 4
0x180011951  mov     [rbp+47h+var_50], rax
0x180011955  xor     r9d, r9d
0x180011958  lea     rax, [rbp+47h+arg_18]
0x18001195c  mov     [rbp+47h+var_38], 4
0x180011964  mov     [rbp+47h+var_40], rax
0x180011968  mov     r10, rdx
0x18001196b  mov     rdx, [rbp+47h+arg_20]
0x18001196f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011973  lea     r8d, [r9+0Ah]
0x180011977  test    rdx, rdx
0x18001197a  jz      short loc_180011992
0x18001197c  mov     rcx, rax
0x18001197f  inc     rcx
0x180011982  cmp     [rdx+rcx*2], r9w
0x180011987  jnz     short loc_18001197F
0x180011989  lea     ecx, ds:2[rcx*2]
0x180011990  jmp     short loc_180011995
0x180011992  mov     ecx, r8d
0x180011995  test    rdx, rdx
0x180011998  mov     [rbp+47h+var_28], ecx
0x18001199b  mov     rcx, [rbp+47h+arg_28]
0x18001199f  lea     r11, aNull; "NULL"
0x1800119a6  cmovz   rdx, r11
0x1800119aa  mov     [rbp+47h+var_24], r9d
0x1800119ae  mov     [rbp+47h+var_30], rdx
0x1800119b2  test    rcx, rcx
0x1800119b5  jz      short loc_1800119CC
0x1800119b7  inc     rax
0x1800119ba  cmp     [rcx+rax*2], r9w
0x1800119bf  jnz     short loc_1800119B7
0x1800119c1  lea     r8d, ds:2[rax*2]
0x1800119c9  test    rcx, rcx
0x1800119cc  cmovz   rcx, r11
0x1800119d0  mov     [rbp+47h+var_14], r9d
0x1800119d4  lea     rax, [rbp+47h+var_60]
0x1800119d8  mov     [rbp+47h+var_20], rcx
0x1800119dc  mov     r9d, 5
0x1800119e2  mov     [rsp+90h+var_70], rax
0x1800119e7  mov     rdx, r10
0x1800119ea  mov     [rbp+47h+var_18], r8d
0x1800119ee  call    McGenEventWrite_EventWriteTransfer
0x1800119f3  mov     rcx, [rbp+47h+var_10]
0x1800119f7  xor     rcx, rsp; StackCookie
0x1800119fa  call    __security_check_cookie
0x1800119ff  add     rsp, 90h
0x180011a06  pop     rbp
0x180011a07  retn
```
