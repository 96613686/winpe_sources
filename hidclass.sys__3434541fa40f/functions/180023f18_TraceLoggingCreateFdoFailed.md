# TraceLoggingCreateFdoFailed

- ea: `0x180023f18`
- end: `0x180023fd7`
- name: `TraceLoggingCreateFdoFailed`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003a590`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180023f18`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingCreateFdoFailed(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  unsigned __int16 *v3; // r8
  int v4; // r9d
  int v5; // [rsp+30h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-9h] BYREF
  int *v7; // [rsp+60h] [rbp+17h]
  __int64 v8; // [rsp+68h] [rbp+1Fh]
  _DWORD *v9; // [rsp+70h] [rbp+27h]
  __int64 v10; // [rsp+78h] [rbp+2Fh]
  __int64 v11; // [rsp+80h] [rbp+37h]
  _DWORD v12[2]; // [rsp+88h] [rbp+3Fh] BYREF

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a2);
    if ( (_BYTE)result )
    {
      v5 = v4;
      v7 = &v5;
      v12[1] = 0;
      v9 = v12;
      v11 = *((_QWORD *)v3 + 1);
      v12[0] = *v3;
      v8 = 4;
      v10 = 2;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CEDD,
               0,
               0,
               5u,
               &v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023f18  push    rbp
0x180023f1a  lea     rbp, [rsp-57h]
0x180023f1f  sub     rsp, 0A0h
0x180023f26  mov     rax, cs:__security_cookie
0x180023f2d  xor     rax, rsp
0x180023f30  mov     [rbp+57h+var_10], rax
0x180023f34  mov     eax, cs:dword_1800310D8
0x180023f3a  mov     r8, rdx
0x180023f3d  mov     r9d, ecx
0x180023f40  cmp     eax, 5
0x180023f43  jbe     short loc_180023FC1
0x180023f45  mov     rdx, 400000000000h
0x180023f4f  lea     rcx, dword_1800310D8
0x180023f56  call    _tlgKeywordOn
0x180023f5b  xor     edx, edx
0x180023f5d  test    al, al
0x180023f5f  jz      short loc_180023FC1
0x180023f61  lea     rax, [rbp+57h+var_70]
0x180023f65  mov     [rbp+57h+var_70], r9d
0x180023f69  mov     [rbp+57h+var_40], rax
0x180023f6d  lea     rcx, dword_1800310D8
0x180023f74  lea     rax, [rbp+57h+var_18]
0x180023f78  mov     [rbp+57h+var_14], edx
0x180023f7b  mov     [rbp+57h+var_30], rax
0x180023f7f  lea     rdx, byte_18002CEDD
0x180023f86  mov     rax, [r8+8]
0x180023f8a  xor     r9d, r9d
0x180023f8d  mov     [rbp+57h+var_20], rax
0x180023f91  movzx   eax, word ptr [r8]
0x180023f95  xor     r8d, r8d
0x180023f98  mov     [rbp+57h+var_18], eax
0x180023f9b  lea     rax, [rbp+57h+var_60]
0x180023f9f  mov     [rsp+0A0h+var_78], rax
0x180023fa4  mov     [rsp+0A0h+var_80], 5
0x180023fac  mov     [rbp+57h+var_38], 4
0x180023fb4  mov     [rbp+57h+var_28], 2
0x180023fbc  call    _tlgWriteTransfer_EtwWriteTransfer
0x180023fc1  mov     rcx, [rbp+57h+var_10]
0x180023fc5  xor     rcx, rsp; StackCookie
0x180023fc8  call    __security_check_cookie
0x180023fcd  add     rsp, 0A0h
0x180023fd4  pop     rbp
0x180023fd5  retn
```
