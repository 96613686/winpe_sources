# WPP_SF__sid_

- ea: `0x14000e370`
- end: `0x14000e3f5`
- name: `WPP_SF__sid_`
- size: `133`
- prototype: `ULONG __fastcall(TRACEHANDLE LoggerHandle, USHORT, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d9d0`

## callees

- `0x14000e370`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x14000e3e6`
- `ADVAPI32!TraceMessage` at `0x14000e3e6`
- `ADVAPI32!IsValidSid` at `0x14000e38a`
- `ADVAPI32!IsValidSid` at `0x14000e3ae`
- `ADVAPI32!IsValidSid` at `0x14000e38a`
- `ADVAPI32!IsValidSid` at `0x14000e3ae`
- `ADVAPI32!GetLengthSid` at `0x14000e397`
- `ADVAPI32!GetLengthSid` at `0x14000e397`

## pseudocode

```c
ULONG __fastcall WPP_SF__sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, char *a4)
{
  char *v5; // rbx
  DWORD LengthSid; // edi

  v5 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_6:
      v5 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids, a2, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(LoggerHandle, 0x2Bu, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids, a2, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x14000e370  push    rbx
0x14000e372  push    rbp
0x14000e373  push    rsi
0x14000e374  push    rdi
0x14000e375  sub     rsp, 48h
0x14000e379  movzx   esi, dx
0x14000e37c  mov     rbx, r9
0x14000e37f  mov     rbp, rcx
0x14000e382  test    r9, r9
0x14000e385  jz      short loc_14000E3A1
0x14000e387  mov     rcx, rbx; pSid
0x14000e38a  call    cs:__imp_IsValidSid
0x14000e390  test    eax, eax
0x14000e392  jz      short loc_14000E3A1
0x14000e394  mov     rcx, rbx; pSid
0x14000e397  call    cs:__imp_GetLengthSid
0x14000e39d  mov     edi, eax
0x14000e39f  jmp     short loc_14000E3AB
0x14000e3a1  mov     edi, 5
0x14000e3a6  test    rbx, rbx
0x14000e3a9  jz      short loc_14000E3B8
0x14000e3ab  mov     rcx, rbx; pSid
0x14000e3ae  call    cs:__imp_IsValidSid
0x14000e3b4  test    eax, eax
0x14000e3b6  jnz     short loc_14000E3BF
0x14000e3b8  lea     rbx, aNull; "NULL"
0x14000e3bf  mov     eax, edi
0x14000e3c1  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids; MessageGuid
0x14000e3c8  mov     [rsp+68h+var_38], 0
0x14000e3d1  mov     r9d, esi; MessageNumber
0x14000e3d4  mov     [rsp+68h+var_40], rax
0x14000e3d9  mov     edx, 2Bh ; '+'; MessageFlags
0x14000e3de  mov     rcx, rbp; LoggerHandle
0x14000e3e1  mov     [rsp+68h+var_48], rbx
0x14000e3e6  call    cs:__imp_TraceMessage
0x14000e3ec  add     rsp, 48h
0x14000e3f0  pop     rdi
0x14000e3f1  pop     rsi
0x14000e3f2  pop     rbp
0x14000e3f3  pop     rbx
0x14000e3f4  retn
```
