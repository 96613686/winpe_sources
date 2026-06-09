# McTemplateK0jqsssstqqd_EtwWriteTransfer

- ea: `0x140007230`
- end: `0x1400073cb`
- name: `McTemplateK0jqsssstqqd_EtwWriteTransfer`
- size: `411`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400074b8`
- `0x140019ce4`

## callees

- `0x1400062a0`
- `0x140007230`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqsssstqqd_EtwWriteTransfer(
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
        char a13)
{
  const char *v14; // rdx
  __int64 v15; // rax
  int v16; // r8d
  __int64 v17; // rcx
  int v18; // ecx
  const char *v19; // rdx
  __int64 v20; // rcx
  int v21; // ecx
  const char *v22; // rdx
  __int64 v23; // rcx
  int v24; // ecx
  const char *v25; // rcx
  bool v26; // zf
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v29; // [rsp+40h] [rbp-A1h]
  __int64 v30; // [rsp+48h] [rbp-99h]
  char *v31; // [rsp+50h] [rbp-91h]
  __int64 v32; // [rsp+58h] [rbp-89h]
  const char *v33; // [rsp+60h] [rbp-81h]
  int v34; // [rsp+68h] [rbp-79h]
  int v35; // [rsp+6Ch] [rbp-75h]
  const char *v36; // [rsp+70h] [rbp-71h]
  int v37; // [rsp+78h] [rbp-69h]
  int v38; // [rsp+7Ch] [rbp-65h]
  const char *v39; // [rsp+80h] [rbp-61h]
  int v40; // [rsp+88h] [rbp-59h]
  int v41; // [rsp+8Ch] [rbp-55h]
  const char *v42; // [rsp+90h] [rbp-51h]
  int v43; // [rsp+98h] [rbp-49h]
  int v44; // [rsp+9Ch] [rbp-45h]
  char *v45; // [rsp+A0h] [rbp-41h]
  __int64 v46; // [rsp+A8h] [rbp-39h]
  char *v47; // [rsp+B0h] [rbp-31h]
  __int64 v48; // [rsp+B8h] [rbp-29h]
  char *v49; // [rsp+C0h] [rbp-21h]
  __int64 v50; // [rsp+C8h] [rbp-19h]
  char *v51; // [rsp+D0h] [rbp-11h]
  __int64 v52; // [rsp+D8h] [rbp-9h]

  v29 = a4;
  v31 = &a5;
  v14 = a6;
  v30 = 16;
  v15 = -1;
  v32 = 4;
  v16 = 5;
  if ( a6 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a6[v17] );
    v18 = v17 + 1;
  }
  else
  {
    v18 = 5;
  }
  v34 = v18;
  v35 = 0;
  if ( !a6 )
    v14 = "NULL";
  v33 = v14;
  v19 = a7;
  if ( a7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( a7[v20] );
    v21 = v20 + 1;
  }
  else
  {
    v21 = 5;
  }
  v37 = v21;
  v38 = 0;
  if ( !a7 )
    v19 = "NULL";
  v36 = v19;
  v22 = a8;
  if ( a8 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a8[v23] );
    v24 = v23 + 1;
  }
  else
  {
    v24 = 5;
  }
  v40 = v24;
  v25 = a9;
  if ( !a8 )
    v22 = "NULL";
  v41 = 0;
  v39 = v22;
  v26 = a9 == 0;
  if ( a9 )
  {
    do
      v26 = a9[++v15] == 0;
    while ( !v26 );
    v16 = v15 + 1;
    v26 = a9 == 0;
  }
  if ( v26 )
    v25 = "NULL";
  v43 = v16;
  v44 = 0;
  v45 = &a10;
  v42 = v25;
  v47 = &a11;
  v46 = 4;
  v49 = &a12;
  v48 = 4;
  v51 = &a13;
  v50 = 4;
  v52 = 4;
  return McGenEventWrite_EtwWriteTransfer((__int64)v25, a2, 0, 0xBu, &v28);
}

```

## disassembly

