# DpiCreateSecurityDescriptorForGpuVirtualization

- ea: `0x1402a8cac`
- end: `0x1402a916a`
- name: `DpiCreateSecurityDescriptorForGpuVirtualization`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402b03e8`

## callees

- `0x1400a0bd0`
- `0x1400a1000`
- `0x1402a8cac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402a910f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9125`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9136`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a910f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9125`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9136`
- `ntoskrnl!ExAllocatePool2` at `0x1402a8d17`
- `ntoskrnl!ExAllocatePool2` at `0x1402a8dfe`
- `ntoskrnl!ExAllocatePool2` at `0x1402a909e`
- `ntoskrnl!ExAllocatePool2` at `0x1402a8d17`
- `ntoskrnl!ExAllocatePool2` at `0x1402a8dfe`
- `ntoskrnl!ExAllocatePool2` at `0x1402a909e`
- `ntoskrnl!SeExports` at `0x1402a8da4`
- `ntoskrnl!SeExports` at `0x1402a8dc1`
- `ntoskrnl!SeExports` at `0x1402a8e5a`
- `ntoskrnl!SeExports` at `0x1402a8eab`
- `ntoskrnl!SeExports` at `0x1402a8fbc`
- `ntoskrnl!SeExports` at `0x1402a9008`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402a8f48`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402a8f48`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1402a8cfa`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1402a8cfa`
- `ntoskrnl!RtlInitializeSid` at `0x1402a8d3f`
- `ntoskrnl!RtlInitializeSid` at `0x1402a8d3f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a8d78`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a8d92`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a8d78`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402a8d92`
- `ntoskrnl!RtlLengthSid` at `0x1402a8db5`
- `ntoskrnl!RtlLengthSid` at `0x1402a8dd4`
- `ntoskrnl!RtlLengthSid` at `0x1402a8de5`
- `ntoskrnl!RtlLengthSid` at `0x1402a8db5`
- `ntoskrnl!RtlLengthSid` at `0x1402a8dd4`
- `ntoskrnl!RtlLengthSid` at `0x1402a8de5`
- `ntoskrnl!RtlCreateAcl` at `0x1402a8e26`
- `ntoskrnl!RtlCreateAcl` at `0x1402a8e26`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8e77`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8ec8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8f0b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8e77`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8ec8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402a8f0b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402a8f88`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402a8f88`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1402a8fd4`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1402a8fd4`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1402a9020`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1402a9020`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402a90d2`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402a90d2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402a9058`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402a9058`
- `watchdog!WdLogSingleEntry1` at `0x1402a8d58`
- `watchdog!WdLogSingleEntry1` at `0x1402a8e3f`
- `watchdog!WdLogSingleEntry1` at `0x1402a8e90`
- `watchdog!WdLogSingleEntry1` at `0x1402a8ee1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8f24`
- `watchdog!WdLogSingleEntry1` at `0x1402a8f61`
- `watchdog!WdLogSingleEntry1` at `0x1402a8fa1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8fed`
- `watchdog!WdLogSingleEntry1` at `0x1402a9039`
- `watchdog!WdLogSingleEntry1` at `0x1402a9079`
- `watchdog!WdLogSingleEntry1` at `0x1402a90eb`
- `watchdog!WdLogSingleEntry1` at `0x1402a8d58`
- `watchdog!WdLogSingleEntry1` at `0x1402a8e3f`
- `watchdog!WdLogSingleEntry1` at `0x1402a8e90`
- `watchdog!WdLogSingleEntry1` at `0x1402a8ee1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8f24`
- `watchdog!WdLogSingleEntry1` at `0x1402a8f61`
- `watchdog!WdLogSingleEntry1` at `0x1402a8fa1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8fed`
- `watchdog!WdLogSingleEntry1` at `0x1402a9039`
- `watchdog!WdLogSingleEntry1` at `0x1402a9079`
- `watchdog!WdLogSingleEntry1` at `0x1402a90eb`

## pseudocode

