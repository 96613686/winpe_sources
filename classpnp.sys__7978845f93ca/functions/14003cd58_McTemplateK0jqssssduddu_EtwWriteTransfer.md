# McTemplateK0jqssssduddu_EtwWriteTransfer

- ea: `0x14003cd58`
- end: `0x14003cee6`
- name: `McTemplateK0jqssssduddu_EtwWriteTransfer`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003bf7c`

## callees

- `0x1400062a0`
- `0x14003cd58`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqssssduddu_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        __int64 a4,
        char a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14)
{
  const char *v14; // rcx
  __int64 v16; // rax
  int v17; // r8d
  __int64 v18; // rdx
  int v19; // edx
  const char *v20; // rcx
  __int64 v21; // rdx
  int v22; // edx
  const char *v23; // rcx
  __int64 v24; // rdx
  int v25; // edx
  const char *v26; // rcx
  bool v27; // zf
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v30; // [rsp+40h] [rbp-B9h]
  __int64 v31; // [rsp+48h] [rbp-B1h]
  char *v32; // [rsp+50h] [rbp-A9h]
  __int64 v33; // [rsp+58h] [rbp-A1h]
  const char *v34; // [rsp+60h] [rbp-99h]
  int v35; // [rsp+68h] [rbp-91h]
  int v36; // [rsp+6Ch] [rbp-8Dh]
  const char *v37; // [rsp+70h] [rbp-89h]
  int v38; // [rsp+78h] [rbp-81h]
  int v39; // [rsp+7Ch] [rbp-7Dh]
  const char *v40; // [rsp+80h] [rbp-79h]
  int v41; // [rsp+88h] [rbp-71h]
  int v42; // [rsp+8Ch] [rbp-6Dh]
  const char *v43; // [rsp+90h] [rbp-69h]
  int v44; // [rsp+98h] [rbp-61h]
  int v45; // [rsp+9Ch] [rbp-5Dh]
  char *v46; // [rsp+A0h] [rbp-59h]
  __int64 v47; // [rsp+A8h] [rbp-51h]
  char *v48; // [rsp+B0h] [rbp-49h]
  __int64 v49; // [rsp+B8h] [rbp-41h]
  char *v50; // [rsp+C0h] [rbp-39h]
  __int64 v51; // [rsp+C8h] [rbp-31h]
  char *v52; // [rsp+D0h] [rbp-29h]
  __int64 v53; // [rsp+D8h] [rbp-21h]
  char *v54; // [rsp+E0h] [rbp-19h]
  __int64 v55; // [rsp+E8h] [rbp-11h]

  v14 = a6;
  v30 = a4;
  v32 = &a5;
  v16 = -1;
  v31 = 16;
  v33 = 4;
  v17 = 5;
  if ( a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a6[v18] );
    v19 = v18 + 1;
  }
  else
  {
    v19 = 5;
  }
  v35 = v19;
  v36 = 0;
  if ( !a6 )
    v14 = "NULL";
  v34 = v14;
  v20 = a7;
  if ( a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a7[v21] );
    v22 = v21 + 1;
  }
  else
  {
    v22 = 5;
  }
  v38 = v22;
  v39 = 0;
  if ( !a7 )
    v20 = "NULL";
  v37 = v20;
  v23 = a8;
  if ( a8 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a8[v24] );
    v25 = v24 + 1;
  }
  else
  {
    v25 = 5;
  }
  v41 = v25;
  v42 = 0;
  if ( !a8 )
    v23 = "NULL";
  v40 = v23;
  v26 = a9;
  v27 = a9 == 0;
  if ( a9 )
  {
    do
      ++v16;
    while ( a9[v16] );
    v17 = v16 + 1;
    v27 = a9 == 0;
  }
  v44 = v17;
  v46 = &a10;
  v45 = 0;
  v48 = &a11;
  if ( v27 )
    v26 = "NULL";
  v43 = v26;
  v50 = &a12;
  v47 = 4;
  v52 = &a13;
  v49 = 1;
  v54 = &a14;
  v51 = 4;
  v53 = 4;
  v55 = 1;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)v26,
           (const EVENT_DESCRIPTOR *)EventSrbNonScsiRequestFailure,
           a3,
           0xCu,
           &v29);
}

```

## disassembly

