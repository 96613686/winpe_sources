# FwppSecurityDescriptorSetInfo

- ea: `0x180010b50`
- end: `0x180010c5c`
- name: `FwppSecurityDescriptorSetInfo`
- size: `268`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PACL Dacl, PACL Sacl)`
- caller_count: `15`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800140f0`
- `0x180014a00`
- `0x180014eb0`
- `0x180014fc0`
- `0x180015b70`
- `0x180016ad0`
- `0x180017980`
- `0x180017e40`
- `0x1800184d0`
- `0x180018ba0`
- `0x180019590`
- `0x180019aa0`
- `0x18001a790`
- `0x18001bba0`
- `0x18001ef70`

## callees

- `0x180007e38`
- `0x180010b50`
- `0x180011500`

## import_xrefs

- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180010c19`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180010c19`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180010beb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180010beb`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180010bbf`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180010bbf`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010b94`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010b94`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010b69`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010b69`

## string_xrefs

- `0x180010b79`: `RtlCreateSecurityDescriptor`
- `0x180010ba4`: `RtlSetOwnerSecurityDescriptor`
- `0x180010bcf`: `RtlSetGroupSecurityDescriptor`
- `0x180010bfb`: `RtlSetDaclSecurityDescriptor`
- `0x180010c29`: `RtlSetSaclSecurityDescriptor`
- `0x180010c40`: `FwppSecurityDescriptorSetInfo`

## pseudocode

```c
__int64 __fastcall FwppSecurityDescriptorSetInfo(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        char a2,
        void *a3,
        void *a4,
        PACL Dacl,
        PACL Sacl)
{
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax

  v10 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v10 >= 0 )
  {
    if ( (a2 & 1) != 0 && (v10 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0), v10 < 0) )
    {
      v12 = "RtlSetOwnerSecurityDescriptor";
    }
    else if ( (a2 & 2) != 0 && (v10 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0), v10 < 0) )
    {
      v12 = "RtlSetGroupSecurityDescriptor";
    }
    else if ( (a2 & 4) != 0 && (v10 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0), v10 < 0) )
    {
      v12 = "RtlSetDaclSecurityDescriptor";
    }
    else
    {
      v13 = 0;
      if ( (a2 & 8) == 0 )
        return v13;
      v10 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0);
      if ( v10 >= 0 )
        return v13;
      v12 = "RtlSetSaclSecurityDescriptor";
    }
  }
  else
  {
    v12 = "RtlCreateSecurityDescriptor";
  }
  v14 = WfpReportSysErrorAsNtStatus(v11, v12, (unsigned int)v10);
  v13 = v14;
  if ( v14 )
    WfpReportError(v14, "FwppSecurityDescriptorSetInfo");
  return v13;
}

```

## disassembly

```asm
0x180010b50  push    rbx
0x180010b52  push    rbp
0x180010b53  push    rsi
0x180010b54  push    rdi
0x180010b55  sub     rsp, 28h
0x180010b59  mov     edi, edx
0x180010b5b  mov     rbp, r9
0x180010b5e  mov     edx, 1; Revision
0x180010b63  mov     rbx, r8
0x180010b66  mov     rsi, rcx
0x180010b69  call    cs:__imp_RtlCreateSecurityDescriptor
0x180010b70  nop     dword ptr [rax+rax+00h]
0x180010b75  test    eax, eax
0x180010b77  jns     short loc_180010B85
0x180010b79  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x180010b80  jmp     loc_180010C30
0x180010b85  test    dil, 1
0x180010b89  jz      short loc_180010BB0
0x180010b8b  xor     r8d, r8d; OwnerDefaulted
0x180010b8e  mov     rdx, rbx; Owner
0x180010b91  mov     rcx, rsi; SecurityDescriptor
0x180010b94  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180010b9b  nop     dword ptr [rax+rax+00h]
0x180010ba0  test    eax, eax
0x180010ba2  jns     short loc_180010BB0
0x180010ba4  lea     rdx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor"
0x180010bab  jmp     loc_180010C30
0x180010bb0  test    dil, 2
0x180010bb4  jz      short loc_180010BD8
0x180010bb6  xor     r8d, r8d; GroupDefaulted
0x180010bb9  mov     rdx, rbp; Group
0x180010bbc  mov     rcx, rsi; SecurityDescriptor
0x180010bbf  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180010bc6  nop     dword ptr [rax+rax+00h]
0x180010bcb  test    eax, eax
0x180010bcd  jns     short loc_180010BD8
0x180010bcf  lea     rdx, aRtlsetgroupsec; "RtlSetGroupSecurityDescriptor"
0x180010bd6  jmp     short loc_180010C30
0x180010bd8  test    dil, 4
0x180010bdc  jz      short loc_180010C04
0x180010bde  mov     r8, [rsp+48h+Dacl]; Dacl
0x180010be3  xor     r9d, r9d; DaclDefaulted
0x180010be6  mov     dl, 1; DaclPresent
0x180010be8  mov     rcx, rsi; SecurityDescriptor
0x180010beb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180010bf2  nop     dword ptr [rax+rax+00h]
0x180010bf7  test    eax, eax
0x180010bf9  jns     short loc_180010C04
0x180010bfb  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x180010c02  jmp     short loc_180010C30
0x180010c04  xor     ebx, ebx
0x180010c06  test    dil, 8
0x180010c0a  jz      short loc_180010C4F
0x180010c0c  mov     r8, [rsp+48h+Sacl]; Sacl
0x180010c11  xor     r9d, r9d; SaclDefaulted
0x180010c14  mov     dl, 1; SaclPresent
0x180010c16  mov     rcx, rsi; SecurityDescriptor
0x180010c19  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180010c20  nop     dword ptr [rax+rax+00h]
0x180010c25  test    eax, eax
0x180010c27  jns     short loc_180010C4F
0x180010c29  lea     rdx, aRtlsetsaclsecu; "RtlSetSaclSecurityDescriptor"
0x180010c30  mov     r8d, eax
0x180010c33  call    WfpReportSysErrorAsNtStatus
0x180010c38  mov     rbx, rax
0x180010c3b  test    rax, rax
0x180010c3e  jz      short loc_180010C4F
0x180010c40  lea     rdx, aFwppsecurityde_0; "FwppSecurityDescriptorSetInfo"
0x180010c47  mov     rcx, rax
0x180010c4a  call    WfpReportError
0x180010c4f  mov     rax, rbx
0x180010c52  add     rsp, 28h
0x180010c56  pop     rdi
0x180010c57  pop     rsi
0x180010c58  pop     rbp
0x180010c59  pop     rbx
0x180010c5a  retn
```
