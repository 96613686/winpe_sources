# HvsocketTraceGuidError

- ea: `0x140009df0`
- end: `0x140009eb8`
- name: `HvsocketTraceGuidError`
- size: `200`
- prototype: `NTSTATUS __fastcall(const int *, int, __int64, __int64)`
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x140001828`
- `0x14000a408`
- `0x140018350`
- `0x140018bc8`
- `0x140018cf0`
- `0x140018e20`
- `0x14001a148`
- `0x14001a790`
- `0x14001a9f0`
- `0x14001ac90`
- `0x14001ae50`
- `0x14001b200`
- `0x14001b3c0`
- `0x14001b98c`
- `0x14001c2d0`
- `0x14001d304`
- `0x14001febc`
- `0x140020124`
- `0x14002052c`
- `0x140020b80`
- `0x140021550`
- `0x1400221e8`
- `0x1400222b0`
- `0x140022634`
- `0x1400235c0`
- `0x140025280`
- `0x140026080`
- `0x140026734`
- `0x140026868`

## callees

- `0x140001008`
- `0x140009df0`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceGuidError(const int *a1, int a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // [rsp+30h] [rbp-29h] BYREF
  int v8; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-19h] BYREF
  const int *v10; // [rsp+60h] [rbp+7h]
  int v11; // [rsp+68h] [rbp+Fh]
  int v12; // [rsp+6Ch] [rbp+13h]
  int *v13; // [rsp+70h] [rbp+17h]
  __int64 v14; // [rsp+78h] [rbp+1Fh]
  int *v15; // [rsp+80h] [rbp+27h]
  __int64 v16; // [rsp+88h] [rbp+2Fh]
  __int64 v17; // [rsp+90h] [rbp+37h]
  __int64 v18; // [rsp+98h] [rbp+3Fh]

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
    v11 = v6;
    v13 = &v7;
    v15 = &v8;
    v10 = a1;
    v7 = a2;
    v12 = 0;
    v14 = 4;
    v8 = a3;
    v16 = 4;
    v17 = a4;
    v18 = 16;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&word_14001190A,
             a3,
             a4,
             6u,
             &v9);
  }
  return result;
}

```

## disassembly

```asm
0x140009df0  push    rbp
0x140009df2  lea     rbp, [rsp-57h]
0x140009df7  sub     rsp, 0B0h
0x140009dfe  mov     rax, cs:__security_cookie
0x140009e05  xor     rax, rsp
0x140009e08  mov     [rbp+57h+var_10], rax
0x140009e0c  mov     eax, cs:dword_140013058
0x140009e12  cmp     eax, 2
0x140009e15  jbe     loc_140009EA2
0x140009e1b  xor     r10d, r10d
0x140009e1e  test    rcx, rcx
0x140009e21  jz      short loc_140009E34
0x140009e23  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009e27  inc     rax
0x140009e2a  cmp     [rcx+rax], r10b
0x140009e2e  jnz     short loc_140009E27
0x140009e30  inc     eax
0x140009e32  jmp     short loc_140009E40
0x140009e34  lea     rcx, byte_14000E6BD
0x140009e3b  mov     eax, 1
0x140009e40  mov     [rbp+57h+var_48], eax
0x140009e43  lea     rax, [rbp+57h+var_80]
0x140009e47  mov     [rbp+57h+var_40], rax
0x140009e4b  lea     rax, [rbp+57h+var_7C]
0x140009e4f  mov     [rbp+57h+var_30], rax
0x140009e53  lea     rax, [rbp+57h+var_70]
0x140009e57  mov     [rbp+57h+var_50], rcx
0x140009e5b  lea     rcx, dword_140013058; int
0x140009e62  mov     [rbp+57h+var_80], edx
0x140009e65  lea     rdx, word_14001190A; int
0x140009e6c  mov     [rsp+0B0h+var_88], rax; __int64
0x140009e71  mov     [rsp+0B0h+var_90], 6; ULONG
0x140009e79  mov     [rbp+57h+var_44], r10d
0x140009e7d  mov     [rbp+57h+var_38], 4
0x140009e85  mov     [rbp+57h+var_7C], r8d
0x140009e89  mov     [rbp+57h+var_28], 4
0x140009e91  mov     [rbp+57h+var_20], r9
0x140009e95  mov     [rbp+57h+var_18], 10h
0x140009e9d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009ea2  mov     rcx, [rbp+57h+var_10]
0x140009ea6  xor     rcx, rsp; StackCookie
0x140009ea9  call    __security_check_cookie
0x140009eae  add     rsp, 0B0h
0x140009eb5  pop     rbp
0x140009eb6  retn
```
