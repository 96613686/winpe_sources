# TraceLoggingTransmitControllerCommandFailed

- ea: `0x14000a018`
- end: `0x14000a0b2`
- name: `TraceLoggingTransmitControllerCommandFailed`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005560`

## callees

- `0x140001008`
- `0x140001040`
- `0x14000a018`
- `0x14000da60`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingTransmitControllerCommandFailed(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // [rsp+30h] [rbp-68h] BYREF
  char v9; // [rsp+31h] [rbp-67h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-58h] BYREF
  char *v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  char *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  result = dword_140013010;
  LOBYTE(a3) = a2;
  LOBYTE(a4) = a1;
  if ( (unsigned int)dword_140013010 > 5 )
  {
    result = tlgKeywordOn(a1, a2, a3, a4);
    if ( (_BYTE)result )
    {
      v8 = v7;
      v11 = &v8;
      v12 = 1;
      v13 = &v9;
      v9 = v6;
      v14 = 1;
      return tlgWriteTransfer_EtwWriteTransfer(v5, (unsigned __int8 *)&byte_140010E81, v6, v7, 4u, &v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a018  sub     rsp, 98h
0x14000a01f  mov     rax, cs:__security_cookie
0x14000a026  xor     rax, rsp
0x14000a029  mov     [rsp+98h+var_18], rax
0x14000a031  mov     eax, cs:dword_140013010
0x14000a037  mov     r8b, dl
0x14000a03a  mov     r9b, cl
0x14000a03d  cmp     eax, 5
0x14000a040  jbe     short loc_14000A099
0x14000a042  call    _tlgKeywordOn
0x14000a047  test    al, al
0x14000a049  jz      short loc_14000A099
0x14000a04b  lea     rax, [rsp+98h+var_68]
0x14000a050  mov     [rsp+98h+var_68], r9b
0x14000a055  mov     [rsp+98h+var_38], rax
0x14000a05a  lea     rdx, byte_140010E81; int
0x14000a061  lea     rax, [rsp+98h+var_67]
0x14000a066  mov     [rsp+98h+var_30], 1
0x14000a06f  mov     [rsp+98h+var_28], rax
0x14000a074  lea     rax, [rsp+98h+var_58]
0x14000a079  mov     [rsp+98h+var_70], rax; __int64
0x14000a07e  mov     [rsp+98h+var_78], 4; ULONG
0x14000a086  mov     [rsp+98h+var_67], r8b
0x14000a08b  mov     [rsp+98h+var_20], 1
0x14000a094  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a099  mov     rcx, [rsp+98h+var_18]
0x14000a0a1  xor     rcx, rsp; StackCookie
0x14000a0a4  call    __security_check_cookie
0x14000a0a9  add     rsp, 98h
0x14000a0b0  retn
```
