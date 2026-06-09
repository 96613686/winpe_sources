# WPP_SF_D_sid_

- ea: `0x1800c0fac`
- end: `0x1800c1050`
- name: `WPP_SF_D_sid_`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180051ea0`
- `0x1800523e8`

## callees

- `0x1800c0fac`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800c1041`
- `ntdll!EtwTraceMessage` at `0x1800c1041`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c0fcf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c0ff3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c0fcf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c0ff3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c0fdc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c0fdc`

## pseudocode

```c
__int64 __fastcall WPP_SF_D_sid_(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, char *pSid)
{
  char *v5; // rbx
  unsigned int v7; // esi
  int v9; // [rsp+98h] [rbp+20h] BYREF

  v9 = a4;
  v5 = pSid;
  v7 = a2;
  if ( pSid && IsValidSid(pSid) )
  {
    GetLengthSid(v5);
  }
  else if ( !v5 )
  {
LABEL_6:
    v5 = "NULL";
    return EtwTraceMessage(a1, 43, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, v7, &v9, 4, v5);
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, v7, &v9, 4, v5);
}

```

## disassembly

```asm
0x1800c0fac  mov     [rsp+arg_18], r9d
0x1800c0fb1  push    rbx
0x1800c0fb2  push    rbp
0x1800c0fb3  push    rsi
0x1800c0fb4  push    rdi
0x1800c0fb5  sub     rsp, 58h
0x1800c0fb9  mov     rbx, [rsp+78h+pSid]
0x1800c0fc1  mov     rbp, rcx
0x1800c0fc4  movzx   esi, dx
0x1800c0fc7  test    rbx, rbx
0x1800c0fca  jz      short loc_1800C0FE6
0x1800c0fcc  mov     rcx, rbx; pSid
0x1800c0fcf  call    cs:__imp_IsValidSid
0x1800c0fd5  test    eax, eax
0x1800c0fd7  jz      short loc_1800C0FE6
0x1800c0fd9  mov     rcx, rbx; pSid
0x1800c0fdc  call    cs:__imp_GetLengthSid
0x1800c0fe2  mov     edi, eax
0x1800c0fe4  jmp     short loc_1800C0FF0
0x1800c0fe6  mov     edi, 5
0x1800c0feb  test    rbx, rbx
0x1800c0fee  jz      short loc_1800C0FFD
0x1800c0ff0  mov     rcx, rbx; pSid
0x1800c0ff3  call    cs:__imp_IsValidSid
0x1800c0ff9  test    eax, eax
0x1800c0ffb  jnz     short loc_1800C1004
0x1800c0ffd  lea     rbx, aNull; "NULL"
0x1800c1004  mov     [rsp+78h+var_38], 0
0x1800c100d  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800c1014  mov     eax, edi
0x1800c1016  mov     r9d, esi
0x1800c1019  mov     [rsp+78h+var_40], rax
0x1800c101e  mov     edx, 2Bh ; '+'
0x1800c1023  mov     [rsp+78h+var_48], rbx
0x1800c1028  lea     rax, [rsp+78h+arg_18]
0x1800c1030  mov     [rsp+78h+var_50], 4
0x1800c1039  mov     rcx, rbp
0x1800c103c  mov     [rsp+78h+var_58], rax
0x1800c1041  call    cs:__imp_EtwTraceMessage
0x1800c1047  add     rsp, 58h
0x1800c104b  pop     rdi
0x1800c104c  pop     rsi
0x1800c104d  pop     rbp
0x1800c104e  pop     rbx
0x1800c104f  retn
```
