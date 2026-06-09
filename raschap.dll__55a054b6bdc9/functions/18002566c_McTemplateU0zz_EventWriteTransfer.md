# McTemplateU0zz_EventWriteTransfer

- ea: `0x18002566c`
- end: `0x180025724`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000febc`

## callees

- `0x180013b20`
- `0x180016ab0`
- `0x18002566c`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  int v7; // ecx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x18002566c  sub     rsp, 78h
0x180025670  mov     rax, cs:__security_cookie
0x180025677  xor     rax, rsp
0x18002567a  mov     [rsp+78h+var_18], rax
0x18002567f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025683  xor     r10d, r10d
0x180025686  mov     edx, 0Ah
0x18002568b  test    r8, r8
0x18002568e  jz      short loc_1800256A6
0x180025690  mov     rcx, rax
0x180025693  inc     rcx
0x180025696  cmp     [r8+rcx*2], r10w
0x18002569b  jnz     short loc_180025693
0x18002569d  lea     ecx, ds:2[rcx*2]
0x1800256a4  jmp     short loc_1800256A8
0x1800256a6  mov     ecx, edx
0x1800256a8  test    r8, r8
0x1800256ab  mov     [rsp+78h+var_30], ecx
0x1800256af  lea     r11, aNull_0; "NULL"
0x1800256b6  mov     [rsp+78h+var_2C], r10d
0x1800256bb  cmovz   r8, r11
0x1800256bf  mov     [rsp+78h+var_38], r8
0x1800256c4  test    r9, r9
0x1800256c7  jz      short loc_1800256DD
0x1800256c9  inc     rax
0x1800256cc  cmp     [r9+rax*2], r10w
0x1800256d1  jnz     short loc_1800256C9
0x1800256d3  lea     edx, ds:2[rax*2]
0x1800256da  test    r9, r9
0x1800256dd  cmovz   r9, r11
0x1800256e1  mov     [rsp+78h+var_20], edx
0x1800256e5  mov     [rsp+78h+var_28], r9
0x1800256ea  lea     rax, [rsp+78h+var_48]
0x1800256ef  mov     r9d, 3
0x1800256f5  mov     [rsp+78h+var_1C], r10d
0x1800256fa  lea     rdx, NullOrEmptyParameterFailureEvent
0x180025701  mov     [rsp+78h+var_58], rax
0x180025706  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18002570d  call    McGenEventWrite_EventWriteTransfer
0x180025712  mov     rcx, [rsp+78h+var_18]
0x180025717  xor     rcx, rsp; StackCookie
0x18002571a  call    __security_check_cookie
0x18002571f  add     rsp, 78h
0x180025723  retn
```
