# TraceLoggingGetClassCollectionFailed

- ea: `0x180021ac0`
- end: `0x180021ba9`
- name: `TraceLoggingGetClassCollectionFailed`
- size: `233`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800017d0`
- `0x180002a50`
- `0x1800053c0`
- `0x18000c250`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180021ac0`
- `0x180027ba0`

## pseudocode

```c
char TraceLoggingGetClassCollectionFailed()
{
  char result; // al
  __int64 v1; // r8
  int v2; // r9d
  __int16 v3; // ax
  __int16 v4; // ax
  __int16 v5; // [rsp+30h] [rbp-19h] BYREF
  __int16 v6; // [rsp+34h] [rbp-15h] BYREF
  int v7; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-9h] BYREF
  __int16 *v9; // [rsp+60h] [rbp+17h]
  __int64 v10; // [rsp+68h] [rbp+1Fh]
  __int16 *v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  int *v13; // [rsp+80h] [rbp+37h]
  __int64 v14; // [rsp+88h] [rbp+3Fh]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_1800310D8, 0x400000000000LL);
    if ( result )
    {
      if ( v1 )
        v3 = *(_WORD *)(v1 + 108);
      else
        v3 = 0;
      v5 = v3;
      v9 = &v5;
      v10 = 2;
      if ( v1 )
        v4 = *(_WORD *)(v1 + 110);
      else
        v4 = 0;
      v6 = v4;
      v7 = v2;
      v11 = &v6;
      v12 = 2;
      v13 = &v7;
      v14 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)&word_18002CA7E,
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
0x180021ac0  push    rbp
0x180021ac2  lea     rbp, [rsp-57h]
0x180021ac7  sub     rsp, 0A0h
0x180021ace  mov     rax, cs:__security_cookie
0x180021ad5  xor     rax, rsp
0x180021ad8  mov     [rbp+57h+var_10], rax
0x180021adc  mov     eax, cs:dword_1800310D8
0x180021ae2  mov     r9d, edx
0x180021ae5  mov     r8, rcx
0x180021ae8  cmp     eax, 5
0x180021aeb  jbe     loc_180021B93
0x180021af1  mov     rdx, 400000000000h
0x180021afb  lea     rcx, dword_1800310D8
0x180021b02  call    _tlgKeywordOn
0x180021b07  xor     ecx, ecx
0x180021b09  test    al, al
0x180021b0b  jz      loc_180021B93
0x180021b11  test    r8, r8
0x180021b14  jz      short loc_180021B1D
0x180021b16  movzx   eax, word ptr [r8+6Ch]
0x180021b1b  jmp     short loc_180021B1F
0x180021b1d  mov     eax, ecx
0x180021b1f  mov     [rbp+57h+var_70], ax
0x180021b23  lea     rax, [rbp+57h+var_70]
0x180021b27  mov     [rbp+57h+var_40], rax
0x180021b2b  mov     [rbp+57h+var_38], 2
0x180021b33  test    r8, r8
0x180021b36  jz      short loc_180021B3F
0x180021b38  movzx   eax, word ptr [r8+6Eh]
0x180021b3d  jmp     short loc_180021B41
0x180021b3f  mov     eax, ecx
0x180021b41  mov     [rbp+57h+var_6C], ax
0x180021b45  lea     rdx, word_18002CA7E
0x180021b4c  lea     rax, [rbp+57h+var_6C]
0x180021b50  mov     [rbp+57h+var_68], r9d
0x180021b54  mov     [rbp+57h+var_30], rax
0x180021b58  lea     rcx, dword_1800310D8
0x180021b5f  lea     rax, [rbp+57h+var_68]
0x180021b63  mov     [rbp+57h+var_28], 2
0x180021b6b  mov     [rbp+57h+var_20], rax
0x180021b6f  xor     r9d, r9d
0x180021b72  lea     rax, [rbp+57h+var_60]
0x180021b76  mov     [rbp+57h+var_18], 4
0x180021b7e  mov     [rsp+0A0h+var_78], rax
0x180021b83  xor     r8d, r8d
0x180021b86  mov     [rsp+0A0h+var_80], 5
0x180021b8e  call    _tlgWriteTransfer_EtwWriteTransfer
0x180021b93  mov     rcx, [rbp+57h+var_10]
0x180021b97  xor     rcx, rsp; StackCookie
0x180021b9a  call    __security_check_cookie
0x180021b9f  add     rsp, 0A0h
0x180021ba6  pop     rbp
0x180021ba7  retn
```
