# McTemplateU0zqqz_EventWriteTransfer

- ea: `0x1800038d4`
- end: `0x1800039b8`
- name: `McTemplateU0zqqz_EventWriteTransfer`
- size: `228`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, int, char, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002350`

## callees

- `0x1800037f8`
- `0x1800038d4`
- `0x180009950`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-9h]
  int v16; // [rsp+48h] [rbp-1h]
  int v17; // [rsp+4Ch] [rbp+3h]
  int *v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  int v25; // [rsp+B8h] [rbp+6Fh] BYREF

  v25 = a4;
  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v16 = v10;
  v17 = 0;
  v18 = &v25;
  v19 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v20 = &a5;
  v11 = a6;
  v15 = a3;
  v21 = 4;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v8 = 2 * v6 + 2;
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v23 = v8;
  v22 = v11;
  v24 = 0;
  return McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWSPHONE_DATASHARING_Context, a2, (__int64)a3, 5u, &v14);
}

```

## disassembly

```asm
0x1800038d4  mov     [rsp-8+arg_18], r9d
0x1800038d9  push    rbp
0x1800038da  lea     rbp, [rsp-47h]
0x1800038df  sub     rsp, 90h
0x1800038e6  mov     rax, cs:__security_cookie
0x1800038ed  xor     rax, rsp
0x1800038f0  mov     [rbp+47h+var_10], rax
0x1800038f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800038f8  xor     r9d, r9d
0x1800038fb  mov     r10, rdx
0x1800038fe  mov     edx, 0Ah
0x180003903  test    r8, r8
0x180003906  jz      short loc_18000391E
0x180003908  mov     rcx, rax
0x18000390b  inc     rcx
0x18000390e  cmp     [r8+rcx*2], r9w
0x180003913  jnz     short loc_18000390B
0x180003915  lea     ecx, ds:2[rcx*2]
0x18000391c  jmp     short loc_180003920
0x18000391e  mov     ecx, edx
0x180003920  mov     [rbp+47h+var_48], ecx
0x180003923  lea     r11, aNull; "NULL"
0x18000392a  lea     rcx, [rbp+47h+arg_18]
0x18000392e  mov     [rbp+47h+var_44], r9d
0x180003932  mov     [rbp+47h+var_40], rcx
0x180003936  test    r8, r8
0x180003939  lea     rcx, [rbp+47h+arg_20]
0x18000393d  mov     [rbp+47h+var_38], 4
0x180003945  cmovz   r8, r11
0x180003949  mov     [rbp+47h+var_30], rcx
0x18000394d  mov     rcx, [rbp+47h+arg_28]
0x180003951  mov     [rbp+47h+var_50], r8
0x180003955  mov     [rbp+47h+var_28], 4
0x18000395d  test    rcx, rcx
0x180003960  jz      short loc_180003976
0x180003962  inc     rax
0x180003965  cmp     [rcx+rax*2], r9w
0x18000396a  jnz     short loc_180003962
0x18000396c  lea     edx, ds:2[rax*2]
0x180003973  test    rcx, rcx
0x180003976  cmovz   rcx, r11
0x18000397a  mov     [rbp+47h+var_18], edx
0x18000397d  mov     [rbp+47h+var_20], rcx
0x180003981  lea     rax, [rbp+47h+var_60]
0x180003985  mov     [rbp+47h+var_14], r9d
0x180003989  lea     rcx, MICROSOFT_WINDOWSPHONE_DATASHARING_Context
0x180003990  mov     r9d, 5
0x180003996  mov     [rsp+90h+var_70], rax
0x18000399b  mov     rdx, r10
0x18000399e  call    McGenEventWrite_EventWriteTransfer
0x1800039a3  mov     rcx, [rbp+47h+var_10]
0x1800039a7  xor     rcx, rsp; StackCookie
0x1800039aa  call    __security_check_cookie
0x1800039af  add     rsp, 90h
0x1800039b6  pop     rbp
0x1800039b7  retn
```
