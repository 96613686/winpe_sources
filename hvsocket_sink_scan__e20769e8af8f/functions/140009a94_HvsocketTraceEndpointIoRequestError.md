# HvsocketTraceEndpointIoRequestError

- ea: `0x140009a94`
- end: `0x140009b7c`
- name: `HvsocketTraceEndpointIoRequestError`
- size: `232`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1400063c0`
- `0x140007b00`
- `0x14000aa50`
- `0x14000ac30`
- `0x14000b2a0`
- `0x14000b740`

## callees

- `0x140001008`
- `0x140009a94`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointIoRequestError(const int *a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS result; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // [rsp+30h] [rbp-51h] BYREF
  int v9; // [rsp+34h] [rbp-4Dh] BYREF
  __int64 v10; // [rsp+38h] [rbp-49h] BYREF
  __int64 v11; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-31h] BYREF
  const int *v13; // [rsp+70h] [rbp-11h]
  int v14; // [rsp+78h] [rbp-9h]
  int v15; // [rsp+7Ch] [rbp-5h]
  int *v16; // [rsp+80h] [rbp-1h]
  __int64 v17; // [rsp+88h] [rbp+7h]
  int *v18; // [rsp+90h] [rbp+Fh]
  __int64 v19; // [rsp+98h] [rbp+17h]
  __int64 *v20; // [rsp+A0h] [rbp+1Fh]
  __int64 v21; // [rsp+A8h] [rbp+27h]
  __int64 *v22; // [rsp+B0h] [rbp+2Fh]
  __int64 v23; // [rsp+B8h] [rbp+37h]

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
    v14 = v7;
    v16 = &v8;
    v18 = &v9;
    v20 = &v10;
    v11 = a5;
    v22 = &v11;
    v13 = a1;
    v8 = a2;
    v15 = 0;
    v17 = 4;
    v9 = a3;
    v19 = 4;
    v10 = a4;
    v21 = 8;
    v23 = 8;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_14001180D,
             a3,
             a4,
             7u,
             &v12);
  }
  return result;
}

```

## disassembly

```asm
0x140009a94  push    rbp
0x140009a96  lea     rbp, [rsp-4Fh]
0x140009a9b  sub     rsp, 0D0h
0x140009aa2  mov     rax, cs:__security_cookie
0x140009aa9  xor     rax, rsp
0x140009aac  mov     [rbp+4Fh+var_10], rax
0x140009ab0  mov     eax, cs:dword_140013058
0x140009ab6  cmp     eax, 2
0x140009ab9  jbe     loc_140009B66
0x140009abf  xor     r10d, r10d
0x140009ac2  test    rcx, rcx
0x140009ac5  jz      short loc_140009AD8
0x140009ac7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009acb  inc     rax
0x140009ace  cmp     [rcx+rax], r10b
0x140009ad2  jnz     short loc_140009ACB
0x140009ad4  inc     eax
0x140009ad6  jmp     short loc_140009AE4
0x140009ad8  lea     rcx, byte_14000E6BD
0x140009adf  mov     eax, 1
0x140009ae4  mov     [rbp+4Fh+var_58], eax
0x140009ae7  lea     rax, [rbp+4Fh+var_A0]
0x140009aeb  mov     [rbp+4Fh+var_50], rax
0x140009aef  lea     rax, [rbp+4Fh+var_9C]
0x140009af3  mov     [rbp+4Fh+var_40], rax
0x140009af7  lea     rax, [rbp+4Fh+var_98]
0x140009afb  mov     [rbp+4Fh+var_30], rax
0x140009aff  mov     rax, [rbp+4Fh+arg_20]
0x140009b03  mov     [rbp+4Fh+var_90], rax
0x140009b07  lea     rax, [rbp+4Fh+var_90]
0x140009b0b  mov     [rbp+4Fh+var_20], rax
0x140009b0f  lea     rax, [rbp+4Fh+var_80]
0x140009b13  mov     [rbp+4Fh+var_60], rcx
0x140009b17  lea     rcx, dword_140013058; int
0x140009b1e  mov     [rbp+4Fh+var_A0], edx
0x140009b21  lea     rdx, byte_14001180D; int
0x140009b28  mov     [rsp+0D0h+var_A8], rax; __int64
0x140009b2d  mov     [rsp+0D0h+var_B0], 7; ULONG
0x140009b35  mov     [rbp+4Fh+var_54], r10d
0x140009b39  mov     [rbp+4Fh+var_48], 4
0x140009b41  mov     [rbp+4Fh+var_9C], r8d
0x140009b45  mov     [rbp+4Fh+var_38], 4
0x140009b4d  mov     [rbp+4Fh+var_98], r9
0x140009b51  mov     [rbp+4Fh+var_28], 8
0x140009b59  mov     [rbp+4Fh+var_18], 8
0x140009b61  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009b66  mov     rcx, [rbp+4Fh+var_10]
0x140009b6a  xor     rcx, rsp; StackCookie
0x140009b6d  call    __security_check_cookie
0x140009b72  add     rsp, 0D0h
0x140009b79  pop     rbp
0x140009b7a  retn
```
