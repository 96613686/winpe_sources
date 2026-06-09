# McTemplateK0jqssssdixuq_EtwWriteTransfer

- ea: `0x140004ed0`
- end: `0x140005093`
- name: `McTemplateK0jqssssdixuq_EtwWriteTransfer`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006300`

## callees

- `0x140004ed0`
- `0x1400062a0`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqssssdixuq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
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
  const char *v15; // rdx
  __int64 v17; // rax
  int v18; // r8d
  __int64 v19; // rcx
  int v20; // ecx
  const char *v21; // rdx
  __int64 v22; // rcx
  int v23; // ecx
  const char *v24; // rdx
  __int64 v25; // rcx
  int v26; // ecx
  const char *v27; // rcx
  bool v28; // zf
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v31; // [rsp+40h] [rbp-B9h]
  __int64 v32; // [rsp+48h] [rbp-B1h]
  char *v33; // [rsp+50h] [rbp-A9h]
  __int64 v34; // [rsp+58h] [rbp-A1h]
  const char *v35; // [rsp+60h] [rbp-99h]
  int v36; // [rsp+68h] [rbp-91h]
  int v37; // [rsp+6Ch] [rbp-8Dh]
  const char *v38; // [rsp+70h] [rbp-89h]
  int v39; // [rsp+78h] [rbp-81h]
  int v40; // [rsp+7Ch] [rbp-7Dh]
  const char *v41; // [rsp+80h] [rbp-79h]
  int v42; // [rsp+88h] [rbp-71h]
  int v43; // [rsp+8Ch] [rbp-6Dh]
  const char *v44; // [rsp+90h] [rbp-69h]
  int v45; // [rsp+98h] [rbp-61h]
  int v46; // [rsp+9Ch] [rbp-5Dh]
  char *v47; // [rsp+A0h] [rbp-59h]
  __int64 v48; // [rsp+A8h] [rbp-51h]
  char *v49; // [rsp+B0h] [rbp-49h]
  __int64 v50; // [rsp+B8h] [rbp-41h]
  char *v51; // [rsp+C0h] [rbp-39h]
  __int64 v52; // [rsp+C8h] [rbp-31h]
  char *v53; // [rsp+D0h] [rbp-29h]
  __int64 v54; // [rsp+D8h] [rbp-21h]
  char *v55; // [rsp+E0h] [rbp-19h]
  __int64 v56; // [rsp+E8h] [rbp-11h]

  v31 = a4;
  v33 = &a5;
  v15 = a6;
  v32 = 16;
  v34 = 4;
  v17 = -1;
  v18 = 5;
  if ( a6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a6[v19] );
    v20 = v19 + 1;
  }
  else
  {
    v20 = 5;
  }
  v36 = v20;
  v37 = 0;
  if ( !a6 )
    v15 = "NULL";
  v35 = v15;
  v21 = a7;
  if ( a7 )
  {
    v22 = -1;
    do
      ++v22;
    while ( a7[v22] );
    v23 = v22 + 1;
  }
  else
  {
    v23 = 5;
  }
  v39 = v23;
  v40 = 0;
  if ( !a7 )
    v21 = "NULL";
  v38 = v21;
  v24 = a8;
  if ( a8 )
  {
    v25 = -1;
    do
      ++v25;
    while ( a8[v25] );
    v26 = v25 + 1;
  }
  else
  {
    v26 = 5;
  }
  v42 = v26;
  v27 = a9;
  if ( !a8 )
    v24 = "NULL";
  v43 = 0;
  v41 = v24;
  v28 = a9 == 0;
  if ( a9 )
  {
    do
      v28 = a9[++v17] == 0;
    while ( !v28 );
    v18 = v17 + 1;
    v28 = a9 == 0;
  }
  v45 = v18;
  v47 = &a10;
  if ( v28 )
    v27 = "NULL";
  v46 = 0;
  v49 = &a11;
  v44 = v27;
  v51 = &a12;
  v48 = 4;
  v53 = &a13;
  v50 = 8;
  v55 = &a14;
  v52 = 8;
  v54 = 1;
  v56 = 4;
  return McGenEventWrite_EtwWriteTransfer((__int64)v27, a2, a3, 0xCu, &v30);
}

```

## disassembly

