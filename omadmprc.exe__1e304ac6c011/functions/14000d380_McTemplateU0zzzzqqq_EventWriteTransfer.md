# McTemplateU0zzzzqqq_EventWriteTransfer

- ea: `0x14000d380`
- end: `0x14000d4df`
- name: `McTemplateU0zzzzqqq_EventWriteTransfer`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c4ac`

## callees

- `0x14000cd7c`
- `0x14000d380`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzqqq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        char a7,
        char a8,
        char a9)
{
  __int64 v9; // rax
  int v10; // r10d
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // rcx
  int v14; // ecx
  const wchar_t *v15; // rcx
  __int64 v16; // rdx
  int v17; // edx
  const wchar_t *v18; // rcx
  bool v19; // zf
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-61h] BYREF
  const wchar_t *v22; // [rsp+40h] [rbp-51h]
  int v23; // [rsp+48h] [rbp-49h]
  int v24; // [rsp+4Ch] [rbp-45h]
  const wchar_t *v25; // [rsp+50h] [rbp-41h]
  int v26; // [rsp+58h] [rbp-39h]
  int v27; // [rsp+5Ch] [rbp-35h]
  const wchar_t *v28; // [rsp+60h] [rbp-31h]
  int v29; // [rsp+68h] [rbp-29h]
  int v30; // [rsp+6Ch] [rbp-25h]
  const wchar_t *v31; // [rsp+70h] [rbp-21h]
  int v32; // [rsp+78h] [rbp-19h]
  int v33; // [rsp+7Ch] [rbp-15h]
  char *v34; // [rsp+80h] [rbp-11h]
  __int64 v35; // [rsp+88h] [rbp-9h]
  char *v36; // [rsp+90h] [rbp-1h]
  __int64 v37; // [rsp+98h] [rbp+7h]
  char *v38; // [rsp+A0h] [rbp+Fh]
  __int64 v39; // [rsp+A8h] [rbp+17h]

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
  v23 = v12;
  v24 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v22 = a3;
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
  v26 = v14;
  v15 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v27 = 0;
  v25 = a4;
  if ( a5 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a5[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v17 = 10;
  }
  v29 = v17;
  v30 = 0;
  if ( !a5 )
    v15 = L"NULL";
  v28 = v15;
  v18 = a6;
  v19 = a6 == 0;
  if ( a6 )
  {
    do
      ++v9;
    while ( a6[v9] );
    v10 = 2 * v9 + 2;
    v19 = a6 == 0;
  }
  v32 = v10;
  v34 = &a7;
  v33 = 0;
  v36 = &a8;
  if ( v19 )
    v18 = L"NULL";
  v31 = v18;
  v38 = &a9;
  v35 = 4;
  v37 = 4;
  v39 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v18,
           (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmTriggerActiveUserSession,
           (__int64)a3,
           8u,
           &v21);
}

```

## disassembly

