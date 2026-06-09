# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x18001b364`
- end: `0x18001b493`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800195c0`

## callees

- `0x180001800`
- `0x18001b0cc`
- `0x18001b364`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v7; // r10d
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-9h]
  int v20; // [rsp+48h] [rbp-1h]
  int v21; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v22; // [rsp+50h] [rbp+7h]
  int v23; // [rsp+58h] [rbp+Fh]
  int v24; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v25; // [rsp+60h] [rbp+17h]
  int v26; // [rsp+68h] [rbp+1Fh]
  int v27; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v28; // [rsp+70h] [rbp+27h]
  int v29; // [rsp+78h] [rbp+2Fh]
  int v30; // [rsp+7Ch] [rbp+33h]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v20 = v9;
  v21 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v19 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v23 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 0;
  v22 = a4;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v26 = v14;
  v27 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v25 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v29 = v7;
  v28 = v15;
  v30 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_Configuration,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x18001b364  mov     [rsp-8+arg_0], rbx
0x18001b369  push    rbp
0x18001b36a  lea     rbp, [rsp-47h]
0x18001b36f  sub     rsp, 90h
0x18001b376  mov     rax, cs:__security_cookie
0x18001b37d  xor     rax, rsp
0x18001b380  mov     [rbp+47h+var_10], rax
0x18001b384  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b388  xor     r11d, r11d
0x18001b38b  mov     r10d, 0Ah
0x18001b391  test    r8, r8
0x18001b394  jz      short loc_18001B3AC
0x18001b396  mov     rcx, rax
0x18001b399  inc     rcx
0x18001b39c  cmp     [r8+rcx*2], r11w
0x18001b3a1  jnz     short loc_18001B399
0x18001b3a3  lea     ecx, ds:2[rcx*2]
0x18001b3aa  jmp     short loc_18001B3AF
0x18001b3ac  mov     ecx, r10d
0x18001b3af  test    r8, r8
0x18001b3b2  mov     [rbp+47h+var_48], ecx
0x18001b3b5  lea     rbx, aNull; "NULL"
0x18001b3bc  mov     [rbp+47h+var_44], r11d
0x18001b3c0  cmovz   r8, rbx
0x18001b3c4  mov     [rbp+47h+var_50], r8
0x18001b3c8  test    r9, r9
0x18001b3cb  jz      short loc_18001B3E3
0x18001b3cd  mov     rcx, rax
0x18001b3d0  inc     rcx
0x18001b3d3  cmp     [r9+rcx*2], r11w
0x18001b3d8  jnz     short loc_18001B3D0
0x18001b3da  lea     ecx, ds:2[rcx*2]
0x18001b3e1  jmp     short loc_18001B3E6
0x18001b3e3  mov     ecx, r10d
0x18001b3e6  test    r9, r9
0x18001b3e9  mov     [rbp+47h+var_38], ecx
0x18001b3ec  mov     rcx, [rbp+47h+arg_20]
0x18001b3f0  cmovz   r9, rbx
0x18001b3f4  mov     [rbp+47h+var_34], r11d
0x18001b3f8  mov     [rbp+47h+var_40], r9
0x18001b3fc  test    rcx, rcx
0x18001b3ff  jz      short loc_18001B417
0x18001b401  mov     rdx, rax
0x18001b404  inc     rdx
0x18001b407  cmp     [rcx+rdx*2], r11w
0x18001b40c  jnz     short loc_18001B404
0x18001b40e  lea     edx, ds:2[rdx*2]
0x18001b415  jmp     short loc_18001B41A
0x18001b417  mov     edx, r10d
0x18001b41a  test    rcx, rcx
0x18001b41d  mov     [rbp+47h+var_28], edx
0x18001b420  mov     [rbp+47h+var_24], r11d
0x18001b424  cmovz   rcx, rbx
0x18001b428  mov     [rbp+47h+var_30], rcx
0x18001b42c  mov     rcx, [rbp+47h+arg_28]
0x18001b430  test    rcx, rcx
0x18001b433  jz      short loc_18001B44A
0x18001b435  inc     rax
0x18001b438  cmp     [rcx+rax*2], r11w
0x18001b43d  jnz     short loc_18001B435
0x18001b43f  lea     r10d, ds:2[rax*2]
0x18001b447  test    rcx, rcx
0x18001b44a  cmovz   rcx, rbx
0x18001b44e  mov     [rbp+47h+var_18], r10d
0x18001b452  lea     rax, [rbp+47h+var_60]
0x18001b456  mov     [rbp+47h+var_20], rcx
0x18001b45a  mov     r9d, 5
0x18001b460  mov     [rsp+90h+var_70], rax
0x18001b465  lea     rdx, TraceMerge_NGEN_Configuration
0x18001b46c  mov     [rbp+47h+var_14], r11d
0x18001b470  call    McGenEventWrite_EventWriteTransfer
0x18001b475  mov     rcx, [rbp+47h+var_10]
0x18001b479  xor     rcx, rsp; StackCookie
0x18001b47c  call    __security_check_cookie
0x18001b481  mov     rbx, [rsp+90h+arg_0]
0x18001b489  add     rsp, 90h
0x18001b490  pop     rbp
0x18001b491  retn
```
