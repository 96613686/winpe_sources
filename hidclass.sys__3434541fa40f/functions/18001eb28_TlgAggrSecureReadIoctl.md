# TlgAggrSecureReadIoctl

- ea: `0x18001eb28`
- end: `0x18001ec29`
- name: `TlgAggrSecureReadIoctl`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ac8`

## callees

- `0x180019664`
- `0x18001eb28`
- `0x1800279f4`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TlgAggrSecureReadIoctl(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int16 v5; // ax
  __int16 v6; // ax
  char v7; // [rsp+30h] [rbp-49h] BYREF
  __int16 v8; // [rsp+34h] [rbp-45h] BYREF
  __int16 v9; // [rsp+38h] [rbp-41h] BYREF
  __int64 v10; // [rsp+40h] [rbp-39h] BYREF
  __int64 v11; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-29h] BYREF
  __int16 *v13; // [rsp+70h] [rbp-9h]
  __int64 v14; // [rsp+78h] [rbp-1h]
  __int16 *v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  char *v17; // [rsp+90h] [rbp+17h]
  __int64 v18; // [rsp+98h] [rbp+1Fh]
  __int64 *v19; // [rsp+A0h] [rbp+27h]
  __int64 v20; // [rsp+A8h] [rbp+2Fh]
  __int64 *v21; // [rsp+B0h] [rbp+37h]
  __int64 v22; // [rsp+B8h] [rbp+3Fh]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a1);
    if ( (_BYTE)result )
    {
      if ( v3 )
        v5 = *(_WORD *)(v3 + 108);
      else
        v5 = 0;
      v8 = v5;
      v13 = &v8;
      v14 = 2;
      if ( v3 )
        v6 = *(_WORD *)(v3 + 110);
      else
        v6 = 0;
      v9 = v6;
      v16 = 2;
      v15 = &v9;
      v17 = &v7;
      v18 = 1;
      v10 = 1;
      v19 = &v10;
      v21 = &v11;
      v7 = v4;
      v20 = 8;
      v11 = 0x2000000;
      v22 = 8;
      return tlgWriteAgg(v2, (unsigned __int8 *)&dword_18002C8C4, v3, v4, &v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001eb28  push    rbp
0x18001eb2a  lea     rbp, [rsp-57h]
0x18001eb2f  sub     rsp, 0D0h
0x18001eb36  mov     rax, cs:__security_cookie
0x18001eb3d  xor     rax, rsp
0x18001eb40  mov     [rbp+57h+var_10], rax
0x18001eb44  mov     eax, cs:dword_1800310D8
0x18001eb4a  mov     r9b, dl
0x18001eb4d  mov     r8, rcx
0x18001eb50  cmp     eax, 5
0x18001eb53  jbe     loc_18001EC13
0x18001eb59  mov     rdx, 400000000000h
0x18001eb63  lea     rcx, dword_1800310D8
0x18001eb6a  call    _tlgKeywordOn
0x18001eb6f  xor     edx, edx
0x18001eb71  test    al, al
0x18001eb73  jz      loc_18001EC13
0x18001eb79  test    r8, r8
0x18001eb7c  jz      short loc_18001EB85
0x18001eb7e  movzx   eax, word ptr [r8+6Ch]
0x18001eb83  jmp     short loc_18001EB87
0x18001eb85  mov     eax, edx
0x18001eb87  mov     [rbp+57h+var_9C], ax
0x18001eb8b  lea     rax, [rbp+57h+var_9C]
0x18001eb8f  mov     [rbp+57h+var_60], rax
0x18001eb93  mov     [rbp+57h+var_58], 2
0x18001eb9b  test    r8, r8
0x18001eb9e  jz      short loc_18001EBA7
0x18001eba0  movzx   eax, word ptr [r8+6Eh]
0x18001eba5  jmp     short loc_18001EBA9
0x18001eba7  mov     eax, edx
0x18001eba9  mov     [rbp+57h+var_98], ax
0x18001ebad  lea     rdx, dword_18002C8C4; int
0x18001ebb4  lea     rax, [rbp+57h+var_98]
0x18001ebb8  mov     [rbp+57h+var_48], 2
0x18001ebc0  mov     [rbp+57h+var_50], rax
0x18001ebc4  lea     rax, [rbp+57h+var_A0]
0x18001ebc8  mov     [rbp+57h+var_40], rax
0x18001ebcc  mov     eax, 1
0x18001ebd1  mov     [rbp+57h+var_38], rax
0x18001ebd5  mov     [rbp+57h+var_90], rax
0x18001ebd9  lea     rax, [rbp+57h+var_90]
0x18001ebdd  mov     [rbp+57h+var_30], rax
0x18001ebe1  lea     rax, [rbp+57h+var_88]
0x18001ebe5  mov     [rbp+57h+var_20], rax
0x18001ebe9  lea     rax, [rbp+57h+var_80]
0x18001ebed  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x18001ebf2  mov     [rbp+57h+var_A0], r9b
0x18001ebf6  mov     [rbp+57h+var_28], 8
0x18001ebfe  mov     [rbp+57h+var_88], 2000000h
0x18001ec06  mov     [rbp+57h+var_18], 8
0x18001ec0e  call    _tlgWriteAgg
0x18001ec13  mov     rcx, [rbp+57h+var_10]
0x18001ec17  xor     rcx, rsp; StackCookie
0x18001ec1a  call    __security_check_cookie
0x18001ec1f  add     rsp, 0D0h
0x18001ec26  pop     rbp
0x18001ec27  retn
```
