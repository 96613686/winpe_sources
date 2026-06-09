# WPP_SF_dD_sid_

- ea: `0x1800c56e4`
- end: `0x1800c57ae`
- name: `WPP_SF_dD_sid_`
- size: `202`
- prototype: `__int64 __fastcall(int, int, int, int, char, PSID pSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018880`
- `0x180027d18`

## callees

- `0x1800c56e4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800c5793`
- `ntdll!EtwTraceMessage` at `0x1800c5793`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5714`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5738`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5714`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5738`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c5721`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c5721`

## pseudocode

```c
__int64 __fastcall WPP_SF_dD_sid_(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, char a5, PSID pSid)
{
  PSID v6; // rbx
  unsigned int v8; // ebp
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v6 = pSid;
  v8 = a2;
  if ( pSid && IsValidSid(pSid) )
  {
    GetLengthSid(v6);
LABEL_5:
    IsValidSid(v6);
    return EtwTraceMessage(a1, 43, a3, v8, &v11, 4, &a5);
  }
  if ( v6 )
    goto LABEL_5;
  return EtwTraceMessage(a1, 43, a3, v8, &v11, 4, &a5);
}

```

## disassembly

```asm
0x1800c56e4  mov     [rsp+arg_0], rbx
0x1800c56e9  mov     [rsp+arg_8], rbp
0x1800c56ee  mov     [rsp+arg_18], r9d
0x1800c56f3  push    rsi
0x1800c56f4  push    rdi
0x1800c56f5  push    r14
0x1800c56f7  sub     rsp, 60h
0x1800c56fb  mov     rbx, [rsp+78h+pSid]
0x1800c5703  mov     rsi, r8
0x1800c5706  movzx   ebp, dx
0x1800c5709  mov     r14, rcx
0x1800c570c  test    rbx, rbx
0x1800c570f  jz      short loc_1800C572B
0x1800c5711  mov     rcx, rbx; pSid
0x1800c5714  call    cs:__imp_IsValidSid
0x1800c571a  test    eax, eax
0x1800c571c  jz      short loc_1800C572B
0x1800c571e  mov     rcx, rbx; pSid
0x1800c5721  call    cs:__imp_GetLengthSid
0x1800c5727  mov     edi, eax
0x1800c5729  jmp     short loc_1800C5735
0x1800c572b  mov     edi, 5
0x1800c5730  test    rbx, rbx
0x1800c5733  jz      short loc_1800C5742
0x1800c5735  mov     rcx, rbx; pSid
0x1800c5738  call    cs:__imp_IsValidSid
0x1800c573e  test    eax, eax
0x1800c5740  jnz     short loc_1800C5749
0x1800c5742  lea     rbx, aNull; "NULL"
0x1800c5749  mov     [rsp+78h+var_28], 0
0x1800c5752  mov     ecx, 4
0x1800c5757  mov     eax, edi
0x1800c5759  mov     r9d, ebp
0x1800c575c  mov     [rsp+78h+var_30], rax
0x1800c5761  mov     r8, rsi
0x1800c5764  mov     [rsp+78h+var_38], rbx
0x1800c5769  lea     rax, [rsp+78h+arg_20]
0x1800c5771  mov     [rsp+78h+var_40], rcx
0x1800c5776  lea     edx, [rcx+27h]
0x1800c5779  mov     [rsp+78h+var_48], rax
0x1800c577e  lea     rax, [rsp+78h+arg_18]
0x1800c5786  mov     [rsp+78h+var_50], rcx
0x1800c578b  mov     rcx, r14
0x1800c578e  mov     [rsp+78h+var_58], rax
0x1800c5793  call    cs:__imp_EtwTraceMessage
0x1800c5799  lea     r11, [rsp+78h+var_18]
0x1800c579e  mov     rbx, [r11+20h]
0x1800c57a2  mov     rbp, [r11+28h]
0x1800c57a6  mov     rsp, r11
0x1800c57a9  pop     r14
0x1800c57ab  pop     rdi
0x1800c57ac  pop     rsi
0x1800c57ad  retn
```
