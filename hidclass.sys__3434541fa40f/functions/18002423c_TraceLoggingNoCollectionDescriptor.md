# TraceLoggingNoCollectionDescriptor

- ea: `0x18002423c`
- end: `0x180024325`
- name: `TraceLoggingNoCollectionDescriptor`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b0d0`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18002423c`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingNoCollectionDescriptor(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  int v3; // r9d
  __int16 v4; // ax
  __int16 v5; // ax
  __int16 v6; // [rsp+30h] [rbp-19h] BYREF
  __int16 v7; // [rsp+34h] [rbp-15h] BYREF
  int v8; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v10; // [rsp+60h] [rbp+17h]
  __int64 v11; // [rsp+68h] [rbp+1Fh]
  __int16 *v12; // [rsp+70h] [rbp+27h]
  __int64 v13; // [rsp+78h] [rbp+2Fh]
  int *v14; // [rsp+80h] [rbp+37h]
  __int64 v15; // [rsp+88h] [rbp+3Fh]

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
      v10 = &v6;
      v11 = 2;
      if ( v2 )
        v5 = *(_WORD *)(v2 + 110);
      else
        v5 = 0;
      v7 = v5;
      v8 = v3;
      v12 = &v7;
      v13 = 2;
      v14 = &v8;
      v15 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CDBB,
               0,
               0,
               5u,
               &v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002423c  push    rbp
0x18002423e  lea     rbp, [rsp-57h]
0x180024243  sub     rsp, 0A0h
0x18002424a  mov     rax, cs:__security_cookie
0x180024251  xor     rax, rsp
0x180024254  mov     [rbp+57h+var_10], rax
0x180024258  mov     eax, cs:dword_1800310D8
0x18002425e  mov     r9d, edx
0x180024261  mov     r8, rcx
0x180024264  cmp     eax, 5
0x180024267  jbe     loc_18002430F
0x18002426d  mov     rdx, 400000000000h
0x180024277  lea     rcx, dword_1800310D8
0x18002427e  call    _tlgKeywordOn
0x180024283  xor     ecx, ecx
0x180024285  test    al, al
0x180024287  jz      loc_18002430F
0x18002428d  test    r8, r8
0x180024290  jz      short loc_180024299
0x180024292  movzx   eax, word ptr [r8+6Ch]
0x180024297  jmp     short loc_18002429B
0x180024299  mov     eax, ecx
0x18002429b  mov     [rbp+57h+var_70], ax
0x18002429f  lea     rax, [rbp+57h+var_70]
0x1800242a3  mov     [rbp+57h+var_40], rax
0x1800242a7  mov     [rbp+57h+var_38], 2
0x1800242af  test    r8, r8
0x1800242b2  jz      short loc_1800242BB
0x1800242b4  movzx   eax, word ptr [r8+6Eh]
0x1800242b9  jmp     short loc_1800242BD
0x1800242bb  mov     eax, ecx
0x1800242bd  mov     [rbp+57h+var_6C], ax
0x1800242c1  lea     rdx, byte_18002CDBB
0x1800242c8  lea     rax, [rbp+57h+var_6C]
0x1800242cc  mov     [rbp+57h+var_68], r9d
0x1800242d0  mov     [rbp+57h+var_30], rax
0x1800242d4  lea     rcx, dword_1800310D8
0x1800242db  lea     rax, [rbp+57h+var_68]
0x1800242df  mov     [rbp+57h+var_28], 2
0x1800242e7  mov     [rbp+57h+var_20], rax
0x1800242eb  xor     r9d, r9d
0x1800242ee  lea     rax, [rbp+57h+var_60]
0x1800242f2  mov     [rbp+57h+var_18], 4
0x1800242fa  mov     [rsp+0A0h+var_78], rax
0x1800242ff  xor     r8d, r8d
0x180024302  mov     [rsp+0A0h+var_80], 5
0x18002430a  call    _tlgWriteTransfer_EtwWriteTransfer
0x18002430f  mov     rcx, [rbp+57h+var_10]
0x180024313  xor     rcx, rsp; StackCookie
0x180024316  call    __security_check_cookie
0x18002431b  add     rsp, 0A0h
0x180024322  pop     rbp
0x180024323  retn
```
