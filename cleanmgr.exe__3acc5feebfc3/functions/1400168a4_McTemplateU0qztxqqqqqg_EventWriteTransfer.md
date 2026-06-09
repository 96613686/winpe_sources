# McTemplateU0qztxqqqqqg_EventWriteTransfer

- ea: `0x1400168a4`
- end: `0x1400169c9`
- name: `McTemplateU0qztxqqqqqg_EventWriteTransfer`
- size: `293`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012a7c`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x1400168a4`

## pseudocode

```c
ULONG __fastcall McTemplateU0qztxqqqqqg_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12)
{
  __int64 v12; // rax
  int v13; // eax
  int v15; // [rsp+30h] [rbp-B9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+40h] [rbp-A9h] BYREF
  int *v17; // [rsp+50h] [rbp-99h]
  __int64 v18; // [rsp+58h] [rbp-91h]
  const wchar_t *v19; // [rsp+60h] [rbp-89h]
  int v20; // [rsp+68h] [rbp-81h]
  int v21; // [rsp+6Ch] [rbp-7Dh]
  char *v22; // [rsp+70h] [rbp-79h]
  __int64 v23; // [rsp+78h] [rbp-71h]
  char *v24; // [rsp+80h] [rbp-69h]
  __int64 v25; // [rsp+88h] [rbp-61h]
  char *v26; // [rsp+90h] [rbp-59h]
  __int64 v27; // [rsp+98h] [rbp-51h]
  char *v28; // [rsp+A0h] [rbp-49h]
  __int64 v29; // [rsp+A8h] [rbp-41h]
  char *v30; // [rsp+B0h] [rbp-39h]
  __int64 v31; // [rsp+B8h] [rbp-31h]
  char *v32; // [rsp+C0h] [rbp-29h]
  __int64 v33; // [rsp+C8h] [rbp-21h]
  char *v34; // [rsp+D0h] [rbp-19h]
  __int64 v35; // [rsp+D8h] [rbp-11h]
  char *v36; // [rsp+E0h] [rbp-9h]
  __int64 v37; // [rsp+E8h] [rbp-1h]

  v15 = 2;
  v18 = 4;
  v17 = &v15;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v20 = v13;
  v21 = 0;
  v23 = 4;
  v22 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v25 = 8;
  v19 = a4;
  v24 = &a6;
  v27 = 4;
  v26 = &a7;
  v28 = &a8;
  v30 = &a9;
  v32 = &a10;
  v34 = &a11;
  v36 = &a12;
  v29 = 4;
  v31 = 4;
  v33 = 4;
  v35 = 4;
  v37 = 8;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)CleanmgrScan, a3, 0xBu, &v16);
}

```

## disassembly

```asm
0x1400168a4  push    rbp
0x1400168a6  lea     rbp, [rsp-17h]
0x1400168ab  sub     rsp, 100h
0x1400168b2  mov     rax, cs:__security_cookie
0x1400168b9  xor     rax, rsp
0x1400168bc  mov     [rbp+17h+var_10], rax
0x1400168c0  xor     edx, edx
0x1400168c2  mov     [rsp+100h+var_D0], 2
0x1400168ca  mov     [rsp+100h+var_A8], 4
0x1400168d3  lea     rax, [rsp+100h+var_D0]
0x1400168d8  mov     [rsp+100h+var_B0], rax
0x1400168dd  test    r9, r9
0x1400168e0  jz      short loc_1400168F9
0x1400168e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400168e6  inc     rax
0x1400168e9  cmp     [r9+rax*2], dx
0x1400168ee  jnz     short loc_1400168E6
0x1400168f0  lea     eax, ds:2[rax*2]
0x1400168f7  jmp     short loc_1400168FE
0x1400168f9  mov     eax, 0Ah
0x1400168fe  mov     [rsp+100h+var_98], eax
0x140016902  lea     rcx, aNull_0; "NULL"
0x140016909  test    r9, r9
0x14001690c  mov     [rbp+17h+var_94], edx
0x14001690f  lea     rax, [rbp+17h+arg_20]
0x140016913  mov     [rbp+17h+var_88], 4
0x14001691b  mov     [rbp+17h+var_90], rax
0x14001691f  lea     rdx, CleanmgrScan
0x140016926  cmovz   r9, rcx
0x14001692a  mov     [rbp+17h+var_78], 8
0x140016932  lea     rax, [rbp+17h+arg_28]
0x140016936  mov     [rsp+100h+var_A0], r9
0x14001693b  mov     [rbp+17h+var_80], rax
0x14001693f  mov     r9d, 0Bh
0x140016945  lea     rax, [rbp+17h+arg_30]
0x140016949  mov     [rbp+17h+var_68], 4
0x140016951  mov     [rbp+17h+var_70], rax
0x140016955  lea     rax, [rbp+17h+arg_38]
0x140016959  mov     [rbp+17h+var_60], rax
0x14001695d  lea     rax, [rbp+17h+arg_40]
0x140016961  mov     [rbp+17h+var_50], rax
0x140016965  lea     rax, [rbp+17h+arg_48]
0x140016969  mov     [rbp+17h+var_40], rax
0x14001696d  lea     rax, [rbp+17h+arg_50]
0x140016971  mov     [rbp+17h+var_30], rax
0x140016975  lea     rax, [rbp+17h+arg_58]
0x140016979  mov     [rbp+17h+var_20], rax
0x14001697d  lea     rax, [rsp+100h+var_C0]
0x140016982  mov     [rsp+100h+var_E0], rax
0x140016987  mov     [rbp+17h+var_58], 4
0x14001698f  mov     [rbp+17h+var_48], 4
0x140016997  mov     [rbp+17h+var_38], 4
0x14001699f  mov     [rbp+17h+var_28], 4
0x1400169a7  mov     [rbp+17h+var_18], 8
0x1400169af  call    McGenEventWrite_EventWriteTransfer
0x1400169b4  mov     rcx, [rbp+17h+var_10]
0x1400169b8  xor     rcx, rsp; StackCookie
0x1400169bb  call    __security_check_cookie
0x1400169c0  add     rsp, 100h
0x1400169c7  pop     rbp
0x1400169c8  retn
```
