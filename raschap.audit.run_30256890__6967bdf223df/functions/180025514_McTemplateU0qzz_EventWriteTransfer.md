# McTemplateU0qzz_EventWriteTransfer

- ea: `0x180025514`
- end: `0x1800255e5`
- name: `McTemplateU0qzz_EventWriteTransfer`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fdf0`

## callees

- `0x180013b20`
- `0x180016ab0`
- `0x180025514`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  int *v13; // [rsp+40h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-38h]
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = a3;
  v13 = &v21;
  v5 = -1;
  v14 = 4;
  v6 = 10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v19 = v6;
  v18 = v9;
  v20 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)RegistryFailureEvent,
           0,
           4u,
           &v12);
}

```

## disassembly

```asm
0x180025514  mov     [rsp-8+arg_10], r8d
0x180025519  push    rbp
0x18002551a  mov     rbp, rsp
0x18002551d  sub     rsp, 80h
0x180025524  mov     rax, cs:__security_cookie
0x18002552b  xor     rax, rsp
0x18002552e  mov     [rbp+var_10], rax
0x180025532  lea     rax, [rbp+arg_10]
0x180025536  mov     r11d, 4
0x18002553c  mov     [rbp+var_40], rax
0x180025540  xor     r8d, r8d
0x180025543  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025547  mov     [rbp+var_38], r11
0x18002554b  lea     edx, [r11+6]
0x18002554f  test    r9, r9
0x180025552  jz      short loc_18002556A
0x180025554  mov     rcx, rax
0x180025557  inc     rcx
0x18002555a  cmp     [r9+rcx*2], r8w
0x18002555f  jnz     short loc_180025557
0x180025561  lea     ecx, ds:2[rcx*2]
0x180025568  jmp     short loc_18002556C
0x18002556a  mov     ecx, edx
0x18002556c  test    r9, r9
0x18002556f  mov     [rbp+var_28], ecx
0x180025572  mov     rcx, [rbp+arg_20]
0x180025576  lea     r10, aNull_0; "NULL"
0x18002557d  cmovz   r9, r10
0x180025581  mov     [rbp+var_24], r8d
0x180025585  mov     [rbp+var_30], r9
0x180025589  test    rcx, rcx
0x18002558c  jz      short loc_1800255A2
0x18002558e  inc     rax
0x180025591  cmp     [rcx+rax*2], r8w
0x180025596  jnz     short loc_18002558E
0x180025598  lea     edx, ds:2[rax*2]
0x18002559f  test    rcx, rcx
0x1800255a2  cmovz   rcx, r10
0x1800255a6  mov     [rbp+var_18], edx
0x1800255a9  mov     [rbp+var_20], rcx
0x1800255ad  lea     rax, [rbp+var_50]
0x1800255b1  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800255b8  mov     [rbp+var_14], r8d
0x1800255bc  mov     r9d, r11d
0x1800255bf  mov     [rsp+80h+var_60], rax
0x1800255c4  lea     rdx, RegistryFailureEvent
0x1800255cb  call    McGenEventWrite_EventWriteTransfer
0x1800255d0  mov     rcx, [rbp+var_10]
0x1800255d4  xor     rcx, rsp; StackCookie
0x1800255d7  call    __security_check_cookie
0x1800255dc  add     rsp, 80h
0x1800255e3  pop     rbp
0x1800255e4  retn
```
