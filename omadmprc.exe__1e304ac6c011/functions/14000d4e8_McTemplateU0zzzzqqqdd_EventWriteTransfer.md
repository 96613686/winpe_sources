# McTemplateU0zzzzqqqdd_EventWriteTransfer

- ea: `0x14000d4e8`
- end: `0x14000d66c`
- name: `McTemplateU0zzzzqqqdd_EventWriteTransfer`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c1a4`
- `0x14000c328`

## callees

- `0x14000cd7c`
- `0x14000d4e8`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzqqqdd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  __int64 v11; // rax
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // ecx
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  int v19; // edx
  const wchar_t *v20; // rcx
  int v21; // eax
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+30h] [rbp-91h] BYREF
  const wchar_t *v24; // [rsp+40h] [rbp-81h]
  int v25; // [rsp+48h] [rbp-79h]
  int v26; // [rsp+4Ch] [rbp-75h]
  const wchar_t *v27; // [rsp+50h] [rbp-71h]
  int v28; // [rsp+58h] [rbp-69h]
  int v29; // [rsp+5Ch] [rbp-65h]
  const wchar_t *v30; // [rsp+60h] [rbp-61h]
  int v31; // [rsp+68h] [rbp-59h]
  int v32; // [rsp+6Ch] [rbp-55h]
  const wchar_t *v33; // [rsp+70h] [rbp-51h]
  int v34; // [rsp+78h] [rbp-49h]
  int v35; // [rsp+7Ch] [rbp-45h]
  char *v36; // [rsp+80h] [rbp-41h]
  __int64 v37; // [rsp+88h] [rbp-39h]
  char *v38; // [rsp+90h] [rbp-31h]
  __int64 v39; // [rsp+98h] [rbp-29h]
  char *v40; // [rsp+A0h] [rbp-21h]
  __int64 v41; // [rsp+A8h] [rbp-19h]
  char *v42; // [rsp+B0h] [rbp-11h]
  __int64 v43; // [rsp+B8h] [rbp-9h]
  char *v44; // [rsp+C0h] [rbp-1h]
  __int64 v45; // [rsp+C8h] [rbp+7h]

  v11 = -1;
  if ( a3 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v25 = v14;
  v26 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v24 = a3;
  if ( a4 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v28 = v16;
  v17 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v29 = 0;
  v27 = a4;
  if ( a5 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a5[v18] );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v19 = 10;
  }
  v31 = v19;
  v32 = 0;
  if ( !a5 )
    v17 = L"NULL";
  v30 = v17;
  v20 = a6;
  if ( a6 )
  {
    do
      ++v11;
    while ( a6[v11] );
    v21 = 2 * v11 + 2;
  }
  else
  {
    v21 = 10;
  }
  v34 = v21;
  v35 = 0;
  v36 = &a7;
  if ( !a6 )
    v20 = L"NULL";
  v33 = v20;
  v38 = &a8;
  v37 = 4;
  v40 = &a9;
  v39 = 4;
  v42 = &a10;
  v44 = &a11;
  v41 = 4;
  v43 = 4;
  v45 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)v20, a2, (__int64)a3, 0xAu, &v23);
}

```

## disassembly

