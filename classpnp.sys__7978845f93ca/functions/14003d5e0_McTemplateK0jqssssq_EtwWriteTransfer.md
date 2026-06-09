# McTemplateK0jqssssq_EtwWriteTransfer

- ea: `0x14003d5e0`
- end: `0x14003d724`
- name: `McTemplateK0jqssssq_EtwWriteTransfer`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003c3a4`

## callees

- `0x1400062a0`
- `0x14003d5e0`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqssssq_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        __int64 a4,
        char a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        char a10)
{
  const char *v10; // rcx
  __int64 v12; // rax
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rdx
  int v18; // edx
  const char *v19; // rcx
  __int64 v20; // rdx
  int v21; // edx
  const char *v22; // rcx
  bool v23; // zf
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+30h] [rbp-69h] BYREF
  __int64 v26; // [rsp+40h] [rbp-59h]
  __int64 v27; // [rsp+48h] [rbp-51h]
  char *v28; // [rsp+50h] [rbp-49h]
  __int64 v29; // [rsp+58h] [rbp-41h]
  const char *v30; // [rsp+60h] [rbp-39h]
  int v31; // [rsp+68h] [rbp-31h]
  int v32; // [rsp+6Ch] [rbp-2Dh]
  const char *v33; // [rsp+70h] [rbp-29h]
  int v34; // [rsp+78h] [rbp-21h]
  int v35; // [rsp+7Ch] [rbp-1Dh]
  const char *v36; // [rsp+80h] [rbp-19h]
  int v37; // [rsp+88h] [rbp-11h]
  int v38; // [rsp+8Ch] [rbp-Dh]
  const char *v39; // [rsp+90h] [rbp-9h]
  int v40; // [rsp+98h] [rbp-1h]
  int v41; // [rsp+9Ch] [rbp+3h]
  char *v42; // [rsp+A0h] [rbp+7h]
  __int64 v43; // [rsp+A8h] [rbp+Fh]

  v10 = a6;
  v26 = a4;
  v28 = &a5;
  v12 = -1;
  v27 = 16;
  v29 = 4;
  v13 = 5;
  if ( a6 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a6[v14] );
    v15 = v14 + 1;
  }
  else
  {
    v15 = 5;
  }
  v31 = v15;
  v32 = 0;
  if ( !a6 )
    v10 = "NULL";
  v30 = v10;
  v16 = a7;
  if ( a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a7[v17] );
    v18 = v17 + 1;
  }
  else
  {
    v18 = 5;
  }
  v34 = v18;
  v35 = 0;
  if ( !a7 )
    v16 = "NULL";
  v33 = v16;
  v19 = a8;
  if ( a8 )
  {
    v20 = -1;
    do
      ++v20;
    while ( a8[v20] );
    v21 = v20 + 1;
  }
  else
  {
    v21 = 5;
  }
  v37 = v21;
  v38 = 0;
  if ( !a8 )
    v19 = "NULL";
  v36 = v19;
  v22 = a9;
  v23 = a9 == 0;
  if ( a9 )
  {
    do
      ++v12;
    while ( a9[v12] );
    v13 = v12 + 1;
    v23 = a9 == 0;
  }
  v40 = v13;
  v42 = &a10;
  v41 = 0;
  if ( v23 )
    v22 = "NULL";
  v39 = v22;
  v43 = 4;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)v22,
           (const EVENT_DESCRIPTOR *)EventFailToProcessZoneCommandAsynchronously,
           a3,
           8u,
           &v25);
}

```

## disassembly

