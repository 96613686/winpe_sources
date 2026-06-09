# WxGetTokenUserSID(void *,_SID *,ulong)

- ea: `0x1800779dc`
- end: `0x180077afb`
- name: `?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `287`
- prototype: `signed int __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f3c0`

## callees

- `0x180046ec0`
- `0x180047818`
- `0x1800779dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077ab2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a6b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a6b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180077aa8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180077aa8`

## pseudocode

```c
signed int __fastcall WxGetTokenUserSID(HANDLE TokenHandle, PSID pDestinationSid)
{
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  int v6; // [rsp+34h] [rbp-84h]
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v6 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( TokenHandle )
  {
    if ( pDestinationSid )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
      {
        if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
        {
          return 0;
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
          v6 = 32;
          if ( result >= 0 )
            return -2147418113;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        v6 = 31;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      result = -2147024809;
      v6 = 28;
    }
  }
  else
  {
    result = -2147024809;
    v6 = 27;
  }
  return result;
}

```

## disassembly

```asm
0x1800779dc  mov     [rsp+arg_10], rbx
0x1800779e1  push    rdi
0x1800779e2  sub     rsp, 0B0h
0x1800779e9  mov     rax, cs:__security_cookie
0x1800779f0  xor     rax, rsp
0x1800779f3  mov     [rsp+0B8h+var_18], rax
0x1800779fb  mov     rbx, rdx
0x1800779fe  mov     [rsp+0B8h+var_84], 0
0x180077a06  xor     edx, edx; Val
0x180077a08  mov     rdi, rcx
0x180077a0b  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x180077a10  lea     r8d, [rdx+58h]; Size
0x180077a14  call    memset_0
0x180077a19  mov     [rsp+0B8h+var_88], 0
0x180077a21  test    rdi, rdi
0x180077a24  jnz     short loc_180077A38
0x180077a26  mov     eax, 80070057h
0x180077a2b  mov     [rsp+0B8h+var_84], 1Bh
0x180077a33  jmp     loc_180077ADA
0x180077a38  test    rbx, rbx
0x180077a3b  jnz     short loc_180077A4F
0x180077a3d  mov     eax, 80070057h
0x180077a42  mov     [rsp+0B8h+var_84], 1Ch
0x180077a4a  jmp     loc_180077ADA
0x180077a4f  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180077a55  lea     rax, [rsp+0B8h+var_88]
0x180077a5a  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180077a5f  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180077a64  mov     rcx, rdi; TokenHandle
0x180077a67  lea     edx, [r9-57h]; TokenInformationClass
0x180077a6b  call    cs:__imp_GetTokenInformation
0x180077a71  test    eax, eax
0x180077a73  jnz     short loc_180077A9B
0x180077a75  call    cs:__imp_GetLastError
0x180077a7b  test    eax, eax
0x180077a7d  jle     short loc_180077A87
0x180077a7f  movzx   eax, ax
0x180077a82  or      eax, 80070000h
0x180077a87  test    eax, eax
0x180077a89  mov     [rsp+0B8h+var_84], 1Fh
0x180077a91  mov     ecx, 8000FFFFh
0x180077a96  cmovns  eax, ecx
0x180077a99  jmp     short loc_180077ADA
0x180077a9b  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x180077aa0  mov     rdx, rbx; pDestinationSid
0x180077aa3  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180077aa8  call    cs:__imp_CopySid
0x180077aae  test    eax, eax
0x180077ab0  jnz     short loc_180077AD8
0x180077ab2  call    cs:__imp_GetLastError
0x180077ab8  test    eax, eax
0x180077aba  jle     short loc_180077AC4
0x180077abc  movzx   eax, ax
0x180077abf  or      eax, 80070000h
0x180077ac4  test    eax, eax
0x180077ac6  mov     [rsp+0B8h+var_84], 20h ; ' '
0x180077ace  mov     ecx, 8000FFFFh
0x180077ad3  cmovns  eax, ecx
0x180077ad6  jmp     short loc_180077ADA
0x180077ad8  xor     eax, eax
0x180077ada  mov     rcx, [rsp+0B8h+var_18]
0x180077ae2  xor     rcx, rsp; StackCookie
0x180077ae5  call    __security_check_cookie
0x180077aea  mov     rbx, [rsp+0B8h+arg_10]
0x180077af2  add     rsp, 0B0h
0x180077af9  pop     rdi
0x180077afa  retn
```
