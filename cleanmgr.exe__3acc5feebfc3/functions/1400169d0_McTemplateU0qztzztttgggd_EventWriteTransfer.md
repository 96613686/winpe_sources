# McTemplateU0qztzztttgggd_EventWriteTransfer

- ea: `0x1400169d0`
- end: `0x140016b79`
- name: `McTemplateU0qztzztttgggd_EventWriteTransfer`
- size: `425`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, const wchar_t *, const wchar_t *, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010894`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x1400169d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qztzztttgggd_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        const wchar_t *a6,
        const wchar_t *a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14)
{
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // ecx
  const wchar_t *v18; // rcx
  __int64 v19; // rdx
  int v20; // edx
  const wchar_t *v21; // rcx
  bool v22; // zf
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+40h] [rbp-C0h] BYREF
  int *v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  const wchar_t *v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  char *v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  const wchar_t *v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+9Ch] [rbp-64h]
  char *v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  char *v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  char *v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+C8h] [rbp-38h]
  char *v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  char *v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+E8h] [rbp-18h]
  char *v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  char *v51; // [rsp+100h] [rbp+0h]
  __int64 v52; // [rsp+108h] [rbp+8h]

  v24 = 2;
  v26 = &v24;
  v14 = -1;
  v27 = 4;
  v15 = 10;
  if ( a4 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a4[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v17 = 10;
  }
  v29 = v17;
  v30 = 0;
  v31 = &a5;
  v18 = a6;
  if ( !a4 )
    a4 = L"NULL";
  v32 = 4;
  v28 = a4;
  if ( a6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a6[v19] );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v20 = 10;
  }
  v34 = v20;
  v35 = 0;
  if ( !a6 )
    v18 = L"NULL";
  v33 = v18;
  v21 = a7;
  v22 = a7 == 0;
  if ( a7 )
  {
    do
      ++v14;
    while ( a7[v14] );
    v15 = (unsigned int)(2 * v14 + 2);
    v22 = a7 == 0;
  }
  v37 = v15;
  v39 = &a8;
  v38 = 0;
  v41 = &a9;
  if ( v22 )
    v21 = L"NULL";
  v36 = v21;
  v43 = &a10;
  v40 = 4;
  v45 = &a11;
  v47 = &a12;
  v49 = &a13;
  v51 = &a14;
  v42 = 4;
  v44 = 4;
  v46 = 8;
  v48 = 8;
  v50 = 8;
  v52 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v21,
           (const EVENT_DESCRIPTOR *)CleanmgrPluginInitStop,
           v15,
           0xDu,
           &v25);
}

```

## disassembly

