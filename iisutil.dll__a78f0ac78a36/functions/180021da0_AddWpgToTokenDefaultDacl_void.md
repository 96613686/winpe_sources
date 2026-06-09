# AddWpgToTokenDefaultDacl(void *)

- ea: `0x180021da0`
- end: `0x180021f4e`
- name: `?AddWpgToTokenDefaultDacl@@YAJPEAX@Z`
- size: `430`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021de1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021de1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e6d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180021f12`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180021f12`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021ead`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021ecd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021eed`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021ead`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021ecd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180021eed`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180021e90`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180021e90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e44`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e53`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e5e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e44`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e53`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021e5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021dd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021e10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021dd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021e10`

## pseudocode

```c
__int64 __fastcall AddWpgToTokenDefaultDacl(HANDLE TokenHandle)
{
  void **v2; // r14
  unsigned int v3; // ebx
  struct _ACL *v4; // rdi
  signed int LastError; // eax
  void *v6; // rbp
  DWORD LengthSid; // ebx
  DWORD v8; // ebx
  DWORD v9; // ebx
  struct _ACL *v10; // rax
  SIZE_T uBytes; // [rsp+58h] [rbp+10h] BYREF
  struct _ACL *TokenInformation; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes);
  v2 = (void **)LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( !v2 )
    return (unsigned int)-2147024882;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v2, uBytes, (PDWORD)&uBytes) )
  {
    v4 = 0;
    goto LABEL_5;
  }
  v6 = *v2;
  LengthSid = GetLengthSid(g_pSidWpg);
  v8 = GetLengthSid(g_pSidLocalSystem) + LengthSid;
  v9 = GetLengthSid(v6) + 32 + v8;
  v10 = (struct _ACL *)LocalAlloc(0x40u, v9);
  v4 = v10;
  if ( v10 )
  {
    if ( !InitializeAcl(v10, v9, 2u)
      || !AddAccessAllowedAce(v4, 2u, 0x101F0000u, v6)
      || !AddAccessAllowedAce(v4, 2u, 0x101F0000u, g_pSidLocalSystem)
      || !AddAccessAllowedAce(v4, 2u, 0x101F0000u, g_pSidWpg)
      || (TokenInformation = v4, !SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u)) )
    {
LABEL_5:
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_15;
    }
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_15:
  LocalFree(v2);
  if ( v4 )
    LocalFree(v4);
  return v3;
}

```

## disassembly

