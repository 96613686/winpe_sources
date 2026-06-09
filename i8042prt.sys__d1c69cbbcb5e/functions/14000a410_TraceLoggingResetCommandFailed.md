# TraceLoggingResetCommandFailed

- ea: `0x14000a410`
- end: `0x14000a483`
- name: `TraceLoggingResetCommandFailed`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001d8b0`

## callees

- `0x140001008`
- `0x140001040`
- `0x14000a410`
- `0x14000da60`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingResetCommandFailed(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+38h] [rbp-40h] BYREF
  int *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  result = dword_140013010;
  if ( (unsigned int)dword_140013010 > 5 )
  {
    result = tlgKeywordOn(a1, a2, (unsigned int)a1, a4);
    if ( (_BYTE)result )
    {
      v8 = v6;
      v10 = &v8;
      v11 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(v5, (unsigned __int8 *)&word_140010F9A, v6, v7, 3u, &v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a410  sub     rsp, 78h
0x14000a414  mov     rax, cs:__security_cookie
0x14000a41b  xor     rax, rsp
0x14000a41e  mov     [rsp+78h+var_10], rax
0x14000a423  mov     eax, cs:dword_140013010
0x14000a429  mov     r8d, ecx
0x14000a42c  cmp     eax, 5
0x14000a42f  jbe     short loc_14000A470
0x14000a431  call    _tlgKeywordOn
0x14000a436  test    al, al
0x14000a438  jz      short loc_14000A470
0x14000a43a  lea     rax, [rsp+78h+var_48]
0x14000a43f  mov     [rsp+78h+var_48], r8d
0x14000a444  mov     [rsp+78h+var_20], rax
0x14000a449  lea     rdx, word_140010F9A; int
0x14000a450  lea     rax, [rsp+78h+var_40]
0x14000a455  mov     [rsp+78h+var_18], 4
0x14000a45e  mov     [rsp+78h+var_50], rax; __int64
0x14000a463  mov     [rsp+78h+var_58], 3; ULONG
0x14000a46b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a470  mov     rcx, [rsp+78h+var_10]
0x14000a475  xor     rcx, rsp; StackCookie
0x14000a478  call    __security_check_cookie
0x14000a47d  add     rsp, 78h
0x14000a481  retn
```
