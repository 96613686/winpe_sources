# LdrpLogVsmEnclaveLdrCreateEnclaveTelemetry

- ea: `0x18011b3fc`
- end: `0x18011b4f8`
- name: `LdrpLogVsmEnclaveLdrCreateEnclaveTelemetry`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010c2c0`

## callees

- `0x180062600`
- `0x180091808`
- `0x180118624`
- `0x18011b3fc`
- `0x180162810`

## string_xrefs

- `0x18011b478`: `LdrCreateEnclave`

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
    result = (unsigned int)dword_1801C49C8;
    if ( (unsigned int)dword_1801C49C8 > 4 )
    {
      result = tlgKeywordOn(&dword_1801C49C8, 0x400000000000LL);
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
                 (unsigned int)&dword_1801C49C8,
                 (unsigned int)&word_18019BA76,
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
0x18011b3fc  mov     [rsp-8+arg_0], rbx
0x18011b401  mov     [rsp-8+arg_8], rdi
0x18011b406  push    rbp
0x18011b407  lea     rbp, [rsp-57h]
0x18011b40c  sub     rsp, 0A0h
0x18011b413  mov     rax, cs:__security_cookie
0x18011b41a  xor     rax, rsp
0x18011b41d  mov     [rbp+57h+var_10], rax
0x18011b421  mov     rax, gs:60h
0x18011b42a  mov     ebx, edx
0x18011b42c  mov     rdi, rcx
0x18011b42f  cmp     qword ptr [rax+30h], 0
0x18011b434  jz      loc_18011B4D6
0x18011b43a  xor     r9d, r9d
0x18011b43d  lea     rdx, VsmEnclaveTelemetryInitOnce
0x18011b444  xor     r8d, r8d
0x18011b447  lea     rcx, VsmEnclaveTelemetryInitRunOnce
0x18011b44e  call    RtlRunOnceExecuteOnce
0x18011b453  mov     eax, cs:dword_1801C49C8
0x18011b459  cmp     eax, 4
0x18011b45c  jbe     short loc_18011B4D6
0x18011b45e  mov     rdx, 400000000000h
0x18011b468  lea     rcx, dword_1801C49C8
0x18011b46f  call    _tlgKeywordOn
0x18011b474  test    al, al
0x18011b476  jz      short loc_18011B4D6
0x18011b478  lea     rax, aLdrcreateencla_0; "LdrCreateEnclave"
0x18011b47f  mov     [rbp+57h+var_38], 11h
0x18011b487  mov     [rbp+57h+var_40], rax
0x18011b48b  lea     rdx, word_18019BA76
0x18011b492  lea     rax, [rbp+57h+var_68]
0x18011b496  mov     [rbp+57h+var_68], rdi
0x18011b49a  mov     [rbp+57h+var_30], rax
0x18011b49e  lea     rcx, dword_1801C49C8
0x18011b4a5  lea     rax, [rbp+57h+var_70]
0x18011b4a9  mov     [rbp+57h+var_28], 8
0x18011b4b1  mov     [rbp+57h+var_20], rax
0x18011b4b5  lea     rax, [rbp+57h+var_60]
0x18011b4b9  mov     [rsp+0A0h+var_78], rax
0x18011b4be  mov     [rsp+0A0h+var_80], 5
0x18011b4c6  mov     [rbp+57h+var_70], ebx
0x18011b4c9  mov     [rbp+57h+var_18], 4
0x18011b4d1  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18011b4d6  mov     rcx, [rbp+57h+var_10]
0x18011b4da  xor     rcx, rsp; StackCookie
0x18011b4dd  call    __security_check_cookie
0x18011b4e2  lea     r11, [rsp+0A0h+var_s0]
0x18011b4ea  mov     rbx, [r11+10h]
0x18011b4ee  mov     rdi, [r11+18h]
0x18011b4f2  mov     rsp, r11
0x18011b4f5  pop     rbp
0x18011b4f6  retn
```
