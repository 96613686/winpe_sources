# McTemplateU0dzz_EventWriteTransfer

- ea: `0x180010bac`
- end: `0x180010c7d`
- name: `McTemplateU0dzz_EventWriteTransfer`
- size: `209`
- prototype: `ULONG __fastcall(__int64, __int64, int, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004e80`

## callees

- `0x18000b838`
- `0x180010bac`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0dzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  int *v13; // [rsp+40h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-38h]
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = a3;
  v13 = &v21;
  v5 = -1;
  v14 = 4;
  v6 = 10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v19 = v6;
  v18 = v9;
  v20 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context,
           (const EVENT_DESCRIPTOR *)CatalogLoadStop,
           0,
           4u,
           &v12);
}

```

## disassembly

```asm
0x180010bac  mov     [rsp-8+arg_10], r8d
0x180010bb1  push    rbp
0x180010bb2  mov     rbp, rsp
0x180010bb5  sub     rsp, 80h
0x180010bbc  mov     rax, cs:__security_cookie
0x180010bc3  xor     rax, rsp
0x180010bc6  mov     [rbp+var_10], rax
0x180010bca  lea     rax, [rbp+arg_10]
0x180010bce  mov     r11d, 4
0x180010bd4  mov     [rbp+var_40], rax
0x180010bd8  xor     r8d, r8d
0x180010bdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010bdf  mov     [rbp+var_38], r11
0x180010be3  lea     edx, [r11+6]
0x180010be7  test    r9, r9
0x180010bea  jz      short loc_180010C02
0x180010bec  mov     rcx, rax
0x180010bef  inc     rcx
0x180010bf2  cmp     [r9+rcx*2], r8w
0x180010bf7  jnz     short loc_180010BEF
0x180010bf9  lea     ecx, ds:2[rcx*2]
0x180010c00  jmp     short loc_180010C04
0x180010c02  mov     ecx, edx
0x180010c04  test    r9, r9
0x180010c07  mov     [rbp+var_28], ecx
0x180010c0a  mov     rcx, [rbp+arg_20]
0x180010c0e  lea     r10, aNull_0; "NULL"
0x180010c15  cmovz   r9, r10
0x180010c19  mov     [rbp+var_24], r8d
0x180010c1d  mov     [rbp+var_30], r9
0x180010c21  test    rcx, rcx
0x180010c24  jz      short loc_180010C3A
0x180010c26  inc     rax
0x180010c29  cmp     [rcx+rax*2], r8w
0x180010c2e  jnz     short loc_180010C26
0x180010c30  lea     edx, ds:2[rax*2]
0x180010c37  test    rcx, rcx
0x180010c3a  cmovz   rcx, r10
0x180010c3e  mov     [rbp+var_18], edx
0x180010c41  mov     [rbp+var_20], rcx
0x180010c45  lea     rax, [rbp+var_50]
0x180010c49  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x180010c50  mov     [rbp+var_14], r8d
0x180010c54  mov     r9d, r11d
0x180010c57  mov     [rsp+80h+var_60], rax
0x180010c5c  lea     rdx, CatalogLoadStop
0x180010c63  call    McGenEventWrite_EventWriteTransfer
0x180010c68  mov     rcx, [rbp+var_10]
0x180010c6c  xor     rcx, rsp; StackCookie
0x180010c6f  call    __security_check_cookie
0x180010c74  add     rsp, 80h
0x180010c7b  pop     rbp
0x180010c7c  retn
```
