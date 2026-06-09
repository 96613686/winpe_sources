# TraceLoggingResetResponseFailed

- ea: `0x14000a48c`
- end: `0x14000a4ff`
- name: `TraceLoggingResetResponseFailed`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140019cfc`
- `0x14001a19c`
- `0x14001d8b0`

## callees

- `0x140001008`
- `0x140001040`
- `0x14000a48c`
- `0x14000da60`

## pseudocode

```c
char TraceLoggingResetResponseFailed()
{
  char result; // al
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  int v4; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  int *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  result = dword_140013010;
  if ( (unsigned int)dword_140013010 > 5 )
  {
    result = tlgKeywordOn();
    if ( result )
    {
      v4 = v2;
      v6 = &v4;
      v7 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(v1, (unsigned __int8 *)&byte_140010F41, v2, v3, 3u, &v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a48c  sub     rsp, 78h
0x14000a490  mov     rax, cs:__security_cookie
0x14000a497  xor     rax, rsp
0x14000a49a  mov     [rsp+78h+var_10], rax
0x14000a49f  mov     eax, cs:dword_140013010
0x14000a4a5  mov     r8d, ecx
0x14000a4a8  cmp     eax, 5
0x14000a4ab  jbe     short loc_14000A4EC
0x14000a4ad  call    _tlgKeywordOn
0x14000a4b2  test    al, al
0x14000a4b4  jz      short loc_14000A4EC
0x14000a4b6  lea     rax, [rsp+78h+var_48]
0x14000a4bb  mov     [rsp+78h+var_48], r8d
0x14000a4c0  mov     [rsp+78h+var_20], rax
0x14000a4c5  lea     rdx, byte_140010F41; int
0x14000a4cc  lea     rax, [rsp+78h+var_40]
0x14000a4d1  mov     [rsp+78h+var_18], 4
0x14000a4da  mov     [rsp+78h+var_50], rax; __int64
0x14000a4df  mov     [rsp+78h+var_58], 3; ULONG
0x14000a4e7  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a4ec  mov     rcx, [rsp+78h+var_10]
0x14000a4f1  xor     rcx, rsp; StackCookie
0x14000a4f4  call    __security_check_cookie
0x14000a4f9  add     rsp, 78h
0x14000a4fd  retn
```
