# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x18004eda4`
- end: `0x18004eff0`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ea00`

## callees

- `0x180002b60`
- `0x180005a9c`
- `0x1800076d4`
- `0x18004eda4`
- `0x18005318c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eee9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004eefa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004eefa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004ee47`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004ee47`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004ee2d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004ee2d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004eded`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004eded`
- `ntdll!RtlQueryInformationAcl` at `0x18004ee94`
- `ntdll!RtlQueryInformationAcl` at `0x18004eec1`
- `ntdll!RtlQueryInformationAcl` at `0x18004ee94`
- `ntdll!RtlQueryInformationAcl` at `0x18004eec1`
- `ntdll!RtlLengthSid` at `0x18004eed8`
- `ntdll!RtlLengthSid` at `0x18004eed8`
- `ntdll!RtlCreateAcl` at `0x18004ef34`
- `ntdll!RtlCreateAcl` at `0x18004ef34`
- `ntdll!RtlGetAce` at `0x18004ef5a`
- `ntdll!RtlGetAce` at `0x18004ef5a`
- `ntdll!RtlAddAce` at `0x18004ef82`
- `ntdll!RtlAddAce` at `0x18004ef82`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004efbb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004efbb`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004ef9f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004ef9f`

## string_xrefs

- `0x18004ee00`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004ef0c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004efd2`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall BuildUserSD(void *a1, void *a2, ACCESS_MASK a3, bool *a4, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS DaclSecurityDescriptor; // eax
  __int64 v9; // rdx
  DWORD i; // ebx
  _DWORD *v12; // rdi
  ULONG v13; // eax
  ULONG v14; // r14d
  HANDLE ProcessHeap; // rax
  struct _ACL *v16; // rax
  struct _ACL *v17; // rdi
  int v18; // ebx
  NTSTATUS Acl; // eax
  __int64 v20; // rdx
  ULONG AceListLength; // [rsp+20h] [rbp-50h]
  unsigned __int8 DaclDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  ULONG AclRevision; // [rsp+34h] [rbp-3Ch] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-28h] BYREF
  __int64 Information; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  DaclPresent[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a1, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 41;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  for ( i = 0; i < Dacl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(Dacl, i, &pAce) )
    {
      v12 = pAce;
      if ( !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, a2) && (a3 & v12[1]) == a3 )
      {
        *a4 = 1;
        return 0;
      }
    }
  }
  Information = 0;
  v29 = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 61;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  AclRevision = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 64;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  v13 = RtlLengthSid(a2);
  v14 = v13 + HIDWORD(Information) + 8;
  ProcessHeap = GetProcessHeap();
  v16 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v14);
  v17 = v16;
  if ( v16 )
  {
    Acl = RtlCreateAcl(v16, v14, AclRevision);
    if ( Acl >= 0 )
    {
      Ace = 0;
      Acl = RtlGetAce(Dacl, 0, &Ace);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAce(v17, AclRevision, 0, Ace, HIDWORD(Information) - 8);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v17, AclRevision, a3, a2);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v17, 0);
            if ( Acl >= 0 )
              return 0;
            v20 = 83;
          }
          else
          {
            v20 = 81;
          }
        }
        else
        {
          v20 = 78;
        }
      }
      else
      {
        v20 = 76;
      }
    }
    else
    {
      v20 = 73;
    }
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)Acl,
            AceListLength);
    MemoryFree(v17);
  }
  else
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8007000ELL,
      AceListLength);
  }
  return v18;
}

```

## disassembly

