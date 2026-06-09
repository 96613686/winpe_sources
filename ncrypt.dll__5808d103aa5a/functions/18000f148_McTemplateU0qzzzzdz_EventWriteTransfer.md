# McTemplateU0qzzzzdz_EventWriteTransfer

- ea: `0x18000f148`
- end: `0x18000f285`
- name: `McTemplateU0qzzzzdz_EventWriteTransfer`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ed40`
- `0x180010684`

## callees

- `0x18000f148`
- `0x18000f698`
- `0x18001f1b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzzzzdz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5,
        int a6,
        int a7,
        char a8,
        const wchar_t *a9)
{
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ecx
  const wchar_t *v13; // r8
  __int64 v14; // rcx
  int v15; // ecx
  const wchar_t *v16; // rcx
  bool v17; // zf
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-61h] BYREF
  int *v20; // [rsp+40h] [rbp-51h]
  __int64 v21; // [rsp+48h] [rbp-49h]
  const wchar_t *v22; // [rsp+50h] [rbp-41h]
  int v23; // [rsp+58h] [rbp-39h]
  int v24; // [rsp+5Ch] [rbp-35h]
  const wchar_t *v25; // [rsp+60h] [rbp-31h]
  int v26; // [rsp+68h] [rbp-29h]
  int v27; // [rsp+6Ch] [rbp-25h]
  const size_t *v28; // [rsp+70h] [rbp-21h]
  __int64 v29; // [rsp+78h] [rbp-19h]
  const size_t *v30; // [rsp+80h] [rbp-11h]
  __int64 v31; // [rsp+88h] [rbp-9h]
  char *v32; // [rsp+90h] [rbp-1h]
  __int64 v33; // [rsp+98h] [rbp+7h]
  const wchar_t *v34; // [rsp+A0h] [rbp+Fh]
  int v35; // [rsp+A8h] [rbp+17h]
  int v36; // [rsp+ACh] [rbp+1Bh]
  int v37; // [rsp+E0h] [rbp+4Fh] BYREF

  v37 = a3;
  v21 = 4;
  v20 = &v37;
  v9 = -1;
  v10 = 10;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v13 = a5;
  v23 = v12;
  v24 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v22 = a4;
  if ( a5 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v26 = v15;
  v27 = 0;
  if ( !a5 )
    v13 = L"NULL";
  v32 = &a8;
  v16 = a9;
  v25 = v13;
  v28 = &LocaleName;
  v30 = &LocaleName;
  v29 = 2;
  v31 = 2;
  v33 = 4;
  v17 = a9 == 0;
  if ( a9 )
  {
    do
      ++v9;
    while ( a9[v9] );
    v10 = 2 * v9 + 2;
    v17 = a9 == 0;
  }
  if ( v17 )
    v16 = L"NULL";
  v35 = v10;
  v34 = v16;
  v36 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v16,
           (const EVENT_DESCRIPTOR *)ETW_LOG_NCRYPT_OPERATION_FAILED,
           (__int64)&LocaleName,
           8u,
           &v19);
}

```

## disassembly

```asm
0x18000f148  mov     [rsp-8+arg_10], r8d
0x18000f14d  push    rbp
0x18000f14e  lea     rbp, [rsp-2Fh]
0x18000f153  sub     rsp, 0C0h
0x18000f15a  mov     rax, cs:__security_cookie
0x18000f161  xor     rax, rsp
0x18000f164  mov     [rbp+2Fh+var_10], rax
0x18000f168  lea     rax, [rbp+2Fh+arg_10]
0x18000f16c  mov     [rbp+2Fh+var_78], 4
0x18000f174  xor     r10d, r10d
0x18000f177  mov     [rbp+2Fh+var_80], rax
0x18000f17b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f17f  lea     edx, [r10+0Ah]
0x18000f183  test    r9, r9
0x18000f186  jz      loc_18000F27E
0x18000f18c  mov     rcx, rax
0x18000f18f  inc     rcx
0x18000f192  cmp     [r9+rcx*2], r10w
0x18000f197  jnz     short loc_18000F18F
0x18000f199  lea     ecx, ds:2[rcx*2]
0x18000f1a0  mov     r8, [rbp+2Fh+arg_20]
0x18000f1a4  lea     r11, aNull_0; "NULL"
0x18000f1ab  test    r9, r9
0x18000f1ae  mov     [rbp+2Fh+var_68], ecx
0x18000f1b1  mov     [rbp+2Fh+var_64], r10d
0x18000f1b5  cmovz   r9, r11
0x18000f1b9  mov     [rbp+2Fh+var_70], r9
0x18000f1bd  test    r8, r8
0x18000f1c0  jz      loc_18000F277
0x18000f1c6  mov     rcx, rax
0x18000f1c9  inc     rcx
0x18000f1cc  cmp     [r8+rcx*2], r10w
0x18000f1d1  jnz     short loc_18000F1C9
0x18000f1d3  lea     ecx, ds:2[rcx*2]
0x18000f1da  test    r8, r8
0x18000f1dd  mov     [rbp+2Fh+var_58], ecx
0x18000f1e0  lea     rcx, [rbp+2Fh+arg_38]
0x18000f1e4  mov     [rbp+2Fh+var_54], r10d
0x18000f1e8  cmovz   r8, r11
0x18000f1ec  mov     [rbp+2Fh+var_30], rcx
0x18000f1f0  mov     rcx, [rbp+2Fh+arg_40]
0x18000f1f4  mov     [rbp+2Fh+var_60], r8
0x18000f1f8  lea     r8, LocaleName
0x18000f1ff  mov     [rbp+2Fh+var_50], r8
0x18000f203  mov     [rbp+2Fh+var_40], r8
0x18000f207  mov     [rbp+2Fh+var_48], 2
0x18000f20f  mov     [rbp+2Fh+var_38], 2
0x18000f217  mov     [rbp+2Fh+var_28], 4
0x18000f21f  test    rcx, rcx
0x18000f222  jz      short loc_18000F238
0x18000f224  inc     rax
0x18000f227  cmp     [rcx+rax*2], r10w
0x18000f22c  jnz     short loc_18000F224
0x18000f22e  lea     edx, ds:2[rax*2]
0x18000f235  test    rcx, rcx
0x18000f238  cmovz   rcx, r11
0x18000f23c  mov     [rbp+2Fh+var_18], edx
0x18000f23f  lea     rax, [rbp+2Fh+var_90]
0x18000f243  mov     [rbp+2Fh+var_20], rcx
0x18000f247  lea     rdx, ETW_LOG_NCRYPT_OPERATION_FAILED
0x18000f24e  mov     [rsp+0C0h+var_A0], rax
0x18000f253  mov     r9d, 8
0x18000f259  mov     [rbp+2Fh+var_14], r10d
0x18000f25d  call    McGenEventWrite_EventWriteTransfer
0x18000f262  mov     rcx, [rbp+2Fh+var_10]
0x18000f266  xor     rcx, rsp; StackCookie
0x18000f269  call    __security_check_cookie
0x18000f26e  add     rsp, 0C0h
0x18000f275  pop     rbp
0x18000f276  retn
0x18000f277  mov     ecx, edx
0x18000f279  jmp     loc_18000F1DA
0x18000f27e  mov     ecx, edx
0x18000f280  jmp     loc_18000F1A0
```