```asm
0x14000d4e8  mov     [rsp-8+arg_0], rbx
0x14000d4ed  mov     [rsp-8+arg_10], rdi
0x14000d4f2  push    rbp
0x14000d4f3  lea     rbp, [rsp-1Fh]
0x14000d4f8  sub     rsp, 0E0h
0x14000d4ff  mov     rax, cs:__security_cookie
0x14000d506  xor     rax, rsp
0x14000d509  mov     [rbp+1Fh+var_10], rax
0x14000d50d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d511  xor     r11d, r11d
0x14000d514  mov     r10, rdx
0x14000d517  mov     ebx, 0Ah
0x14000d51c  test    r8, r8
0x14000d51f  jz      short loc_14000D537
0x14000d521  mov     rcx, rax
0x14000d524  inc     rcx
0x14000d527  cmp     [r8+rcx*2], r11w
0x14000d52c  jnz     short loc_14000D524
0x14000d52e  lea     ecx, ds:2[rcx*2]
0x14000d535  jmp     short loc_14000D539
0x14000d537  mov     ecx, ebx
0x14000d539  test    r8, r8
0x14000d53c  mov     [rbp+1Fh+var_98], ecx
0x14000d53f  lea     rdi, aNull; "NULL"
0x14000d546  mov     [rbp+1Fh+var_94], r11d
0x14000d54a  cmovz   r8, rdi
0x14000d54e  mov     [rsp+0E0h+var_A0], r8
0x14000d553  test    r9, r9
0x14000d556  jz      short loc_14000D56E
0x14000d558  mov     rcx, rax
0x14000d55b  inc     rcx
0x14000d55e  cmp     [r9+rcx*2], r11w
0x14000d563  jnz     short loc_14000D55B
0x14000d565  lea     ecx, ds:2[rcx*2]
0x14000d56c  jmp     short loc_14000D570
0x14000d56e  mov     ecx, ebx
0x14000d570  test    r9, r9
0x14000d573  mov     [rbp+1Fh+var_88], ecx
0x14000d576  mov     rcx, [rbp+1Fh+arg_20]
0x14000d57a  cmovz   r9, rdi
0x14000d57e  mov     [rbp+1Fh+var_84], r11d
0x14000d582  mov     [rbp+1Fh+var_90], r9
0x14000d586  test    rcx, rcx
0x14000d589  jz      short loc_14000D5A1
0x14000d58b  mov     rdx, rax
0x14000d58e  inc     rdx
0x14000d591  cmp     [rcx+rdx*2], r11w
0x14000d596  jnz     short loc_14000D58E
0x14000d598  lea     edx, ds:2[rdx*2]
0x14000d59f  jmp     short loc_14000D5A3
0x14000d5a1  mov     edx, ebx
0x14000d5a3  test    rcx, rcx
0x14000d5a6  mov     [rbp+1Fh+var_78], edx
0x14000d5a9  mov     [rbp+1Fh+var_74], r11d
0x14000d5ad  cmovz   rcx, rdi
0x14000d5b1  mov     [rbp+1Fh+var_80], rcx
0x14000d5b5  mov     rcx, [rbp+1Fh+arg_28]
0x14000d5b9  test    rcx, rcx
0x14000d5bc  jz      short loc_14000D5D1
0x14000d5be  inc     rax
0x14000d5c1  cmp     [rcx+rax*2], r11w
0x14000d5c6  jnz     short loc_14000D5BE
0x14000d5c8  lea     eax, ds:2[rax*2]
0x14000d5cf  jmp     short loc_14000D5D3
0x14000d5d1  mov     eax, ebx
0x14000d5d3  mov     [rbp+1Fh+var_68], eax
0x14000d5d6  test    rcx, rcx
0x14000d5d9  lea     rax, [rbp+1Fh+arg_30]
0x14000d5dd  mov     [rbp+1Fh+var_64], r11d
0x14000d5e1  mov     [rbp+1Fh+var_60], rax
0x14000d5e5  cmovz   rcx, rdi
0x14000d5e9  lea     rax, [rbp+1Fh+arg_38]
0x14000d5ed  mov     [rbp+1Fh+var_70], rcx
0x14000d5f1  mov     [rbp+1Fh+var_50], rax
0x14000d5f5  mov     r9d, ebx
0x14000d5f8  lea     rax, [rbp+1Fh+arg_40]
0x14000d5fc  mov     [rbp+1Fh+var_58], 4
0x14000d604  mov     [rbp+1Fh+var_40], rax
0x14000d608  mov     rdx, r10
0x14000d60b  lea     rax, [rbp+1Fh+arg_48]
0x14000d60f  mov     [rbp+1Fh+var_48], 4
0x14000d617  mov     [rbp+1Fh+var_30], rax
0x14000d61b  lea     rax, [rbp+1Fh+arg_50]
0x14000d61f  mov     [rbp+1Fh+var_20], rax
0x14000d623  lea     rax, [rsp+0E0h+var_B0]
0x14000d628  mov     [rsp+0E0h+var_C0], rax
0x14000d62d  mov     [rbp+1Fh+var_38], 4
0x14000d635  mov     [rbp+1Fh+var_28], 4
0x14000d63d  mov     [rbp+1Fh+var_18], 4
0x14000d645  call    McGenEventWrite_EventWriteTransfer
0x14000d64a  mov     rcx, [rbp+1Fh+var_10]
0x14000d64e  xor     rcx, rsp; StackCookie
0x14000d651  call    __security_check_cookie
0x14000d656  lea     r11, [rsp+0E0h+var_s0]
0x14000d65e  mov     rbx, [r11+10h]
0x14000d662  mov     rdi, [r11+20h]
0x14000d666  mov     rsp, r11
0x14000d669  pop     rbp
0x14000d66a  retn
```
