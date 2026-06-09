# TraceLoggingGetReportIdentifierFailed

- ea: `0x180003090`
- end: `0x180003186`
- name: `TraceLoggingGetReportIdentifierFailed`
- size: `246`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800017d0`
- `0x180002a50`
- `0x180003030`
- `0x1800043a0`
- `0x1800053c0`
- `0x180008a80`

## callees

- `0x180003090`
- `0x18001203c`
- `0x1800142c4`
- `0x180019664`
- `0x180027ba0`

## pseudocode

```c
char __fastcall TraceLoggingGetReportIdentifierFailed(__int64 a1, __int64 a2, __int64 a3)
{
  char result; // al
  const GUID *v4; // r8
  __int64 v5; // r9
  int v6; // r10d
  __int16 v7; // ax
  __int16 v8; // ax
  __int16 v9; // [rsp+30h] [rbp-19h] BYREF
  __int16 v10; // [rsp+34h] [rbp-15h] BYREF
  int v11; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+68h] [rbp+1Fh]
  __int16 *v15; // [rsp+70h] [rbp+27h]
  __int64 v16; // [rsp+78h] [rbp+2Fh]
  int *v17; // [rsp+80h] [rbp+37h]
  __int64 v18; // [rsp+88h] [rbp+3Fh]

  result = IsTraceLoggedRecently(a1, a2, a3, a1);
  if ( !result )
  {
    result = dword_1800310D8;
    if ( (unsigned int)dword_1800310D8 > 5 )
    {
      result = tlgKeywordOn((__int64)&dword_1800310D8, 0x400000000000LL);
      if ( result )
      {
        if ( v5 )
          v7 = *(_WORD *)(v5 + 108);
        else
          v7 = (__int16)v4;
        v9 = v7;
        v13 = &v9;
        v14 = 2;
        if ( v5 )
          v8 = *(_WORD *)(v5 + 110);
        else
          v8 = (__int16)v4;
        v10 = v8;
        v16 = 2;
        v15 = &v10;
        v11 = v6;
        v17 = &v11;
        v18 = 4;
        return tlgWriteTransfer_EtwWriteTransfer(
                 (__int64)&dword_1800310D8,
                 (unsigned __int8 *)byte_18002CC9F,
                 v4,
                 0,
                 5u,
                 &v12);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003090  push    rbp
0x180003092  lea     rbp, [rsp-57h]
0x180003097  sub     rsp, 0A0h
0x18000309e  mov     rax, cs:__security_cookie
0x1800030a5  xor     rax, rsp
0x1800030a8  mov     [rbp+57h+var_10], rax
0x1800030ac  mov     r10d, edx
0x1800030af  mov     r9, rcx
0x1800030b2  call    IsTraceLoggedRecently
0x1800030b7  xor     r8d, r8d
0x1800030ba  test    al, al
0x1800030bc  jnz     loc_180003170
0x1800030c2  mov     eax, cs:dword_1800310D8
0x1800030c8  cmp     eax, 5
0x1800030cb  jbe     loc_180003170
0x1800030d1  mov     rdx, 400000000000h
0x1800030db  lea     rcx, dword_1800310D8
0x1800030e2  call    _tlgKeywordOn
0x1800030e7  test    al, al
0x1800030e9  jz      loc_180003170
0x1800030ef  test    r9, r9
0x1800030f2  jz      short loc_1800030FB
0x1800030f4  movzx   eax, word ptr [r9+6Ch]
0x1800030f9  jmp     short loc_1800030FE
0x1800030fb  mov     eax, r8d
0x1800030fe  mov     [rbp+57h+var_70], ax
0x180003102  lea     rax, [rbp+57h+var_70]
0x180003106  mov     [rbp+57h+var_40], rax
0x18000310a  mov     [rbp+57h+var_38], 2
0x180003112  test    r9, r9
0x180003115  jz      short loc_18000311E
0x180003117  movzx   eax, word ptr [r9+6Eh]
0x18000311c  jmp     short loc_180003121
0x18000311e  mov     eax, r8d
0x180003121  mov     [rbp+57h+var_6C], ax
0x180003125  lea     rdx, byte_18002CC9F
0x18000312c  lea     rax, [rbp+57h+var_6C]
0x180003130  mov     [rbp+57h+var_28], 2
0x180003138  mov     [rbp+57h+var_30], rax
0x18000313c  lea     rcx, dword_1800310D8
0x180003143  lea     rax, [rbp+57h+var_68]
0x180003147  mov     [rbp+57h+var_68], r10d
0x18000314b  mov     [rbp+57h+var_20], rax
0x18000314f  xor     r9d, r9d
0x180003152  lea     rax, [rbp+57h+var_60]
0x180003156  mov     [rbp+57h+var_18], 4
0x18000315e  mov     [rsp+0A0h+var_78], rax
0x180003163  mov     [rsp+0A0h+var_80], 5
0x18000316b  call    _tlgWriteTransfer_EtwWriteTransfer
0x180003170  mov     rcx, [rbp+57h+var_10]
0x180003174  xor     rcx, rsp; StackCookie
0x180003177  call    __security_check_cookie
0x18000317c  add     rsp, 0A0h
0x180003183  pop     rbp
0x180003184  retn
```
