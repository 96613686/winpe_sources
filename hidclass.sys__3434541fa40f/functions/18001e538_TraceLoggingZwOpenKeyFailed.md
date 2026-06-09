# TraceLoggingZwOpenKeyFailed

- ea: `0x18001e538`
- end: `0x18001e5f7`
- name: `TraceLoggingZwOpenKeyFailed`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004227c`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18001e538`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingZwOpenKeyFailed(__int64 a1, __int64 a2)
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
               (unsigned __int8 *)word_18002C7F2,
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
0x18001e538  push    rbp
0x18001e53a  lea     rbp, [rsp-57h]
0x18001e53f  sub     rsp, 0A0h
0x18001e546  mov     rax, cs:__security_cookie
0x18001e54d  xor     rax, rsp
0x18001e550  mov     [rbp+57h+var_10], rax
0x18001e554  mov     eax, cs:dword_1800310D8
0x18001e55a  mov     r8, rdx
0x18001e55d  mov     r9d, ecx
0x18001e560  cmp     eax, 5
0x18001e563  jbe     short loc_18001E5E1
0x18001e565  mov     rdx, 400000000000h
0x18001e56f  lea     rcx, dword_1800310D8
0x18001e576  call    _tlgKeywordOn
0x18001e57b  xor     edx, edx
0x18001e57d  test    al, al
0x18001e57f  jz      short loc_18001E5E1
0x18001e581  lea     rax, [rbp+57h+var_70]
0x18001e585  mov     [rbp+57h+var_70], r9d
0x18001e589  mov     [rbp+57h+var_40], rax
0x18001e58d  lea     rcx, dword_1800310D8
0x18001e594  lea     rax, [rbp+57h+var_18]
0x18001e598  mov     [rbp+57h+var_14], edx
0x18001e59b  mov     [rbp+57h+var_30], rax
0x18001e59f  lea     rdx, word_18002C7F2
0x18001e5a6  mov     rax, [r8+8]
0x18001e5aa  xor     r9d, r9d
0x18001e5ad  mov     [rbp+57h+var_20], rax
0x18001e5b1  movzx   eax, word ptr [r8]
0x18001e5b5  xor     r8d, r8d
0x18001e5b8  mov     [rbp+57h+var_18], eax
0x18001e5bb  lea     rax, [rbp+57h+var_60]
0x18001e5bf  mov     [rsp+0A0h+var_78], rax
0x18001e5c4  mov     [rsp+0A0h+var_80], 5
0x18001e5cc  mov     [rbp+57h+var_38], 4
0x18001e5d4  mov     [rbp+57h+var_28], 2
0x18001e5dc  call    _tlgWriteTransfer_EtwWriteTransfer
0x18001e5e1  mov     rcx, [rbp+57h+var_10]
0x18001e5e5  xor     rcx, rsp; StackCookie
0x18001e5e8  call    __security_check_cookie
0x18001e5ed  add     rsp, 0A0h
0x18001e5f4  pop     rbp
0x18001e5f5  retn
```
