# HvsocketTraceGuidULongError

- ea: `0x140009ec0`
- end: `0x140009f9e`
- name: `HvsocketTraceGuidULongError`
- size: `222`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140004f2c`
- `0x1400059b8`
- `0x14000695c`
- `0x140006be0`
- `0x14001e5ac`
- `0x140020b80`
- `0x140021550`

## callees

- `0x140001008`
- `0x140009ec0`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceGuidULongError(const int *a1, int a2, __int64 a3, __int64 a4, int a5)
{
  NTSTATUS result; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // [rsp+30h] [rbp-41h] BYREF
  int v9; // [rsp+34h] [rbp-3Dh] BYREF
  int v10; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-31h] BYREF
  const int *v12; // [rsp+60h] [rbp-11h]
  int v13; // [rsp+68h] [rbp-9h]
  int v14; // [rsp+6Ch] [rbp-5h]
  int *v15; // [rsp+70h] [rbp-1h]
  __int64 v16; // [rsp+78h] [rbp+7h]
  int *v17; // [rsp+80h] [rbp+Fh]
  __int64 v18; // [rsp+88h] [rbp+17h]
  __int64 v19; // [rsp+90h] [rbp+1Fh]
  __int64 v20; // [rsp+98h] [rbp+27h]
  int *v21; // [rsp+A0h] [rbp+2Fh]
  __int64 v22; // [rsp+A8h] [rbp+37h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( a1 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *((_BYTE *)a1 + v6) );
      v7 = v6 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v7 = 1;
    }
    v13 = v7;
    v15 = &v8;
    v17 = &v9;
    v10 = a5;
    v21 = &v10;
    v12 = a1;
    v8 = a2;
    v14 = 0;
    v16 = 4;
    v9 = a3;
    v18 = 4;
    v19 = a4;
    v20 = 16;
    v22 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_140011987,
             a3,
             a4,
             7u,
             &v11);
  }
  return result;
}

```

## disassembly

```asm
0x140009ec0  push    rbp
0x140009ec2  lea     rbp, [rsp-4Fh]
0x140009ec7  sub     rsp, 0C0h
0x140009ece  mov     rax, cs:__security_cookie
0x140009ed5  xor     rax, rsp
0x140009ed8  mov     [rbp+4Fh+var_10], rax
0x140009edc  mov     eax, cs:dword_140013058
0x140009ee2  cmp     eax, 2
0x140009ee5  jbe     loc_140009F88
0x140009eeb  xor     r10d, r10d
0x140009eee  test    rcx, rcx
0x140009ef1  jz      short loc_140009F04
0x140009ef3  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009ef7  inc     rax
0x140009efa  cmp     [rcx+rax], r10b
0x140009efe  jnz     short loc_140009EF7
0x140009f00  inc     eax
0x140009f02  jmp     short loc_140009F10
0x140009f04  lea     rcx, byte_14000E6BD
0x140009f0b  mov     eax, 1
0x140009f10  mov     [rbp+4Fh+var_58], eax
0x140009f13  lea     rax, [rbp+4Fh+var_90]
0x140009f17  mov     [rbp+4Fh+var_50], rax
0x140009f1b  lea     rax, [rbp+4Fh+var_8C]
0x140009f1f  mov     [rbp+4Fh+var_40], rax
0x140009f23  mov     eax, [rbp+4Fh+arg_20]
0x140009f26  mov     [rbp+4Fh+var_88], eax
0x140009f29  lea     rax, [rbp+4Fh+var_88]
0x140009f2d  mov     [rbp+4Fh+var_20], rax
0x140009f31  lea     rax, [rbp+4Fh+var_80]
0x140009f35  mov     [rbp+4Fh+var_60], rcx
0x140009f39  lea     rcx, dword_140013058; int
0x140009f40  mov     [rbp+4Fh+var_90], edx
0x140009f43  lea     rdx, byte_140011987; int
0x140009f4a  mov     [rsp+0C0h+var_98], rax; __int64
0x140009f4f  mov     [rsp+0C0h+var_A0], 7; ULONG
0x140009f57  mov     [rbp+4Fh+var_54], r10d
0x140009f5b  mov     [rbp+4Fh+var_48], 4
0x140009f63  mov     [rbp+4Fh+var_8C], r8d
0x140009f67  mov     [rbp+4Fh+var_38], 4
0x140009f6f  mov     [rbp+4Fh+var_30], r9
0x140009f73  mov     [rbp+4Fh+var_28], 10h
0x140009f7b  mov     [rbp+4Fh+var_18], 4
0x140009f83  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009f88  mov     rcx, [rbp+4Fh+var_10]
0x140009f8c  xor     rcx, rsp; StackCookie
0x140009f8f  call    __security_check_cookie
0x140009f94  add     rsp, 0C0h
0x140009f9b  pop     rbp
0x140009f9c  retn
```
