# TraceLoggingIoAllocateDriverObjectExtensionFailed

- ea: `0x18001d43c`
- end: `0x18001d4ce`
- name: `TraceLoggingIoAllocateDriverObjectExtensionFailed`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800385f0`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18001d43c`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingIoAllocateDriverObjectExtensionFailed(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  __int64 v4; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      v4 = 304;
      v6 = &v4;
      v7 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002C78B,
               0,
               0,
               3u,
               &v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d43c  sub     rsp, 78h
0x18001d440  mov     rax, cs:__security_cookie
0x18001d447  xor     rax, rsp
0x18001d44a  mov     [rsp+78h+var_10], rax
0x18001d44f  mov     eax, cs:dword_1800310D8
0x18001d455  cmp     eax, 5
0x18001d458  jbe     short loc_18001D4BB
0x18001d45a  mov     rdx, 400000000000h
0x18001d464  lea     rcx, dword_1800310D8
0x18001d46b  call    _tlgKeywordOn
0x18001d470  test    al, al
0x18001d472  jz      short loc_18001D4BB
0x18001d474  lea     rax, [rsp+78h+var_48]
0x18001d479  mov     [rsp+78h+var_48], 130h
0x18001d482  mov     [rsp+78h+var_20], rax
0x18001d487  lea     rdx, byte_18002C78B
0x18001d48e  lea     rax, [rsp+78h+var_40]
0x18001d493  mov     [rsp+78h+var_18], 8
0x18001d49c  mov     [rsp+78h+var_50], rax
0x18001d4a1  lea     rcx, dword_1800310D8
0x18001d4a8  xor     r9d, r9d
0x18001d4ab  mov     [rsp+78h+var_58], 3
0x18001d4b3  xor     r8d, r8d
0x18001d4b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x18001d4bb  mov     rcx, [rsp+78h+var_10]
0x18001d4c0  xor     rcx, rsp; StackCookie
0x18001d4c3  call    __security_check_cookie
0x18001d4c8  add     rsp, 78h
0x18001d4cc  retn
```
