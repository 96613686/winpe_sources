# McTemplateU0qs_EtwEventWriteTransfer

- ea: `0x180027dec`
- end: `0x180027e7c`
- name: `McTemplateU0qs_EtwEventWriteTransfer`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006bd0`

## callees

- `0x1800053e0`
- `0x180020250`
- `0x180027dec`

## pseudocode

```c
__int64 __fastcall McTemplateU0qs_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const char *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = "NULL";
  v10 = a4;
  return McGenEventWrite_EtwEventWriteTransfer((__int64)"NULL", (__int64)IdentityInResponsePacket, a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x180027dec  mov     r11, rsp
0x180027def  mov     [r11+18h], r8d
0x180027df3  sub     rsp, 78h
0x180027df7  mov     rax, cs:__security_cookie
0x180027dfe  xor     rax, rsp
0x180027e01  mov     [rsp+78h+var_18], rax
0x180027e06  xor     edx, edx
0x180027e08  mov     qword ptr [r11-30h], 4
0x180027e10  lea     rax, [r11+18h]
0x180027e14  mov     [r11-38h], rax
0x180027e18  test    r9, r9
0x180027e1b  jz      short loc_180027E2E
0x180027e1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027e21  inc     rax
0x180027e24  cmp     [r9+rax], dl
0x180027e28  jnz     short loc_180027E21
0x180027e2a  inc     eax
0x180027e2c  jmp     short loc_180027E33
0x180027e2e  mov     eax, 5
0x180027e33  test    r9, r9
0x180027e36  mov     [rsp+78h+var_20], eax
0x180027e3a  lea     rcx, aNull; "NULL"
0x180027e41  mov     [rsp+78h+var_1C], edx
0x180027e45  cmovz   r9, rcx
0x180027e49  lea     rax, [rsp+78h+var_48]
0x180027e4e  mov     [rsp+78h+var_28], r9
0x180027e53  lea     rdx, IdentityInResponsePacket
0x180027e5a  mov     r9d, 3
0x180027e60  mov     [rsp+78h+var_58], rax
0x180027e65  call    McGenEventWrite_EtwEventWriteTransfer
0x180027e6a  mov     rcx, [rsp+78h+var_18]
0x180027e6f  xor     rcx, rsp; StackCookie
0x180027e72  call    __security_check_cookie
0x180027e77  add     rsp, 78h
0x180027e7b  retn
```