```c
__int64 __fastcall DpiCreateSecurityDescriptorForGpuVirtualization(_QWORD *a1)
{
  ULONG v2; // eax
  void *Pool2; // rax
  void *v4; // r14
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  ULONG v7; // ebx
  ULONG v8; // ebx
  ULONG v9; // ebx
  struct _ACL *v10; // rax
  struct _ACL *v11; // rsi
  void *v12; // rdi
  NTSTATUS Acl; // eax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  ULONG v21; // eax
  void *v22; // rax
  NTSTATUS v23; // eax
  size_t Size; // [rsp+20h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v27; // [rsp+48h] [rbp-18h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v27 = 0;
  LODWORD(Size) = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = RtlLengthRequiredSid(2u);
  Pool2 = (void *)ExAllocatePool2(256, v2, 1953656900);
  v4 = Pool2;
  if ( Pool2 )
  {
    v6 = RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
    v5 = v6;
    if ( v6 >= 0 )
    {
      *RtlSubAuthoritySid(v4, 0) = 83;
      *RtlSubAuthoritySid(v4, 1u) = 0;
      v7 = RtlLengthSid(SeExports->SeLocalSystemSid);
      v8 = RtlLengthSid(SeExports->SeAliasAdminsSid) + v7;
      v9 = RtlLengthSid(v4) + 32 + v8;
      v10 = (struct _ACL *)ExAllocatePool2(256, v9, 1953656900);
      v11 = v10;
      if ( v10 )
      {
        v12 = 0;
        Acl = RtlCreateAcl(v10, v9, 2u);
        v5 = Acl;
        if ( Acl >= 0 )
        {
          v14 = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, SeExports->SeLocalSystemSid);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v15 = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
            v5 = v15;
            if ( v15 >= 0 )
            {
              v16 = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, v4);
              v5 = v16;
              if ( v16 >= 0 )
              {
                v17 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                v5 = v17;
                if ( v17 >= 0 )
                {
                  v18 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
                  v5 = v18;
                  if ( v18 >= 0 )
                  {
                    v19 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                    v5 = v19;
                    if ( v19 >= 0 )
                    {
                      v20 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                      v5 = v20;
                      if ( v20 >= 0 )
                      {
                        v21 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                        LODWORD(Size) = v21;
                        if ( v21 >= 0x28 )
                        {
                          v22 = (void *)ExAllocatePool2(256, v21, 1953656900);
                          v12 = v22;
                          if ( v22 )
                          {
                            memset(v22, 0, (unsigned int)Size);
                            v23 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v12, (PULONG)&Size);
                            v5 = v23;
                            if ( v23 >= 0 )
                            {
                              *a1 = v12;
                              v12 = 0;
                              v5 = 0;
                            }
                            else
                            {
                              WdLogSingleEntry1(2, v23);
                              WdLogGlobalForLineNumber = 336;
                            }
                          }
                          else
                          {
                            v5 = -1073741670;
                          }
                        }
                        else
                        {
                          v5 = -1073741595;
                          WdLogSingleEntry1(2, -1073741595);
                          WdLogGlobalForLineNumber = 317;
                        }
                      }
                      else
                      {
                        WdLogSingleEntry1(2, v20);
                        WdLogGlobalForLineNumber = 300;
                      }
                    }
                    else
                    {
                      WdLogSingleEntry1(2, v19);
                      WdLogGlobalForLineNumber = 290;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry1(2, v18);
                    WdLogGlobalForLineNumber = 280;
                  }
                }
                else
                {
                  WdLogSingleEntry1(2, v17);
                  WdLogGlobalForLineNumber = 270;
                }
              }
              else
              {
                WdLogSingleEntry1(2, v16);
                WdLogGlobalForLineNumber = 256;
              }
            }
            else
            {
              WdLogSingleEntry1(2, v15);
              WdLogGlobalForLineNumber = 246;
            }
          }
          else
          {
            WdLogSingleEntry1(2, v14);
            WdLogGlobalForLineNumber = 236;
          }
        }
        else
        {
          WdLogSingleEntry1(2, Acl);
          WdLogGlobalForLineNumber = 226;
        }
        ExFreePoolWithTag(v11, 0);
        if ( v12 )
          ExFreePoolWithTag(v12, 0);
      }
      else
      {
        v5 = -1073741670;
      }
    }
    else
    {
      WdLogSingleEntry1(2, v6);
      WdLogGlobalForLineNumber = 196;
    }
    ExFreePoolWithTag(v4, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v5;
}

```