```asm
0x140007230  push    rbp
0x140007232  lea     rbp, [rsp-0Fh]
0x140007237  sub     rsp, 0F0h
0x14000723e  mov     rax, cs:__security_cookie
0x140007245  xor     rax, rsp
0x140007248  mov     [rbp+0Fh+var_10], rax
0x14000724c  lea     rax, [rbp+0Fh+arg_20]
0x140007250  mov     [rsp+0F0h+var_B0], r9
0x140007255  mov     r10, rdx
0x140007258  mov     [rsp+0F0h+var_A0], rax
0x14000725d  mov     rdx, [rbp+0Fh+arg_28]
0x140007261  xor     r9d, r9d
0x140007264  mov     [rsp+0F0h+var_A8], 10h
0x14000726d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140007274  mov     [rsp+0F0h+var_98], 4
0x14000727d  mov     r8d, 5
0x140007283  test    rdx, rdx
0x140007286  jz      loc_1400073BB
0x14000728c  mov     rcx, rax
0x14000728f  nop
0x140007290  inc     rcx
0x140007293  cmp     [rdx+rcx], r9b
0x140007297  jnz     short loc_140007290
0x140007299  inc     ecx
0x14000729b  test    rdx, rdx
0x14000729e  mov     [rbp+0Fh+var_88], ecx
0x1400072a1  lea     r11, aNull; "NULL"
0x1400072a8  mov     [rbp+0Fh+var_84], r9d
0x1400072ac  cmovz   rdx, r11
0x1400072b0  mov     [rsp+0F0h+var_90], rdx
0x1400072b5  mov     rdx, [rbp+0Fh+arg_30]
0x1400072b9  test    rdx, rdx
0x1400072bc  jz      loc_1400073C3
0x1400072c2  mov     rcx, rax
0x1400072c5  inc     rcx
0x1400072c8  cmp     [rdx+rcx], r9b
0x1400072cc  jnz     short loc_1400072C5
0x1400072ce  inc     ecx
0x1400072d0  test    rdx, rdx
0x1400072d3  mov     [rbp+0Fh+var_78], ecx
0x1400072d6  mov     [rbp+0Fh+var_74], r9d
0x1400072da  cmovz   rdx, r11
0x1400072de  mov     [rbp+0Fh+var_80], rdx
0x1400072e2  mov     rdx, [rbp+0Fh+arg_38]
0x1400072e6  test    rdx, rdx
0x1400072e9  jz      loc_1400073B3
0x1400072ef  mov     rcx, rax
0x1400072f2  inc     rcx
0x1400072f5  cmp     [rdx+rcx], r9b
0x1400072f9  jnz     short loc_1400072F2
0x1400072fb  inc     ecx
0x1400072fd  test    rdx, rdx
0x140007300  mov     [rbp+0Fh+var_68], ecx
0x140007303  mov     rcx, [rbp+0Fh+arg_40]
0x140007307  cmovz   rdx, r11
0x14000730b  mov     [rbp+0Fh+var_64], r9d
0x14000730f  mov     [rbp+0Fh+var_70], rdx
0x140007313  test    rcx, rcx
0x140007316  jz      short loc_140007332
0x140007318  nop     dword ptr [rax+rax+00000000h]
0x140007320  cmp     [rcx+rax+1], r9b
0x140007325  lea     rax, [rax+1]
0x140007329  jnz     short loc_140007320
0x14000732b  lea     r8d, [rax+1]
0x14000732f  test    rcx, rcx
0x140007332  cmovz   rcx, r11
0x140007336  mov     [rbp+0Fh+var_58], r8d
0x14000733a  lea     rax, [rbp+0Fh+arg_48]
0x14000733e  mov     [rbp+0Fh+var_54], r9d
0x140007342  mov     [rbp+0Fh+var_50], rax
0x140007346  mov     r9d, 0Bh
0x14000734c  lea     rax, [rbp+0Fh+arg_50]
0x140007350  mov     [rbp+0Fh+var_60], rcx
0x140007354  mov     [rbp+0Fh+var_40], rax
0x140007358  xor     r8d, r8d
0x14000735b  lea     rax, [rbp+0Fh+arg_58]
0x14000735f  mov     [rbp+0Fh+var_48], 4
0x140007367  mov     [rbp+0Fh+var_30], rax
0x14000736b  mov     rdx, r10
0x14000736e  lea     rax, [rbp+0Fh+arg_60]
0x140007372  mov     [rbp+0Fh+var_38], 4
0x14000737a  mov     [rbp+0Fh+var_20], rax
0x14000737e  lea     rax, [rsp+0F0h+var_C0]
0x140007383  mov     [rsp+0F0h+var_D0], rax
0x140007388  mov     [rbp+0Fh+var_28], 4
0x140007390  mov     [rbp+0Fh+var_18], 4
0x140007398  call    McGenEventWrite_EtwWriteTransfer
0x14000739d  mov     rcx, [rbp+0Fh+var_10]
0x1400073a1  xor     rcx, rsp; StackCookie
0x1400073a4  call    __security_check_cookie
0x1400073a9  add     rsp, 0F0h
0x1400073b0  pop     rbp
0x1400073b1  retn
0x1400073b3  mov     ecx, r8d
0x1400073b6  jmp     loc_1400072FD
0x1400073bb  mov     ecx, r8d
0x1400073be  jmp     loc_14000729B
0x1400073c3  mov     ecx, r8d
0x1400073c6  jmp     loc_1400072D0
```
