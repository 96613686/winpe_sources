# WPP_SF__sid_dd

- ea: `0x180022c04`
- end: `0x180022cbd`
- name: `WPP_SF__sid_dd`
- size: `185`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043d8`

## callees

- `0x180022c04`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c2e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c2e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022c21`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022c45`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022c21`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022c45`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022ca7`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022ca7`

## pseudocode

```c
ULONG WPP_SF__sid_dd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, ...)
{
  char *v4; // rbx
  DWORD LengthSid; // edi
  __int64 v8; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v8 = va_arg(va1, _QWORD);
  v4 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v4);
  }
  else
  {
    LengthSid = 5;
    if ( !v4 )
    {
LABEL_6:
      v4 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
               0xCu,
               v4,
               LengthSid,
               va,
               4,
               va1,
               4,
               0);
    }
  }
  if ( !IsValidSid(v4) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
           0xCu,
           v4,
           LengthSid,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x180022c04  mov     [rsp+arg_0], rbx
0x180022c09  mov     [rsp+arg_8], rsi
0x180022c0e  push    rdi
0x180022c0f  sub     rsp, 60h
0x180022c13  mov     rbx, r9
0x180022c16  mov     rsi, rcx
0x180022c19  test    r9, r9
0x180022c1c  jz      short loc_180022C38
0x180022c1e  mov     rcx, rbx; pSid
0x180022c21  call    cs:__imp_IsValidSid
0x180022c27  test    eax, eax
0x180022c29  jz      short loc_180022C38
0x180022c2b  mov     rcx, rbx; pSid
0x180022c2e  call    cs:__imp_GetLengthSid
0x180022c34  mov     edi, eax
0x180022c36  jmp     short loc_180022C42
0x180022c38  mov     edi, 5
0x180022c3d  test    rbx, rbx
0x180022c40  jz      short loc_180022C4F
0x180022c42  mov     rcx, rbx; pSid
0x180022c45  call    cs:__imp_IsValidSid
0x180022c4b  test    eax, eax
0x180022c4d  jnz     short loc_180022C56
0x180022c4f  lea     rbx, aNull; "NULL"
0x180022c56  mov     [rsp+68h+var_18], 0
0x180022c5f  lea     rcx, [rsp+68h+arg_28]
0x180022c67  mov     r9d, 0Ch; MessageNumber
0x180022c6d  mov     eax, edi
0x180022c6f  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids; MessageGuid
0x180022c76  lea     edx, [r9-8]
0x180022c7a  mov     [rsp+68h+var_20], rdx
0x180022c7f  mov     [rsp+68h+var_28], rcx
0x180022c84  lea     rcx, [rsp+68h+arg_20]
0x180022c8c  mov     [rsp+68h+var_30], rdx
0x180022c91  lea     edx, [r9+1Fh]; MessageFlags
0x180022c95  mov     [rsp+68h+var_38], rcx
0x180022c9a  mov     rcx, rsi; LoggerHandle
0x180022c9d  mov     [rsp+68h+var_40], rax
0x180022ca2  mov     [rsp+68h+var_48], rbx
0x180022ca7  call    cs:__imp_TraceMessage
0x180022cad  mov     rbx, [rsp+68h+arg_0]
0x180022cb2  mov     rsi, [rsp+68h+arg_8]
0x180022cb7  add     rsp, 60h
0x180022cbb  pop     rdi
0x180022cbc  retn
```