```asm
0x140004ed0  mov     [rsp-8+arg_0], rbx
0x140004ed5  push    rbp
0x140004ed6  lea     rbp, [rsp-7]
0x140004edb  sub     rsp, 100h
0x140004ee2  mov     rax, cs:__security_cookie
0x140004ee9  xor     rax, rsp
0x140004eec  mov     [rbp+7+var_10], rax
0x140004ef0  lea     rax, [rbp+7+arg_20]
0x140004ef4  mov     [rsp+100h+var_C0], r9
0x140004ef9  mov     r10, rdx
0x140004efc  mov     [rsp+100h+var_B0], rax
0x140004f01  mov     rdx, [rbp+7+arg_28]
0x140004f05  xor     r9d, r9d
0x140004f08  mov     [rsp+100h+var_B8], 10h
0x140004f11  mov     r11, r8
0x140004f14  mov     [rsp+100h+var_A8], 4
0x140004f1d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004f24  mov     r8d, 5
0x140004f2a  test    rdx, rdx
0x140004f2d  jz      loc_140005083
0x140004f33  mov     rcx, rax
0x140004f36  inc     rcx
0x140004f39  cmp     [rdx+rcx], r9b
0x140004f3d  jnz     short loc_140004F36
0x140004f3f  inc     ecx
0x140004f41  test    rdx, rdx
0x140004f44  mov     [rsp+100h+var_98], ecx
0x140004f48  lea     rbx, aNull; "NULL"
0x140004f4f  mov     [rsp+100h+var_94], r9d
0x140004f54  cmovz   rdx, rbx
0x140004f58  mov     [rsp+100h+var_A0], rdx
0x140004f5d  mov     rdx, [rbp+7+arg_30]
0x140004f61  test    rdx, rdx
0x140004f64  jz      loc_14000508B
0x140004f6a  mov     rcx, rax
0x140004f6d  nop     dword ptr [rax]
0x140004f70  inc     rcx
0x140004f73  cmp     [rdx+rcx], r9b
0x140004f77  jnz     short loc_140004F70
0x140004f79  inc     ecx
0x140004f7b  test    rdx, rdx
0x140004f7e  mov     [rsp+100h+var_88], ecx
0x140004f82  mov     [rbp+7+var_84], r9d
0x140004f86  cmovz   rdx, rbx
0x140004f8a  mov     [rsp+100h+var_90], rdx
0x140004f8f  mov     rdx, [rbp+7+arg_38]
0x140004f93  test    rdx, rdx
0x140004f96  jz      loc_14000507B
0x140004f9c  mov     rcx, rax
0x140004f9f  nop
0x140004fa0  inc     rcx
0x140004fa3  cmp     [rdx+rcx], r9b
0x140004fa7  jnz     short loc_140004FA0
0x140004fa9  inc     ecx
0x140004fab  test    rdx, rdx
0x140004fae  mov     [rbp+7+var_78], ecx
0x140004fb1  mov     rcx, [rbp+7+arg_40]
0x140004fb5  cmovz   rdx, rbx
0x140004fb9  mov     [rbp+7+var_74], r9d
0x140004fbd  mov     [rbp+7+var_80], rdx
0x140004fc1  test    rcx, rcx
0x140004fc4  jz      short loc_140004FE2
0x140004fc6  nop     word ptr [rax+rax+00000000h]
0x140004fd0  cmp     [rcx+rax+1], r9b
0x140004fd5  lea     rax, [rax+1]
0x140004fd9  jnz     short loc_140004FD0
0x140004fdb  lea     r8d, [rax+1]
0x140004fdf  test    rcx, rcx
0x140004fe2  lea     rax, [rbp+7+arg_48]
0x140004fe6  mov     [rbp+7+var_68], r8d
0x140004fea  mov     [rbp+7+var_60], rax
0x140004fee  cmovz   rcx, rbx
0x140004ff2  lea     rax, [rbp+7+arg_50]
0x140004ff6  mov     [rbp+7+var_64], r9d
0x140004ffa  mov     [rbp+7+var_50], rax
0x140004ffe  mov     r9d, 0Ch
0x140005004  lea     rax, [rbp+7+arg_58]
0x140005008  mov     [rbp+7+var_70], rcx
0x14000500c  mov     [rbp+7+var_40], rax
0x140005010  mov     r8, r11
0x140005013  lea     rax, [rbp+7+arg_60]
0x140005017  mov     [rbp+7+var_58], 4
0x14000501f  mov     [rbp+7+var_30], rax
0x140005023  mov     rdx, r10
0x140005026  lea     rax, [rbp+7+arg_68]
0x14000502a  mov     [rbp+7+var_48], 8
0x140005032  mov     [rbp+7+var_20], rax
0x140005036  lea     rax, [rsp+100h+var_D0]
0x14000503b  mov     [rsp+100h+var_E0], rax
0x140005040  mov     [rbp+7+var_38], 8
0x140005048  mov     [rbp+7+var_28], 1
0x140005050  mov     [rbp+7+var_18], 4
0x140005058  call    McGenEventWrite_EtwWriteTransfer
0x14000505d  mov     rcx, [rbp+7+var_10]
0x140005061  xor     rcx, rsp; StackCookie
0x140005064  call    __security_check_cookie
0x140005069  mov     rbx, [rsp+100h+arg_0]
0x140005071  add     rsp, 100h
0x140005078  pop     rbp
0x140005079  retn
0x14000507b  mov     ecx, r8d
0x14000507e  jmp     loc_140004FAB
0x140005083  mov     ecx, r8d
0x140005086  jmp     loc_140004F41
0x14000508b  mov     ecx, r8d
0x14000508e  jmp     loc_140004F7B
```
