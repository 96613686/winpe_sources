# IsLocalSystemTokenUser(void *,int *)

- ea: `0x1800b93bc`
- end: `0x1800b9508`
- name: `?IsLocalSystemTokenUser@@YAKPEAXPEAH@Z`
- size: `332`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008c0c0`

## callees

- `0x18000a504`
- `0x1800b93bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b94b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b94b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b93e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b947c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b93e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b947c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b94c9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b94c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b945f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b94a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b945f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b94a6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b9413`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b9413`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b9427`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b9427`

## pseudocode

```c
__int64 __fastcall IsLocalSystemTokenUser(HANDLE TokenHandle, int *a2)
{
  HLOCAL v4; // rax
  void *v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // ebx
  PSID *v8; // rax
  PSID *v9; // rdi
  PSID *v11; // [rsp+30h] [rbp-10h] BYREF
  void *v12; // [rsp+38h] [rbp-8h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+38h] BYREF
  WINBOOL IsMember; // [rsp+80h] [rbp+40h] BYREF
  DWORD cbSid; // [rsp+88h] [rbp+48h] BYREF

  IsMember = 0;
  cbSid = 68;
  v4 = LocalAlloc(0, 0x44u);
  TokenInformationLength = 0;
  v5 = v4;
  v12 = v4;
  if ( !a2 )
  {
    v7 = 13;
    goto LABEL_17;
  }
  if ( !v4 )
    goto LABEL_15;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, v4, &cbSid) && CheckTokenMembership(TokenHandle, v5, &IsMember) )
  {
    if ( !IsMember )
      goto LABEL_14;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_6;
    }
    v8 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    v9 = v8;
    if ( v8 )
    {
      v11 = v8;
      if ( !GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        v7 = GetLastError();
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v11);
        goto LABEL_17;
      }
      *a2 = EqualSid(*v9, v5);
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v11);
LABEL_14:
      v7 = 0;
      goto LABEL_17;
    }
LABEL_15:
    v7 = 14;
    goto LABEL_17;
  }
  LastError = GetLastError();
LABEL_6:
  v7 = LastError;
LABEL_17:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v12);
  return v7;
}

```

## disassembly

```asm
0x1800b93bc  push    rbp
0x1800b93be  push    rbx
0x1800b93bf  push    rsi
0x1800b93c0  push    rdi
0x1800b93c1  push    r14
0x1800b93c3  mov     rbp, rsp
0x1800b93c6  sub     rsp, 40h
0x1800b93ca  mov     r14, rdx
0x1800b93cd  mov     [rbp+IsMember], 0
0x1800b93d4  mov     edx, 44h ; 'D'; uBytes
0x1800b93d9  mov     rsi, rcx
0x1800b93dc  xor     ecx, ecx; uFlags
0x1800b93de  mov     [rbp+cbSid], edx
0x1800b93e1  call    cs:__imp_LocalAlloc
0x1800b93e7  mov     [rbp+TokenInformationLength], 0
0x1800b93ee  mov     rbx, rax
0x1800b93f1  mov     [rbp+var_8], rax
0x1800b93f5  test    r14, r14
0x1800b93f8  jz      loc_1800B94ED
0x1800b93fe  test    rax, rax
0x1800b9401  jz      loc_1800B94E6
0x1800b9407  xor     edx, edx; DomainSid
0x1800b9409  lea     r9, [rbp+cbSid]; cbSid
0x1800b940d  mov     r8, rax; pSid
0x1800b9410  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800b9413  call    cs:__imp_CreateWellKnownSid
0x1800b9419  test    eax, eax
0x1800b941b  jz      short loc_1800B9431
0x1800b941d  lea     r8, [rbp+IsMember]; IsMember
0x1800b9421  mov     rdx, rbx; SidToCheck
0x1800b9424  mov     rcx, rsi; TokenHandle
0x1800b9427  call    cs:__imp_CheckTokenMembership
0x1800b942d  test    eax, eax
0x1800b942f  jnz     short loc_1800B943E
0x1800b9431  call    cs:__imp_GetLastError
0x1800b9437  mov     ebx, eax
0x1800b9439  jmp     loc_1800B94F2
0x1800b943e  cmp     [rbp+IsMember], 0
0x1800b9442  jz      loc_1800B94E2
0x1800b9448  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800b944c  lea     rax, [rbp+TokenInformationLength]
0x1800b9450  xor     r8d, r8d; TokenInformation
0x1800b9453  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800b9458  mov     rcx, rsi; TokenHandle
0x1800b945b  lea     edx, [r8+1]; TokenInformationClass
0x1800b945f  call    cs:__imp_GetTokenInformation
0x1800b9465  test    eax, eax
0x1800b9467  jnz     short loc_1800B9474
0x1800b9469  call    cs:__imp_GetLastError
0x1800b946f  cmp     eax, 7Ah ; 'z'
0x1800b9472  jnz     short loc_1800B9437
0x1800b9474  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800b9477  mov     ecx, 40h ; '@'; uFlags
0x1800b947c  call    cs:__imp_LocalAlloc
0x1800b9482  mov     rdi, rax
0x1800b9485  test    rax, rax
0x1800b9488  jz      short loc_1800B94E6
0x1800b948a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800b948e  mov     r8, rdi; TokenInformation
0x1800b9491  mov     [rbp+var_10], rax
0x1800b9495  mov     edx, 1; TokenInformationClass
0x1800b949a  lea     rax, [rbp+TokenInformationLength]
0x1800b949e  mov     rcx, rsi; TokenHandle
0x1800b94a1  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800b94a6  call    cs:__imp_GetTokenInformation
0x1800b94ac  test    eax, eax
0x1800b94ae  jnz     short loc_1800B94C3
0x1800b94b0  call    cs:__imp_GetLastError
0x1800b94b6  lea     rcx, [rbp+var_10]
0x1800b94ba  mov     ebx, eax
0x1800b94bc  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b94c1  jmp     short loc_1800B94F2
0x1800b94c3  mov     rcx, [rdi]; pSid1
0x1800b94c6  mov     rdx, rbx; pSid2
0x1800b94c9  call    cs:__imp_EqualSid
0x1800b94cf  xor     ecx, ecx
0x1800b94d1  test    eax, eax
0x1800b94d3  setnz   cl
0x1800b94d6  mov     [r14], ecx
0x1800b94d9  lea     rcx, [rbp+var_10]
0x1800b94dd  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b94e2  xor     ebx, ebx
0x1800b94e4  jmp     short loc_1800B94F2
0x1800b94e6  mov     ebx, 0Eh
0x1800b94eb  jmp     short loc_1800B94F2
0x1800b94ed  mov     ebx, 0Dh
0x1800b94f2  lea     rcx, [rbp+var_8]
0x1800b94f6  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b94fb  mov     eax, ebx
0x1800b94fd  add     rsp, 40h
0x1800b9501  pop     r14
0x1800b9503  pop     rdi
0x1800b9504  pop     rsi
0x1800b9505  pop     rbx
0x1800b9506  pop     rbp
0x1800b9507  retn
```
