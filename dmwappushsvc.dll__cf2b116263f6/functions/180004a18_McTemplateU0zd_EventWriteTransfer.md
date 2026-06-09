# McTemplateU0zd_EventWriteTransfer

- ea: `0x180004a18`
- end: `0x180004aad`
- name: `McTemplateU0zd_EventWriteTransfer`
- size: `149`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030e4`

## callees

- `0x180001a70`
- `0x180004968`
- `0x180004a18`

## pseudocode

```c
ULONG __fastcall McTemplateU0zd_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180004a18  mov     [rsp+arg_18], r9d
0x180004a1d  sub     rsp, 78h
0x180004a21  mov     rax, cs:__security_cookie
0x180004a28  xor     rax, rsp
0x180004a2b  mov     [rsp+78h+var_18], rax
0x180004a30  xor     r9d, r9d
0x180004a33  test    r8, r8
0x180004a36  jz      short loc_180004A4F
0x180004a38  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a3c  inc     rax
0x180004a3f  cmp     [r8+rax*2], r9w
0x180004a44  jnz     short loc_180004A3C
0x180004a46  lea     eax, ds:2[rax*2]
0x180004a4d  jmp     short loc_180004A54
0x180004a4f  mov     eax, 0Ah
0x180004a54  mov     [rsp+78h+var_30], eax
0x180004a58  lea     rcx, aNull; "NULL"
0x180004a5f  lea     rax, [rsp+78h+arg_18]
0x180004a67  mov     [rsp+78h+var_2C], r9d
0x180004a6c  test    r8, r8
0x180004a6f  mov     [rsp+78h+var_28], rax
0x180004a74  lea     rax, [rsp+78h+var_48]
0x180004a79  mov     [rsp+78h+var_20], 4
0x180004a82  cmovz   r8, rcx
0x180004a86  mov     [rsp+78h+var_58], rax
0x180004a8b  mov     r9d, 3
0x180004a91  mov     [rsp+78h+var_38], r8
0x180004a96  call    McGenEventWrite_EventWriteTransfer
0x180004a9b  mov     rcx, [rsp+78h+var_18]
0x180004aa0  xor     rcx, rsp; StackCookie
0x180004aa3  call    __security_check_cookie
0x180004aa8  add     rsp, 78h
0x180004aac  retn
```
