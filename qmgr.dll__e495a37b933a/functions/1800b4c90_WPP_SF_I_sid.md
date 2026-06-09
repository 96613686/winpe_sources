# WPP_SF_I_sid_

- ea: `0x1800b4c90`
- end: `0x1800b4d3e`
- name: `WPP_SF_I_sid_`
- size: `174`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a130`

## callees

- `0x1800b4c90`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800b4d28`
- `ntdll!EtwTraceMessage` at `0x1800b4d28`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4cb7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4cdb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4cb7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4cdb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4cc4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4cc4`

## pseudocode

```c
__int64 __fastcall WPP_SF_I_sid_(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char *pSid)
{
  char *v5; // rbx
  __int64 v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = a4;
  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    GetLengthSid(v5);
  }
  else if ( !v5 )
  {
LABEL_6:
    v5 = "NULL";
    return EtwTraceMessage(a1, 43, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids, 81, &v8, 8, v5);
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids, 81, &v8, 8, v5);
}

```

## disassembly

```asm
0x1800b4c90  mov     [rsp+arg_0], rbx
0x1800b4c95  mov     [rsp+arg_8], rsi
0x1800b4c9a  mov     [rsp+arg_18], r9
0x1800b4c9f  push    rdi
0x1800b4ca0  sub     rsp, 50h
0x1800b4ca4  mov     rbx, [rsp+58h+pSid]
0x1800b4cac  mov     rsi, rcx
0x1800b4caf  test    rbx, rbx
0x1800b4cb2  jz      short loc_1800B4CCE
0x1800b4cb4  mov     rcx, rbx; pSid
0x1800b4cb7  call    cs:__imp_IsValidSid
0x1800b4cbd  test    eax, eax
0x1800b4cbf  jz      short loc_1800B4CCE
0x1800b4cc1  mov     rcx, rbx; pSid
0x1800b4cc4  call    cs:__imp_GetLengthSid
0x1800b4cca  mov     edi, eax
0x1800b4ccc  jmp     short loc_1800B4CD8
0x1800b4cce  mov     edi, 5
0x1800b4cd3  test    rbx, rbx
0x1800b4cd6  jz      short loc_1800B4CE5
0x1800b4cd8  mov     rcx, rbx; pSid
0x1800b4cdb  call    cs:__imp_IsValidSid
0x1800b4ce1  test    eax, eax
0x1800b4ce3  jnz     short loc_1800B4CEC
0x1800b4ce5  lea     rbx, aNull; "NULL"
0x1800b4cec  mov     [rsp+58h+var_18], 0
0x1800b4cf5  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x1800b4cfc  mov     r9d, 51h ; 'Q'
0x1800b4d02  mov     eax, edi
0x1800b4d04  mov     [rsp+58h+var_20], rax
0x1800b4d09  mov     rcx, rsi
0x1800b4d0c  mov     [rsp+58h+var_28], rbx
0x1800b4d11  lea     rax, [rsp+58h+arg_18]
0x1800b4d16  mov     [rsp+58h+var_30], 8
0x1800b4d1f  lea     edx, [r9-26h]
0x1800b4d23  mov     [rsp+58h+var_38], rax
0x1800b4d28  call    cs:__imp_EtwTraceMessage
0x1800b4d2e  mov     rbx, [rsp+58h+arg_0]
0x1800b4d33  mov     rsi, [rsp+58h+arg_8]
0x1800b4d38  add     rsp, 50h
0x1800b4d3c  pop     rdi
0x1800b4d3d  retn
```
