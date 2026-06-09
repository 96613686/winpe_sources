# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)

- ea: `0x180002b44`
- end: `0x180002def`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000289c`

## callees

- `0x180002b44`
- `0x180004760`
- `0x180006cf4`
- `0x180006d14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180002da0`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180002da0`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002c17`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002d68`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002c17`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002d68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002bc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002bc3`

## string_xrefs

- `0x180002c6a`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002dc6`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(
        __int64 a1)
{
  const char *v1; // r9
  __int64 v2; // rdx
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // r9
  DWORD v8; // ebx
  HANDLE v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  DWORD v12; // ebx
  HANDLE v13; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  void *pPrimaryGroup; // rax
  HRESULT v17; // eax
  int lpdwDaclSize; // [rsp+20h] [rbp-79h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+70h] [rbp-29h] BYREF
  PSID pOwner; // [rsp+78h] [rbp-21h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-19h] BYREF
  PACL pDacl; // [rsp+88h] [rbp-11h] BYREF
  void *v26; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v27[6]; // [rsp+98h] [rbp-1h] BYREF
  char v28; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  DWORD dwPrimaryGroupSize; // [rsp+100h] [rbp+67h] BYREF
  int v31; // [rsp+104h] [rbp+6Bh]
  DWORD dwOwnerSize; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+110h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+118h] [rbp+7Fh] BYREF

  v31 = HIDWORD(a1);
  v27[0] = &pDacl;
  pDacl = 0;
  v27[1] = &pSacl;
  pSacl = 0;
  v27[2] = &pOwner;
  pOwner = 0;
  v27[3] = &v26;
  v26 = 0;
  v27[4] = &pAbsoluteSecurityDescriptor;
  v27[5] = &SecurityDescriptor;
  SecurityDescriptor = 0;
  pAbsoluteSecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:(ML;;NX;;;LW)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v2 = 304;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v2,
                  (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
                  v1);
    goto LABEL_24;
  }
  if ( MakeAbsoluteSD(
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
         &dwPrimaryGroupSize)
    || GetLastError() != 122 )
  {
    v2 = 308;
    goto LABEL_23;
  }
  v3 = dwAbsoluteSecurityDescriptorSize;
  ProcessHeap = GetProcessHeap();
  pAbsoluteSecurityDescriptor = HeapAlloc(ProcessHeap, 8u, v3);
  if ( !pAbsoluteSecurityDescriptor )
  {
    v5 = 312;
LABEL_7:
    LastError = -2147024882;
    v7 = 2147942414LL;
    goto LABEL_8;
  }
  v8 = dwDaclSize;
  v9 = GetProcessHeap();
  pDacl = (PACL)HeapAlloc(v9, 8u, v8);
  if ( !pDacl )
  {
    v5 = 315;
    goto LABEL_7;
  }
  v10 = dwSaclSize;
  v11 = GetProcessHeap();
  pSacl = (PACL)HeapAlloc(v11, 8u, v10);
  if ( !pSacl )
  {
    v5 = 318;
    goto LABEL_7;
  }
  v12 = dwOwnerSize;
  v13 = GetProcessHeap();
  pOwner = HeapAlloc(v13, 8u, v12);
  if ( !pOwner )
  {
    v5 = 321;
    goto LABEL_7;
  }
  v14 = dwPrimaryGroupSize;
  v15 = GetProcessHeap();
  pPrimaryGroup = HeapAlloc(v15, 8u, v14);
  v26 = pPrimaryGroup;
  if ( !pPrimaryGroup )
  {
    v5 = 324;
    goto LABEL_7;
  }
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          pDacl,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v2 = 327;
    goto LABEL_23;
  }
  v17 = CoInitializeSecurity(pAbsoluteSecurityDescriptor, -1, 0, 0, 0, 2u, 0, 0, 0);
  LastError = v17;
  if ( v17 >= 0 )
  {
    LastError = 0;
    goto LABEL_24;
  }
  v7 = (unsigned int)v17;
  v5 = 330;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)v7,
    lpdwDaclSize);
LABEL_24:
  v28 = 0;
  _lambda_f43ef05b8ea00435162459fb60b25850_::operator()(v27);
  return LastError;
}

```

## disassembly

