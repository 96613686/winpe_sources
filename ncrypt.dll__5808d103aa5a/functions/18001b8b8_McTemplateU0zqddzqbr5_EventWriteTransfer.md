# McTemplateU0zqddzqbr5_EventWriteTransfer

- ea: `0x18001b8b8`
- end: `0x18001b9c8`
- name: `McTemplateU0zqddzqbr5_EventWriteTransfer`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b784`

## callees

- `0x18000f698`
- `0x18001b8b8`
- `0x18001f1b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqddzqbr5_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        char a5,
        char a6,
        const wchar_t *a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ecx
  const wchar_t *v13; // rcx
  bool v14; // zf
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-61h] BYREF
  const wchar_t *v17; // [rsp+40h] [rbp-51h]
  int v18; // [rsp+48h] [rbp-49h]
  int v19; // [rsp+4Ch] [rbp-45h]
  int *v20; // [rsp+50h] [rbp-41h]
  __int64 v21; // [rsp+58h] [rbp-39h]
  char *v22; // [rsp+60h] [rbp-31h]
  __int64 v23; // [rsp+68h] [rbp-29h]
  char *v24; // [rsp+70h] [rbp-21h]
  __int64 v25; // [rsp+78h] [rbp-19h]
  const wchar_t *v26; // [rsp+80h] [rbp-11h]
  int v27; // [rsp+88h] [rbp-9h]
  int v28; // [rsp+8Ch] [rbp-5h]
  int *v29; // [rsp+90h] [rbp-1h]
  __int64 v30; // [rsp+98h] [rbp+7h]
  __int64 v31; // [rsp+A0h] [rbp+Fh]
  int v32; // [rsp+A8h] [rbp+17h]
  int v33; // [rsp+ACh] [rbp+1Bh]
  int v34; // [rsp+E8h] [rbp+57h] BYREF

  v34 = a4;
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
  v18 = v12;
  v19 = 0;
  v20 = &v34;
  v21 = 4;
  v22 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v17 = a3;
  v24 = &a6;
  v13 = a7;
  v23 = 4;
  v25 = 4;
  v14 = a7 == 0;
  if ( a7 )
  {
    do
      ++v9;
    while ( a7[v9] );
    v10 = 2 * v9 + 2;
    v14 = a7 == 0;
  }
  v27 = v10;
  v29 = &a8;
  if ( v14 )
    v13 = L"NULL";
  v31 = a9;
  v32 = a8;
  v28 = 0;
  v33 = 0;
  v26 = v13;
  v30 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v13,
           (const EVENT_DESCRIPTOR *)ETW_LOG_NCRYPT_UNPROTECT_KEY_FAILED,
           (__int64)a3,
           8u,
           &v16);
}

```

## disassembly

```asm
0x18001b8b8  mov     [rsp-8+arg_18], r9d
0x18001b8bd  push    rbp
0x18001b8be  lea     rbp, [rsp-2Fh]
0x18001b8c3  sub     rsp, 0C0h
0x18001b8ca  mov     rax, cs:__security_cookie
0x18001b8d1  xor     rax, rsp
0x18001b8d4  mov     [rbp+2Fh+var_10], rax
0x18001b8d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b8dc  xor     r9d, r9d
0x18001b8df  mov     edx, 0Ah
0x18001b8e4  test    r8, r8
0x18001b8e7  jz      short loc_18001B8FF
0x18001b8e9  mov     rcx, rax
0x18001b8ec  inc     rcx
0x18001b8ef  cmp     [r8+rcx*2], r9w
0x18001b8f4  jnz     short loc_18001B8EC
0x18001b8f6  lea     ecx, ds:2[rcx*2]
0x18001b8fd  jmp     short loc_18001B901
0x18001b8ff  mov     ecx, edx
0x18001b901  mov     [rbp+2Fh+var_78], ecx
0x18001b904  lea     r10, aNull_0; "NULL"
0x18001b90b  lea     rcx, [rbp+2Fh+arg_18]
0x18001b90f  mov     [rbp+2Fh+var_74], r9d
0x18001b913  mov     [rbp+2Fh+var_70], rcx
0x18001b917  test    r8, r8
0x18001b91a  lea     rcx, [rbp+2Fh+arg_20]
0x18001b91e  mov     [rbp+2Fh+var_68], 4
0x18001b926  mov     [rbp+2Fh+var_60], rcx
0x18001b92a  cmovz   r8, r10
0x18001b92e  lea     rcx, [rbp+2Fh+arg_28]
0x18001b932  mov     [rbp+2Fh+var_80], r8
0x18001b936  mov     [rbp+2Fh+var_50], rcx
0x18001b93a  mov     rcx, [rbp+2Fh+arg_30]
0x18001b93e  mov     [rbp+2Fh+var_58], 4
0x18001b946  mov     [rbp+2Fh+var_48], 4
0x18001b94e  test    rcx, rcx
0x18001b951  jz      short loc_18001B967
0x18001b953  inc     rax
0x18001b956  cmp     [rcx+rax*2], r9w
0x18001b95b  jnz     short loc_18001B953
0x18001b95d  lea     edx, ds:2[rax*2]
0x18001b964  test    rcx, rcx
0x18001b967  lea     rax, [rbp+2Fh+arg_38]
0x18001b96b  mov     [rbp+2Fh+var_38], edx
0x18001b96e  mov     [rbp+2Fh+var_30], rax
0x18001b972  lea     rdx, ETW_LOG_NCRYPT_UNPROTECT_KEY_FAILED
0x18001b979  mov     rax, [rbp+2Fh+arg_40]
0x18001b97d  cmovz   rcx, r10
0x18001b981  mov     [rbp+2Fh+var_20], rax
0x18001b985  mov     eax, [rbp+2Fh+arg_38]
0x18001b988  mov     [rbp+2Fh+var_18], eax
0x18001b98b  lea     rax, [rbp+2Fh+var_90]
0x18001b98f  mov     [rbp+2Fh+var_34], r9d
0x18001b993  mov     [rbp+2Fh+var_14], r9d
0x18001b997  mov     r9d, 8
0x18001b99d  mov     [rsp+0C0h+var_A0], rax
0x18001b9a2  mov     [rbp+2Fh+var_40], rcx
0x18001b9a6  mov     [rbp+2Fh+var_28], 4
0x18001b9ae  call    McGenEventWrite_EventWriteTransfer
0x18001b9b3  mov     rcx, [rbp+2Fh+var_10]
0x18001b9b7  xor     rcx, rsp; StackCookie
0x18001b9ba  call    __security_check_cookie
0x18001b9bf  add     rsp, 0C0h
0x18001b9c6  pop     rbp
0x18001b9c7  retn
```