```asm
0x18004eda4  push    rbp
0x18004eda6  push    rbx
0x18004eda7  push    rsi
0x18004eda8  push    rdi
0x18004eda9  push    r12
0x18004edab  push    r14
0x18004edad  push    r15
0x18004edaf  mov     rbp, rsp
0x18004edb2  sub     rsp, 70h
0x18004edb6  mov     rax, cs:__security_cookie
0x18004edbd  xor     rax, rsp
0x18004edc0  mov     [rbp+var_10], rax
0x18004edc4  mov     r12, [rbp+SecurityDescriptor]
0x18004edc8  mov     r14, r9
0x18004edcb  mov     esi, r8d
0x18004edce  mov     [rbp+DaclPresent], 0
0x18004edd2  mov     r15, rdx
0x18004edd5  mov     [rbp+Dacl], 0
0x18004eddd  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x18004ede1  mov     [rbp+DaclDefaulted], 0
0x18004ede5  lea     r8, [rbp+Dacl]; Dacl
0x18004ede9  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18004eded  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18004edf3  test    eax, eax
0x18004edf5  jns     short loc_18004EE11
0x18004edf7  mov     edx, 29h ; ')'; void *
0x18004edfc  mov     rcx, [rbp+38h]; this
0x18004ee00  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ee07  mov     r9d, eax; char *
0x18004ee0a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004ee0f  jmp     short loc_18004EE64
0x18004ee11  xor     ebx, ebx
0x18004ee13  mov     rcx, [rbp+Dacl]; Acl
0x18004ee17  movzx   eax, word ptr [rcx+4]
0x18004ee1b  cmp     ebx, eax
0x18004ee1d  jnb     short loc_18004EE7F
0x18004ee1f  lea     r8, [rbp+pAce]; pAce
0x18004ee23  mov     [rbp+pAce], 0
0x18004ee2b  mov     edx, ebx; dwAceIndex
0x18004ee2d  call    cs:__imp_GetAce
0x18004ee33  test    eax, eax
0x18004ee35  jz      short loc_18004EE5A
0x18004ee37  mov     rdi, [rbp+pAce]
0x18004ee3b  cmp     byte ptr [rdi], 0
0x18004ee3e  jnz     short loc_18004EE5A
0x18004ee40  lea     rcx, [rdi+8]; pSid1
0x18004ee44  mov     rdx, r15; pSid2
0x18004ee47  call    cs:__imp_EqualSid
0x18004ee4d  test    eax, eax
0x18004ee4f  jz      short loc_18004EE5A
0x18004ee51  mov     eax, [rdi+4]
0x18004ee54  and     eax, esi
0x18004ee56  cmp     eax, esi
0x18004ee58  jz      short loc_18004EE5E
0x18004ee5a  inc     ebx
0x18004ee5c  jmp     short loc_18004EE13
0x18004ee5e  mov     byte ptr [r14], 1
0x18004ee62  xor     eax, eax
0x18004ee64  mov     rcx, [rbp+var_10]
0x18004ee68  xor     rcx, rsp; StackCookie
0x18004ee6b  call    __security_check_cookie
0x18004ee70  add     rsp, 70h
0x18004ee74  pop     r15
0x18004ee76  pop     r14
0x18004ee78  pop     r12
0x18004ee7a  pop     rdi
0x18004ee7b  pop     rsi
0x18004ee7c  pop     rbx
0x18004ee7d  pop     rbp
0x18004ee7e  retn
0x18004ee7f  xor     eax, eax
0x18004ee81  lea     rdx, [rbp+Information]; Information
0x18004ee85  mov     [rbp+Information], rax
0x18004ee89  mov     [rbp+var_18], eax
0x18004ee8c  lea     r9d, [rax+2]; InformationClass
0x18004ee90  lea     r8d, [rax+0Ch]; InformationLength
0x18004ee94  call    cs:__imp_RtlQueryInformationAcl
0x18004ee9a  test    eax, eax
0x18004ee9c  jns     short loc_18004EEA8
0x18004ee9e  mov     edx, 3Dh ; '='
0x18004eea3  jmp     loc_18004EDFC
0x18004eea8  mov     rcx, [rbp+Dacl]; Acl
0x18004eeac  lea     rdx, [rbp+AclRevision]; Information
0x18004eeb0  mov     r9d, 1; InformationClass
0x18004eeb6  mov     [rbp+AclRevision], 0
0x18004eebd  lea     r8d, [r9+3]; InformationLength
0x18004eec1  call    cs:__imp_RtlQueryInformationAcl
0x18004eec7  test    eax, eax
0x18004eec9  jns     short loc_18004EED5
0x18004eecb  mov     edx, 40h ; '@'
0x18004eed0  jmp     loc_18004EDFC
0x18004eed5  mov     rcx, r15; Sid
0x18004eed8  call    cs:__imp_RtlLengthSid
0x18004eede  mov     r14d, dword ptr [rbp+Information+4]
0x18004eee2  add     r14d, 8
0x18004eee6  add     r14d, eax
0x18004eee9  call    cs:__imp_GetProcessHeap
0x18004eeef  mov     r8d, r14d; dwBytes
0x18004eef2  mov     edx, 8; dwFlags
0x18004eef7  mov     rcx, rax; hHeap
0x18004eefa  call    cs:__imp_HeapAlloc
0x18004ef00  mov     rdi, rax
0x18004ef03  test    rax, rax
0x18004ef06  jnz     short loc_18004EF2A
0x18004ef08  mov     rcx, [rbp+38h]; this
0x18004ef0c  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ef13  mov     ebx, 8007000Eh
0x18004ef18  lea     edx, [rax+47h]; void *
0x18004ef1b  mov     r9d, ebx; char *
0x18004ef1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef23  mov     eax, ebx
0x18004ef25  jmp     loc_18004EE64
0x18004ef2a  mov     r8d, [rbp+AclRevision]; AclRevision
0x18004ef2e  mov     edx, r14d; AclSize
0x18004ef31  mov     rcx, rdi; Acl
0x18004ef34  call    cs:__imp_RtlCreateAcl
0x18004ef3a  test    eax, eax
0x18004ef3c  jns     short loc_18004EF48
0x18004ef3e  mov     edx, 49h ; 'I'
0x18004ef43  jmp     loc_18004EFCE
0x18004ef48  mov     rcx, [rbp+Dacl]; Acl
0x18004ef4c  lea     r8, [rbp+Ace]; Ace
0x18004ef50  xor     edx, edx; AceIndex
0x18004ef52  mov     [rbp+Ace], 0
0x18004ef5a  call    cs:__imp_RtlGetAce
0x18004ef60  test    eax, eax
0x18004ef62  jns     short loc_18004EF6B
0x18004ef64  mov     edx, 4Ch ; 'L'
0x18004ef69  jmp     short loc_18004EFCE
0x18004ef6b  mov     eax, dword ptr [rbp+Information+4]
0x18004ef6e  xor     r8d, r8d; StartingAceIndex
0x18004ef71  mov     r9, [rbp+Ace]; AceList
0x18004ef75  add     eax, 0FFFFFFF8h
0x18004ef78  mov     edx, [rbp+AclRevision]; AceRevision
0x18004ef7b  mov     rcx, rdi; Acl
0x18004ef7e  mov     [rsp+70h+AceListLength], eax; int
0x18004ef82  call    cs:__imp_RtlAddAce
0x18004ef88  test    eax, eax
0x18004ef8a  jns     short loc_18004EF93
0x18004ef8c  mov     edx, 4Eh ; 'N'
0x18004ef91  jmp     short loc_18004EFCE
0x18004ef93  mov     edx, [rbp+AclRevision]; Revision
0x18004ef96  mov     r9, r15; Sid
0x18004ef99  mov     r8d, esi; AccessMask
0x18004ef9c  mov     rcx, rdi; Acl
0x18004ef9f  call    cs:__imp_RtlAddAccessAllowedAce
0x18004efa5  test    eax, eax
0x18004efa7  jns     short loc_18004EFB0
0x18004efa9  mov     edx, 51h ; 'Q'
0x18004efae  jmp     short loc_18004EFCE
0x18004efb0  xor     r9d, r9d; DaclDefaulted
0x18004efb3  mov     r8, rdi; Dacl
0x18004efb6  mov     dl, 1; DaclPresent
0x18004efb8  mov     rcx, r12; SecurityDescriptor
0x18004efbb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18004efc1  test    eax, eax
0x18004efc3  jns     loc_18004EE62
0x18004efc9  mov     edx, 53h ; 'S'; void *
0x18004efce  mov     rcx, [rbp+38h]; this
0x18004efd2  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004efd9  mov     r9d, eax; char *
0x18004efdc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004efe1  mov     rcx, rdi; void *
0x18004efe4  mov     ebx, eax
0x18004efe6  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004efeb  jmp     loc_18004EF23
```