```asm
0x14000d380  mov     [rsp-8+arg_0], rbx
0x14000d385  push    rbp
0x14000d386  lea     rbp, [rsp-2Fh]
0x14000d38b  sub     rsp, 0C0h
0x14000d392  mov     rax, cs:__security_cookie
0x14000d399  xor     rax, rsp
0x14000d39c  mov     [rbp+2Fh+var_10], rax
0x14000d3a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d3a4  xor     r11d, r11d
0x14000d3a7  mov     r10d, 0Ah
0x14000d3ad  test    r8, r8
0x14000d3b0  jz      short loc_14000D3C8
0x14000d3b2  mov     rcx, rax
0x14000d3b5  inc     rcx
0x14000d3b8  cmp     [r8+rcx*2], r11w
0x14000d3bd  jnz     short loc_14000D3B5
0x14000d3bf  lea     ecx, ds:2[rcx*2]
0x14000d3c6  jmp     short loc_14000D3CB
0x14000d3c8  mov     ecx, r10d
0x14000d3cb  test    r8, r8
0x14000d3ce  mov     [rbp+2Fh+var_78], ecx
0x14000d3d1  lea     rbx, aNull; "NULL"
0x14000d3d8  mov     [rbp+2Fh+var_74], r11d
0x14000d3dc  cmovz   r8, rbx
0x14000d3e0  mov     [rbp+2Fh+var_80], r8
0x14000d3e4  test    r9, r9
0x14000d3e7  jz      short loc_14000D3FF
0x14000d3e9  mov     rcx, rax
0x14000d3ec  inc     rcx
0x14000d3ef  cmp     [r9+rcx*2], r11w
0x14000d3f4  jnz     short loc_14000D3EC
0x14000d3f6  lea     ecx, ds:2[rcx*2]
0x14000d3fd  jmp     short loc_14000D402
0x14000d3ff  mov     ecx, r10d
0x14000d402  test    r9, r9
0x14000d405  mov     [rbp+2Fh+var_68], ecx
0x14000d408  mov     rcx, [rbp+2Fh+arg_20]
0x14000d40c  cmovz   r9, rbx
0x14000d410  mov     [rbp+2Fh+var_64], r11d
0x14000d414  mov     [rbp+2Fh+var_70], r9
0x14000d418  test    rcx, rcx
0x14000d41b  jz      short loc_14000D433
0x14000d41d  mov     rdx, rax
0x14000d420  inc     rdx
0x14000d423  cmp     [rcx+rdx*2], r11w
0x14000d428  jnz     short loc_14000D420
0x14000d42a  lea     edx, ds:2[rdx*2]
0x14000d431  jmp     short loc_14000D436
0x14000d433  mov     edx, r10d
0x14000d436  test    rcx, rcx
0x14000d439  mov     [rbp+2Fh+var_58], edx
0x14000d43c  mov     [rbp+2Fh+var_54], r11d
0x14000d440  cmovz   rcx, rbx
0x14000d444  mov     [rbp+2Fh+var_60], rcx
0x14000d448  mov     rcx, [rbp+2Fh+arg_28]
0x14000d44c  test    rcx, rcx
0x14000d44f  jz      short loc_14000D466
0x14000d451  inc     rax
0x14000d454  cmp     [rcx+rax*2], r11w
0x14000d459  jnz     short loc_14000D451
0x14000d45b  lea     r10d, ds:2[rax*2]
0x14000d463  test    rcx, rcx
0x14000d466  lea     rax, [rbp+2Fh+arg_30]
0x14000d46a  mov     [rbp+2Fh+var_48], r10d
0x14000d46e  mov     [rbp+2Fh+var_40], rax
0x14000d472  lea     rdx, EnterpriseDiagnosticsOmaDmTriggerActiveUserSession
0x14000d479  lea     rax, [rbp+2Fh+arg_38]
0x14000d47d  mov     [rbp+2Fh+var_44], r11d
0x14000d481  mov     [rbp+2Fh+var_30], rax
0x14000d485  cmovz   rcx, rbx
0x14000d489  lea     rax, [rbp+2Fh+arg_40]
0x14000d48d  mov     [rbp+2Fh+var_50], rcx
0x14000d491  mov     [rbp+2Fh+var_20], rax
0x14000d495  mov     r9d, 8
0x14000d49b  lea     rax, [rbp+2Fh+var_90]
0x14000d49f  mov     [rbp+2Fh+var_38], 4
0x14000d4a7  mov     [rsp+0C0h+var_A0], rax
0x14000d4ac  mov     [rbp+2Fh+var_28], 4
0x14000d4b4  mov     [rbp+2Fh+var_18], 4
0x14000d4bc  call    McGenEventWrite_EventWriteTransfer
0x14000d4c1  mov     rcx, [rbp+2Fh+var_10]
0x14000d4c5  xor     rcx, rsp; StackCookie
0x14000d4c8  call    __security_check_cookie
0x14000d4cd  mov     rbx, [rsp+0C0h+arg_0]
0x14000d4d5  add     rsp, 0C0h
0x14000d4dc  pop     rbp
0x14000d4dd  retn
```
