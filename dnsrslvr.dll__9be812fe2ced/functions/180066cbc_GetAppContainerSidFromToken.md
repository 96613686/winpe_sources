# GetAppContainerSidFromToken

- ea: `0x180066cbc`
- end: `0x180066dff`
- name: `GetAppContainerSidFromToken`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066e08`

## callees

- `0x180046ec0`
- `0x180066cbc`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066d31`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066d31`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180066d85`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180066d85`

## pseudocode

```c
__int64 __fastcall GetAppContainerSidFromToken(HANDLE TokenHandle, PSID pDestinationSid)
{
  DWORD v2; // r9d
  signed int v5; // eax
  signed int v6; // ebx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+38h] [rbp-70h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  v2 = 76;
  TokenInformationLength = 76;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_q(1035, 15, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, TokenHandle);
    v2 = TokenInformationLength;
  }
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, v2, &TokenInformationLength) )
  {
    if ( TokenInformation[0] )
    {
      if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147418113;
      }
    }
    else
    {
      v6 = -2147418113;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180066cbc  mov     [rsp+arg_10], rbx
0x180066cc1  push    rdi
0x180066cc2  sub     rsp, 0A0h
0x180066cc9  mov     rax, cs:__security_cookie
0x180066cd0  xor     rax, rsp
0x180066cd3  mov     [rsp+0A8h+var_18], rax
0x180066cdb  mov     r9d, 4Ch ; 'L'
0x180066ce1  mov     [rsp+0A8h+var_74], 0
0x180066ce9  mov     [rsp+0A8h+TokenInformationLength], r9d
0x180066cee  mov     rdi, rdx
0x180066cf1  mov     rbx, rcx
0x180066cf4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180066cfb  jz      short loc_180066D1A
0x180066cfd  lea     edx, [r9-3Dh]
0x180066d01  mov     ecx, 40Bh
0x180066d06  mov     r9, rbx
0x180066d09  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180066d10  call    WPP_SF_q
0x180066d15  mov     r9d, [rsp+0A8h+TokenInformationLength]; TokenInformationLength
0x180066d1a  lea     rax, [rsp+0A8h+TokenInformationLength]
0x180066d1f  mov     edx, 1Fh; TokenInformationClass
0x180066d24  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180066d29  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x180066d2e  mov     rcx, rbx; TokenHandle
0x180066d31  call    cs:__imp_GetTokenInformation
0x180066d37  test    eax, eax
0x180066d39  jnz     short loc_180066D64
0x180066d3b  call    cs:__imp_GetLastError
0x180066d41  mov     ebx, eax
0x180066d43  test    eax, eax
0x180066d45  jle     short loc_180066D50
0x180066d47  movzx   ebx, ax
0x180066d4a  or      ebx, 80070000h
0x180066d50  test    ebx, ebx
0x180066d52  mov     [rsp+0A8h+var_74], 122h
0x180066d5a  mov     eax, 8000FFFFh
0x180066d5f  cmovns  ebx, eax
0x180066d62  jmp     short loc_180066DBA
0x180066d64  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x180066d69  test    r8, r8
0x180066d6c  jnz     short loc_180066D7D
0x180066d6e  mov     ebx, 8000FFFFh
0x180066d73  mov     [rsp+0A8h+var_74], 124h
0x180066d7b  jmp     short loc_180066DBA
0x180066d7d  mov     rdx, rdi; pDestinationSid
0x180066d80  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180066d85  call    cs:__imp_CopySid
0x180066d8b  test    eax, eax
0x180066d8d  jnz     short loc_180066DB8
0x180066d8f  call    cs:__imp_GetLastError
0x180066d95  mov     ebx, eax
0x180066d97  test    eax, eax
0x180066d99  jle     short loc_180066DA4
0x180066d9b  movzx   ebx, ax
0x180066d9e  or      ebx, 80070000h
0x180066da4  test    ebx, ebx
0x180066da6  mov     [rsp+0A8h+var_74], 128h
0x180066dae  mov     eax, 8000FFFFh
0x180066db3  cmovns  ebx, eax
0x180066db6  jmp     short loc_180066DBA
0x180066db8  xor     ebx, ebx
0x180066dba  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180066dc1  jz      short loc_180066DDC
0x180066dc3  mov     edx, 10h
0x180066dc8  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180066dcf  mov     ecx, 40Bh
0x180066dd4  mov     r9d, ebx
0x180066dd7  call    WPP_SF_d
0x180066ddc  mov     eax, ebx
0x180066dde  mov     rcx, [rsp+0A8h+var_18]
0x180066de6  xor     rcx, rsp; StackCookie
0x180066de9  call    __security_check_cookie
0x180066dee  mov     rbx, [rsp+0A8h+arg_10]
0x180066df6  add     rsp, 0A0h
0x180066dfd  pop     rdi
0x180066dfe  retn
```
