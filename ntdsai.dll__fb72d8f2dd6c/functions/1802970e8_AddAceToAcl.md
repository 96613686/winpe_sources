# AddAceToAcl

- ea: `0x1802970e8`
- end: `0x180297255`
- name: `AddAceToAcl`
- size: `365`
- prototype: `__int64 __fastcall(PACL pAcl, PSID pSid, DWORD AccessMask)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18029725c`

## callees

- `0x18000ef30`
- `0x18001e090`
- `0x1802970e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180297169`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180297169`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1802971c7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1802971c7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18029720b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18029720b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18029713b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180297158`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18029713b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180297158`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1802971b4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1802971b4`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802971f3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802971f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297215`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180297198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180297198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180297229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180297229`

## pseudocode

```c
__int64 __fastcall AddAceToAcl(PACL pAcl, PSID pSid, DWORD AccessMask, struct _ACL **a4)
{
  struct _ACL *v4; // rdi
  DWORD LengthSid; // eax
  DWORD LastError; // ebx
  unsigned int v11; // eax
  DWORD v12; // r15d
  struct _ACL *v13; // rax
  DWORD dwAclRevision; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-30h] BYREF
  __int64 pAclInformation; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+48h] [rbp-20h]

  pAce = 0;
  v4 = 0;
  pAclInformation = 0;
  *a4 = 0;
  v18 = 0;
  dwAclRevision = 0;
  if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation)
    && GetAclInformation(pAcl, &dwAclRevision, 4u, AclRevisionInformation) )
  {
    LengthSid = GetLengthSid(pSid);
    LastError = 8;
    v11 = DsaSafeAdd(8, LengthSid);
    v12 = DsaSafeAdd(v11, HIDWORD(pAclInformation));
    DsaSafeAdd((unsigned int)pAclInformation, 1);
    v13 = (struct _ACL *)LocalAlloc(0, v12);
    v4 = v13;
    if ( !v13 )
      return LastError;
    if ( InitializeAcl(v13, v12, dwAclRevision) && GetAce(pAcl, 0, &pAce) )
    {
      if ( HIDWORD(pAclInformation) < 8 )
      {
        LastError = 1336;
LABEL_12:
        LocalFree(v4);
        return LastError;
      }
      if ( AddAce(v4, dwAclRevision, 0, pAce, HIDWORD(pAclInformation) - 8)
        && AddAccessAllowedAce(v4, 2u, AccessMask, pSid) )
      {
        LastError = 0;
        *a4 = v4;
        return LastError;
      }
    }
  }
  LastError = GetLastError();
  if ( LastError && v4 )
    goto LABEL_12;
  return LastError;
}

```

## disassembly

