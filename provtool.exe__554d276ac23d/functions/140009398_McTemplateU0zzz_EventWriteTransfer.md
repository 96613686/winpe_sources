# McTemplateU0zzz_EventWriteTransfer

- ea: `0x140009398`
- end: `0x140009489`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400059ac`

## callees

- `0x140009340`
- `0x140009398`
- `0x14000ded0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+58h] [rbp-30h]
  int v20; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v21; // [rsp+60h] [rbp-28h]
  int v22; // [rsp+68h] [rbp-20h]
  int v23; // [rsp+6Ch] [rbp-1Ch]

  v5 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v17 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v15 = a3;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v19 = v10;
  v11 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v20 = 0;
  v18 = a4;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v12 = a5 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v22 = v6;
  v21 = v11;
  v23 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v11,
           (const EVENT_DESCRIPTOR *)ProvToolSettingsDetail,
           (__int64)a3,
           4u,
           &v14);
}

```

## disassembly

```asm
0x140009398  sub     rsp, 88h
0x14000939f  mov     rax, cs:__security_cookie
0x1400093a6  xor     rax, rsp
0x1400093a9  mov     [rsp+88h+var_18], rax
0x1400093ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400093b2  xor     r10d, r10d
0x1400093b5  mov     edx, 0Ah
0x1400093ba  test    r8, r8
0x1400093bd  jz      short loc_1400093D5
0x1400093bf  mov     rcx, rax
0x1400093c2  inc     rcx
0x1400093c5  cmp     [r8+rcx*2], r10w
0x1400093ca  jnz     short loc_1400093C2
0x1400093cc  lea     ecx, ds:2[rcx*2]
0x1400093d3  jmp     short loc_1400093D7
0x1400093d5  mov     ecx, edx
0x1400093d7  test    r8, r8
0x1400093da  mov     [rsp+88h+var_40], ecx
0x1400093de  lea     r11, aNull; "NULL"
0x1400093e5  mov     [rsp+88h+var_3C], r10d
0x1400093ea  cmovz   r8, r11
0x1400093ee  mov     [rsp+88h+var_48], r8
0x1400093f3  test    r9, r9
0x1400093f6  jz      short loc_14000940E
0x1400093f8  mov     rcx, rax
0x1400093fb  inc     rcx
0x1400093fe  cmp     [r9+rcx*2], r10w
0x140009403  jnz     short loc_1400093FB
0x140009405  lea     ecx, ds:2[rcx*2]
0x14000940c  jmp     short loc_140009410
0x14000940e  mov     ecx, edx
0x140009410  test    r9, r9
0x140009413  mov     [rsp+88h+var_30], ecx
0x140009417  mov     rcx, [rsp+88h+arg_20]
0x14000941f  cmovz   r9, r11
0x140009423  mov     [rsp+88h+var_2C], r10d
0x140009428  mov     [rsp+88h+var_38], r9
0x14000942d  test    rcx, rcx
0x140009430  jz      short loc_140009446
0x140009432  inc     rax
0x140009435  cmp     [rcx+rax*2], r10w
0x14000943a  jnz     short loc_140009432
0x14000943c  lea     edx, ds:2[rax*2]
0x140009443  test    rcx, rcx
0x140009446  cmovz   rcx, r11
0x14000944a  mov     [rsp+88h+var_20], edx
0x14000944e  lea     rax, [rsp+88h+var_58]
0x140009453  mov     [rsp+88h+var_28], rcx
0x140009458  lea     rdx, ProvToolSettingsDetail
0x14000945f  mov     [rsp+88h+var_68], rax
0x140009464  mov     r9d, 4
0x14000946a  mov     [rsp+88h+var_1C], r10d
0x14000946f  call    McGenEventWrite_EventWriteTransfer
0x140009474  mov     rcx, [rsp+88h+var_18]
0x140009479  xor     rcx, rsp; StackCookie
0x14000947c  call    __security_check_cookie
0x140009481  add     rsp, 88h
0x140009488  retn
```
