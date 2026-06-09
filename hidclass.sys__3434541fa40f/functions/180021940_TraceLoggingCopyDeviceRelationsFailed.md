# TraceLoggingCopyDeviceRelationsFailed

- ea: `0x180021940`
- end: `0x1800219b6`
- name: `TraceLoggingCopyDeviceRelationsFailed`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003fa00`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180021940`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingCopyDeviceRelationsFailed(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)&dword_18002CA54,
               0,
               0,
               2u,
               &v4);
  }
  return result;
}

```

## disassembly

```asm
0x180021940  sub     rsp, 68h
0x180021944  mov     rax, cs:__security_cookie
0x18002194b  xor     rax, rsp
0x18002194e  mov     [rsp+68h+var_18], rax
0x180021953  mov     eax, cs:dword_1800310D8
0x180021959  cmp     eax, 5
0x18002195c  jbe     short loc_1800219A3
0x18002195e  mov     rdx, 400000000000h
0x180021968  lea     rcx, dword_1800310D8
0x18002196f  call    _tlgKeywordOn
0x180021974  test    al, al
0x180021976  jz      short loc_1800219A3
0x180021978  lea     rax, [rsp+68h+var_38]
0x18002197d  xor     r9d, r9d
0x180021980  mov     [rsp+68h+var_40], rax
0x180021985  lea     rdx, dword_18002CA54
0x18002198c  xor     r8d, r8d
0x18002198f  mov     [rsp+68h+var_48], 2
0x180021997  lea     rcx, dword_1800310D8
0x18002199e  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800219a3  mov     rcx, [rsp+68h+var_18]
0x1800219a8  xor     rcx, rsp; StackCookie
0x1800219ab  call    __security_check_cookie
0x1800219b0  add     rsp, 68h
0x1800219b4  retn
```
