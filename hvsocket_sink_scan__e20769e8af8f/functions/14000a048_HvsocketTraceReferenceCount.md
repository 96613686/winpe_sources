# HvsocketTraceReferenceCount

- ea: `0x14000a048`
- end: `0x14000a14e`
- name: `HvsocketTraceReferenceCount`
- size: `262`
- prototype: ``
- caller_count: `114`
- callee_count: `3`
- tags: ``

## callers

- `0x140001508`
- `0x140001608`
- `0x140001828`
- `0x140001d04`
- `0x140001e90`
- `0x1400020c4`
- `0x14000227c`
- `0x1400022e4`
- `0x1400023b0`
- `0x1400028d0`
- `0x140002a40`
- `0x140002b78`
- `0x140002d08`
- `0x140002e48`
- `0x140003cec`
- `0x140003ee8`
- `0x140003fe0`
- `0x1400049a0`
- `0x140004f2c`
- `0x1400051b0`
- `0x140005280`
- `0x1400056e0`
- `0x1400058d0`
- `0x1400059b8`
- `0x140005d74`
- `0x140006000`
- `0x140006290`
- `0x140006448`
- `0x140006500`
- `0x1400065fc`
- `0x14000695c`
- `0x140006be0`
- `0x140006de8`
- `0x140007160`
- `0x14000727c`
- `0x1400073d0`
- `0x1400074a4`
- `0x140007794`
- `0x140007b00`
- `0x140008200`
- `0x1400083f0`
- `0x1400085c8`
- `0x140008860`
- `0x140008960`
- `0x140008ab8`
- `0x140008e7c`
- `0x140009060`
- `0x1400093e0`
- `0x14000add0`
- `0x14000af30`

## callees

- `0x140001008`
- `0x14000a048`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceReferenceCount(const int *a1, int a2, __int64 a3, __int64 a4, const int *a5)
{
  NTSTATUS result; // eax
  const int *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // [rsp+30h] [rbp-51h] BYREF
  __int64 v13; // [rsp+38h] [rbp-49h] BYREF
  __int64 v14; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-31h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-11h]
  __int64 v17; // [rsp+78h] [rbp-9h]
  __int64 *v18; // [rsp+80h] [rbp-1h]
  __int64 v19; // [rsp+88h] [rbp+7h]
  const int *v20; // [rsp+90h] [rbp+Fh]
  int v21; // [rsp+98h] [rbp+17h]
  int v22; // [rsp+9Ch] [rbp+1Bh]
  const int *v23; // [rsp+A0h] [rbp+1Fh]
  int v24; // [rsp+A8h] [rbp+27h]
  int v25; // [rsp+ACh] [rbp+2Bh]
  int *v26; // [rsp+B0h] [rbp+2Fh]
  __int64 v27; // [rsp+B8h] [rbp+37h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 5 )
  {
    v7 = a5;
    v16 = &v13;
    v14 = a4;
    v18 = &v14;
    v8 = -1;
    v13 = a3;
    v17 = 8;
    v9 = 1;
    v19 = 8;
    if ( a5 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_BYTE *)a5 + v10) );
      v11 = (unsigned int)(v10 + 1);
    }
    else
    {
      v7 = &byte_14000E6BD;
      v11 = 1;
    }
    v20 = v7;
    v21 = v11;
    v22 = 0;
    if ( a1 )
    {
      do
        ++v8;
      while ( *((_BYTE *)a1 + v8) );
      v9 = (unsigned int)(v8 + 1);
    }
    else
    {
      a1 = &byte_14000E6BD;
    }
    v23 = a1;
    v26 = &v12;
    v24 = v9;
    v25 = 0;
    v12 = a2;
    v27 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_140011657,
             v11,
             v9,
             7u,
             &v15);
  }
  return result;
}

```

## disassembly

```asm
0x14000a048  push    rbp
0x14000a04a  lea     rbp, [rsp-4Fh]
0x14000a04f  sub     rsp, 0D0h
0x14000a056  mov     rax, cs:__security_cookie
0x14000a05d  xor     rax, rsp
0x14000a060  mov     [rbp+4Fh+var_10], rax
0x14000a064  mov     eax, cs:dword_140013058
0x14000a06a  mov     r10d, edx
0x14000a06d  cmp     eax, 5
0x14000a070  jbe     loc_14000A138
0x14000a076  mov     rdx, [rbp+4Fh+arg_20]
0x14000a07a  lea     rax, [rbp+4Fh+var_98]
0x14000a07e  mov     [rbp+4Fh+var_60], rax
0x14000a082  xor     r11d, r11d
0x14000a085  lea     rax, [rbp+4Fh+var_90]
0x14000a089  mov     [rbp+4Fh+var_90], r9
0x14000a08d  mov     [rbp+4Fh+var_50], rax
0x14000a091  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a095  mov     [rbp+4Fh+var_98], r8
0x14000a099  mov     [rbp+4Fh+var_58], 8
0x14000a0a1  lea     r9d, [r11+1]; int
0x14000a0a5  mov     [rbp+4Fh+var_48], 8
0x14000a0ad  test    rdx, rdx
0x14000a0b0  jz      short loc_14000A0C3
0x14000a0b2  mov     r8, rax
0x14000a0b5  inc     r8
0x14000a0b8  cmp     [rdx+r8], r11b
0x14000a0bc  jnz     short loc_14000A0B5
0x14000a0be  inc     r8d
0x14000a0c1  jmp     short loc_14000A0CD
0x14000a0c3  lea     rdx, byte_14000E6BD
0x14000a0ca  mov     r8d, r9d; int
0x14000a0cd  mov     [rbp+4Fh+var_40], rdx
0x14000a0d1  mov     [rbp+4Fh+var_38], r8d
0x14000a0d5  mov     [rbp+4Fh+var_34], r11d
0x14000a0d9  test    rcx, rcx
0x14000a0dc  jz      short loc_14000A0ED
0x14000a0de  inc     rax
0x14000a0e1  cmp     [rcx+rax], r11b
0x14000a0e5  jnz     short loc_14000A0DE
0x14000a0e7  lea     r9d, [rax+1]
0x14000a0eb  jmp     short loc_14000A0F4
0x14000a0ed  lea     rcx, byte_14000E6BD
0x14000a0f4  lea     rax, [rbp+4Fh+var_A0]
0x14000a0f8  mov     [rbp+4Fh+var_30], rcx
0x14000a0fc  mov     [rbp+4Fh+var_20], rax
0x14000a100  lea     rdx, byte_140011657; int
0x14000a107  lea     rax, [rbp+4Fh+var_80]
0x14000a10b  mov     [rbp+4Fh+var_28], r9d
0x14000a10f  mov     [rsp+0D0h+var_A8], rax; __int64
0x14000a114  lea     rcx, dword_140013058; int
0x14000a11b  mov     [rsp+0D0h+var_B0], 7; ULONG
0x14000a123  mov     [rbp+4Fh+var_24], r11d
0x14000a127  mov     [rbp+4Fh+var_A0], r10d
0x14000a12b  mov     [rbp+4Fh+var_18], 4
0x14000a133  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a138  mov     rcx, [rbp+4Fh+var_10]
0x14000a13c  xor     rcx, rsp; StackCookie
0x14000a13f  call    __security_check_cookie
0x14000a144  add     rsp, 0D0h
0x14000a14b  pop     rbp
0x14000a14c  retn
```