```asm
0x14003cd58  push    rbp
0x14003cd5a  lea     rbp, [rsp-7]
0x14003cd5f  sub     rsp, 100h
0x14003cd66  mov     rax, cs:__security_cookie
0x14003cd6d  xor     rax, rsp
0x14003cd70  mov     [rbp+7+var_10], rax
0x14003cd74  mov     rcx, [rbp+7+arg_28]
0x14003cd78  lea     rax, [rbp+7+arg_20]
0x14003cd7c  mov     [rsp+100h+var_C0], r9
0x14003cd81  mov     r10, r8
0x14003cd84  xor     r9d, r9d
0x14003cd87  mov     [rsp+100h+var_B0], rax
0x14003cd8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003cd90  mov     [rsp+100h+var_B8], 10h
0x14003cd99  mov     [rsp+100h+var_A8], 4
0x14003cda2  lea     r8d, [r9+5]
0x14003cda6  test    rcx, rcx
0x14003cda9  jz      short loc_14003CDBB
0x14003cdab  mov     rdx, rax
0x14003cdae  inc     rdx
0x14003cdb1  cmp     [rcx+rdx], r9b
0x14003cdb5  jnz     short loc_14003CDAE
0x14003cdb7  inc     edx
0x14003cdb9  jmp     short loc_14003CDBE
0x14003cdbb  mov     edx, r8d
0x14003cdbe  test    rcx, rcx
0x14003cdc1  mov     [rsp+100h+var_98], edx
0x14003cdc5  lea     r11, aNull; "NULL"
0x14003cdcc  mov     [rsp+100h+var_94], r9d
0x14003cdd1  cmovz   rcx, r11
0x14003cdd5  mov     [rsp+100h+var_A0], rcx
0x14003cdda  mov     rcx, [rbp+7+arg_30]
0x14003cdde  test    rcx, rcx
0x14003cde1  jz      short loc_14003CDF3
0x14003cde3  mov     rdx, rax
0x14003cde6  inc     rdx
0x14003cde9  cmp     [rcx+rdx], r9b
0x14003cded  jnz     short loc_14003CDE6
0x14003cdef  inc     edx
0x14003cdf1  jmp     short loc_14003CDF6
0x14003cdf3  mov     edx, r8d
0x14003cdf6  test    rcx, rcx
0x14003cdf9  mov     [rsp+100h+var_88], edx
0x14003cdfd  mov     [rbp+7+var_84], r9d
0x14003ce01  cmovz   rcx, r11
0x14003ce05  mov     [rsp+100h+var_90], rcx
0x14003ce0a  mov     rcx, [rbp+7+arg_38]
0x14003ce0e  test    rcx, rcx
0x14003ce11  jz      short loc_14003CE23
0x14003ce13  mov     rdx, rax
0x14003ce16  inc     rdx
0x14003ce19  cmp     [rcx+rdx], r9b
0x14003ce1d  jnz     short loc_14003CE16
0x14003ce1f  inc     edx
0x14003ce21  jmp     short loc_14003CE26
0x14003ce23  mov     edx, r8d
0x14003ce26  test    rcx, rcx
0x14003ce29  mov     [rbp+7+var_78], edx
0x14003ce2c  mov     [rbp+7+var_74], r9d
0x14003ce30  cmovz   rcx, r11
0x14003ce34  mov     [rbp+7+var_80], rcx
0x14003ce38  mov     rcx, [rbp+7+arg_40]
0x14003ce3c  test    rcx, rcx
0x14003ce3f  jz      short loc_14003CE51
0x14003ce41  inc     rax
0x14003ce44  cmp     [rcx+rax], r9b
0x14003ce48  jnz     short loc_14003CE41
0x14003ce4a  lea     r8d, [rax+1]
0x14003ce4e  test    rcx, rcx
0x14003ce51  lea     rax, [rbp+7+arg_48]
0x14003ce55  mov     [rbp+7+var_68], r8d
0x14003ce59  mov     [rbp+7+var_60], rax
0x14003ce5d  lea     rdx, EventSrbNonScsiRequestFailure
0x14003ce64  lea     rax, [rbp+7+arg_50]
0x14003ce68  mov     [rbp+7+var_64], r9d
0x14003ce6c  mov     [rbp+7+var_50], rax
0x14003ce70  cmovz   rcx, r11
0x14003ce74  lea     rax, [rbp+7+arg_58]
0x14003ce78  mov     [rbp+7+var_70], rcx
0x14003ce7c  mov     [rbp+7+var_40], rax
0x14003ce80  mov     r9d, 0Ch
0x14003ce86  lea     rax, [rbp+7+arg_60]
0x14003ce8a  mov     [rbp+7+var_58], 4
0x14003ce92  mov     [rbp+7+var_30], rax
0x14003ce96  mov     r8, r10
0x14003ce99  lea     rax, [rbp+7+arg_68]
0x14003ce9d  mov     [rbp+7+var_48], 1
0x14003cea5  mov     [rbp+7+var_20], rax
0x14003cea9  lea     rax, [rsp+100h+var_D0]
0x14003ceae  mov     [rsp+100h+var_E0], rax
0x14003ceb3  mov     [rbp+7+var_38], 4
0x14003cebb  mov     [rbp+7+var_28], 4
0x14003cec3  mov     [rbp+7+var_18], 1
0x14003cecb  call    McGenEventWrite_EtwWriteTransfer
0x14003ced0  mov     rcx, [rbp+7+var_10]
0x14003ced4  xor     rcx, rsp; StackCookie
0x14003ced7  call    __security_check_cookie
0x14003cedc  add     rsp, 100h
0x14003cee3  pop     rbp
0x14003cee4  retn
```
