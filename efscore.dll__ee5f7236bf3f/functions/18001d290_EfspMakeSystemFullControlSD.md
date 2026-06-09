# EfspMakeSystemFullControlSD

- ea: `0x18001d290`
- end: `0x18001d5b2`
- name: `EfspMakeSystemFullControlSD`
- size: `802`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016e58`
- `0x18001abf0`

## callees

- `0x180005045`
- `0x1800102f0`
- `0x180010bf0`
- `0x18001d290`
- `0x180063698`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001d4db`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001d4db`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001d4b9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001d4b9`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001d49a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001d49a`
- `ntdll!RtlLengthSid` at `0x18001d431`
- `ntdll!RtlLengthSid` at `0x18001d431`
- `ntdll!RtlSubAuthoritySid` at `0x18001d422`
- `ntdll!RtlSubAuthoritySid` at `0x18001d422`
- `ntdll!RtlInitializeSid` at `0x18001d3d5`
- `ntdll!RtlInitializeSid` at `0x18001d3d5`
- `ntdll!RtlLengthRequiredSid` at `0x18001d2cf`
- `ntdll!RtlLengthRequiredSid` at `0x18001d370`
- `ntdll!RtlLengthRequiredSid` at `0x18001d2cf`
- `ntdll!RtlLengthRequiredSid` at `0x18001d370`

## pseudocode

```c
__int64 __fastcall EfspMakeSystemFullControlSD(_QWORD *a1)
{
  ULONG v2; // eax
  _SID_IDENTIFIER_AUTHORITY *p_IdentifierAuthority; // rbx
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  _DWORD *v9; // rax
  ULONG v10; // eax
  int v11; // edi
  NTSTATUS SecurityDescriptor; // eax
  struct _ACL *v13; // r15
  int v14; // r12d
  _WORD *v15; // rsi
  int v16; // r8d
  ULONG v17; // edi
  _WORD *v18; // rax
  __int64 v20; // [rsp+0h] [rbp-30h] BYREF
  PSID pSid; // [rsp+20h] [rbp-10h]
  int v22; // [rsp+30h] [rbp+0h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+38h] [rbp+8h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(1u);
  p_IdentifierAuthority = 0;
  v4 = v2;
  if ( !v2
    || v2 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)v2 + g_ulAdditionalProbeSize + 8 < v2
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_9;
  }
  v5 = v4 + 23;
  if ( v4 + 23 <= v4 + 8 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
  v7 = alloca(v6);
  v8 = alloca(v6);
  p_IdentifierAuthority = (_SID_IDENTIFIER_AUTHORITY *)&v22;
  if ( &v20 == (__int64 *)-48LL || (v22 = 1801679955, (p_IdentifierAuthority = &IdentifierAuthority) == 0) )
  {
LABEL_9:
    if ( v4 + 8 >= v4 )
    {
      v9 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v9 )
      {
LABEL_13:
        v10 = RtlLengthRequiredSid(1u);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v10, 10, 118);
        v11 = -1073741670;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -1073741670, 10, 119);
        return (unsigned int)v11;
      }
      *v9 = 1885431112;
      p_IdentifierAuthority = (_SID_IDENTIFIER_AUTHORITY *)(v9 + 2);
    }
    if ( !p_IdentifierAuthority )
      goto LABEL_13;
  }
  SecurityDescriptor = RtlInitializeSid(p_IdentifierAuthority, &IdentifierAuthority, 1u);
  v11 = SecurityDescriptor;
  if ( SecurityDescriptor >= 0 )
  {
    *RtlSubAuthoritySid(p_IdentifierAuthority, 0) = 18;
    v17 = RtlLengthSid(p_IdentifierAuthority) + 56;
    v13 = (struct _ACL *)wil::details::heap_allocator::allocate(v17);
    v18 = wil::details::heap_allocator::allocate(0x28u);
    v15 = v18;
    if ( !v13 || !v18 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 10, 142);
      v16 = -1073741670;
      LODWORD(pSid) = 5007;
      v11 = -1073741670;
      goto LABEL_27;
    }
    memset_0(v13, 0, v17);
    *(_WORD *)&v13->AclRevision = 4;
    v13->AclSize = v17;
    v13->AceCount = 0;
    SecurityDescriptor = RtlAddAccessAllowedAceEx(v13, 4u, 3u, 0x10000000u, p_IdentifierAuthority);
    v11 = SecurityDescriptor;
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(v15, 1u);
      v11 = SecurityDescriptor;
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlSetDaclSecurityDescriptor(v15, 1u, v13, 0);
        v11 = SecurityDescriptor;
        if ( SecurityDescriptor >= 0 )
        {
          v15[1] |= 0x1000u;
          *a1 = v15;
          v15 = 0;
          goto LABEL_28;
        }
        v14 = 5044;
      }
      else
      {
        v14 = 5035;
      }
    }
    else
    {
      v14 = 5030;
    }
  }
  else
  {
    v13 = 0;
    v14 = 4988;
    v15 = 0;
  }
  v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SecurityDescriptor, 10, v14);
  LODWORD(pSid) = v14;
