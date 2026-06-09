# McTemplateU0z_EtwEventWriteTransfer

- ea: `0x180001d04`
- end: `0x180001d86`
- name: `McTemplateU0z_EtwEventWriteTransfer`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c884`
- `0x1800108f0`
- `0x18001189c`
- `0x180011b98`
- `0x180014070`
- `0x180014590`
- `0x180021150`
- `0x1800216a4`

## callees

- `0x180001d04`
- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0z_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

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
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, (__int64)a3, 2, (__int64)v6);
}

```

## disassembly

```asm
0x180001d04  sub     rsp, 68h
0x180001d08  mov     rax, cs:__security_cookie
0x180001d0f  xor     rax, rsp
0x180001d12  mov     [rsp+68h+var_18], rax
0x180001d17  xor     r9d, r9d
0x180001d1a  test    r8, r8
0x180001d1d  jz      short loc_180001D7F
0x180001d1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001d23  inc     rax
0x180001d26  cmp     [r8+rax*2], r9w
0x180001d2b  jnz     short loc_180001D23
0x180001d2d  lea     eax, ds:2[rax*2]
0x180001d34  test    r8, r8
0x180001d37  mov     [rsp+68h+var_20], eax
0x180001d3b  lea     rcx, aNull_0; "NULL"
0x180001d42  mov     [rsp+68h+var_1C], r9d
0x180001d47  cmovz   r8, rcx
0x180001d4b  lea     rax, [rsp+68h+var_38]
0x180001d50  lea     rcx, Dhcpv6_Context
0x180001d57  mov     [rsp+68h+var_28], r8
0x180001d5c  mov     r9d, 2
0x180001d62  mov     [rsp+68h+var_48], rax
0x180001d67  call    McGenEventWrite_EtwEventWriteTransfer
0x180001d6c  mov     rcx, [rsp+68h+var_18]
0x180001d71  xor     rcx, rsp; StackCookie
0x180001d74  call    __security_check_cookie
0x180001d79  add     rsp, 68h
0x180001d7d  retn
0x180001d7f  mov     eax, 0Ah
0x180001d84  jmp     short loc_180001D34
```
