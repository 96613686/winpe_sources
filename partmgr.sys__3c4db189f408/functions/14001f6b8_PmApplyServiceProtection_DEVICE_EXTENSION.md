# PmApplyServiceProtection(_DEVICE_EXTENSION *)

- ea: `0x14001f6b8`
- end: `0x14001f969`
- name: `?PmApplyServiceProtection@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140007674`

## callees

- `0x14001f6b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f93e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f94f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f93e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f94f`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14001f902`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14001f902`
- `ntoskrnl!RtlAddProcessTrustLabelAce` at `0x14001f8a8`
- `ntoskrnl!RtlAddProcessTrustLabelAce` at `0x14001f8a8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001f8e3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001f8e3`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001f922`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001f922`
- `ntoskrnl!ExAllocatePool2` at `0x14001f741`
- `ntoskrnl!ExAllocatePool2` at `0x14001f845`
- `ntoskrnl!ExAllocatePool2` at `0x14001f741`
- `ntoskrnl!ExAllocatePool2` at `0x14001f845`
- `ntoskrnl!RtlLengthSid` at `0x14001f6f2`
- `ntoskrnl!RtlLengthSid` at `0x14001f703`
- `ntoskrnl!RtlLengthSid` at `0x14001f723`
- `ntoskrnl!RtlLengthSid` at `0x14001f829`
- `ntoskrnl!RtlLengthSid` at `0x14001f6f2`
- `ntoskrnl!RtlLengthSid` at `0x14001f703`
- `ntoskrnl!RtlLengthSid` at `0x14001f723`
- `ntoskrnl!RtlLengthSid` at `0x14001f829`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f7a2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f7d2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f802`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f7a2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f7d2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001f802`
- `ntoskrnl!RtlCreateAcl` at `0x14001f76d`
- `ntoskrnl!RtlCreateAcl` at `0x14001f86b`
- `ntoskrnl!RtlCreateAcl` at `0x14001f76d`
- `ntoskrnl!RtlCreateAcl` at `0x14001f86b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001f8c4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001f8c4`
- `ntoskrnl!SeExports` at `0x14001f6c3`
- `ntoskrnl!SeExports` at `0x14001f712`
- `ntoskrnl!SeExports` at `0x14001f783`
- `ntoskrnl!SeExports` at `0x14001f7b8`
- `ntoskrnl!SeExports` at `0x14001f7e8`
- `ntoskrnl!SeExports` at `0x14001f818`
- `ntoskrnl!SeExports` at `0x14001f881`

## pseudocode

