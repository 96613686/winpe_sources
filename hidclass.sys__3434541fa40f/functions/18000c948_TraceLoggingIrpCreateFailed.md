# TraceLoggingIrpCreateFailed

- ea: `0x18000c948`
- end: `0x18000ca23`
- name: `TraceLoggingIrpCreateFailed`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b140`

## callees

- `0x18000c948`
- `0x180013f44`
- `0x1800142c4`
- `0x180019664`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingIrpCreateFailed(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  const CHAR *v3; // r9
  __int16 v4; // ax
  __int16 v5; // ax
  __int16 v6; // [rsp+30h] [rbp-19h] BYREF
  __int16 v7; // [rsp+34h] [rbp-15h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v9; // [rsp+60h] [rbp+17h]
  __int64 v10; // [rsp+68h] [rbp+1Fh]
  __int16 *v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  _BYTE v13[16]; // [rsp+80h] [rbp+37h] BYREF

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a1);
    if ( (_BYTE)result )
    {
      if ( v2 )
        v4 = *(_WORD *)(v2 + 108);
      else
        v4 = 0;
      v6 = v4;
      v9 = &v6;
      v10 = 2;
      if ( v2 )
        v5 = *(_WORD *)(v2 + 110);
      else
        v5 = 0;
      v7 = v5;
      v12 = 2;
      v11 = &v7;
      tlgCreate1Sz_char((__int64)v13, v3);
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)word_18002C85A,
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
0x18000c948  push    rbp
0x18000c94a  lea     rbp, [rsp-57h]
0x18000c94f  sub     rsp, 0A0h
0x18000c956  mov     rax, cs:__security_cookie
0x18000c95d  xor     rax, rsp
0x18000c960  mov     [rbp+57h+var_10], rax
0x18000c964  mov     eax, cs:dword_1800310D8
0x18000c96a  mov     r9, rdx
0x18000c96d  mov     r8, rcx
0x18000c970  cmp     eax, 5
0x18000c973  jbe     loc_18000CA0D
0x18000c979  mov     rdx, 400000000000h
0x18000c983  lea     rcx, dword_1800310D8
0x18000c98a  call    _tlgKeywordOn
0x18000c98f  test    al, al
0x18000c991  jz      short loc_18000CA0D
0x18000c993  test    r8, r8
0x18000c996  jz      short loc_18000C99F
0x18000c998  movzx   eax, word ptr [r8+6Ch]
0x18000c99d  jmp     short loc_18000C9A1
0x18000c99f  xor     eax, eax
0x18000c9a1  mov     [rbp+57h+var_70], ax
0x18000c9a5  lea     rax, [rbp+57h+var_70]
0x18000c9a9  mov     [rbp+57h+var_40], rax
0x18000c9ad  mov     [rbp+57h+var_38], 2
0x18000c9b5  test    r8, r8
0x18000c9b8  jz      short loc_18000C9C1
0x18000c9ba  movzx   eax, word ptr [r8+6Eh]
0x18000c9bf  jmp     short loc_18000C9C3
0x18000c9c1  xor     eax, eax
0x18000c9c3  mov     [rbp+57h+var_6C], ax
0x18000c9c7  lea     rcx, [rbp+57h+var_20]
0x18000c9cb  lea     rax, [rbp+57h+var_6C]
0x18000c9cf  mov     [rbp+57h+var_28], 2
0x18000c9d7  mov     rdx, r9
0x18000c9da  mov     [rbp+57h+var_30], rax
0x18000c9de  call    _tlgCreate1Sz_char
0x18000c9e3  lea     r8, [rbp+57h+var_60]
0x18000c9e7  xor     r9d, r9d
0x18000c9ea  mov     [rsp+0A0h+var_78], r8
0x18000c9ef  lea     rdx, word_18002C85A
0x18000c9f6  xor     r8d, r8d
0x18000c9f9  mov     [rsp+0A0h+var_80], 5
0x18000ca01  lea     rcx, dword_1800310D8
0x18000ca08  call    _tlgWriteTransfer_EtwWriteTransfer
0x18000ca0d  mov     rcx, [rbp+57h+var_10]
0x18000ca11  xor     rcx, rsp; StackCookie
0x18000ca14  call    __security_check_cookie
0x18000ca19  add     rsp, 0A0h
0x18000ca20  pop     rbp
0x18000ca21  retn
```