```asm
0x14003d5e0  push    rbp
0x14003d5e2  lea     rbp, [rsp-27h]
0x14003d5e7  sub     rsp, 0C0h
0x14003d5ee  mov     rax, cs:__security_cookie
0x14003d5f5  xor     rax, rsp
0x14003d5f8  mov     [rbp+27h+var_10], rax
0x14003d5fc  mov     rcx, [rbp+27h+arg_28]
0x14003d600  lea     rax, [rbp+27h+arg_20]
0x14003d604  mov     [rbp+27h+var_80], r9
0x14003d608  mov     r10, r8
0x14003d60b  xor     r9d, r9d
0x14003d60e  mov     [rbp+27h+var_70], rax
0x14003d612  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003d616  mov     [rbp+27h+var_78], 10h
0x14003d61e  mov     [rbp+27h+var_68], 4
0x14003d626  lea     r8d, [r9+5]
0x14003d62a  test    rcx, rcx
0x14003d62d  jz      short loc_14003D63F
0x14003d62f  mov     rdx, rax
0x14003d632  inc     rdx
0x14003d635  cmp     [rcx+rdx], r9b
0x14003d639  jnz     short loc_14003D632
0x14003d63b  inc     edx
0x14003d63d  jmp     short loc_14003D642
0x14003d63f  mov     edx, r8d
0x14003d642  test    rcx, rcx
0x14003d645  mov     [rbp+27h+var_58], edx
0x14003d648  lea     r11, aNull; "NULL"
0x14003d64f  mov     [rbp+27h+var_54], r9d
0x14003d653  cmovz   rcx, r11
0x14003d657  mov     [rbp+27h+var_60], rcx
0x14003d65b  mov     rcx, [rbp+27h+arg_30]
0x14003d65f  test    rcx, rcx
0x14003d662  jz      short loc_14003D674
0x14003d664  mov     rdx, rax
0x14003d667  inc     rdx
0x14003d66a  cmp     [rcx+rdx], r9b
0x14003d66e  jnz     short loc_14003D667
0x14003d670  inc     edx
0x14003d672  jmp     short loc_14003D677
0x14003d674  mov     edx, r8d
0x14003d677  test    rcx, rcx
0x14003d67a  mov     [rbp+27h+var_48], edx
0x14003d67d  mov     [rbp+27h+var_44], r9d
0x14003d681  cmovz   rcx, r11
0x14003d685  mov     [rbp+27h+var_50], rcx
0x14003d689  mov     rcx, [rbp+27h+arg_38]
0x14003d68d  test    rcx, rcx
0x14003d690  jz      short loc_14003D6A2
0x14003d692  mov     rdx, rax
0x14003d695  inc     rdx
0x14003d698  cmp     [rcx+rdx], r9b
0x14003d69c  jnz     short loc_14003D695
0x14003d69e  inc     edx
0x14003d6a0  jmp     short loc_14003D6A5
0x14003d6a2  mov     edx, r8d
0x14003d6a5  test    rcx, rcx
0x14003d6a8  mov     [rbp+27h+var_38], edx
0x14003d6ab  mov     [rbp+27h+var_34], r9d
0x14003d6af  cmovz   rcx, r11
0x14003d6b3  mov     [rbp+27h+var_40], rcx
0x14003d6b7  mov     rcx, [rbp+27h+arg_40]
0x14003d6bb  test    rcx, rcx
0x14003d6be  jz      short loc_14003D6D0
0x14003d6c0  inc     rax
0x14003d6c3  cmp     [rcx+rax], r9b
0x14003d6c7  jnz     short loc_14003D6C0
0x14003d6c9  lea     r8d, [rax+1]
0x14003d6cd  test    rcx, rcx
0x14003d6d0  lea     rax, [rbp+27h+arg_48]
0x14003d6d4  mov     [rbp+27h+var_28], r8d
0x14003d6d8  mov     [rbp+27h+var_20], rax
0x14003d6dc  lea     rdx, EventFailToProcessZoneCommandAsynchronously
0x14003d6e3  lea     rax, [rbp+27h+var_90]
0x14003d6e7  mov     [rbp+27h+var_24], r9d
0x14003d6eb  cmovz   rcx, r11
0x14003d6ef  mov     [rsp+0C0h+var_A0], rax
0x14003d6f4  mov     r9d, 8
0x14003d6fa  mov     [rbp+27h+var_30], rcx
0x14003d6fe  mov     r8, r10
0x14003d701  mov     [rbp+27h+var_18], 4
0x14003d709  call    McGenEventWrite_EtwWriteTransfer
0x14003d70e  mov     rcx, [rbp+27h+var_10]
0x14003d712  xor     rcx, rsp; StackCookie
0x14003d715  call    __security_check_cookie
0x14003d71a  add     rsp, 0C0h
0x14003d721  pop     rbp
0x14003d722  retn
```