## disassembly

```asm
0x1402a8cac  mov     [rsp-28h+arg_8], rbx
0x1402a8cb1  mov     [rsp-28h+arg_10], rsi
0x1402a8cb6  push    rbp
0x1402a8cb7  push    rdi
0x1402a8cb8  push    r13
0x1402a8cba  push    r14
0x1402a8cbc  push    r15
0x1402a8cbe  mov     rbp, rsp
0x1402a8cc1  sub     rsp, 60h
0x1402a8cc5  mov     rax, cs:__security_cookie
0x1402a8ccc  xor     rax, rsp
0x1402a8ccf  mov     [rbp+var_8], rax
0x1402a8cd3  xor     eax, eax
0x1402a8cd5  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1402a8cdb  xorps   xmm0, xmm0
0x1402a8cde  mov     [rbp+var_18], rax
0x1402a8ce2  mov     r15, rcx
0x1402a8ce5  mov     dword ptr [rbp+Size], eax
0x1402a8ce8  movups  [rbp+SecurityDescriptor], xmm0
0x1402a8cec  lea     r13d, [rax+2]
0x1402a8cf0  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x1402a8cf3  mov     ecx, r13d; SubAuthorityCount
0x1402a8cf6  movups  [rbp+var_28], xmm0
0x1402a8cfa  call    cs:__imp_RtlLengthRequiredSid
0x1402a8d01  nop     dword ptr [rax+rax+00h]
0x1402a8d06  mov     esi, 74727044h
0x1402a8d0b  mov     edi, 100h
0x1402a8d10  mov     edx, eax
0x1402a8d12  mov     r8d, esi
0x1402a8d15  mov     ecx, edi
0x1402a8d17  call    cs:__imp_ExAllocatePool2
0x1402a8d1e  nop     dword ptr [rax+rax+00h]
0x1402a8d23  mov     r14, rax
0x1402a8d26  test    rax, rax
0x1402a8d29  jnz     short loc_1402A8D35
0x1402a8d2b  mov     ebx, 0C000009Ah
0x1402a8d30  jmp     loc_1402A9142
0x1402a8d35  mov     r8b, r13b; SubAuthorityCount
0x1402a8d38  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1402a8d3c  mov     rcx, r14; Sid
0x1402a8d3f  call    cs:__imp_RtlInitializeSid
0x1402a8d46  nop     dword ptr [rax+rax+00h]
0x1402a8d4b  movsxd  rbx, eax
0x1402a8d4e  test    eax, eax
0x1402a8d50  jns     short loc_1402A8D73
0x1402a8d52  mov     rdx, rbx
0x1402a8d55  mov     ecx, r13d
0x1402a8d58  call    cs:__imp_WdLogSingleEntry1
0x1402a8d5f  nop     dword ptr [rax+rax+00h]
0x1402a8d64  mov     cs:WdLogGlobalForLineNumber, 0C4h
0x1402a8d6e  jmp     loc_1402A9131
0x1402a8d73  xor     edx, edx; SubAuthority
0x1402a8d75  mov     rcx, r14; Sid
0x1402a8d78  call    cs:__imp_RtlSubAuthoritySid
0x1402a8d7f  nop     dword ptr [rax+rax+00h]
0x1402a8d84  mov     edx, 1; SubAuthority
0x1402a8d89  mov     rcx, r14; Sid
0x1402a8d8c  mov     dword ptr [rax], 53h ; 'S'
0x1402a8d92  call    cs:__imp_RtlSubAuthoritySid
0x1402a8d99  nop     dword ptr [rax+rax+00h]
0x1402a8d9e  mov     dword ptr [rax], 0
0x1402a8da4  mov     rax, cs:__imp_SeExports
0x1402a8dab  mov     rcx, [rax]
0x1402a8dae  mov     rcx, [rcx+108h]; Sid
0x1402a8db5  call    cs:__imp_RtlLengthSid
0x1402a8dbc  nop     dword ptr [rax+rax+00h]
0x1402a8dc1  mov     rcx, cs:__imp_SeExports
0x1402a8dc8  mov     ebx, eax
0x1402a8dca  mov     rcx, [rcx]
0x1402a8dcd  mov     rcx, [rcx+110h]; Sid
0x1402a8dd4  call    cs:__imp_RtlLengthSid
0x1402a8ddb  nop     dword ptr [rax+rax+00h]
0x1402a8de0  mov     rcx, r14; Sid
0x1402a8de3  add     ebx, eax
0x1402a8de5  call    cs:__imp_RtlLengthSid
0x1402a8dec  nop     dword ptr [rax+rax+00h]
0x1402a8df1  mov     r8d, esi
0x1402a8df4  mov     rcx, rdi
0x1402a8df7  add     eax, 20h ; ' '
0x1402a8dfa  add     ebx, eax
0x1402a8dfc  mov     edx, ebx
0x1402a8dfe  call    cs:__imp_ExAllocatePool2
0x1402a8e05  nop     dword ptr [rax+rax+00h]
0x1402a8e0a  mov     rsi, rax
0x1402a8e0d  test    rax, rax
0x1402a8e10  jnz     short loc_1402A8E1C
0x1402a8e12  mov     ebx, 0C000009Ah
0x1402a8e17  jmp     loc_1402A9131
0x1402a8e1c  mov     r8d, r13d; AclRevision
0x1402a8e1f  mov     edx, ebx; AclLength
0x1402a8e21  mov     rcx, rsi; Acl
0x1402a8e24  xor     edi, edi
0x1402a8e26  call    cs:__imp_RtlCreateAcl
0x1402a8e2d  nop     dword ptr [rax+rax+00h]
0x1402a8e32  movsxd  rbx, eax
0x1402a8e35  test    eax, eax
0x1402a8e37  jns     short loc_1402A8E5A
0x1402a8e39  mov     rdx, rbx
0x1402a8e3c  mov     ecx, r13d
0x1402a8e3f  call    cs:__imp_WdLogSingleEntry1
0x1402a8e46  nop     dword ptr [rax+rax+00h]
0x1402a8e4b  mov     cs:WdLogGlobalForLineNumber, 0E2h
0x1402a8e55  jmp     loc_1402A910A
0x1402a8e5a  mov     rax, cs:__imp_SeExports
0x1402a8e61  mov     r8d, 1F01FFh; AccessMask
0x1402a8e67  mov     edx, r13d; AceRevision
0x1402a8e6a  mov     rcx, rsi; Acl
0x1402a8e6d  mov     r9, [rax]
0x1402a8e70  mov     r9, [r9+108h]; Sid
0x1402a8e77  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a8e7e  nop     dword ptr [rax+rax+00h]
0x1402a8e83  movsxd  rbx, eax
0x1402a8e86  test    eax, eax
0x1402a8e88  jns     short loc_1402A8EAB
0x1402a8e8a  mov     rdx, rbx
0x1402a8e8d  mov     ecx, r13d
0x1402a8e90  call    cs:__imp_WdLogSingleEntry1
0x1402a8e97  nop     dword ptr [rax+rax+00h]
0x1402a8e9c  mov     cs:WdLogGlobalForLineNumber, 0ECh
0x1402a8ea6  jmp     loc_1402A910A
0x1402a8eab  mov     rax, cs:__imp_SeExports
0x1402a8eb2  mov     r8d, 1F01FFh; AccessMask
0x1402a8eb8  mov     edx, r13d; AceRevision
0x1402a8ebb  mov     rcx, rsi; Acl
0x1402a8ebe  mov     r9, [rax]
0x1402a8ec1  mov     r9, [r9+110h]; Sid
0x1402a8ec8  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a8ecf  nop     dword ptr [rax+rax+00h]
0x1402a8ed4  movsxd  rbx, eax
0x1402a8ed7  test    eax, eax
0x1402a8ed9  jns     short loc_1402A8EFC
0x1402a8edb  mov     rdx, rbx
0x1402a8ede  mov     ecx, r13d
0x1402a8ee1  call    cs:__imp_WdLogSingleEntry1
0x1402a8ee8  nop     dword ptr [rax+rax+00h]
0x1402a8eed  mov     cs:WdLogGlobalForLineNumber, 0F6h
0x1402a8ef7  jmp     loc_1402A910A
0x1402a8efc  mov     r9, r14; Sid
0x1402a8eff  mov     r8d, 1F01FFh; AccessMask
0x1402a8f05  mov     edx, r13d; AceRevision
0x1402a8f08  mov     rcx, rsi; Acl
0x1402a8f0b  call    cs:__imp_RtlAddAccessAllowedAce
0x1402a8f12  nop     dword ptr [rax+rax+00h]
0x1402a8f17  movsxd  rbx, eax
0x1402a8f1a  test    eax, eax
0x1402a8f1c  jns     short loc_1402A8F3F
0x1402a8f1e  mov     rdx, rbx
0x1402a8f21  mov     ecx, r13d
0x1402a8f24  call    cs:__imp_WdLogSingleEntry1
0x1402a8f2b  nop     dword ptr [rax+rax+00h]
0x1402a8f30  mov     cs:WdLogGlobalForLineNumber, 100h
0x1402a8f3a  jmp     loc_1402A910A
0x1402a8f3f  mov     edx, 1; Revision
0x1402a8f44  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a8f48  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402a8f4f  nop     dword ptr [rax+rax+00h]
0x1402a8f54  movsxd  rbx, eax
0x1402a8f57  test    eax, eax
0x1402a8f59  jns     short loc_1402A8F7C
0x1402a8f5b  mov     rdx, rbx
0x1402a8f5e  mov     ecx, r13d
0x1402a8f61  call    cs:__imp_WdLogSingleEntry1
0x1402a8f68  nop     dword ptr [rax+rax+00h]
0x1402a8f6d  mov     cs:WdLogGlobalForLineNumber, 10Eh
0x1402a8f77  jmp     loc_1402A910A
0x1402a8f7c  xor     r9d, r9d; DaclDefaulted
0x1402a8f7f  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a8f83  mov     r8, rsi; Dacl
0x1402a8f86  mov     dl, 1; DaclPresent
0x1402a8f88  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402a8f8f  nop     dword ptr [rax+rax+00h]
0x1402a8f94  movsxd  rbx, eax
0x1402a8f97  test    eax, eax
0x1402a8f99  jns     short loc_1402A8FBC
0x1402a8f9b  mov     rdx, rbx
0x1402a8f9e  mov     ecx, r13d
0x1402a8fa1  call    cs:__imp_WdLogSingleEntry1
0x1402a8fa8  nop     dword ptr [rax+rax+00h]
0x1402a8fad  mov     cs:WdLogGlobalForLineNumber, 118h
0x1402a8fb7  jmp     loc_1402A910A
0x1402a8fbc  mov     rax, cs:__imp_SeExports
0x1402a8fc3  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a8fc7  xor     r8d, r8d; OwnerDefaulted
0x1402a8fca  mov     rdx, [rax]
0x1402a8fcd  mov     rdx, [rdx+108h]; Owner
0x1402a8fd4  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1402a8fdb  nop     dword ptr [rax+rax+00h]
0x1402a8fe0  movsxd  rbx, eax
0x1402a8fe3  test    eax, eax
0x1402a8fe5  jns     short loc_1402A9008
0x1402a8fe7  mov     rdx, rbx
0x1402a8fea  mov     ecx, r13d
0x1402a8fed  call    cs:__imp_WdLogSingleEntry1
0x1402a8ff4  nop     dword ptr [rax+rax+00h]
0x1402a8ff9  mov     cs:WdLogGlobalForLineNumber, 122h
0x1402a9003  jmp     loc_1402A910A
0x1402a9008  mov     rax, cs:__imp_SeExports
0x1402a900f  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a9013  xor     r8d, r8d; GroupDefaulted
0x1402a9016  mov     rdx, [rax]
0x1402a9019  mov     rdx, [rdx+108h]; Group
0x1402a9020  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1402a9027  nop     dword ptr [rax+rax+00h]
0x1402a902c  movsxd  rbx, eax
0x1402a902f  test    eax, eax
0x1402a9031  jns     short loc_1402A9054
0x1402a9033  mov     rdx, rbx
0x1402a9036  mov     ecx, r13d
0x1402a9039  call    cs:__imp_WdLogSingleEntry1
0x1402a9040  nop     dword ptr [rax+rax+00h]
0x1402a9045  mov     cs:WdLogGlobalForLineNumber, 12Ch
0x1402a904f  jmp     loc_1402A910A
0x1402a9054  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1402a9058  call    cs:__imp_RtlLengthSecurityDescriptor
0x1402a905f  nop     dword ptr [rax+rax+00h]
0x1402a9064  mov     dword ptr [rbp+Size], eax
0x1402a9067  cmp     eax, 28h ; '('
0x1402a906a  jnb     short loc_1402A9091
0x1402a906c  mov     rbx, 0FFFFFFFFC00000E5h
0x1402a9073  mov     rdx, rbx
0x1402a9076  mov     ecx, r13d
0x1402a9079  call    cs:__imp_WdLogSingleEntry1
0x1402a9080  nop     dword ptr [rax+rax+00h]
0x1402a9085  mov     cs:WdLogGlobalForLineNumber, 13Dh
0x1402a908f  jmp     short loc_1402A910A
0x1402a9091  mov     edx, eax
0x1402a9093  mov     ecx, 100h
0x1402a9098  mov     r8d, 74727044h
0x1402a909e  call    cs:__imp_ExAllocatePool2
0x1402a90a5  nop     dword ptr [rax+rax+00h]
0x1402a90aa  mov     rdi, rax
0x1402a90ad  test    rax, rax
0x1402a90b0  jnz     short loc_1402A90B9
0x1402a90b2  mov     ebx, 0C000009Ah
0x1402a90b7  jmp     short loc_1402A910A
0x1402a90b9  mov     r8d, dword ptr [rbp+Size]; Size
0x1402a90bd  xor     edx, edx; Val
0x1402a90bf  mov     rcx, rdi; void *
0x1402a90c2  call    memset
0x1402a90c7  lea     r8, [rbp+Size]; BufferLength
0x1402a90cb  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1402a90ce  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1402a90d2  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1402a90d9  nop     dword ptr [rax+rax+00h]
0x1402a90de  movsxd  rbx, eax
0x1402a90e1  test    eax, eax
0x1402a90e3  jns     short loc_1402A9103
0x1402a90e5  mov     rdx, rbx
0x1402a90e8  mov     ecx, r13d
0x1402a90eb  call    cs:__imp_WdLogSingleEntry1
0x1402a90f2  nop     dword ptr [rax+rax+00h]
0x1402a90f7  mov     cs:WdLogGlobalForLineNumber, 150h
0x1402a9101  jmp     short loc_1402A910A
0x1402a9103  mov     [r15], rdi
0x1402a9106  xor     edi, edi
0x1402a9108  xor     ebx, ebx
0x1402a910a  xor     edx, edx; Tag
0x1402a910c  mov     rcx, rsi; P
0x1402a910f  call    cs:__imp_ExFreePoolWithTag
0x1402a9116  nop     dword ptr [rax+rax+00h]
0x1402a911b  test    rdi, rdi
0x1402a911e  jz      short loc_1402A9131
0x1402a9120  xor     edx, edx; Tag
0x1402a9122  mov     rcx, rdi; P
0x1402a9125  call    cs:__imp_ExFreePoolWithTag
0x1402a912c  nop     dword ptr [rax+rax+00h]
0x1402a9131  xor     edx, edx; Tag
0x1402a9133  mov     rcx, r14; P
0x1402a9136  call    cs:__imp_ExFreePoolWithTag
0x1402a913d  nop     dword ptr [rax+rax+00h]
0x1402a9142  mov     eax, ebx
0x1402a9144  mov     rcx, [rbp+var_8]
0x1402a9148  xor     rcx, rsp; StackCookie
0x1402a914b  call    __security_check_cookie
0x1402a9150  lea     r11, [rsp+60h+var_s0]
0x1402a9155  mov     rbx, [r11+38h]
0x1402a9159  mov     rsi, [r11+40h]
0x1402a915d  mov     rsp, r11
0x1402a9160  pop     r15
0x1402a9162  pop     r14
0x1402a9164  pop     r13
0x1402a9166  pop     rdi
0x1402a9167  pop     rbp
0x1402a9168  retn
```
