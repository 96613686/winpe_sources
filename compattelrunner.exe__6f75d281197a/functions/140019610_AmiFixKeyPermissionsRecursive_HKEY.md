# AmiFixKeyPermissionsRecursive(HKEY__ *)

- ea: `0x140019610`
- end: `0x14001976d`
- name: `?AmiFixKeyPermissionsRecursive@@YAKPEAUHKEY__@@@Z`
- size: `349`
- prototype: `unsigned int __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019fa0`

## callees

- `0x140001ba0`
- `0x1400151b0`
- `0x140018a34`
- `0x140019610`
- `0x140019774`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400196ba`
- `ntdll!RtlNtStatusToDosError` at `0x1400196ba`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400196ae`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400196ae`
- `ntdll!RtlFreeSid` at `0x14001974d`
- `ntdll!RtlFreeSid` at `0x14001974d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400196e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400196e6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400196dc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400196dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001973a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001973a`

## string_xrefs

- `0x140019669`: `AmiUtilityInitSecurityDescriptor failed [%d]`
- `0x1400196c0`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x1400196ec`: `SetSecurityDescriptorOwner failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiFixKeyPermissionsRecursive(HKEY a1)
{
  unsigned int inited; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  int v6; // eax
  __int64 SubAuthority2; // [rsp+20h] [rbp-59h]
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-11h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v12; // [rsp+90h] [rbp+17h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp+1Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  pOwner = 0;
  v12 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  inited = AmiUtilityInitSecurityDescriptor(pSecurityDescriptor, (PACL *)&hMem);
  v3 = inited;
  if ( inited )
  {
    v4 = "AmiUtilityInitSecurityDescriptor failed [%d]";
    v5 = 1026;
  }
  else
  {
    v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner);
    if ( v6 >= 0 )
    {
      if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
      {
        inited = AmiFixKeyPermissionsRecursiveHelper(a1, pSecurityDescriptor);
        v3 = inited;
        if ( !inited )
          goto LABEL_10;
        v4 = "AmiFixKeyPermissionsRecursiveHelper failed [%d]";
        v5 = 1061;
      }
      else
      {
        inited = GetLastError();
        v4 = "SetSecurityDescriptorOwner failed [%d]";
        v5 = 1054;
        v3 = inited;
      }
    }
    else
    {
      inited = RtlNtStatusToDosError(v6);
      v4 = "RtlAllocateAndInitializeSid failed [%d]";
      v5 = 1047;
      v3 = inited;
    }
  }
  LODWORD(SubAuthority2) = inited;
  AslLogCallPrintf(1, "AmiFixKeyPermissionsRecursive", v5, v4, SubAuthority2);
LABEL_10:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( pOwner )
    RtlFreeSid(pOwner);
  return v3;
}

```

## disassembly

