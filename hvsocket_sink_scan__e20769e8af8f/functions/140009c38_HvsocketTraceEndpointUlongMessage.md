# HvsocketTraceEndpointUlongMessage

- ea: `0x140009c38`
- end: `0x140009cf1`
- name: `HvsocketTraceEndpointUlongMessage`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400034f4`
- `0x1400036d0`
- `0x140003bc8`
- `0x140019b70`

## callees

- `0x140001008`
- `0x140009c38`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointUlongMessage(const int *a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // [rsp+30h] [rbp-19h] BYREF
  __int64 v7; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-9h] BYREF
  const int *v9; // [rsp+60h] [rbp+17h]
  int v10; // [rsp+68h] [rbp+1Fh]
  int v11; // [rsp+6Ch] [rbp+23h]
  __int64 *v12; // [rsp+70h] [rbp+27h]
  __int64 v13; // [rsp+78h] [rbp+2Fh]
  int *v14; // [rsp+80h] [rbp+37h]
  __int64 v15; // [rsp+88h] [rbp+3Fh]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    if ( a1 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_BYTE *)a1 + v4) );
      v5 = v4 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v5 = 1;
    }
    v10 = v5;
    v12 = &v7;
    v14 = &v6;
    v9 = a1;
    v7 = a2;
    v11 = 0;
    v13 = 8;
    v6 = a3;
    v15 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_1400115D3,
             a3,
             0,
             5u,
             &v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009c38  push    rbp
0x140009c3a  lea     rbp, [rsp-57h]
0x140009c3f  sub     rsp, 0A0h
0x140009c46  mov     rax, cs:__security_cookie
0x140009c4d  xor     rax, rsp
0x140009c50  mov     [rbp+57h+var_10], rax
0x140009c54  mov     eax, cs:dword_140013058
0x140009c5a  cmp     eax, 4
0x140009c5d  jbe     short loc_140009CDB
0x140009c5f  xor     r9d, r9d; int
0x140009c62  test    rcx, rcx
0x140009c65  jz      short loc_140009C78
0x140009c67  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009c6b  inc     rax
0x140009c6e  cmp     [rcx+rax], r9b
0x140009c72  jnz     short loc_140009C6B
0x140009c74  inc     eax
0x140009c76  jmp     short loc_140009C84
0x140009c78  lea     rcx, byte_14000E6BD
0x140009c7f  mov     eax, 1
0x140009c84  mov     [rbp+57h+var_38], eax
0x140009c87  lea     rax, [rbp+57h+var_68]
0x140009c8b  mov     [rbp+57h+var_30], rax
0x140009c8f  lea     rax, [rbp+57h+var_70]
0x140009c93  mov     [rbp+57h+var_20], rax
0x140009c97  lea     rax, [rbp+57h+var_60]
0x140009c9b  mov     [rbp+57h+var_40], rcx
0x140009c9f  lea     rcx, dword_140013058; int
0x140009ca6  mov     [rbp+57h+var_68], rdx
0x140009caa  lea     rdx, byte_1400115D3; int
0x140009cb1  mov     [rsp+0A0h+var_78], rax; __int64
0x140009cb6  mov     [rsp+0A0h+var_80], 5; ULONG
0x140009cbe  mov     [rbp+57h+var_34], r9d
0x140009cc2  mov     [rbp+57h+var_28], 8
0x140009cca  mov     [rbp+57h+var_70], r8d
0x140009cce  mov     [rbp+57h+var_18], 4
0x140009cd6  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009cdb  mov     rcx, [rbp+57h+var_10]
0x140009cdf  xor     rcx, rsp; StackCookie
0x140009ce2  call    __security_check_cookie
0x140009ce7  add     rsp, 0A0h
0x140009cee  pop     rbp
0x140009cef  retn
```
