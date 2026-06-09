# PrjfTelemetryTombstoneFailureOperation

- ea: `0x140006570`
- end: `0x140006659`
- name: `PrjfTelemetryTombstoneFailureOperation`
- size: `233`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140007cec`
- `0x140009d20`
- `0x140024184`
- `0x14002c3f8`
- `0x14002c98c`
- `0x140040670`
- `0x140041e28`
- `0x140042658`
- `0x140042eac`
- `0x140043d88`

## callees

- `0x140001008`
- `0x140006570`
- `0x14000ba20`

## pseudocode

```c
NTSTATUS __fastcall PrjfTelemetryTombstoneFailureOperation(char a1, char a2, int a3)
{
  NTSTATUS result; // eax
  char v4; // [rsp+30h] [rbp-29h] BYREF
  char v5; // [rsp+31h] [rbp-28h] BYREF
  int v6; // [rsp+34h] [rbp-25h] BYREF
  __int64 v7; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-19h] BYREF
  char *v9; // [rsp+60h] [rbp+7h]
  __int64 v10; // [rsp+68h] [rbp+Fh]
  char *v11; // [rsp+70h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  int *v13; // [rsp+80h] [rbp+27h]
  __int64 v14; // [rsp+88h] [rbp+2Fh]
  __int64 *v15; // [rsp+90h] [rbp+37h]
  __int64 v16; // [rsp+98h] [rbp+3Fh]

  result = dword_14001A068;
  if ( (unsigned int)dword_14001A068 > 5 )
  {
    result = qword_14001A078;
    if ( (qword_14001A078 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
      {
        v4 = a1;
        v9 = &v4;
        v5 = a2;
        v11 = &v5;
        v6 = a3;
        v13 = &v6;
        v10 = 1;
        v15 = &v7;
        v12 = 1;
        v14 = 4;
        v7 = 0x1000000;
        v16 = 8;
        return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14001A068, byte_1400165FE, 0, 0, 6u, &v8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006570  push    rbp
0x140006572  lea     rbp, [rsp-57h]
0x140006577  sub     rsp, 0B0h
0x14000657e  mov     rax, cs:__security_cookie
0x140006585  xor     rax, rsp
0x140006588  mov     [rbp+57h+var_10], rax
0x14000658c  mov     eax, cs:dword_14001A068
0x140006592  cmp     eax, 5
0x140006595  jbe     loc_140006643
0x14000659b  mov     r9, cs:qword_14001A080
0x1400065a2  mov     r10, 400000000000h
0x1400065ac  mov     rax, cs:qword_14001A078
0x1400065b3  test    r10, rax
0x1400065b6  jz      loc_140006643
0x1400065bc  mov     rax, r9
0x1400065bf  and     rax, r10
0x1400065c2  cmp     rax, r9
0x1400065c5  jnz     short loc_140006643
0x1400065c7  lea     rax, [rbp+57h+var_80]
0x1400065cb  mov     [rbp+57h+var_80], cl
0x1400065ce  mov     [rbp+57h+var_50], rax
0x1400065d2  lea     rcx, dword_14001A068
0x1400065d9  lea     rax, [rbp+57h+var_7F]
0x1400065dd  mov     [rbp+57h+var_7F], dl
0x1400065e0  mov     [rbp+57h+var_40], rax
0x1400065e4  lea     rdx, byte_1400165FE
0x1400065eb  lea     rax, [rbp+57h+var_7C]
0x1400065ef  mov     [rbp+57h+var_7C], r8d
0x1400065f3  mov     [rbp+57h+var_30], rax
0x1400065f7  xor     r9d, r9d
0x1400065fa  lea     rax, [rbp+57h+var_78]
0x1400065fe  mov     [rbp+57h+var_48], 1
0x140006606  mov     [rbp+57h+var_20], rax
0x14000660a  xor     r8d, r8d
0x14000660d  lea     rax, [rbp+57h+var_70]
0x140006611  mov     [rbp+57h+var_38], 1
0x140006619  mov     [rsp+0B0h+var_88], rax
0x14000661e  mov     [rsp+0B0h+var_90], 6
0x140006626  mov     [rbp+57h+var_28], 4
0x14000662e  mov     [rbp+57h+var_78], 1000000h
0x140006636  mov     [rbp+57h+var_18], 8
0x14000663e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006643  mov     rcx, [rbp+57h+var_10]
0x140006647  xor     rcx, rsp; StackCookie
0x14000664a  call    __security_check_cookie
0x14000664f  add     rsp, 0B0h
0x140006656  pop     rbp
0x140006657  retn
```
