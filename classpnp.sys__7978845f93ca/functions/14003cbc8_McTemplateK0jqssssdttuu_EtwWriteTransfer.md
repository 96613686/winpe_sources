# McTemplateK0jqssssdttuu_EtwWriteTransfer

- ea: `0x14003cbc8`
- end: `0x14003cd52`
- name: `McTemplateK0jqssssdttuu_EtwWriteTransfer`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003b8c8`

## callees

- `0x1400062a0`
- `0x14003cbc8`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqssssdttuu_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
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
  if ( v27 )
    v26 = "NULL";
  v44 = v17;
  v45 = 0;
  v46 = &a10;
  v43 = v26;
  v48 = &a11;
  v47 = 4;
  v50 = &a12;
  v49 = 4;
  v52 = &a13;
  v54 = &a14;
  v51 = 4;
  v53 = 1;
  v55 = 1;
  return McGenEventWrite_EtwWriteTransfer((__int64)v26, a2, 0, 0xCu, &v29);
}

```

## disassembly

```asm
0x14003cbc8  push    rbp
0x14003cbca  lea     rbp, [rsp-7]
0x14003cbcf  sub     rsp, 100h
0x14003cbd6  mov     rax, cs:__security_cookie
0x14003cbdd  xor     rax, rsp
0x14003cbe0  mov     [rbp+7+var_10], rax
0x14003cbe4  mov     rcx, [rbp+7+arg_28]
0x14003cbe8  lea     rax, [rbp+7+arg_20]
0x14003cbec  mov     [rsp+100h+var_C0], r9
0x14003cbf1  mov     r10, rdx
0x14003cbf4  xor     r9d, r9d
0x14003cbf7  mov     [rsp+100h+var_B0], rax
0x14003cbfc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003cc00  mov     [rsp+100h+var_B8], 10h
0x14003cc09  mov     [rsp+100h+var_A8], 4
0x14003cc12  lea     r8d, [r9+5]
0x14003cc16  test    rcx, rcx
0x14003cc19  jz      short loc_14003CC2B
0x14003cc1b  mov     rdx, rax
0x14003cc1e  inc     rdx
0x14003cc21  cmp     [rcx+rdx], r9b
0x14003cc25  jnz     short loc_14003CC1E
0x14003cc27  inc     edx
0x14003cc29  jmp     short loc_14003CC2E
0x14003cc2b  mov     edx, r8d
0x14003cc2e  test    rcx, rcx
0x14003cc31  mov     [rsp+100h+var_98], edx
0x14003cc35  lea     r11, aNull; "NULL"
0x14003cc3c  mov     [rsp+100h+var_94], r9d
0x14003cc41  cmovz   rcx, r11
0x14003cc45  mov     [rsp+100h+var_A0], rcx
0x14003cc4a  mov     rcx, [rbp+7+arg_30]
0x14003cc4e  test    rcx, rcx
0x14003cc51  jz      short loc_14003CC63
0x14003cc53  mov     rdx, rax
0x14003cc56  inc     rdx
0x14003cc59  cmp     [rcx+rdx], r9b
0x14003cc5d  jnz     short loc_14003CC56
0x14003cc5f  inc     edx
0x14003cc61  jmp     short loc_14003CC66
0x14003cc63  mov     edx, r8d
0x14003cc66  test    rcx, rcx
0x14003cc69  mov     [rsp+100h+var_88], edx
0x14003cc6d  mov     [rbp+7+var_84], r9d
0x14003cc71  cmovz   rcx, r11
0x14003cc75  mov     [rsp+100h+var_90], rcx
0x14003cc7a  mov     rcx, [rbp+7+arg_38]
0x14003cc7e  test    rcx, rcx
0x14003cc81  jz      short loc_14003CC93
0x14003cc83  mov     rdx, rax
0x14003cc86  inc     rdx
0x14003cc89  cmp     [rcx+rdx], r9b
0x14003cc8d  jnz     short loc_14003CC86
0x14003cc8f  inc     edx
0x14003cc91  jmp     short loc_14003CC96
0x14003cc93  mov     edx, r8d
0x14003cc96  test    rcx, rcx
0x14003cc99  mov     [rbp+7+var_78], edx
0x14003cc9c  mov     [rbp+7+var_74], r9d
0x14003cca0  cmovz   rcx, r11
0x14003cca4  mov     [rbp+7+var_80], rcx
0x14003cca8  mov     rcx, [rbp+7+arg_40]
0x14003ccac  test    rcx, rcx
0x14003ccaf  jz      short loc_14003CCC1
0x14003ccb1  inc     rax
0x14003ccb4  cmp     [rcx+rax], r9b
0x14003ccb8  jnz     short loc_14003CCB1
0x14003ccba  lea     r8d, [rax+1]
0x14003ccbe  test    rcx, rcx
0x14003ccc1  cmovz   rcx, r11
0x14003ccc5  mov     [rbp+7+var_68], r8d
0x14003ccc9  lea     rax, [rbp+7+arg_48]
0x14003cccd  mov     [rbp+7+var_64], r9d
0x14003ccd1  mov     [rbp+7+var_60], rax
0x14003ccd5  mov     r9d, 0Ch
0x14003ccdb  lea     rax, [rbp+7+arg_50]
0x14003ccdf  mov     [rbp+7+var_70], rcx
0x14003cce3  mov     [rbp+7+var_50], rax
0x14003cce7  xor     r8d, r8d
0x14003ccea  lea     rax, [rbp+7+arg_58]
0x14003ccee  mov     [rbp+7+var_58], 4
0x14003ccf6  mov     [rbp+7+var_40], rax
0x14003ccfa  mov     rdx, r10
0x14003ccfd  lea     rax, [rbp+7+arg_60]
0x14003cd01  mov     [rbp+7+var_48], 4
0x14003cd09  mov     [rbp+7+var_30], rax
0x14003cd0d  lea     rax, [rbp+7+arg_68]
0x14003cd11  mov     [rbp+7+var_20], rax
0x14003cd15  lea     rax, [rsp+100h+var_D0]
0x14003cd1a  mov     [rsp+100h+var_E0], rax
0x14003cd1f  mov     [rbp+7+var_38], 4
0x14003cd27  mov     [rbp+7+var_28], 1
0x14003cd2f  mov     [rbp+7+var_18], 1
0x14003cd37  call    McGenEventWrite_EtwWriteTransfer
0x14003cd3c  mov     rcx, [rbp+7+var_10]
0x14003cd40  xor     rcx, rsp; StackCookie
0x14003cd43  call    __security_check_cookie
0x14003cd48  add     rsp, 100h
0x14003cd4f  pop     rbp
0x14003cd50  retn
```
