# McTemplateU0ddz_EventWriteTransfer

- ea: `0x18001b808`
- end: `0x18001b8b0`
- name: `McTemplateU0ddz_EventWriteTransfer`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006090`
- `0x180007420`

## callees

- `0x18000f698`
- `0x18001b808`
- `0x18001f1b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0ddz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-50h] BYREF
  int *v10; // [rsp+40h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-38h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  const wchar_t *v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+A0h] [rbp+20h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF

  v18 = a4;
  v17 = a3;
  v5 = a5;
  v10 = &v17;
  v11 = 4;
  v13 = 4;
  v12 = &v18;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v15 = v7;
  v16 = 0;
  if ( !a5 )
    v5 = L"NULL";
  v14 = v5;
  return McGenEventWrite_EventWriteTransfer((__int64)v5, a2, (__int64)L"NULL", 4u, &v9);
}

```

## disassembly

```asm
0x18001b808  mov     [rsp-8+arg_18], r9d
0x18001b80d  mov     [rsp-8+arg_10], r8d
0x18001b812  push    rbp
0x18001b813  mov     rbp, rsp
0x18001b816  sub     rsp, 80h
0x18001b81d  mov     rax, cs:__security_cookie
0x18001b824  xor     rax, rsp
0x18001b827  mov     [rbp+var_10], rax
0x18001b82b  mov     rcx, [rbp+arg_20]
0x18001b82f  lea     rax, [rbp+arg_10]
0x18001b833  mov     r10d, 4
0x18001b839  mov     [rbp+var_40], rax
0x18001b83d  xor     r9d, r9d
0x18001b840  mov     [rbp+var_38], r10
0x18001b844  mov     [rbp+var_28], r10
0x18001b848  lea     rax, [rbp+arg_18]
0x18001b84c  mov     [rbp+var_30], rax
0x18001b850  test    rcx, rcx
0x18001b853  jz      short loc_18001B86C
0x18001b855  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b859  inc     rax
0x18001b85c  cmp     [rcx+rax*2], r9w
0x18001b861  jnz     short loc_18001B859
0x18001b863  lea     eax, ds:2[rax*2]
0x18001b86a  jmp     short loc_18001B871
0x18001b86c  mov     eax, 0Ah
0x18001b871  test    rcx, rcx
0x18001b874  mov     [rbp+var_18], eax
0x18001b877  lea     r8, aNull_0; "NULL"
0x18001b87e  mov     [rbp+var_14], r9d
0x18001b882  cmovz   rcx, r8
0x18001b886  lea     rax, [rbp+var_50]
0x18001b88a  mov     r9d, r10d
0x18001b88d  mov     [rbp+var_20], rcx
0x18001b891  mov     [rsp+80h+var_60], rax
0x18001b896  call    McGenEventWrite_EventWriteTransfer
0x18001b89b  mov     rcx, [rbp+var_10]
0x18001b89f  xor     rcx, rsp; StackCookie
0x18001b8a2  call    __security_check_cookie
0x18001b8a7  add     rsp, 80h
0x18001b8ae  pop     rbp
0x18001b8af  retn
```
