# McTemplateK0zd_EtwWriteTransfer

- ea: `0x140003098`
- end: `0x14000312e`
- name: `McTemplateK0zd_EtwWriteTransfer`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000f9a0`

## callees

- `0x140002f6c`
- `0x140003098`
- `0x140003540`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zd_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-38h]
  int v10; // [rsp+48h] [rbp-30h]
  int v11; // [rsp+4Ch] [rbp-2Ch]
  char *v12; // [rsp+50h] [rbp-28h]
  __int64 v13; // [rsp+58h] [rbp-20h]

  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v10 = v6;
  v11 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v13 = 4;
  v9 = a4;
  v12 = &a5;
  return McGenEventWrite_EtwWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)AccessCheckFailure, a3, 3u, &v8);
}

```

## disassembly

```asm
0x140003098  sub     rsp, 78h
0x14000309c  mov     rax, cs:__security_cookie
0x1400030a3  xor     rax, rsp
0x1400030a6  mov     [rsp+78h+var_18], rax
0x1400030ab  xor     edx, edx
0x1400030ad  test    r9, r9
0x1400030b0  jz      short loc_1400030C9
0x1400030b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400030b6  inc     rax
0x1400030b9  cmp     [r9+rax*2], dx
0x1400030be  jnz     short loc_1400030B6
0x1400030c0  lea     eax, ds:2[rax*2]
0x1400030c7  jmp     short loc_1400030CE
0x1400030c9  mov     eax, 0Ah
0x1400030ce  test    r9, r9
0x1400030d1  mov     [rsp+78h+var_30], eax
0x1400030d5  lea     rcx, aNull_1; "NULL"
0x1400030dc  mov     [rsp+78h+var_2C], edx
0x1400030e0  cmovz   r9, rcx
0x1400030e4  mov     [rsp+78h+var_20], 4
0x1400030ed  lea     rax, [rsp+78h+arg_20]
0x1400030f5  mov     [rsp+78h+var_38], r9
0x1400030fa  mov     [rsp+78h+var_28], rax
0x1400030ff  lea     rdx, AccessCheckFailure
0x140003106  lea     rax, [rsp+78h+var_48]
0x14000310b  mov     r9d, 3
0x140003111  mov     [rsp+78h+var_58], rax
0x140003116  call    McGenEventWrite_EtwWriteTransfer
0x14000311b  mov     rcx, [rsp+78h+var_18]
0x140003120  xor     rcx, rsp; StackCookie
0x140003123  call    __security_check_cookie
0x140003128  add     rsp, 78h
0x14000312c  retn
```
