# McTemplateU0zt_EventWriteTransfer

- ea: `0x180010c84`
- end: `0x180010d20`
- name: `McTemplateU0zt_EventWriteTransfer`
- size: `156`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800109d4`

## callees

- `0x18000b838`
- `0x180010c84`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0zt_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context, a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180010c84  mov     [rsp+arg_18], r9d
0x180010c89  sub     rsp, 78h
0x180010c8d  mov     rax, cs:__security_cookie
0x180010c94  xor     rax, rsp
0x180010c97  mov     [rsp+78h+var_18], rax
0x180010c9c  xor     r9d, r9d
0x180010c9f  test    r8, r8
0x180010ca2  jz      short loc_180010CBB
0x180010ca4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ca8  inc     rax
0x180010cab  cmp     [r8+rax*2], r9w
0x180010cb0  jnz     short loc_180010CA8
0x180010cb2  lea     eax, ds:2[rax*2]
0x180010cb9  jmp     short loc_180010CC0
0x180010cbb  mov     eax, 0Ah
0x180010cc0  mov     [rsp+78h+var_30], eax
0x180010cc4  lea     rcx, aNull_0; "NULL"
0x180010ccb  lea     rax, [rsp+78h+arg_18]
0x180010cd3  mov     [rsp+78h+var_2C], r9d
0x180010cd8  test    r8, r8
0x180010cdb  mov     [rsp+78h+var_28], rax
0x180010ce0  lea     rax, [rsp+78h+var_48]
0x180010ce5  mov     [rsp+78h+var_20], 4
0x180010cee  cmovz   r8, rcx
0x180010cf2  mov     [rsp+78h+var_58], rax
0x180010cf7  mov     r9d, 3
0x180010cfd  mov     [rsp+78h+var_38], r8
0x180010d02  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x180010d09  call    McGenEventWrite_EventWriteTransfer
0x180010d0e  mov     rcx, [rsp+78h+var_18]
0x180010d13  xor     rcx, rsp; StackCookie
0x180010d16  call    __security_check_cookie
0x180010d1b  add     rsp, 78h
0x180010d1f  retn
```
