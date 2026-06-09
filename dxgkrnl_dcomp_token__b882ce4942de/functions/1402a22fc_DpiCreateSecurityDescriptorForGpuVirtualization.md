# DpiCreateSecurityDescriptorForGpuVirtualization

- ea: `0x1402a22fc`
- end: `0x1402a27ba`
- name: `DpiCreateSecurityDescriptorForGpuVirtualization`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402a9a38`

## callees

- `0x1400a0100`
- `0x1400a0540`
- `0x1402a22fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402a275f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a2775`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a2786`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a275f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a2775`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a2786`
- `ntoskrnl!ExAllocatePool2` at `0x1402a2367`
- `ntoskrnl!ExAllocatePool2` at `0x1402a244e`
- `ntoskrnl!ExAllocatePool2` at `0x1402a26ee`
- `ntoskrnl!ExAllocatePool2` at `0x1402a2367`
- `ntoskrnl!ExAllocatePool2` at `0x1402a244e`
- `ntoskrnl!ExAllocatePool2` at `0x1402a26ee`
- `ntoskrnl!SeExports` at `0x1402a23f4`
- `ntoskrnl!SeExports` at `0x1402a2411`
- `ntoskrnl!SeExports` at `0x1402a24aa`
- `ntoskrnl!SeExports` at `0x1402a24fb`
- `ntoskrnl!SeExports` at `0x1402a260c`
- `ntoskrnl!SeExports` at `0x1402a2658`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402a2598`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402a2598`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1402a234a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1402a234a`
- `ntoskrnl!RtlInitializeSid` at `0x1402a238f`
- `ntoskrnl!RtlInitializeSid` at `0x1402a238f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a23c8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a23e2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a23c8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a23e2`
- `ntoskrnl!RtlLengthSid` at `0x1402a2405`
- `ntoskrnl!RtlLengthSid` at `0x1402a2424`
- `ntoskrnl!RtlLengthSid` at `0x1402a2435`
- `ntoskrnl!RtlLengthSid` at `0x1402a2405`
- `ntoskrnl!RtlLengthSid` at `0x1402a2424`
- `ntoskrnl!RtlLengthSid` at `0x1402a2435`
- `ntoskrnl!RtlCreateAcl` at `0x1402a2476`
- `ntoskrnl!RtlCreateAcl` at `0x1402a2476`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a24c7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a2518`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a255b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a24c7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a2518`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a255b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402a25d8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402a25d8`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1402a2624`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1402a2624`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1402a2670`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1402a2670`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402a2722`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402a2722`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402a26a8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402a26a8`
- `watchdog!WdLogSingleEntry1` at `0x1402a23a8`
- `watchdog!WdLogSingleEntry1` at `0x1402a248f`
- `watchdog!WdLogSingleEntry1` at `0x1402a24e0`
- `watchdog!WdLogSingleEntry1` at `0x1402a2531`
- `watchdog!WdLogSingleEntry1` at `0x1402a2574`
- `watchdog!WdLogSingleEntry1` at `0x1402a25b1`
- `watchdog!WdLogSingleEntry1` at `0x1402a25f1`
- `watchdog!WdLogSingleEntry1` at `0x1402a263d`
- `watchdog!WdLogSingleEntry1` at `0x1402a2689`
- `watchdog!WdLogSingleEntry1` at `0x1402a26c9`
- `watchdog!WdLogSingleEntry1` at `0x1402a273b`
- `watchdog!WdLogSingleEntry1` at `0x1402a23a8`
- `watchdog!WdLogSingleEntry1` at `0x1402a248f`
- `watchdog!WdLogSingleEntry1` at `0x1402a24e0`
- `watchdog!WdLogSingleEntry1` at `0x1402a2531`
- `watchdog!WdLogSingleEntry1` at `0x1402a2574`
- `watchdog!WdLogSingleEntry1` at `0x1402a25b1`
- `watchdog!WdLogSingleEntry1` at `0x1402a25f1`
- `watchdog!WdLogSingleEntry1` at `0x1402a263d`
- `watchdog!WdLogSingleEntry1` at `0x1402a2689`
- `watchdog!WdLogSingleEntry1` at `0x1402a26c9`
- `watchdog!WdLogSingleEntry1` at `0x1402a273b`

## pseudocode

```c
__int64 __fastcall DpiCreateSecurityDescriptorForGpuVirtualization(_QWORD *a1)
{
  ULONG v2; // eax
  void *Pool2; // rax
  void *v4; // r14
  NTSTATUS Acl; // ebx
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rsi
  void *v11; // rdi
  ULONG v12; // eax
  void *v13; // rax
  size_t Size; // [rsp+20h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v17 = 0;
  LODWORD(Size) = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = RtlLengthRequiredSid(2u);
  Pool2 = (void *)ExAllocatePool2(256, v2, 1953656900);
  v4 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
    if ( Acl >= 0 )
    {
      *RtlSubAuthoritySid(v4, 0) = 83;
      *RtlSubAuthoritySid(v4, 1u) = 0;
      v6 = RtlLengthSid(SeExports->SeLocalSystemSid);
      v7 = RtlLengthSid(SeExports->SeAliasAdminsSid) + v6;
      v8 = RtlLengthSid(v4) + 32 + v7;
      v9 = (struct _ACL *)ExAllocatePool2(256, v8, 1953656900);
      v10 = v9;
      if ( v9 )
      {
        v11 = 0;
        Acl = RtlCreateAcl(v9, v8, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v10, 2u, 0x1F01FFu, SeExports->SeLocalSystemSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v10, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v10, 2u, 0x1F01FFu, v4);
              if ( Acl >= 0 )
              {
                Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                if ( Acl >= 0 )
                {
                  Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                      if ( Acl >= 0 )
                      {
                        v12 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                        LODWORD(Size) = v12;
                        if ( v12 >= 0x28 )
                        {
                          v13 = (void *)ExAllocatePool2(256, v12, 1953656900);
                          v11 = v13;
                          if ( v13 )
                          {
                            memset(v13, 0, (unsigned int)Size);
                            Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v11, (PULONG)&Size);
                            if ( Acl >= 0 )
                            {
                              *a1 = v11;
                              v11 = 0;
                              Acl = 0;
                            }
                            else
                            {
                              WdLogSingleEntry1(2);
                              WdLogGlobalForLineNumber = 335;
                            }
                          }
                          else
                          {
                            Acl = -1073741670;
                          }
                        }
                        else
                        {
                          Acl = -1073741595;
                          WdLogSingleEntry1(2);
                          WdLogGlobalForLineNumber = 316;
                        }
                      }
                      else
                      {
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 299;
                      }
                    }
                    else
                    {
                      WdLogSingleEntry1(2);
                      WdLogGlobalForLineNumber = 289;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 279;
                  }
                }
                else
                {
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 269;
                }
              }
              else
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 255;
              }
            }
            else
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 245;
            }
          }
          else
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 235;
          }
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 225;
        }
        ExFreePoolWithTag(v10, 0);
        if ( v11 )
          ExFreePoolWithTag(v11, 0);
      }
      else
      {
        Acl = -1073741670;
      }
    }
    else
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 195;
    }
    ExFreePoolWithTag(v4, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1402a22fc  mov     [rsp-28h+arg_8], rbx
0x1402a2301  mov     [rsp-28h+arg_10], rsi
0x1402a2306  push    rbp
0x1402a2307  push    rdi
0x1402a2308  push    r13
0x1402a230a  push    r14
0x1402a230c  push    r15
0x1402a230e  mov     rbp, rsp
0x1402a2311  sub     rsp, 60h
0x1402a2315  mov     rax, cs:__security_cookie
0x1402a231c  xor     rax, rsp
0x1402a231f  mov     [rbp+var_8], rax
0x1402a2323  xor     eax, eax
0x1402a2325  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1402a232b  xorps   xmm0, xmm0
0x1402a232e  mov     [rbp+var_18], rax
0x1402a2332  mov     r15, rcx
0x1402a2335  mov     dword ptr [rbp+Size], eax
0x1402a2338  movups  [rbp+SecurityDescriptor], xmm0
0x1402a233c  lea     r13d, [rax+2]
0x1402a2340  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x1402a2343  mov     ecx, r13d; SubAuthorityCount
0x1402a2346  movups  [rbp+var_28], xmm0
0x1402a234a  call    cs:__imp_RtlLengthRequiredSid
0x1402a2351  nop     dword ptr [rax+rax+00h]
0x1402a2356  mov     edi, 74727044h
0x1402a235b  mov     esi, 100h
0x1402a2360  mov     edx, eax
0x1402a2362  mov     r8d, edi
0x1402a2365  mov     ecx, esi
0x1402a2367  call    cs:__imp_ExAllocatePool2
0x1402a236e  nop     dword ptr [rax+rax+00h]
0x1402a2373  mov     r14, rax
0x1402a2376  test    rax, rax
0x1402a2379  jnz     short loc_1402A2385
0x1402a237b  mov     ebx, 0C000009Ah
0x1402a2380  jmp     loc_1402A2792
0x1402a2385  mov     r8b, r13b; SubAuthorityCount
0x1402a2388  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1402a238c  mov     rcx, r14; Sid
0x1402a238f  call    cs:__imp_RtlInitializeSid
0x1402a2396  nop     dword ptr [rax+rax+00h]
0x1402a239b  movsxd  rbx, eax
0x1402a239e  test    eax, eax
0x1402a23a0  jns     short loc_1402A23C3
0x1402a23a2  mov     rdx, rbx
0x1402a23a5  mov     ecx, r13d
0x1402a23a8  call    cs:__imp_WdLogSingleEntry1
0x1402a23af  nop     dword ptr [rax+rax+00h]
0x1402a23b4  mov     cs:WdLogGlobalForLineNumber, 0C3h
0x1402a23be  jmp     loc_1402A2781
0x1402a23c3  xor     edx, edx; SubAuthority
0x1402a23c5  mov     rcx, r14; Sid
0x1402a23c8  call    cs:__imp_RtlSubAuthoritySid
0x1402a23cf  nop     dword ptr [rax+rax+00h]
0x1402a23d4  mov     edx, 1; SubAuthority
0x1402a23d9  mov     rcx, r14; Sid
0x1402a23dc  mov     dword ptr [rax], 53h ; 'S'
0x1402a23e2  call    cs:__imp_RtlSubAuthoritySid
0x1402a23e9  nop     dword ptr [rax+rax+00h]
0x1402a23ee  mov     dword ptr [rax], 0
0x1402a23f4  mov     rax, cs:__imp_SeExports
0x1402a23fb  mov     rcx, [rax]
0x1402a23fe  mov     rcx, [rcx+108h]; Sid
0x1402a2405  call    cs:__imp_RtlLengthSid
0x1402a240c  nop     dword ptr [rax+rax+00h]
0x1402a2411  mov     rcx, cs:__imp_SeExports
0x1402a2418  mov     ebx, eax
0x1402a241a  mov     rcx, [rcx]
0x1402a241d  mov     rcx, [rcx+110h]; Sid
0x1402a2424  call    cs:__imp_RtlLengthSid
0x1402a242b  nop     dword ptr [rax+rax+00h]
0x1402a2430  mov     rcx, r14; Sid
0x1402a2433  add     ebx, eax
0x1402a2435  call    cs:__imp_RtlLengthSid
0x1402a243c  nop     dword ptr [rax+rax+00h]
0x1402a2441  mov     r8d, edi
0x1402a2444  mov     rcx, rsi
0x1402a2447  add     eax, 20h ; ' '
0x1402a244a  add     ebx, eax
0x1402a244c  mov     edx, ebx
0x1402a244e  call    cs:__imp_ExAllocatePool2
0x1402a2455  nop     dword ptr [rax+rax+00h]
0x1402a245a  mov     rsi, rax
0x1402a245d  test    rax, rax
0x1402a2460  jnz     short loc_1402A246C
0x1402a2462  mov     ebx, 0C000009Ah
0x1402a2467  jmp     loc_1402A2781
0x1402a246c  mov     r8d, r13d; AclRevision
0x1402a246f  mov     edx, ebx; AclLength
0x1402a2471  mov     rcx, rsi; Acl
0x1402a2474  xor     edi, edi
0x1402a2476  call    cs:__imp_RtlCreateAcl
0x1402a247d  nop     dword ptr [rax+rax+00h]
0x1402a2482  movsxd  rbx, eax
0x1402a2485  test    eax, eax
0x1402a2487  jns     short loc_1402A24AA
0x1402a2489  mov     rdx, rbx
0x1402a248c  mov     ecx, r13d
0x1402a248f  call    cs:__imp_WdLogSingleEntry1
0x1402a2496  nop     dword ptr [rax+rax+00h]
0x1402a249b  mov     cs:WdLogGlobalForLineNumber, 0E1h
0x1402a24a5  jmp     loc_1402A275A
0x1402a24aa  mov     rax, cs:__imp_SeExports
0x1402a24b1  mov     r8d, 1F01FFh; AccessMask
0x1402a24b7  mov     edx, r13d; AceRevision
0x1402a24ba  mov     rcx, rsi; Acl
0x1402a24bd  mov     r9, [rax]
0x1402a24c0  mov     r9, [r9+108h]; Sid
0x1402a24c7  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a24ce  nop     dword ptr [rax+rax+00h]
0x1402a24d3  movsxd  rbx, eax
0x1402a24d6  test    eax, eax
0x1402a24d8  jns     short loc_1402A24FB
0x1402a24da  mov     rdx, rbx
0x1402a24dd  mov     ecx, r13d
0x1402a24e0  call    cs:__imp_WdLogSingleEntry1
0x1402a24e7  nop     dword ptr [rax+rax+00h]
0x1402a24ec  mov     cs:WdLogGlobalForLineNumber, 0EBh
0x1402a24f6  jmp     loc_1402A275A
0x1402a24fb  mov     rax, cs:__imp_SeExports
0x1402a2502  mov     r8d, 1F01FFh; AccessMask
0x1402a2508  mov     edx, r13d; AceRevision
0x1402a250b  mov     rcx, rsi; Acl
0x1402a250e  mov     r9, [rax]
0x1402a2511  mov     r9, [r9+110h]; Sid
0x1402a2518  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a251f  nop     dword ptr [rax+rax+00h]
0x1402a2524  movsxd  rbx, eax
0x1402a2527  test    eax, eax
0x1402a2529  jns     short loc_1402A254C
0x1402a252b  mov     rdx, rbx
0x1402a252e  mov     ecx, r13d
0x1402a2531  call    cs:__imp_WdLogSingleEntry1
0x1402a2538  nop     dword ptr [rax+rax+00h]
0x1402a253d  mov     cs:WdLogGlobalForLineNumber, 0F5h
0x1402a2547  jmp     loc_1402A275A
0x1402a254c  mov     r9, r14; Sid
0x1402a254f  mov     r8d, 1F01FFh; AccessMask
0x1402a2555  mov     edx, r13d; AceRevision
0x1402a2558  mov     rcx, rsi; Acl
0x1402a255b  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a2562  nop     dword ptr [rax+rax+00h]
0x1402a2567  movsxd  rbx, eax
0x1402a256a  test    eax, eax
0x1402a256c  jns     short loc_1402A258F
0x1402a256e  mov     rdx, rbx
0x1402a2571  mov     ecx, r13d
0x1402a2574  call    cs:__imp_WdLogSingleEntry1
0x1402a257b  nop     dword ptr [rax+rax+00h]
0x1402a2580  mov     cs:WdLogGlobalForLineNumber, 0FFh
0x1402a258a  jmp     loc_1402A275A
0x1402a258f  mov     edx, 1; Revision
0x1402a2594  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a2598  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402a259f  nop     dword ptr [rax+rax+00h]
0x1402a25a4  movsxd  rbx, eax
0x1402a25a7  test    eax, eax
0x1402a25a9  jns     short loc_1402A25CC
0x1402a25ab  mov     rdx, rbx
0x1402a25ae  mov     ecx, r13d
0x1402a25b1  call    cs:__imp_WdLogSingleEntry1
0x1402a25b8  nop     dword ptr [rax+rax+00h]
0x1402a25bd  mov     cs:WdLogGlobalForLineNumber, 10Dh
0x1402a25c7  jmp     loc_1402A275A
0x1402a25cc  xor     r9d, r9d; DaclDefaulted
0x1402a25cf  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a25d3  mov     r8, rsi; Dacl
0x1402a25d6  mov     dl, 1; DaclPresent
0x1402a25d8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402a25df  nop     dword ptr [rax+rax+00h]
0x1402a25e4  movsxd  rbx, eax
0x1402a25e7  test    eax, eax
0x1402a25e9  jns     short loc_1402A260C
0x1402a25eb  mov     rdx, rbx
0x1402a25ee  mov     ecx, r13d
0x1402a25f1  call    cs:__imp_WdLogSingleEntry1
0x1402a25f8  nop     dword ptr [rax+rax+00h]
0x1402a25fd  mov     cs:WdLogGlobalForLineNumber, 117h
0x1402a2607  jmp     loc_1402A275A
0x1402a260c  mov     rax, cs:__imp_SeExports
0x1402a2613  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a2617  xor     r8d, r8d; OwnerDefaulted
0x1402a261a  mov     rdx, [rax]
0x1402a261d  mov     rdx, [rdx+108h]; Owner
0x1402a2624  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1402a262b  nop     dword ptr [rax+rax+00h]
0x1402a2630  movsxd  rbx, eax
0x1402a2633  test    eax, eax
0x1402a2635  jns     short loc_1402A2658
0x1402a2637  mov     rdx, rbx
0x1402a263a  mov     ecx, r13d
0x1402a263d  call    cs:__imp_WdLogSingleEntry1
0x1402a2644  nop     dword ptr [rax+rax+00h]
0x1402a2649  mov     cs:WdLogGlobalForLineNumber, 121h
0x1402a2653  jmp     loc_1402A275A
0x1402a2658  mov     rax, cs:__imp_SeExports
0x1402a265f  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a2663  xor     r8d, r8d; GroupDefaulted
0x1402a2666  mov     rdx, [rax]
0x1402a2669  mov     rdx, [rdx+108h]; Group
0x1402a2670  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1402a2677  nop     dword ptr [rax+rax+00h]
0x1402a267c  movsxd  rbx, eax
0x1402a267f  test    eax, eax
0x1402a2681  jns     short loc_1402A26A4
0x1402a2683  mov     rdx, rbx
0x1402a2686  mov     ecx, r13d
0x1402a2689  call    cs:__imp_WdLogSingleEntry1
0x1402a2690  nop     dword ptr [rax+rax+00h]
0x1402a2695  mov     cs:WdLogGlobalForLineNumber, 12Bh
0x1402a269f  jmp     loc_1402A275A
0x1402a26a4  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a26a8  call    cs:__imp_RtlLengthSecurityDescriptor
0x1402a26af  nop     dword ptr [rax+rax+00h]
0x1402a26b4  mov     dword ptr [rbp+Size], eax
0x1402a26b7  cmp     eax, 28h ; '('
0x1402a26ba  jnb     short loc_1402A26E1
0x1402a26bc  mov     rbx, 0FFFFFFFFC00000E5h
0x1402a26c3  mov     rdx, rbx
0x1402a26c6  mov     ecx, r13d
0x1402a26c9  call    cs:__imp_WdLogSingleEntry1
0x1402a26d0  nop     dword ptr [rax+rax+00h]
0x1402a26d5  mov     cs:WdLogGlobalForLineNumber, 13Ch
0x1402a26df  jmp     short loc_1402A275A
0x1402a26e1  mov     edx, eax
0x1402a26e3  mov     ecx, 100h
0x1402a26e8  mov     r8d, 74727044h
0x1402a26ee  call    cs:__imp_ExAllocatePool2
0x1402a26f5  nop     dword ptr [rax+rax+00h]
0x1402a26fa  mov     rdi, rax
0x1402a26fd  test    rax, rax
0x1402a2700  jnz     short loc_1402A2709
0x1402a2702  mov     ebx, 0C000009Ah
0x1402a2707  jmp     short loc_1402A275A
0x1402a2709  mov     r8d, dword ptr [rbp+Size]; Size
0x1402a270d  xor     edx, edx; Val
0x1402a270f  mov     rcx, rdi; void *
0x1402a2712  call    memset
0x1402a2717  lea     r8, [rbp+Size]; BufferLength
0x1402a271b  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1402a271e  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1402a2722  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1402a2729  nop     dword ptr [rax+rax+00h]
0x1402a272e  movsxd  rbx, eax
0x1402a2731  test    eax, eax
0x1402a2733  jns     short loc_1402A2753
0x1402a2735  mov     rdx, rbx
0x1402a2738  mov     ecx, r13d
0x1402a273b  call    cs:__imp_WdLogSingleEntry1
0x1402a2742  nop     dword ptr [rax+rax+00h]
0x1402a2747  mov     cs:WdLogGlobalForLineNumber, 14Fh
0x1402a2751  jmp     short loc_1402A275A
0x1402a2753  mov     [r15], rdi
0x1402a2756  xor     edi, edi
0x1402a2758  xor     ebx, ebx
0x1402a275a  xor     edx, edx; Tag
0x1402a275c  mov     rcx, rsi; P
0x1402a275f  call    cs:__imp_ExFreePoolWithTag
0x1402a2766  nop     dword ptr [rax+rax+00h]
0x1402a276b  test    rdi, rdi
0x1402a276e  jz      short loc_1402A2781
0x1402a2770  xor     edx, edx; Tag
0x1402a2772  mov     rcx, rdi; P
0x1402a2775  call    cs:__imp_ExFreePoolWithTag
0x1402a277c  nop     dword ptr [rax+rax+00h]
0x1402a2781  xor     edx, edx; Tag
0x1402a2783  mov     rcx, r14; P
0x1402a2786  call    cs:__imp_ExFreePoolWithTag
0x1402a278d  nop     dword ptr [rax+rax+00h]
0x1402a2792  mov     eax, ebx
0x1402a2794  mov     rcx, [rbp+var_8]
0x1402a2798  xor     rcx, rsp; StackCookie
0x1402a279b  call    __security_check_cookie
0x1402a27a0  lea     r11, [rsp+60h+var_s0]
0x1402a27a5  mov     rbx, [r11+38h]
0x1402a27a9  mov     rsi, [r11+40h]
0x1402a27ad  mov     rsp, r11
0x1402a27b0  pop     r15
0x1402a27b2  pop     r14
0x1402a27b4  pop     r13
0x1402a27b6  pop     rdi
0x1402a27b7  pop     rbp
0x1402a27b8  retn
```