```asm
0x180002b44  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x180002b49  push    rbp
0x180002b4a  push    rbx
0x180002b4b  push    rsi
0x180002b4c  push    rdi
0x180002b4d  lea     rbp, [rsp-3Fh]
0x180002b52  sub     rsp, 0D8h
0x180002b59  xor     edi, edi
0x180002b5b  lea     rax, [rbp+57h+pDacl]
0x180002b5f  mov     [rbp+57h+var_58], rax
0x180002b63  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180002b67  lea     rax, [rbp+57h+var_70]
0x180002b6b  mov     [rbp+57h+pDacl], rdi
0x180002b6f  mov     [rbp+57h+var_50], rax
0x180002b73  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:("...
0x180002b7a  lea     rax, [rbp+57h+var_78]
0x180002b7e  mov     [rbp+57h+var_70], rdi
0x180002b82  mov     [rbp+57h+var_48], rax
0x180002b86  lea     edx, [rdi+1]; StringSDRevision
0x180002b89  lea     rax, [rbp+57h+var_60]
0x180002b8d  mov     [rbp+57h+var_78], rdi
0x180002b91  mov     [rbp+57h+var_40], rax
0x180002b95  xor     r9d, r9d; SecurityDescriptorSize
0x180002b98  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180002b9c  mov     [rbp+57h+var_60], rdi
0x180002ba0  mov     [rbp+57h+var_38], rax
0x180002ba4  lea     rax, [rbp+57h+SecurityDescriptor]
0x180002ba8  mov     [rbp+57h+var_30], rax
0x180002bac  mov     [rbp+57h+SecurityDescriptor], rdi
0x180002bb0  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x180002bb4  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x180002bb7  mov     [rbp+57h+dwDaclSize], edi
0x180002bba  mov     [rbp+57h+dwSaclSize], edi
0x180002bbd  mov     [rbp+57h+dwOwnerSize], edi
0x180002bc0  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x180002bc3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002bc9  test    eax, eax
0x180002bcb  jnz     short loc_180002BD7
0x180002bcd  mov     edx, 130h
0x180002bd2  jmp     loc_180002DC2
0x180002bd7  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180002bdb  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180002bdf  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180002be4  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180002be8  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x180002bed  lea     rax, [rbp+57h+dwOwnerSize]
0x180002bf1  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180002bf6  xor     r9d, r9d; pDacl
0x180002bf9  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x180002bfe  lea     rax, [rbp+57h+dwSaclSize]
0x180002c02  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180002c07  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180002c09  lea     rax, [rbp+57h+dwDaclSize]
0x180002c0d  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x180002c12  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x180002c17  call    cs:__imp_MakeAbsoluteSD
0x180002c1d  test    eax, eax
0x180002c1f  jnz     loc_180002DBD
0x180002c25  call    cs:__imp_GetLastError
0x180002c2b  cmp     eax, 7Ah ; 'z'
0x180002c2e  jnz     loc_180002DBD
0x180002c34  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180002c37  call    cs:__imp_GetProcessHeap
0x180002c3d  mov     esi, 8
0x180002c42  mov     r8d, ebx; dwBytes
0x180002c45  mov     edx, esi; dwFlags
0x180002c47  mov     rcx, rax; hHeap
0x180002c4a  call    cs:__imp_HeapAlloc
0x180002c50  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x180002c54  test    rax, rax
0x180002c57  jnz     short loc_180002C7B
0x180002c59  mov     edx, 138h; void *
0x180002c5e  mov     ebx, 8007000Eh
0x180002c63  mov     r9d, ebx; char *
0x180002c66  mov     rcx, [rbp+5Fh]; this
0x180002c6a  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c76  jmp     loc_180002DD4
0x180002c7b  mov     ebx, [rbp+57h+dwDaclSize]
0x180002c7e  call    cs:__imp_GetProcessHeap
0x180002c84  mov     r8d, ebx; dwBytes
0x180002c87  mov     edx, esi; dwFlags
0x180002c89  mov     rcx, rax; hHeap
0x180002c8c  call    cs:__imp_HeapAlloc
0x180002c92  mov     [rbp+57h+pDacl], rax
0x180002c96  test    rax, rax
0x180002c99  jnz     short loc_180002CA2
0x180002c9b  mov     edx, 13Bh
0x180002ca0  jmp     short loc_180002C5E
0x180002ca2  mov     ebx, [rbp+57h+dwSaclSize]
0x180002ca5  call    cs:__imp_GetProcessHeap
0x180002cab  mov     r8d, ebx; dwBytes
0x180002cae  mov     edx, esi; dwFlags
0x180002cb0  mov     rcx, rax; hHeap
0x180002cb3  call    cs:__imp_HeapAlloc
0x180002cb9  mov     [rbp+57h+var_70], rax
0x180002cbd  test    rax, rax
0x180002cc0  jnz     short loc_180002CC9
0x180002cc2  mov     edx, 13Eh
0x180002cc7  jmp     short loc_180002C5E
0x180002cc9  mov     ebx, [rbp+57h+dwOwnerSize]
0x180002ccc  call    cs:__imp_GetProcessHeap
0x180002cd2  mov     r8d, ebx; dwBytes
0x180002cd5  mov     edx, esi; dwFlags
0x180002cd7  mov     rcx, rax; hHeap
0x180002cda  call    cs:__imp_HeapAlloc
0x180002ce0  mov     [rbp+57h+var_78], rax
0x180002ce4  test    rax, rax
0x180002ce7  jnz     short loc_180002CF3
0x180002ce9  mov     edx, 141h
0x180002cee  jmp     loc_180002C5E
0x180002cf3  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x180002cf6  call    cs:__imp_GetProcessHeap
0x180002cfc  mov     r8d, ebx; dwBytes
0x180002cff  mov     edx, esi; dwFlags
0x180002d01  mov     rcx, rax; hHeap
0x180002d04  call    cs:__imp_HeapAlloc
0x180002d0a  mov     [rbp+57h+var_60], rax
0x180002d0e  test    rax, rax
0x180002d11  jnz     short loc_180002D1D
0x180002d13  mov     edx, 144h
0x180002d18  jmp     loc_180002C5E
0x180002d1d  mov     r9, [rbp+57h+pDacl]; pDacl
0x180002d21  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x180002d25  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180002d29  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180002d2d  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x180002d32  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180002d36  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x180002d3b  lea     rax, [rbp+57h+dwOwnerSize]
0x180002d3f  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180002d44  mov     rax, [rbp+57h+var_78]
0x180002d48  mov     [rsp+0F0h+pOwner], rax; pOwner
0x180002d4d  lea     rax, [rbp+57h+dwSaclSize]
0x180002d51  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180002d56  mov     rax, [rbp+57h+var_70]
0x180002d5a  mov     [rsp+0F0h+pSacl], rax; pSacl
0x180002d5f  lea     rax, [rbp+57h+dwDaclSize]
0x180002d63  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x180002d68  call    cs:__imp_MakeAbsoluteSD
0x180002d6e  test    eax, eax
0x180002d70  jnz     short loc_180002D79
0x180002d72  mov     edx, 147h
0x180002d77  jmp     short loc_180002DC2
0x180002d79  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x180002d7d  xor     r9d, r9d; pReserved1
0x180002d80  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x180002d85  xor     r8d, r8d; asAuthSvc
0x180002d88  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x180002d8c  or      edx, 0FFFFFFFFh; cAuthSvc
0x180002d8f  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x180002d94  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x180002d9c  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x180002da0  call    cs:__imp_CoInitializeSecurity
0x180002da6  mov     ebx, eax
0x180002da8  test    eax, eax
0x180002daa  jns     short loc_180002DB9
0x180002dac  mov     r9d, eax
0x180002daf  mov     edx, 14Ah
0x180002db4  jmp     loc_180002C66
0x180002db9  mov     ebx, edi
0x180002dbb  jmp     short loc_180002DD4
0x180002dbd  mov     edx, 134h; void *
0x180002dc2  mov     rcx, [rbp+5Fh]; this
0x180002dc6  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002dcd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002dd2  mov     ebx, eax
0x180002dd4  lea     rcx, [rbp+57h+var_58]
0x180002dd8  mov     [rbp+57h+var_28], dil
0x180002ddc  call    ??R_lambda_f43ef05b8ea00435162459fb60b25850_@@QEBA@XZ; _lambda_f43ef05b8ea00435162459fb60b25850_::operator()(void)
0x180002de1  mov     eax, ebx
0x180002de3  add     rsp, 0D8h
0x180002dea  pop     rdi
0x180002deb  pop     rsi
0x180002dec  pop     rbx
0x180002ded  pop     rbp
0x180002dee  retn
```
