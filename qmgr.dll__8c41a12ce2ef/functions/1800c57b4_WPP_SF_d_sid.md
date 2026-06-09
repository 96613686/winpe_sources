# WPP_SF_d_sid_

- ea: `0x1800c57b4`
- end: `0x1800c5858`
- name: `WPP_SF_d_sid_`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007da90`
- `0x1800c3000`
- `0x1800c3080`

## callees

- `0x1800c57b4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800c5849`
- `ntdll!EtwTraceMessage` at `0x1800c5849`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c57d7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c57fb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c57d7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c57fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c57e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c57e4`

## pseudocode

```c
__int64 __fastcall WPP_SF_d_sid_(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, char *pSid)
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
    return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, v7, &v9, 4, v5);
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, v7, &v9, 4, v5);
}

```

## disassembly

```asm
0x1800c57b4  mov     [rsp+arg_18], r9d
0x1800c57b9  push    rbx
0x1800c57ba  push    rbp
0x1800c57bb  push    rsi
0x1800c57bc  push    rdi
0x1800c57bd  sub     rsp, 58h
0x1800c57c1  mov     rbx, [rsp+78h+pSid]
0x1800c57c9  mov     rbp, rcx
0x1800c57cc  movzx   esi, dx
0x1800c57cf  test    rbx, rbx
0x1800c57d2  jz      short loc_1800C57EE
0x1800c57d4  mov     rcx, rbx; pSid
0x1800c57d7  call    cs:__imp_IsValidSid
0x1800c57dd  test    eax, eax
0x1800c57df  jz      short loc_1800C57EE
0x1800c57e1  mov     rcx, rbx; pSid
0x1800c57e4  call    cs:__imp_GetLengthSid
0x1800c57ea  mov     edi, eax
0x1800c57ec  jmp     short loc_1800C57F8
0x1800c57ee  mov     edi, 5
0x1800c57f3  test    rbx, rbx
0x1800c57f6  jz      short loc_1800C5805
0x1800c57f8  mov     rcx, rbx; pSid
0x1800c57fb  call    cs:__imp_IsValidSid
0x1800c5801  test    eax, eax
0x1800c5803  jnz     short loc_1800C580C
0x1800c5805  lea     rbx, aNull; "NULL"
0x1800c580c  mov     [rsp+78h+var_38], 0
0x1800c5815  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800c581c  mov     eax, edi
0x1800c581e  mov     r9d, esi
0x1800c5821  mov     [rsp+78h+var_40], rax
0x1800c5826  mov     edx, 2Bh ; '+'
0x1800c582b  mov     [rsp+78h+var_48], rbx
0x1800c5830  lea     rax, [rsp+78h+arg_18]
0x1800c5838  mov     [rsp+78h+var_50], 4
0x1800c5841  mov     rcx, rbp
0x1800c5844  mov     [rsp+78h+var_58], rax
0x1800c5849  call    cs:__imp_EtwTraceMessage
0x1800c584f  add     rsp, 58h
0x1800c5853  pop     rdi
0x1800c5854  pop     rsi
0x1800c5855  pop     rbp
0x1800c5856  pop     rbx
0x1800c5857  retn
```
