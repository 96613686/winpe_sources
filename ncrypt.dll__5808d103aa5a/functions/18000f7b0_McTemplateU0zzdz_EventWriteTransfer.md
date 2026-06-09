# McTemplateU0zzdz_EventWriteTransfer

- ea: `0x18000f7b0`
- end: `0x18000f8b2`
- name: `McTemplateU0zzdz_EventWriteTransfer`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019b84`

## callees

- `0x18000f698`
- `0x18000f7b0`
- `0x18001f1b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzdz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  bool v13; // zf
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-9h]
  int v17; // [rsp+48h] [rbp-1h]
  int v18; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v19; // [rsp+50h] [rbp+7h]
  int v20; // [rsp+58h] [rbp+Fh]
  int v21; // [rsp+5Ch] [rbp+13h]
  char *v22; // [rsp+60h] [rbp+17h]
  __int64 v23; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v24; // [rsp+70h] [rbp+27h]
  int v25; // [rsp+78h] [rbp+2Fh]
  int v26; // [rsp+7Ch] [rbp+33h]

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
  v17 = v9;
  v18 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v16 = a3;
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
  v20 = v11;
  v21 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v22 = &a5;
  v12 = a6;
  v19 = a4;
  v23 = 4;
  v13 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v13 = a6 == 0;
  }
  if ( v13 )
    v12 = L"NULL";
  v25 = v7;
  v24 = v12;
  v26 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v12,
           (const EVENT_DESCRIPTOR *)ETW_LOG_NCRYPT_OPEN_KEY_FAILED,
           (__int64)a3,
           5u,
           &v15);
}

```

## disassembly

```asm
0x18000f7b0  push    rbp
0x18000f7b2  lea     rbp, [rsp-47h]
0x18000f7b7  sub     rsp, 90h
0x18000f7be  mov     rax, cs:__security_cookie
0x18000f7c5  xor     rax, rsp
0x18000f7c8  mov     [rbp+47h+var_10], rax
0x18000f7cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f7d0  xor     r10d, r10d
0x18000f7d3  mov     edx, 0Ah
0x18000f7d8  test    r8, r8
0x18000f7db  jz      loc_18000F8AB
0x18000f7e1  mov     rcx, rax
0x18000f7e4  inc     rcx
0x18000f7e7  cmp     [r8+rcx*2], r10w
0x18000f7ec  jnz     short loc_18000F7E4
0x18000f7ee  lea     ecx, ds:2[rcx*2]
0x18000f7f5  test    r8, r8
0x18000f7f8  mov     [rbp+47h+var_48], ecx
0x18000f7fb  lea     r11, aNull_0; "NULL"
0x18000f802  mov     [rbp+47h+var_44], r10d
0x18000f806  cmovz   r8, r11
0x18000f80a  mov     [rbp+47h+var_50], r8
0x18000f80e  test    r9, r9
0x18000f811  jz      short loc_18000F891
0x18000f813  mov     rcx, rax
0x18000f816  inc     rcx
0x18000f819  cmp     [r9+rcx*2], r10w
0x18000f81e  jnz     short loc_18000F816
0x18000f820  lea     ecx, ds:2[rcx*2]
0x18000f827  mov     [rbp+47h+var_38], ecx
0x18000f82a  test    r9, r9
0x18000f82d  lea     rcx, [rbp+47h+arg_20]
0x18000f831  mov     [rbp+47h+var_34], r10d
0x18000f835  cmovz   r9, r11
0x18000f839  mov     [rbp+47h+var_30], rcx
0x18000f83d  mov     rcx, [rbp+47h+arg_28]
0x18000f841  mov     [rbp+47h+var_40], r9
0x18000f845  mov     [rbp+47h+var_28], 4
0x18000f84d  test    rcx, rcx
0x18000f850  jnz     short loc_18000F895
0x18000f852  cmovz   rcx, r11
0x18000f856  mov     [rbp+47h+var_18], edx
0x18000f859  lea     rax, [rbp+47h+var_60]
0x18000f85d  mov     [rbp+47h+var_20], rcx
0x18000f861  lea     rdx, ETW_LOG_NCRYPT_OPEN_KEY_FAILED
0x18000f868  mov     [rsp+90h+var_70], rax
0x18000f86d  mov     r9d, 5
0x18000f873  mov     [rbp+47h+var_14], r10d
0x18000f877  call    McGenEventWrite_EventWriteTransfer
0x18000f87c  mov     rcx, [rbp+47h+var_10]
0x18000f880  xor     rcx, rsp; StackCookie
0x18000f883  call    __security_check_cookie
0x18000f888  add     rsp, 90h
0x18000f88f  pop     rbp
0x18000f890  retn
0x18000f891  mov     ecx, edx
0x18000f893  jmp     short loc_18000F827
0x18000f895  inc     rax
0x18000f898  cmp     [rcx+rax*2], r10w
0x18000f89d  jnz     short loc_18000F895
0x18000f89f  lea     edx, ds:2[rax*2]
0x18000f8a6  test    rcx, rcx
0x18000f8a9  jmp     short loc_18000F852
0x18000f8ab  mov     ecx, edx
0x18000f8ad  jmp     loc_18000F7F5
```
