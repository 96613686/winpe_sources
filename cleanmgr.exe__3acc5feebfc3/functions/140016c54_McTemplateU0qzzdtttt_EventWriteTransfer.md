# McTemplateU0qzzdtttt_EventWriteTransfer

- ea: `0x140016c54`
- end: `0x140016d76`
- name: `McTemplateU0qzzdtttt_EventWriteTransfer`
- size: `290`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, const wchar_t *, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ee64`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x140016c54`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzzdtttt_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10)
{
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rcx
  int v13; // ecx
  const wchar_t *v14; // rcx
  bool v15; // zf
  int v17; // [rsp+30h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+40h] [rbp-79h] BYREF
  int *v19; // [rsp+50h] [rbp-69h]
  __int64 v20; // [rsp+58h] [rbp-61h]
  const wchar_t *v21; // [rsp+60h] [rbp-59h]
  int v22; // [rsp+68h] [rbp-51h]
  int v23; // [rsp+6Ch] [rbp-4Dh]
  const wchar_t *v24; // [rsp+70h] [rbp-49h]
  int v25; // [rsp+78h] [rbp-41h]
  int v26; // [rsp+7Ch] [rbp-3Dh]
  char *v27; // [rsp+80h] [rbp-39h]
  __int64 v28; // [rsp+88h] [rbp-31h]
  char *v29; // [rsp+90h] [rbp-29h]
  __int64 v30; // [rsp+98h] [rbp-21h]
  char *v31; // [rsp+A0h] [rbp-19h]
  __int64 v32; // [rsp+A8h] [rbp-11h]
  char *v33; // [rsp+B0h] [rbp-9h]
  __int64 v34; // [rsp+B8h] [rbp-1h]
  char *v35; // [rsp+C0h] [rbp+7h]
  __int64 v36; // [rsp+C8h] [rbp+Fh]

  v17 = 2;
  v19 = &v17;
  v10 = -1;
  v20 = 4;
  v11 = 10;
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
  v22 = v13;
  v14 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v23 = 0;
  v21 = a4;
  v15 = a5 == 0;
  if ( a5 )
  {
    do
      ++v10;
    while ( a5[v10] );
    v11 = 2 * v10 + 2;
    v15 = a5 == 0;
  }
  v25 = v11;
  v27 = &a6;
  v26 = 0;
  v29 = &a7;
  if ( v15 )
    v14 = L"NULL";
  v24 = v14;
  v31 = &a8;
  v28 = 4;
  v33 = &a9;
  v35 = &a10;
  v30 = 4;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v14,
           (const EVENT_DESCRIPTOR *)CleanmgrPluginPurgeStart,
           0,
           9u,
           &v18);
}

```

## disassembly

```asm
0x140016c54  push    rbp
0x140016c56  lea     rbp, [rsp-27h]
0x140016c5b  sub     rsp, 0E0h
0x140016c62  mov     rax, cs:__security_cookie
0x140016c69  xor     rax, rsp
0x140016c6c  mov     [rbp+27h+var_10], rax
0x140016c70  lea     rax, [rsp+0E0h+var_B0]
0x140016c75  mov     [rsp+0E0h+var_B0], 2
0x140016c7d  xor     r8d, r8d
0x140016c80  mov     [rbp+27h+var_90], rax
0x140016c84  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016c88  mov     [rbp+27h+var_88], 4
0x140016c90  lea     edx, [r8+0Ah]
0x140016c94  test    r9, r9
0x140016c97  jz      short loc_140016CAF
0x140016c99  mov     rcx, rax
0x140016c9c  inc     rcx
0x140016c9f  cmp     [r9+rcx*2], r8w
0x140016ca4  jnz     short loc_140016C9C
0x140016ca6  lea     ecx, ds:2[rcx*2]
0x140016cad  jmp     short loc_140016CB1
0x140016caf  mov     ecx, edx
0x140016cb1  test    r9, r9
0x140016cb4  mov     [rbp+27h+var_78], ecx
0x140016cb7  mov     rcx, [rbp+27h+arg_20]
0x140016cbb  lea     r11, aNull_0; "NULL"
0x140016cc2  cmovz   r9, r11
0x140016cc6  mov     [rbp+27h+var_74], r8d
0x140016cca  mov     [rbp+27h+var_80], r9
0x140016cce  test    rcx, rcx
0x140016cd1  jz      short loc_140016CE7
0x140016cd3  inc     rax
0x140016cd6  cmp     [rcx+rax*2], r8w
0x140016cdb  jnz     short loc_140016CD3
0x140016cdd  lea     edx, ds:2[rax*2]
0x140016ce4  test    rcx, rcx
0x140016ce7  lea     rax, [rbp+27h+arg_28]
0x140016ceb  mov     [rbp+27h+var_68], edx
0x140016cee  mov     [rbp+27h+var_60], rax
0x140016cf2  lea     rdx, CleanmgrPluginPurgeStart
0x140016cf9  lea     rax, [rbp+27h+arg_30]
0x140016cfd  mov     [rbp+27h+var_64], r8d
0x140016d01  mov     [rbp+27h+var_50], rax
0x140016d05  cmovz   rcx, r11
0x140016d09  lea     rax, [rbp+27h+arg_38]
0x140016d0d  mov     [rbp+27h+var_70], rcx
0x140016d11  mov     [rbp+27h+var_40], rax
0x140016d15  mov     r9d, 9
0x140016d1b  lea     rax, [rbp+27h+arg_40]
0x140016d1f  mov     [rbp+27h+var_58], 4
0x140016d27  mov     [rbp+27h+var_30], rax
0x140016d2b  lea     rax, [rbp+27h+arg_48]
0x140016d2f  mov     [rbp+27h+var_20], rax
0x140016d33  lea     rax, [rbp+27h+var_A0]
0x140016d37  mov     [rsp+0E0h+var_C0], rax
0x140016d3c  mov     [rbp+27h+var_48], 4
0x140016d44  mov     [rbp+27h+var_38], 4
0x140016d4c  mov     [rbp+27h+var_28], 4
0x140016d54  mov     [rbp+27h+var_18], 4
0x140016d5c  call    McGenEventWrite_EventWriteTransfer
0x140016d61  mov     rcx, [rbp+27h+var_10]
0x140016d65  xor     rcx, rsp; StackCookie
0x140016d68  call    __security_check_cookie
0x140016d6d  add     rsp, 0E0h
0x140016d74  pop     rbp
0x140016d75  retn
```
