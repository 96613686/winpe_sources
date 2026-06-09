# AddWpgToTokenDefaultDacl(void *)

- ea: `0x180023400`
- end: `0x18002360d`
- name: `?AddWpgToTokenDefaultDacl@@YAJPEAX@Z`
- size: `525`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180023400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002348e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002348e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800234f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800234f7`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800235be`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800235be`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023547`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002356d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023593`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023547`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002356d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023593`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023520`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023520`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800234e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023432`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002347c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023432`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002347c`

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
0x180023400  mov     rax, rsp
0x180023403  mov     [rax+8], rbx
0x180023407  mov     [rax+20h], rbp
0x18002340b  push    rsi
0x18002340c  push    rdi
0x18002340d  push    r14
0x18002340f  sub     rsp, 30h
0x180023413  xor     r9d, r9d; TokenInformationLength
0x180023416  mov     dword ptr [rax+10h], 0
0x18002341d  lea     rax, [rax+10h]
0x180023421  xor     r8d, r8d; TokenInformation
0x180023424  mov     rsi, rcx
0x180023427  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002342c  lea     ebx, [r9+1]
0x180023430  mov     edx, ebx; TokenInformationClass
0x180023432  call    cs:__imp_GetTokenInformation
0x180023439  nop     dword ptr [rax+rax+00h]
0x18002343e  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180023442  lea     edi, [rbx+3Fh]
0x180023445  mov     ecx, edi; uFlags
0x180023447  call    cs:__imp_LocalAlloc
0x18002344e  nop     dword ptr [rax+rax+00h]
0x180023453  mov     r14, rax
0x180023456  test    rax, rax
0x180023459  jnz     short loc_180023465
0x18002345b  mov     ebx, 8007000Eh
0x180023460  jmp     loc_1800235F7
0x180023465  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x18002346a  lea     rax, [rsp+48h+uBytes]
0x18002346f  mov     r8, r14; TokenInformation
0x180023472  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180023477  mov     edx, ebx; TokenInformationClass
0x180023479  mov     rcx, rsi; TokenHandle
0x18002347c  call    cs:__imp_GetTokenInformation
0x180023483  nop     dword ptr [rax+rax+00h]
0x180023488  test    eax, eax
0x18002348a  jnz     short loc_1800234B2
0x18002348c  xor     edi, edi
0x18002348e  call    cs:__imp_GetLastError
0x180023495  nop     dword ptr [rax+rax+00h]
0x18002349a  mov     ebx, eax
0x18002349c  test    eax, eax
0x18002349e  jle     loc_1800235D4
0x1800234a4  movzx   ebx, ax
0x1800234a7  or      ebx, 80070000h
0x1800234ad  jmp     loc_1800235D4
0x1800234b2  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; pSid
0x1800234b9  mov     rbp, [r14]
0x1800234bc  call    cs:__imp_GetLengthSid
0x1800234c3  nop     dword ptr [rax+rax+00h]
0x1800234c8  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x1800234cf  mov     ebx, eax
0x1800234d1  call    cs:__imp_GetLengthSid
0x1800234d8  nop     dword ptr [rax+rax+00h]
0x1800234dd  mov     rcx, rbp; pSid
0x1800234e0  add     ebx, eax
0x1800234e2  call    cs:__imp_GetLengthSid
0x1800234e9  nop     dword ptr [rax+rax+00h]
0x1800234ee  add     eax, 20h ; ' '
0x1800234f1  mov     ecx, edi; uFlags
0x1800234f3  add     ebx, eax
0x1800234f5  mov     edx, ebx; uBytes
0x1800234f7  call    cs:__imp_LocalAlloc
0x1800234fe  nop     dword ptr [rax+rax+00h]
0x180023503  mov     rdi, rax
0x180023506  test    rax, rax
0x180023509  jnz     short loc_180023515
0x18002350b  mov     ebx, 8007000Eh
0x180023510  jmp     loc_1800235D4
0x180023515  mov     r8d, 2; dwAclRevision
0x18002351b  mov     edx, ebx; nAclLength
0x18002351d  mov     rcx, rdi; pAcl
0x180023520  call    cs:__imp_InitializeAcl
0x180023527  nop     dword ptr [rax+rax+00h]
0x18002352c  test    eax, eax
0x18002352e  jz      loc_18002348E
0x180023534  mov     ebx, 101F0000h
0x180023539  mov     r9, rbp; pSid
0x18002353c  mov     r8d, ebx; AccessMask
0x18002353f  mov     edx, 2; dwAceRevision
0x180023544  mov     rcx, rdi; pAcl
0x180023547  call    cs:__imp_AddAccessAllowedAce
0x18002354e  nop     dword ptr [rax+rax+00h]
0x180023553  test    eax, eax
0x180023555  jz      loc_18002348E
0x18002355b  mov     r9, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180023562  mov     r8d, ebx; AccessMask
0x180023565  mov     edx, 2; dwAceRevision
0x18002356a  mov     rcx, rdi; pAcl
0x18002356d  call    cs:__imp_AddAccessAllowedAce
0x180023574  nop     dword ptr [rax+rax+00h]
0x180023579  test    eax, eax
0x18002357b  jz      loc_18002348E
0x180023581  mov     r9, cs:?g_pSidWpg@@3PEAXEA; pSid
0x180023588  mov     r8d, ebx; AccessMask
0x18002358b  mov     edx, 2; dwAceRevision
0x180023590  mov     rcx, rdi; pAcl
0x180023593  call    cs:__imp_AddAccessAllowedAce
0x18002359a  nop     dword ptr [rax+rax+00h]
0x18002359f  test    eax, eax
0x1800235a1  jz      loc_18002348E
0x1800235a7  mov     r9d, 8; TokenInformationLength
0x1800235ad  mov     [rsp+48h+TokenInformation], rdi
0x1800235b2  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800235b7  mov     rcx, rsi; TokenHandle
0x1800235ba  lea     edx, [r9-2]; TokenInformationClass
0x1800235be  call    cs:__imp_SetTokenInformation
0x1800235c5  nop     dword ptr [rax+rax+00h]
0x1800235ca  test    eax, eax
0x1800235cc  jz      loc_18002348E
0x1800235d2  xor     ebx, ebx
0x1800235d4  mov     rcx, r14; hMem
0x1800235d7  call    cs:__imp_LocalFree
0x1800235de  nop     dword ptr [rax+rax+00h]
0x1800235e3  test    rdi, rdi
0x1800235e6  jz      short loc_1800235F7
0x1800235e8  mov     rcx, rdi; hMem
0x1800235eb  call    cs:__imp_LocalFree
0x1800235f2  nop     dword ptr [rax+rax+00h]
0x1800235f7  mov     rbp, [rsp+48h+arg_18]
0x1800235fc  mov     eax, ebx
0x1800235fe  mov     rbx, [rsp+48h+arg_0]
0x180023603  add     rsp, 30h
0x180023607  pop     r14
0x180023609  pop     rdi
0x18002360a  pop     rsi
0x18002360b  retn
```
