# PoWdiLogVetoTelemetry

- ea: `0x1800039b0`
- end: `0x180003aad`
- name: `PoWdiLogVetoTelemetry`
- size: `253`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d30`
- `0x180003eb0`
- `0x180004240`

## callees

- `0x18000113c`
- `0x1800039b0`
- `0x180004930`

## pseudocode

```c
__int64 __fastcall PoWdiLogVetoTelemetry(__int64 a1, int a2, __int64 a3, const WCHAR *a4)
{
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // eax
  int v7; // [rsp+30h] [rbp-29h] BYREF
  int v8; // [rsp+34h] [rbp-25h] BYREF
  int v9; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-19h] BYREF
  int *v11; // [rsp+60h] [rbp+7h]
  __int64 v12; // [rsp+68h] [rbp+Fh]
  int *v13; // [rsp+70h] [rbp+17h]
  __int64 v14; // [rsp+78h] [rbp+1Fh]
  int *v15; // [rsp+80h] [rbp+27h]
  __int64 v16; // [rsp+88h] [rbp+2Fh]
  const WCHAR *v17; // [rsp+90h] [rbp+37h]
  int v18; // [rsp+98h] [rbp+3Fh]
  int v19; // [rsp+9Ch] [rbp+43h]

  result = (unsigned int)dword_1800091A8;
  if ( (unsigned int)dword_1800091A8 > 5 )
  {
    result = qword_1800091B8;
    if ( (qword_1800091B8 & 0x400000000000LL) != 0 )
    {
      result = qword_1800091C0 & 0x400000000000LL;
      if ( (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
      {
        v7 = a1;
        v11 = &v7;
        v12 = 4;
        v13 = &v8;
        v15 = &v9;
        v8 = a2;
        v14 = 4;
        v9 = a3;
        v16 = 4;
        if ( a4 )
        {
          v5 = -1;
          do
            ++v5;
          while ( a4[v5] );
          v6 = 2 * v5 + 2;
        }
        else
        {
          a4 = &SourceString;
          v6 = 2;
        }
        v18 = v6;
        v17 = a4;
        v19 = 0;
        return tlgWriteTransfer_EtwEventWriteTransfer(a1, byte_180006F05, a3, (__int64)a4, 6, (__int64)v10);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800039b0  push    rbp
0x1800039b2  lea     rbp, [rsp-57h]
0x1800039b7  sub     rsp, 0B0h
0x1800039be  mov     rax, cs:__security_cookie
0x1800039c5  xor     rax, rsp
0x1800039c8  mov     [rbp+57h+var_10], rax
0x1800039cc  mov     eax, cs:dword_1800091A8
0x1800039d2  cmp     eax, 5
0x1800039d5  jbe     loc_180003A98
0x1800039db  mov     r10, cs:qword_1800091C0
0x1800039e2  mov     r11, 400000000000h
0x1800039ec  mov     rax, cs:qword_1800091B8
0x1800039f3  test    r11, rax
0x1800039f6  jz      loc_180003A98
0x1800039fc  mov     rax, r10
0x1800039ff  and     rax, r11
0x180003a02  cmp     rax, r10
0x180003a05  jnz     loc_180003A98
0x180003a0b  lea     rax, [rbp+57h+var_80]
0x180003a0f  mov     [rbp+57h+var_80], ecx
0x180003a12  mov     [rbp+57h+var_50], rax
0x180003a16  xor     r10d, r10d
0x180003a19  mov     [rbp+57h+var_48], 4
0x180003a21  lea     rax, [rbp+57h+var_7C]
0x180003a25  mov     [rbp+57h+var_40], rax
0x180003a29  lea     rax, [rbp+57h+var_78]
0x180003a2d  mov     [rbp+57h+var_30], rax
0x180003a31  mov     [rbp+57h+var_7C], edx
0x180003a34  mov     [rbp+57h+var_38], 4
0x180003a3c  mov     [rbp+57h+var_78], r8d
0x180003a40  mov     [rbp+57h+var_28], 4
0x180003a48  test    r9, r9
0x180003a4b  jz      short loc_180003A64
0x180003a4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a51  inc     rax
0x180003a54  cmp     [r9+rax*2], r10w
0x180003a59  jnz     short loc_180003A51
0x180003a5b  lea     eax, ds:2[rax*2]
0x180003a62  jmp     short loc_180003A70
0x180003a64  lea     r9, SourceString
0x180003a6b  mov     eax, 2
0x180003a70  mov     [rbp+57h+var_18], eax
0x180003a73  lea     rdx, byte_180006F05
0x180003a7a  lea     rax, [rbp+57h+var_70]
0x180003a7e  mov     [rbp+57h+var_20], r9
0x180003a82  mov     [rsp+0B0h+var_88], rax
0x180003a87  mov     [rsp+0B0h+var_90], 6
0x180003a8f  mov     [rbp+57h+var_14], r10d
0x180003a93  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180003a98  mov     rcx, [rbp+57h+var_10]
0x180003a9c  xor     rcx, rsp; StackCookie
0x180003a9f  call    __security_check_cookie
0x180003aa4  add     rsp, 0B0h
0x180003aab  pop     rbp
0x180003aac  retn
```
