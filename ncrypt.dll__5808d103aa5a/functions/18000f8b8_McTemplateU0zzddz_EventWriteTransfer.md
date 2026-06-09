# McTemplateU0zzddz_EventWriteTransfer

- ea: `0x18000f8b8`
- end: `0x18000f9d1`
- name: `McTemplateU0zzddz_EventWriteTransfer`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800106f0`

## callees

- `0x18000f698`
- `0x18000f8b8`
- `0x18001f1b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzddz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6,
        const wchar_t *a7)
{
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // rcx
  int v12; // ecx
  const wchar_t *v13; // rcx
  bool v14; // zf
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v17; // [rsp+40h] [rbp-21h]
  int v18; // [rsp+48h] [rbp-19h]
  int v19; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v20; // [rsp+50h] [rbp-11h]
  int v21; // [rsp+58h] [rbp-9h]
  int v22; // [rsp+5Ch] [rbp-5h]
  char *v23; // [rsp+60h] [rbp-1h]
  __int64 v24; // [rsp+68h] [rbp+7h]
  char *v25; // [rsp+70h] [rbp+Fh]
  __int64 v26; // [rsp+78h] [rbp+17h]
  const wchar_t *v27; // [rsp+80h] [rbp+1Fh]
  int v28; // [rsp+88h] [rbp+27h]
  int v29; // [rsp+8Ch] [rbp+2Bh]

  v7 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v18 = v10;
  v19 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v17 = a3;
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
  v21 = v12;
  v22 = 0;
  v23 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v20 = a4;
  v25 = &a6;
  v13 = a7;
  v24 = 4;
  v26 = 4;
  v14 = a7 == 0;
  if ( a7 )
  {
    do
      ++v7;
    while ( a7[v7] );
    v8 = 2 * v7 + 2;
    v14 = a7 == 0;
  }
  if ( v14 )
    v13 = L"NULL";
  v28 = v8;
  v27 = v13;
  v29 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v13,
           (const EVENT_DESCRIPTOR *)ETW_LOG_NCRYPT_PROTECT_KEY_FAILED,
           (__int64)a3,
           6u,
           &v16);
}

```

## disassembly

```asm
0x18000f8b8  push    rbp
0x18000f8ba  lea     rbp, [rsp-3Fh]
0x18000f8bf  sub     rsp, 0A0h
0x18000f8c6  mov     rax, cs:__security_cookie
0x18000f8cd  xor     rax, rsp
0x18000f8d0  mov     [rbp+3Fh+var_10], rax
0x18000f8d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f8d8  xor     r10d, r10d
0x18000f8db  mov     edx, 0Ah
0x18000f8e0  test    r8, r8
0x18000f8e3  jz      loc_18000F9AD
0x18000f8e9  mov     rcx, rax
0x18000f8ec  inc     rcx
0x18000f8ef  cmp     [r8+rcx*2], r10w
0x18000f8f4  jnz     short loc_18000F8EC
0x18000f8f6  lea     ecx, ds:2[rcx*2]
0x18000f8fd  test    r8, r8
0x18000f900  mov     [rbp+3Fh+var_58], ecx
0x18000f903  lea     r11, aNull_0; "NULL"
0x18000f90a  mov     [rbp+3Fh+var_54], r10d
0x18000f90e  cmovz   r8, r11
0x18000f912  mov     [rbp+3Fh+var_60], r8
0x18000f916  test    r9, r9
0x18000f919  jz      loc_18000F9B4
0x18000f91f  mov     rcx, rax
0x18000f922  inc     rcx
0x18000f925  cmp     [r9+rcx*2], r10w
0x18000f92a  jnz     short loc_18000F922
0x18000f92c  lea     ecx, ds:2[rcx*2]
0x18000f933  mov     [rbp+3Fh+var_48], ecx
0x18000f936  test    r9, r9
0x18000f939  lea     rcx, [rbp+3Fh+arg_20]
0x18000f93d  mov     [rbp+3Fh+var_44], r10d
0x18000f941  mov     [rbp+3Fh+var_40], rcx
0x18000f945  cmovz   r9, r11
0x18000f949  lea     rcx, [rbp+3Fh+arg_28]
0x18000f94d  mov     [rbp+3Fh+var_50], r9
0x18000f951  mov     [rbp+3Fh+var_30], rcx
0x18000f955  mov     rcx, [rbp+3Fh+arg_30]
0x18000f959  mov     [rbp+3Fh+var_38], 4
0x18000f961  mov     [rbp+3Fh+var_28], 4
0x18000f969  test    rcx, rcx
0x18000f96c  jnz     short loc_18000F9BB
0x18000f96e  cmovz   rcx, r11
0x18000f972  mov     [rbp+3Fh+var_18], edx
0x18000f975  lea     rax, [rbp+3Fh+var_70]
0x18000f979  mov     [rbp+3Fh+var_20], rcx
0x18000f97d  lea     rdx, ETW_LOG_NCRYPT_PROTECT_KEY_FAILED
0x18000f984  mov     [rsp+0A0h+var_80], rax
0x18000f989  mov     r9d, 6
0x18000f98f  mov     [rbp+3Fh+var_14], r10d
0x18000f993  call    McGenEventWrite_EventWriteTransfer
0x18000f998  mov     rcx, [rbp+3Fh+var_10]
0x18000f99c  xor     rcx, rsp; StackCookie
0x18000f99f  call    __security_check_cookie
0x18000f9a4  add     rsp, 0A0h
0x18000f9ab  pop     rbp
0x18000f9ac  retn
0x18000f9ad  mov     ecx, edx
0x18000f9af  jmp     loc_18000F8FD
0x18000f9b4  mov     ecx, edx
0x18000f9b6  jmp     loc_18000F933
0x18000f9bb  inc     rax
0x18000f9be  cmp     [rcx+rax*2], r10w
0x18000f9c3  jnz     short loc_18000F9BB
0x18000f9c5  lea     edx, ds:2[rax*2]
0x18000f9cc  test    rcx, rcx
0x18000f9cf  jmp     short loc_18000F96E
```