```asm
0x1802970e8  push    rbp
0x1802970ea  push    rbx
0x1802970eb  push    rsi
0x1802970ec  push    rdi
0x1802970ed  push    r12
0x1802970ef  push    r13
0x1802970f1  push    r14
0x1802970f3  push    r15
0x1802970f5  mov     rbp, rsp
0x1802970f8  sub     rsp, 68h
0x1802970fc  mov     rax, cs:__security_cookie
0x180297103  xor     rax, rsp
0x180297106  mov     [rbp+var_18], rax
0x18029710a  xor     eax, eax
0x18029710c  mov     [rbp+pAce], 0
0x180297114  xor     edi, edi
0x180297116  mov     [rbp+pAclInformation], rax
0x18029711a  mov     r14, r9
0x18029711d  mov     [r9], rdi
0x180297120  mov     r13d, r8d
0x180297123  mov     [rbp+var_20], eax
0x180297126  mov     r12, rdx
0x180297129  mov     [rbp+dwAclRevision], eax
0x18029712c  lea     r9d, [rdi+2]; dwAclInformationClass
0x180297130  mov     rsi, rcx
0x180297133  lea     r8d, [rdi+0Ch]; nAclInformationLength
0x180297137  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18029713b  call    cs:__imp_GetAclInformation
0x180297141  test    eax, eax
0x180297143  jz      loc_180297215
0x180297149  lea     r9d, [rdi+1]; dwAclInformationClass
0x18029714d  mov     rcx, rsi; pAcl
0x180297150  lea     r8d, [rdi+4]; nAclInformationLength
0x180297154  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x180297158  call    cs:__imp_GetAclInformation
0x18029715e  test    eax, eax
0x180297160  jz      loc_180297215
0x180297166  mov     rcx, r12; pSid
0x180297169  call    cs:__imp_GetLengthSid
0x18029716f  lea     ebx, [rdi+8]
0x180297172  mov     edx, eax
0x180297174  mov     ecx, ebx
0x180297176  call    DsaSafeAdd
0x18029717b  mov     edx, dword ptr [rbp+pAclInformation+4]
0x18029717e  mov     ecx, eax
0x180297180  call    DsaSafeAdd
0x180297185  mov     ecx, dword ptr [rbp+pAclInformation]
0x180297188  lea     edx, [rdi+1]
0x18029718b  mov     r15d, eax
0x18029718e  call    DsaSafeAdd
0x180297193  mov     edx, r15d; uBytes
0x180297196  xor     ecx, ecx; uFlags
0x180297198  call    cs:__imp_LocalAlloc
0x18029719e  mov     rdi, rax
0x1802971a1  test    rax, rax
0x1802971a4  jz      loc_180297236
0x1802971aa  mov     r8d, [rbp+dwAclRevision]; dwAclRevision
0x1802971ae  mov     edx, r15d; nAclLength
0x1802971b1  mov     rcx, rax; pAcl
0x1802971b4  call    cs:__imp_InitializeAcl
0x1802971ba  test    eax, eax
0x1802971bc  jz      short loc_180297215
0x1802971be  lea     r8, [rbp+pAce]; pAce
0x1802971c2  xor     edx, edx; dwAceIndex
0x1802971c4  mov     rcx, rsi; pAcl
0x1802971c7  call    cs:__imp_GetAce
0x1802971cd  test    eax, eax
0x1802971cf  jz      short loc_180297215
0x1802971d1  mov     eax, dword ptr [rbp+pAclInformation+4]
0x1802971d4  cmp     eax, ebx
0x1802971d6  jnb     short loc_1802971DF
0x1802971d8  mov     ebx, 538h
0x1802971dd  jmp     short loc_180297226
0x1802971df  mov     r9, [rbp+pAce]; pAceList
0x1802971e3  add     eax, 0FFFFFFF8h
0x1802971e6  mov     edx, [rbp+dwAclRevision]; dwAceRevision
0x1802971e9  xor     r8d, r8d; dwStartingAceIndex
0x1802971ec  mov     rcx, rdi; pAcl
0x1802971ef  mov     [rsp+68h+nAceListLength], eax; nAceListLength
0x1802971f3  call    cs:__imp_AddAce
0x1802971f9  test    eax, eax
0x1802971fb  jz      short loc_180297215
0x1802971fd  mov     r9, r12; pSid
0x180297200  mov     r8d, r13d; AccessMask
0x180297203  mov     edx, 2; dwAceRevision
0x180297208  mov     rcx, rdi; pAcl
0x18029720b  call    cs:__imp_AddAccessAllowedAce
0x180297211  test    eax, eax
0x180297213  jnz     short loc_180297231
0x180297215  call    cs:__imp_GetLastError
0x18029721b  mov     ebx, eax
0x18029721d  test    eax, eax
0x18029721f  jz      short loc_180297236
0x180297221  test    rdi, rdi
0x180297224  jz      short loc_180297236
0x180297226  mov     rcx, rdi; hMem
0x180297229  call    cs:__imp_LocalFree
0x18029722f  jmp     short loc_180297236
0x180297231  xor     ebx, ebx
0x180297233  mov     [r14], rdi
0x180297236  mov     eax, ebx
0x180297238  mov     rcx, [rbp+var_18]
0x18029723c  xor     rcx, rsp; StackCookie
0x18029723f  call    __security_check_cookie
0x180297244  add     rsp, 68h
0x180297248  pop     r15
0x18029724a  pop     r14
0x18029724c  pop     r13
0x18029724e  pop     r12
0x180297250  pop     rdi
0x180297251  pop     rsi
0x180297252  pop     rbx
0x180297253  pop     rbp
0x180297254  retn
```
