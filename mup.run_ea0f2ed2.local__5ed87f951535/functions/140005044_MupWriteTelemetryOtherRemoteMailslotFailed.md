# MupWriteTelemetryOtherRemoteMailslotFailed

- ea: `0x140005044`
- end: `0x1400050dc`
- name: `MupWriteTelemetryOtherRemoteMailslotFailed`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f21c`

## callees

- `0x140001008`
- `0x1400024fc`
- `0x140005044`
- `0x1400054a0`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14000506c`
- `ntoskrnl!RtlHashUnicodeString` at `0x14000506c`

## pseudocode

```c
NTSTATUS __fastcall MupWriteTelemetryOtherRemoteMailslotFailed(const UNICODE_STRING *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  NTSTATUS result; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  ULONG HashValue; // [rsp+30h] [rbp-58h] BYREF
  __int64 v9; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-28h]
  __int64 v12; // [rsp+68h] [rbp-20h]

  HashValue = 0;
  RtlHashUnicodeString(a1, 1u, 0, &HashValue);
  result = dword_14000A098;
  if ( (unsigned int)dword_14000A098 > 5 )
  {
    result = tlgKeywordOn(v2, v1, v3);
    if ( (_BYTE)result )
    {
      v9 = HashValue;
      v11 = &v9;
      v12 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(v5, (unsigned __int8 *)&byte_140007FB1, v6, v7, 3u, &v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005044  sub     rsp, 88h
0x14000504b  mov     rax, cs:__security_cookie
0x140005052  xor     rax, rsp
0x140005055  mov     [rsp+88h+var_18], rax
0x14000505a  lea     r9, [rsp+88h+HashValue]; HashValue
0x14000505f  mov     [rsp+88h+HashValue], 0
0x140005067  xor     r8d, r8d; HashAlgorithm
0x14000506a  mov     dl, 1; CaseInSensitive
0x14000506c  call    cs:__imp_RtlHashUnicodeString
0x140005073  nop     dword ptr [rax+rax+00h]
0x140005078  mov     eax, cs:dword_14000A098
0x14000507e  cmp     eax, 5
0x140005081  jbe     short loc_1400050C6
0x140005083  call    _tlgKeywordOn
0x140005088  test    al, al
0x14000508a  jz      short loc_1400050C6
0x14000508c  mov     eax, [rsp+88h+HashValue]
0x140005090  lea     rdx, byte_140007FB1; int
0x140005097  mov     [rsp+88h+var_50], rax
0x14000509c  lea     rax, [rsp+88h+var_50]
0x1400050a1  mov     [rsp+88h+var_28], rax
0x1400050a6  lea     rax, [rsp+88h+var_48]
0x1400050ab  mov     [rsp+88h+var_60], rax; __int64
0x1400050b0  mov     [rsp+88h+var_68], 3; ULONG
0x1400050b8  mov     [rsp+88h+var_20], 8
0x1400050c1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400050c6  mov     rcx, [rsp+88h+var_18]
0x1400050cb  xor     rcx, rsp; StackCookie
0x1400050ce  call    __security_check_cookie
0x1400050d3  add     rsp, 88h
0x1400050da  retn
```
