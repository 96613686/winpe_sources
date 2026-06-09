# CSecDesc::MakeSD(void)

- ea: `0x18001d380`
- end: `0x18001d6e2`
- name: `?MakeSD@CSecDesc@@QEAAPEAU_SECURITY_DESCRIPTOR@@XZ`
- size: `866`
- prototype: `struct _SECURITY_DESCRIPTOR *__fastcall(CSecDesc *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800113f0`
- `0x18001c310`
- `0x18001c850`
- `0x1800b5ca8`

## callees

- `0x18000a504`
- `0x18001d380`
- `0x180072a08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d417`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d417`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d60d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d60d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d4cb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d4cb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001d5db`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001d5db`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d454`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d454`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3c6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3c6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3f6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001d58b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001d5b1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001d58b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001d5b1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d4e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d4e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001d511`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001d511`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d4b1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d4b1`

## string_xrefs

- `0x18001d5ef`: `CSecDesc::MakeSD: Failed to set security descriptor owner.  Error = %d`
- `0x18001d640`: `CSecDesc::MakeSD: Failed to alocate security descriptor.  Error = %d`
- `0x18001d668`: `CSecDesc::MakeSD: Failed to initialize acl.  Error = %d`
- `0x18001d5c5`: `CSecDesc::MakeSD: Couldn't copy owner Sid. Error %d`
- `0x18001d59f`: `CSecDesc::MakeSD: Couldn't copy group Sid. Error %d`
- `0x18001d69a`: `CSecDesc::MakeSD: Failed to initialize security descriptor.  Error = %d`
- `0x18001d6a9`: `CSecDesc::MakeSD: Failed to set security descriptor dacl.  Error = %d`
- `0x18001d6b8`: `CSecDesc::MakeSD: Failed to set security descriptor group.  Error = %d`

## pseudocode

