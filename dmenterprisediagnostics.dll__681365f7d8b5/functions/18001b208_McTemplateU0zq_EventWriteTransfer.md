# McTemplateU0zq_EventWriteTransfer

- ea: `0x18001b208`
- end: `0x18001b2a3`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e28`

## callees

- `0x180001800`
- `0x18001b0cc`
- `0x18001b208`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_BinaryNotFound,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x18001b208  mov     [rsp+arg_18], r9d
0x18001b20d  sub     rsp, 78h
0x18001b211  mov     rax, cs:__security_cookie
0x18001b218  xor     rax, rsp
0x18001b21b  mov     [rsp+78h+var_18], rax
0x18001b220  xor     edx, edx
0x18001b222  test    r8, r8
0x18001b225  jz      short loc_18001B23E
0x18001b227  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b22b  inc     rax
0x18001b22e  cmp     [r8+rax*2], dx
0x18001b233  jnz     short loc_18001B22B
0x18001b235  lea     eax, ds:2[rax*2]
0x18001b23c  jmp     short loc_18001B243
0x18001b23e  mov     eax, 0Ah
0x18001b243  mov     [rsp+78h+var_30], eax
0x18001b247  lea     rcx, aNull; "NULL"
0x18001b24e  lea     rax, [rsp+78h+arg_18]
0x18001b256  mov     [rsp+78h+var_2C], edx
0x18001b25a  test    r8, r8
0x18001b25d  mov     [rsp+78h+var_28], rax
0x18001b262  lea     rax, [rsp+78h+var_48]
0x18001b267  mov     [rsp+78h+var_20], 4
0x18001b270  cmovz   r8, rcx
0x18001b274  mov     [rsp+78h+var_58], rax
0x18001b279  mov     r9d, 3
0x18001b27f  mov     [rsp+78h+var_38], r8
0x18001b284  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x18001b28b  call    McGenEventWrite_EventWriteTransfer
0x18001b290  mov     rcx, [rsp+78h+var_18]
0x18001b295  xor     rcx, rsp; StackCookie
0x18001b298  call    __security_check_cookie
0x18001b29d  add     rsp, 78h
0x18001b2a1  retn
```
