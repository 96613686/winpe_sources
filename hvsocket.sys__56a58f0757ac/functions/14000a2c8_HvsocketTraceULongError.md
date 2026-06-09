# HvsocketTraceULongError

- ea: `0x14000a2c8`
- end: `0x14000a398`
- name: `HvsocketTraceULongError`
- size: `208`
- prototype: `NTSTATUS __fastcall(const int *, int, __int64, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140018008`
- `0x1400189d0`
- `0x1400193ec`
- `0x140019b70`
- `0x14001b578`
- `0x14001b74c`
- `0x1400213d0`
- `0x140021550`

## callees

- `0x140001008`
- `0x14000a2c8`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceULongError(const int *a1, int a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // [rsp+30h] [rbp-29h] BYREF
  int v8; // [rsp+34h] [rbp-25h] BYREF
  int v9; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-19h] BYREF
  const int *v11; // [rsp+60h] [rbp+7h]
  int v12; // [rsp+68h] [rbp+Fh]
  int v13; // [rsp+6Ch] [rbp+13h]
  int *v14; // [rsp+70h] [rbp+17h]
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  int *v16; // [rsp+80h] [rbp+27h]
  __int64 v17; // [rsp+88h] [rbp+2Fh]
  int *v18; // [rsp+90h] [rbp+37h]
  __int64 v19; // [rsp+98h] [rbp+3Fh]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_BYTE *)a1 + v5) );
      v6 = v5 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v6 = 1;
    }
    v12 = v6;
    v14 = &v7;
    v16 = &v8;
    v18 = &v9;
    v11 = a1;
    v7 = a2;
    v13 = 0;
    v15 = 4;
    v8 = a3;
    v17 = 4;
    v9 = a4;
    v19 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&dword_140011824,
             a3,
             a4,
             6u,
             &v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000a2c8  push    rbp
0x14000a2ca  lea     rbp, [rsp-57h]
0x14000a2cf  sub     rsp, 0B0h
0x14000a2d6  mov     rax, cs:__security_cookie
0x14000a2dd  xor     rax, rsp
0x14000a2e0  mov     [rbp+57h+var_10], rax
0x14000a2e4  mov     eax, cs:dword_140013058
0x14000a2ea  cmp     eax, 2
0x14000a2ed  jbe     loc_14000A382
0x14000a2f3  xor     r10d, r10d
0x14000a2f6  test    rcx, rcx
0x14000a2f9  jz      short loc_14000A30C
0x14000a2fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a2ff  inc     rax
0x14000a302  cmp     [rcx+rax], r10b
0x14000a306  jnz     short loc_14000A2FF
0x14000a308  inc     eax
0x14000a30a  jmp     short loc_14000A318
0x14000a30c  lea     rcx, byte_14000E6BD
0x14000a313  mov     eax, 1
0x14000a318  mov     [rbp+57h+var_48], eax
0x14000a31b  lea     rax, [rbp+57h+var_80]
0x14000a31f  mov     [rbp+57h+var_40], rax
0x14000a323  lea     rax, [rbp+57h+var_7C]
0x14000a327  mov     [rbp+57h+var_30], rax
0x14000a32b  lea     rax, [rbp+57h+var_78]
0x14000a32f  mov     [rbp+57h+var_20], rax
0x14000a333  lea     rax, [rbp+57h+var_70]
0x14000a337  mov     [rbp+57h+var_50], rcx
0x14000a33b  lea     rcx, dword_140013058; int
0x14000a342  mov     [rbp+57h+var_80], edx
0x14000a345  lea     rdx, dword_140011824; int
0x14000a34c  mov     [rsp+0B0h+var_88], rax; __int64
0x14000a351  mov     [rsp+0B0h+var_90], 6; ULONG
0x14000a359  mov     [rbp+57h+var_44], r10d
0x14000a35d  mov     [rbp+57h+var_38], 4
0x14000a365  mov     [rbp+57h+var_7C], r8d
0x14000a369  mov     [rbp+57h+var_28], 4
0x14000a371  mov     [rbp+57h+var_78], r9d
0x14000a375  mov     [rbp+57h+var_18], 4
0x14000a37d  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a382  mov     rcx, [rbp+57h+var_10]
0x14000a386  xor     rcx, rsp; StackCookie
0x14000a389  call    __security_check_cookie
0x14000a38e  add     rsp, 0B0h
0x14000a395  pop     rbp
0x14000a396  retn
```
