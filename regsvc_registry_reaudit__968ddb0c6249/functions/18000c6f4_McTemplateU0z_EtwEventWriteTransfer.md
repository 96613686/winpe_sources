# McTemplateU0z_EtwEventWriteTransfer

- ea: `0x18000c6f4`
- end: `0x18000c76e`
- name: `McTemplateU0z_EtwEventWriteTransfer`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b008`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x18000c6f4`

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
  return McGenEventWrite_EtwEventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2, (__int64)v6);
}

```

## disassembly

```asm
0x18000c6f4  sub     rsp, 68h
0x18000c6f8  mov     rax, cs:__security_cookie
0x18000c6ff  xor     rax, rsp
0x18000c702  mov     [rsp+68h+var_18], rax
0x18000c707  xor     r9d, r9d
0x18000c70a  test    r8, r8
0x18000c70d  jz      short loc_18000C726
0x18000c70f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c713  inc     rax
0x18000c716  cmp     [r8+rax*2], r9w
0x18000c71b  jnz     short loc_18000C713
0x18000c71d  lea     eax, ds:2[rax*2]
0x18000c724  jmp     short loc_18000C72B
0x18000c726  mov     eax, 0Ah
0x18000c72b  test    r8, r8
0x18000c72e  mov     [rsp+68h+var_20], eax
0x18000c732  lea     rcx, aNull_0; "NULL"
0x18000c739  mov     [rsp+68h+var_1C], r9d
0x18000c73e  cmovz   r8, rcx
0x18000c742  lea     rax, [rsp+68h+var_38]
0x18000c747  mov     r9d, 2
0x18000c74d  mov     [rsp+68h+var_28], r8
0x18000c752  mov     [rsp+68h+var_48], rax
0x18000c757  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c75c  mov     rcx, [rsp+68h+var_18]
0x18000c761  xor     rcx, rsp; StackCookie
0x18000c764  call    __security_check_cookie
0x18000c769  add     rsp, 68h
0x18000c76d  retn
```
