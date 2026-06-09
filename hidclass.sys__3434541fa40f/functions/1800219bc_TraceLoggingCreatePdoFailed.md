# TraceLoggingCreatePdoFailed

- ea: `0x1800219bc`
- end: `0x180021ab9`
- name: `TraceLoggingCreatePdoFailed`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019014`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x1800219bc`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingCreatePdoFailed(__int64 a1, __int64 a2, __int64 a3)
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
               (unsigned __int8 *)&word_18002CAFE,
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
0x1800219bc  push    rbp
0x1800219be  lea     rbp, [rsp-57h]
0x1800219c3  sub     rsp, 0B0h
0x1800219ca  mov     rax, cs:__security_cookie
0x1800219d1  xor     rax, rsp
0x1800219d4  mov     [rbp+57h+var_10], rax
0x1800219d8  mov     eax, cs:dword_1800310D8
0x1800219de  mov     r10d, edx
0x1800219e1  mov     r9, rcx
0x1800219e4  cmp     eax, 5
0x1800219e7  jbe     loc_180021AA3
0x1800219ed  mov     rdx, 400000000000h
0x1800219f7  lea     rcx, dword_1800310D8
0x1800219fe  call    _tlgKeywordOn
0x180021a03  xor     ecx, ecx
0x180021a05  test    al, al
0x180021a07  jz      loc_180021AA3
0x180021a0d  test    r9, r9
0x180021a10  jz      short loc_180021A19
0x180021a12  movzx   eax, word ptr [r9+6Ch]
0x180021a17  jmp     short loc_180021A1B
0x180021a19  mov     eax, ecx
0x180021a1b  mov     [rbp+57h+var_80], ax
0x180021a1f  lea     rax, [rbp+57h+var_80]
0x180021a23  mov     [rbp+57h+var_50], rax
0x180021a27  mov     [rbp+57h+var_48], 2
0x180021a2f  test    r9, r9
0x180021a32  jz      short loc_180021A3B
0x180021a34  movzx   eax, word ptr [r9+6Eh]
0x180021a39  jmp     short loc_180021A3D
0x180021a3b  mov     eax, ecx
0x180021a3d  mov     [rbp+57h+var_7C], ax
0x180021a41  lea     rdx, word_18002CAFE
0x180021a48  lea     rax, [rbp+57h+var_7C]
0x180021a4c  mov     [rbp+57h+var_74], r8d
0x180021a50  mov     [rbp+57h+var_40], rax
0x180021a54  lea     rcx, dword_1800310D8
0x180021a5b  lea     rax, [rbp+57h+var_78]
0x180021a5f  mov     [rbp+57h+var_38], 2
0x180021a67  mov     [rbp+57h+var_30], rax
0x180021a6b  xor     r9d, r9d
0x180021a6e  lea     rax, [rbp+57h+var_74]
0x180021a72  mov     [rbp+57h+var_78], r10d
0x180021a76  mov     [rbp+57h+var_20], rax
0x180021a7a  xor     r8d, r8d
0x180021a7d  lea     rax, [rbp+57h+var_70]
0x180021a81  mov     [rbp+57h+var_28], 4
0x180021a89  mov     [rsp+0B0h+var_88], rax
0x180021a8e  mov     [rsp+0B0h+var_90], 6
0x180021a96  mov     [rbp+57h+var_18], 4
0x180021a9e  call    _tlgWriteTransfer_EtwWriteTransfer
0x180021aa3  mov     rcx, [rbp+57h+var_10]
0x180021aa7  xor     rcx, rsp; StackCookie
0x180021aaa  call    __security_check_cookie
0x180021aaf  add     rsp, 0B0h
0x180021ab6  pop     rbp
0x180021ab7  retn
```