```c
__int64 __fastcall PmApplyServiceProtection(struct _DEVICE_EXTENSION *a1)
{
  PSID SeAliasAdminsSid; // rbx
  ULONG v3; // edi
  ULONG v4; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rdi
  NTSTATUS Acl; // ebx
  ULONG v8; // ebx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rsi
  __int128 SecurityDescriptor; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-38h]

  SecurityDescriptor = 0;
  v13 = 0;
  v14 = 0;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v3 = RtlLengthSid(SeExports->SeUserModeDriversSid);
  LODWORD(SeAliasAdminsSid) = v3 + RtlLengthSid(SeAliasAdminsSid);
  v4 = RtlLengthSid(SeExports->SeLocalSystemSid) + 32 + (_DWORD)SeAliasAdminsSid;
  Pool2 = (struct _ACL *)ExAllocatePool2(258, v4, 1128361296);
  v6 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlCreateAcl(Pool2, v4, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeLocalSystemSid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeUserModeDriversSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeAliasAdminsSid);
          if ( Acl >= 0 )
          {
            v8 = RtlLengthSid(SeExports->SeProcTrustWinTcbSid) + 16;
            v9 = (struct _ACL *)ExAllocatePool2(258, v8, 1128361296);
            v10 = v9;
            if ( v9 )
            {
              Acl = RtlCreateAcl(v9, v8, 2u);
              if ( Acl >= 0 )
              {
                Acl = RtlAddProcessTrustLabelAce(
                        v10,
                        2,
                        0,
                        SeExports->SeProcTrustWinTcbSid,
                        20,
                        1179785,
                        SecurityDescriptor,
                        *((_QWORD *)&SecurityDescriptor + 1),
                        v13,
                        *((_QWORD *)&v13 + 1),
                        v14);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, v6, 0);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlSetSaclSecurityDescriptor(&SecurityDescriptor, 1u, v10, 0);
                      if ( Acl >= 0 )
                      {
                        Acl = ObSetSecurityObjectByPointer(*((_QWORD *)a1 + 1), 132, &SecurityDescriptor);
                        *(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) |= 0x100u;
                      }
                    }
                  }
                }
              }
              ExFreePoolWithTag(v10, 0);
            }
            else
            {
              Acl = -1073741670;
            }
          }
        }
      }
    }
    ExFreePoolWithTag(v6, 0);
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
0x14001f6b8  push    rbx
0x14001f6ba  push    rbp
0x14001f6bb  push    rsi
0x14001f6bc  push    rdi
0x14001f6bd  push    r14
0x14001f6bf  sub     rsp, 60h
0x14001f6c3  mov     rdx, cs:__imp_SeExports
0x14001f6ca  xorps   xmm0, xmm0
0x14001f6cd  movups  [rsp+88h+SecurityDescriptor], xmm0
0x14001f6d2  xor     eax, eax
0x14001f6d4  mov     rbp, rcx
0x14001f6d7  movups  [rsp+88h+var_48], xmm0
0x14001f6dc  mov     [rsp+88h+var_38], rax
0x14001f6e1  mov     rax, [rdx]
0x14001f6e4  mov     rcx, [rax+210h]; Sid
0x14001f6eb  mov     rbx, [rax+110h]
0x14001f6f2  call    cs:__imp_RtlLengthSid
0x14001f6f9  nop     dword ptr [rax+rax+00h]
0x14001f6fe  mov     rcx, rbx; Sid
0x14001f701  mov     edi, eax
0x14001f703  call    cs:__imp_RtlLengthSid
0x14001f70a  nop     dword ptr [rax+rax+00h]
0x14001f70f  lea     ebx, [rdi+rax]
0x14001f712  mov     rax, cs:__imp_SeExports
0x14001f719  mov     rcx, [rax]
0x14001f71c  mov     rcx, [rcx+108h]; Sid
0x14001f723  call    cs:__imp_RtlLengthSid
0x14001f72a  nop     dword ptr [rax+rax+00h]
0x14001f72f  mov     ecx, 102h
0x14001f734  mov     r8d, 43416D50h
0x14001f73a  add     eax, 20h ; ' '
0x14001f73d  add     ebx, eax
0x14001f73f  mov     edx, ebx
0x14001f741  call    cs:__imp_ExAllocatePool2
0x14001f748  nop     dword ptr [rax+rax+00h]
0x14001f74d  mov     rdi, rax
0x14001f750  test    rax, rax
0x14001f753  jnz     short loc_14001F75F
0x14001f755  mov     ebx, 0C000009Ah
0x14001f75a  jmp     loc_14001F95B
0x14001f75f  mov     r14d, 2
0x14001f765  mov     edx, ebx; AclLength
0x14001f767  mov     r8d, r14d; AclRevision
0x14001f76a  mov     rcx, rdi; Acl
0x14001f76d  call    cs:__imp_RtlCreateAcl
0x14001f774  nop     dword ptr [rax+rax+00h]
0x14001f779  mov     ebx, eax
0x14001f77b  test    eax, eax
0x14001f77d  js      loc_14001F94A
0x14001f783  mov     rax, cs:__imp_SeExports
0x14001f78a  mov     esi, 80000000h
0x14001f78f  mov     r8d, esi; AccessMask
0x14001f792  mov     edx, r14d; AceRevision
0x14001f795  mov     rcx, rdi; Acl
0x14001f798  mov     r9, [rax]
0x14001f79b  mov     r9, [r9+108h]; Sid
0x14001f7a2  call    cs:__imp_RtlAddAccessAllowedAce
0x14001f7a9  nop     dword ptr [rax+rax+00h]
0x14001f7ae  mov     ebx, eax
0x14001f7b0  test    eax, eax
0x14001f7b2  js      loc_14001F94A
0x14001f7b8  mov     rax, cs:__imp_SeExports
0x14001f7bf  mov     r8d, esi; AccessMask
0x14001f7c2  mov     edx, r14d; AceRevision
0x14001f7c5  mov     rcx, rdi; Acl
0x14001f7c8  mov     r9, [rax]
0x14001f7cb  mov     r9, [r9+210h]; Sid
0x14001f7d2  call    cs:__imp_RtlAddAccessAllowedAce
0x14001f7d9  nop     dword ptr [rax+rax+00h]
0x14001f7de  mov     ebx, eax
0x14001f7e0  test    eax, eax
0x14001f7e2  js      loc_14001F94A
0x14001f7e8  mov     rax, cs:__imp_SeExports
0x14001f7ef  mov     r8d, esi; AccessMask
0x14001f7f2  mov     edx, r14d; AceRevision
0x14001f7f5  mov     rcx, rdi; Acl
0x14001f7f8  mov     r9, [rax]
0x14001f7fb  mov     r9, [r9+110h]; Sid
0x14001f802  call    cs:__imp_RtlAddAccessAllowedAce
0x14001f809  nop     dword ptr [rax+rax+00h]
0x14001f80e  mov     ebx, eax
0x14001f810  test    eax, eax
0x14001f812  js      loc_14001F94A
0x14001f818  mov     rax, cs:__imp_SeExports
0x14001f81f  mov     rcx, [rax]
0x14001f822  mov     rcx, [rcx+218h]; Sid
0x14001f829  call    cs:__imp_RtlLengthSid
0x14001f830  nop     dword ptr [rax+rax+00h]
0x14001f835  mov     ecx, 102h
0x14001f83a  mov     r8d, 43416D50h
0x14001f840  lea     ebx, [rax+10h]
0x14001f843  mov     edx, ebx
0x14001f845  call    cs:__imp_ExAllocatePool2
0x14001f84c  nop     dword ptr [rax+rax+00h]
0x14001f851  mov     rsi, rax
0x14001f854  test    rax, rax
0x14001f857  jnz     short loc_14001F863
0x14001f859  mov     ebx, 0C000009Ah
0x14001f85e  jmp     loc_14001F94A
0x14001f863  mov     r8d, r14d; AclRevision
0x14001f866  mov     edx, ebx; AclLength
0x14001f868  mov     rcx, rsi; Acl
0x14001f86b  call    cs:__imp_RtlCreateAcl
0x14001f872  nop     dword ptr [rax+rax+00h]
0x14001f877  mov     ebx, eax
0x14001f879  test    eax, eax
0x14001f87b  js      loc_14001F939
0x14001f881  mov     rax, cs:__imp_SeExports
0x14001f888  xor     r8d, r8d
0x14001f88b  mov     [rsp+88h+var_60], 120089h
0x14001f893  mov     edx, r14d
0x14001f896  mov     rcx, rsi
0x14001f899  mov     [rsp+88h+var_68], 14h
0x14001f89e  mov     r9, [rax]
0x14001f8a1  mov     r9, [r9+218h]
0x14001f8a8  call    cs:__imp_RtlAddProcessTrustLabelAce
0x14001f8af  nop     dword ptr [rax+rax+00h]
0x14001f8b4  mov     ebx, eax
0x14001f8b6  test    eax, eax
0x14001f8b8  js      short loc_14001F939
0x14001f8ba  mov     edx, 1; Revision
0x14001f8bf  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14001f8c4  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001f8cb  nop     dword ptr [rax+rax+00h]
0x14001f8d0  mov     ebx, eax
0x14001f8d2  test    eax, eax
0x14001f8d4  js      short loc_14001F939
0x14001f8d6  xor     r9d, r9d; DaclDefaulted
0x14001f8d9  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14001f8de  mov     r8, rdi; Dacl
0x14001f8e1  mov     dl, 1; DaclPresent
0x14001f8e3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001f8ea  nop     dword ptr [rax+rax+00h]
0x14001f8ef  mov     ebx, eax
0x14001f8f1  test    eax, eax
0x14001f8f3  js      short loc_14001F939
0x14001f8f5  xor     r9d, r9d; SaclDefaulted
0x14001f8f8  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14001f8fd  mov     r8, rsi; Sacl
0x14001f900  mov     dl, 1; SaclPresent
0x14001f902  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14001f909  nop     dword ptr [rax+rax+00h]
0x14001f90e  mov     ebx, eax
0x14001f910  test    eax, eax
0x14001f912  js      short loc_14001F939
0x14001f914  mov     rcx, [rbp+8]
0x14001f918  lea     r8, [rsp+88h+SecurityDescriptor]
0x14001f91d  mov     edx, 84h
0x14001f922  call    cs:__imp_ObSetSecurityObjectByPointer
0x14001f929  nop     dword ptr [rax+rax+00h]
0x14001f92e  mov     ebx, eax
0x14001f930  mov     rax, [rbp+8]
0x14001f934  bts     dword ptr [rax+34h], 8
0x14001f939  xor     edx, edx; Tag
0x14001f93b  mov     rcx, rsi; P
0x14001f93e  call    cs:__imp_ExFreePoolWithTag
0x14001f945  nop     dword ptr [rax+rax+00h]
0x14001f94a  xor     edx, edx; Tag
0x14001f94c  mov     rcx, rdi; P
0x14001f94f  call    cs:__imp_ExFreePoolWithTag
0x14001f956  nop     dword ptr [rax+rax+00h]
0x14001f95b  mov     eax, ebx
0x14001f95d  add     rsp, 60h
0x14001f961  pop     r14
0x14001f963  pop     rdi
0x14001f964  pop     rsi
0x14001f965  pop     rbp
0x14001f966  pop     rbx
0x14001f967  retn
```
