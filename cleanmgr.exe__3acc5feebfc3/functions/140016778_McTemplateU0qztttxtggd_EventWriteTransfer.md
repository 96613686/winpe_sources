# McTemplateU0qztttxtggd_EventWriteTransfer

- ea: `0x140016778`
- end: `0x14001689d`
- name: `McTemplateU0qztttxtggd_EventWriteTransfer`
- size: `293`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140012a7c`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x140016778`

## pseudocode

```c
ULONG __fastcall McTemplateU0qztttxtggd_EventWriteTransfer(
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
  v25 = 4;
  v19 = a4;
  v24 = &a6;
  v27 = 4;
  v26 = &a7;
  v28 = &a8;
  v30 = &a9;
  v32 = &a10;
  v34 = &a11;
  v36 = &a12;
  v29 = 8;
  v31 = 4;
  v33 = 8;
  v35 = 8;
  v37 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)CleanmgrPluginScan,
           a3,
           0xBu,
           &v16);
}

```

## disassembly

```asm
0x140016778  push    rbp
0x14001677a  lea     rbp, [rsp-17h]
0x14001677f  sub     rsp, 100h
0x140016786  mov     rax, cs:__security_cookie
0x14001678d  xor     rax, rsp
0x140016790  mov     [rbp+17h+var_10], rax
0x140016794  xor     edx, edx
0x140016796  mov     [rsp+100h+var_D0], 2
0x14001679e  mov     [rsp+100h+var_A8], 4
0x1400167a7  lea     rax, [rsp+100h+var_D0]
0x1400167ac  mov     [rsp+100h+var_B0], rax
0x1400167b1  test    r9, r9
0x1400167b4  jz      short loc_1400167CD
0x1400167b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400167ba  inc     rax
0x1400167bd  cmp     [r9+rax*2], dx
0x1400167c2  jnz     short loc_1400167BA
0x1400167c4  lea     eax, ds:2[rax*2]
0x1400167cb  jmp     short loc_1400167D2
0x1400167cd  mov     eax, 0Ah
0x1400167d2  mov     [rsp+100h+var_98], eax
0x1400167d6  lea     rcx, aNull_0; "NULL"
0x1400167dd  test    r9, r9
0x1400167e0  mov     [rbp+17h+var_94], edx
0x1400167e3  lea     rax, [rbp+17h+arg_20]
0x1400167e7  mov     [rbp+17h+var_88], 4
0x1400167ef  mov     [rbp+17h+var_90], rax
0x1400167f3  lea     rdx, CleanmgrPluginScan
0x1400167fa  cmovz   r9, rcx
0x1400167fe  mov     [rbp+17h+var_78], 4
0x140016806  lea     rax, [rbp+17h+arg_28]
0x14001680a  mov     [rsp+100h+var_A0], r9
0x14001680f  mov     [rbp+17h+var_80], rax
0x140016813  mov     r9d, 0Bh
0x140016819  lea     rax, [rbp+17h+arg_30]
0x14001681d  mov     [rbp+17h+var_68], 4
0x140016825  mov     [rbp+17h+var_70], rax
0x140016829  lea     rax, [rbp+17h+arg_38]
0x14001682d  mov     [rbp+17h+var_60], rax
0x140016831  lea     rax, [rbp+17h+arg_40]
0x140016835  mov     [rbp+17h+var_50], rax
0x140016839  lea     rax, [rbp+17h+arg_48]
0x14001683d  mov     [rbp+17h+var_40], rax
0x140016841  lea     rax, [rbp+17h+arg_50]
0x140016845  mov     [rbp+17h+var_30], rax
0x140016849  lea     rax, [rbp+17h+arg_58]
0x14001684d  mov     [rbp+17h+var_20], rax
0x140016851  lea     rax, [rsp+100h+var_C0]
0x140016856  mov     [rsp+100h+var_E0], rax
0x14001685b  mov     [rbp+17h+var_58], 8
0x140016863  mov     [rbp+17h+var_48], 4
0x14001686b  mov     [rbp+17h+var_38], 8
0x140016873  mov     [rbp+17h+var_28], 8
0x14001687b  mov     [rbp+17h+var_18], 4
0x140016883  call    McGenEventWrite_EventWriteTransfer
0x140016888  mov     rcx, [rbp+17h+var_10]
0x14001688c  xor     rcx, rsp; StackCookie
0x14001688f  call    __security_check_cookie
0x140016894  add     rsp, 100h
0x14001689b  pop     rbp
0x14001689c  retn
```
