# CITransaction::GetTransactionSecurityAttributes(_SECURITY_ATTRIBUTES * *)

- ea: `0x180029434`
- end: `0x180029629`
- name: `?GetTransactionSecurityAttributes@CITransaction@@SAJPEAPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `501`
- prototype: `static int(struct _SECURITY_ATTRIBUTES **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002847c`
- `0x180042ca0`

## callees

- `0x18001d178`
- `0x18001d184`
- `0x180029434`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029547`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800294cb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800294cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029588`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800295de`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029588`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800295de`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002953d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002953d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029527`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029597`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029597`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e8`
- `ADVAPI32!SetEntriesInAclA` at `0x180029508`
- `ADVAPI32!SetEntriesInAclA` at `0x180029508`

## pseudocode

```c
__int64 __fastcall CITransaction::GetTransactionSecurityAttributes(struct _SECURITY_ATTRIBUTES **a1)
{
  void *v2; // rsi
  struct _SECURITY_ATTRIBUTES *v3; // rdi
  void *v4; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  struct _SECURITY_ATTRIBUTES *v7; // rax
  PSID pSid; // [rsp+60h] [rbp-29h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-21h] BYREF
  _EXPLICIT_ACCESS_A pListOfExplicitEntries; // [rsp+70h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+17h] BYREF

  pSid = 0;
  NewAcl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( CITransaction::ms_pSecurityAttributes )
    goto LABEL_23;
  v2 = 0;
  v3 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    pListOfExplicitEntries.Trustee.ptstrName = (LPCH)pSid;
    pListOfExplicitEntries.grfAccessPermissions = 1179703;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    if ( !SetEntriesInAclA(1u, &pListOfExplicitEntries, 0, &NewAcl) )
    {
      v4 = operator new[](0x28u);
      v2 = v4;
      if ( !v4 )
        goto LABEL_12;
      if ( !InitializeSecurityDescriptor(v4, 1u) || !SetSecurityDescriptorDacl(v2, 1, NewAcl, 0) )
        goto LABEL_7;
      v7 = (struct _SECURITY_ATTRIBUTES *)operator new[](0x18u);
      v3 = v7;
      if ( !v7 )
      {
LABEL_12:
        v6 = -2147024882;
LABEL_13:
        if ( pSid )
          FreeSid(pSid);
        if ( NewAcl )
          LocalFree(NewAcl);
        if ( v2 )
          operator delete(v2);
        if ( v3 )
          operator delete(v3);
        return v6;
      }
      v7->bInheritHandle = 0;
      v7->lpSecurityDescriptor = v2;
      v7->nLength = 24;
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&CITransaction::ms_pSecurityAttributes,
        (signed __int64)v7,
        0);
      if ( CITransaction::ms_pSecurityAttributes != v7 )
      {
        FreeSid(pSid);
        LocalFree(NewAcl);
        operator delete(v2);
        operator delete(v3);
      }
LABEL_23:
      v6 = 0;
      *a1 = CITransaction::ms_pSecurityAttributes;
      return v6;
    }
  }
LABEL_7:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_13;
  return v6;
}

```

## disassembly

```asm
0x180029434  push    rbp
0x180029436  push    rbx
0x180029437  push    rsi
0x180029438  push    rdi
0x180029439  push    r14
0x18002943b  push    r15
0x18002943d  lea     rbp, [rsp-2Fh]
0x180029442  sub     rsp, 0B8h
0x180029449  mov     rax, cs:__security_cookie
0x180029450  xor     rax, rsp
0x180029453  mov     [rbp+57h+var_38], rax
0x180029457  mov     rax, cs:?ms_pSecurityAttributes@CITransaction@@0REAU_SECURITY_ATTRIBUTES@@EA; _SECURITY_ATTRIBUTES * CITransaction::ms_pSecurityAttributes
0x18002945e  xor     r15d, r15d
0x180029461  mov     [rbp+57h+var_80], r15
0x180029465  xorps   xmm0, xmm0
0x180029468  mov     [rbp+57h+NewAcl], r15
0x18002946c  mov     r14, rcx
0x18002946f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x180029473  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x180029479  lea     ebx, [r15+1]
0x18002947d  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180029481  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180029485  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180029489  test    rax, rax
0x18002948c  jnz     loc_1800295FE
0x180029492  lea     rax, [rbp+57h+var_80]
0x180029496  xor     r9d, r9d; nSubAuthority1
0x180029499  mov     [rsp+0E0h+pSid], rax; pSid
0x18002949e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800294a2  mov     [rsp+0E0h+nSubAuthority7], r15d; nSubAuthority7
0x1800294a7  xor     r8d, r8d; nSubAuthority0
0x1800294aa  mov     [rsp+0E0h+nSubAuthority6], r15d; nSubAuthority6
0x1800294af  mov     dl, bl; nSubAuthorityCount
0x1800294b1  mov     [rsp+0E0h+nSubAuthority5], r15d; nSubAuthority5
0x1800294b6  mov     esi, r15d
0x1800294b9  mov     [rsp+0E0h+nSubAuthority4], r15d; nSubAuthority4
0x1800294be  mov     edi, r15d
0x1800294c1  mov     [rsp+0E0h+nSubAuthority3], r15d; nSubAuthority3
0x1800294c6  mov     [rsp+0E0h+nSubAuthority2], r15d; nSubAuthority2
0x1800294cb  call    cs:__imp_AllocateAndInitializeSid
0x1800294d1  test    eax, eax
0x1800294d3  jz      short loc_180029547
0x1800294d5  mov     rax, [rbp+57h+var_80]
0x1800294d9  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800294dd  xor     r8d, r8d; OldAcl
0x1800294e0  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800294e4  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800294e8  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 120037h
0x1800294ef  mov     ecx, ebx; cCountOfExplicitEntries
0x1800294f1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800294f9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r15
0x1800294fd  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r15
0x180029501  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180029508  call    cs:__imp_SetEntriesInAclA
0x18002950e  test    eax, eax
0x180029510  jnz     short loc_180029547
0x180029512  lea     ecx, [rbx+27h]; unsigned __int64
0x180029515  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002951a  mov     rsi, rax
0x18002951d  test    rax, rax
0x180029520  jz      short loc_18002957A
0x180029522  mov     edx, ebx; dwRevision
0x180029524  mov     rcx, rax; pSecurityDescriptor
0x180029527  call    cs:__imp_InitializeSecurityDescriptor
0x18002952d  test    eax, eax
0x18002952f  jz      short loc_180029547
0x180029531  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180029535  xor     r9d, r9d; bDaclDefaulted
0x180029538  mov     edx, ebx; bDaclPresent
0x18002953a  mov     rcx, rsi; pSecurityDescriptor
0x18002953d  call    cs:__imp_SetSecurityDescriptorDacl
0x180029543  test    eax, eax
0x180029545  jnz     short loc_180029566
0x180029547  call    cs:__imp_GetLastError
0x18002954d  mov     ebx, eax
0x18002954f  test    eax, eax
0x180029551  jle     short loc_18002955C
0x180029553  movzx   ebx, ax
0x180029556  or      ebx, 80070000h
0x18002955c  test    ebx, ebx
0x18002955e  jns     loc_18002960B
0x180029564  jmp     short loc_18002957F
0x180029566  mov     ebx, 18h
0x18002956b  mov     ecx, ebx; unsigned __int64
0x18002956d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029572  mov     rdi, rax
0x180029575  test    rax, rax
0x180029578  jnz     short loc_1800295B9
0x18002957a  mov     ebx, 8007000Eh
0x18002957f  mov     rcx, [rbp+57h+var_80]; pSid
0x180029583  test    rcx, rcx
0x180029586  jz      short loc_18002958E
0x180029588  call    cs:__imp_FreeSid
0x18002958e  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180029592  test    rcx, rcx
0x180029595  jz      short loc_18002959D
0x180029597  call    cs:__imp_LocalFree
0x18002959d  test    rsi, rsi
0x1800295a0  jz      short loc_1800295AA
0x1800295a2  mov     rcx, rsi; Block
0x1800295a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800295aa  test    rdi, rdi
0x1800295ad  jz      short loc_18002960B
0x1800295af  mov     rcx, rdi; Block
0x1800295b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800295b7  jmp     short loc_18002960B
0x1800295b9  mov     [rax+10h], r15d
0x1800295bd  mov     [rax+8], rsi
0x1800295c1  mov     [rax], ebx
0x1800295c3  xor     eax, eax
0x1800295c5  lock cmpxchg cs:?ms_pSecurityAttributes@CITransaction@@0REAU_SECURITY_ATTRIBUTES@@EA, rdi; _SECURITY_ATTRIBUTES * CITransaction::ms_pSecurityAttributes
0x1800295ce  mov     rcx, cs:?ms_pSecurityAttributes@CITransaction@@0REAU_SECURITY_ATTRIBUTES@@EA; _SECURITY_ATTRIBUTES * CITransaction::ms_pSecurityAttributes
0x1800295d5  cmp     rcx, rdi
0x1800295d8  jz      short loc_1800295FE
0x1800295da  mov     rcx, [rbp+57h+var_80]; pSid
0x1800295de  call    cs:__imp_FreeSid
0x1800295e4  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800295e8  call    cs:__imp_LocalFree
0x1800295ee  mov     rcx, rsi; Block
0x1800295f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800295f6  mov     rcx, rdi; Block
0x1800295f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800295fe  mov     rcx, cs:?ms_pSecurityAttributes@CITransaction@@0REAU_SECURITY_ATTRIBUTES@@EA; _SECURITY_ATTRIBUTES * CITransaction::ms_pSecurityAttributes
0x180029605  mov     ebx, r15d
0x180029608  mov     [r14], rcx
0x18002960b  mov     eax, ebx
0x18002960d  mov     rcx, [rbp+57h+var_38]
0x180029611  xor     rcx, rsp; StackCookie
0x180029614  call    __security_check_cookie
0x180029619  add     rsp, 0B8h
0x180029620  pop     r15
0x180029622  pop     r14
0x180029624  pop     rdi
0x180029625  pop     rsi
0x180029626  pop     rbx
0x180029627  pop     rbp
0x180029628  retn
```