```c
struct _SECURITY_DESCRIPTOR *__fastcall CSecDesc::MakeSD(CSecDesc *this)
{
  DWORD LengthSid; // ebp
  DWORD v3; // r14d
  void *v4; // rcx
  void *v5; // rcx
  unsigned int v6; // ecx
  int v7; // esi
  __int64 i; // rdi
  DWORD v9; // eax
  int v10; // edi
  char *v11; // rax
  char *v12; // rsi
  struct _ACL *v13; // r12
  void *v14; // r8
  void *v15; // r8
  char *v16; // rbp
  __int64 j; // rdi
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD LastError; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // eax
  PSID pSid; // [rsp+20h] [rbp-38h]
  void *v28; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 4) || *((_DWORD *)this + 5) )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"MakeSD: Not initialised or failure.");
    return 0;
  }
  else
  {
    LengthSid = 0;
    v3 = 0;
    *((_DWORD *)this + 5) = 1;
    v4 = (void *)*((_QWORD *)this + 3);
    if ( v4 )
      LengthSid = GetLengthSid(v4);
    v5 = (void *)*((_QWORD *)this + 4);
    if ( v5 )
      v3 = GetLengthSid(v5);
    v6 = *((_DWORD *)this + 2);
    v7 = 0;
    for ( i = 0; (unsigned int)i < v6; v7 += v9 )
    {
      v9 = GetLengthSid(*(PSID *)(*(_QWORD *)this + 24 * i));
      v6 = *((_DWORD *)this + 2);
      i = (unsigned int)(i + 1);
    }
    v10 = v7 + 8 * v6;
    v11 = (char *)LocalAlloc(0x40u, LengthSid + v3 + v10 + 48);
    v28 = v11;
    v12 = v11;
    if ( v11 )
    {
      v13 = (struct _ACL *)&v11[LengthSid + 40 + v3];
      if ( InitializeAcl(v13, v10 + 8, 2u) )
      {
        v14 = (void *)*((_QWORD *)this + 3);
        if ( !v14 || CopySid(LengthSid, v12 + 40, v14) )
        {
          v15 = (void *)*((_QWORD *)this + 4);
          v16 = &v12[LengthSid];
          if ( !v15 || CopySid(v3, v16 + 40, v15) )
          {
            for ( j = 0; (unsigned int)j < *((_DWORD *)this + 2); j = (unsigned int)(j + 1) )
            {
              if ( !AddAccessAllowedAceEx(
                      v13,
                      2u,
                      *(_DWORD *)(*(_QWORD *)this + 24 * j + 16),
                      *(_DWORD *)(*(_QWORD *)this + 24 * j + 8),
                      *(PSID *)(*(_QWORD *)this + 24 * j)) )
              {
                LODWORD(pSid) = GetLastError();
                CDebugWrapper::Msg(
                  (CDebugWrapper *)dbgCommon,
                  2u,
                  L"CSecDesc::MakeSD: Failed to add ace (%d).  Error = %d",
                  (unsigned int)j,
                  pSid);
                LocalFree(v12);
                return 0;
              }
            }
            if ( InitializeSecurityDescriptor(v12, 1u) )
            {
              if ( SetSecurityDescriptorDacl(v12, 1, v13, 0) )
              {
                if ( *((_QWORD *)this + 3) && !SetSecurityDescriptorOwner(v12, v12 + 40, 0) )
                {
                  LastError = GetLastError();
                  CDebugWrapper::Msg(
                    (CDebugWrapper *)dbgCommon,
                    2u,
                    L"CSecDesc::MakeSD: Failed to set security descriptor owner.  Error = %d",
                    LastError);
                  LocalFree(v12);
                  return 0;
                }
                if ( !*((_QWORD *)this + 4) || SetSecurityDescriptorGroup(v12, v16 + 40, 0) )
                {
                  *((_DWORD *)this + 5) = 0;
                  return (struct _SECURITY_DESCRIPTOR *)v12;
                }
                v26 = GetLastError();
                CDebugWrapper::Msg(
                  (CDebugWrapper *)dbgCommon,
                  2u,
                  L"CSecDesc::MakeSD: Failed to set security descriptor group.  Error = %d",
                  v26);
              }
              else
              {
                v25 = GetLastError();
                CDebugWrapper::Msg(
                  (CDebugWrapper *)dbgCommon,
                  2u,
                  L"CSecDesc::MakeSD: Failed to set security descriptor dacl.  Error = %d",
                  v25);
              }
            }
            else
            {
              v24 = GetLastError();
              CDebugWrapper::Msg(
                (CDebugWrapper *)dbgCommon,
                2u,
                L"CSecDesc::MakeSD: Failed to initialize security descriptor.  Error = %d",
                v24);
            }
          }
          else
          {
            v19 = GetLastError();
            CDebugWrapper::Msg(
              (CDebugWrapper *)dbgCommon,
              2u,
              L"CSecDesc::MakeSD: Couldn't copy group Sid. Error %d",
              v19);
          }
        }
        else
        {
          v20 = GetLastError();
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgCommon,
            2u,
            L"CSecDesc::MakeSD: Couldn't copy owner Sid. Error %d",
            v20);
        }
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v28);
        return 0;
      }
      else
      {
        v23 = GetLastError();
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgCommon,
          2u,
          L"CSecDesc::MakeSD: Failed to initialize acl.  Error = %d",
          v23);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v28);
        return 0;
      }
    }
    else
    {
      v22 = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgCommon,
        2u,
        L"CSecDesc::MakeSD: Failed to alocate security descriptor.  Error = %d",
        v22);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18001d380  push    rbx
0x18001d382  sub     rsp, 50h
0x18001d386  cmp     dword ptr [rcx+10h], 0
0x18001d38a  mov     rbx, rcx
0x18001d38d  jz      loc_18001D61A
0x18001d393  cmp     dword ptr [rcx+14h], 0
0x18001d397  jnz     loc_18001D61A
0x18001d39d  mov     [rsp+58h+arg_8], rbp
0x18001d3a2  xor     ebp, ebp
0x18001d3a4  mov     [rsp+58h+arg_10], rsi
0x18001d3a9  mov     [rsp+58h+arg_18], rdi
0x18001d3ae  mov     [rsp+58h+var_20], r14
0x18001d3b3  xor     r14d, r14d
0x18001d3b6  mov     dword ptr [rcx+14h], 1
0x18001d3bd  mov     rcx, [rcx+18h]; pSid
0x18001d3c1  test    rcx, rcx
0x18001d3c4  jz      short loc_18001D3CE
0x18001d3c6  call    cs:__imp_GetLengthSid
0x18001d3cc  mov     ebp, eax
0x18001d3ce  mov     rcx, [rbx+20h]; pSid
0x18001d3d2  test    rcx, rcx
0x18001d3d5  jz      short loc_18001D3E0
0x18001d3d7  call    cs:__imp_GetLengthSid
0x18001d3dd  mov     r14d, eax
0x18001d3e0  mov     ecx, [rbx+8]
0x18001d3e3  xor     esi, esi
0x18001d3e5  xor     edi, edi
0x18001d3e7  test    ecx, ecx
0x18001d3e9  jz      short loc_18001D407
0x18001d3eb  mov     rcx, [rbx]
0x18001d3ee  lea     rdx, [rdi+rdi*2]
0x18001d3f2  mov     rcx, [rcx+rdx*8]; pSid
0x18001d3f6  call    cs:__imp_GetLengthSid
0x18001d3fc  mov     ecx, [rbx+8]
0x18001d3ff  inc     edi
0x18001d401  add     esi, eax
0x18001d403  cmp     edi, ecx
0x18001d405  jb      short loc_18001D3EB
0x18001d407  lea     edi, [rsi+rcx*8]
0x18001d40a  mov     ecx, 40h ; '@'; uFlags
0x18001d40f  lea     edx, [rdi+30h]
0x18001d412  add     edx, r14d
0x18001d415  add     edx, ebp; uBytes
0x18001d417  call    cs:__imp_LocalAlloc
0x18001d41d  mov     [rsp+58h+arg_0], rax
0x18001d422  mov     rsi, rax
0x18001d425  test    rax, rax
0x18001d428  jz      loc_18001D63A
0x18001d42e  mov     [rsp+58h+var_10], r12
0x18001d433  lea     edx, [rdi+8]; nAclLength
0x18001d436  mov     r12d, r14d
0x18001d439  mov     r8d, 2; dwAclRevision
0x18001d43f  add     r12, 28h ; '('
0x18001d443  mov     [rsp+58h+var_28], r15
0x18001d448  mov     r15d, ebp
0x18001d44b  add     r12, r15
0x18001d44e  add     r12, rax
0x18001d451  mov     rcx, r12; pAcl
0x18001d454  call    cs:__imp_InitializeAcl
0x18001d45a  test    eax, eax
0x18001d45c  jz      loc_18001D662
0x18001d462  mov     r8, [rbx+18h]; pSourceSid
0x18001d466  mov     [rsp+58h+var_18], r13
0x18001d46b  test    r8, r8
0x18001d46e  jnz     loc_18001D5AB
0x18001d474  mov     r8, [rbx+20h]; pSourceSid
0x18001d478  lea     rbp, [r15+rsi]
0x18001d47c  test    r8, r8
0x18001d47f  jnz     loc_18001D584
0x18001d485  xor     edi, edi
0x18001d487  cmp     edi, [rbx+8]
0x18001d48a  jnb     short loc_18001D4C3
0x18001d48c  mov     rax, [rbx]
0x18001d48f  lea     rcx, [rdi+rdi*2]
0x18001d493  mov     r9d, [rax+rcx*8+8]; AccessMask
0x18001d498  lea     r8, [rax+rcx*8]
0x18001d49c  mov     rax, [rax+rcx*8]
0x18001d4a0  mov     edx, 2; dwAceRevision
0x18001d4a5  mov     r8d, [r8+10h]; AceFlags
0x18001d4a9  mov     rcx, r12; pAcl
0x18001d4ac  mov     [rsp+58h+pSid], rax; pSid
0x18001d4b1  call    cs:__imp_AddAccessAllowedAceEx
0x18001d4b7  test    eax, eax
0x18001d4b9  jz      loc_18001D552
0x18001d4bf  inc     edi
0x18001d4c1  jmp     short loc_18001D487
0x18001d4c3  mov     edx, 1; dwRevision
0x18001d4c8  mov     rcx, rsi; pSecurityDescriptor
0x18001d4cb  call    cs:__imp_InitializeSecurityDescriptor
0x18001d4d1  test    eax, eax
0x18001d4d3  jz      loc_18001D694
0x18001d4d9  xor     r9d, r9d; bDaclDefaulted
0x18001d4dc  mov     r8, r12; pDacl
0x18001d4df  mov     edx, 1; bDaclPresent
0x18001d4e4  mov     rcx, rsi; pSecurityDescriptor
0x18001d4e7  call    cs:__imp_SetSecurityDescriptorDacl
0x18001d4ed  test    eax, eax
0x18001d4ef  jz      loc_18001D6A3
0x18001d4f5  cmp     qword ptr [rbx+18h], 0
0x18001d4fa  jnz     loc_18001D5D1
0x18001d500  cmp     qword ptr [rbx+20h], 0
0x18001d505  jz      short loc_18001D51F
0x18001d507  xor     r8d, r8d; bGroupDefaulted
0x18001d50a  lea     rdx, [rbp+28h]; pGroup
0x18001d50e  mov     rcx, rsi; pSecurityDescriptor
0x18001d511  call    cs:__imp_SetSecurityDescriptorGroup
0x18001d517  test    eax, eax
0x18001d519  jz      loc_18001D6B2
0x18001d51f  mov     dword ptr [rbx+14h], 0
0x18001d526  mov     rax, rsi
0x18001d529  mov     r13, [rsp+58h+var_18]
0x18001d52e  mov     r12, [rsp+58h+var_10]
0x18001d533  mov     r15, [rsp+58h+var_28]
0x18001d538  mov     rdi, [rsp+58h+arg_18]
0x18001d53d  mov     rsi, [rsp+58h+arg_10]
0x18001d542  mov     rbp, [rsp+58h+arg_8]
0x18001d547  mov     r14, [rsp+58h+var_20]
0x18001d54c  add     rsp, 50h
0x18001d550  pop     rbx
0x18001d551  retn
0x18001d552  call    cs:__imp_GetLastError
0x18001d558  mov     r9d, edi
0x18001d55b  lea     r8, aCsecdescMakesd; "CSecDesc::MakeSD: Failed to add ace (%d"...
0x18001d562  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d569  mov     dword ptr [rsp+58h+pSid], eax
0x18001d56d  mov     edx, 2; unsigned int
0x18001d572  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d577  mov     rcx, rsi; hMem
0x18001d57a  call    cs:__imp_LocalFree
0x18001d580  xor     eax, eax
0x18001d582  jmp     short loc_18001D529
0x18001d584  lea     rdx, [rbp+28h]; pDestinationSid
0x18001d588  mov     ecx, r14d; nDestinationSidLength
0x18001d58b  call    cs:__imp_CopySid
0x18001d591  test    eax, eax
0x18001d593  jnz     loc_18001D485
0x18001d599  call    cs:__imp_GetLastError
0x18001d59f  lea     r8, aCsecdescMakesd_5; "CSecDesc::MakeSD: Couldn't copy group S"...
0x18001d5a6  jmp     loc_18001D6BF
0x18001d5ab  lea     rdx, [rsi+28h]; pDestinationSid
0x18001d5af  mov     ecx, ebp; nDestinationSidLength
0x18001d5b1  call    cs:__imp_CopySid
0x18001d5b7  test    eax, eax
0x18001d5b9  jnz     loc_18001D474
0x18001d5bf  call    cs:__imp_GetLastError
0x18001d5c5  lea     r8, aCsecdescMakesd_3; "CSecDesc::MakeSD: Couldn't copy owner S"...
0x18001d5cc  jmp     loc_18001D6BF
0x18001d5d1  xor     r8d, r8d; bOwnerDefaulted
0x18001d5d4  lea     rdx, [rsi+28h]; pOwner
0x18001d5d8  mov     rcx, rsi; pSecurityDescriptor
0x18001d5db  call    cs:__imp_SetSecurityDescriptorOwner
0x18001d5e1  test    eax, eax
0x18001d5e3  jnz     loc_18001D500
0x18001d5e9  call    cs:__imp_GetLastError
0x18001d5ef  lea     r8, aCsecdescMakesd_6; "CSecDesc::MakeSD: Failed to set securit"...
0x18001d5f6  mov     edx, 2; unsigned int
0x18001d5fb  mov     r9d, eax
0x18001d5fe  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d605  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d60a  mov     rcx, rsi; hMem
0x18001d60d  call    cs:__imp_LocalFree
0x18001d613  xor     eax, eax
0x18001d615  jmp     loc_18001D529
0x18001d61a  lea     r8, aMakesdNotIniti; "MakeSD: Not initialised or failure."
0x18001d621  mov     edx, 2; unsigned int
0x18001d626  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d62d  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d632  xor     eax, eax
0x18001d634  add     rsp, 50h
0x18001d638  pop     rbx
0x18001d639  retn
0x18001d63a  call    cs:__imp_GetLastError
0x18001d640  lea     r8, aCsecdescMakesd_4; "CSecDesc::MakeSD: Failed to alocate sec"...
0x18001d647  mov     edx, 2; unsigned int
0x18001d64c  mov     r9d, eax
0x18001d64f  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d656  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d65b  xor     eax, eax
0x18001d65d  jmp     loc_18001D538
0x18001d662  call    cs:__imp_GetLastError
0x18001d668  lea     r8, aCsecdescMakesd_0; "CSecDesc::MakeSD: Failed to initialize "...
0x18001d66f  mov     edx, 2; unsigned int
0x18001d674  mov     r9d, eax
0x18001d677  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d67e  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d683  lea     rcx, [rsp+58h+arg_0]
0x18001d688  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001d68d  xor     eax, eax
0x18001d68f  jmp     loc_18001D52E
0x18001d694  call    cs:__imp_GetLastError
0x18001d69a  lea     r8, aCsecdescMakesd_1; "CSecDesc::MakeSD: Failed to initialize "...
0x18001d6a1  jmp     short loc_18001D6BF
0x18001d6a3  call    cs:__imp_GetLastError
0x18001d6a9  lea     r8, aCsecdescMakesd_2; "CSecDesc::MakeSD: Failed to set securit"...
0x18001d6b0  jmp     short loc_18001D6BF
0x18001d6b2  call    cs:__imp_GetLastError
0x18001d6b8  lea     r8, aCsecdescMakesd_7; "CSecDesc::MakeSD: Failed to set securit"...
0x18001d6bf  mov     r9d, eax
0x18001d6c2  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001d6c9  mov     edx, 2; unsigned int
0x18001d6ce  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001d6d3  lea     rcx, [rsp+58h+arg_0]
0x18001d6d8  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001d6dd  jmp     loc_18001D580
```
