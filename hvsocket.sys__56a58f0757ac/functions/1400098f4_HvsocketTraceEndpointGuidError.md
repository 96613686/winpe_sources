# HvsocketTraceEndpointGuidError

- ea: `0x1400098f4`
- end: `0x1400099d4`
- name: `HvsocketTraceEndpointGuidError`
- size: `224`
- prototype: `NTSTATUS __fastcall(const int *, int, __int64, __int64, __int64)`
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x1400023b0`
- `0x1400065fc`
- `0x1400093e0`
- `0x14000a7c0`
- `0x14000b390`
- `0x14000b520`
- `0x14001cc80`
- `0x14001cf60`
- `0x14001e1c0`
- `0x14001e5ac`
- `0x140020b80`
- `0x140021550`
- `0x140024b90`
- `0x140024c3c`
- `0x140024d90`
- `0x140024edc`
- `0x1400256b0`
- `0x140025ab0`
- `0x140025b20`
- `0x140025c64`
- `0x1400263d0`

## callees

- `0x140001008`
- `0x1400098f4`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointGuidError(const int *a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS result; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // [rsp+30h] [rbp-41h] BYREF
  int v9; // [rsp+34h] [rbp-3Dh] BYREF
  __int64 v10; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-31h] BYREF
  const int *v12; // [rsp+60h] [rbp-11h]
  int v13; // [rsp+68h] [rbp-9h]
  int v14; // [rsp+6Ch] [rbp-5h]
  int *v15; // [rsp+70h] [rbp-1h]
  __int64 v16; // [rsp+78h] [rbp+7h]
  int *v17; // [rsp+80h] [rbp+Fh]
  __int64 v18; // [rsp+88h] [rbp+17h]
  __int64 *v19; // [rsp+90h] [rbp+1Fh]
  __int64 v20; // [rsp+98h] [rbp+27h]
  __int64 v21; // [rsp+A0h] [rbp+2Fh]
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
    v19 = &v10;
    v21 = a5;
    v12 = a1;
    v8 = a2;
    v14 = 0;
    v16 = 4;
    v9 = a3;
    v18 = 4;
    v10 = a4;
    v20 = 8;
    v22 = 16;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_14001197B,
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
0x1400098f4  push    rbp
0x1400098f6  lea     rbp, [rsp-4Fh]
0x1400098fb  sub     rsp, 0C0h
0x140009902  mov     rax, cs:__security_cookie
0x140009909  xor     rax, rsp
0x14000990c  mov     [rbp+4Fh+var_10], rax
0x140009910  mov     eax, cs:dword_140013058
0x140009916  cmp     eax, 2
0x140009919  jbe     loc_1400099BE
0x14000991f  xor     r10d, r10d
0x140009922  test    rcx, rcx
0x140009925  jz      short loc_140009938
0x140009927  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000992b  inc     rax
0x14000992e  cmp     [rcx+rax], r10b
0x140009932  jnz     short loc_14000992B
0x140009934  inc     eax
0x140009936  jmp     short loc_140009944
0x140009938  lea     rcx, byte_14000E6BD
0x14000993f  mov     eax, 1
0x140009944  mov     [rbp+4Fh+var_58], eax
0x140009947  lea     rax, [rbp+4Fh+var_90]
0x14000994b  mov     [rbp+4Fh+var_50], rax
0x14000994f  lea     rax, [rbp+4Fh+var_8C]
0x140009953  mov     [rbp+4Fh+var_40], rax
0x140009957  lea     rax, [rbp+4Fh+var_88]
0x14000995b  mov     [rbp+4Fh+var_30], rax
0x14000995f  mov     rax, [rbp+4Fh+arg_20]
0x140009963  mov     [rbp+4Fh+var_20], rax
0x140009967  lea     rax, [rbp+4Fh+var_80]
0x14000996b  mov     [rbp+4Fh+var_60], rcx
0x14000996f  lea     rcx, dword_140013058; int
0x140009976  mov     [rbp+4Fh+var_90], edx
0x140009979  lea     rdx, byte_14001197B; int
0x140009980  mov     [rsp+0C0h+var_98], rax; __int64
0x140009985  mov     [rsp+0C0h+var_A0], 7; ULONG
0x14000998d  mov     [rbp+4Fh+var_54], r10d
0x140009991  mov     [rbp+4Fh+var_48], 4
0x140009999  mov     [rbp+4Fh+var_8C], r8d
0x14000999d  mov     [rbp+4Fh+var_38], 4
0x1400099a5  mov     [rbp+4Fh+var_88], r9
0x1400099a9  mov     [rbp+4Fh+var_28], 8
0x1400099b1  mov     [rbp+4Fh+var_18], 10h
0x1400099b9  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400099be  mov     rcx, [rbp+4Fh+var_10]
0x1400099c2  xor     rcx, rsp; StackCookie
0x1400099c5  call    __security_check_cookie
0x1400099ca  add     rsp, 0C0h
0x1400099d1  pop     rbp
0x1400099d2  retn
```
