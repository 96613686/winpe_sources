# SuifTraceLogging::WriteErrorTrace(long,int,char const *,ushort const *)

- ea: `0x140017e70`
- end: `0x140017fb6`
- name: `?WriteErrorTrace@SuifTraceLogging@@CAXJHPEBDPEBG@Z`
- size: `326`
- prototype: `void __fastcall(int, int, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017fbc`

## callees

- `0x14000182c`
- `0x140017e70`
- `0x1400187e0`

## pseudocode

```c
void __fastcall SuifTraceLogging::WriteErrorTrace(int a1, int a2, const char *a3, const unsigned __int16 *a4)
{
  int v4; // r11d
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // [rsp+30h] [rbp-39h] BYREF
  int v9; // [rsp+34h] [rbp-35h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-29h] BYREF
  const unsigned __int16 *v12; // [rsp+60h] [rbp-9h]
  int v13; // [rsp+68h] [rbp-1h]
  int v14; // [rsp+6Ch] [rbp+3h]
  int *v15; // [rsp+70h] [rbp+7h]
  __int64 v16; // [rsp+78h] [rbp+Fh]
  const char *v17; // [rsp+80h] [rbp+17h]
  int v18; // [rsp+88h] [rbp+1Fh]
  int v19; // [rsp+8Ch] [rbp+23h]
  int *v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+98h] [rbp+2Fh]
  __int64 *v22; // [rsp+A0h] [rbp+37h]
  __int64 v23; // [rsp+A8h] [rbp+3Fh]

  v4 = 2;
  if ( (unsigned int)dword_140027000 > 2
    && (qword_140027010 & 0x400000000000LL) != 0
    && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
  {
    v8 = a2;
    v22 = &v10;
    v10 = 0x1000000;
    v20 = &v8;
    v5 = -1;
    v9 = a1;
    v23 = 8;
    v21 = 4;
    if ( a3 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a3[v6] );
      v7 = v6 + 1;
    }
    else
    {
      a3 = (const char *)&word_14001C5D2;
      v7 = 1;
    }
    v18 = v7;
    v15 = &v9;
    v17 = a3;
    v19 = 0;
    v16 = 4;
    if ( a4 )
    {
      do
        ++v5;
      while ( a4[v5] );
      v4 = 2 * v5 + 2;
    }
    else
    {
      a4 = (const unsigned __int16 *)&dword_14001C5D4;
    }
    v12 = a4;
    v14 = 0;
    v13 = v4;
    tlgWriteTransfer_EventWriteTransfer(&dword_140027000, byte_140022FC1, 0, 0, 7, v11);
  }
}

```

## disassembly

```asm
0x140017e70  mov     [rsp-8+arg_0], rbx
0x140017e75  push    rbp
0x140017e76  lea     rbp, [rsp-57h]
0x140017e7b  sub     rsp, 0C0h
0x140017e82  mov     rax, cs:__security_cookie
0x140017e89  xor     rax, rsp
0x140017e8c  mov     [rbp+57h+var_10], rax
0x140017e90  mov     eax, cs:dword_140027000
0x140017e96  mov     r11d, 2
0x140017e9c  cmp     eax, r11d
0x140017e9f  jbe     loc_140017F99
0x140017ea5  mov     r10, cs:qword_140027018
0x140017eac  mov     rbx, 400000000000h
0x140017eb6  mov     rax, cs:qword_140027010
0x140017ebd  test    rbx, rax
0x140017ec0  jz      loc_140017F99
0x140017ec6  mov     rax, r10
0x140017ec9  and     rax, rbx
0x140017ecc  cmp     rax, r10
0x140017ecf  jnz     loc_140017F99
0x140017ed5  lea     rax, [rbp+57h+var_88]
0x140017ed9  mov     [rbp+57h+var_90], edx
0x140017edc  mov     [rbp+57h+var_20], rax
0x140017ee0  xor     edx, edx
0x140017ee2  lea     rax, [rbp+57h+var_90]
0x140017ee6  mov     [rbp+57h+var_88], 1000000h
0x140017eee  mov     [rbp+57h+var_30], rax
0x140017ef2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017ef6  mov     [rbp+57h+var_8C], ecx
0x140017ef9  mov     [rbp+57h+var_18], 8
0x140017f01  mov     [rbp+57h+var_28], 4
0x140017f09  test    r8, r8
0x140017f0c  jz      short loc_140017F1E
0x140017f0e  mov     rcx, rax
0x140017f11  inc     rcx
0x140017f14  cmp     [r8+rcx], dl
0x140017f18  jnz     short loc_140017F11
0x140017f1a  inc     ecx
0x140017f1c  jmp     short loc_140017F2A
0x140017f1e  lea     r8, word_14001C5D2
0x140017f25  mov     ecx, 1
0x140017f2a  mov     [rbp+57h+var_38], ecx
0x140017f2d  lea     rcx, [rbp+57h+var_8C]
0x140017f31  mov     [rbp+57h+var_50], rcx
0x140017f35  mov     [rbp+57h+var_40], r8
0x140017f39  mov     [rbp+57h+var_34], edx
0x140017f3c  mov     [rbp+57h+var_48], 4
0x140017f44  test    r9, r9
0x140017f47  jz      short loc_140017F5D
0x140017f49  inc     rax
0x140017f4c  cmp     [r9+rax*2], dx
0x140017f51  jnz     short loc_140017F49
0x140017f53  lea     r11d, ds:2[rax*2]
0x140017f5b  jmp     short loc_140017F64
0x140017f5d  lea     r9, dword_14001C5D4
0x140017f64  lea     rax, [rbp+57h+var_80]
0x140017f68  mov     [rbp+57h+var_60], r9
0x140017f6c  mov     [rbp+57h+var_54], edx
0x140017f6f  lea     rcx, dword_140027000
0x140017f76  mov     [rsp+0C0h+var_98], rax
0x140017f7b  lea     rdx, byte_140022FC1
0x140017f82  xor     r9d, r9d
0x140017f85  mov     [rsp+0C0h+var_A0], 7
0x140017f8d  xor     r8d, r8d
0x140017f90  mov     [rbp+57h+var_58], r11d
0x140017f94  call    _tlgWriteTransfer_EventWriteTransfer
0x140017f99  mov     rcx, [rbp+57h+var_10]
0x140017f9d  xor     rcx, rsp; StackCookie
0x140017fa0  call    __security_check_cookie
0x140017fa5  mov     rbx, [rsp+0C0h+arg_0]
0x140017fad  add     rsp, 0C0h
0x140017fb4  pop     rbp
0x140017fb5  retn
```
