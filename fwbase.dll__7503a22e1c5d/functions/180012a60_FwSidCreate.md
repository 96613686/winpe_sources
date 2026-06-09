# FwSidCreate

- ea: `0x180012a60`
- end: `0x180012b04`
- name: `FwSidCreate`
- size: `164`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0, DWORD nSubAuthority1, PSID *pSid)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180012a60`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012ab1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012ab1`

## string_xrefs

- `0x180012ad9`: `AllocateAndInitializeSid`
- `0x180012ae0`: `FwSidCreate`
- `0x180012af4`: `FwSidCreate`

## pseudocode

```c
__int64 __fastcall FwSidCreate(DWORD nSubAuthority0, DWORD nSubAuthority1, PSID *pSid)
{
  unsigned int v3; // ebx
  DWORD LastError; // eax
  int v6; // eax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          (nSubAuthority1 != 0) + 1,
          nSubAuthority0,
          nSubAuthority1,
          0,
          0,
          0,
          0,
          0,
          0,
          pSid) )
  {
    LastError = GetLastError();
    v6 = FwReportErrorAsWinError("FwSidCreate", "AllocateAndInitializeSid", LastError);
    v3 = v6;
    if ( v6 < 0 )
      return (unsigned int)FwReportReturnError("FwSidCreate", (unsigned int)v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180012a60  push    rbx
0x180012a62  sub     rsp, 70h
0x180012a66  mov     rax, cs:__security_cookie
0x180012a6d  xor     rax, rsp
0x180012a70  mov     [rsp+78h+var_10], rax
0x180012a75  xor     ebx, ebx
0x180012a77  mov     [rsp+78h+pSid], r8; pSid
0x180012a7c  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x180012a80  test    edx, edx
0x180012a82  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x180012a86  mov     r9d, edx; nSubAuthority1
0x180012a89  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x180012a8d  setnz   dl
0x180012a90  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x180012a94  mov     r8d, ecx; nSubAuthority0
0x180012a97  inc     dl; nSubAuthorityCount
0x180012a99  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x180012a9d  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x180012aa2  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x180012aa6  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 500h
0x180012aad  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x180012ab1  call    cs:__imp_AllocateAndInitializeSid
0x180012ab7  test    eax, eax
0x180012ab9  jz      short loc_180012AD0
0x180012abb  mov     eax, ebx
0x180012abd  mov     rcx, [rsp+78h+var_10]
0x180012ac2  xor     rcx, rsp; StackCookie
0x180012ac5  call    __security_check_cookie
0x180012aca  add     rsp, 70h
0x180012ace  pop     rbx
0x180012acf  retn
0x180012ad0  call    cs:__imp_GetLastError
0x180012ad6  mov     r8d, eax
0x180012ad9  lea     rdx, aAllocateandini; "AllocateAndInitializeSid"
0x180012ae0  lea     rcx, aFwsidcreate_0; "FwSidCreate"
0x180012ae7  call    FwReportErrorAsWinError
0x180012aec  mov     ebx, eax
0x180012aee  test    eax, eax
0x180012af0  jns     short loc_180012ABB
0x180012af2  mov     edx, eax
0x180012af4  lea     rcx, aFwsidcreate_0; "FwSidCreate"
0x180012afb  call    FwReportReturnError
0x180012b00  mov     ebx, eax
0x180012b02  jmp     short loc_180012ABB
```