LABEL_27:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 10, (char)pSid);
LABEL_28:
  if ( p_IdentifierAuthority && *(_DWORD *)&p_IdentifierAuthority[-2].Value[4] == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v11 < 0 )
  {
    if ( v13 )
      EfsFreeHeap(v13);
    if ( v15 )
      EfsFreeHeap(v15);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001d290  push    rbp
0x18001d292  push    rdi
0x18001d293  push    r12
0x18001d295  push    r14
0x18001d297  push    r15
0x18001d299  sub     rsp, 50h
0x18001d29d  lea     rbp, [rsp+30h]
0x18001d2a2  mov     [rbp+40h+arg_8], rbx
0x18001d2a6  mov     [rbp+40h+arg_10], rsi
0x18001d2aa  mov     rax, cs:__security_cookie
0x18001d2b1  xor     rax, rbp
0x18001d2b4  mov     [rbp+40h+var_30], rax
0x18001d2b8  mov     r12, rcx
0x18001d2bb  mov     dword ptr [rbp+40h+IdentifierAuthority.Value], 0
0x18001d2c2  mov     esi, 1
0x18001d2c7  mov     word ptr [rbp+40h+IdentifierAuthority.Value+4], 500h
0x18001d2cd  mov     ecx, esi; SubAuthorityCount
0x18001d2cf  call    cs:__imp_RtlLengthRequiredSid
0x18001d2d5  xor     ebx, ebx
0x18001d2d7  mov     edi, eax
0x18001d2d9  test    eax, eax
0x18001d2db  jz      short loc_18001D342
0x18001d2dd  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001d2e4  ja      short loc_18001D342
0x18001d2e6  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001d2ed  add     rcx, 8
0x18001d2f1  add     rcx, rdi
0x18001d2f4  cmp     rcx, rdi
0x18001d2f7  jb      short loc_18001D342
0x18001d2f9  call    VerifyStackAvailable
0x18001d2fe  test    eax, eax
0x18001d300  jz      short loc_18001D342
0x18001d302  lea     rax, [rdi+8]
0x18001d306  lea     rcx, [rax+0Fh]
0x18001d30a  cmp     rcx, rax
0x18001d30d  ja      short loc_18001D319
0x18001d30f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001d319  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d31d  mov     rax, rcx
0x18001d320  call    _alloca_probe
0x18001d325  sub     rsp, rcx
0x18001d328  lea     rbx, [rsp+70h+var_40]
0x18001d32d  test    rbx, rbx
0x18001d330  jz      short loc_18001D342
0x18001d332  mov     dword ptr [rbx], 6B637453h
0x18001d338  add     rbx, 8
0x18001d33c  jnz     loc_18001D3CB
0x18001d342  lea     rcx, [rdi+8]
0x18001d346  cmp     rcx, rdi
0x18001d349  jb      short loc_18001D369
0x18001d34b  mov     rax, cs:g_pfnAllocate
0x18001d352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d357  mov     rbx, rax
0x18001d35a  test    rax, rax
0x18001d35d  jz      short loc_18001D36E
0x18001d35f  mov     dword ptr [rax], 70616548h
0x18001d365  add     rbx, 8
0x18001d369  test    rbx, rbx
0x18001d36c  jnz     short loc_18001D3CB
0x18001d36e  mov     ecx, esi; SubAuthorityCount
0x18001d370  call    cs:__imp_RtlLengthRequiredSid
0x18001d376  mov     rcx, cs:g_hPublisher
0x18001d37d  lea     rdx, EFS_ERROR_MEMORY
0x18001d384  mov     r14d, 0Ah
0x18001d38a  mov     dword ptr [rsp+70h+pSid], 1376h
0x18001d392  mov     r9d, r14d
0x18001d395  mov     r8d, eax
0x18001d398  call    fnEfsLogTrace1
0x18001d39d  mov     rcx, cs:g_hPublisher
0x18001d3a4  lea     rdx, EFS_TRACE_ERROR
0x18001d3ab  mov     r9d, r14d
0x18001d3ae  mov     dword ptr [rsp+70h+pSid], 1377h
0x18001d3b6  mov     r8d, 0C000009Ah
0x18001d3bc  mov     edi, 0C000009Ah
0x18001d3c1  call    fnEfsLogTrace1
0x18001d3c6  jmp     loc_18001D58F
0x18001d3cb  mov     r8b, sil; SubAuthorityCount
0x18001d3ce  lea     rdx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x18001d3d2  mov     rcx, rbx; Sid
0x18001d3d5  call    cs:__imp_RtlInitializeSid
0x18001d3db  mov     edi, eax
0x18001d3dd  test    eax, eax
0x18001d3df  jns     short loc_18001D41D
0x18001d3e1  xor     r15d, r15d
0x18001d3e4  mov     r12d, 137Ch
0x18001d3ea  xor     esi, esi
0x18001d3ec  mov     rcx, cs:g_hPublisher
0x18001d3f3  lea     rdx, EFS_API_ERROR
0x18001d3fa  mov     r14d, 0Ah
0x18001d400  mov     dword ptr [rsp+70h+pSid], r12d
0x18001d405  mov     r9d, r14d
0x18001d408  mov     r8d, eax
0x18001d40b  call    fnEfsLogTrace1
0x18001d410  mov     r8d, eax
0x18001d413  mov     dword ptr [rsp+70h+pSid], r12d
0x18001d418  jmp     loc_18001D53E
0x18001d41d  xor     edx, edx; SubAuthority
0x18001d41f  mov     rcx, rbx; Sid
0x18001d422  call    cs:__imp_RtlSubAuthoritySid
0x18001d428  mov     rcx, rbx; Sid
0x18001d42b  mov     dword ptr [rax], 12h
0x18001d431  call    cs:__imp_RtlLengthSid
0x18001d437  lea     edi, [rax+38h]
0x18001d43a  mov     ecx, edi; unsigned __int64
0x18001d43c  mov     r14d, edi
0x18001d43f  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001d444  mov     ecx, 28h ; '('; unsigned __int64
0x18001d449  mov     r15, rax
0x18001d44c  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001d451  mov     rsi, rax
0x18001d454  test    r15, r15
0x18001d457  jz      loc_18001D503
0x18001d45d  test    rax, rax
0x18001d460  jz      loc_18001D503
0x18001d466  mov     r8d, r14d; Size
0x18001d469  xor     edx, edx; Val
0x18001d46b  mov     rcx, r15; void *
0x18001d46e  call    memset_0
0x18001d473  xor     eax, eax
0x18001d475  mov     word ptr [r15], 4
0x18001d47b  mov     r9d, 10000000h; AccessMask
0x18001d481  mov     [r15+2], di
0x18001d486  mov     rcx, r15; pAcl
0x18001d489  mov     [r15+4], ax
0x18001d48e  mov     [rsp+70h+pSid], rbx; pSid
0x18001d493  lea     edx, [rax+4]; dwAceRevision
0x18001d496  lea     r8d, [rax+3]; AceFlags
0x18001d49a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18001d4a0  mov     edi, eax
0x18001d4a2  test    eax, eax
0x18001d4a4  jns     short loc_18001D4B1
0x18001d4a6  mov     r12d, 13A6h
0x18001d4ac  jmp     loc_18001D3EC
0x18001d4b1  mov     edx, 1; Revision
0x18001d4b6  mov     rcx, rsi; SecurityDescriptor
0x18001d4b9  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001d4bf  mov     edi, eax
0x18001d4c1  test    eax, eax
0x18001d4c3  jns     short loc_18001D4D0
0x18001d4c5  mov     r12d, 13ABh
0x18001d4cb  jmp     loc_18001D3EC
0x18001d4d0  xor     r9d, r9d; DaclDefaulted
0x18001d4d3  mov     r8, r15; Dacl
0x18001d4d6  mov     dl, 1; DaclPresent
0x18001d4d8  mov     rcx, rsi; SecurityDescriptor
0x18001d4db  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001d4e1  mov     edi, eax
0x18001d4e3  test    eax, eax
0x18001d4e5  jns     short loc_18001D4F2
0x18001d4e7  mov     r12d, 13B4h
0x18001d4ed  jmp     loc_18001D3EC
0x18001d4f2  mov     eax, 1000h
0x18001d4f7  or      [rsi+2], ax
0x18001d4fb  mov     [r12], rsi
0x18001d4ff  xor     esi, esi
0x18001d501  jmp     short loc_18001D554
0x18001d503  mov     rcx, cs:g_hPublisher
0x18001d50a  lea     rdx, EFS_API_ERROR
0x18001d511  mov     r14d, 0Ah
0x18001d517  mov     dword ptr [rsp+70h+pSid], 138Eh
0x18001d51f  mov     r9d, r14d
0x18001d522  lea     r8d, [r14-2]
0x18001d526  call    fnEfsLogTrace1
0x18001d52b  mov     r8d, 0C000009Ah
0x18001d531  mov     dword ptr [rsp+70h+pSid], 138Fh
0x18001d539  mov     edi, 0C000009Ah
0x18001d53e  mov     rcx, cs:g_hPublisher
0x18001d545  lea     rdx, EFS_TRACE_ERROR
0x18001d54c  mov     r9d, r14d
0x18001d54f  call    fnEfsLogTrace1
0x18001d554  test    rbx, rbx
0x18001d557  jz      short loc_18001D571
0x18001d559  lea     rcx, [rbx-8]
0x18001d55d  cmp     dword ptr [rcx], 70616548h
0x18001d563  jnz     short loc_18001D571
0x18001d565  mov     rax, cs:g_pfnFree
0x18001d56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d571  test    edi, edi
0x18001d573  jns     short loc_18001D58F
0x18001d575  test    r15, r15
0x18001d578  jz      short loc_18001D582
0x18001d57a  mov     rcx, r15; lpMem
0x18001d57d  call    EfsFreeHeap
0x18001d582  test    rsi, rsi
0x18001d585  jz      short loc_18001D58F
0x18001d587  mov     rcx, rsi; lpMem
0x18001d58a  call    EfsFreeHeap
0x18001d58f  mov     eax, edi
0x18001d591  mov     rcx, [rbp+40h+var_30]
0x18001d595  xor     rcx, rbp; StackCookie
0x18001d598  call    __security_check_cookie
0x18001d59d  mov     rbx, [rbp+40h+arg_8]
0x18001d5a1  mov     rsi, [rbp+40h+arg_10]
0x18001d5a5  lea     rsp, [rbp+20h]
0x18001d5a9  pop     r15
0x18001d5ab  pop     r14
0x18001d5ad  pop     r12
0x18001d5af  pop     rdi
0x18001d5b0  pop     rbp
0x18001d5b1  retn
```
