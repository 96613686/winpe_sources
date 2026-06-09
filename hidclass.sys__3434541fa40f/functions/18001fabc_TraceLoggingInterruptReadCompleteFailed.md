# TraceLoggingInterruptReadCompleteFailed

- ea: `0x18001fabc`
- end: `0x18001fb98`
- name: `TraceLoggingInterruptReadCompleteFailed`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800017d0`

## callees

- `0x180013f44`
- `0x1800142c4`
- `0x180019664`
- `0x18001fabc`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingInterruptReadCompleteFailed(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  __int16 v3; // ax
  __int16 v4; // ax
  __int16 v5; // [rsp+30h] [rbp-19h] BYREF
  __int16 v6; // [rsp+34h] [rbp-15h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v8; // [rsp+60h] [rbp+17h]
  __int64 v9; // [rsp+68h] [rbp+1Fh]
  __int16 *v10; // [rsp+70h] [rbp+27h]
  __int64 v11; // [rsp+78h] [rbp+2Fh]
  _BYTE v12[16]; // [rsp+80h] [rbp+37h] BYREF

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a1);
    if ( (_BYTE)result )
    {
      if ( v2 )
        v3 = *(_WORD *)(v2 + 108);
      else
        v3 = 0;
      v5 = v3;
      v8 = &v5;
      v9 = 2;
      if ( v2 )
        v4 = *(_WORD *)(v2 + 110);
      else
        v4 = 0;
      v6 = v4;
      v11 = 2;
      v10 = &v6;
      tlgCreate1Sz_char((__int64)v12, "Pingpong is NULL");
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002C9ED,
               0,
               0,
               5u,
               &v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fabc  push    rbp
0x18001fabe  lea     rbp, [rsp-57h]
0x18001fac3  sub     rsp, 0A0h
0x18001faca  mov     rax, cs:__security_cookie
0x18001fad1  xor     rax, rsp
0x18001fad4  mov     [rbp+57h+var_10], rax
0x18001fad8  mov     eax, cs:dword_1800310D8
0x18001fade  mov     r8, rcx
0x18001fae1  cmp     eax, 5
0x18001fae4  jbe     loc_18001FB82
0x18001faea  mov     rdx, 400000000000h
0x18001faf4  lea     rcx, dword_1800310D8
0x18001fafb  call    _tlgKeywordOn
0x18001fb00  test    al, al
0x18001fb02  jz      short loc_18001FB82
0x18001fb04  test    r8, r8
0x18001fb07  jz      short loc_18001FB10
0x18001fb09  movzx   eax, word ptr [r8+6Ch]
0x18001fb0e  jmp     short loc_18001FB12
0x18001fb10  xor     eax, eax
0x18001fb12  mov     [rbp+57h+var_70], ax
0x18001fb16  lea     rax, [rbp+57h+var_70]
0x18001fb1a  mov     [rbp+57h+var_40], rax
0x18001fb1e  mov     [rbp+57h+var_38], 2
0x18001fb26  test    r8, r8
0x18001fb29  jz      short loc_18001FB32
0x18001fb2b  movzx   eax, word ptr [r8+6Eh]
0x18001fb30  jmp     short loc_18001FB34
0x18001fb32  xor     eax, eax
0x18001fb34  mov     [rbp+57h+var_6C], ax
0x18001fb38  lea     rdx, aPingpongIsNull; "Pingpong is NULL"
0x18001fb3f  lea     rax, [rbp+57h+var_6C]
0x18001fb43  mov     [rbp+57h+var_28], 2
0x18001fb4b  lea     rcx, [rbp+57h+var_20]
0x18001fb4f  mov     [rbp+57h+var_30], rax
0x18001fb53  call    _tlgCreate1Sz_char
0x18001fb58  lea     r8, [rbp+57h+var_60]
0x18001fb5c  xor     r9d, r9d
0x18001fb5f  mov     [rsp+0A0h+var_78], r8
0x18001fb64  lea     rdx, byte_18002C9ED
0x18001fb6b  xor     r8d, r8d
0x18001fb6e  mov     [rsp+0A0h+var_80], 5
0x18001fb76  lea     rcx, dword_1800310D8
0x18001fb7d  call    _tlgWriteTransfer_EtwWriteTransfer
0x18001fb82  mov     rcx, [rbp+57h+var_10]
0x18001fb86  xor     rcx, rsp; StackCookie
0x18001fb89  call    __security_check_cookie
0x18001fb8e  add     rsp, 0A0h
0x18001fb95  pop     rbp
0x18001fb96  retn
```
