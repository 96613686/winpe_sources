# McTemplateU0zq_EtwEventWriteTransfer

- ea: `0x1800143b0`
- end: `0x180014445`
- name: `McTemplateU0zq_EtwEventWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800136b0`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x1800143b0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zq_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
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
  return McGenEventWrite_EtwEventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x1800143b0  mov     [rsp+arg_18], r9d
0x1800143b5  sub     rsp, 78h
0x1800143b9  mov     rax, cs:__security_cookie
0x1800143c0  xor     rax, rsp
0x1800143c3  mov     [rsp+78h+var_18], rax
0x1800143c8  xor     r9d, r9d
0x1800143cb  test    r8, r8
0x1800143ce  jz      short loc_1800143E7
0x1800143d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800143d4  inc     rax
0x1800143d7  cmp     [r8+rax*2], r9w
0x1800143dc  jnz     short loc_1800143D4
0x1800143de  lea     eax, ds:2[rax*2]
0x1800143e5  jmp     short loc_1800143EC
0x1800143e7  mov     eax, 0Ah
0x1800143ec  mov     [rsp+78h+var_30], eax
0x1800143f0  lea     rcx, aNull_0; "NULL"
0x1800143f7  lea     rax, [rsp+78h+arg_18]
0x1800143ff  mov     [rsp+78h+var_2C], r9d
0x180014404  test    r8, r8
0x180014407  mov     [rsp+78h+var_28], rax
0x18001440c  lea     rax, [rsp+78h+var_48]
0x180014411  mov     [rsp+78h+var_20], 4
0x18001441a  cmovz   r8, rcx
0x18001441e  mov     [rsp+78h+var_58], rax
0x180014423  mov     r9d, 3
0x180014429  mov     [rsp+78h+var_38], r8
0x18001442e  call    McGenEventWrite_EtwEventWriteTransfer
0x180014433  mov     rcx, [rsp+78h+var_18]
0x180014438  xor     rcx, rsp; StackCookie
0x18001443b  call    __security_check_cookie
0x180014440  add     rsp, 78h
0x180014444  retn
```
