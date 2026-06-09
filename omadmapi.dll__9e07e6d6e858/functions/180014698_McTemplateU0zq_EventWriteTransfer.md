# McTemplateU0zq_EventWriteTransfer

- ea: `0x180014698`
- end: `0x180014735`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `157`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180011bc0`
- `0x1800148f0`
- `0x180015bb0`
- `0x180016c50`
- `0x1800174d0`
- `0x180018480`
- `0x180018cf0`
- `0x180018ea0`
- `0x180019060`
- `0x180019250`
- `0x180019410`
- `0x18001a3f0`

## callees

- `0x1800031b0`
- `0x180014514`
- `0x180014698`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)WP_OMADMAPI_PROVIDER_Context, a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180014698  mov     [rsp+arg_18], r9d
0x18001469d  sub     rsp, 78h
0x1800146a1  mov     rax, cs:__security_cookie
0x1800146a8  xor     rax, rsp
0x1800146ab  mov     [rsp+78h+var_18], rax
0x1800146b0  xor     r9d, r9d
0x1800146b3  test    r8, r8
0x1800146b6  jz      short loc_1800146CF
0x1800146b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800146bc  inc     rax
0x1800146bf  cmp     [r8+rax*2], r9w
0x1800146c4  jnz     short loc_1800146BC
0x1800146c6  lea     eax, ds:2[rax*2]
0x1800146cd  jmp     short loc_1800146D4
0x1800146cf  mov     eax, 0Ah
0x1800146d4  mov     [rsp+78h+var_30], eax
0x1800146d8  lea     rcx, aNull; "NULL"
0x1800146df  lea     rax, [rsp+78h+arg_18]
0x1800146e7  mov     [rsp+78h+var_2C], r9d
0x1800146ec  test    r8, r8
0x1800146ef  mov     [rsp+78h+var_28], rax
0x1800146f4  lea     rax, [rsp+78h+var_48]
0x1800146f9  mov     [rsp+78h+var_20], 4
0x180014702  cmovz   r8, rcx
0x180014706  mov     [rsp+78h+var_58], rax
0x18001470b  mov     r9d, 3
0x180014711  mov     [rsp+78h+var_38], r8
0x180014716  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18001471d  call    McGenEventWrite_EventWriteTransfer
0x180014722  mov     rcx, [rsp+78h+var_18]
0x180014727  xor     rcx, rsp; StackCookie
0x18001472a  call    __security_check_cookie
0x18001472f  add     rsp, 78h
0x180014733  retn
```
