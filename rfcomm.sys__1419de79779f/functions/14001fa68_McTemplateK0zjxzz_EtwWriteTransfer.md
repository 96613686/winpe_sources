# McTemplateK0zjxzz_EtwWriteTransfer

- ea: `0x14001fa68`
- end: `0x14001fb6e`
- name: `McTemplateK0zjxzz_EtwWriteTransfer`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a380`

## callees

- `0x14001fa00`
- `0x14001fa68`
- `0x14001fc30`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zjxzz_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        __int64 a5,
        char a6,
        const char *a7,
        const char *a8)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  const char *v15; // rax
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-39h] BYREF
  const char *v19; // [rsp+40h] [rbp-29h]
  int v20; // [rsp+48h] [rbp-21h]
  int v21; // [rsp+4Ch] [rbp-1Dh]
  __int64 v22; // [rsp+50h] [rbp-19h]
  __int64 v23; // [rsp+58h] [rbp-11h]
  char *v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  const char *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  const char *v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+88h] [rbp+1Fh]
  int v31; // [rsp+8Ch] [rbp+23h]

  v8 = -1;
  v9 = 10;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a4[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v20 = v11;
  v22 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = &a6;
  v12 = a7;
  v19 = a4;
  v21 = 0;
  v23 = 16;
  v25 = 8;
  if ( a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&a7[2 * v13] );
    v14 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v14 = 10;
  }
  v27 = v14;
  v28 = 0;
  if ( !a7 )
    v12 = L"NULL";
  v26 = v12;
  v15 = a8;
  v16 = a8 == 0;
  if ( a8 )
  {
    do
      ++v8;
    while ( *(_WORD *)&a8[2 * v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v16 = a8 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v30 = v9;
  v29 = v15;
  v31 = 0;
  return McGenEventWrite_EtwWriteTransfer(v8, v14, v9, (__int64)a4, &v18);
}

```

## disassembly

```asm
0x14001fa68  push    rbp
0x14001fa6a  lea     rbp, [rsp-37h]
0x14001fa6f  sub     rsp, 0A0h
0x14001fa76  mov     rax, cs:__security_cookie
0x14001fa7d  xor     rax, rsp
0x14001fa80  mov     [rbp+37h+var_10], rax
0x14001fa84  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001fa88  xor     r10d, r10d
0x14001fa8b  mov     r8d, 0Ah
0x14001fa91  test    r9, r9
0x14001fa94  jz      short loc_14001FAAC
0x14001fa96  mov     rax, rcx
0x14001fa99  inc     rax
0x14001fa9c  cmp     [r9+rax*2], r10w
0x14001faa1  jnz     short loc_14001FA99
0x14001faa3  lea     eax, ds:2[rax*2]
0x14001faaa  jmp     short loc_14001FAAF
0x14001faac  mov     eax, r8d
0x14001faaf  mov     [rbp+37h+var_58], eax
0x14001fab2  lea     r11, aNull_0; "NULL"
0x14001fab9  mov     rax, [rbp+37h+arg_20]
0x14001fabd  test    r9, r9
0x14001fac0  mov     [rbp+37h+var_50], rax
0x14001fac4  lea     rax, [rbp+37h+arg_28]
0x14001fac8  cmovz   r9, r11; int
0x14001facc  mov     [rbp+37h+var_40], rax
0x14001fad0  mov     rax, [rbp+37h+arg_30]
0x14001fad4  mov     [rbp+37h+var_60], r9
0x14001fad8  mov     [rbp+37h+var_54], r10d
0x14001fadc  mov     [rbp+37h+var_48], 10h
0x14001fae4  mov     [rbp+37h+var_38], 8
0x14001faec  test    rax, rax
0x14001faef  jz      short loc_14001FB07
0x14001faf1  mov     rdx, rcx
0x14001faf4  inc     rdx
0x14001faf7  cmp     [rax+rdx*2], r10w
0x14001fafc  jnz     short loc_14001FAF4
0x14001fafe  lea     edx, ds:2[rdx*2]
0x14001fb05  jmp     short loc_14001FB0A
0x14001fb07  mov     edx, r8d; int
0x14001fb0a  test    rax, rax
0x14001fb0d  mov     [rbp+37h+var_28], edx
0x14001fb10  mov     [rbp+37h+var_24], r10d
0x14001fb14  cmovz   rax, r11
0x14001fb18  mov     [rbp+37h+var_30], rax
0x14001fb1c  mov     rax, [rbp+37h+arg_38]
0x14001fb20  test    rax, rax
0x14001fb23  jz      short loc_14001FB3A
0x14001fb25  inc     rcx; int
0x14001fb28  cmp     [rax+rcx*2], r10w
0x14001fb2d  jnz     short loc_14001FB25
0x14001fb2f  lea     r8d, ds:2[rcx*2]; int
0x14001fb37  test    rax, rax
0x14001fb3a  cmovz   rax, r11
0x14001fb3e  mov     [rbp+37h+var_18], r8d
0x14001fb42  mov     [rbp+37h+var_20], rax
0x14001fb46  lea     rax, [rbp+37h+var_70]
0x14001fb4a  mov     [rsp+0A0h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x14001fb4f  mov     [rbp+37h+var_14], r10d
0x14001fb53  call    McGenEventWrite_EtwWriteTransfer
0x14001fb58  mov     rcx, [rbp+37h+var_10]
0x14001fb5c  xor     rcx, rsp; StackCookie
0x14001fb5f  call    __security_check_cookie
0x14001fb64  add     rsp, 0A0h
0x14001fb6b  pop     rbp
0x14001fb6c  retn
```
