# CdTelemetryMount

- ea: `0x14001b0d8`
- end: `0x14001b20a`
- name: `CdTelemetryMount`
- size: `306`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400142d8`

## callees

- `0x140001008`
- `0x140002df0`
- `0x14001b0d8`

## pseudocode

```c
NTSTATUS __fastcall CdTelemetryMount(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  __int64 v5; // rcx
  unsigned __int8 *v6; // rdx
  int v7; // eax
  ULONG v8; // [rsp+20h] [rbp-29h]
  int v9; // [rsp+30h] [rbp-19h] BYREF
  int v10; // [rsp+34h] [rbp-15h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-9h] BYREF
  __int64 v12; // [rsp+60h] [rbp+17h]
  __int64 v13; // [rsp+68h] [rbp+1Fh]
  int *v14; // [rsp+70h] [rbp+27h]
  __int64 v15; // [rsp+78h] [rbp+2Fh]
  int *v16; // [rsp+80h] [rbp+37h]
  __int64 v17; // [rsp+88h] [rbp+3Fh]

  result = dword_140007020;
  if ( a3 )
  {
    if ( (unsigned int)dword_140007020 > 5 )
    {
      v5 = 0x200000000000LL;
      result = qword_140007030;
      if ( (qword_140007030 & 0x200000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_140007038 & 0x200000000000LL) == qword_140007038 )
        {
          v15 = 4;
          v14 = &v9;
          v6 = (unsigned __int8 *)&byte_140005291;
          v7 = *(_DWORD *)(a3 + 424) * *(_DWORD *)(a3 + 436);
          v17 = 4;
          v10 = v7;
          v16 = &v10;
          v8 = 5;
          goto LABEL_10;
        }
      }
    }
  }
  else if ( (unsigned int)dword_140007020 > 5 )
  {
    result = qword_140007030;
    if ( (qword_140007030 & 0x200000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_140007038 & 0x200000000000LL) == qword_140007038 )
      {
        v5 = 4;
        v14 = &v9;
        v15 = 4;
        v6 = (unsigned __int8 *)byte_1400052C9;
        v8 = 4;
LABEL_10:
        v12 = a1;
        v13 = 16;
        v9 = 0;
        return tlgWriteTransfer_EtwWriteTransfer(v5, v6, a3, a1, v8, &v11);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b0d8  push    rbp
0x14001b0da  lea     rbp, [rsp-57h]
0x14001b0df  sub     rsp, 0A0h
0x14001b0e6  mov     rax, cs:__security_cookie
0x14001b0ed  xor     rax, rsp
0x14001b0f0  mov     [rbp+57h+var_10], rax
0x14001b0f4  mov     eax, cs:dword_140007020
0x14001b0fa  xor     r10d, r10d
0x14001b0fd  mov     r9, rcx; int
0x14001b100  test    r8, r8
0x14001b103  jnz     short loc_14001B164
0x14001b105  cmp     eax, 5
0x14001b108  jbe     loc_14001B1F4
0x14001b10e  mov     rdx, cs:qword_140007038
0x14001b115  mov     rcx, 200000000000h
0x14001b11f  mov     rax, cs:qword_140007030
0x14001b126  test    rcx, rax
0x14001b129  jz      loc_14001B1F4
0x14001b12f  mov     rax, rdx
0x14001b132  and     rax, rcx
0x14001b135  cmp     rax, rdx
0x14001b138  jnz     loc_14001B1F4
0x14001b13e  lea     rax, [rbp+57h+var_70]
0x14001b142  lea     ecx, [r10+4]
0x14001b146  mov     [rbp+57h+var_30], rax
0x14001b14a  lea     rax, [rbp+57h+var_60]
0x14001b14e  mov     [rbp+57h+var_28], rcx
0x14001b152  mov     [rsp+0A0h+var_78], rax
0x14001b157  lea     rdx, byte_1400052C9
0x14001b15e  mov     [rsp+0A0h+var_80], ecx
0x14001b162  jmp     short loc_14001B1DF
0x14001b164  cmp     eax, 5
0x14001b167  jbe     loc_14001B1F4
0x14001b16d  mov     rdx, cs:qword_140007038
0x14001b174  mov     rcx, 200000000000h; int
0x14001b17e  mov     rax, cs:qword_140007030
0x14001b185  test    rcx, rax
0x14001b188  jz      short loc_14001B1F4
0x14001b18a  mov     rax, rdx
0x14001b18d  and     rax, rcx
0x14001b190  cmp     rax, rdx
0x14001b193  jnz     short loc_14001B1F4
0x14001b195  lea     rax, [rbp+57h+var_70]
0x14001b199  mov     [rbp+57h+var_28], 4
0x14001b1a1  mov     [rbp+57h+var_30], rax
0x14001b1a5  lea     rdx, byte_140005291; int
0x14001b1ac  mov     eax, [r8+1B4h]
0x14001b1b3  imul    eax, [r8+1A8h]
0x14001b1bb  mov     [rbp+57h+var_18], 4
0x14001b1c3  mov     [rbp+57h+var_6C], eax
0x14001b1c6  lea     rax, [rbp+57h+var_6C]
0x14001b1ca  mov     [rbp+57h+var_20], rax
0x14001b1ce  lea     rax, [rbp+57h+var_60]
0x14001b1d2  mov     [rsp+0A0h+var_78], rax; __int64
0x14001b1d7  mov     [rsp+0A0h+var_80], 5; ULONG
0x14001b1df  mov     [rbp+57h+var_40], r9
0x14001b1e3  mov     [rbp+57h+var_38], 10h
0x14001b1eb  mov     [rbp+57h+var_70], r10d
0x14001b1ef  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001b1f4  mov     rcx, [rbp+57h+var_10]
0x14001b1f8  xor     rcx, rsp; StackCookie
0x14001b1fb  call    __security_check_cookie
0x14001b200  add     rsp, 0A0h
0x14001b207  pop     rbp
0x14001b208  retn
```
