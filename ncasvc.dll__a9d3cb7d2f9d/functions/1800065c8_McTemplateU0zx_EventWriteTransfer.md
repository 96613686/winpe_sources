# McTemplateU0zx_EventWriteTransfer

- ea: `0x1800065c8`
- end: `0x18000665e`
- name: `McTemplateU0zx_EventWriteTransfer`
- size: `150`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, ...)`
- caller_count: `34`
- callee_count: `3`
- tags: ``

## callers

- `0x1800067e0`
- `0x180006940`
- `0x180007560`
- `0x180007780`
- `0x180007954`
- `0x180007b58`
- `0x180007f10`
- `0x180008138`
- `0x18000833c`
- `0x180008560`
- `0x180008774`
- `0x180008a4c`
- `0x180008be4`
- `0x18000ce40`
- `0x18000d720`
- `0x18000e250`
- `0x18000ebf0`
- `0x18000f1b0`
- `0x18000fcf0`
- `0x1800100f0`
- `0x180010430`
- `0x180010820`
- `0x180010c70`
- `0x180012950`
- `0x1800136e0`
- `0x180013c10`
- `0x180014330`
- `0x180014900`
- `0x180014b80`
- `0x180014f40`
- `0x1800156d0`
- `0x1800164e0`
- `0x180018090`
- `0x180018200`

## callees

- `0x180004c2c`
- `0x1800065c8`
- `0x18001cc70`

## pseudocode

```c
ULONG McTemplateU0zx_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-38h]
  int v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+4Ch] [rbp-2Ch]
  va_list v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  va_copy(v10, va);
  v11 = 8;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v6);
}

```

## disassembly

```asm
0x1800065c8  mov     [rsp+arg_18], r9
0x1800065cd  sub     rsp, 78h
0x1800065d1  mov     rax, cs:__security_cookie
0x1800065d8  xor     rax, rsp
0x1800065db  mov     [rsp+78h+var_18], rax
0x1800065e0  xor     r9d, r9d
0x1800065e3  test    r8, r8
0x1800065e6  jz      short loc_1800065FF
0x1800065e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800065ec  inc     rax
0x1800065ef  cmp     [r8+rax*2], r9w
0x1800065f4  jnz     short loc_1800065EC
0x1800065f6  lea     eax, ds:2[rax*2]
0x1800065fd  jmp     short loc_180006604
0x1800065ff  mov     eax, 0Ah
0x180006604  mov     [rsp+78h+var_30], eax
0x180006608  lea     rcx, aNull_0; "NULL"
0x18000660f  lea     rax, [rsp+78h+arg_18]
0x180006617  mov     [rsp+78h+var_2C], r9d
0x18000661c  test    r8, r8
0x18000661f  mov     [rsp+78h+var_28], rax
0x180006624  lea     rax, [rsp+78h+var_48]
0x180006629  mov     [rsp+78h+var_20], 8
0x180006632  cmovz   r8, rcx
0x180006636  mov     [rsp+78h+var_58], rax
0x18000663b  mov     r9d, 3
0x180006641  mov     [rsp+78h+var_38], r8
0x180006646  call    McGenEventWrite_EventWriteTransfer
0x18000664b  mov     rcx, [rsp+78h+var_18]
0x180006650  xor     rcx, rsp; StackCookie
0x180006653  call    __security_check_cookie
0x180006658  add     rsp, 78h
0x18000665c  retn
```
