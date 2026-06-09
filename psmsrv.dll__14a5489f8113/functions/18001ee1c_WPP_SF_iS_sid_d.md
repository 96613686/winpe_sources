# WPP_SF_iS_sid_d

- ea: `0x18001ee1c`
- end: `0x18001ef2d`
- name: `WPP_SF_iS_sid_d`
- size: `273`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, PSID pSid, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017768`
- `0x18001cf00`

## callees

- `0x18001ee1c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ee59`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ee59`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ee4c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ee70`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ee4c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ee70`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ef12`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ef12`

## pseudocode

```c
ULONG WPP_SF_iS_sid_d(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, ...)
{
  char *v3; // rbx
  DWORD LengthSid; // edi
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v11; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  const wchar_t *v13; // [rsp+B0h] [rbp+28h]
  char *pSid; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, const wchar_t *);
  pSid = va_arg(va1, char *);
  v3 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v3);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( v3 )
  {
LABEL_5:
    if ( IsValidSid(v3) )
      goto LABEL_7;
  }
  v3 = "NULL";
LABEL_7:
  v7 = v13;
  if ( v13 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v13[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !v13 )
    v7 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
           a2,
           va,
           8,
           v7,
           v9,
           v3,
           LengthSid,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18001ee1c  mov     [rsp+arg_0], rbx
0x18001ee21  mov     [rsp+arg_8], rbp
0x18001ee26  mov     [rsp+arg_18], r9
0x18001ee2b  push    rsi
0x18001ee2c  push    rdi
0x18001ee2d  push    r14
0x18001ee2f  sub     rsp, 70h
0x18001ee33  mov     rbx, [rsp+88h+pSid]
0x18001ee3b  xor     r14d, r14d
0x18001ee3e  movzx   esi, dx
0x18001ee41  mov     rbp, rcx
0x18001ee44  test    rbx, rbx
0x18001ee47  jz      short loc_18001EE63
0x18001ee49  mov     rcx, rbx; pSid
0x18001ee4c  call    cs:__imp_IsValidSid
0x18001ee52  test    eax, eax
0x18001ee54  jz      short loc_18001EE63
0x18001ee56  mov     rcx, rbx; pSid
0x18001ee59  call    cs:__imp_GetLengthSid
0x18001ee5f  mov     edi, eax
0x18001ee61  jmp     short loc_18001EE6D
0x18001ee63  mov     edi, 5
0x18001ee68  test    rbx, rbx
0x18001ee6b  jz      short loc_18001EE7A
0x18001ee6d  mov     rcx, rbx; pSid
0x18001ee70  call    cs:__imp_IsValidSid
0x18001ee76  test    eax, eax
0x18001ee78  jnz     short loc_18001EE81
0x18001ee7a  lea     rbx, aNull; "NULL"
0x18001ee81  mov     rcx, [rsp+88h+arg_20]
0x18001ee89  test    rcx, rcx
0x18001ee8c  jz      short loc_18001EEA6
0x18001ee8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee92  inc     rax
0x18001ee95  cmp     [rcx+rax*2], r14w
0x18001ee9a  jnz     short loc_18001EE92
0x18001ee9c  lea     rdx, ds:2[rax*2]
0x18001eea4  jmp     short loc_18001EEAB
0x18001eea6  mov     edx, 0Ah
0x18001eeab  mov     [rsp+88h+var_28], r14
0x18001eeb0  lea     r8, aNull_0; "NULL"
0x18001eeb7  mov     [rsp+88h+var_30], 4
0x18001eec0  test    rcx, rcx
0x18001eec3  mov     eax, edi
0x18001eec5  mov     r9d, esi; MessageNumber
0x18001eec8  cmovz   rcx, r8
0x18001eecc  lea     r8, [rsp+88h+arg_30]
0x18001eed4  mov     [rsp+88h+var_38], r8
0x18001eed9  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids; MessageGuid
0x18001eee0  mov     [rsp+88h+var_40], rax
0x18001eee5  lea     rax, [rsp+88h+arg_18]
0x18001eeed  mov     [rsp+88h+var_48], rbx
0x18001eef2  mov     [rsp+88h+var_50], rdx
0x18001eef7  mov     edx, 2Bh ; '+'; MessageFlags
0x18001eefc  mov     [rsp+88h+var_58], rcx
0x18001ef01  mov     rcx, rbp; LoggerHandle
0x18001ef04  mov     [rsp+88h+var_60], 8
0x18001ef0d  mov     [rsp+88h+var_68], rax
0x18001ef12  call    cs:__imp_TraceMessage
0x18001ef18  lea     r11, [rsp+88h+var_18]
0x18001ef1d  mov     rbx, [r11+20h]
0x18001ef21  mov     rbp, [r11+28h]
0x18001ef25  mov     rsp, r11
0x18001ef28  pop     r14
0x18001ef2a  pop     rdi
0x18001ef2b  pop     rsi
0x18001ef2c  retn
```
