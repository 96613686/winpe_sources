# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x18001a8b4`
- end: `0x18001a9e2`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018bac`

## callees

- `0x1800017e0`
- `0x18001a62c`
- `0x18001a8b4`

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
0x18001a8b4  mov     [rsp-8+arg_0], rbx
0x18001a8b9  push    rbp
0x18001a8ba  lea     rbp, [rsp-47h]
0x18001a8bf  sub     rsp, 90h
0x18001a8c6  mov     rax, cs:__security_cookie
0x18001a8cd  xor     rax, rsp
0x18001a8d0  mov     [rbp+47h+var_10], rax
0x18001a8d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a8d8  xor     r11d, r11d
0x18001a8db  mov     r10d, 0Ah
0x18001a8e1  test    r8, r8
0x18001a8e4  jz      short loc_18001A8FC
0x18001a8e6  mov     rcx, rax
0x18001a8e9  inc     rcx
0x18001a8ec  cmp     [r8+rcx*2], r11w
0x18001a8f1  jnz     short loc_18001A8E9
0x18001a8f3  lea     ecx, ds:2[rcx*2]
0x18001a8fa  jmp     short loc_18001A8FF
0x18001a8fc  mov     ecx, r10d
0x18001a8ff  test    r8, r8
0x18001a902  mov     [rbp+47h+var_48], ecx
0x18001a905  lea     rbx, aNull; "NULL"
0x18001a90c  mov     [rbp+47h+var_44], r11d
0x18001a910  cmovz   r8, rbx
0x18001a914  mov     [rbp+47h+var_50], r8
0x18001a918  test    r9, r9
0x18001a91b  jz      short loc_18001A933
0x18001a91d  mov     rcx, rax
0x18001a920  inc     rcx
0x18001a923  cmp     [r9+rcx*2], r11w
0x18001a928  jnz     short loc_18001A920
0x18001a92a  lea     ecx, ds:2[rcx*2]
0x18001a931  jmp     short loc_18001A936
0x18001a933  mov     ecx, r10d
0x18001a936  test    r9, r9
0x18001a939  mov     [rbp+47h+var_38], ecx
0x18001a93c  mov     rcx, [rbp+47h+arg_20]
0x18001a940  cmovz   r9, rbx
0x18001a944  mov     [rbp+47h+var_34], r11d
0x18001a948  mov     [rbp+47h+var_40], r9
0x18001a94c  test    rcx, rcx
0x18001a94f  jz      short loc_18001A967
0x18001a951  mov     rdx, rax
0x18001a954  inc     rdx
0x18001a957  cmp     [rcx+rdx*2], r11w
0x18001a95c  jnz     short loc_18001A954
0x18001a95e  lea     edx, ds:2[rdx*2]
0x18001a965  jmp     short loc_18001A96A
0x18001a967  mov     edx, r10d
0x18001a96a  test    rcx, rcx
0x18001a96d  mov     [rbp+47h+var_28], edx
0x18001a970  mov     [rbp+47h+var_24], r11d
0x18001a974  cmovz   rcx, rbx
0x18001a978  mov     [rbp+47h+var_30], rcx
0x18001a97c  mov     rcx, [rbp+47h+arg_28]
0x18001a980  test    rcx, rcx
0x18001a983  jz      short loc_18001A99A
0x18001a985  inc     rax
0x18001a988  cmp     [rcx+rax*2], r11w
0x18001a98d  jnz     short loc_18001A985
0x18001a98f  lea     r10d, ds:2[rax*2]
0x18001a997  test    rcx, rcx
0x18001a99a  cmovz   rcx, rbx
0x18001a99e  mov     [rbp+47h+var_18], r10d
0x18001a9a2  lea     rax, [rbp+47h+var_60]
0x18001a9a6  mov     [rbp+47h+var_20], rcx
0x18001a9aa  mov     r9d, 5
0x18001a9b0  mov     [rsp+90h+var_70], rax
0x18001a9b5  lea     rdx, TraceMerge_NGEN_Configuration
0x18001a9bc  mov     [rbp+47h+var_14], r11d
0x18001a9c0  call    McGenEventWrite_EventWriteTransfer
0x18001a9c5  mov     rcx, [rbp+47h+var_10]
0x18001a9c9  xor     rcx, rsp; StackCookie
0x18001a9cc  call    __security_check_cookie
0x18001a9d1  mov     rbx, [rsp+90h+arg_0]
0x18001a9d9  add     rsp, 90h
0x18001a9e0  pop     rbp
0x18001a9e1  retn
```
