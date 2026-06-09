# TraceLoggingUnreadKeyboardReportsFlushed

- ea: `0x18001ee14`
- end: `0x18001ef11`
- name: `TraceLoggingUnreadKeyboardReportsFlushed`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b140`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18001ee14`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingUnreadKeyboardReportsFlushed(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  int v4; // r8d
  __int64 v5; // r9
  int v6; // r10d
  __int16 v7; // ax
  __int16 v8; // ax
  __int16 v9; // [rsp+30h] [rbp-29h] BYREF
  __int16 v10; // [rsp+34h] [rbp-25h] BYREF
  int v11; // [rsp+38h] [rbp-21h] BYREF
  int v12; // [rsp+3Ch] [rbp-1Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-19h] BYREF
  __int16 *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  __int16 *v16; // [rsp+70h] [rbp+17h]
  __int64 v17; // [rsp+78h] [rbp+1Fh]
  int *v18; // [rsp+80h] [rbp+27h]
  __int64 v19; // [rsp+88h] [rbp+2Fh]
  int *v20; // [rsp+90h] [rbp+37h]
  __int64 v21; // [rsp+98h] [rbp+3Fh]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      if ( v5 )
        v7 = *(_WORD *)(v5 + 108);
      else
        v7 = 0;
      v9 = v7;
      v14 = &v9;
      v15 = 2;
      if ( v5 )
        v8 = *(_WORD *)(v5 + 110);
      else
        v8 = 0;
      v10 = v8;
      v12 = v4;
      v16 = &v10;
      v17 = 2;
      v18 = &v11;
      v11 = v6;
      v20 = &v12;
      v19 = 4;
      v21 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)&unk_18002C918,
               0,
               0,
               6u,
               &v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ee14  push    rbp
0x18001ee16  lea     rbp, [rsp-57h]
0x18001ee1b  sub     rsp, 0B0h
0x18001ee22  mov     rax, cs:__security_cookie
0x18001ee29  xor     rax, rsp
0x18001ee2c  mov     [rbp+57h+var_10], rax
0x18001ee30  mov     eax, cs:dword_1800310D8
0x18001ee36  mov     r10d, edx
0x18001ee39  mov     r9, rcx
0x18001ee3c  cmp     eax, 5
0x18001ee3f  jbe     loc_18001EEFB
0x18001ee45  mov     rdx, 400000000000h
0x18001ee4f  lea     rcx, dword_1800310D8
0x18001ee56  call    _tlgKeywordOn
0x18001ee5b  xor     ecx, ecx
0x18001ee5d  test    al, al
0x18001ee5f  jz      loc_18001EEFB
0x18001ee65  test    r9, r9
0x18001ee68  jz      short loc_18001EE71
0x18001ee6a  movzx   eax, word ptr [r9+6Ch]
0x18001ee6f  jmp     short loc_18001EE73
0x18001ee71  mov     eax, ecx
0x18001ee73  mov     [rbp+57h+var_80], ax
0x18001ee77  lea     rax, [rbp+57h+var_80]
0x18001ee7b  mov     [rbp+57h+var_50], rax
0x18001ee7f  mov     [rbp+57h+var_48], 2
0x18001ee87  test    r9, r9
0x18001ee8a  jz      short loc_18001EE93
0x18001ee8c  movzx   eax, word ptr [r9+6Eh]
0x18001ee91  jmp     short loc_18001EE95
0x18001ee93  mov     eax, ecx
0x18001ee95  mov     [rbp+57h+var_7C], ax
0x18001ee99  lea     rdx, unk_18002C918
0x18001eea0  lea     rax, [rbp+57h+var_7C]
0x18001eea4  mov     [rbp+57h+var_74], r8d
0x18001eea8  mov     [rbp+57h+var_40], rax
0x18001eeac  lea     rcx, dword_1800310D8
0x18001eeb3  lea     rax, [rbp+57h+var_78]
0x18001eeb7  mov     [rbp+57h+var_38], 2
0x18001eebf  mov     [rbp+57h+var_30], rax
0x18001eec3  xor     r9d, r9d
0x18001eec6  lea     rax, [rbp+57h+var_74]
0x18001eeca  mov     [rbp+57h+var_78], r10d
0x18001eece  mov     [rbp+57h+var_20], rax
0x18001eed2  xor     r8d, r8d
0x18001eed5  lea     rax, [rbp+57h+var_70]
0x18001eed9  mov     [rbp+57h+var_28], 4
0x18001eee1  mov     [rsp+0B0h+var_88], rax
0x18001eee6  mov     [rsp+0B0h+var_90], 6
0x18001eeee  mov     [rbp+57h+var_18], 4
0x18001eef6  call    _tlgWriteTransfer_EtwWriteTransfer
0x18001eefb  mov     rcx, [rbp+57h+var_10]
0x18001eeff  xor     rcx, rsp; StackCookie
0x18001ef02  call    __security_check_cookie
0x18001ef07  add     rsp, 0B0h
0x18001ef0e  pop     rbp
0x18001ef0f  retn
```