```asm
0x1400169d0  mov     [rsp-8+arg_0], rbx
0x1400169d5  push    rbp
0x1400169d6  lea     rbp, [rsp-20h]
0x1400169db  sub     rsp, 120h
0x1400169e2  mov     rax, cs:__security_cookie
0x1400169e9  xor     rax, rsp
0x1400169ec  mov     [rbp+20h+var_10], rax
0x1400169f0  lea     rax, [rsp+120h+var_F0]
0x1400169f5  mov     [rsp+120h+var_F0], 2
0x1400169fd  xor     r10d, r10d
0x140016a00  mov     [rsp+120h+var_D0], rax
0x140016a05  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016a09  mov     [rsp+120h+var_C8], 4
0x140016a12  lea     r8d, [r10+0Ah]
0x140016a16  test    r9, r9
0x140016a19  jz      short loc_140016A31
0x140016a1b  mov     rcx, rax
0x140016a1e  inc     rcx
0x140016a21  cmp     [r9+rcx*2], r10w
0x140016a26  jnz     short loc_140016A1E
0x140016a28  lea     ecx, ds:2[rcx*2]
0x140016a2f  jmp     short loc_140016A34
0x140016a31  mov     ecx, r8d
0x140016a34  mov     [rsp+120h+var_B8], ecx
0x140016a38  lea     rbx, aNull_0; "NULL"
0x140016a3f  lea     rcx, [rbp+20h+arg_20]
0x140016a43  mov     [rsp+120h+var_B4], r10d
0x140016a48  test    r9, r9
0x140016a4b  mov     [rsp+120h+var_B0], rcx
0x140016a50  mov     rcx, [rbp+20h+arg_28]
0x140016a54  cmovz   r9, rbx
0x140016a58  mov     [rsp+120h+var_A8], 4
0x140016a61  mov     [rsp+120h+var_C0], r9
0x140016a66  test    rcx, rcx
0x140016a69  jz      short loc_140016A81
0x140016a6b  mov     rdx, rax
0x140016a6e  inc     rdx
0x140016a71  cmp     [rcx+rdx*2], r10w
0x140016a76  jnz     short loc_140016A6E
0x140016a78  lea     edx, ds:2[rdx*2]
0x140016a7f  jmp     short loc_140016A84
0x140016a81  mov     edx, r8d
0x140016a84  test    rcx, rcx
0x140016a87  mov     [rbp+20h+var_98], edx
0x140016a8a  mov     [rbp+20h+var_94], r10d
0x140016a8e  cmovz   rcx, rbx
0x140016a92  mov     [rbp+20h+var_A0], rcx
0x140016a96  mov     rcx, [rbp+20h+arg_30]
0x140016a9a  test    rcx, rcx
0x140016a9d  jz      short loc_140016AB4
0x140016a9f  inc     rax
0x140016aa2  cmp     [rcx+rax*2], r10w
0x140016aa7  jnz     short loc_140016A9F
0x140016aa9  lea     r8d, ds:2[rax*2]
0x140016ab1  test    rcx, rcx
0x140016ab4  lea     rax, [rbp+20h+arg_38]
0x140016ab8  mov     [rbp+20h+var_88], r8d
0x140016abc  mov     [rbp+20h+var_80], rax
0x140016ac0  lea     rdx, CleanmgrPluginInitStop
0x140016ac7  lea     rax, [rbp+20h+arg_40]
0x140016acb  mov     [rbp+20h+var_84], r10d
0x140016acf  mov     [rbp+20h+var_70], rax
0x140016ad3  cmovz   rcx, rbx
0x140016ad7  lea     rax, [rbp+20h+arg_48]
0x140016adb  mov     [rbp+20h+var_90], rcx
0x140016adf  mov     [rbp+20h+var_60], rax
0x140016ae3  mov     r9d, 0Dh
0x140016ae9  lea     rax, [rbp+20h+arg_50]
0x140016af0  mov     [rbp+20h+var_78], 4
0x140016af8  mov     [rbp+20h+var_50], rax
0x140016afc  lea     rax, [rbp+20h+arg_58]
0x140016b03  mov     [rbp+20h+var_40], rax
0x140016b07  lea     rax, [rbp+20h+arg_60]
0x140016b0e  mov     [rbp+20h+var_30], rax
0x140016b12  lea     rax, [rbp+20h+arg_68]
0x140016b19  mov     [rbp+20h+var_20], rax
0x140016b1d  lea     rax, [rsp+120h+var_E0]
0x140016b22  mov     [rsp+120h+var_100], rax
0x140016b27  mov     [rbp+20h+var_68], 4
0x140016b2f  mov     [rbp+20h+var_58], 4
0x140016b37  mov     [rbp+20h+var_48], 8
0x140016b3f  mov     [rbp+20h+var_38], 8
0x140016b47  mov     [rbp+20h+var_28], 8
0x140016b4f  mov     [rbp+20h+var_18], 4
0x140016b57  call    McGenEventWrite_EventWriteTransfer
0x140016b5c  mov     rcx, [rbp+20h+var_10]
0x140016b60  xor     rcx, rsp; StackCookie
0x140016b63  call    __security_check_cookie
0x140016b68  mov     rbx, [rsp+120h+arg_0]
0x140016b70  add     rsp, 120h
0x140016b77  pop     rbp
0x140016b78  retn
```
