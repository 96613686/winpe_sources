# TraceLoggingStrSafeOverflow

- ea: `0x18002204c`
- end: `0x1800220f6`
- name: `TraceLoggingStrSafeOverflow`
- size: `170`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180019d28`
- `0x18003a1c0`
- `0x18003a590`
- `0x18003da1c`
- `0x18003fbbc`

## callees

- `0x180013f44`
- `0x1800142c4`
- `0x180019664`
- `0x18002204c`
- `0x180027ba0`

## pseudocode

```c
char TraceLoggingStrSafeOverflow()
{
  char result; // al
  const CHAR *v1; // r9
  int v2; // r8d
  int v3; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v5[16]; // [rsp+60h] [rbp-38h] BYREF
  int *v6; // [rsp+70h] [rbp-28h]
  __int64 v7; // [rsp+78h] [rbp-20h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_1800310D8, 0x400000000000LL);
    if ( result )
    {
      tlgCreate1Sz_char((__int64)v5, v1);
      v3 = v2;
      v7 = 4;
      v6 = &v3;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CB43,
               0,
               0,
               4u,
               &v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002204c  sub     rsp, 98h
0x180022053  mov     rax, cs:__security_cookie
0x18002205a  xor     rax, rsp
0x18002205d  mov     [rsp+98h+var_18], rax
0x180022065  mov     eax, cs:dword_1800310D8
0x18002206b  mov     r8d, edx
0x18002206e  mov     r9, rcx
0x180022071  cmp     eax, 5
0x180022074  jbe     short loc_1800220DD
0x180022076  mov     rdx, 400000000000h
0x180022080  lea     rcx, dword_1800310D8
0x180022087  call    _tlgKeywordOn
0x18002208c  test    al, al
0x18002208e  jz      short loc_1800220DD
0x180022090  mov     rdx, r9
0x180022093  lea     rcx, [rsp+98h+var_38]
0x180022098  call    _tlgCreate1Sz_char
0x18002209d  mov     edx, 4
0x1800220a2  mov     [rsp+98h+var_68], r8d
0x1800220a7  lea     rax, [rsp+98h+var_68]
0x1800220ac  mov     [rsp+98h+var_20], rdx
0x1800220b1  mov     [rsp+98h+var_28], rax
0x1800220b6  lea     rcx, dword_1800310D8
0x1800220bd  lea     rax, [rsp+98h+var_58]
0x1800220c2  xor     r9d, r9d
0x1800220c5  mov     [rsp+98h+var_70], rax
0x1800220ca  xor     r8d, r8d
0x1800220cd  mov     [rsp+98h+var_78], edx
0x1800220d1  lea     rdx, byte_18002CB43
0x1800220d8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800220dd  mov     rcx, [rsp+98h+var_18]
0x1800220e5  xor     rcx, rsp; StackCookie
0x1800220e8  call    __security_check_cookie
0x1800220ed  add     rsp, 98h
0x1800220f4  retn
```
