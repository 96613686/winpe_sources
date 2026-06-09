# TraceLoggingGetCollectionDescFailed

- ea: `0x180021bb0`
- end: `0x180021c99`
- name: `TraceLoggingGetCollectionDescFailed`
- size: `233`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800017d0`
- `0x180002a50`
- `0x1800043a0`
- `0x1800053c0`
- `0x180008760`
- `0x180008a80`
- `0x18000cc90`
- `0x18000ef30`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180021bb0`
- `0x180027ba0`

## pseudocode

```c
char TraceLoggingGetCollectionDescFailed()
{
  char result; // al
  __int64 v1; // r8
  int v2; // r9d
  __int16 v3; // ax
  __int16 v4; // ax
  __int16 v5; // [rsp+30h] [rbp-19h] BYREF
  __int16 v6; // [rsp+34h] [rbp-15h] BYREF
  int v7; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v9; // [rsp+60h] [rbp+17h]
  __int64 v10; // [rsp+68h] [rbp+1Fh]
  __int16 *v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  int *v13; // [rsp+80h] [rbp+37h]
  __int64 v14; // [rsp+88h] [rbp+3Fh]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_1800310D8, 0x400000000000LL);
    if ( result )
    {
      if ( v1 )
        v3 = *(_WORD *)(v1 + 108);
      else
        v3 = 0;
      v5 = v3;
      v9 = &v5;
      v10 = 2;
      if ( v1 )
        v4 = *(_WORD *)(v1 + 110);
      else
        v4 = 0;
      v6 = v4;
      v7 = v2;
      v11 = &v6;
      v12 = 2;
      v13 = &v7;
      v14 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CB79,
               0,
               0,
               5u,
               &v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021bb0  push    rbp
0x180021bb2  lea     rbp, [rsp-57h]
0x180021bb7  sub     rsp, 0A0h
0x180021bbe  mov     rax, cs:__security_cookie
0x180021bc5  xor     rax, rsp
0x180021bc8  mov     [rbp+57h+var_10], rax
0x180021bcc  mov     eax, cs:dword_1800310D8
0x180021bd2  mov     r9d, edx
0x180021bd5  mov     r8, rcx
0x180021bd8  cmp     eax, 5
0x180021bdb  jbe     loc_180021C83
0x180021be1  mov     rdx, 400000000000h
0x180021beb  lea     rcx, dword_1800310D8
0x180021bf2  call    _tlgKeywordOn
0x180021bf7  xor     ecx, ecx
0x180021bf9  test    al, al
0x180021bfb  jz      loc_180021C83
0x180021c01  test    r8, r8
0x180021c04  jz      short loc_180021C0D
0x180021c06  movzx   eax, word ptr [r8+6Ch]
0x180021c0b  jmp     short loc_180021C0F
0x180021c0d  mov     eax, ecx
0x180021c0f  mov     [rbp+57h+var_70], ax
0x180021c13  lea     rax, [rbp+57h+var_70]
0x180021c17  mov     [rbp+57h+var_40], rax
0x180021c1b  mov     [rbp+57h+var_38], 2
0x180021c23  test    r8, r8
0x180021c26  jz      short loc_180021C2F
0x180021c28  movzx   eax, word ptr [r8+6Eh]
0x180021c2d  jmp     short loc_180021C31
0x180021c2f  mov     eax, ecx
0x180021c31  mov     [rbp+57h+var_6C], ax
0x180021c35  lea     rdx, byte_18002CB79
0x180021c3c  lea     rax, [rbp+57h+var_6C]
0x180021c40  mov     [rbp+57h+var_68], r9d
0x180021c44  mov     [rbp+57h+var_30], rax
0x180021c48  lea     rcx, dword_1800310D8
0x180021c4f  lea     rax, [rbp+57h+var_68]
0x180021c53  mov     [rbp+57h+var_28], 2
0x180021c5b  mov     [rbp+57h+var_20], rax
0x180021c5f  xor     r9d, r9d
0x180021c62  lea     rax, [rbp+57h+var_60]
0x180021c66  mov     [rbp+57h+var_18], 4
0x180021c6e  mov     [rsp+0A0h+var_78], rax
0x180021c73  xor     r8d, r8d
0x180021c76  mov     [rsp+0A0h+var_80], 5
0x180021c7e  call    _tlgWriteTransfer_EtwWriteTransfer
0x180021c83  mov     rcx, [rbp+57h+var_10]
0x180021c87  xor     rcx, rsp; StackCookie
0x180021c8a  call    __security_check_cookie
0x180021c8f  add     rsp, 0A0h
0x180021c96  pop     rbp
0x180021c97  retn
```
