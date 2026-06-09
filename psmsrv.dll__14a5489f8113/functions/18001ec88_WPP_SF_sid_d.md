# WPP_SF__sid_d

- ea: `0x18001ec88`
- end: `0x18001ed26`
- name: `WPP_SF__sid_d`
- size: `158`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000191c`
- `0x180016760`

## callees

- `0x18001ec88`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ecb4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ecb4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eca7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eccb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eca7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eccb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ed15`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ed15`

## pseudocode

```c
ULONG WPP_SF__sid_d(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, char *a4, ...)
{
  char *v5; // rbx
  DWORD LengthSid; // edi
  va_list va; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va, a4);
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
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, va, 4, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, va, 4, 0);
}

```

## disassembly

```asm
0x18001ec88  push    rbx
0x18001ec8a  push    rbp
0x18001ec8b  push    rsi
0x18001ec8c  push    rdi
0x18001ec8d  push    r14
0x18001ec8f  sub     rsp, 50h
0x18001ec93  movzx   ebp, dx
0x18001ec96  mov     rbx, r9
0x18001ec99  mov     rsi, r8
0x18001ec9c  mov     r14, rcx
0x18001ec9f  test    r9, r9
0x18001eca2  jz      short loc_18001ECBE
0x18001eca4  mov     rcx, rbx; pSid
0x18001eca7  call    cs:__imp_IsValidSid
0x18001ecad  test    eax, eax
0x18001ecaf  jz      short loc_18001ECBE
0x18001ecb1  mov     rcx, rbx; pSid
0x18001ecb4  call    cs:__imp_GetLengthSid
0x18001ecba  mov     edi, eax
0x18001ecbc  jmp     short loc_18001ECC8
0x18001ecbe  mov     edi, 5
0x18001ecc3  test    rbx, rbx
0x18001ecc6  jz      short loc_18001ECD5
0x18001ecc8  mov     rcx, rbx; pSid
0x18001eccb  call    cs:__imp_IsValidSid
0x18001ecd1  test    eax, eax
0x18001ecd3  jnz     short loc_18001ECDC
0x18001ecd5  lea     rbx, aNull; "NULL"
0x18001ecdc  mov     [rsp+78h+var_38], 0
0x18001ece5  lea     rcx, [rsp+78h+arg_20]
0x18001eced  mov     [rsp+78h+var_40], 4
0x18001ecf6  mov     r9d, ebp; MessageNumber
0x18001ecf9  mov     [rsp+78h+var_48], rcx
0x18001ecfe  mov     r8, rsi; MessageGuid
0x18001ed01  mov     eax, edi
0x18001ed03  mov     rcx, r14; LoggerHandle
0x18001ed06  mov     [rsp+78h+var_50], rax
0x18001ed0b  mov     edx, 2Bh ; '+'; MessageFlags
0x18001ed10  mov     [rsp+78h+var_58], rbx
0x18001ed15  call    cs:__imp_TraceMessage
0x18001ed1b  add     rsp, 50h
0x18001ed1f  pop     r14
0x18001ed21  pop     rdi
0x18001ed22  pop     rsi
0x18001ed23  pop     rbp
0x18001ed24  pop     rbx
0x18001ed25  retn
```
