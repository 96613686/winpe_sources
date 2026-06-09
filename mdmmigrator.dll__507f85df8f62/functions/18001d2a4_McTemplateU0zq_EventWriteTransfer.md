# McTemplateU0zq_EventWriteTransfer

- ea: `0x18001d2a4`
- end: `0x18001d345`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c054`
- `0x18001c61c`

## callees

- `0x1800022e0`
- `0x1800097fc`
- `0x18001d2a4`

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
           (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)DMScheduleAdminPollValues,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x18001d2a4  mov     [rsp+arg_18], r9d
0x18001d2a9  sub     rsp, 78h
0x18001d2ad  mov     rax, cs:__security_cookie
0x18001d2b4  xor     rax, rsp
0x18001d2b7  mov     [rsp+78h+var_18], rax
0x18001d2bc  xor     edx, edx
0x18001d2be  test    r8, r8
0x18001d2c1  jz      short loc_18001D2DA
0x18001d2c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d2c7  inc     rax
0x18001d2ca  cmp     [r8+rax*2], dx
0x18001d2cf  jnz     short loc_18001D2C7
0x18001d2d1  lea     eax, ds:2[rax*2]
0x18001d2d8  jmp     short loc_18001D2DF
0x18001d2da  mov     eax, 0Ah
0x18001d2df  mov     [rsp+78h+var_30], eax
0x18001d2e3  lea     rcx, aNull_0; "NULL"
0x18001d2ea  lea     rax, [rsp+78h+arg_18]
0x18001d2f2  mov     [rsp+78h+var_2C], edx
0x18001d2f6  test    r8, r8
0x18001d2f9  mov     [rsp+78h+var_28], rax
0x18001d2fe  lea     rax, [rsp+78h+var_48]
0x18001d303  mov     [rsp+78h+var_20], 4
0x18001d30c  cmovz   r8, rcx
0x18001d310  mov     [rsp+78h+var_58], rax
0x18001d315  mov     r9d, 3
0x18001d31b  mov     [rsp+78h+var_38], r8
0x18001d320  lea     rdx, DMScheduleAdminPollValues
0x18001d327  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001d32e  call    McGenEventWrite_EventWriteTransfer
0x18001d333  mov     rcx, [rsp+78h+var_18]
0x18001d338  xor     rcx, rsp; StackCookie
0x18001d33b  call    __security_check_cookie
0x18001d340  add     rsp, 78h
0x18001d344  retn
```
