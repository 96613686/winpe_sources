# LsapDbInitializeRights(void)

- ea: `0x1801119ec`
- end: `0x180111cf7`
- name: `?LsapDbInitializeRights@@YAJXZ`
- size: `779`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a003c`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x1801119ec`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180111b7c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180111b7c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180111c52`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180111c52`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180111c2f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180111c2f`
- `ntdll!RtlNewSecurityObject` at `0x180111cb5`
- `ntdll!RtlNewSecurityObject` at `0x180111cb5`
- `ntdll!RtlAddAccessAllowedAce` at `0x180111c03`
- `ntdll!RtlAddAccessAllowedAce` at `0x180111c03`
- `ntdll!RtlCreateAcl` at `0x180111bd3`
- `ntdll!RtlCreateAcl` at `0x180111bd3`
- `ntdll!RtlLengthSid` at `0x180111ba0`
- `ntdll!RtlLengthSid` at `0x180111ba0`
- `ntdll!RtlInitUnicodeString` at `0x180111a18`
- `ntdll!RtlInitUnicodeString` at `0x180111a3c`
- `ntdll!RtlInitUnicodeString` at `0x180111a60`
- `ntdll!RtlInitUnicodeString` at `0x180111a84`
- `ntdll!RtlInitUnicodeString` at `0x180111aa8`
- `ntdll!RtlInitUnicodeString` at `0x180111acc`
- `ntdll!RtlInitUnicodeString` at `0x180111af0`
- `ntdll!RtlInitUnicodeString` at `0x180111b14`
- `ntdll!RtlInitUnicodeString` at `0x180111b38`
- `ntdll!RtlInitUnicodeString` at `0x180111b5c`
- `ntdll!RtlInitUnicodeString` at `0x180111cd5`
- `ntdll!RtlInitUnicodeString` at `0x180111a18`
- `ntdll!RtlInitUnicodeString` at `0x180111a3c`
- `ntdll!RtlInitUnicodeString` at `0x180111a60`
- `ntdll!RtlInitUnicodeString` at `0x180111a84`
- `ntdll!RtlInitUnicodeString` at `0x180111aa8`
- `ntdll!RtlInitUnicodeString` at `0x180111acc`
- `ntdll!RtlInitUnicodeString` at `0x180111af0`
- `ntdll!RtlInitUnicodeString` at `0x180111b14`
- `ntdll!RtlInitUnicodeString` at `0x180111b38`
- `ntdll!RtlInitUnicodeString` at `0x180111b5c`
- `ntdll!RtlInitUnicodeString` at `0x180111cd5`

## string_xrefs

- `0x180111a48`: `SeServiceLogonRight`
- `0x180111ad8`: `SeDenyServiceLogonRight`

## pseudocode

```c
__int64 LsapDbInitializeRights(void)
{
  NTSTATUS Acl; // ebx
  ULONG v1; // ebx
  struct _ACL *v2; // rax
  struct _ACL *v3; // rdi
  void *v4; // rdx
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-18h]

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v7 = 0;
  RtlInitUnicodeString(&LsapDbRightAndAccess, L"SeInteractiveLogonRight");
  dword_18019FBF0 = 1;
  RtlInitUnicodeString(&stru_18019FBF8, L"SeNetworkLogonRight");
  dword_18019FC08 = 2;
  RtlInitUnicodeString(&stru_18019FC10, L"SeServiceLogonRight");
  dword_18019FC20 = 16;
  RtlInitUnicodeString(&stru_18019FC28, L"SeBatchLogonRight");
  dword_18019FC38 = 4;
  RtlInitUnicodeString(&stru_18019FC40, L"SeDenyInteractiveLogonRight");
  dword_18019FC50 = 64;
  RtlInitUnicodeString(&stru_18019FC58, L"SeDenyNetworkLogonRight");
  dword_18019FC68 = 128;
  RtlInitUnicodeString(&stru_18019FC70, L"SeDenyServiceLogonRight");
  dword_18019FC80 = 512;
  RtlInitUnicodeString(&stru_18019FC88, L"SeDenyBatchLogonRight");
  dword_18019FC98 = 256;
  RtlInitUnicodeString(&stru_18019FCA0, L"SeRemoteInteractiveLogonRight");
  dword_18019FCB0 = 1024;
  RtlInitUnicodeString(&stru_18019FCB8, L"SeDenyRemoteInteractiveLogonRight");
  dword_18019FCC8 = 2048;
  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl >= 0 )
  {
    v1 = RtlLengthSid(*((PSID *)WellKnownSids + 96)) + 16;
    v2 = (struct _ACL *)LsapAllocate(v1);
    v3 = v2;
    if ( v2 )
    {
      Acl = RtlCreateAcl(v2, v1, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v3, 2u, 3u, *((PSID *)WellKnownSids + 96));
        if ( Acl >= 0 )
        {
          Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *((PSID *)WellKnownSids + 96), 0);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v3, 0);
            if ( Acl >= 0 )
            {
              UserRightGenericMapping.GenericRead = 131073;
              UserRightGenericMapping.GenericWrite = 131074;
              UserRightGenericMapping.GenericExecute = 0x20000;
              UserRightGenericMapping.GenericAll = 983043;
              Acl = RtlNewSecurityObject(
                      0,
                      SecurityDescriptor,
                      &UserRightSD,
                      0,
                      LsapGlobalProcessToken,
                      &UserRightGenericMapping);
              if ( Acl >= 0 )
                RtlInitUnicodeString(&UserRightTypeName, L"UserRightObject");
            }
          }
        }
      }
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v3, v4);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1801119ec  mov     [rsp+arg_0], rbx
0x1801119f1  push    rdi
0x1801119f2  sub     rsp, 60h
0x1801119f6  xorps   xmm0, xmm0
0x1801119f9  lea     rdx, aSeinteractivel; "SeInteractiveLogonRight"
0x180111a00  xor     eax, eax
0x180111a02  lea     rcx, ?LsapDbRightAndAccess@@3PAU_LSAP_DB_RIGHT_AND_ACCESS@@A; DestinationString
0x180111a09  movups  [rsp+68h+SecurityDescriptor], xmm0
0x180111a0e  mov     [rsp+68h+var_18], rax
0x180111a13  movups  [rsp+68h+var_28], xmm0
0x180111a18  call    cs:__imp_RtlInitUnicodeString
0x180111a1f  nop     dword ptr [rax+rax+00h]
0x180111a24  lea     rdx, aSenetworklogon; "SeNetworkLogonRight"
0x180111a2b  mov     cs:dword_18019FBF0, 1
0x180111a35  lea     rcx, stru_18019FBF8; DestinationString
0x180111a3c  call    cs:__imp_RtlInitUnicodeString
0x180111a43  nop     dword ptr [rax+rax+00h]
0x180111a48  lea     rdx, aSeservicelogon; "SeServiceLogonRight"
0x180111a4f  mov     cs:dword_18019FC08, 2
0x180111a59  lea     rcx, stru_18019FC10; DestinationString
0x180111a60  call    cs:__imp_RtlInitUnicodeString
0x180111a67  nop     dword ptr [rax+rax+00h]
0x180111a6c  lea     rdx, aSebatchlogonri; "SeBatchLogonRight"
0x180111a73  mov     cs:dword_18019FC20, 10h
0x180111a7d  lea     rcx, stru_18019FC28; DestinationString
0x180111a84  call    cs:__imp_RtlInitUnicodeString
0x180111a8b  nop     dword ptr [rax+rax+00h]
0x180111a90  lea     rdx, aSedenyinteract; "SeDenyInteractiveLogonRight"
0x180111a97  mov     cs:dword_18019FC38, 4
0x180111aa1  lea     rcx, stru_18019FC40; DestinationString
0x180111aa8  call    cs:__imp_RtlInitUnicodeString
0x180111aaf  nop     dword ptr [rax+rax+00h]
0x180111ab4  lea     rdx, aSedenynetworkl; "SeDenyNetworkLogonRight"
0x180111abb  mov     cs:dword_18019FC50, 40h ; '@'
0x180111ac5  lea     rcx, stru_18019FC58; DestinationString
0x180111acc  call    cs:__imp_RtlInitUnicodeString
0x180111ad3  nop     dword ptr [rax+rax+00h]
0x180111ad8  lea     rdx, aSedenyservicel; "SeDenyServiceLogonRight"
0x180111adf  mov     cs:dword_18019FC68, 80h
0x180111ae9  lea     rcx, stru_18019FC70; DestinationString
0x180111af0  call    cs:__imp_RtlInitUnicodeString
0x180111af7  nop     dword ptr [rax+rax+00h]
0x180111afc  lea     rdx, aSedenybatchlog; "SeDenyBatchLogonRight"
0x180111b03  mov     cs:dword_18019FC80, 200h
0x180111b0d  lea     rcx, stru_18019FC88; DestinationString
0x180111b14  call    cs:__imp_RtlInitUnicodeString
0x180111b1b  nop     dword ptr [rax+rax+00h]
0x180111b20  lea     rdx, aSeremoteintera; "SeRemoteInteractiveLogonRight"
0x180111b27  mov     cs:dword_18019FC98, 100h
0x180111b31  lea     rcx, stru_18019FCA0; DestinationString
0x180111b38  call    cs:__imp_RtlInitUnicodeString
0x180111b3f  nop     dword ptr [rax+rax+00h]
0x180111b44  lea     rdx, aSedenyremotein; "SeDenyRemoteInteractiveLogonRight"
0x180111b4b  mov     cs:dword_18019FCB0, 400h
0x180111b55  lea     rcx, stru_18019FCB8; DestinationString
0x180111b5c  call    cs:__imp_RtlInitUnicodeString
0x180111b63  nop     dword ptr [rax+rax+00h]
0x180111b68  mov     edx, 1; Revision
0x180111b6d  mov     cs:dword_18019FCC8, 800h
0x180111b77  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180111b7c  call    cs:__imp_RtlCreateSecurityDescriptor
0x180111b83  nop     dword ptr [rax+rax+00h]
0x180111b88  mov     ebx, eax
0x180111b8a  test    eax, eax
0x180111b8c  js      loc_180111CE9
0x180111b92  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180111b99  mov     rcx, [rcx+300h]; Sid
0x180111ba0  call    cs:__imp_RtlLengthSid
0x180111ba7  nop     dword ptr [rax+rax+00h]
0x180111bac  lea     ebx, [rax+10h]
0x180111baf  mov     ecx, ebx
0x180111bb1  call    LsapAllocate
0x180111bb6  mov     rdi, rax
0x180111bb9  test    rax, rax
0x180111bbc  jnz     short loc_180111BC8
0x180111bbe  mov     ebx, 0C000009Ah
0x180111bc3  jmp     loc_180111CE9
0x180111bc8  mov     r8d, 2; AclRevision
0x180111bce  mov     edx, ebx; AclSize
0x180111bd0  mov     rcx, rdi; Acl
0x180111bd3  call    cs:__imp_RtlCreateAcl
0x180111bda  nop     dword ptr [rax+rax+00h]
0x180111bdf  mov     ebx, eax
0x180111be1  test    eax, eax
0x180111be3  js      loc_180111CE1
0x180111be9  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180111bf0  mov     edx, 2; Revision
0x180111bf5  mov     rcx, rdi; Acl
0x180111bf8  mov     r9, [r9+300h]; Sid
0x180111bff  lea     r8d, [rdx+1]; AccessMask
0x180111c03  call    cs:__imp_RtlAddAccessAllowedAce
0x180111c0a  nop     dword ptr [rax+rax+00h]
0x180111c0f  mov     ebx, eax
0x180111c11  test    eax, eax
0x180111c13  js      loc_180111CE1
0x180111c19  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180111c20  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180111c25  xor     r8d, r8d; OwnerDefaulted
0x180111c28  mov     rdx, [rdx+300h]; Owner
0x180111c2f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180111c36  nop     dword ptr [rax+rax+00h]
0x180111c3b  mov     ebx, eax
0x180111c3d  test    eax, eax
0x180111c3f  js      loc_180111CE1
0x180111c45  xor     r9d, r9d; DaclDefaulted
0x180111c48  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180111c4d  mov     r8, rdi; Dacl
0x180111c50  mov     dl, 1; DaclPresent
0x180111c52  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180111c59  nop     dword ptr [rax+rax+00h]
0x180111c5e  mov     ebx, eax
0x180111c60  test    eax, eax
0x180111c62  js      short loc_180111CE1
0x180111c64  lea     rax, ?UserRightGenericMapping@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING UserRightGenericMapping
0x180111c6b  mov     cs:?UserRightGenericMapping@@3U_GENERIC_MAPPING@@A.GenericRead, 20001h; _GENERIC_MAPPING UserRightGenericMapping ...
0x180111c75  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x180111c7a  lea     r8, ?UserRightSD@@3PEAXEA; NewDescriptor
0x180111c81  mov     rax, cs:?LsapGlobalProcessToken@@3PEAXEA; void * LsapGlobalProcessToken
0x180111c88  lea     rdx, [rsp+68h+SecurityDescriptor]; CreatorDescriptor
0x180111c8d  xor     r9d, r9d; IsDirectoryObject
0x180111c90  mov     [rsp+68h+Token], rax; Token
0x180111c95  xor     ecx, ecx; ParentDescriptor
0x180111c97  mov     cs:?UserRightGenericMapping@@3U_GENERIC_MAPPING@@A.GenericWrite, 20002h; _GENERIC_MAPPING UserRightGenericMapping ...
0x180111ca1  mov     cs:?UserRightGenericMapping@@3U_GENERIC_MAPPING@@A.GenericExecute, 20000h; _GENERIC_MAPPING UserRightGenericMapping ...
0x180111cab  mov     cs:?UserRightGenericMapping@@3U_GENERIC_MAPPING@@A.GenericAll, 0F0003h; _GENERIC_MAPPING UserRightGenericMapping ...
0x180111cb5  call    cs:__imp_RtlNewSecurityObject
0x180111cbc  nop     dword ptr [rax+rax+00h]
0x180111cc1  mov     ebx, eax
0x180111cc3  test    eax, eax
0x180111cc5  js      short loc_180111CE1
0x180111cc7  lea     rdx, aUserrightobjec; "UserRightObject"
0x180111cce  lea     rcx, ?UserRightTypeName@@3U_UNICODE_STRING@@A; DestinationString
0x180111cd5  call    cs:__imp_RtlInitUnicodeString
0x180111cdc  nop     dword ptr [rax+rax+00h]
0x180111ce1  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x180111ce4  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180111ce9  mov     eax, ebx
0x180111ceb  mov     rbx, [rsp+68h+arg_0]
0x180111cf0  add     rsp, 60h
0x180111cf4  pop     rdi
0x180111cf5  retn
```
