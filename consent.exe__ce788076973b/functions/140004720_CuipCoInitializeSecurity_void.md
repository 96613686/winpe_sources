# CuipCoInitializeSecurity(void)

- ea: `0x140004720`
- end: `0x14000497f`
- name: `?CuipCoInitializeSecurity@@YAKXZ`
- size: `607`
- prototype: `DWORD(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140004720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000496a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000496a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004972`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400048df`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400048df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400048f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400048fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400048f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400048fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004948`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400047f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004803`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004811`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000481f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000482d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400047f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004803`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004811`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000481f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000482d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400047b4`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400048a4`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400047b4`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400048a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000474a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000474a`

## pseudocode

```c
DWORD CuipCoInitializeSecurity(void)
{
  DWORD LastError; // ebx
  HLOCAL v1; // rdi
  struct _ACL *v2; // rsi
  struct _ACL *pSacl; // r14
  HLOCAL pOwner; // r15
  HLOCAL pPrimaryGroup; // rax
  void *v6; // r12
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp+Fh] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+C0h] [rbp+67h] BYREF
  DWORD dwOwnerSize; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+D0h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+D8h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0x3;;;IU)(A;;0x3;;;SY)S:(ML;;NX;;;HI)",
          1u,
          &SecurityDescriptor,
          0) )
    return GetLastError();
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  MakeAbsoluteSD(
    SecurityDescriptor,
    0,
    &dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    &dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v1 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
    v2 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
    pSacl = (struct _ACL *)LocalAlloc(0, dwSaclSize);
    pOwner = LocalAlloc(0, dwOwnerSize);
    pPrimaryGroup = LocalAlloc(0, dwPrimaryGroupSize);
    v6 = pPrimaryGroup;
    if ( v1 && v2 && pSacl && pOwner && pPrimaryGroup )
    {
      if ( MakeAbsoluteSD(
             SecurityDescriptor,
             v1,
             &dwAbsoluteSecurityDescriptorSize,
             v2,
             &dwDaclSize,
             pSacl,
             &dwSaclSize,
             pOwner,
             &dwOwnerSize,
             pPrimaryGroup,
             &dwPrimaryGroupSize) )
      {
        LastError = 0;
        if ( CoInitializeSecurity(v1, -1, 0, 0, 6u, 2u, 0, 0, 0) < 0 )
          LastError = 5;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 8;
    }
    LocalFree(v6);
    LocalFree(pOwner);
    LocalFree(pSacl);
    LocalFree(v2);
    LocalFree(v1);
  }
  LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x140004720  push    rbp
0x140004722  push    r13
0x140004724  lea     rbp, [rsp-4Fh]
0x140004729  sub     rsp, 0A8h
0x140004730  xor     r13d, r13d
0x140004733  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140004737  xor     r9d, r9d; SecurityDescriptorSize
0x14000473a  mov     [rbp+57h+SecurityDescriptor], r13
0x14000473e  mov     edx, 1; StringSDRevision
0x140004743  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x3;;;IU)(A;;0x3;;;SY)S:("...
0x14000474a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140004750  test    eax, eax
0x140004752  jz      loc_14000496A
0x140004758  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x14000475c  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140004760  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140004765  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140004769  mov     [rsp+0B0h+pPrimaryGroup], r13; pPrimaryGroup
0x14000476e  lea     rax, [rbp+57h+dwOwnerSize]
0x140004772  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140004777  xor     r9d, r9d; pDacl
0x14000477a  mov     [rsp+0B0h+pOwner], r13; pOwner
0x14000477f  lea     rax, [rbp+57h+dwSaclSize]
0x140004783  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x140004788  xor     edx, edx; pAbsoluteSecurityDescriptor
0x14000478a  lea     rax, [rbp+57h+dwDaclSize]
0x14000478e  mov     [rsp+0B0h+pSacl], r13; pSacl
0x140004793  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x140004798  mov     [rsp+0B0h+var_10], rbx
0x1400047a0  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x1400047a4  mov     [rbp+57h+dwDaclSize], r13d
0x1400047a8  mov     [rbp+57h+dwSaclSize], r13d
0x1400047ac  mov     [rbp+57h+dwOwnerSize], r13d
0x1400047b0  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x1400047b4  call    cs:__imp_MakeAbsoluteSD
0x1400047ba  call    cs:__imp_GetLastError
0x1400047c0  mov     ebx, eax
0x1400047c2  cmp     eax, 7Ah ; 'z'
0x1400047c5  jnz     loc_140004944
0x1400047cb  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x1400047ce  xor     ecx, ecx; uFlags
0x1400047d0  mov     [rsp+0B0h+var_18], rsi
0x1400047d8  mov     [rsp+0B0h+var_20], rdi
0x1400047e0  mov     [rsp+0B0h+var_28], r12
0x1400047e8  mov     [rsp+0B0h+var_30], r14
0x1400047f0  mov     [rsp+0B0h+var_38], r15
0x1400047f5  call    cs:__imp_LocalAlloc
0x1400047fb  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x1400047fe  xor     ecx, ecx; uFlags
0x140004800  mov     rdi, rax
0x140004803  call    cs:__imp_LocalAlloc
0x140004809  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x14000480c  xor     ecx, ecx; uFlags
0x14000480e  mov     rsi, rax
0x140004811  call    cs:__imp_LocalAlloc
0x140004817  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x14000481a  xor     ecx, ecx; uFlags
0x14000481c  mov     r14, rax
0x14000481f  call    cs:__imp_LocalAlloc
0x140004825  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x140004828  xor     ecx, ecx; uFlags
0x14000482a  mov     r15, rax
0x14000482d  call    cs:__imp_LocalAlloc
0x140004833  mov     r12, rax
0x140004836  test    rdi, rdi
0x140004839  jz      loc_140004963
0x14000483f  test    rsi, rsi
0x140004842  jz      loc_140004963
0x140004848  test    r14, r14
0x14000484b  jz      loc_140004963
0x140004851  test    r15, r15
0x140004854  jz      loc_140004963
0x14000485a  test    rax, rax
0x14000485d  jz      loc_140004963
0x140004863  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140004867  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x14000486b  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140004870  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140004874  mov     [rsp+0B0h+pPrimaryGroup], r12; pPrimaryGroup
0x140004879  lea     rax, [rbp+57h+dwOwnerSize]
0x14000487d  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140004882  mov     r9, rsi; pDacl
0x140004885  mov     [rsp+0B0h+pOwner], r15; pOwner
0x14000488a  lea     rax, [rbp+57h+dwSaclSize]
0x14000488e  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x140004893  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x140004896  lea     rax, [rbp+57h+dwDaclSize]
0x14000489a  mov     [rsp+0B0h+pSacl], r14; pSacl
0x14000489f  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x1400048a4  call    cs:__imp_MakeAbsoluteSD
0x1400048aa  test    eax, eax
0x1400048ac  jz      loc_140004972
0x1400048b2  mov     [rsp+0B0h+lpdwOwnerSize], r13; pReserved3
0x1400048b7  xor     r9d, r9d; pReserved1
0x1400048ba  mov     dword ptr [rsp+0B0h+pOwner], r13d; dwCapabilities
0x1400048bf  xor     r8d, r8d; asAuthSvc
0x1400048c2  mov     [rsp+0B0h+lpdwSaclSize], r13; pAuthList
0x1400048c7  mov     edx, 0FFFFFFFFh; cAuthSvc
0x1400048cc  mov     dword ptr [rsp+0B0h+pSacl], 2; dwImpLevel
0x1400048d4  mov     rcx, rdi; pSecDesc
0x1400048d7  mov     dword ptr [rsp+0B0h+lpdwDaclSize], 6; dwAuthnLevel
0x1400048df  call    cs:__imp_CoInitializeSecurity
0x1400048e5  mov     ebx, r13d
0x1400048e8  mov     ecx, 5
0x1400048ed  test    eax, eax
0x1400048ef  cmovs   ebx, ecx
0x1400048f2  mov     rcx, r12; hMem
0x1400048f5  call    cs:__imp_LocalFree
0x1400048fb  mov     rcx, r15; hMem
0x1400048fe  call    cs:__imp_LocalFree
0x140004904  mov     rcx, r14; hMem
0x140004907  call    cs:__imp_LocalFree
0x14000490d  mov     rcx, rsi; hMem
0x140004910  call    cs:__imp_LocalFree
0x140004916  mov     rcx, rdi; hMem
0x140004919  call    cs:__imp_LocalFree
0x14000491f  mov     r15, [rsp+0B0h+var_38]
0x140004924  mov     r14, [rsp+0B0h+var_30]
0x14000492c  mov     r12, [rsp+0B0h+var_28]
0x140004934  mov     rdi, [rsp+0B0h+var_20]
0x14000493c  mov     rsi, [rsp+0B0h+var_18]
0x140004944  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x140004948  call    cs:__imp_LocalFree
0x14000494e  mov     eax, ebx
0x140004950  mov     rbx, [rsp+0B0h+var_10]
0x140004958  add     rsp, 0A8h
0x14000495f  pop     r13
0x140004961  pop     rbp
0x140004962  retn
0x140004963  mov     ebx, 8
0x140004968  jmp     short loc_1400048F2
0x14000496a  call    cs:__imp_GetLastError
0x140004970  jmp     short loc_140004958
0x140004972  call    cs:__imp_GetLastError
0x140004978  mov     ebx, eax
0x14000497a  jmp     loc_1400048F2
```
