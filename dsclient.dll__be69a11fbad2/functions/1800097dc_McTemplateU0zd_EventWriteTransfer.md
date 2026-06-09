# McTemplateU0zd_EventWriteTransfer

- ea: `0x1800097dc`
- end: `0x18000987d`
- name: `McTemplateU0zd_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800095e8`

## callees

- `0x1800037f8`
- `0x1800097dc`
- `0x180009950`

## pseudocode

```c
ULONG __fastcall McTemplateU0zd_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
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
           (REGHANDLE *)MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context,
           (const EVENT_DESCRIPTOR *)ExecGenericTraceFunctionError,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x1800097dc  mov     [rsp+arg_18], r9d
0x1800097e1  sub     rsp, 78h
0x1800097e5  mov     rax, cs:__security_cookie
0x1800097ec  xor     rax, rsp
0x1800097ef  mov     [rsp+78h+var_18], rax
0x1800097f4  xor     edx, edx
0x1800097f6  test    r8, r8
0x1800097f9  jz      short loc_180009812
0x1800097fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800097ff  inc     rax
0x180009802  cmp     [r8+rax*2], dx
0x180009807  jnz     short loc_1800097FF
0x180009809  lea     eax, ds:2[rax*2]
0x180009810  jmp     short loc_180009817
0x180009812  mov     eax, 0Ah
0x180009817  mov     [rsp+78h+var_30], eax
0x18000981b  lea     rcx, aNull; "NULL"
0x180009822  lea     rax, [rsp+78h+arg_18]
0x18000982a  mov     [rsp+78h+var_2C], edx
0x18000982e  test    r8, r8
0x180009831  mov     [rsp+78h+var_28], rax
0x180009836  lea     rax, [rsp+78h+var_48]
0x18000983b  mov     [rsp+78h+var_20], 4
0x180009844  cmovz   r8, rcx
0x180009848  mov     [rsp+78h+var_58], rax
0x18000984d  mov     r9d, 3
0x180009853  mov     [rsp+78h+var_38], r8
0x180009858  lea     rdx, ExecGenericTraceFunctionError
0x18000985f  lea     rcx, MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context
0x180009866  call    McGenEventWrite_EventWriteTransfer
0x18000986b  mov     rcx, [rsp+78h+var_18]
0x180009870  xor     rcx, rsp; StackCookie
0x180009873  call    __security_check_cookie
0x180009878  add     rsp, 78h
0x18000987c  retn
```
