# WPP_SF_S_sid_

- ea: `0x180025a8c`
- end: `0x180025b4b`
- name: `WPP_SF_S_sid_`
- size: `191`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180024754`

## callees

- `0x18000cb80`
- `0x180025a8c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180025b3a`
- `ADVAPI32!TraceMessage` at `0x180025b3a`
- `ADVAPI32!GetLengthSid` at `0x180025abf`
- `ADVAPI32!GetLengthSid` at `0x180025abf`
- `ADVAPI32!IsValidSid` at `0x180025ab2`
- `ADVAPI32!IsValidSid` at `0x180025ad3`
- `ADVAPI32!IsValidSid` at `0x180025ab2`
- `ADVAPI32!IsValidSid` at `0x180025ad3`

## pseudocode

```c
ULONG __fastcall WPP_SF_S_sid_(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, const wchar_t *a4, char *pSid)
{
  const char *v5; // rbx
  unsigned int v8; // edi
  DWORD LengthSid; // ebp

  v5 = pSid;
  v8 = 5;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( pSid )
  {
LABEL_5:
    if ( IsValidSid(pSid) )
      goto LABEL_7;
  }
  v5 = "NULL";
LABEL_7:
  if ( a4 )
    v8 = mqwcslen(a4) + 1;
  else
    a4 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_f073386f5643352810e6d9a62b947684_Traceguids,
           0x52u,
           a4,
           2LL * v8,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x180025a8c  push    rbx
0x180025a8e  push    rbp
0x180025a8f  push    rsi
0x180025a90  push    rdi
0x180025a91  push    r14
0x180025a93  sub     rsp, 50h
0x180025a97  mov     rbx, [rsp+78h+pSid]
0x180025a9f  mov     rsi, r9
0x180025aa2  mov     r14, rcx
0x180025aa5  mov     edi, 5
0x180025aaa  test    rbx, rbx
0x180025aad  jz      short loc_180025AC9
0x180025aaf  mov     rcx, rbx; pSid
0x180025ab2  call    cs:__imp_IsValidSid
0x180025ab8  test    eax, eax
0x180025aba  jz      short loc_180025AC9
0x180025abc  mov     rcx, rbx; pSid
0x180025abf  call    cs:__imp_GetLengthSid
0x180025ac5  mov     ebp, eax
0x180025ac7  jmp     short loc_180025AD0
0x180025ac9  mov     ebp, edi
0x180025acb  test    rbx, rbx
0x180025ace  jz      short loc_180025ADD
0x180025ad0  mov     rcx, rbx; pSid
0x180025ad3  call    cs:__imp_IsValidSid
0x180025ad9  test    eax, eax
0x180025adb  jnz     short loc_180025AE4
0x180025add  lea     rbx, aNull; "NULL"
0x180025ae4  test    rsi, rsi
0x180025ae7  jz      short loc_180025AF4
0x180025ae9  mov     rcx, rsi; wchar_t *
0x180025aec  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180025af1  lea     edi, [rax+1]
0x180025af4  mov     [rsp+78h+var_38], 0
0x180025afd  lea     rdx, aNull_0; "NULL"
0x180025b04  mov     eax, ebp
0x180025b06  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids; MessageGuid
0x180025b0d  mov     [rsp+78h+var_40], rax
0x180025b12  mov     r9d, 52h ; 'R'; MessageNumber
0x180025b18  mov     [rsp+78h+var_48], rbx
0x180025b1d  mov     ecx, edi
0x180025b1f  add     rcx, rcx
0x180025b22  mov     [rsp+78h+var_50], rcx
0x180025b27  test    rsi, rsi
0x180025b2a  mov     rcx, r14; LoggerHandle
0x180025b2d  cmovz   rsi, rdx
0x180025b31  lea     edx, [r9-27h]; MessageFlags
0x180025b35  mov     [rsp+78h+var_58], rsi
0x180025b3a  call    cs:__imp_TraceMessage
0x180025b40  add     rsp, 50h
0x180025b44  pop     r14
0x180025b46  pop     rdi
0x180025b47  pop     rsi
0x180025b48  pop     rbp
0x180025b49  pop     rbx
0x180025b4a  retn
```
