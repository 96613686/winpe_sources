# LdrpLogVsmEnclaveLdrCreateEnclaveTelemetry

- ea: `0x18011a90c`
- end: `0x18011aa08`
- name: `LdrpLogVsmEnclaveLdrCreateEnclaveTelemetry`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010ad20`

## callees

- `0x180045a00`
- `0x1800853a8`
- `0x180117224`
- `0x18011a90c`
- `0x180162000`

## string_xrefs

- `0x18011a988`: `LdrCreateEnclave`

## pseudocode

```c
__int64 __fastcall LdrpLogVsmEnclaveLdrCreateEnclaveTelemetry(__int64 a1, int a2)
{
  __int64 result; // rax
  int v5; // r8d
  int v6; // r9d
  int v7; // [rsp+30h] [rbp-19h] BYREF
  __int64 v8; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-9h] BYREF
  const char *v10; // [rsp+60h] [rbp+17h]
  __int64 v11; // [rsp+68h] [rbp+1Fh]
  __int64 *v12; // [rsp+70h] [rbp+27h]
  __int64 v13; // [rsp+78h] [rbp+2Fh]
  int *v14; // [rsp+80h] [rbp+37h]
  __int64 v15; // [rsp+88h] [rbp+3Fh]

  result = (__int64)NtCurrentPeb();
  if ( *(_QWORD *)(result + 48) )
  {
    RtlRunOnceExecuteOnce(&VsmEnclaveTelemetryInitRunOnce, VsmEnclaveTelemetryInitOnce, 0, 0);
    result = (unsigned int)dword_1801C4A00;
    if ( (unsigned int)dword_1801C4A00 > 4 )
    {
      result = tlgKeywordOn(&dword_1801C4A00, 0x400000000000LL);
      if ( (_BYTE)result )
      {
        v11 = 17;
        v10 = "LdrCreateEnclave";
        v8 = a1;
        v12 = &v8;
        v13 = 8;
        v14 = &v7;
        v7 = a2;
        v15 = 4;
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 (unsigned int)&dword_1801C4A00,
                 (unsigned int)byte_18019BBD5,
                 v5,
                 v6,
                 5,
                 (__int64)v9);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18011a90c  mov     [rsp-8+arg_0], rbx
0x18011a911  mov     [rsp-8+arg_8], rdi
0x18011a916  push    rbp
0x18011a917  lea     rbp, [rsp-57h]
0x18011a91c  sub     rsp, 0A0h
0x18011a923  mov     rax, cs:__security_cookie
0x18011a92a  xor     rax, rsp
0x18011a92d  mov     [rbp+57h+var_10], rax
0x18011a931  mov     rax, gs:60h
0x18011a93a  mov     ebx, edx
0x18011a93c  mov     rdi, rcx
0x18011a93f  cmp     qword ptr [rax+30h], 0
0x18011a944  jz      loc_18011A9E6
0x18011a94a  xor     r9d, r9d
0x18011a94d  lea     rdx, VsmEnclaveTelemetryInitOnce
0x18011a954  xor     r8d, r8d
0x18011a957  lea     rcx, VsmEnclaveTelemetryInitRunOnce
0x18011a95e  call    RtlRunOnceExecuteOnce
0x18011a963  mov     eax, cs:dword_1801C4A00
0x18011a969  cmp     eax, 4
0x18011a96c  jbe     short loc_18011A9E6
0x18011a96e  mov     rdx, 400000000000h
0x18011a978  lea     rcx, dword_1801C4A00
0x18011a97f  call    _tlgKeywordOn
0x18011a984  test    al, al
0x18011a986  jz      short loc_18011A9E6
0x18011a988  lea     rax, aLdrcreateencla_0; "LdrCreateEnclave"
0x18011a98f  mov     [rbp+57h+var_38], 11h
0x18011a997  mov     [rbp+57h+var_40], rax
0x18011a99b  lea     rdx, byte_18019BBD5
0x18011a9a2  lea     rax, [rbp+57h+var_68]
0x18011a9a6  mov     [rbp+57h+var_68], rdi
0x18011a9aa  mov     [rbp+57h+var_30], rax
0x18011a9ae  lea     rcx, dword_1801C4A00
0x18011a9b5  lea     rax, [rbp+57h+var_70]
0x18011a9b9  mov     [rbp+57h+var_28], 8
0x18011a9c1  mov     [rbp+57h+var_20], rax
0x18011a9c5  lea     rax, [rbp+57h+var_60]
0x18011a9c9  mov     [rsp+0A0h+var_78], rax
0x18011a9ce  mov     [rsp+0A0h+var_80], 5
0x18011a9d6  mov     [rbp+57h+var_70], ebx
0x18011a9d9  mov     [rbp+57h+var_18], 4
0x18011a9e1  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18011a9e6  mov     rcx, [rbp+57h+var_10]
0x18011a9ea  xor     rcx, rsp; StackCookie
0x18011a9ed  call    __security_check_cookie
0x18011a9f2  lea     r11, [rsp+0A0h+var_s0]
0x18011a9fa  mov     rbx, [r11+10h]
0x18011a9fe  mov     rdi, [r11+18h]
0x18011aa02  mov     rsp, r11
0x18011aa05  pop     rbp
0x18011aa06  retn
```
