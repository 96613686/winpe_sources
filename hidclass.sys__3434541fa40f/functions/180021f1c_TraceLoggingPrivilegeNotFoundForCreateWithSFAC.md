# TraceLoggingPrivilegeNotFoundForCreateWithSFAC

- ea: `0x180021f1c`
- end: `0x180022046`
- name: `TraceLoggingPrivilegeNotFoundForCreateWithSFAC`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000c2e0`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180021f1c`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingPrivilegeNotFoundForCreateWithSFAC(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  NTSTATUS result; // eax
  __int16 v6; // r8
  char v7; // r9
  __int64 v8; // r10
  __int16 v9; // r11
  __int16 v10; // ax
  __int16 v11; // ax
  char v12; // [rsp+30h] [rbp-61h] BYREF
  __int16 v13; // [rsp+34h] [rbp-5Dh] BYREF
  __int16 v14; // [rsp+38h] [rbp-59h] BYREF
  __int16 v15; // [rsp+3Ch] [rbp-55h] BYREF
  __int16 v16; // [rsp+40h] [rbp-51h] BYREF
  int v17; // [rsp+44h] [rbp-4Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-41h] BYREF
  __int16 *v19; // [rsp+70h] [rbp-21h]
  __int64 v20; // [rsp+78h] [rbp-19h]
  __int16 *v21; // [rsp+80h] [rbp-11h]
  __int64 v22; // [rsp+88h] [rbp-9h]
  __int16 *v23; // [rsp+90h] [rbp-1h]
  __int64 v24; // [rsp+98h] [rbp+7h]
  __int16 *v25; // [rsp+A0h] [rbp+Fh]
  __int64 v26; // [rsp+A8h] [rbp+17h]
  char *v27; // [rsp+B0h] [rbp+1Fh]
  __int64 v28; // [rsp+B8h] [rbp+27h]
  int *v29; // [rsp+C0h] [rbp+2Fh]
  __int64 v30; // [rsp+C8h] [rbp+37h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      if ( v8 )
        v10 = *(_WORD *)(v8 + 108);
      else
        v10 = 0;
      v13 = v10;
      v19 = &v13;
      v20 = 2;
      if ( v8 )
        v11 = *(_WORD *)(v8 + 110);
      else
        v11 = 0;
      v14 = v11;
      v16 = v6;
      v21 = &v14;
      v12 = v7;
      v23 = &v15;
      v22 = 2;
      v25 = &v16;
      v15 = v9;
      v27 = &v12;
      v17 = a5;
      v29 = &v17;
      v24 = 2;
      v26 = 2;
      v28 = 1;
      v30 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CC31,
               0,
               0,
               8u,
               &v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021f1c  push    rbp
0x180021f1e  lea     rbp, [rsp-4Fh]
0x180021f23  sub     rsp, 0E0h
0x180021f2a  mov     rax, cs:__security_cookie
0x180021f31  xor     rax, rsp
0x180021f34  mov     [rbp+4Fh+var_10], rax
0x180021f38  mov     eax, cs:dword_1800310D8
0x180021f3e  movzx   r11d, dx
0x180021f42  mov     r10, rcx
0x180021f45  cmp     eax, 5
0x180021f48  jbe     loc_180022030
0x180021f4e  mov     rdx, 400000000000h
0x180021f58  lea     rcx, dword_1800310D8
0x180021f5f  call    _tlgKeywordOn
0x180021f64  xor     ecx, ecx
0x180021f66  test    al, al
0x180021f68  jz      loc_180022030
0x180021f6e  test    r10, r10
0x180021f71  jz      short loc_180021F7A
0x180021f73  movzx   eax, word ptr [r10+6Ch]
0x180021f78  jmp     short loc_180021F7C
0x180021f7a  mov     eax, ecx
0x180021f7c  mov     [rbp+4Fh+var_AC], ax
0x180021f80  lea     rax, [rbp+4Fh+var_AC]
0x180021f84  mov     [rbp+4Fh+var_70], rax
0x180021f88  mov     [rbp+4Fh+var_68], 2
0x180021f90  test    r10, r10
0x180021f93  jz      short loc_180021F9C
0x180021f95  movzx   eax, word ptr [r10+6Eh]
0x180021f9a  jmp     short loc_180021F9E
0x180021f9c  mov     eax, ecx
0x180021f9e  mov     [rbp+4Fh+var_A8], ax
0x180021fa2  lea     rdx, byte_18002CC31
0x180021fa9  lea     rax, [rbp+4Fh+var_A8]
0x180021fad  mov     [rbp+4Fh+var_A0], r8w
0x180021fb2  mov     [rbp+4Fh+var_60], rax
0x180021fb6  lea     rcx, dword_1800310D8
0x180021fbd  lea     rax, [rbp+4Fh+var_A4]
0x180021fc1  mov     [rbp+4Fh+var_B0], r9b
0x180021fc5  mov     [rbp+4Fh+var_50], rax
0x180021fc9  xor     r9d, r9d
0x180021fcc  lea     rax, [rbp+4Fh+var_A0]
0x180021fd0  mov     [rbp+4Fh+var_58], 2
0x180021fd8  mov     [rbp+4Fh+var_40], rax
0x180021fdc  xor     r8d, r8d
0x180021fdf  lea     rax, [rbp+4Fh+var_B0]
0x180021fe3  mov     [rbp+4Fh+var_A4], r11w
0x180021fe8  mov     [rbp+4Fh+var_30], rax
0x180021fec  mov     eax, [rbp+4Fh+arg_20]
0x180021fef  mov     [rbp+4Fh+var_9C], eax
0x180021ff2  lea     rax, [rbp+4Fh+var_9C]
0x180021ff6  mov     [rbp+4Fh+var_20], rax
0x180021ffa  lea     rax, [rbp+4Fh+var_90]
0x180021ffe  mov     [rsp+0E0h+var_B8], rax
0x180022003  mov     [rsp+0E0h+var_C0], 8
0x18002200b  mov     [rbp+4Fh+var_48], 2
0x180022013  mov     [rbp+4Fh+var_38], 2
0x18002201b  mov     [rbp+4Fh+var_28], 1
0x180022023  mov     [rbp+4Fh+var_18], 4
0x18002202b  call    _tlgWriteTransfer_EtwWriteTransfer
0x180022030  mov     rcx, [rbp+4Fh+var_10]
0x180022034  xor     rcx, rsp; StackCookie
0x180022037  call    __security_check_cookie
0x18002203c  add     rsp, 0E0h
0x180022043  pop     rbp
0x180022044  retn
```
