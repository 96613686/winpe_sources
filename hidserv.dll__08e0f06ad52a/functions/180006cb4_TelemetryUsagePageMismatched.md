# TelemetryUsagePageMismatched

- ea: `0x180006cb4`
- end: `0x180006dc2`
- name: `TelemetryUsagePageMismatched`
- size: `270`
- prototype: `ULONG __fastcall(const int *, __int16, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005708`

## callees

- `0x180006cb4`
- `0x1800081d4`
- `0x180008450`

## pseudocode

```c
ULONG __fastcall TelemetryUsagePageMismatched(const int *a1, __int16 a2, __int64 a3)
{
  ULONG result; // eax
  __int64 v4; // rax
  int v5; // eax
  __int16 v6; // [rsp+30h] [rbp-49h] BYREF
  __int16 v7; // [rsp+34h] [rbp-45h] BYREF
  __int64 v8; // [rsp+38h] [rbp-41h] BYREF
  __int64 v9; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v11; // [rsp+70h] [rbp-9h]
  __int64 v12; // [rsp+78h] [rbp-1h]
  const int *v13; // [rsp+80h] [rbp+7h]
  int v14; // [rsp+88h] [rbp+Fh]
  int v15; // [rsp+8Ch] [rbp+13h]
  __int16 *v16; // [rsp+90h] [rbp+17h]
  __int64 v17; // [rsp+98h] [rbp+1Fh]
  __int16 *v18; // [rsp+A0h] [rbp+27h]
  __int64 v19; // [rsp+A8h] [rbp+2Fh]
  __int64 *v20; // [rsp+B0h] [rbp+37h]
  __int64 v21; // [rsp+B8h] [rbp+3Fh]

  result = dword_18000D000;
  if ( (unsigned int)dword_18000D000 > 5 )
  {
    result = qword_18000D010;
    if ( (qword_18000D010 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_18000D018 & 0x400000000000LL) == qword_18000D018 )
      {
        v8 = 1;
        v12 = 8;
        v11 = &v8;
        if ( a1 )
        {
          v4 = -1;
          do
            ++v4;
          while ( *((_WORD *)a1 + v4) );
          v5 = 2 * v4 + 2;
        }
        else
        {
          a1 = &dword_18000A75C;
          v5 = 2;
        }
        v14 = v5;
        v16 = &v6;
        v18 = &v7;
        v20 = &v9;
        v6 = a2;
        v13 = a1;
        v15 = 0;
        v17 = 2;
        v7 = a3;
        v19 = 2;
        v9 = 0x1000000;
        v21 = 8;
        return tlgWriteAgg((__int64)a1, (unsigned __int8 *)&byte_18000AD21, a3, 0, &v10);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006cb4  push    rbp
0x180006cb6  lea     rbp, [rsp-57h]
0x180006cbb  sub     rsp, 0D0h
0x180006cc2  mov     rax, cs:__security_cookie
0x180006cc9  xor     rax, rsp
0x180006ccc  mov     [rbp+57h+var_10], rax
0x180006cd0  mov     eax, cs:dword_18000D000
0x180006cd6  cmp     eax, 5
0x180006cd9  jbe     loc_180006DAD
0x180006cdf  mov     r9, cs:qword_18000D018
0x180006ce6  mov     r10, 400000000000h
0x180006cf0  mov     rax, cs:qword_18000D010
0x180006cf7  test    r10, rax
0x180006cfa  jz      loc_180006DAD
0x180006d00  mov     rax, r9
0x180006d03  and     rax, r10
0x180006d06  cmp     rax, r9
0x180006d09  jnz     loc_180006DAD
0x180006d0f  xor     r9d, r9d; int
0x180006d12  mov     [rbp+57h+var_98], 1
0x180006d1a  mov     [rbp+57h+var_58], 8
0x180006d22  lea     rax, [rbp+57h+var_98]
0x180006d26  mov     [rbp+57h+var_60], rax
0x180006d2a  lea     r10d, [r9+2]
0x180006d2e  test    rcx, rcx
0x180006d31  jz      short loc_180006D4A
0x180006d33  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d37  inc     rax
0x180006d3a  cmp     [rcx+rax*2], r9w
0x180006d3f  jnz     short loc_180006D37
0x180006d41  lea     eax, ds:2[rax*2]
0x180006d48  jmp     short loc_180006D54
0x180006d4a  lea     rcx, dword_18000A75C; int
0x180006d51  mov     eax, r10d
0x180006d54  mov     [rbp+57h+var_48], eax
0x180006d57  lea     rax, [rbp+57h+var_A0]
0x180006d5b  mov     [rbp+57h+var_40], rax
0x180006d5f  lea     rax, [rbp+57h+var_9C]
0x180006d63  mov     [rbp+57h+var_30], rax
0x180006d67  lea     rax, [rbp+57h+var_90]
0x180006d6b  mov     [rbp+57h+var_20], rax
0x180006d6f  lea     rax, [rbp+57h+var_80]
0x180006d73  mov     [rbp+57h+var_A0], dx
0x180006d77  lea     rdx, byte_18000AD21; int
0x180006d7e  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x180006d83  mov     [rbp+57h+var_50], rcx
0x180006d87  mov     [rbp+57h+var_44], r9d
0x180006d8b  mov     [rbp+57h+var_38], r10
0x180006d8f  mov     [rbp+57h+var_9C], r8w
0x180006d94  mov     [rbp+57h+var_28], r10
0x180006d98  mov     [rbp+57h+var_90], 1000000h
0x180006da0  mov     [rbp+57h+var_18], 8
0x180006da8  call    _tlgWriteAgg
0x180006dad  mov     rcx, [rbp+57h+var_10]
0x180006db1  xor     rcx, rsp; StackCookie
0x180006db4  call    __security_check_cookie
0x180006db9  add     rsp, 0D0h
0x180006dc0  pop     rbp
0x180006dc1  retn
```