```asm
0x140019610  push    rbp
0x140019612  push    rbx
0x140019613  push    rsi
0x140019614  push    rdi
0x140019615  lea     rbp, [rsp-3Fh]
0x14001961a  sub     rsp, 0B8h
0x140019621  mov     rax, cs:__security_cookie
0x140019628  xor     rax, rsp
0x14001962b  mov     [rbp+57h+var_30], rax
0x14001962f  xorps   xmm0, xmm0
0x140019632  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x140019638  xor     esi, esi
0x14001963a  lea     rdx, [rbp+57h+hMem]; NewAcl
0x14001963e  mov     rdi, rcx
0x140019641  mov     [rbp+57h+hMem], rsi
0x140019645  xor     eax, eax
0x140019647  mov     [rbp+57h+pOwner], rsi
0x14001964b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14001964f  mov     [rbp+57h+var_40], rax
0x140019653  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x140019657  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x14001965a  movups  [rbp+57h+var_50], xmm0
0x14001965e  call    ?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)
0x140019663  mov     ebx, eax
0x140019665  test    eax, eax
0x140019667  jz      short loc_14001967B
0x140019669  lea     r9, aAmiutilityinit_0; "AmiUtilityInitSecurityDescriptor failed"...
0x140019670  mov     r8d, 402h
0x140019676  jmp     loc_14001971C
0x14001967b  lea     rax, [rbp+57h+pOwner]
0x14001967f  mov     r9d, 220h; SubAuthority1
0x140019685  mov     [rsp+0D0h+Sid], rax; Sid
0x14001968a  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14001968e  mov     [rsp+0D0h+SubAuthority7], esi; SubAuthority7
0x140019692  mov     r8d, 20h ; ' '; SubAuthority0
0x140019698  mov     [rsp+0D0h+SubAuthority6], esi; SubAuthority6
0x14001969c  mov     dl, 2; SubAuthorityCount
0x14001969e  mov     [rsp+0D0h+SubAuthority5], esi; SubAuthority5
0x1400196a2  mov     [rsp+0D0h+SubAuthority4], esi; SubAuthority4
0x1400196a6  mov     [rsp+0D0h+SubAuthority3], esi; SubAuthority3
0x1400196aa  mov     dword ptr [rsp+0D0h+SubAuthority2], esi; SubAuthority2
0x1400196ae  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400196b4  test    eax, eax
0x1400196b6  jns     short loc_1400196D1
0x1400196b8  mov     ecx, eax; Status
0x1400196ba  call    cs:__imp_RtlNtStatusToDosError
0x1400196c0  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x1400196c7  mov     r8d, 417h
0x1400196cd  mov     ebx, eax
0x1400196cf  jmp     short loc_14001971C
0x1400196d1  mov     rdx, [rbp+57h+pOwner]; pOwner
0x1400196d5  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400196d9  xor     r8d, r8d; bOwnerDefaulted
0x1400196dc  call    cs:__imp_SetSecurityDescriptorOwner
0x1400196e2  test    eax, eax
0x1400196e4  jnz     short loc_1400196FD
0x1400196e6  call    cs:__imp_GetLastError
0x1400196ec  lea     r9, aSetsecuritydes; "SetSecurityDescriptorOwner failed [%d]"
0x1400196f3  mov     r8d, 41Eh
0x1400196f9  mov     ebx, eax
0x1400196fb  jmp     short loc_14001971C
0x1400196fd  lea     rdx, [rbp+57h+pSecurityDescriptor]; void *
0x140019701  mov     rcx, rdi; HKEY
0x140019704  call    ?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z; AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)
0x140019709  mov     ebx, eax
0x14001970b  test    eax, eax
0x14001970d  jz      short loc_140019731
0x14001970f  lea     r9, aAmifixkeypermi_0; "AmiFixKeyPermissionsRecursiveHelper fai"...
0x140019716  mov     r8d, 425h
0x14001971c  lea     rdx, aAmifixkeypermi_2; "AmiFixKeyPermissionsRecursive"
0x140019723  mov     dword ptr [rsp+0D0h+SubAuthority2], eax
0x140019727  mov     ecx, 1
0x14001972c  call    AslLogCallPrintf
0x140019731  mov     rcx, [rbp+57h+hMem]; hMem
0x140019735  test    rcx, rcx
0x140019738  jz      short loc_140019744
0x14001973a  call    cs:__imp_LocalFree
0x140019740  mov     [rbp+57h+hMem], rsi
0x140019744  mov     rcx, [rbp+57h+pOwner]; Sid
0x140019748  test    rcx, rcx
0x14001974b  jz      short loc_140019753
0x14001974d  call    cs:__imp_RtlFreeSid
0x140019753  mov     eax, ebx
0x140019755  mov     rcx, [rbp+57h+var_30]
0x140019759  xor     rcx, rsp; StackCookie
0x14001975c  call    __security_check_cookie
0x140019761  add     rsp, 0B8h
0x140019768  pop     rdi
0x140019769  pop     rsi
0x14001976a  pop     rbx
0x14001976b  pop     rbp
0x14001976c  retn
```
