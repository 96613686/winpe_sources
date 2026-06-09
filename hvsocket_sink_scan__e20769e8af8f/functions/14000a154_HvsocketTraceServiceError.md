# HvsocketTraceServiceError

- ea: `0x14000a154`
- end: `0x14000a22c`
- name: `HvsocketTraceServiceError`
- size: `216`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140004f2c`
- `0x14000695c`
- `0x140008ab8`
- `0x1400093e0`
- `0x1400095a0`
- `0x14001a148`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001daa0`
- `0x14001e5ac`
- `0x14001f5e4`
- `0x140020b80`
- `0x140021550`
- `0x140021da4`
- `0x140021f5c`
- `0x1400220a8`
- `0x1400222b0`
- `0x140022634`
- `0x140024f30`
- `0x140025d30`

## callees

- `0x140001008`
- `0x14000a154`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceServiceError(const int *a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS result; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // [rsp+30h] [rbp-41h] BYREF
  int v9; // [rsp+34h] [rbp-3Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-31h] BYREF
  const int *v11; // [rsp+60h] [rbp-11h]
  int v12; // [rsp+68h] [rbp-9h]
  int v13; // [rsp+6Ch] [rbp-5h]
  int *v14; // [rsp+70h] [rbp-1h]
  __int64 v15; // [rsp+78h] [rbp+7h]
  int *v16; // [rsp+80h] [rbp+Fh]
  __int64 v17; // [rsp+88h] [rbp+17h]
  __int64 v18; // [rsp+90h] [rbp+1Fh]
  __int64 v19; // [rsp+98h] [rbp+27h]
  __int64 v20; // [rsp+A0h] [rbp+2Fh]
  __int64 v21; // [rsp+A8h] [rbp+37h]

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
    v12 = v7;
    v14 = &v8;
    v16 = &v9;
    v20 = a5;
    v11 = a1;
    v8 = a2;
    v13 = 0;
    v15 = 4;
    v9 = a3;
    v17 = 4;
    v18 = a4;
    v19 = 16;
    v21 = 16;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&dword_1400116E4,
             a3,
             a4,
             7u,
             &v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000a154  push    rbp
0x14000a156  lea     rbp, [rsp-4Fh]
0x14000a15b  sub     rsp, 0C0h
0x14000a162  mov     rax, cs:__security_cookie
0x14000a169  xor     rax, rsp
0x14000a16c  mov     [rbp+4Fh+var_10], rax
0x14000a170  mov     eax, cs:dword_140013058
0x14000a176  cmp     eax, 2
0x14000a179  jbe     loc_14000A216
0x14000a17f  xor     r10d, r10d
0x14000a182  test    rcx, rcx
0x14000a185  jz      short loc_14000A198
0x14000a187  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a18b  inc     rax
0x14000a18e  cmp     [rcx+rax], r10b
0x14000a192  jnz     short loc_14000A18B
0x14000a194  inc     eax
0x14000a196  jmp     short loc_14000A1A4
0x14000a198  lea     rcx, byte_14000E6BD
0x14000a19f  mov     eax, 1
0x14000a1a4  mov     [rbp+4Fh+var_58], eax
0x14000a1a7  lea     rax, [rbp+4Fh+var_90]
0x14000a1ab  mov     [rbp+4Fh+var_50], rax
0x14000a1af  lea     rax, [rbp+4Fh+var_8C]
0x14000a1b3  mov     [rbp+4Fh+var_40], rax
0x14000a1b7  mov     rax, [rbp+4Fh+arg_20]
0x14000a1bb  mov     [rbp+4Fh+var_20], rax
0x14000a1bf  lea     rax, [rbp+4Fh+var_80]
0x14000a1c3  mov     [rbp+4Fh+var_60], rcx
0x14000a1c7  lea     rcx, dword_140013058; int
0x14000a1ce  mov     [rbp+4Fh+var_90], edx
0x14000a1d1  lea     rdx, dword_1400116E4; int
0x14000a1d8  mov     [rsp+0C0h+var_98], rax; __int64
0x14000a1dd  mov     [rsp+0C0h+var_A0], 7; ULONG
0x14000a1e5  mov     [rbp+4Fh+var_54], r10d
0x14000a1e9  mov     [rbp+4Fh+var_48], 4
0x14000a1f1  mov     [rbp+4Fh+var_8C], r8d
0x14000a1f5  mov     [rbp+4Fh+var_38], 4
0x14000a1fd  mov     [rbp+4Fh+var_30], r9
0x14000a201  mov     [rbp+4Fh+var_28], 10h
0x14000a209  mov     [rbp+4Fh+var_18], 10h
0x14000a211  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a216  mov     rcx, [rbp+4Fh+var_10]
0x14000a21a  xor     rcx, rsp; StackCookie
0x14000a21d  call    __security_check_cookie
0x14000a222  add     rsp, 0C0h
0x14000a229  pop     rbp
0x14000a22a  retn
```
