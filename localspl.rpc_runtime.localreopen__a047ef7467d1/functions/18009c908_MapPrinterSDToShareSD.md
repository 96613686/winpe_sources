# MapPrinterSDToShareSD

- ea: `0x18009c908`
- end: `0x18009ca79`
- name: `MapPrinterSDToShareSD`
- size: `369`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800930e0`
- `0x1800932c8`
- `0x18009353c`
- `0x1800939e8`

## callees

- `0x18003ea2c`
- `0x18009c5cc`
- `0x18009c908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca53`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009c950`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009c950`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009c9af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009c9af`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009c939`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009c939`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009c9f0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009c9f0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18009c969`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18009c969`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18009c999`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18009c999`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009c981`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009c981`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009c9e2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009c9e2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009ca22`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009ca22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c9fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c9fe`

## string_xrefs

- `0x18009ca5c`: `Failed to map printer security descriptor to share.  Error %d`

## pseudocode

```c
void *__fastcall MapPrinterSDToShareSD(void *a1)
{
  int v2; // edi
  int v3; // eax
  PACL v4; // rbx
  HLOCAL v5; // rax
  void *v6; // rdi
  DWORD LastError; // eax
  PSID pGroup; // [rsp+20h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h]
  WINBOOL bOwnerDefaulted; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwBufferLength; // [rsp+90h] [rbp+30h] BYREF
  PSID pOwner; // [rsp+98h] [rbp+38h] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v12 = 0;
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  dwBufferLength = 0;
  if ( !IsValidSecurityDescriptor(a1) || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    return 0;
  if ( GetSecurityDescriptorOwner(a1, &pOwner, &bOwnerDefaulted) )
  {
    v2 = 0;
    SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted);
  }
  else
  {
    v2 = 1;
  }
  if ( GetSecurityDescriptorGroup(a1, &pGroup, &bOwnerDefaulted) )
    SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bOwnerDefaulted);
  else
    v2 = 1;
  v3 = ProcessSecurityDescriptorDacl(a1, &pDacl, &bOwnerDefaulted);
  v4 = pDacl;
  if ( !v3 || (SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0), v2) )
  {
    if ( v4 )
      LocalFree(v4);
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "MapPrinterSDToShareSD",
      L"Failed to map printer security descriptor to share.  Error %d",
      LastError);
    return 0;
  }
  dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  v5 = LocalAlloc(0x40u, dwBufferLength);
  v6 = v5;
  if ( !v5 )
  {
    LocalFree(v4);
    return 0;
  }
  if ( !MakeSelfRelativeSD(pSecurityDescriptor, v5, &dwBufferLength) )
  {
    LocalFree(v6);
    v6 = 0;
  }
  LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18009c908  push    rbp
0x18009c90a  push    rbx
0x18009c90b  push    rdi
0x18009c90c  mov     rbp, rsp
0x18009c90f  sub     rsp, 60h
0x18009c913  xor     eax, eax
0x18009c915  xorps   xmm0, xmm0
0x18009c918  movups  [rbp+pSecurityDescriptor], xmm0
0x18009c91c  mov     [rbp+var_10], rax
0x18009c920  mov     rbx, rcx
0x18009c923  movups  [rbp+var_20], xmm0
0x18009c927  mov     [rbp+bOwnerDefaulted], eax
0x18009c92a  mov     [rbp+pOwner], rax
0x18009c92e  mov     [rbp+pGroup], rax
0x18009c932  mov     [rbp+pDacl], rax
0x18009c936  mov     [rbp+dwBufferLength], eax
0x18009c939  call    cs:__imp_IsValidSecurityDescriptor
0x18009c93f  test    eax, eax
0x18009c941  jz      loc_18009CA6F
0x18009c947  mov     edx, 1; dwRevision
0x18009c94c  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009c950  call    cs:__imp_InitializeSecurityDescriptor
0x18009c956  test    eax, eax
0x18009c958  jz      loc_18009CA6F
0x18009c95e  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18009c962  mov     rcx, rbx; pSecurityDescriptor
0x18009c965  lea     rdx, [rbp+pOwner]; pOwner
0x18009c969  call    cs:__imp_GetSecurityDescriptorOwner
0x18009c96f  test    eax, eax
0x18009c971  jz      short loc_18009C989
0x18009c973  mov     r8d, [rbp+bOwnerDefaulted]; bOwnerDefaulted
0x18009c977  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009c97b  mov     rdx, [rbp+pOwner]; pOwner
0x18009c97f  xor     edi, edi
0x18009c981  call    cs:__imp_SetSecurityDescriptorOwner
0x18009c987  jmp     short loc_18009C98E
0x18009c989  mov     edi, 1
0x18009c98e  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18009c992  mov     rcx, rbx; pSecurityDescriptor
0x18009c995  lea     rdx, [rbp+pGroup]; pGroup
0x18009c999  call    cs:__imp_GetSecurityDescriptorGroup
0x18009c99f  test    eax, eax
0x18009c9a1  jz      short loc_18009C9B7
0x18009c9a3  mov     r8d, [rbp+bOwnerDefaulted]; bGroupDefaulted
0x18009c9a7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009c9ab  mov     rdx, [rbp+pGroup]; pGroup
0x18009c9af  call    cs:__imp_SetSecurityDescriptorGroup
0x18009c9b5  jmp     short loc_18009C9BC
0x18009c9b7  mov     edi, 1
0x18009c9bc  lea     r8, [rbp+bOwnerDefaulted]; int *
0x18009c9c0  mov     rcx, rbx; void *
0x18009c9c3  lea     rdx, [rbp+pDacl]; struct _ACL **
0x18009c9c7  call    ?ProcessSecurityDescriptorDacl@@YAHPEAXPEAPEAU_ACL@@PEAH@Z; ProcessSecurityDescriptorDacl(void *,_ACL * *,int *)
0x18009c9cc  mov     rbx, [rbp+pDacl]
0x18009c9d0  test    eax, eax
0x18009c9d2  jz      short loc_18009CA45
0x18009c9d4  xor     r9d, r9d; bDaclDefaulted
0x18009c9d7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009c9db  mov     r8, rbx; pDacl
0x18009c9de  lea     edx, [r9+1]; bDaclPresent
0x18009c9e2  call    cs:__imp_SetSecurityDescriptorDacl
0x18009c9e8  test    edi, edi
0x18009c9ea  jnz     short loc_18009CA45
0x18009c9ec  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009c9f0  call    cs:__imp_GetSecurityDescriptorLength
0x18009c9f6  mov     edx, eax; uBytes
0x18009c9f8  lea     ecx, [rdi+40h]; uFlags
0x18009c9fb  mov     [rbp+dwBufferLength], edx
0x18009c9fe  call    cs:__imp_LocalAlloc
0x18009ca04  mov     rdi, rax
0x18009ca07  test    rax, rax
0x18009ca0a  jnz     short loc_18009CA17
0x18009ca0c  mov     rcx, rbx; hMem
0x18009ca0f  call    cs:__imp_LocalFree
0x18009ca15  jmp     short loc_18009CA6F
0x18009ca17  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18009ca1b  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x18009ca1e  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18009ca22  call    cs:__imp_MakeSelfRelativeSD
0x18009ca28  test    eax, eax
0x18009ca2a  jnz     short loc_18009CA37
0x18009ca2c  mov     rcx, rdi; hMem
0x18009ca2f  call    cs:__imp_LocalFree
0x18009ca35  xor     edi, edi
0x18009ca37  mov     rcx, rbx; hMem
0x18009ca3a  call    cs:__imp_LocalFree
0x18009ca40  mov     rax, rdi
0x18009ca43  jmp     short loc_18009CA71
0x18009ca45  test    rbx, rbx
0x18009ca48  jz      short loc_18009CA53
0x18009ca4a  mov     rcx, rbx; hMem
0x18009ca4d  call    cs:__imp_LocalFree
0x18009ca53  call    cs:__imp_GetLastError
0x18009ca59  mov     r8d, eax
0x18009ca5c  lea     rdx, aFailedToMapPri; "Failed to map printer security descript"...
0x18009ca63  lea     rcx, aMapprintersdto; "MapPrinterSDToShareSD"
0x18009ca6a  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009ca6f  xor     eax, eax
0x18009ca71  add     rsp, 60h
0x18009ca75  pop     rdi
0x18009ca76  pop     rbx
0x18009ca77  pop     rbp
0x18009ca78  retn
```
