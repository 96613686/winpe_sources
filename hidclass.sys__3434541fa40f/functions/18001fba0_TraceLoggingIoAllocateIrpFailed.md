# TraceLoggingIoAllocateIrpFailed

- ea: `0x18001fba0`
- end: `0x18001fc31`
- name: `TraceLoggingIoAllocateIrpFailed`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c924`
- `0x180025f64`
- `0x18003a590`
- `0x18003d8fc`
- `0x18003fca8`
- `0x18004215c`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18001fba0`
- `0x180027ba0`

## pseudocode

```c
char TraceLoggingIoAllocateIrpFailed()
{
  char result; // al
  int v1; // r8d
  int v2; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+38h] [rbp-40h] BYREF
  int *v4; // [rsp+58h] [rbp-20h]
  __int64 v5; // [rsp+60h] [rbp-18h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_1800310D8, 0x400000000000LL);
    if ( result )
    {
      v2 = v1;
      v4 = &v2;
      v5 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002C9B7,
               0,
               0,
               3u,
               &v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fba0  sub     rsp, 78h
0x18001fba4  mov     rax, cs:__security_cookie
0x18001fbab  xor     rax, rsp
0x18001fbae  mov     [rsp+78h+var_10], rax
0x18001fbb3  mov     eax, cs:dword_1800310D8
0x18001fbb9  mov     r8d, ecx
0x18001fbbc  cmp     eax, 5
0x18001fbbf  jbe     short loc_18001FC1E
0x18001fbc1  mov     rdx, 400000000000h
0x18001fbcb  lea     rcx, dword_1800310D8
0x18001fbd2  call    _tlgKeywordOn
0x18001fbd7  test    al, al
0x18001fbd9  jz      short loc_18001FC1E
0x18001fbdb  lea     rax, [rsp+78h+var_48]
0x18001fbe0  mov     [rsp+78h+var_48], r8d
0x18001fbe5  mov     [rsp+78h+var_20], rax
0x18001fbea  lea     rdx, byte_18002C9B7
0x18001fbf1  lea     rax, [rsp+78h+var_40]
0x18001fbf6  mov     [rsp+78h+var_18], 4
0x18001fbff  mov     [rsp+78h+var_50], rax
0x18001fc04  lea     rcx, dword_1800310D8
0x18001fc0b  xor     r9d, r9d
0x18001fc0e  mov     [rsp+78h+var_58], 3
0x18001fc16  xor     r8d, r8d
0x18001fc19  call    _tlgWriteTransfer_EtwWriteTransfer
0x18001fc1e  mov     rcx, [rsp+78h+var_10]
0x18001fc23  xor     rcx, rsp; StackCookie
0x18001fc26  call    __security_check_cookie
0x18001fc2b  add     rsp, 78h
0x18001fc2f  retn
```
