# McTemplateU0zzzqqdd_EventWriteTransfer

- ea: `0x14000d108`
- end: `0x14000d232`
- name: `McTemplateU0zzzqqdd_EventWriteTransfer`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c9a4`

## callees

- `0x14000cd7c`
- `0x14000d108`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzqqdd_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6,
        char a7,
        char a8,
        char a9)
{
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // rcx
  int v14; // ecx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-61h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-51h]
  int v20; // [rsp+48h] [rbp-49h]
  int v21; // [rsp+4Ch] [rbp-45h]
  const wchar_t *v22; // [rsp+50h] [rbp-41h]
  int v23; // [rsp+58h] [rbp-39h]
  int v24; // [rsp+5Ch] [rbp-35h]
  const wchar_t *v25; // [rsp+60h] [rbp-31h]
  int v26; // [rsp+68h] [rbp-29h]
  int v27; // [rsp+6Ch] [rbp-25h]
  char *v28; // [rsp+70h] [rbp-21h]
  __int64 v29; // [rsp+78h] [rbp-19h]
  char *v30; // [rsp+80h] [rbp-11h]
  __int64 v31; // [rsp+88h] [rbp-9h]
  char *v32; // [rsp+90h] [rbp-1h]
  __int64 v33; // [rsp+98h] [rbp+7h]
  char *v34; // [rsp+A0h] [rbp+Fh]
  __int64 v35; // [rsp+A8h] [rbp+17h]

  v9 = -1;
  v10 = 10;
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v20 = v12;
  v21 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v19 = a3;
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v23 = v14;
  v15 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 0;
  v22 = a4;
  v16 = a5 == 0;
  if ( a5 )
  {
    do
      ++v9;
    while ( a5[v9] );
    v10 = 2 * v9 + 2;
    v16 = a5 == 0;
  }
  v26 = v10;
  v28 = &a6;
  v27 = 0;
  v30 = &a7;
  if ( v16 )
    v15 = L"NULL";
  v25 = v15;
  v32 = &a8;
  v29 = 4;
  v34 = &a9;
  v31 = 4;
  v33 = 4;
  v35 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionHandled,
           (__int64)a3,
           8u,
           &v18);
}

```

## disassembly

```asm
0x14000d108  push    rbp
0x14000d10a  lea     rbp, [rsp-2Fh]
0x14000d10f  sub     rsp, 0C0h
0x14000d116  mov     rax, cs:__security_cookie
0x14000d11d  xor     rax, rsp
0x14000d120  mov     [rbp+2Fh+var_10], rax
0x14000d124  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d128  xor     r10d, r10d
0x14000d12b  mov     edx, 0Ah
0x14000d130  test    r8, r8
0x14000d133  jz      short loc_14000D14B
0x14000d135  mov     rcx, rax
0x14000d138  inc     rcx
0x14000d13b  cmp     [r8+rcx*2], r10w
0x14000d140  jnz     short loc_14000D138
0x14000d142  lea     ecx, ds:2[rcx*2]
0x14000d149  jmp     short loc_14000D14D
0x14000d14b  mov     ecx, edx
0x14000d14d  test    r8, r8
0x14000d150  mov     [rbp+2Fh+var_78], ecx
0x14000d153  lea     r11, aNull; "NULL"
0x14000d15a  mov     [rbp+2Fh+var_74], r10d
0x14000d15e  cmovz   r8, r11
0x14000d162  mov     [rbp+2Fh+var_80], r8
0x14000d166  test    r9, r9
0x14000d169  jz      short loc_14000D181
0x14000d16b  mov     rcx, rax
0x14000d16e  inc     rcx
0x14000d171  cmp     [r9+rcx*2], r10w
0x14000d176  jnz     short loc_14000D16E
0x14000d178  lea     ecx, ds:2[rcx*2]
0x14000d17f  jmp     short loc_14000D183
0x14000d181  mov     ecx, edx
0x14000d183  test    r9, r9
0x14000d186  mov     [rbp+2Fh+var_68], ecx
0x14000d189  mov     rcx, [rbp+2Fh+arg_20]
0x14000d18d  cmovz   r9, r11
0x14000d191  mov     [rbp+2Fh+var_64], r10d
0x14000d195  mov     [rbp+2Fh+var_70], r9
0x14000d199  test    rcx, rcx
0x14000d19c  jz      short loc_14000D1B2
0x14000d19e  inc     rax
0x14000d1a1  cmp     [rcx+rax*2], r10w
0x14000d1a6  jnz     short loc_14000D19E
0x14000d1a8  lea     edx, ds:2[rax*2]
0x14000d1af  test    rcx, rcx
0x14000d1b2  lea     rax, [rbp+2Fh+arg_28]
0x14000d1b6  mov     [rbp+2Fh+var_58], edx
0x14000d1b9  mov     [rbp+2Fh+var_50], rax
0x14000d1bd  lea     rdx, EnterpriseDiagnosticsOmaDmSessionHandled
0x14000d1c4  lea     rax, [rbp+2Fh+arg_30]
0x14000d1c8  mov     [rbp+2Fh+var_54], r10d
0x14000d1cc  mov     [rbp+2Fh+var_40], rax
0x14000d1d0  cmovz   rcx, r11
0x14000d1d4  lea     rax, [rbp+2Fh+arg_38]
0x14000d1d8  mov     [rbp+2Fh+var_60], rcx
0x14000d1dc  mov     [rbp+2Fh+var_30], rax
0x14000d1e0  mov     r9d, 8
0x14000d1e6  lea     rax, [rbp+2Fh+arg_40]
0x14000d1ea  mov     [rbp+2Fh+var_48], 4
0x14000d1f2  mov     [rbp+2Fh+var_20], rax
0x14000d1f6  lea     rax, [rbp+2Fh+var_90]
0x14000d1fa  mov     [rsp+0C0h+var_A0], rax
0x14000d1ff  mov     [rbp+2Fh+var_38], 4
0x14000d207  mov     [rbp+2Fh+var_28], 4
0x14000d20f  mov     [rbp+2Fh+var_18], 4
0x14000d217  call    McGenEventWrite_EventWriteTransfer
0x14000d21c  mov     rcx, [rbp+2Fh+var_10]
0x14000d220  xor     rcx, rsp; StackCookie
0x14000d223  call    __security_check_cookie
0x14000d228  add     rsp, 0C0h
0x14000d22f  pop     rbp
0x14000d230  retn
```