```asm
0x180021da0  mov     rax, rsp
0x180021da3  mov     [rax+8], rbx
0x180021da7  mov     [rax+20h], rbp
0x180021dab  push    rsi
0x180021dac  push    rdi
0x180021dad  push    r14
0x180021daf  sub     rsp, 30h
0x180021db3  xor     r9d, r9d; TokenInformationLength
0x180021db6  mov     dword ptr [rax+10h], 0
0x180021dbd  lea     rax, [rax+10h]
0x180021dc1  xor     r8d, r8d; TokenInformation
0x180021dc4  mov     rsi, rcx
0x180021dc7  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180021dcc  lea     ebx, [r9+1]
0x180021dd0  mov     edx, ebx; TokenInformationClass
0x180021dd2  call    cs:__imp_GetTokenInformation
0x180021dd8  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180021ddc  lea     edi, [rbx+3Fh]
0x180021ddf  mov     ecx, edi; uFlags
0x180021de1  call    cs:__imp_LocalAlloc
0x180021de7  mov     r14, rax
0x180021dea  test    rax, rax
0x180021ded  jnz     short loc_180021DF9
0x180021def  mov     ebx, 8007000Eh
0x180021df4  jmp     loc_180021F39
0x180021df9  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x180021dfe  lea     rax, [rsp+48h+uBytes]
0x180021e03  mov     r8, r14; TokenInformation
0x180021e06  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180021e0b  mov     edx, ebx; TokenInformationClass
0x180021e0d  mov     rcx, rsi; TokenHandle
0x180021e10  call    cs:__imp_GetTokenInformation
0x180021e16  test    eax, eax
0x180021e18  jnz     short loc_180021E3A
0x180021e1a  xor     edi, edi
0x180021e1c  call    cs:__imp_GetLastError
0x180021e22  mov     ebx, eax
0x180021e24  test    eax, eax
0x180021e26  jle     loc_180021F22
0x180021e2c  movzx   ebx, ax
0x180021e2f  or      ebx, 80070000h
0x180021e35  jmp     loc_180021F22
0x180021e3a  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; pSid
0x180021e41  mov     rbp, [r14]
0x180021e44  call    cs:__imp_GetLengthSid
0x180021e4a  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180021e51  mov     ebx, eax
0x180021e53  call    cs:__imp_GetLengthSid
0x180021e59  mov     rcx, rbp; pSid
0x180021e5c  add     ebx, eax
0x180021e5e  call    cs:__imp_GetLengthSid
0x180021e64  add     eax, 20h ; ' '
0x180021e67  mov     ecx, edi; uFlags
0x180021e69  add     ebx, eax
0x180021e6b  mov     edx, ebx; uBytes
0x180021e6d  call    cs:__imp_LocalAlloc
0x180021e73  mov     rdi, rax
0x180021e76  test    rax, rax
0x180021e79  jnz     short loc_180021E85
0x180021e7b  mov     ebx, 8007000Eh
0x180021e80  jmp     loc_180021F22
0x180021e85  mov     r8d, 2; dwAclRevision
0x180021e8b  mov     edx, ebx; nAclLength
0x180021e8d  mov     rcx, rdi; pAcl
0x180021e90  call    cs:__imp_InitializeAcl
0x180021e96  test    eax, eax
0x180021e98  jz      short loc_180021E1C
0x180021e9a  mov     ebx, 101F0000h
0x180021e9f  mov     r9, rbp; pSid
0x180021ea2  mov     r8d, ebx; AccessMask
0x180021ea5  mov     edx, 2; dwAceRevision
0x180021eaa  mov     rcx, rdi; pAcl
0x180021ead  call    cs:__imp_AddAccessAllowedAce
0x180021eb3  test    eax, eax
0x180021eb5  jz      loc_180021E1C
0x180021ebb  mov     r9, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180021ec2  mov     r8d, ebx; AccessMask
0x180021ec5  mov     edx, 2; dwAceRevision
0x180021eca  mov     rcx, rdi; pAcl
0x180021ecd  call    cs:__imp_AddAccessAllowedAce
0x180021ed3  test    eax, eax
0x180021ed5  jz      loc_180021E1C
0x180021edb  mov     r9, cs:?g_pSidWpg@@3PEAXEA; pSid
0x180021ee2  mov     r8d, ebx; AccessMask
0x180021ee5  mov     edx, 2; dwAceRevision
0x180021eea  mov     rcx, rdi; pAcl
0x180021eed  call    cs:__imp_AddAccessAllowedAce
0x180021ef3  test    eax, eax
0x180021ef5  jz      loc_180021E1C
0x180021efb  mov     r9d, 8; TokenInformationLength
0x180021f01  mov     [rsp+48h+TokenInformation], rdi
0x180021f06  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180021f0b  mov     rcx, rsi; TokenHandle
0x180021f0e  lea     edx, [r9-2]; TokenInformationClass
0x180021f12  call    cs:__imp_SetTokenInformation
0x180021f18  test    eax, eax
0x180021f1a  jz      loc_180021E1C
0x180021f20  xor     ebx, ebx
0x180021f22  mov     rcx, r14; hMem
0x180021f25  call    cs:__imp_LocalFree
0x180021f2b  test    rdi, rdi
0x180021f2e  jz      short loc_180021F39
0x180021f30  mov     rcx, rdi; hMem
0x180021f33  call    cs:__imp_LocalFree
0x180021f39  mov     rbp, [rsp+48h+arg_18]
0x180021f3e  mov     eax, ebx
0x180021f40  mov     rbx, [rsp+48h+arg_0]
0x180021f45  add     rsp, 30h
0x180021f49  pop     r14
0x180021f4b  pop     rdi
0x180021f4c  pop     rsi
0x180021f4d  retn
```
